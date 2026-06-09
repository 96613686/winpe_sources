# CDummySnapinC::GetResultViewType(__int64,ushort * *,long *)

- ea: `0x18008a0e0`
- end: `0x18008a2cb`
- name: `?GetResultViewType@CDummySnapinC@@UEAAJ_JPEAPEAGPEAJ@Z`
- size: `491`
- prototype: `__int64 __fastcall(CDummySnapinC *__hidden this, __int64, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180019670`
- `0x18008a0e0`
- `0x18008b4c0`
- `0x180134540`

## import_xrefs

- `mmcbase!?HrFromSc@@YAJAEBVSC@mmcerror@@@Z` at `0x18008a29a`
- `mmcbase!?HrFromSc@@YAJAEBVSC@mmcerror@@@Z` at `0x18008a29a`
- `mmcbase!?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18008a28f`
- `mmcbase!?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x18008a28f`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18008a110`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18008a110`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18008a142`
- `mmcbase!?IsError@SC@mmcerror@@QEBA_NXZ` at `0x18008a142`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a137`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a16b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a1a7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a209`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a24f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a26e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a137`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a16b`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a1a7`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a209`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a24f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18008a26e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a176`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a1b2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a214`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a279`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a176`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a1b2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a214`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18008a279`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008a2a7`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18008a2a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a1e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18008a1e6`
- `ole32!CoTaskMemFree` at `0x18008a189`
- `ole32!CoTaskMemFree` at `0x18008a189`
- `ole32!CoTaskMemAlloc` at `0x18008a237`
- `ole32!CoTaskMemAlloc` at `0x18008a237`
- `ole32!StringFromCLSID` at `0x18008a12a`
- `ole32!StringFromCLSID` at `0x18008a12a`

## pseudocode

```c
__int64 __fastcall CDummySnapinC::GetResultViewType(CDummySnapinC *this, __int64 a2, unsigned __int16 **a3, int *a4)
{
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rax
  unsigned int v10; // eax
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  _BYTE v16[24]; // [rsp+20h] [rbp-E0h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v18[520]; // [rsp+40h] [rbp-C0h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v16, 0);
  lpsz = 0;
  v5 = StringFromCLSID(&CLSID_MessageView, &lpsz);
  mmcerror::SC::operator=(v16, v5);
  v6 = -1;
  if ( mmcerror::SC::IsError((mmcerror::SC *)v16) )
  {
    v8 = StringCchCopyW(v18, 0x208u, L"res://");
    mmcerror::SC::operator=(v16, v8);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v16) )
      goto LABEL_12;
    v9 = -1;
    do
      ++v9;
    while ( v18[v9] );
    GetModuleFileNameW(0, &v18[v9], 520 - v9);
    v10 = StringCchCatW(v18, 0x208u, L"/error.htm");
    mmcerror::SC::operator=(v16, v10);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v16) )
      goto LABEL_12;
  }
  else
  {
    v7 = StringCchCopyW(v18, 0x208u, lpsz);
    mmcerror::SC::operator=(v16, v7);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v16) )
    {
LABEL_12:
      TraceError(L"CDummySnapinC::GetResultViewType", (const struct mmcerror::SC *)v16);
      goto LABEL_13;
    }
    CoTaskMemFree(lpsz);
  }
  do
    ++v6;
  while ( v18[v6] );
  v11 = (int)v6 + 1;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v11);
  *a3 = v12;
  if ( !v12 )
  {
    mmcerror::SC::operator=(v16, 2147942414LL);
    goto LABEL_12;
  }
  v13 = StringCchCopyW(v12, v11, v18);
  mmcerror::SC::operator=(v16, v13);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v16) )
    goto LABEL_12;
LABEL_13:
  v14 = HrFromSc((const struct mmcerror::SC *)v16);
  mmcerror::SC::~SC((mmcerror::SC *)v16);
  return v14;
}

