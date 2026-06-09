# SetKernelHandleToLowIL(void *)

- ea: `0x180044400`
- end: `0x18004446c`
- name: `?SetKernelHandleToLowIL@@YAJPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180044400`
- `0x180044474`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044455`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180044447`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004441e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18004441e`

## pseudocode

```c
__int64 __fastcall SetKernelHandleToLowIL(void *a1)
{
  enum _SE_OBJECT_TYPE v2; // edx
  unsigned int v3; // ebx
  signed int LastError; // eax
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(L"LW", &Sid) )
  {
    v3 = SetHandleIntegrityLevel(a1, v2, Sid, 0, 0);
    LocalFree(Sid);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180044400  push    rbx
0x180044402  sub     rsp, 30h
0x180044406  mov     rbx, rcx
0x180044409  mov     [rsp+38h+Sid], 0
0x180044412  lea     rcx, StringSid; "LW"
0x180044419  lea     rdx, [rsp+38h+Sid]; Sid
0x18004441e  call    cs:__imp_ConvertStringSidToSidW
0x180044424  test    eax, eax
0x180044426  jz      short loc_180044455
0x180044428  mov     r8, [rsp+38h+Sid]; void *
0x18004442d  xor     r9d, r9d; bool *
0x180044430  mov     rcx, rbx; void *
0x180044433  mov     [rsp+38h+var_18], 0; unsigned int
0x18004443b  call    ?SetHandleIntegrityLevel@@YAJPEAXW4_SE_OBJECT_TYPE@@0PEA_NK@Z; SetHandleIntegrityLevel(void *,_SE_OBJECT_TYPE,void *,bool *,ulong)
0x180044440  mov     rcx, [rsp+38h+Sid]; hMem
0x180044445  mov     ebx, eax
0x180044447  call    cs:__imp_LocalFree
0x18004444d  mov     eax, ebx
0x18004444f  add     rsp, 30h
0x180044453  pop     rbx
0x180044454  retn
0x180044455  call    cs:__imp_GetLastError
0x18004445b  mov     ebx, eax
0x18004445d  test    eax, eax
0x18004445f  jle     short loc_18004444D
0x180044461  movzx   ebx, ax
0x180044464  or      ebx, 80070000h
0x18004446a  jmp     short loc_18004444D
```
