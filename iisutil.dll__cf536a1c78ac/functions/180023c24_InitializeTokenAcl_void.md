# InitializeTokenAcl(void)

- ea: `0x180023c24`
- end: `0x180023ddb`
- name: `?InitializeTokenAcl@@YAJXZ`
- size: `439`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fbd0`

## callees

- `0x1800034f0`
- `0x180017854`
- `0x180023c24`
- `0x180023f3c`
- `0x18002e516`
- `0x18002e560`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d6f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023c9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d1d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023c9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023d1d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023d06`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180023d06`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023d8e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023d8e`

## pseudocode

```c
__int64 InitializeTokenAcl(void)
{
  signed int WellKnownSID; // eax
  signed int ProcessIntegrityLevel; // ebx
  bool v2; // cc
  HLOCAL v3; // rax
  char *v4; // rax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp+Fh] BYREF
  _QWORD v7[4]; // [rsp+70h] [rbp+17h] BYREF
  void *Src; // [rsp+90h] [rbp+37h]
  unsigned int uBytes; // [rsp+98h] [rbp+3Fh]
  __int16 uBytes_4; // [rsp+9Ch] [rbp+43h]

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v7[0] = 0;
  Src = v7;
  uBytes = 32;
  uBytes_4 = 256;
  WellKnownSID = GetWellKnownSID(WinBuiltinIUsersSid, (struct BUFFER *)v7);
  ProcessIntegrityLevel = WellKnownSID;
  v2 = WellKnownSID <= 0;
  if ( WellKnownSID )
  {
LABEL_2:
    if ( !v2 )
      ProcessIntegrityLevel = (unsigned __int16)WellKnownSID | 0x80070000;
    goto LABEL_10;
  }
  v3 = LocalAlloc(0x40u, uBytes);
  g_pSidWpg = v3;
  if ( !v3
    || (memcpy_0(v3, Src, uBytes),
        !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &g_pSidLocalSystem)) )
  {
    WellKnownSID = GetLastError();
    ProcessIntegrityLevel = WellKnownSID;
    v2 = WellKnownSID <= 0;
    goto LABEL_2;
  }
  v4 = (char *)LocalAlloc(0, 0x1Cu);
  g_pTokenPrivilege = (PTOKEN_PRIVILEGES)v4;
  if ( v4 )
  {
    *(_DWORD *)v4 = 1;
    g_BackupPrivilegeValue = (struct _LUID)17LL;
    *(_QWORD *)(v4 + 4) = 17;
    *((_DWORD *)v4 + 3) = 0;
  }
  ProcessIntegrityLevel = QueryProcessIntegrityLevel();
  if ( ProcessIntegrityLevel >= 0 )
  {
    BUFFER::~BUFFER((BUFFER *)v7);
    return 0;
  }
LABEL_10:
  if ( g_pSidWpg )
  {
    LocalFree(g_pSidWpg);
    g_pSidWpg = 0;
  }
  if ( g_pSidLocalSystem )
  {
    FreeSid(g_pSidLocalSystem);
    g_pSidLocalSystem = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v7);
  return (unsigned int)ProcessIntegrityLevel;
}

```

## disassembly

