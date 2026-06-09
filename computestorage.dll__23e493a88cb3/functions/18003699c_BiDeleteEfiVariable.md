# BiDeleteEfiVariable

- ea: `0x18003699c`
- end: `0x180036b0f`
- name: `BiDeleteEfiVariable`
- size: `371`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180036d98`

## callees

- `0x180002690`
- `0x180034254`
- `0x180034db0`
- `0x1800350ac`
- `0x1800352f8`
- `0x18003699c`
- `0x180049010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180036a5c`
- `ntdll!RtlInitUnicodeString` at `0x180036a5c`

## string_xrefs

- `0x180036acb`: `Failed to delete "%ws" variable. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteEfiVariable(PCWSTR SourceString)
{
  NTSTATUS v2; // ebx
  unsigned int v3; // eax
  int v4; // eax
  int v6; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall *v7)(struct _UNICODE_STRING *, _DWORD *, _QWORD, int *, _QWORD); // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall *v8)(struct _UNICODE_STRING *, _DWORD *, _QWORD, _QWORD, int); // [rsp+40h] [rbp-40h] BYREF
  __int64 v9; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v11[4]; // [rsp+60h] [rbp-20h] BYREF

  v11[0] = -1947934879;
  v11[1] = 299013066;
  v11[2] = -536867414;
  v11[3] = -1943338088;
  DestinationString = 0;
  v9 = 0;
  v8 = 0;
  v7 = 0;
  v6 = 0;
  if ( (int)BiLookupNtdllProcedureAddress("ZwQuerySystemEnvironmentValueEx", (PVOID *)&v7) < 0
    || (int)BiLookupNtdllProcedureAddress("ZwSetSystemEnvironmentValueEx", (PVOID *)&v8) < 0 )
  {
    return (unsigned int)-1073741637;
  }
  else
  {
    v2 = BiAcquirePrivilege(0x16u, (__int64)&v9);
    if ( v2 >= 0 )
    {
      v6 = 0;
      RtlInitUnicodeString(&DestinationString, SourceString);
      v3 = v7(&DestinationString, v11, 0, &v6, 0);
      v2 = v3;
      if ( v3 == -1073741789 )
      {
        v4 = v8(&DestinationString, v11, 0, 0, 1);
        v2 = v4;
        if ( v4 < 0 )
          BiLogMessage(4, L"Failed to delete \"%ws\" variable. Status: %x", SourceString, (unsigned int)v4);
      }
      else if ( v3 == -1073741568 )
      {
        v2 = 0;
      }
      else
      {
        BiLogMessage(4, L"Failed to query \"%ws\" variable. Status: %x", SourceString, v3);
      }
      BiReleasePrivilege((unsigned int *)&v9);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003699c  mov     [rsp-8+arg_8], rbx
0x1800369a1  mov     [rsp-8+arg_10], rdi
0x1800369a6  push    rbp
0x1800369a7  mov     rbp, rsp
0x1800369aa  sub     rsp, 80h
0x1800369b1  mov     rax, cs:__security_cookie
0x1800369b8  xor     rax, rsp
0x1800369bb  mov     [rbp+var_10], rax
0x1800369bf  mov     rdi, rcx
0x1800369c2  mov     [rbp+var_20], 8BE4DF61h
0x1800369c9  xorps   xmm0, xmm0
0x1800369cc  mov     [rbp+var_1C], 11D293CAh
0x1800369d3  lea     rcx, aZwquerysysteme; "ZwQuerySystemEnvironmentValueEx"
0x1800369da  mov     [rbp+var_18], 0E0000DAAh
0x1800369e1  lea     rdx, [rbp+var_48]
0x1800369e5  mov     [rbp+var_14], 8C2B0398h
0x1800369ec  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800369f0  mov     [rbp+var_38], 0
0x1800369f8  mov     [rbp+var_40], 0
0x180036a00  mov     [rbp+var_48], 0
0x180036a08  mov     [rbp+var_50], 0
0x180036a0f  call    BiLookupNtdllProcedureAddress
0x180036a14  test    eax, eax
0x180036a16  jns     short loc_180036A22
0x180036a18  mov     ebx, 0C00000BBh
0x180036a1d  jmp     loc_180036AEB
0x180036a22  lea     rdx, [rbp+var_40]
0x180036a26  lea     rcx, aZwsetsystemenv; "ZwSetSystemEnvironmentValueEx"
0x180036a2d  call    BiLookupNtdllProcedureAddress
0x180036a32  test    eax, eax
0x180036a34  js      short loc_180036A18
0x180036a36  lea     rdx, [rbp+var_38]
0x180036a3a  mov     ecx, 16h
0x180036a3f  call    BiAcquirePrivilege
0x180036a44  mov     ebx, eax
0x180036a46  test    eax, eax
0x180036a48  js      loc_180036AEB
0x180036a4e  mov     rdx, rdi; SourceString
0x180036a51  mov     [rbp+var_50], 0
0x180036a58  lea     rcx, [rbp+DestinationString]; DestinationString
0x180036a5c  call    cs:__imp_RtlInitUnicodeString
0x180036a63  nop     dword ptr [rax+rax+00h]
0x180036a68  mov     rax, [rbp+var_48]
0x180036a6c  lea     r9, [rbp+var_50]
0x180036a70  xor     r8d, r8d
0x180036a73  mov     [rsp+80h+var_60], 0
0x180036a7c  lea     rdx, [rbp+var_20]
0x180036a80  lea     rcx, [rbp+DestinationString]
0x180036a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a89  mov     ebx, eax
0x180036a8b  cmp     eax, 0C0000023h
0x180036a90  jz      short loc_180036AA6
0x180036a92  cmp     eax, 0C0000100h
0x180036a97  jnz     short loc_180036A9D
0x180036a99  xor     ebx, ebx
0x180036a9b  jmp     short loc_180036AE2
0x180036a9d  lea     rdx, aFailedToQueryW; "Failed to query \"%ws\" variable. Statu"...
0x180036aa4  jmp     short loc_180036AD2
0x180036aa6  mov     rax, [rbp+var_40]
0x180036aaa  lea     rdx, [rbp+var_20]
0x180036aae  xor     r9d, r9d
0x180036ab1  mov     dword ptr [rsp+80h+var_60], 1
0x180036ab9  xor     r8d, r8d
0x180036abc  lea     rcx, [rbp+DestinationString]
0x180036ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036ac5  mov     ebx, eax
0x180036ac7  test    eax, eax
0x180036ac9  jns     short loc_180036AE2
0x180036acb  lea     rdx, aFailedToDelete_0; "Failed to delete \"%ws\" variable. Stat"...
0x180036ad2  mov     r9d, eax
0x180036ad5  mov     r8, rdi
0x180036ad8  mov     ecx, 4
0x180036add  call    BiLogMessage
0x180036ae2  lea     rcx, [rbp+var_38]
0x180036ae6  call    BiReleasePrivilege
0x180036aeb  mov     eax, ebx
0x180036aed  mov     rcx, [rbp+var_10]
0x180036af1  xor     rcx, rsp; StackCookie
0x180036af4  call    __security_check_cookie
0x180036af9  lea     r11, [rsp+80h+var_s0]
0x180036b01  mov     rbx, [r11+18h]
0x180036b05  mov     rdi, [r11+20h]
0x180036b09  mov     rsp, r11
0x180036b0c  pop     rbp
0x180036b0d  retn
```
