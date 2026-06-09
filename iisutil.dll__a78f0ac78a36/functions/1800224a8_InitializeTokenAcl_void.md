# InitializeTokenAcl(void)

- ea: `0x1800224a8`
- end: `0x18002263a`
- name: `?InitializeTokenAcl@@YAJXZ`
- size: `402`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ea00`

## callees

- `0x180002b60`
- `0x180016be4`
- `0x1800224a8`
- `0x180022770`
- `0x18002c476`
- `0x18002c4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022531`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800225db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002251f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002258f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002251f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002258f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002257e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002257e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800225f4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800225f4`

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
0x1800224a8  mov     [rsp-8+arg_0], rbx
0x1800224ad  mov     [rsp-8+arg_8], rdi
0x1800224b2  push    rbp
0x1800224b3  lea     rbp, [rsp-57h]
0x1800224b8  sub     rsp, 0B0h
0x1800224bf  mov     rax, cs:__security_cookie
0x1800224c6  xor     rax, rsp
0x1800224c9  mov     [rbp+57h+var_10], rax
0x1800224cd  xor     edi, edi
0x1800224cf  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800224d5  lea     rax, [rbp+57h+var_40]
0x1800224d9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1800224dc  lea     rdx, [rbp+57h+var_40]; this
0x1800224e0  mov     [rbp+57h+var_40], rdi
0x1800224e4  mov     [rbp+57h+Src], rax
0x1800224e8  lea     ecx, [rdi+3Eh]; WellKnownSidType
0x1800224eb  mov     dword ptr [rbp+57h+uBytes], 20h ; ' '
0x1800224f2  mov     word ptr [rbp+57h+uBytes+4], 100h
0x1800224f8  call    ?GetWellKnownSID@@YAKW4WELL_KNOWN_SID_TYPE@@PEAVBUFFER@@@Z; GetWellKnownSID(WELL_KNOWN_SID_TYPE,BUFFER *)
0x1800224fd  mov     ebx, eax
0x1800224ff  test    eax, eax
0x180022501  jz      short loc_180022517
0x180022503  jle     loc_1800225CF
0x180022509  movzx   ebx, ax
0x18002250c  or      ebx, 80070000h
0x180022512  jmp     loc_1800225CF
0x180022517  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18002251a  mov     ecx, 40h ; '@'; uFlags
0x18002251f  call    cs:__imp_LocalAlloc
0x180022525  mov     cs:?g_pSidWpg@@3PEAXEA, rax; void * g_pSidWpg
0x18002252c  test    rax, rax
0x18002252f  jnz     short loc_18002253D
0x180022531  call    cs:__imp_GetLastError
0x180022537  mov     ebx, eax
0x180022539  test    eax, eax
0x18002253b  jmp     short loc_180022503
0x18002253d  mov     r8d, dword ptr [rbp+57h+uBytes]; Size
0x180022541  mov     rcx, rax; void *
0x180022544  mov     rdx, [rbp+57h+Src]; Src
0x180022548  call    memcpy_0
0x18002254d  lea     rax, ?g_pSidLocalSystem@@3PEAXEA; void * g_pSidLocalSystem
0x180022554  xor     r9d, r9d; nSubAuthority1
0x180022557  mov     [rsp+0B0h+pSid], rax; pSid
0x18002255c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180022560  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x180022564  mov     dl, 1; nSubAuthorityCount
0x180022566  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x18002256a  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x18002256e  lea     r8d, [r9+12h]; nSubAuthority0
0x180022572  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x180022576  mov     [rsp+0B0h+nSubAuthority3], edi; nSubAuthority3
0x18002257a  mov     [rsp+0B0h+nSubAuthority2], edi; nSubAuthority2
0x18002257e  call    cs:__imp_AllocateAndInitializeSid
0x180022584  test    eax, eax
0x180022586  jz      short loc_180022531
0x180022588  mov     edx, 1Ch; uBytes
0x18002258d  xor     ecx, ecx; uFlags
0x18002258f  call    cs:__imp_LocalAlloc
0x180022595  mov     cs:?g_pTokenPrivilege@@3PEAU_TOKEN_PRIVILEGES@@EA, rax; _TOKEN_PRIVILEGES * g_pTokenPrivilege
0x18002259c  mov     rcx, rax
0x18002259f  test    rax, rax
0x1800225a2  jz      short loc_1800225C4
0x1800225a4  mov     dword ptr [rcx], 1
0x1800225aa  mov     [rbp+57h+var_50], 11h
0x1800225b2  mov     rax, [rbp+57h+var_50]
0x1800225b6  mov     cs:?g_BackupPrivilegeValue@@3U_LUID@@A, rax; _LUID g_BackupPrivilegeValue
0x1800225bd  mov     [rcx+4], rax
0x1800225c1  mov     [rcx+0Ch], edi
0x1800225c4  call    ?QueryProcessIntegrityLevel@@YAJXZ; QueryProcessIntegrityLevel(void)
0x1800225c9  mov     ebx, eax
0x1800225cb  test    eax, eax
0x1800225cd  jns     short loc_18002260E
0x1800225cf  mov     rcx, cs:?g_pSidWpg@@3PEAXEA; hMem
0x1800225d6  test    rcx, rcx
0x1800225d9  jz      short loc_1800225E8
0x1800225db  call    cs:__imp_LocalFree
0x1800225e1  mov     cs:?g_pSidWpg@@3PEAXEA, rdi; void * g_pSidWpg
0x1800225e8  mov     rcx, cs:?g_pSidLocalSystem@@3PEAXEA; pSid
0x1800225ef  test    rcx, rcx
0x1800225f2  jz      short loc_180022601
0x1800225f4  call    cs:__imp_FreeSid
0x1800225fa  mov     cs:?g_pSidLocalSystem@@3PEAXEA, rdi; void * g_pSidLocalSystem
0x180022601  lea     rcx, [rbp+57h+var_40]; this
0x180022605  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002260a  mov     eax, ebx
0x18002260c  jmp     short loc_180022619
0x18002260e  lea     rcx, [rbp+57h+var_40]; this
0x180022612  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180022617  xor     eax, eax
0x180022619  mov     rcx, [rbp+57h+var_10]
0x18002261d  xor     rcx, rsp; StackCookie
0x180022620  call    __security_check_cookie
0x180022625  lea     r11, [rsp+0B0h+var_s0]
0x18002262d  mov     rbx, [r11+10h]
0x180022631  mov     rdi, [r11+18h]
0x180022635  mov     rsp, r11
0x180022638  pop     rbp
0x180022639  retn
```
