# CONFIG_SYSTEM::SetMetadata(ushort *,tagVARIANT)

- ea: `0x18003b960`
- end: `0x18003c052`
- name: `?SetMetadata@CONFIG_SYSTEM@@UEAAJPEAGUtagVARIANT@@@Z`
- size: `1778`
- prototype: `int(CONFIG_SYSTEM *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010468`
- `0x18001a314`
- `0x18001a588`
- `0x18001a648`
- `0x18001c250`
- `0x180035ff0`
- `0x18003b960`
- `0x18004dde0`
- `0x180050944`
- `0x1800509d4`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18003c020`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003c020`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003bac0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003bf26`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003bac0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003bf26`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003b9da`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003b9da`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003bacd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003bacd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003ba9f`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003ba9f`
- `OLEAUT32!__imp_VariantInit` at `0x18003b9e8`
- `OLEAUT32!__imp_VariantInit` at `0x18003b9f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003bf6d`
- `OLEAUT32!__imp_VariantInit` at `0x18003b9e8`
- `OLEAUT32!__imp_VariantInit` at `0x18003b9f2`
- `OLEAUT32!__imp_VariantInit` at `0x18003bf6d`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfcf`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfdc`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfe7`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfcf`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfdc`
- `OLEAUT32!__imp_VariantClear` at `0x18003bfe7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003baff`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bbb5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bc36`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bcc8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bd18`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bd68`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bdb8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003be08`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003be52`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bea7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003beeb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bf84`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003baff`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bbb5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bc36`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bcc8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bd18`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bd68`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bdb8`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003be08`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003be52`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bea7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003beeb`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003bf84`

## string_xrefs

- `0x18003ba1a`: `pathMapper`
- `0x18003bb88`: `pathMapper2`
- `0x18003bde9`: `disableExtensions`
- `0x18003be33`: `hideExceptionPhysicalPath`
- `0x18003ba5f`: `AdministrationConfig`
- `0x18003bfaf`: `CONFIG_SYSTEM::SetMetadata`

## pseudocode

