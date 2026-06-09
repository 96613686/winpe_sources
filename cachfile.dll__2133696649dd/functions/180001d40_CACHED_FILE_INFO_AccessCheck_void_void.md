# CACHED_FILE_INFO::AccessCheck(void *,void *)

- ea: `0x180001d40`
- end: `0x180002023`
- name: `?AccessCheck@CACHED_FILE_INFO@@UEAAJPEAX0@Z`
- size: `739`
- prototype: `__int64 __fastcall(CACHED_FILE_INFO *this, void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180001d40`
- `0x180003c26`
- `0x180003c32`
- `0x180003c70`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001eff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001ff8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180001ff8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001fa6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180001fa6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001e99`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180001e99`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001ee1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180001ee1`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180001e0f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180001e0f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180001e63`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180001e63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000200e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000200e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f68`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001f68`
- `iisutil!MakePathCanonicalizationProof` at `0x180001f85`
- `iisutil!MakePathCanonicalizationProof` at `0x180001f85`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001fcc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001fcc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001dcb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001dcb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001eec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f19`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f96`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001eec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f19`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001f96`

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::AccessCheck(CACHED_FILE_INFO *this, void *a2, void *a3)
{
  void *v6; // rdx
  void *Ptr; // rax
  signed int PathCanonicalizationProof; // ebp
  DWORD LengthSid; // eax
  signed int LastError; // eax
  signed int v12; // eax
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rax
  const WCHAR *Str; // rax
  HANDLE FileW; // rax
  DWORD PrivilegeSetLength; // [rsp+40h] [rbp-208h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-204h] BYREF
  DWORD GrantedAccess; // [rsp+48h] [rbp-200h] BYREF
  _BYTE v20[64]; // [rsp+50h] [rbp-1F8h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp-1B8h] BYREF
  unsigned __int16 v22[128]; // [rsp+110h] [rbp-138h] BYREF

  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  if ( !a2 )
    return 0;
  v6 = (void *)*((_QWORD *)this + 93);
  if ( v6 )
  {
    if ( a3 && EqualSid(a3, v6) )
      return 0;
  }
  if ( *(_WORD *)(*(__int64 (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)this + 88LL))(this) != 92
    || *(_WORD *)((*(__int64 (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)this + 88LL))(this) + 2) != 92 )
  {
    PrivilegeSetLength = 128;
    PrivilegeSet.PrivilegeCount = 0;
    Ptr = BUFFER::QueryPtr((CACHED_FILE_INFO *)((char *)this + 432));
    if ( !AccessCheck(Ptr, a2, 0x120089u, &g_gmFile, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
      return (unsigned int)-2147024891;
    PathCanonicalizationProof = 0;
    if ( !AccessStatus )
      return (unsigned int)-2147024891;
LABEL_6:
    if ( a3 && !*((_QWORD *)this + 93) && !_InterlockedCompareExchange((volatile signed __int32 *)this + 184, 1, 0) )
    {
      LengthSid = GetLengthSid(a3);
      memcpy_0((char *)this + 752, a3, LengthSid);
      *((_QWORD *)this + 93) = (char *)this + 752;
    }
    return (unsigned int)PathCanonicalizationProof;
  }
  memset_0(v22, 0, sizeof(v22));
  STRU::STRU((STRU *)v20, v22, 0x80u);
  v14 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(CACHED_FILE_INFO *))(*(_QWORD *)this + 88LL))(this);
  PathCanonicalizationProof = MakePathCanonicalizationProof(v14, (struct STRU *)v20);
  if ( PathCanonicalizationProof < 0 )
  {
    STRU::~STRU((STRU *)v20);
    return (unsigned int)PathCanonicalizationProof;
  }
  if ( SetThreadToken(0, a2) )
  {
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 24LL))(g_pGlobalInfo);
    Str = STRU::QueryStr((STRU *)v20);
    FileW = CreateFileW(Str, 0x80000000, 7u, 0, 3u, 0x42000001u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      PathCanonicalizationProof = LastError;
      if ( LastError > 0 )
        PathCanonicalizationProof = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      PathCanonicalizationProof = 0;
      CloseHandle(FileW);
    }
    (*(void (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 32LL))(g_pGlobalInfo);
    RevertToSelf();
    STRU::~STRU((STRU *)v20);
    if ( PathCanonicalizationProof < 0 )
      return (unsigned int)PathCanonicalizationProof;
    goto LABEL_6;
  }
  v12 = GetLastError();
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  STRU::~STRU((STRU *)v20);
  return v13;
}

