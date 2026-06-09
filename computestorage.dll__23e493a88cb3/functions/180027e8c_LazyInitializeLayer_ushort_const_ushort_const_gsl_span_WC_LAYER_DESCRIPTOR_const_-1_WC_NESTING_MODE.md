# LazyInitializeLayer(ushort const *,ushort const *,gsl::span<_WC_LAYER_DESCRIPTOR const,-1>,_WC_NESTING_MODE)

- ea: `0x180027e8c`
- end: `0x18002819c`
- name: `?LazyInitializeLayer@@YAXPEBG0V?$span@$$CBU_WC_LAYER_DESCRIPTOR@@$0?0@gsl@@W4_WC_NESTING_MODE@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800152d0`
- `0x1800154a0`

## callees

- `0x180002690`
- `0x180006e10`
- `0x180008a8c`
- `0x180008fac`
- `0x18000971c`
- `0x18000a578`
- `0x1800127bc`
- `0x1800136f8`
- `0x180013d30`
- `0x180027c64`
- `0x180027e8c`
- `0x1800296d4`
- `0x180029fc8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028091`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028091`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027f80`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800280ed`
- `wc_storage!WcInitializeSandboxEx` at `0x18002804a`
- `wc_storage!WcInitializeSandboxEx` at `0x18002804a`

## string_xrefs

- `0x180028145`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18002815d`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x180028175`: `onecore\vm\compute\shared\storage\layerutilities.cpp`
- `0x18002818a`: `onecore\vm\compute\shared\storage\layerutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall LazyInitializeLayer(PCWSTR pszPathIn, _WORD *a2, __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rsi
  gsl::details *v8; // rcx
  unsigned __int64 v9; // r8
  const WCHAR *p_Src; // rdx
  const WCHAR *v11; // rcx
  const char *v12; // r9
  char v13; // bl
  bool v14; // zf
  char v15; // al
  wil::details::in1diag3 *v16; // rcx
  unsigned __int16 **v17; // rdx
  const unsigned __int16 *v18; // rdx
  __int128 *v19; // rdx
  unsigned __int16 **v20; // rcx
  int v21; // eax
  const WCHAR *v22; // rcx
  char *FileW; // rax
  __int64 v24; // r8
  const char *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  const char *v29; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-99h]
  HANDLE hObject[2]; // [rsp+40h] [rbp-79h] BYREF
  unsigned __int16 *v33[3]; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v34; // [rsp+68h] [rbp-51h]
  __int128 Src; // [rsp+70h] [rbp-49h] BYREF
  __int128 v36; // [rsp+80h] [rbp-39h]
  LPCWSTR lpFileName[3]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int64 v38; // [rsp+A8h] [rbp-11h]
  __int128 v39; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v40; // [rsp+C0h] [rbp+7h]
  __int128 v41; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v42; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v6 = *a3;
  if ( !*a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  v7 = a3[1];
  if ( !a2 )
    goto LABEL_8;
  v8 = (gsl::details *)(v6 - 1);
  if ( !v6 )
  {
    gsl::details::terminate(v8);
LABEL_40:
    wil::details::in1diag3::Throw_GetLastError(
      v16,
      (void *)0x2E,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
      v12);
  }
  if ( LayerHasHiveIntegratedLayout(*(PCWSTR *)(32LL * (_QWORD)v8 + v7 + 24)) )
  {
LABEL_8:
    Vml::CombineFilePath(&Src, pszPathIn, L"WcSandboxState");
  }
  else
  {
    Src = 0;
    v36 = 0;
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    std::wstring::_Construct<1,unsigned short const *>((__int64)&Src, a2, v9);
  }
  v41 = 0;
  v42 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v41, 17);
  p_Src = (const WCHAR *)&Src;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    p_Src = (const WCHAR *)Src;
  Vml::CombineFilePath(lpFileName, p_Src, L"initialized");
  v11 = (const WCHAR *)lpFileName;
  if ( v38 > 7 )
    v11 = lpFileName[0];
  if ( GetFileAttributesW(v11) == -1 )
  {
    v13 = 0;
    v14 = GetLastError() == 2;
    v15 = 1;
    if ( !v14 )
      goto LABEL_17;
  }
  else
  {
    v13 = 1;
  }
  v15 = 0;