```c
__int64 __fastcall CONFIG_SYSTEM::SetMetadata(CONFIG_SYSTEM *this, unsigned __int16 *a2, struct tagVARIANT *a3)
{
  struct IUnknown *v6; // rdi
  HRESULT AdministrationConfigPath; // ebx
  struct IUnknown *v8; // rax
  const unsigned __int16 *v9; // rax
  struct IAppHostChangeHandler *v10; // rdx
  int v11; // eax
  struct IAppHostChangeHandler *v12; // rdx
  int v13; // eax
  unsigned int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  const unsigned __int16 *bstrVal; // rbx
  const unsigned __int16 *Str; // rax
  int v22; // edx
  int v23; // ecx
  struct IUnknown *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct IAppHostChangeHandler *v26; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG v28; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvargDest; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[56]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v31[264]; // [rsp+E0h] [rbp-20h] BYREF

  v25 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&pvargDest, 0, sizeof(pvargDest));
  memset_0(v31, 0, 0x208u);
  STRU::STRU((STRU *)v30, v31, 0x104u);
  v6 = 0;
  VariantInit(&pvarg);
  VariantInit(&pvargDest);
  if ( !a2 )
  {
    AdministrationConfigPath = -2147024809;
    goto LABEL_84;
  }
  if ( *((_DWORD *)this + 7) )
  {
    AdministrationConfigPath = -2147024863;
    goto LABEL_84;
  }
  if ( wcscmp_0(L"pathMapper", a2) )
  {
    if ( !wcscmp_0(L"pathMapper2", a2) )
    {
      v10 = 0;
      v26 = 0;
      if ( a3->vt )
      {
        AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xDu);
        if ( AdministrationConfigPath < 0 )
          goto LABEL_84;
        AdministrationConfigPath = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IAppHostChangeHandler **))pvarg.llVal)(
                                     pvarg.llVal,
                                     &IID_IAppHostPathMapper2,
                                     &v26);
        if ( AdministrationConfigPath < 0 )
          goto LABEL_84;
        v10 = v26;
      }
      v11 = CONFIG_CACHE::SetPathMapper(
              (CONFIG_SYSTEM *)((char *)this + 40),
              (struct IUnknown *)v10,
              &IID_IAppHostPathMapper2);
      goto LABEL_35;
    }
    if ( !wcscmp_0(L"changeHandler", a2) )
    {
      v12 = 0;
      v26 = 0;
      if ( a3->vt )
      {
        AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xDu);
        if ( AdministrationConfigPath < 0 )
          goto LABEL_84;
        AdministrationConfigPath = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IAppHostChangeHandler **))pvarg.llVal)(
                                     pvarg.llVal,
                                     &IID_IAppHostChangeHandler,
                                     &v26);
        if ( AdministrationConfigPath < 0 )
          goto LABEL_84;
        v12 = v26;
      }
      v11 = CONFIG_CHANGE_NOTIFIER::SetChangeHandler((CONFIG_SYSTEM *)((char *)this + 880), v12);
LABEL_35:
      AdministrationConfigPath = v11;
      if ( v11 < 0 )
        goto LABEL_84;
      if ( v26 )
        ((void (__fastcall *)(struct IAppHostChangeHandler *))v26->lpVtbl->Release)(v26);
      goto LABEL_79;
    }
    if ( !wcscmp_0(L"ignoreInvalidAttributes", a2) )
    {
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v13 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v13 | 1;
      else
        v14 = v13 & 0xFFFFFFFE;
    }
    else if ( !wcscmp_0(L"ignoreInvalidRanges", a2) )
    {
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v15 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v15 | 2;
      else
        v14 = v15 & 0xFFFFFFFD;
    }
    else if ( !wcscmp_0(L"ignoreInvalidDecryption", a2) )
    {
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v16 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v16 | 8;
      else
        v14 = v16 & 0xFFFFFFF7;
    }
    else if ( !wcscmp_0(L"expandEnvironmentStrings", a2) )
    {
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v17 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v17 | 0x20;
      else
        v14 = v17 & 0xFFFFFFDF;
    }
    else if ( !wcscmp_0(L"disableExtensions", a2) )
    {
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v18 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v18 | 0x40;
      else
        v14 = v18 & 0xFFFFFFBF;
    }
    else
    {
      if ( wcscmp_0(L"hideExceptionPhysicalPath", a2) )
      {
        if ( !wcscmp_0(L"lockMetadata", a2) )
        {
          AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
          if ( AdministrationConfigPath < 0 )
            goto LABEL_84;
          *((_DWORD *)this + 7) = pvarg.iVal == -1;
          goto LABEL_79;
        }
        if ( !wcscmp_0(L"defaultManagedRuntimeVersion", a2) )
        {
          AdministrationConfigPath = VariantChangeType(&pvargDest, a3, 0, 8u);
          if ( AdministrationConfigPath < 0 )
            goto LABEL_84;
          bstrVal = pvargDest.bstrVal;
          CONFIG_CACHE::WriteLock((CONFIG_SYSTEM *)((char *)this + 40));
          AdministrationConfigPath = CONFIG_CACHE::SetManagedRuntimeVersion(
                                       (CONFIG_SYSTEM *)((char *)this + 40),
                                       bstrVal,
                                       0);
          if ( AdministrationConfigPath >= 0 )
          {
            Str = STRU::QueryStr((CONFIG_SYSTEM *)((char *)this + 216));
            AdministrationConfigPath = SMALL_STRU::Copy((CONFIG_SYSTEM *)((char *)this + 816), Str);
          }
          CONFIG_CACHE::WriteUnlock((CONFIG_SYSTEM *)((char *)this + 40));
          if ( AdministrationConfigPath < 0 )
            goto LABEL_84;
        }
        else
        {
          AdministrationConfigPath = -2147024846;
        }
LABEL_79:
        memset(&v28, 0, sizeof(v28));
        VariantInit(&v28);
        if ( VariantChangeType(&v28, a3, 2u, 8u) >= 0 && (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x10) != 0 )
          McTemplateU0zzzpzzz_EtwEventWriteTransfer(
            v23,
            v22,
            (unsigned int)&szDomain,
            (unsigned int)&szDomain,
            (__int64)L"CONFIG_SYSTEM::SetMetadata",
            (char)this,
            (__int64)&szDomain,
            (__int64)a2,
            v28.llVal);
        VariantClear(&v28);
        goto LABEL_83;
      }
      AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xBu);
      if ( AdministrationConfigPath < 0 )
        goto LABEL_84;
      v19 = *((_DWORD *)this + 258);
      if ( pvarg.iVal == -1 )
        v14 = v19 | 0x80;
      else
        v14 = v19 & 0xFFFFFF7F;
    }
    *((_DWORD *)this + 258) = v14;
    goto LABEL_79;
  }
  if ( !*((_QWORD *)this + 130) )
  {
    AdministrationConfigPath = -2147024883;
    goto LABEL_84;
  }
  if ( !a3->vt )
  {
    v25 = 0;
    goto LABEL_20;
  }
  if ( a3->vt == 8 && !wcscmp_0(a3->bstrVal, L"AdministrationConfig") )
  {
    v8 = (struct IUnknown *)operator new(0x50u);
    v6 = v8;
    if ( !v8 )
    {
      AdministrationConfigPath = -2147024888;
LABEL_83:
      v6 = 0;
      goto LABEL_84;
    }
    _InterlockedIncrement(&g_cModuleRefs);
    v8[1].lpVtbl = 0;
    LODWORD(v8[2].lpVtbl) = 1;
    v8->lpVtbl = (struct IUnknownVtbl *)&ADMINISTRATION_CONFIG_PATH_MAPPER::`vftable';
    STRU::STRU((STRU *)&v8[3]);
    AdministrationConfigPath = CONFIG_CACHE::GetAdministrationConfigPath(
                                 (CONFIG_SYSTEM *)((char *)this + 40),
                                 (struct STRU *)v30);
    if ( AdministrationConfigPath >= 0 )
    {
      v9 = STRU::QueryStr((STRU *)v30);
      AdministrationConfigPath = STRU::Copy((STRU *)&v6[3], v9);
      if ( AdministrationConfigPath >= 0 )
      {
        v25 = v6;
LABEL_20:
        AdministrationConfigPath = CONFIG_CACHE::SetPathMapper(
                                     (CONFIG_SYSTEM *)((char *)this + 40),
                                     v6,
                                     &IID_IAppHostPathMapper);
        v6 = 0;
        if ( AdministrationConfigPath < 0 )
          goto LABEL_84;
        if ( v25 )
        {
          ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
          v25 = 0;
        }
        goto LABEL_79;
      }
    }
  }
  else
  {
    AdministrationConfigPath = VariantChangeType(&pvarg, a3, 0, 0xDu);
    if ( AdministrationConfigPath >= 0 )
    {
      AdministrationConfigPath = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IUnknown **))pvarg.llVal)(
                                   pvarg.llVal,
                                   &IID_IAppHostPathMapper,
                                   &v25);
      if ( AdministrationConfigPath >= 0 )
      {
        v6 = v25;
        goto LABEL_20;
      }
    }
  }
