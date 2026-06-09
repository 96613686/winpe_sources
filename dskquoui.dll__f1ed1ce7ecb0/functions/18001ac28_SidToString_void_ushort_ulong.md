# SidToString(void *,ushort *,ulong *)

- ea: `0x18001ac28`
- end: `0x18001aca4`
- name: `?SidToString@@YAHPEAXPEAGPEAK@Z`
- size: `124`
- prototype: `int(void *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e4fc`
- `0x1800151c0`

## callees

- `0x180005410`
- `0x18001ac28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ac6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ac8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ac4a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001ac4a`
- `KERNEL32!lstrlenW` at `0x18001ac5b`
- `KERNEL32!lstrlenW` at `0x18001ac5b`

## pseudocode

```c
__int64 __fastcall SidToString(void *a1, unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  LPCWSTR lpString; // [rsp+48h] [rbp+20h] BYREF

  lpString = 0;
  v5 = ConvertSidToStringSidW(a1, (LPWSTR *)&lpString);
  if ( v5 )
  {
    v6 = lstrlenW(lpString) + 1;
    if ( *a3 >= v6 )
    {
      StringCchCopyW(a2, *a3, lpString);
    }
    else
    {
      *a3 = v6;
      SetLastError(0x7Au);
      v5 = 0;
    }
    LocalFree((HLOCAL)lpString);
  }
  return v5;
}

```

## disassembly

```asm
0x18001ac28  mov     rax, rsp
0x18001ac2b  mov     [rax+8], rbx
0x18001ac2f  mov     [rax+10h], rsi
0x18001ac33  push    rdi
0x18001ac34  sub     rsp, 20h
0x18001ac38  mov     rsi, rdx
0x18001ac3b  mov     qword ptr [rax+20h], 0
0x18001ac43  lea     rdx, [rax+20h]; StringSid
0x18001ac47  mov     rdi, r8
0x18001ac4a  call    cs:__imp_ConvertSidToStringSidW
0x18001ac50  mov     ebx, eax
0x18001ac52  test    eax, eax
0x18001ac54  jz      short loc_18001AC92
0x18001ac56  mov     rcx, [rsp+28h+lpString]; lpString
0x18001ac5b  call    cs:__imp_lstrlenW
0x18001ac61  inc     eax
0x18001ac63  cmp     [rdi], eax
0x18001ac65  jnb     short loc_18001AC78
0x18001ac67  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18001ac6c  mov     [rdi], eax
0x18001ac6e  call    cs:__imp_SetLastError
0x18001ac74  xor     ebx, ebx
0x18001ac76  jmp     short loc_18001AC87
0x18001ac78  mov     edx, [rdi]; unsigned __int64
0x18001ac7a  mov     rcx, rsi; unsigned __int16 *
0x18001ac7d  mov     r8, [rsp+28h+lpString]; unsigned __int16 *
0x18001ac82  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac87  mov     rcx, [rsp+28h+lpString]; hMem
0x18001ac8c  call    cs:__imp_LocalFree
0x18001ac92  mov     rsi, [rsp+28h+arg_8]
0x18001ac97  mov     eax, ebx
0x18001ac99  mov     rbx, [rsp+28h+arg_0]
0x18001ac9e  add     rsp, 20h
0x18001aca2  pop     rdi
0x18001aca3  retn
```
