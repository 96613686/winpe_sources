# BackupReadSecurityData

- ea: `0x18002e340`
- end: `0x18002e4be`
- name: `BackupReadSecurityData`
- size: `382`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030710`

## callees

- `0x18002e340`
- `0x180031108`
- `0x180051bf0`
- `0x18007a7dd`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18002e3df`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002e3df`
- `ntdll!NtQuerySecurityObject` at `0x18002e3a9`
- `ntdll!NtQuerySecurityObject` at `0x18002e44d`
- `ntdll!NtQuerySecurityObject` at `0x18002e485`
- `ntdll!NtQuerySecurityObject` at `0x18002e3a9`
- `ntdll!NtQuerySecurityObject` at `0x18002e44d`
- `ntdll!NtQuerySecurityObject` at `0x18002e485`

## pseudocode

```c
__int64 __fastcall BackupReadSecurityData(HANDLE Handle, __int64 a2, __int64 a3)
{
  ULONG *v5; // rdi
  size_t v6; // r8
  void *v7; // rcx
  NTSTATUS v8; // eax
  void *v9; // rcx
  __int64 result; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  ULONG LengthNeeded; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_BYTE *)(a3 + 20) )
  {
    if ( *(_BYTE *)(a2 + 1129) )
    {
      v5 = (ULONG *)(a2 + 1080);
      while ( 1 )
      {
        v6 = *v5;
        v7 = *(void **)(a2 + 1088);
        LengthNeeded = 0;
        memset_0(v7, 0, v6);
        v8 = NtQuerySecurityObject(Handle, 0x1007Fu, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
        if ( v8 >= 0 )
          break;
        if ( v8 != -2147483643 && v8 != -1073741789 )
        {
          v11 = NtQuerySecurityObject(Handle, 0x7Fu, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
          if ( v11 >= 0 )
            break;
          if ( v11 != -2147483643 && v11 != -1073741789 )
          {
            v12 = NtQuerySecurityObject(Handle, 0x77u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
            if ( v12 >= 0 )
              break;
            if ( v12 != -2147483643 && v12 != -1073741789 )
              return 1;
          }
        }
        result = GrowBuffer(v5, LengthNeeded);
        if ( !(_DWORD)result )
          return result;
      }
      v9 = *(void **)(a2 + 1088);
      *(_BYTE *)(a2 + 1128) = 1;
      *(_DWORD *)a2 = 3;
      *(_DWORD *)(a2 + 4) = 2;
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 1068) = 20;
      *(_QWORD *)(a2 + 8) = RtlLengthSecurityDescriptor(v9);
      *(_BYTE *)(a2 + 1129) = 0;
    }
    else if ( *(_QWORD *)(a2 + 1056) >= (__int64)*(unsigned int *)(a2 + 1068) )
    {
      BackupReadBuffer(a2, a3);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002e340  mov     [rsp+arg_0], rbx
0x18002e345  mov     [rsp+arg_8], rsi
0x18002e34a  push    rdi
0x18002e34b  sub     rsp, 30h
0x18002e34f  cmp     byte ptr [r8+14h], 0
0x18002e354  mov     rbx, rdx
0x18002e357  mov     rsi, rcx
0x18002e35a  jz      loc_18002E3F2
0x18002e360  cmp     byte ptr [rdx+469h], 0
0x18002e367  jz      loc_18002E407
0x18002e36d  lea     rdi, [rdx+438h]
0x18002e374  mov     r8d, [rdi]; Size
0x18002e377  xor     edx, edx; Val
0x18002e379  mov     rcx, [rbx+440h]; void *
0x18002e380  mov     [rsp+38h+arg_10], 0
0x18002e388  call    memset_0
0x18002e38d  mov     r9d, [rdi]; Length
0x18002e390  lea     rax, [rsp+38h+arg_10]
0x18002e395  mov     r8, [rbx+440h]; SecurityDescriptor
0x18002e39c  mov     edx, 1007Fh; SecurityInformation
0x18002e3a1  mov     rcx, rsi; Handle
0x18002e3a4  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x18002e3a9  call    cs:__imp_NtQuerySecurityObject
0x18002e3af  test    eax, eax
0x18002e3b1  js      short loc_18002E423
0x18002e3b3  mov     rcx, [rbx+440h]; SecurityDescriptor
0x18002e3ba  mov     byte ptr [rbx+468h], 1
0x18002e3c1  mov     dword ptr [rbx], 3
0x18002e3c7  mov     dword ptr [rbx+4], 2
0x18002e3ce  mov     dword ptr [rbx+10h], 0
0x18002e3d5  mov     dword ptr [rbx+42Ch], 14h
0x18002e3df  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002e3e5  mov     eax, eax
0x18002e3e7  mov     [rbx+8], rax
0x18002e3eb  mov     byte ptr [rbx+469h], 0
0x18002e3f2  mov     eax, 1
0x18002e3f7  mov     rbx, [rsp+38h+arg_0]
0x18002e3fc  mov     rsi, [rsp+38h+arg_8]
0x18002e401  add     rsp, 30h
0x18002e405  pop     rdi
0x18002e406  retn
0x18002e407  mov     ecx, [rdx+42Ch]
0x18002e40d  cmp     [rdx+420h], rcx
0x18002e414  jl      short loc_18002E3F2
0x18002e416  mov     rdx, r8
0x18002e419  mov     rcx, rbx
0x18002e41c  call    BackupReadBuffer
0x18002e421  jmp     short loc_18002E3F2
0x18002e423  cmp     eax, 80000005h
0x18002e428  jz      short loc_18002E4A5
0x18002e42a  cmp     eax, 0C0000023h
0x18002e42f  jz      short loc_18002E4A5
0x18002e431  mov     r9d, [rdi]; Length
0x18002e434  lea     rax, [rsp+38h+arg_10]
0x18002e439  mov     r8, [rbx+440h]; SecurityDescriptor
0x18002e440  mov     edx, 7Fh; SecurityInformation
0x18002e445  mov     rcx, rsi; Handle
0x18002e448  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x18002e44d  call    cs:__imp_NtQuerySecurityObject
0x18002e453  test    eax, eax
0x18002e455  jns     loc_18002E3B3
0x18002e45b  cmp     eax, 80000005h
0x18002e460  jz      short loc_18002E4A5
0x18002e462  cmp     eax, 0C0000023h
0x18002e467  jz      short loc_18002E4A5
0x18002e469  mov     r9d, [rdi]; Length
0x18002e46c  lea     rax, [rsp+38h+arg_10]
0x18002e471  mov     r8, [rbx+440h]; SecurityDescriptor
0x18002e478  mov     edx, 77h ; 'w'; SecurityInformation
0x18002e47d  mov     rcx, rsi; Handle
0x18002e480  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x18002e485  call    cs:__imp_NtQuerySecurityObject
0x18002e48b  test    eax, eax
0x18002e48d  jns     loc_18002E3B3
0x18002e493  cmp     eax, 80000005h
0x18002e498  jz      short loc_18002E4A5
0x18002e49a  cmp     eax, 0C0000023h
0x18002e49f  jnz     loc_18002E3F2
0x18002e4a5  mov     edx, [rsp+38h+arg_10]
0x18002e4a9  mov     rcx, rdi
0x18002e4ac  call    GrowBuffer
0x18002e4b1  test    eax, eax
0x18002e4b3  jnz     loc_18002E374
0x18002e4b9  jmp     loc_18002E3F7
```