```asm
0x180023c24  mov     [rsp-8+arg_0], rbx
0x180023c29  mov     [rsp-8+arg_8], rdi
0x180023c2e  push    rbp
0x180023c2f  lea     rbp, [rsp-57h]
0x180023c34  sub     rsp, 0B0h
0x180023c3b  mov     rax, cs:__security_cookie
0x180023c42  xor     rax, rsp
0x180023c45  mov     [rbp+57h+var_10], rax
0x180023c49  xor     edi, edi
0x180023c4b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180023c51  lea     rax, [rbp+57h+var_40]
0x180023c55  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180023c58  lea     rdx, [rbp+57h+var_40]; this
0x180023c5c  mov     [rbp+57h+var_40], rdi
0x180023c60  mov     [rbp+57h+Src], rax
0x180023c64  lea     ecx, [rdi+3Eh]; WellKnownSidType
0x180023c67  mov     dword ptr [rbp+57h+uBytes], 20h ; ' '
0x180023c6e  mov     word ptr [rbp+57h+uBytes+4], 100h
0x180023c74  call    ?GetWellKnownSID@@YAKW4WELL_KNOWN_SID_TYPE@@PEAVBUFFER@@@Z; GetWellKnownSID(WELL_KNOWN_SID_TYPE,BUFFER *)
0x180023c79  mov     ebx, eax
0x180023c7b  test    eax, eax
0x180023c7d  jz      short loc_180023C93
0x180023c7f  jle     loc_180023D63
0x180023c85  movzx   ebx, ax
0x180023c88  or      ebx, 80070000h
0x180023c8e  jmp     loc_180023D63
0x180023c93  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x180023c96  mov     ecx, 40h ; '@'; uFlags
0x180023c9b  call    cs:__imp_LocalAlloc
0x180023ca2  nop     dword ptr [rax+rax+00h]
0x180023ca7  mov     cs:?g_pSidWpg@@3PEAXEA, rax; void * g_pSidWpg
0x180023cae  test    rax, rax
0x180023cb1  jnz     short loc_180023CC5
0x180023cb3  call    cs:__imp_GetLastError
0x180023cba  nop     dword ptr [rax+rax+00h]
0x180023cbf  mov     ebx, eax
0x180023cc1  test    eax, eax
0x180023cc3  jmp     short loc_180023C7F
0x180023cc5  mov     r8d, dword ptr [rbp+57h+uBytes]; Size
0x180023cc9  mov     rcx, rax; void *
0x180023ccc  mov     rdx, [rbp+57h+Src]; Src
0x180023cd0  call    memcpy_0
0x180023cd5  lea     rax, ?g_pSidLocalSystem@@3PEAXEA; void * g_pSidLocalSystem
0x180023cdc  xor     r9d, r9d; nSubAuthority1
0x180023cdf  mov     [rsp+0B0h+pSid], rax; pSid
0x180023ce4  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180023ce8  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x180023cec  mov     dl, 1; nSubAuthorityCount
0x180023cee  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x180023cf2  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x180023cf6  lea     r8d, [r9+12h]; nSubAuthority0
0x180023cfa  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x180023cfe  mov     [rsp+0B0h+nSubAuthority3], edi; nSubAuthority3
0x180023d02  mov     [rsp+0B0h+nSubAuthority2], edi; nSubAuthority2
0x180023d06  call    cs:__imp_AllocateAndInitializeSid
0x180023d0d  nop     dword ptr [rax+rax+00h]
0x180023d12  test    eax, eax
0x180023d14  jz      short loc_180023CB3
0x180023d16  mov     edx, 1Ch; uBytes
0x180023d1b  xor     ecx, ecx; uFlags
0x180023d1d  call    cs:__imp_LocalAlloc
0x180023d24  nop     dword ptr [rax+rax+00h]
0x180023d29  mov     cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA, rax; _TOKEN_PRIVILEGES * g_pTokenPrivilege
0x180023d30  mov     rcx, rax
0x180023d33  test    rax, rax
0x180023d36  jz      short loc_180023D58
0x180023d38  mov     dword ptr [rcx], 1
0x180023d3e  mov     [rbp+57h+var_50], 11h
0x180023d46  mov     rax, [rbp+57h+var_50]
0x180023d4a  mov     cs:?g_BackupPrivilegeValue@@3U_LUID@@A, rax; _LUID g_BackupPrivilegeValue
0x180023d51  mov     [rcx+4], rax
0x180023d55  mov     [rcx+0Ch], edi
0x180023d58  call    ?QueryProcessIntegrityLevel@@YAJXZ; QueryProcessIntegrityLevel(void)
0x180023d5d  mov     ebx, eax
0x180023d5f  test    eax, eax
0x180023d61  jns     short loc_180023DAE
0x180023d63  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; hMem
0x180023d6a  test    rcx, rcx
0x180023d6d  jz      short loc_180023D82
0x180023d6f  call    cs:__imp_LocalFree
0x180023d76  nop     dword ptr [rax+rax+00h]
0x180023d7b  mov     cs:?g_pSidWpg@@3PEAXEA, rdi; void * g_pSidWpg
0x180023d82  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x180023d89  test    rcx, rcx
0x180023d8c  jz      short loc_180023DA1
0x180023d8e  call    cs:__imp_FreeSid
0x180023d95  nop     dword ptr [rax+rax+00h]
0x180023d9a  mov     cs:?g_pSidLocalSystem@@3PEAXEA, rdi; void * g_pSidLocalSystem
0x180023da1  lea     rcx, [rbp+57h+var_40]; this
0x180023da5  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023daa  mov     eax, ebx
0x180023dac  jmp     short loc_180023DB9
0x180023dae  lea     rcx, [rbp+57h+var_40]; this
0x180023db2  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023db7  xor     eax, eax
0x180023db9  mov     rcx, [rbp+57h+var_10]
0x180023dbd  xor     rcx, rsp; StackCookie
0x180023dc0  call    __security_check_cookie
0x180023dc5  lea     r11, [rsp+0B0h+var_s0]
0x180023dcd  mov     rbx, [r11+10h]
0x180023dd1  mov     rdi, [r11+18h]
0x180023dd5  mov     rsp, r11
0x180023dd8  pop     rbp
0x180023dd9  retn
```