LABEL_84:
  VariantClear(&pvargDest);
  VariantClear(&pvarg);
  if ( v25 )
  {
    ((void (__fastcall *)(struct IUnknown *))v25->lpVtbl->Release)(v25);
    v25 = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct IUnknown *))v6->lpVtbl->Release)(v6);
  STRU::~STRU((STRU *)v30);
  return (unsigned int)AdministrationConfigPath;
}

```

## disassembly

```asm
0x18003b960  mov     [rsp-8+arg_18], rbx
0x18003b965  push    rbp
0x18003b966  push    rsi
0x18003b967  push    rdi
0x18003b968  push    r12
0x18003b96a  push    r13
0x18003b96c  push    r14
0x18003b96e  push    r15
0x18003b970  lea     rbp, [rsp-200h]
0x18003b978  sub     rsp, 300h
0x18003b97f  mov     rax, cs:__security_cookie
0x18003b986  xor     rax, rsp
0x18003b989  mov     [rbp+230h+var_40], rax
0x18003b990  xor     eax, eax
0x18003b992  mov     r14, r8
0x18003b995  mov     r15, rdx
0x18003b998  mov     qword ptr [rsp+330h+pvarg+10h], rax
0x18003b99d  mov     rsi, rcx
0x18003b9a0  mov     qword ptr [rbp+230h+pvargDest+10h], rax
0x18003b9a4  xorps   xmm0, xmm0
0x18003b9a7  lea     rcx, [rbp+230h+var_250]; void *
0x18003b9ab  xorps   xmm1, xmm1
0x18003b9ae  xor     r12d, r12d
0x18003b9b1  xor     edx, edx; Val
0x18003b9b3  mov     [rsp+330h+var_2E0], r12
0x18003b9b8  mov     r8d, 208h; Size
0x18003b9be  movups  xmmword ptr [rsp+330h+pvarg], xmm0
0x18003b9c3  movups  xmmword ptr [rbp+230h+pvargDest], xmm1
0x18003b9c7  call    memset_0
0x18003b9cc  mov     r8d, 104h
0x18003b9d2  lea     rdx, [rbp+230h+var_250]
0x18003b9d6  lea     rcx, [rbp+230h+var_288]
0x18003b9da  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003b9e0  lea     rcx, [rsp+330h+pvarg]; pvarg
0x18003b9e5  mov     edi, r12d
0x18003b9e8  call    cs:__imp_VariantInit
0x18003b9ee  lea     rcx, [rbp+230h+pvargDest]; pvarg
0x18003b9f2  call    cs:__imp_VariantInit
0x18003b9f8  test    r15, r15
0x18003b9fb  jnz     short loc_18003BA07
0x18003b9fd  mov     ebx, 80070057h
0x18003ba02  jmp     loc_18003BFD8
0x18003ba07  cmp     [rsi+1Ch], r12d
0x18003ba0b  jz      short loc_18003BA17
0x18003ba0d  mov     ebx, 80070021h
0x18003ba12  jmp     loc_18003BFD8
0x18003ba17  mov     rdx, r15; String2
0x18003ba1a  lea     rcx, aPathmapper; "pathMapper"
0x18003ba21  call    wcscmp_0
0x18003ba26  mov     r13d, 8
0x18003ba2c  test    eax, eax
0x18003ba2e  jnz     loc_18003BB85
0x18003ba34  cmp     [rsi+410h], r12
0x18003ba3b  jnz     short loc_18003BA47
0x18003ba3d  mov     ebx, 8007000Dh
0x18003ba42  jmp     loc_18003BFD8
0x18003ba47  cmp     [r14], r12w
0x18003ba4b  jz      loc_18003BB3C
0x18003ba51  cmp     [r14], r13w
0x18003ba55  jnz     loc_18003BAEE
0x18003ba5b  mov     rcx, [r14+8]; String1
0x18003ba5f  lea     rdx, aAdministration_1; "AdministrationConfig"
0x18003ba66  call    wcscmp_0
0x18003ba6b  test    eax, eax
0x18003ba6d  jnz     short loc_18003BAEE
0x18003ba6f  lea     ecx, [rax+50h]; Size
0x18003ba72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ba77  mov     rdi, rax
0x18003ba7a  test    rax, rax
0x18003ba7d  jz      short loc_18003BAE4
0x18003ba7f  lock inc cs:?g_cModuleRefs@@3JC; long volatile g_cModuleRefs
0x18003ba86  mov     [rax+8], r12
0x18003ba8a  lea     rcx, [rdi+18h]
0x18003ba8e  lea     rax, ??_7ADMINISTRATION_CONFIG_PATH_MAPPER@@6B@; const ADMINISTRATION_CONFIG_PATH_MAPPER::`vftable'
0x18003ba95  mov     dword ptr [rdi+10h], 1
0x18003ba9c  mov     [rdi], rax
0x18003ba9f  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18003baa5  lea     rcx, [rsi+28h]; this
0x18003baa9  lea     rdx, [rbp+230h+var_288]; struct STRU *
0x18003baad  call    ?GetAdministrationConfigPath@CONFIG_CACHE@@QEAAJPEAVSTRU@@@Z; CONFIG_CACHE::GetAdministrationConfigPath(STRU *)
0x18003bab2  mov     ebx, eax
0x18003bab4  test    eax, eax
0x18003bab6  js      loc_18003BFD8
0x18003babc  lea     rcx, [rbp+230h+var_288]
0x18003bac0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003bac6  mov     rdx, rax
0x18003bac9  lea     rcx, [rdi+18h]
0x18003bacd  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003bad3  mov     ebx, eax
0x18003bad5  test    eax, eax
0x18003bad7  js      loc_18003BFD8
0x18003badd  mov     [rsp+330h+var_2E0], rdi
0x18003bae2  jmp     short loc_18003BB41
0x18003bae4  mov     ebx, 80070008h
0x18003bae9  jmp     loc_18003BFD5
0x18003baee  mov     r9d, 0Dh; vt
0x18003baf4  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003baf9  xor     r8d, r8d; wFlags
0x18003bafc  mov     rdx, r14; pvarSrc
0x18003baff  call    cs:__imp_VariantChangeType
0x18003bb05  mov     ebx, eax
0x18003bb07  test    eax, eax
0x18003bb09  js      loc_18003BFD8
0x18003bb0f  mov     rcx, qword ptr [rsp+330h+pvarg+8]
0x18003bb14  lea     r8, [rsp+330h+var_2E0]
0x18003bb19  lea     rdx, IID_IAppHostPathMapper
0x18003bb20  mov     rax, [rcx]
0x18003bb23  mov     rax, [rax]
0x18003bb26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb2b  mov     ebx, eax
0x18003bb2d  test    eax, eax
0x18003bb2f  js      loc_18003BFD8
0x18003bb35  mov     rdi, [rsp+330h+var_2E0]
0x18003bb3a  jmp     short loc_18003BB41
0x18003bb3c  mov     [rsp+330h+var_2E0], r12
0x18003bb41  lea     rcx, [rsi+28h]; this
0x18003bb45  mov     rdx, rdi; struct IUnknown *
0x18003bb48  lea     r8, IID_IAppHostPathMapper; struct _GUID *
0x18003bb4f  call    ?SetPathMapper@CONFIG_CACHE@@QEAAJPEAUIUnknown@@AEBU_GUID@@@Z; CONFIG_CACHE::SetPathMapper(IUnknown *,_GUID const &)
0x18003bb54  mov     ebx, eax
0x18003bb56  mov     rdi, r12
0x18003bb59  test    eax, eax
0x18003bb5b  js      loc_18003BFD8
0x18003bb61  mov     rcx, [rsp+330h+var_2E0]
0x18003bb66  test    rcx, rcx
0x18003bb69  jz      loc_18003BF5A
0x18003bb6f  mov     rax, [rcx]
0x18003bb72  mov     rax, [rax+10h]
0x18003bb76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb7b  mov     [rsp+330h+var_2E0], r12
0x18003bb80  jmp     loc_18003BF5A
0x18003bb85  mov     rdx, r15; String2
0x18003bb88  lea     rcx, aPathmapper2; "pathMapper2"
0x18003bb8f  call    wcscmp_0
0x18003bb94  test    eax, eax
0x18003bb96  jnz     short loc_18003BC02
0x18003bb98  mov     rdx, r12
0x18003bb9b  mov     [rsp+330h+var_2D8], rdx
0x18003bba0  cmp     [r14], r12w
0x18003bba4  jz      short loc_18003BBF0
0x18003bba6  lea     r9d, [rax+0Dh]; vt
0x18003bbaa  xor     r8d, r8d; wFlags
0x18003bbad  mov     rdx, r14; pvarSrc
0x18003bbb0  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bbb5  call    cs:__imp_VariantChangeType
0x18003bbbb  mov     ebx, eax
0x18003bbbd  test    eax, eax
0x18003bbbf  js      loc_18003BFD8
0x18003bbc5  mov     rcx, qword ptr [rsp+330h+pvarg+8]
0x18003bbca  lea     r8, [rsp+330h+var_2D8]
0x18003bbcf  lea     rdx, IID_IAppHostPathMapper2
0x18003bbd6  mov     rax, [rcx]
0x18003bbd9  mov     rax, [rax]
0x18003bbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbe1  mov     ebx, eax
0x18003bbe3  test    eax, eax
0x18003bbe5  js      loc_18003BFD8
0x18003bbeb  mov     rdx, [rsp+330h+var_2D8]; struct IUnknown *
0x18003bbf0  lea     rcx, [rsi+28h]; this
0x18003bbf4  lea     r8, IID_IAppHostPathMapper2; struct _GUID *
0x18003bbfb  call    ?SetPathMapper@CONFIG_CACHE@@QEAAJPEAUIUnknown@@AEBU_GUID@@@Z; CONFIG_CACHE::SetPathMapper(IUnknown *,_GUID const &)
0x18003bc00  jmp     short loc_18003BC7D
0x18003bc02  mov     rdx, r15; String2
0x18003bc05  lea     rcx, aChangehandler; "changeHandler"
0x18003bc0c  call    wcscmp_0
0x18003bc11  test    eax, eax
0x18003bc13  jnz     loc_18003BCA6
0x18003bc19  mov     rdx, r12
0x18003bc1c  mov     [rsp+330h+var_2D8], rdx
0x18003bc21  cmp     [r14], r12w
0x18003bc25  jz      short loc_18003BC71
0x18003bc27  lea     r9d, [rax+0Dh]; vt
0x18003bc2b  xor     r8d, r8d; wFlags
0x18003bc2e  mov     rdx, r14; pvarSrc
0x18003bc31  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bc36  call    cs:__imp_VariantChangeType
0x18003bc3c  mov     ebx, eax
0x18003bc3e  test    eax, eax
0x18003bc40  js      loc_18003BFD8
0x18003bc46  mov     rcx, qword ptr [rsp+330h+pvarg+8]
0x18003bc4b  lea     r8, [rsp+330h+var_2D8]
0x18003bc50  lea     rdx, IID_IAppHostChangeHandler
0x18003bc57  mov     rax, [rcx]
0x18003bc5a  mov     rax, [rax]
0x18003bc5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc62  mov     ebx, eax
0x18003bc64  test    eax, eax
0x18003bc66  js      loc_18003BFD8
0x18003bc6c  mov     rdx, [rsp+330h+var_2D8]; struct IAppHostChangeHandler *
0x18003bc71  lea     rcx, [rsi+370h]; this
0x18003bc78  call    ?SetChangeHandler@CONFIG_CHANGE_NOTIFIER@@QEAAJPEAUIAppHostChangeHandler@@@Z; CONFIG_CHANGE_NOTIFIER::SetChangeHandler(IAppHostChangeHandler *)
0x18003bc7d  mov     ebx, eax
0x18003bc7f  test    eax, eax
0x18003bc81  js      loc_18003BFD8
0x18003bc87  mov     rcx, [rsp+330h+var_2D8]
0x18003bc8c  test    rcx, rcx
0x18003bc8f  jz      loc_18003BF5A
0x18003bc95  mov     rax, [rcx]
0x18003bc98  mov     rax, [rax+10h]
0x18003bc9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bca1  jmp     loc_18003BF5A
0x18003bca6  mov     rdx, r15; String2
0x18003bca9  lea     rcx, aIgnoreinvalida; "ignoreInvalidAttributes"
0x18003bcb0  call    wcscmp_0
0x18003bcb5  test    eax, eax
0x18003bcb7  jnz     short loc_18003BCF6
0x18003bcb9  lea     r9d, [rax+0Bh]; vt
0x18003bcbd  xor     r8d, r8d; wFlags
0x18003bcc0  mov     rdx, r14; pvarSrc
0x18003bcc3  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bcc8  call    cs:__imp_VariantChangeType
0x18003bcce  mov     ebx, eax
0x18003bcd0  test    eax, eax
0x18003bcd2  js      loc_18003BFD8
0x18003bcd8  cmp     word ptr [rsp+330h+pvarg+8], 0FFFFh
0x18003bcde  mov     eax, [rsi+408h]
0x18003bce4  jnz     short loc_18003BCEE
0x18003bce6  or      eax, 1
0x18003bce9  jmp     loc_18003BE7A
0x18003bcee  and     eax, 0FFFFFFFEh
0x18003bcf1  jmp     loc_18003BE7A
0x18003bcf6  mov     rdx, r15; String2
0x18003bcf9  lea     rcx, aIgnoreinvalidr; "ignoreInvalidRanges"
0x18003bd00  call    wcscmp_0
0x18003bd05  test    eax, eax
0x18003bd07  jnz     short loc_18003BD46
0x18003bd09  lea     r9d, [rax+0Bh]; vt
0x18003bd0d  xor     r8d, r8d; wFlags
0x18003bd10  mov     rdx, r14; pvarSrc
0x18003bd13  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bd18  call    cs:__imp_VariantChangeType
0x18003bd1e  mov     ebx, eax
0x18003bd20  test    eax, eax
0x18003bd22  js      loc_18003BFD8
0x18003bd28  cmp     word ptr [rsp+330h+pvarg+8], 0FFFFh
0x18003bd2e  mov     eax, [rsi+408h]
0x18003bd34  jnz     short loc_18003BD3E
0x18003bd36  or      eax, 2
0x18003bd39  jmp     loc_18003BE7A
0x18003bd3e  and     eax, 0FFFFFFFDh
0x18003bd41  jmp     loc_18003BE7A
0x18003bd46  mov     rdx, r15; String2
0x18003bd49  lea     rcx, aIgnoreinvalidd; "ignoreInvalidDecryption"
0x18003bd50  call    wcscmp_0
0x18003bd55  test    eax, eax
0x18003bd57  jnz     short loc_18003BD96
0x18003bd59  lea     r9d, [rax+0Bh]; vt
0x18003bd5d  xor     r8d, r8d; wFlags
0x18003bd60  mov     rdx, r14; pvarSrc
0x18003bd63  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bd68  call    cs:__imp_VariantChangeType
0x18003bd6e  mov     ebx, eax
0x18003bd70  test    eax, eax
0x18003bd72  js      loc_18003BFD8
0x18003bd78  cmp     word ptr [rsp+330h+pvarg+8], 0FFFFh
0x18003bd7e  mov     eax, [rsi+408h]
0x18003bd84  jnz     short loc_18003BD8E
0x18003bd86  or      eax, r13d
0x18003bd89  jmp     loc_18003BE7A
0x18003bd8e  and     eax, 0FFFFFFF7h
0x18003bd91  jmp     loc_18003BE7A
0x18003bd96  mov     rdx, r15; String2
0x18003bd99  lea     rcx, aExpandenvironm; "expandEnvironmentStrings"
0x18003bda0  call    wcscmp_0
0x18003bda5  test    eax, eax
0x18003bda7  jnz     short loc_18003BDE6
0x18003bda9  lea     r9d, [rax+0Bh]; vt
0x18003bdad  xor     r8d, r8d; wFlags
0x18003bdb0  mov     rdx, r14; pvarSrc
0x18003bdb3  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003bdb8  call    cs:__imp_VariantChangeType
0x18003bdbe  mov     ebx, eax
0x18003bdc0  test    eax, eax
0x18003bdc2  js      loc_18003BFD8
0x18003bdc8  cmp     word ptr [rsp+330h+pvarg+8], 0FFFFh
0x18003bdce  mov     eax, [rsi+408h]
0x18003bdd4  jnz     short loc_18003BDDE
0x18003bdd6  or      eax, 20h
0x18003bdd9  jmp     loc_18003BE7A
0x18003bdde  and     eax, 0FFFFFFDFh
0x18003bde1  jmp     loc_18003BE7A
0x18003bde6  mov     rdx, r15; String2
0x18003bde9  lea     rcx, aDisableextensi; "disableExtensions"
0x18003bdf0  call    wcscmp_0
0x18003bdf5  test    eax, eax
0x18003bdf7  jnz     short loc_18003BE30
0x18003bdf9  lea     r9d, [rax+0Bh]; vt
0x18003bdfd  xor     r8d, r8d; wFlags
0x18003be00  mov     rdx, r14; pvarSrc
0x18003be03  lea     rcx, [rsp+330h+pvarg]; pvargDest
0x18003be08  call    cs:__imp_VariantChangeType
0x18003be0e  mov     ebx, eax
0x18003be10  test    eax, eax
0x18003be12  js      loc_18003BFD8
0x18003be18  cmp     word ptr [rsp+330h+pvarg+8], 0FFFFh
0x18003be1e  mov     eax, [rsi+408h]
0x18003be24  jnz     short loc_18003BE2B
0x18003be26  or      eax, 40h
0x18003be29  jmp     short loc_18003BE7A
0x18003be2b  and     eax, 0FFFFFFBFh
  ... truncated ...
```
