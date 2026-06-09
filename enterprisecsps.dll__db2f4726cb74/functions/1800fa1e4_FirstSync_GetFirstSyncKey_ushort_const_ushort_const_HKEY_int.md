# FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)

- ea: `0x1800fa1e4`
- end: `0x1800fa4b3`
- name: `?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z`
- size: `719`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, HKEY *, int)`
- caller_count: `27`
- callee_count: `8`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18003a500`
- `0x18003bc50`
- `0x18003c2d0`
- `0x18003c800`
- `0x18003d010`
- `0x18003d690`
- `0x18003dbc0`
- `0x18003e340`
- `0x18003e870`
- `0x18003eed0`
- `0x1800f9f2c`
- `0x1800fa040`
- `0x1800fa0fc`
- `0x1800fa4bc`
- `0x1800fa5a4`
- `0x1800fa68c`
- `0x1800fa764`
- `0x1800fa83c`
- `0x1800faa68`
- `0x1800faeb4`
- `0x1800fafb0`
- `0x1800fb0a4`
- `0x1800fb2fc`
- `0x1800fb440`
- `0x1800fb594`
- `0x1800fb67c`
- `0x1800fb764`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000d4d4`
- `0x18002201c`
- `0x180025ac0`
- `0x18002aed0`
- `0x18002dcc8`
- `0x1800fa1e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fa400`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fa400`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fa30d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fa44d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fa30d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fa44d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa2b1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa33b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa35f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa2b1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa33b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800fa35f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800fa289`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800fa289`

## pseudocode