```

## disassembly

```asm
0x18008a0e0  push    rbp
0x18008a0e2  push    rbx
0x18008a0e3  push    rsi
0x18008a0e4  push    r14
0x18008a0e6  lea     rbp, [rsp-368h]
0x18008a0ee  sub     rsp, 468h
0x18008a0f5  mov     rax, cs:__security_cookie
0x18008a0fc  xor     rax, rsp
0x18008a0ff  mov     [rbp+380h+var_30], rax
0x18008a106  xor     edx, edx
0x18008a108  lea     rcx, [rsp+480h+var_460]
0x18008a10d  mov     rsi, r8
0x18008a110  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18008a116  xor     r14d, r14d
0x18008a119  lea     rdx, [rsp+480h+lpsz]; lplpsz
0x18008a11e  lea     rcx, CLSID_MessageView; rclsid
0x18008a125  mov     [rsp+480h+lpsz], r14
0x18008a12a  call    cs:__imp_StringFromCLSID
0x18008a130  mov     edx, eax
0x18008a132  lea     rcx, [rsp+480h+var_460]
0x18008a137  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a13d  lea     rcx, [rsp+480h+var_460]
0x18008a142  call    cs:__imp_?IsError@SC@mmcerror@@QEBA_NXZ; mmcerror::SC::IsError(void)
0x18008a148  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008a14c  lea     rcx, [rsp+480h+var_440]; unsigned __int16 *
0x18008a151  mov     edx, 208h; unsigned __int64
0x18008a156  test    al, al
0x18008a158  jnz     short loc_18008A194
0x18008a15a  mov     r8, [rsp+480h+lpsz]; unsigned __int16 *
0x18008a15f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008a164  mov     edx, eax
0x18008a166  lea     rcx, [rsp+480h+var_460]
0x18008a16b  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a171  lea     rcx, [rsp+480h+var_460]
0x18008a176  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008a17c  test    al, al
0x18008a17e  jnz     loc_18008A283
0x18008a184  mov     rcx, [rsp+480h+lpsz]; pv
0x18008a189  call    cs:__imp_CoTaskMemFree
0x18008a18f  jmp     loc_18008A21E
0x18008a194  lea     r8, aRes; "res://"
0x18008a19b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008a1a0  mov     edx, eax
0x18008a1a2  lea     rcx, [rsp+480h+var_460]
0x18008a1a7  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a1ad  lea     rcx, [rsp+480h+var_460]
0x18008a1b2  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008a1b8  test    al, al
0x18008a1ba  jnz     loc_18008A283
0x18008a1c0  lea     rcx, [rsp+480h+var_440]
0x18008a1c5  mov     rax, rbx
0x18008a1c8  inc     rax
0x18008a1cb  cmp     [rcx+rax*2], r14w
0x18008a1d0  jnz     short loc_18008A1C8
0x18008a1d2  mov     r8d, 208h
0x18008a1d8  lea     rdx, [rsp+480h+var_440]
0x18008a1dd  sub     r8d, eax; nSize
0x18008a1e0  lea     rdx, [rdx+rax*2]; lpFilename
0x18008a1e4  xor     ecx, ecx; hModule
0x18008a1e6  call    cs:__imp_GetModuleFileNameW
0x18008a1ec  lea     r8, aErrorHtm; "/error.htm"
0x18008a1f3  mov     edx, 208h; unsigned __int64
0x18008a1f8  lea     rcx, [rsp+480h+var_440]; unsigned __int16 *
0x18008a1fd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008a202  mov     edx, eax
0x18008a204  lea     rcx, [rsp+480h+var_460]
0x18008a209  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a20f  lea     rcx, [rsp+480h+var_460]
0x18008a214  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008a21a  test    al, al
0x18008a21c  jnz     short loc_18008A283
0x18008a21e  lea     rax, [rsp+480h+var_440]
0x18008a223  inc     rbx
0x18008a226  cmp     [rax+rbx*2], r14w
0x18008a22b  jnz     short loc_18008A223
0x18008a22d  lea     eax, [rbx+1]
0x18008a230  movsxd  rbx, eax
0x18008a233  lea     rcx, [rbx+rbx]; cb
0x18008a237  call    cs:__imp_CoTaskMemAlloc
0x18008a23d  mov     [rsi], rax
0x18008a240  test    rax, rax
0x18008a243  jnz     short loc_18008A257
0x18008a245  mov     edx, 8007000Eh
0x18008a24a  lea     rcx, [rsp+480h+var_460]
0x18008a24f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a255  jmp     short loc_18008A283
0x18008a257  lea     r8, [rsp+480h+var_440]; unsigned __int16 *
0x18008a25c  mov     rdx, rbx; unsigned __int64
0x18008a25f  mov     rcx, rax; unsigned __int16 *
0x18008a262  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008a267  mov     edx, eax
0x18008a269  lea     rcx, [rsp+480h+var_460]
0x18008a26e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18008a274  lea     rcx, [rsp+480h+var_460]
0x18008a279  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18008a27f  test    al, al
0x18008a281  jz      short loc_18008A295
0x18008a283  lea     rdx, [rsp+480h+var_460]
0x18008a288  lea     rcx, aCdummysnapincG; "CDummySnapinC::GetResultViewType"
0x18008a28f  call    cs:__imp_?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceError(ushort const *,mmcerror::SC const &)
0x18008a295  lea     rcx, [rsp+480h+var_460]
0x18008a29a  call    cs:__imp_?HrFromSc@@YAJAEBVSC@mmcerror@@@Z; HrFromSc(mmcerror::SC const &)
0x18008a2a0  lea     rcx, [rsp+480h+var_460]
0x18008a2a5  mov     ebx, eax
0x18008a2a7  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18008a2ad  mov     eax, ebx
0x18008a2af  mov     rcx, [rbp+380h+var_30]
0x18008a2b6  xor     rcx, rsp; StackCookie
0x18008a2b9  call    __security_check_cookie
0x18008a2be  add     rsp, 468h
0x18008a2c5  pop     r14
0x18008a2c7  pop     rsi
0x18008a2c8  pop     rbx
0x18008a2c9  pop     rbp
0x18008a2ca  retn
```