LABEL_17:
  v16 = retaddr;
  if ( v15 )
    goto LABEL_40;
  if ( !v13 )
  {
    Vml::CombineFilePath(v33, pszPathIn, L".\\");
    hObject[0] = 0;
    v17 = v33;
    if ( v34 > 7 )
      v17 = (unsigned __int16 **)v33[0];
    GetDiskHandle(hObject, v17);
    v18 = (const unsigned __int16 *)v33;
    if ( v34 > 7 )
      v18 = v33[0];
    ExpandVolume(hObject[0], v18);
    v39 = 0;
    v40 = 0;
    Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v39, 18);
    v19 = &Src;
    if ( *((_QWORD *)&v36 + 1) > 7u )
      v19 = (__int128 *)Src;
    v20 = v33;
    if ( v34 > 7 )
      v20 = (unsigned __int16 **)v33[0];
    v21 = WcInitializeSandboxEx(v20, v19, v7, *(unsigned int *)a3);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        (const char *)(unsigned int)v21,
        0);
    v22 = (const WCHAR *)lpFileName;
    if ( v38 > 7 )
      v22 = lpFileName[0];
    FileW = (char *)CreateFileW(v22, 0x40000000u, 3u, 0, 1u, 0x2000000u, 0);
    hObject[1] = FileW;
    LOBYTE(v26) = ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\layerutilities.cpp",
        v25);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v39, v26, v24, v25);
    if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject[0]);
    std::wstring::~wstring((char **)v33);
  }
  std::wstring::~wstring((char **)lpFileName);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v41, v27, v28, v29);
  return std::wstring::~wstring((char **)&Src);
}

