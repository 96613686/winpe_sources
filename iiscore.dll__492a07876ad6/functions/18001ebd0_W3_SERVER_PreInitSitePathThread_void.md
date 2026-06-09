# W3_SERVER::PreInitSitePathThread(void *)

- ea: `0x18001ebd0`
- end: `0x18001eeb5`
- name: `?PreInitSitePathThread@W3_SERVER@@CAKPEAX@Z`
- size: `741`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001ebd0`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ee78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ee89`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ee78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001ee89`
- `iisutil!PuDbgPrint` at `0x18001ee17`
- `iisutil!PuDbgPrint` at `0x18001ee17`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001eda2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001edb6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001eda2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001edb6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ed5b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001ed5b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ec3b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ec66`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ec3b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001ec66`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ed77`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001ed77`

## string_xrefs

- `0x18001ee10`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001edf3`: `PreInitSitesThread: Premature Exit Occured ( hr = %x )\n`
- `0x18001edfe`: `W3_SERVER::PreInitSitePathThread`

## pseudocode

```c
__int64 __fastcall W3_SERVER::PreInitSitePathThread(PVOID Parameter)
{
  int v1; // ebx
  __int64 v2; // rsi
  __int64 (__fastcall *v3)(__int64, unsigned __int16 *, unsigned __int16 *, int *, _QWORD); // rdi
  unsigned __int16 *Str; // rbx
  unsigned __int16 *v5; // rax
  unsigned int v7; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v8; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h] BYREF
  int v11; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v12; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v13[56]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v14[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v15[256]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v16[256]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  v7 = 0;
  v12 = 0;
  v11 = 256;
  memset_0(v15, 0, sizeof(v15));
  STRU::STRU((STRU *)v13, v15, 0x100u);
  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v14, v16, 0x100u);
  v1 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const wchar_t *, __int64 *, _QWORD, _QWORD))(**((_QWORD **)g_pW3Server + 187) + 24LL))(
         *((_QWORD *)g_pW3Server + 187),
         L"system.applicationHost/sites",
         L"MACHINE/WEBROOT/APPHOST",
         &v10,
         0,
         0);
  if ( v1 < 0 )
    goto LABEL_10;
  v1 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 40LL))(v10, &v8);
  if ( v1 < 0 )
    goto LABEL_10;
  v1 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v8 + 24LL))(v8, &v7);
  if ( v1 < 0 )
    goto LABEL_10;
  if ( v7 <= 1 )
  {
    v1 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, 0, &v9);
    if ( v1 < 0 )
      goto LABEL_10;
    v1 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v9 + 64LL))(
           v9,
           L"name",
           &v12,
           0,
           0);
    if ( v1 < 0
      || (v1 = STRU::Copy((STRU *)v13, L"MACHINE/WEBROOT/APPHOST/"), v1 < 0)
      || (v1 = STRU::Append((STRU *)v13, v12), v1 < 0)
      || (v2 = *((_QWORD *)g_pW3Server + 187),
          v3 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, int *, _QWORD))(*(_QWORD *)v2 + 32LL),
          Str = STRU::QueryStr((STRU *)v14),
          v5 = STRU::QueryStr((STRU *)v13),
          v1 = v3(v2, v5, Str, &v11, 0),
          v1 < 0) )
    {
LABEL_10:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
          4274,
          "W3_SERVER::PreInitSitePathThread",
          "PreInitSitesThread: Premature Exit Occured ( hr = %x )\n",
          v1);
    }
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v8 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  STRU::~STRU((STRU *)v14);
  STRU::~STRU((STRU *)v13);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001ebd0  push    rbp
0x18001ebd2  push    rbx
0x18001ebd3  push    rsi
0x18001ebd4  push    rdi
0x18001ebd5  push    r14
0x18001ebd7  lea     rbp, [rsp-3F0h]
0x18001ebdf  sub     rsp, 4F0h
0x18001ebe6  mov     rax, cs:__security_cookie
0x18001ebed  xor     rax, rsp
0x18001ebf0  mov     [rbp+410h+var_30], rax
0x18001ebf7  xor     r14d, r14d
0x18001ebfa  lea     rcx, [rbp+410h+var_430]; void *
0x18001ebfe  mov     ebx, 200h
0x18001ec03  mov     [rsp+510h+var_4B8], r14
0x18001ec08  mov     edi, 100h
0x18001ec0d  mov     [rsp+510h+var_4C8], r14
0x18001ec12  mov     r8d, ebx; Size
0x18001ec15  mov     [rsp+510h+var_4C0], r14
0x18001ec1a  xor     edx, edx; Val
0x18001ec1c  mov     [rsp+510h+var_4D0], r14d
0x18001ec21  mov     [rsp+510h+var_4A8], r14
0x18001ec26  mov     [rsp+510h+var_4B0], edi
0x18001ec2a  call    memset_0
0x18001ec2f  mov     r8d, edi
0x18001ec32  lea     rdx, [rbp+410h+var_430]
0x18001ec36  lea     rcx, [rsp+510h+var_4A0]
0x18001ec3b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001ec42  nop     dword ptr [rax+rax+00h]
0x18001ec47  mov     r8d, ebx; Size
0x18001ec4a  lea     rcx, [rbp+410h+var_230]; void *
0x18001ec51  xor     edx, edx; Val
0x18001ec53  call    memset_0
0x18001ec58  mov     r8d, edi
0x18001ec5b  lea     rdx, [rbp+410h+var_230]
0x18001ec62  lea     rcx, [rbp+410h+var_468]
0x18001ec66  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001ec6d  nop     dword ptr [rax+rax+00h]
0x18001ec72  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001ec79  lea     r9, [rsp+510h+var_4B8]
0x18001ec7e  mov     [rsp+510h+var_4E8], r14
0x18001ec83  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001ec8a  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18001ec91  mov     [rsp+510h+var_4F0], r14
0x18001ec96  mov     rcx, [rax+5D8h]
0x18001ec9d  mov     rax, [rcx]
0x18001eca0  mov     rax, [rax+18h]
0x18001eca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eca9  mov     ebx, eax
0x18001ecab  test    eax, eax
0x18001ecad  js      loc_18001EDE3
0x18001ecb3  mov     rcx, [rsp+510h+var_4B8]
0x18001ecb8  lea     rdx, [rsp+510h+var_4C8]
0x18001ecbd  mov     rax, [rcx]
0x18001ecc0  mov     rax, [rax+28h]
0x18001ecc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc9  mov     ebx, eax
0x18001eccb  test    eax, eax
0x18001eccd  js      loc_18001EDE3
0x18001ecd3  mov     rcx, [rsp+510h+var_4C8]
0x18001ecd8  lea     rdx, [rsp+510h+var_4D0]
0x18001ecdd  mov     rax, [rcx]
0x18001ece0  mov     rax, [rax+18h]
0x18001ece4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ece9  mov     ebx, eax
0x18001eceb  test    eax, eax
0x18001eced  js      loc_18001EDE3
0x18001ecf3  cmp     [rsp+510h+var_4D0], 1
0x18001ecf8  ja      loc_18001EE23
0x18001ecfe  mov     rcx, [rsp+510h+var_4C8]
0x18001ed03  lea     r8, [rsp+510h+var_4C0]
0x18001ed08  xor     edx, edx
0x18001ed0a  mov     rax, [rcx]
0x18001ed0d  mov     rax, [rax+20h]
0x18001ed11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed16  mov     ebx, eax
0x18001ed18  test    eax, eax
0x18001ed1a  js      loc_18001EDE3
0x18001ed20  mov     rcx, [rsp+510h+var_4C0]
0x18001ed25  lea     r8, [rsp+510h+var_4A8]
0x18001ed2a  xor     r9d, r9d
0x18001ed2d  mov     [rsp+510h+var_4F0], r14
0x18001ed32  lea     rdx, aName_0; "name"
0x18001ed39  mov     rax, [rcx]
0x18001ed3c  mov     rax, [rax+40h]
0x18001ed40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed45  mov     ebx, eax
0x18001ed47  test    eax, eax
0x18001ed49  js      loc_18001EDE3
0x18001ed4f  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x18001ed56  lea     rcx, [rsp+510h+var_4A0]
0x18001ed5b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001ed62  nop     dword ptr [rax+rax+00h]
0x18001ed67  mov     ebx, eax
0x18001ed69  test    eax, eax
0x18001ed6b  js      short loc_18001EDE3
0x18001ed6d  mov     rdx, [rsp+510h+var_4A8]
0x18001ed72  lea     rcx, [rsp+510h+var_4A0]
0x18001ed77  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001ed7e  nop     dword ptr [rax+rax+00h]
0x18001ed83  mov     ebx, eax
0x18001ed85  test    eax, eax
0x18001ed87  js      short loc_18001EDE3
0x18001ed89  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001ed90  lea     rcx, [rbp+410h+var_468]
0x18001ed94  mov     rsi, [rax+5D8h]
0x18001ed9b  mov     rax, [rsi]
0x18001ed9e  mov     rdi, [rax+20h]
0x18001eda2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001eda9  nop     dword ptr [rax+rax+00h]
0x18001edae  lea     rcx, [rsp+510h+var_4A0]
0x18001edb3  mov     rbx, rax
0x18001edb6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001edbd  nop     dword ptr [rax+rax+00h]
0x18001edc2  lea     r9, [rsp+510h+var_4B0]
0x18001edc7  mov     [rsp+510h+var_4F0], r14
0x18001edcc  mov     rdx, rax
0x18001edcf  mov     r8, rbx
0x18001edd2  mov     rax, rdi
0x18001edd5  mov     rcx, rsi
0x18001edd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eddd  mov     ebx, eax
0x18001eddf  test    eax, eax
0x18001ede1  jns     short loc_18001EE23
0x18001ede3  test    byte ptr cs:g_dwDebugFlags, 3
0x18001edea  jz      short loc_18001EE23
0x18001edec  mov     rcx, cs:g_pDebug
0x18001edf3  lea     rax, aPreinitsitesth; "PreInitSitesThread: Premature Exit Occu"...
0x18001edfa  mov     dword ptr [rsp+510h+var_4E8], ebx
0x18001edfe  lea     r9, aW3ServerPreini; "W3_SERVER::PreInitSitePathThread"
0x18001ee05  mov     r8d, 10B2h
0x18001ee0b  mov     [rsp+510h+var_4F0], rax
0x18001ee10  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001ee17  call    cs:__imp_PuDbgPrint
0x18001ee1e  nop     dword ptr [rax+rax+00h]
0x18001ee23  mov     rcx, [rsp+510h+var_4C0]
0x18001ee28  test    rcx, rcx
0x18001ee2b  jz      short loc_18001EE3E
0x18001ee2d  mov     rax, [rcx]
0x18001ee30  mov     rax, [rax+10h]
0x18001ee34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee39  mov     [rsp+510h+var_4C0], r14
0x18001ee3e  mov     rcx, [rsp+510h+var_4C8]
0x18001ee43  test    rcx, rcx
0x18001ee46  jz      short loc_18001EE59
0x18001ee48  mov     rax, [rcx]
0x18001ee4b  mov     rax, [rax+10h]
0x18001ee4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee54  mov     [rsp+510h+var_4C8], r14
0x18001ee59  mov     rcx, [rsp+510h+var_4B8]
0x18001ee5e  test    rcx, rcx
0x18001ee61  jz      short loc_18001EE74
0x18001ee63  mov     rax, [rcx]
0x18001ee66  mov     rax, [rax+10h]
0x18001ee6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee6f  mov     [rsp+510h+var_4B8], r14
0x18001ee74  lea     rcx, [rbp+410h+var_468]
0x18001ee78  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ee7f  nop     dword ptr [rax+rax+00h]
0x18001ee84  lea     rcx, [rsp+510h+var_4A0]
0x18001ee89  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001ee90  nop     dword ptr [rax+rax+00h]
0x18001ee95  mov     eax, ebx
0x18001ee97  mov     rcx, [rbp+410h+var_30]
0x18001ee9e  xor     rcx, rsp; StackCookie
0x18001eea1  call    __security_check_cookie
0x18001eea6  add     rsp, 4F0h
0x18001eead  pop     r14
0x18001eeaf  pop     rdi
0x18001eeb0  pop     rsi
0x18001eeb1  pop     rbx
0x18001eeb2  pop     rbp
0x18001eeb3  retn
```
