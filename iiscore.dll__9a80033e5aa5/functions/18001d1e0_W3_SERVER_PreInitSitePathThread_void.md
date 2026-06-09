# W3_SERVER::PreInitSitePathThread(void *)

- ea: `0x18001d1e0`
- end: `0x18001d48a`
- name: `?PreInitSitePathThread@W3_SERVER@@CAKPEAX@Z`
- size: `682`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001d1e0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d45a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d465`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d45a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001d465`
- `iisutil!PuDbgPrint` at `0x18001d3ff`
- `iisutil!PuDbgPrint` at `0x18001d3ff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d396`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d3a4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d396`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001d3a4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d35b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001d35b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d24b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d270`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d24b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001d270`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d371`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001d371`

## string_xrefs

- `0x18001d3f8`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001d3db`: `PreInitSitesThread: Premature Exit Occured ( hr = %x )\n`
- `0x18001d3e6`: `W3_SERVER::PreInitSitePathThread`

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
0x18001d1e0  push    rbp
0x18001d1e2  push    rbx
0x18001d1e3  push    rsi
0x18001d1e4  push    rdi
0x18001d1e5  push    r14
0x18001d1e7  lea     rbp, [rsp-3F0h]
0x18001d1ef  sub     rsp, 4F0h
0x18001d1f6  mov     rax, cs:__security_cookie
0x18001d1fd  xor     rax, rsp
0x18001d200  mov     [rbp+410h+var_30], rax
0x18001d207  xor     r14d, r14d
0x18001d20a  lea     rcx, [rbp+410h+var_430]; void *
0x18001d20e  mov     ebx, 200h
0x18001d213  mov     [rsp+510h+var_4B8], r14
0x18001d218  mov     edi, 100h
0x18001d21d  mov     [rsp+510h+var_4C8], r14
0x18001d222  mov     r8d, ebx; Size
0x18001d225  mov     [rsp+510h+var_4C0], r14
0x18001d22a  xor     edx, edx; Val
0x18001d22c  mov     [rsp+510h+var_4D0], r14d
0x18001d231  mov     [rsp+510h+var_4A8], r14
0x18001d236  mov     [rsp+510h+var_4B0], edi
0x18001d23a  call    memset_0
0x18001d23f  mov     r8d, edi
0x18001d242  lea     rdx, [rbp+410h+var_430]
0x18001d246  lea     rcx, [rsp+510h+var_4A0]
0x18001d24b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d251  mov     r8d, ebx; Size
0x18001d254  lea     rcx, [rbp+410h+var_230]; void *
0x18001d25b  xor     edx, edx; Val
0x18001d25d  call    memset_0
0x18001d262  mov     r8d, edi
0x18001d265  lea     rdx, [rbp+410h+var_230]
0x18001d26c  lea     rcx, [rbp+410h+var_468]
0x18001d270  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001d276  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001d27d  lea     r9, [rsp+510h+var_4B8]
0x18001d282  mov     [rsp+510h+var_4E8], r14
0x18001d287  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001d28e  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18001d295  mov     [rsp+510h+var_4F0], r14
0x18001d29a  mov     rcx, [rax+5D8h]
0x18001d2a1  mov     rax, [rcx]
0x18001d2a4  mov     rax, [rax+18h]
0x18001d2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ad  mov     ebx, eax
0x18001d2af  test    eax, eax
0x18001d2b1  js      loc_18001D3CB
0x18001d2b7  mov     rcx, [rsp+510h+var_4B8]
0x18001d2bc  lea     rdx, [rsp+510h+var_4C8]
0x18001d2c1  mov     rax, [rcx]
0x18001d2c4  mov     rax, [rax+28h]
0x18001d2c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2cd  mov     ebx, eax
0x18001d2cf  test    eax, eax
0x18001d2d1  js      loc_18001D3CB
0x18001d2d7  mov     rcx, [rsp+510h+var_4C8]
0x18001d2dc  lea     rdx, [rsp+510h+var_4D0]
0x18001d2e1  mov     rax, [rcx]
0x18001d2e4  mov     rax, [rax+18h]
0x18001d2e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ed  mov     ebx, eax
0x18001d2ef  test    eax, eax
0x18001d2f1  js      loc_18001D3CB
0x18001d2f7  cmp     [rsp+510h+var_4D0], 1
0x18001d2fc  ja      loc_18001D405
0x18001d302  mov     rcx, [rsp+510h+var_4C8]
0x18001d307  lea     r8, [rsp+510h+var_4C0]
0x18001d30c  xor     edx, edx
0x18001d30e  mov     rax, [rcx]
0x18001d311  mov     rax, [rax+20h]
0x18001d315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d31a  mov     ebx, eax
0x18001d31c  test    eax, eax
0x18001d31e  js      loc_18001D3CB
0x18001d324  mov     rcx, [rsp+510h+var_4C0]
0x18001d329  lea     r8, [rsp+510h+var_4A8]
0x18001d32e  xor     r9d, r9d
0x18001d331  mov     [rsp+510h+var_4F0], r14
0x18001d336  lea     rdx, aName_0; "name"
0x18001d33d  mov     rax, [rcx]
0x18001d340  mov     rax, [rax+40h]
0x18001d344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d349  mov     ebx, eax
0x18001d34b  test    eax, eax
0x18001d34d  js      short loc_18001D3CB
0x18001d34f  lea     rdx, aMachineWebroot_0; "MACHINE/WEBROOT/APPHOST/"
0x18001d356  lea     rcx, [rsp+510h+var_4A0]
0x18001d35b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18001d361  mov     ebx, eax
0x18001d363  test    eax, eax
0x18001d365  js      short loc_18001D3CB
0x18001d367  mov     rdx, [rsp+510h+var_4A8]
0x18001d36c  lea     rcx, [rsp+510h+var_4A0]
0x18001d371  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001d377  mov     ebx, eax
0x18001d379  test    eax, eax
0x18001d37b  js      short loc_18001D3CB
0x18001d37d  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001d384  lea     rcx, [rbp+410h+var_468]
0x18001d388  mov     rsi, [rax+5D8h]
0x18001d38f  mov     rax, [rsi]
0x18001d392  mov     rdi, [rax+20h]
0x18001d396  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d39c  lea     rcx, [rsp+510h+var_4A0]
0x18001d3a1  mov     rbx, rax
0x18001d3a4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001d3aa  lea     r9, [rsp+510h+var_4B0]
0x18001d3af  mov     [rsp+510h+var_4F0], r14
0x18001d3b4  mov     rdx, rax
0x18001d3b7  mov     r8, rbx
0x18001d3ba  mov     rax, rdi
0x18001d3bd  mov     rcx, rsi
0x18001d3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3c5  mov     ebx, eax
0x18001d3c7  test    eax, eax
0x18001d3c9  jns     short loc_18001D405
0x18001d3cb  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d3d2  jz      short loc_18001D405
0x18001d3d4  mov     rcx, cs:g_pDebug
0x18001d3db  lea     rax, aPreinitsitesth; "PreInitSitesThread: Premature Exit Occu"...
0x18001d3e2  mov     dword ptr [rsp+510h+var_4E8], ebx
0x18001d3e6  lea     r9, aW3ServerPreini; "W3_SERVER::PreInitSitePathThread"
0x18001d3ed  mov     r8d, 10B2h
0x18001d3f3  mov     [rsp+510h+var_4F0], rax
0x18001d3f8  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001d3ff  call    cs:__imp_PuDbgPrint
0x18001d405  mov     rcx, [rsp+510h+var_4C0]
0x18001d40a  test    rcx, rcx
0x18001d40d  jz      short loc_18001D420
0x18001d40f  mov     rax, [rcx]
0x18001d412  mov     rax, [rax+10h]
0x18001d416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d41b  mov     [rsp+510h+var_4C0], r14
0x18001d420  mov     rcx, [rsp+510h+var_4C8]
0x18001d425  test    rcx, rcx
0x18001d428  jz      short loc_18001D43B
0x18001d42a  mov     rax, [rcx]
0x18001d42d  mov     rax, [rax+10h]
0x18001d431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d436  mov     [rsp+510h+var_4C8], r14
0x18001d43b  mov     rcx, [rsp+510h+var_4B8]
0x18001d440  test    rcx, rcx
0x18001d443  jz      short loc_18001D456
0x18001d445  mov     rax, [rcx]
0x18001d448  mov     rax, [rax+10h]
0x18001d44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d451  mov     [rsp+510h+var_4B8], r14
0x18001d456  lea     rcx, [rbp+410h+var_468]
0x18001d45a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d460  lea     rcx, [rsp+510h+var_4A0]
0x18001d465  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001d46b  mov     eax, ebx
0x18001d46d  mov     rcx, [rbp+410h+var_30]
0x18001d474  xor     rcx, rsp; StackCookie
0x18001d477  call    __security_check_cookie
0x18001d47c  add     rsp, 4F0h
0x18001d483  pop     r14
0x18001d485  pop     rdi
0x18001d486  pop     rsi
0x18001d487  pop     rbx
0x18001d488  pop     rbp
0x18001d489  retn
```