```

## disassembly

```asm
0x180027e8c  mov     [rsp-8+arg_18], rbx
0x180027e91  push    rbp
0x180027e92  push    rsi
0x180027e93  push    rdi
0x180027e94  push    r14
0x180027e96  push    r15
0x180027e98  lea     rbp, [rsp-37h]
0x180027e9d  sub     rsp, 0F0h
0x180027ea4  mov     rax, cs:__security_cookie
0x180027eab  xor     rax, rsp
0x180027eae  mov     [rbp+57h+var_30], rax
0x180027eb2  mov     rdi, r8
0x180027eb5  mov     rbx, rdx
0x180027eb8  mov     r14, rcx
0x180027ebb  xor     r15d, r15d
0x180027ebe  mov     rdx, [r8]
0x180027ec1  mov     rcx, [rbp+5Fh]; this
0x180027ec5  test    rdx, rdx
0x180027ec8  jz      loc_180028157
0x180027ece  mov     rsi, [r8+8]
0x180027ed2  test    rbx, rbx
0x180027ed5  jz      short loc_180027F25
0x180027ed7  mov     rax, [rbp+5Fh]
0x180027edb  lea     rcx, [rdx-1]; this
0x180027edf  cmp     rcx, rdx
0x180027ee2  jnb     loc_18002816F
0x180027ee8  shl     rcx, 5
0x180027eec  mov     rcx, [rcx+rsi+18h]; pszPathIn
0x180027ef1  call    ?LayerHasHiveIntegratedLayout@@YA_NPEBG@Z; LayerHasHiveIntegratedLayout(ushort const *)
0x180027ef6  test    al, al
0x180027ef8  jnz     short loc_180027F25
0x180027efa  xorps   xmm0, xmm0
0x180027efd  movups  [rbp+57h+Src], xmm0
0x180027f01  xorps   xmm1, xmm1
0x180027f04  movdqu  [rbp+57h+var_90], xmm1
0x180027f09  or      r8, 0FFFFFFFFFFFFFFFFh
0x180027f0d  inc     r8
0x180027f10  cmp     [rbx+r8*2], r15w
0x180027f15  jnz     short loc_180027F0D
0x180027f17  mov     rdx, rbx
0x180027f1a  lea     rcx, [rbp+57h+Src]
0x180027f1e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027f23  jmp     short loc_180027F39
0x180027f25  lea     r8, aWcsandboxstate; "WcSandboxState"
0x180027f2c  mov     rdx, r14; pszPathIn
0x180027f2f  lea     rcx, [rbp+57h+Src]; Src
0x180027f33  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180027f38  nop
0x180027f39  xorps   xmm0, xmm0
0x180027f3c  xor     eax, eax
0x180027f3e  movups  [rbp+57h+var_48], xmm0
0x180027f42  mov     [rbp+57h+var_38], rax
0x180027f46  lea     edx, [rax+11h]; int
0x180027f49  lea     rcx, [rbp+57h+var_48]; this
0x180027f4d  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180027f52  nop
0x180027f53  lea     rdx, [rbp+57h+Src]
0x180027f57  cmp     qword ptr [rbp+57h+var_90+8], 7
0x180027f5c  cmova   rdx, qword ptr [rbp+57h+Src]; pszPathIn
0x180027f61  lea     r8, aInitialized; "initialized"
0x180027f68  lea     rcx, [rbp+57h+lpFileName]; Src
0x180027f6c  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180027f71  nop
0x180027f72  lea     rcx, [rbp+57h+lpFileName]
0x180027f76  cmp     [rbp+57h+var_68], 7
0x180027f7b  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180027f80  call    cs:__imp_GetFileAttributesW
0x180027f87  nop     dword ptr [rax+rax+00h]
0x180027f8c  cmp     eax, 0FFFFFFFFh
0x180027f8f  jz      short loc_180027F95
0x180027f91  mov     bl, 1
0x180027f93  jmp     short loc_180027FAB
0x180027f95  mov     bl, r15b
0x180027f98  call    cs:__imp_GetLastError
0x180027f9f  nop     dword ptr [rax+rax+00h]
0x180027fa4  cmp     eax, 2
0x180027fa7  mov     al, 1
0x180027fa9  jnz     short loc_180027FAE
0x180027fab  mov     al, r15b
0x180027fae  mov     rcx, [rbp+5Fh]
0x180027fb2  test    al, al
0x180027fb4  jnz     loc_180028175
0x180027fba  test    bl, bl
0x180027fbc  jnz     loc_180028104
0x180027fc2  lea     r8, pszMore; ".\\"
0x180027fc9  mov     rdx, r14; pszPathIn
0x180027fcc  lea     rcx, [rbp+57h+var_C0]; Src
0x180027fd0  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180027fd5  nop
0x180027fd6  mov     [rbp+57h+hObject], r15
0x180027fda  lea     rdx, [rbp+57h+var_C0]
0x180027fde  cmp     [rbp+57h+var_A8], 7
0x180027fe3  cmova   rdx, [rbp+57h+var_C0]
0x180027fe8  lea     rcx, [rbp+57h+hObject]
0x180027fec  call    ?GetDiskHandle@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBG@Z; GetDiskHandle(ushort const *)
0x180027ff1  nop
0x180027ff2  lea     rdx, [rbp+57h+var_C0]
0x180027ff6  cmp     [rbp+57h+var_A8], 7
0x180027ffb  cmova   rdx, [rbp+57h+var_C0]; unsigned __int16 *
0x180028000  mov     rcx, [rbp+57h+hObject]; void *
0x180028004  call    ?ExpandVolume@@YA_NPEAXPEBG@Z; ExpandVolume(void *,ushort const *)
0x180028009  xorps   xmm0, xmm0
0x18002800c  xor     eax, eax
0x18002800e  movups  [rbp+57h+var_60], xmm0
0x180028012  mov     [rbp+57h+var_50], rax
0x180028016  lea     edx, [rax+12h]; int
0x180028019  lea     rcx, [rbp+57h+var_60]; this
0x18002801d  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x180028022  nop
0x180028023  lea     rdx, [rbp+57h+Src]
0x180028027  cmp     qword ptr [rbp+57h+var_90+8], 7
0x18002802c  cmova   rdx, qword ptr [rbp+57h+Src]
0x180028031  lea     rcx, [rbp+57h+var_C0]
0x180028035  cmp     [rbp+57h+var_A8], 7
0x18002803a  cmova   rcx, [rbp+57h+var_C0]
0x18002803f  mov     [rsp+110h+dwCreationDisposition], r15d; int
0x180028044  mov     r9d, [rdi]
0x180028047  mov     r8, rsi
0x18002804a  call    cs:__imp_WcInitializeSandboxEx
0x180028051  nop     dword ptr [rax+rax+00h]
0x180028056  mov     rcx, [rbp+5Fh]; this
0x18002805a  test    eax, eax
0x18002805c  js      loc_180028187
0x180028062  lea     rcx, [rbp+57h+lpFileName]
0x180028066  cmp     [rbp+57h+var_68], 7
0x18002806b  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x180028070  mov     [rsp+110h+hTemplateFile], r15; hTemplateFile
0x180028075  mov     [rsp+110h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002807d  mov     [rsp+110h+dwCreationDisposition], 1; dwCreationDisposition
0x180028085  xor     r9d, r9d; lpSecurityAttributes
0x180028088  mov     edx, 40000000h; dwDesiredAccess
0x18002808d  lea     r8d, [r9+3]; dwShareMode
0x180028091  call    cs:__imp_CreateFileW
0x180028098  nop     dword ptr [rax+rax+00h]
0x18002809d  mov     [rbp+57h+var_C8], rax
0x1800280a1  lea     rcx, [rax+1]
0x1800280a5  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800280ac  setz    dl
0x1800280af  mov     rcx, [rbp+5Fh]; this
0x1800280b3  test    dl, dl
0x1800280b5  jnz     loc_180028145
0x1800280bb  lea     rcx, [rax-1]
0x1800280bf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800280c3  ja      short loc_1800280D5
0x1800280c5  mov     rcx, rax; hObject
0x1800280c8  call    cs:__imp_CloseHandle
0x1800280cf  nop     dword ptr [rax+rax+00h]
0x1800280d4  nop
0x1800280d5  lea     rcx, [rbp+57h+var_60]; this
0x1800280d9  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x1800280de  nop
0x1800280df  mov     rcx, [rbp+57h+hObject]; hObject
0x1800280e3  lea     rax, [rcx-1]
0x1800280e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800280eb  ja      short loc_1800280FA
0x1800280ed  call    cs:__imp_CloseHandle
0x1800280f4  nop     dword ptr [rax+rax+00h]
0x1800280f9  nop
0x1800280fa  lea     rcx, [rbp+57h+var_C0]
0x1800280fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028103  nop
0x180028104  lea     rcx, [rbp+57h+lpFileName]
0x180028108  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002810d  nop
0x18002810e  lea     rcx, [rbp+57h+var_48]; this
0x180028112  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x180028117  nop
0x180028118  lea     rcx, [rbp+57h+Src]
0x18002811c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028121  mov     rcx, [rbp+57h+var_30]
0x180028125  xor     rcx, rsp; StackCookie
0x180028128  call    __security_check_cookie
0x18002812d  mov     rbx, [rsp+110h+arg_18]
0x180028135  add     rsp, 0F0h
0x18002813c  pop     r15
0x18002813e  pop     r14
0x180028140  pop     rdi
0x180028141  pop     rsi
0x180028142  pop     rbp
0x180028143  retn
0x180028145  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002814c  mov     edx, 4Ah ; 'J'; void *
0x180028151  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028157  mov     r9d, 80070057h; char *
0x18002815d  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028164  mov     edx, 78h ; 'x'; void *
0x180028169  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002816f  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180028174  nop
0x180028175  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x18002817c  mov     edx, 2Eh ; '.'; void *
0x180028181  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180028187  mov     r9d, eax; char *
0x18002818a  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\shared\\storage\\"...
0x180028191  mov     edx, 3Fh ; '?'; void *
0x180028196  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
