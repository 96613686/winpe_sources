# UtilDuplicateSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x180039c1c`
- end: `0x180039ceb`
- name: `?UtilDuplicateSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `207`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003b078`

## callees

- `0x1800028b4`
- `0x1800047cc`
- `0x180039c1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c9b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039c57`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180039c57`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039c91`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180039c91`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180039c43`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180039c43`

## pseudocode

```c
__int64 __fastcall UtilDuplicateSid(PSID pSourceSid, PSID *a2)
{
  signed int v4; // ebx
  DWORD LengthSid; // esi
  void *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  PSID v8; // rcx
  signed int LastError; // eax
  const struct std::nothrow_t *v10; // rdx
  PSID v11; // rcx

  if ( !a2 || !pSourceSid )
    return 2147942487LL;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    v6 = operator new[](LengthSid, (const struct std::nothrow_t *)&std::nothrow);
    v8 = *a2;
    *a2 = v6;
    if ( v8 )
      operator delete(v8, v7);
    if ( *a2 )
    {
      if ( CopySid(LengthSid, *a2, pSourceSid) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        v11 = *a2;
        *a2 = 0;
        if ( v4 >= 0 )
          v4 = -2147467259;
        if ( v11 )
          operator delete(v11, v10);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180039c1c  mov     [rsp+arg_0], rbx
0x180039c21  mov     [rsp+arg_8], rsi
0x180039c26  push    rdi
0x180039c27  sub     rsp, 20h
0x180039c2b  mov     rdi, rdx
0x180039c2e  mov     rbx, rcx
0x180039c31  test    rdx, rdx
0x180039c34  jz      loc_180039CD6
0x180039c3a  test    rcx, rcx
0x180039c3d  jz      loc_180039CD6
0x180039c43  call    cs:__imp_IsValidSid
0x180039c49  test    eax, eax
0x180039c4b  jnz     short loc_180039C54
0x180039c4d  mov     ebx, 80070057h
0x180039c52  jmp     short loc_180039CD2
0x180039c54  mov     rcx, rbx; pSid
0x180039c57  call    cs:__imp_GetLengthSid
0x180039c5d  mov     ecx, eax; unsigned __int64
0x180039c5f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039c66  mov     esi, eax
0x180039c68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180039c6d  mov     rcx, [rdi]; void *
0x180039c70  mov     [rdi], rax
0x180039c73  test    rcx, rcx
0x180039c76  jz      short loc_180039C7D
0x180039c78  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039c7d  mov     rdx, [rdi]; pDestinationSid
0x180039c80  test    rdx, rdx
0x180039c83  jnz     short loc_180039C8C
0x180039c85  mov     ebx, 8007000Eh
0x180039c8a  jmp     short loc_180039CD2
0x180039c8c  mov     r8, rbx; pSourceSid
0x180039c8f  mov     ecx, esi; nDestinationSidLength
0x180039c91  call    cs:__imp_CopySid
0x180039c97  test    eax, eax
0x180039c99  jnz     short loc_180039CD0
0x180039c9b  call    cs:__imp_GetLastError
0x180039ca1  mov     ebx, eax
0x180039ca3  test    eax, eax
0x180039ca5  jle     short loc_180039CB0
0x180039ca7  movzx   ebx, ax
0x180039caa  or      ebx, 80070000h
0x180039cb0  mov     rcx, [rdi]; void *
0x180039cb3  test    ebx, ebx
0x180039cb5  mov     eax, 80004005h
0x180039cba  mov     qword ptr [rdi], 0
0x180039cc1  cmovns  ebx, eax
0x180039cc4  test    rcx, rcx
0x180039cc7  jz      short loc_180039CD2
0x180039cc9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039cce  jmp     short loc_180039CD2
0x180039cd0  xor     ebx, ebx
0x180039cd2  mov     eax, ebx
0x180039cd4  jmp     short loc_180039CDB
0x180039cd6  mov     eax, 80070057h
0x180039cdb  mov     rbx, [rsp+28h+arg_0]
0x180039ce0  mov     rsi, [rsp+28h+arg_8]
0x180039ce5  add     rsp, 20h
0x180039ce9  pop     rdi
0x180039cea  retn
```