```

## disassembly

```asm
0x180001d40  push    rbx
0x180001d42  push    rsi
0x180001d43  push    rdi
0x180001d44  push    r14
0x180001d46  sub     rsp, 228h
0x180001d4d  mov     rax, cs:__security_cookie
0x180001d54  xor     rax, rsp
0x180001d57  mov     [rsp+248h+var_38], rax
0x180001d5f  xor     r14d, r14d
0x180001d62  mov     rsi, r8
0x180001d65  mov     [rsp+248h+var_208], r14d
0x180001d6a  mov     rdi, rdx
0x180001d6d  mov     [rsp+248h+var_200], r14d
0x180001d72  mov     rbx, rcx
0x180001d75  mov     [rsp+248h+var_204], r14d
0x180001d7a  test    rdx, rdx
0x180001d7d  jz      loc_180001E71
0x180001d83  mov     rdx, [rcx+2E8h]; pSid2
0x180001d8a  test    rdx, rdx
0x180001d8d  jnz     loc_180001E57
0x180001d93  mov     rax, [rbx]
0x180001d96  mov     rcx, rbx
0x180001d99  mov     [rsp+248h+var_28], rbp
0x180001da1  mov     rax, [rax+58h]
0x180001da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001daa  cmp     word ptr [rax], 5Ch ; '\'
0x180001dae  jz      loc_180001F26
0x180001db4  lea     rcx, [rbx+1B0h]
0x180001dbb  mov     [rsp+248h+var_208], 80h
0x180001dc3  mov     [rsp+248h+var_1B8.PrivilegeCount], r14d
0x180001dcb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001dd1  lea     rcx, [rsp+248h+var_204]
0x180001dd6  mov     r8d, 120089h; DesiredAccess
0x180001ddc  mov     [rsp+248h+AccessStatus], rcx; AccessStatus
0x180001de1  lea     r9, ?g_gmFile@@3U_GENERIC_MAPPING@@A; GenericMapping
0x180001de8  lea     rcx, [rsp+248h+var_200]
0x180001ded  mov     rdx, rdi; ClientToken
0x180001df0  mov     [rsp+248h+GrantedAccess], rcx; GrantedAccess
0x180001df5  lea     rcx, [rsp+248h+var_208]
0x180001dfa  mov     [rsp+248h+PrivilegeSetLength], rcx; PrivilegeSetLength
0x180001dff  lea     rcx, [rsp+248h+var_1B8]
0x180001e07  mov     [rsp+248h+PrivilegeSet], rcx; PrivilegeSet
0x180001e0c  mov     rcx, rax; pSecurityDescriptor
0x180001e0f  call    cs:__imp_AccessCheck
0x180001e15  test    eax, eax
0x180001e17  jz      loc_180002019
0x180001e1d  mov     ebp, r14d
0x180001e20  cmp     [rsp+248h+var_204], r14d
0x180001e25  jz      loc_180002019
0x180001e2b  test    rsi, rsi
0x180001e2e  jnz     short loc_180001E75
0x180001e30  mov     eax, ebp
0x180001e32  mov     rbp, [rsp+248h+var_28]
0x180001e3a  mov     rcx, [rsp+248h+var_38]
0x180001e42  xor     rcx, rsp; StackCookie
0x180001e45  call    __security_check_cookie
0x180001e4a  add     rsp, 228h
0x180001e51  pop     r14
0x180001e53  pop     rdi
0x180001e54  pop     rsi
0x180001e55  pop     rbx
0x180001e56  retn
0x180001e57  test    rsi, rsi
0x180001e5a  jz      loc_180001D93
0x180001e60  mov     rcx, rsi; pSid1
0x180001e63  call    cs:__imp_EqualSid
0x180001e69  test    eax, eax
0x180001e6b  jz      loc_180001D93
0x180001e71  xor     eax, eax
0x180001e73  jmp     short loc_180001E3A
0x180001e75  cmp     [rbx+2E8h], r14
0x180001e7c  jnz     short loc_180001E30
0x180001e7e  mov     ecx, 1
0x180001e83  xor     eax, eax
0x180001e85  lock cmpxchg [rbx+2E0h], ecx
0x180001e8d  jnz     short loc_180001E30
0x180001e8f  mov     rcx, rsi; pSid
0x180001e92  lea     rdi, [rbx+2F0h]
0x180001e99  call    cs:__imp_GetLengthSid
0x180001e9f  mov     r8d, eax; Size
0x180001ea2  mov     rdx, rsi; Src
0x180001ea5  mov     rcx, rdi; void *
0x180001ea8  call    memcpy_0
0x180001ead  mov     [rbx+2E8h], rdi
0x180001eb4  jmp     loc_180001E30
0x180001eb9  call    cs:__imp_GetLastError
0x180001ebf  mov     ebp, eax
0x180001ec1  test    eax, eax
0x180001ec3  jle     short loc_180001ECE
0x180001ec5  movzx   ebp, ax
0x180001ec8  or      ebp, 80070000h
0x180001ece  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001ed5  mov     rax, [rcx]
0x180001ed8  mov     rax, [rax+20h]
0x180001edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee1  call    cs:__imp_RevertToSelf
0x180001ee7  lea     rcx, [rsp+248h+var_1F8]
0x180001eec  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001ef2  test    ebp, ebp
0x180001ef4  js      loc_180001E30
0x180001efa  jmp     loc_180001E2B
0x180001eff  call    cs:__imp_GetLastError
0x180001f05  mov     ebx, eax
0x180001f07  test    eax, eax
0x180001f09  jle     short loc_180001F14
0x180001f0b  movzx   ebx, ax
0x180001f0e  or      ebx, 80070000h
0x180001f14  lea     rcx, [rsp+248h+var_1F8]
0x180001f19  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001f1f  mov     eax, ebx
0x180001f21  jmp     loc_180001E32
0x180001f26  mov     rax, [rbx]
0x180001f29  mov     rcx, rbx
0x180001f2c  mov     rax, [rax+58h]
0x180001f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f35  cmp     word ptr [rax+2], 5Ch ; '\'
0x180001f3a  jnz     loc_180001DB4
0x180001f40  xor     edx, edx; Val
0x180001f42  lea     rcx, [rsp+248h+var_138]; void *
0x180001f4a  mov     r8d, 100h; Size
0x180001f50  call    memset_0
0x180001f55  mov     r8d, 80h
0x180001f5b  lea     rdx, [rsp+248h+var_138]
0x180001f63  lea     rcx, [rsp+248h+var_1F8]
0x180001f68  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001f6e  mov     rax, [rbx]
0x180001f71  mov     rcx, rbx
0x180001f74  mov     rax, [rax+58h]
0x180001f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f7d  mov     rcx, rax
0x180001f80  lea     rdx, [rsp+248h+var_1F8]
0x180001f85  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180001f8b  mov     ebp, eax
0x180001f8d  test    eax, eax
0x180001f8f  jns     short loc_180001FA1
0x180001f91  lea     rcx, [rsp+248h+var_1F8]
0x180001f96  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001f9c  jmp     loc_180001E30
0x180001fa1  mov     rdx, rdi; Token
0x180001fa4  xor     ecx, ecx; Thread
0x180001fa6  call    cs:__imp_SetThreadToken
0x180001fac  test    eax, eax
0x180001fae  jz      loc_180001EFF
0x180001fb4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180001fbb  mov     rax, [rcx]
0x180001fbe  mov     rax, [rax+18h]
0x180001fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc7  lea     rcx, [rsp+248h+var_1F8]
0x180001fcc  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180001fd2  mov     [rsp+248h+GrantedAccess], r14; hTemplateFile
0x180001fd7  xor     r9d, r9d; lpSecurityAttributes
0x180001fda  mov     rcx, rax; lpFileName
0x180001fdd  mov     dword ptr [rsp+248h+PrivilegeSetLength], 42000001h; dwFlagsAndAttributes
0x180001fe5  mov     edx, 80000000h; dwDesiredAccess
0x180001fea  mov     dword ptr [rsp+248h+PrivilegeSet], 3; dwCreationDisposition
0x180001ff2  mov     r8d, 7; dwShareMode
0x180001ff8  call    cs:__imp_CreateFileW
0x180001ffe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002002  jz      loc_180001EB9
0x180002008  mov     rcx, rax; hObject
0x18000200b  mov     ebp, r14d
0x18000200e  call    cs:__imp_CloseHandle
0x180002014  jmp     loc_180001ECE
0x180002019  mov     ebp, 80070005h
0x18000201e  jmp     loc_180001E30
```
