# IsServiceSid(ushort const *,int *)

- ea: `0x180026c20`
- end: `0x180026ce5`
- name: `?IsServiceSid@@YAJPEBGPEAH@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026e30`

## callees

- `0x180026c20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c55`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180026c98`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180026c98`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180026c81`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180026c81`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180026cb5`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180026cb5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180026c4b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180026c4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cd0`

## pseudocode

```c
__int64 __fastcall IsServiceSid(const unsigned __int16 *a1, int *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int i; // edi
  int v6; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  PSID Sid; // [rsp+58h] [rbp+38h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v4 = 0;
    for ( i = 0; i < 3; ++i )
    {
      if ( IsWellKnownSid(Sid, *((WELL_KNOWN_SID_TYPE *)qword_18008FF68 + (int)i)) )
        goto LABEL_10;
    }
    v6 = 0;
    SidIdentifierAuthority = GetSidIdentifierAuthority(Sid);
    if ( !*(_DWORD *)SidIdentifierAuthority->Value
      && *(_WORD *)&SidIdentifierAuthority->Value[4] == 1280
      && *GetSidSubAuthority(Sid, 0) == 99 )
    {
LABEL_10:
      v6 = 1;
    }
    *a2 = v6;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( Sid )
    LocalFree(Sid);
  return v4;
}

```

## disassembly

```asm
0x180026c20  mov     [rsp-18h+arg_0], rbx
0x180026c25  push    rbp
0x180026c26  push    rsi
0x180026c27  push    rdi
0x180026c28  mov     rbp, rsp
0x180026c2b  sub     rsp, 20h
0x180026c2f  mov     rsi, rdx
0x180026c32  mov     [rbp+Sid], 0
0x180026c3a  lea     rdx, [rbp+Sid]; Sid
0x180026c3e  mov     [rbp+arg_10], 0
0x180026c45  mov     [rbp+arg_14], 500h
0x180026c4b  call    cs:__imp_ConvertStringSidToSidW
0x180026c51  test    eax, eax
0x180026c53  jnz     short loc_180026C6C
0x180026c55  call    cs:__imp_GetLastError
0x180026c5b  mov     ebx, eax
0x180026c5d  test    eax, eax
0x180026c5f  jle     short loc_180026CC7
0x180026c61  movzx   ebx, ax
0x180026c64  or      ebx, 80070000h
0x180026c6a  jmp     short loc_180026CC7
0x180026c6c  xor     ebx, ebx
0x180026c6e  xor     edi, edi
0x180026c70  mov     rcx, [rbp+Sid]; pSid
0x180026c74  lea     rax, qword_18008FF68
0x180026c7b  movsxd  rdx, edi
0x180026c7e  mov     edx, [rax+rdx*4]; WellKnownSidType
0x180026c81  call    cs:__imp_IsWellKnownSid
0x180026c87  test    eax, eax
0x180026c89  jnz     short loc_180026CC0
0x180026c8b  inc     edi
0x180026c8d  cmp     edi, 3
0x180026c90  jb      short loc_180026C70
0x180026c92  mov     rcx, [rbp+Sid]; pSid
0x180026c96  xor     edi, edi
0x180026c98  call    cs:__imp_GetSidIdentifierAuthority
0x180026c9e  mov     ecx, [rax]
0x180026ca0  cmp     ecx, [rbp+arg_10]
0x180026ca3  jnz     short loc_180026CC5
0x180026ca5  movzx   eax, word ptr [rax+4]
0x180026ca9  cmp     ax, [rbp+arg_14]
0x180026cad  jnz     short loc_180026CC5
0x180026caf  mov     rcx, [rbp+Sid]; pSid
0x180026cb3  xor     edx, edx; nSubAuthority
0x180026cb5  call    cs:__imp_GetSidSubAuthority
0x180026cbb  cmp     dword ptr [rax], 63h ; 'c'
0x180026cbe  jnz     short loc_180026CC5
0x180026cc0  mov     edi, 1
0x180026cc5  mov     [rsi], edi
0x180026cc7  mov     rcx, [rbp+Sid]; hMem
0x180026ccb  test    rcx, rcx
0x180026cce  jz      short loc_180026CD6
0x180026cd0  call    cs:__imp_LocalFree
0x180026cd6  mov     eax, ebx
0x180026cd8  mov     rbx, [rsp+20h+arg_0]
0x180026cdd  add     rsp, 20h
0x180026ce1  pop     rdi
0x180026ce2  pop     rsi
0x180026ce3  pop     rbp
0x180026ce4  retn
```