```c
__int64 __fastcall FirstSync::GetFirstSyncKey(PCWSTR pszMore, PCWSTR a2, unsigned __int16 *a3, HKEY *a4)
{
  int v4; // r14d
  __int64 v8; // rdx
  int v9; // ebx
  const WCHAR *v10; // rax
  LSTATUS v11; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  HKEY *p_lpdwDisposition; // rcx
  unsigned int v15; // eax
  int v16; // eax
  bool v17; // sf
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v22; // [rsp+50h] [rbp-B0h] BYREF
  HKEY lpdwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszPathOut[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = (int)a4;
  if ( pszMore )
  {
    if ( !a3 )
    {
      v8 = 368;
      goto LABEL_3;
    }
    *(_QWORD *)a3 = 0;
    memset_0(pszPathOut, 0, 0x208u);
    v10 = (const WCHAR *)DMGetKnownRegPath(2);
    v9 = PathCchCombine(pszPathOut, 0x104u, v10, pszMore);
    if ( v9 < 0 )
    {
      v8 = 373;
      goto LABEL_4;
    }
    v9 = PathCchAppend(pszPathOut, 0x104u, L"FirstSync");
    if ( v9 < 0 )
    {
      v8 = 374;
      goto LABEL_4;
    }
    if ( a2 )
    {
      lpdwDisposition = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &lpdwDisposition,
        0);
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &lpdwDisposition);
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_20;
      v12 = PathCchAppend(pszPathOut, 0x104u, L"\\");
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 386;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
          (const char *)(unsigned int)v12,
          phkResulta);
LABEL_20:
        p_lpdwDisposition = &lpdwDisposition;
LABEL_31:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(p_lpdwDisposition);
        return (unsigned int)v9;
      }
      v12 = PathCchAppend(pszPathOut, 0x104u, a2);
      v9 = v12;
      if ( v12 < 0 )
      {
        v13 = 387;
        goto LABEL_19;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&lpdwDisposition);
    }
    v22 = 0;
    if ( v4 )
    {
      LODWORD(lpdwDisposition) = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v22,
        0);
      v15 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0xF003Fu, 0, &v22, (LPDWORD)&lpdwDisposition);
      if ( v15 )
      {
        v16 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x18A,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
                (const char *)v15,
                phkResultb);
LABEL_28:
        v9 = v16;
LABEL_30:
        p_lpdwDisposition = &v22;
        goto LABEL_31;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v22,
        0);
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0x20019u, &v22);
      v17 = v16 < 0;
      if ( v16 > 0 )
      {
        v16 = (unsigned __int16)v16 | 0x80070000;
        v17 = v16 < 0;
      }
      if ( v17 )
        goto LABEL_28;
    }
    v9 = 0;
    *(_QWORD *)a3 = v22;
    v22 = 0;
    goto LABEL_30;
  }
  v8 = 367;
LABEL_3:
  v9 = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)(unsigned int)v9,
    phkResult);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800fa1e4  mov     [rsp-8+arg_18], rbx
0x1800fa1e9  push    rbp
0x1800fa1ea  push    rsi
0x1800fa1eb  push    rdi
0x1800fa1ec  push    r12
0x1800fa1ee  push    r14
0x1800fa1f0  lea     rbp, [rsp-180h]
0x1800fa1f8  sub     rsp, 280h
0x1800fa1ff  mov     rax, cs:__security_cookie
0x1800fa206  xor     rax, rsp
0x1800fa209  mov     [rbp+1A0h+var_30], rax
0x1800fa210  mov     r14d, r9d
0x1800fa213  mov     rdi, r8
0x1800fa216  mov     rsi, rdx
0x1800fa219  mov     rbx, rcx
0x1800fa21c  test    rcx, rcx
0x1800fa21f  jnz     short loc_1800FA246
0x1800fa221  mov     edx, 16Fh; void *
0x1800fa226  mov     ebx, 80070057h
0x1800fa22b  mov     rcx, [rbp+1A8h]; this
0x1800fa232  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fa239  mov     r9d, ebx; char *
0x1800fa23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa241  jmp     loc_1800FA48A
0x1800fa246  test    rdi, rdi
0x1800fa249  jnz     short loc_1800FA252
0x1800fa24b  mov     edx, 170h
0x1800fa250  jmp     short loc_1800FA226
0x1800fa252  mov     qword ptr [r8], 0
0x1800fa259  lea     rcx, [rsp+2A0h+pszPathOut]; void *
0x1800fa25e  mov     r8d, 208h; Size
0x1800fa264  xor     edx, edx; Val
0x1800fa266  call    memset_0
0x1800fa26b  mov     ecx, 2
0x1800fa270  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800fa275  mov     r12d, 104h
0x1800fa27b  lea     rcx, [rsp+2A0h+pszPathOut]; pszPathOut
0x1800fa280  mov     edx, r12d; cchPathOut
0x1800fa283  mov     r8, rax; pszPathIn
0x1800fa286  mov     r9, rbx; pszMore
0x1800fa289  call    cs:__imp_PathCchCombine
0x1800fa290  nop     dword ptr [rax+rax+00h]
0x1800fa295  mov     ebx, eax
0x1800fa297  test    eax, eax
0x1800fa299  jns     short loc_1800FA2A2
0x1800fa29b  lea     edx, [r12+71h]
0x1800fa2a0  jmp     short loc_1800FA22B
0x1800fa2a2  lea     r8, aFirstsync; "FirstSync"
0x1800fa2a9  mov     rdx, r12; cchPath
0x1800fa2ac  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800fa2b1  call    cs:__imp_PathCchAppend
0x1800fa2b8  nop     dword ptr [rax+rax+00h]
0x1800fa2bd  mov     ebx, eax
0x1800fa2bf  test    eax, eax
0x1800fa2c1  jns     short loc_1800FA2CD
0x1800fa2c3  mov     edx, 176h
0x1800fa2c8  jmp     loc_1800FA22B
0x1800fa2cd  mov     rbx, 0FFFFFFFF80000002h
0x1800fa2d4  test    rsi, rsi
0x1800fa2d7  jz      loc_1800FA3A7
0x1800fa2dd  xor     edx, edx
0x1800fa2df  mov     [rsp+2A0h+var_248], 0
0x1800fa2e8  lea     rcx, [rsp+2A0h+var_248]
0x1800fa2ed  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800fa2f2  lea     rax, [rsp+2A0h+var_248]
0x1800fa2f7  mov     r9d, 20019h; samDesired
0x1800fa2fd  xor     r8d, r8d; ulOptions
0x1800fa300  mov     [rsp+2A0h+phkResult], rax; int
0x1800fa305  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800fa30a  mov     rcx, rbx; hKey
0x1800fa30d  call    cs:__imp_RegOpenKeyExW
0x1800fa314  nop     dword ptr [rax+rax+00h]
0x1800fa319  mov     ebx, eax
0x1800fa31b  test    eax, eax
0x1800fa31d  jle     short loc_1800FA328
0x1800fa31f  movzx   ebx, ax
0x1800fa322  or      ebx, 80070000h
0x1800fa328  test    ebx, ebx
0x1800fa32a  js      short loc_1800FA38C
0x1800fa32c  lea     r8, StringValue; "\\"
0x1800fa333  mov     rdx, r12; cchPath
0x1800fa336  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800fa33b  call    cs:__imp_PathCchAppend
0x1800fa342  nop     dword ptr [rax+rax+00h]
0x1800fa347  mov     ebx, eax
0x1800fa349  test    eax, eax
0x1800fa34b  jns     short loc_1800FA354
0x1800fa34d  mov     edx, 182h
0x1800fa352  jmp     short loc_1800FA376
0x1800fa354  mov     r8, rsi; pszMore
0x1800fa357  lea     rcx, [rsp+2A0h+pszPathOut]; pszPath
0x1800fa35c  mov     rdx, r12; cchPath
0x1800fa35f  call    cs:__imp_PathCchAppend
0x1800fa366  nop     dword ptr [rax+rax+00h]
0x1800fa36b  mov     ebx, eax
0x1800fa36d  test    eax, eax
0x1800fa36f  jns     short loc_1800FA396
0x1800fa371  mov     edx, 183h; void *
0x1800fa376  mov     rcx, [rbp+1A8h]; this
0x1800fa37d  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fa384  mov     r9d, eax; char *
0x1800fa387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fa38c  lea     rcx, [rsp+2A0h+var_248]
0x1800fa391  jmp     loc_1800FA485
0x1800fa396  lea     rcx, [rsp+2A0h+var_248]
0x1800fa39b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fa3a0  mov     rbx, 0FFFFFFFF80000002h
0x1800fa3a7  xor     edx, edx
0x1800fa3a9  mov     [rsp+2A0h+var_250], 0
0x1800fa3b2  lea     rcx, [rsp+2A0h+var_250]
0x1800fa3b7  test    r14d, r14d
0x1800fa3ba  jz      short loc_1800FA42D
0x1800fa3bc  mov     dword ptr [rsp+2A0h+var_248], edx
0x1800fa3c0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800fa3c5  lea     rax, [rsp+2A0h+var_248]
0x1800fa3ca  xor     r9d, r9d; lpClass
0x1800fa3cd  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800fa3d2  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800fa3d7  lea     rax, [rsp+2A0h+var_250]
0x1800fa3dc  xor     r8d, r8d; Reserved
0x1800fa3df  mov     [rsp+2A0h+var_268], rax; phkResult
0x1800fa3e4  mov     rcx, rbx; hKey
0x1800fa3e7  mov     [rsp+2A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800fa3f0  mov     [rsp+2A0h+samDesired], 0F003Fh; samDesired
0x1800fa3f8  mov     dword ptr [rsp+2A0h+phkResult], 0; unsigned int
0x1800fa400  call    cs:__imp_RegCreateKeyExW
0x1800fa407  nop     dword ptr [rax+rax+00h]
0x1800fa40c  test    eax, eax
0x1800fa40e  jz      short loc_1800FA46D
0x1800fa410  mov     rcx, [rbp+1A8h]; this
0x1800fa417  lea     r8, aOnecoreuapAdmi_111; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800fa41e  mov     r9d, eax; char *
0x1800fa421  mov     edx, 18Ah; void *
0x1800fa426  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800fa42b  jmp     short loc_1800FA469
0x1800fa42d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800fa432  lea     rax, [rsp+2A0h+var_250]
0x1800fa437  mov     r9d, 20019h; samDesired
0x1800fa43d  xor     r8d, r8d; ulOptions
0x1800fa440  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800fa445  lea     rdx, [rsp+2A0h+pszPathOut]; lpSubKey
0x1800fa44a  mov     rcx, rbx; hKey
0x1800fa44d  call    cs:__imp_RegOpenKeyExW
0x1800fa454  nop     dword ptr [rax+rax+00h]
0x1800fa459  test    eax, eax
0x1800fa45b  jle     short loc_1800FA467
0x1800fa45d  movzx   eax, ax
0x1800fa460  or      eax, 80070000h
0x1800fa465  test    eax, eax
0x1800fa467  jns     short loc_1800FA46D
0x1800fa469  mov     ebx, eax
0x1800fa46b  jmp     short loc_1800FA480
0x1800fa46d  mov     rax, [rsp+2A0h+var_250]
0x1800fa472  xor     ebx, ebx
0x1800fa474  mov     [rdi], rax
0x1800fa477  mov     [rsp+2A0h+var_250], 0
0x1800fa480  lea     rcx, [rsp+2A0h+var_250]
0x1800fa485  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800fa48a  mov     eax, ebx
0x1800fa48c  mov     rcx, [rbp+1A0h+var_30]
0x1800fa493  xor     rcx, rsp; StackCookie
0x1800fa496  call    __security_check_cookie
0x1800fa49b  mov     rbx, [rsp+2A0h+arg_18]
0x1800fa4a3  add     rsp, 280h
0x1800fa4aa  pop     r14
0x1800fa4ac  pop     r12
0x1800fa4ae  pop     rdi
0x1800fa4af  pop     rsi
0x1800fa4b0  pop     rbp
0x1800fa4b1  retn
```
