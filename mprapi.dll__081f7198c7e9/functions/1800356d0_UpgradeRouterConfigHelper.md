# UpgradeRouterConfigHelper

- ea: `0x1800356d0`
- end: `0x18003593f`
- name: `UpgradeRouterConfigHelper`
- size: `623`
- prototype: `__int64 __fastcall(struct INetCfg *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026b90`
- `0x180028840`

## callees

- `0x1800355a4`
- `0x1800356d0`
- `0x180035b28`
- `0x180035c70`
- `0x180035e2c`
- `0x180036c94`
- `0x180036f18`
- `0x1800373a0`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003574f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180035768`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003574f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180035768`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035771`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035771`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035728`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035728`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800358b6`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800358b6`
- `rtutils!TracePrintfW` at `0x18003581b`
- `rtutils!TracePrintfW` at `0x180035848`
- `rtutils!TracePrintfW` at `0x18003591a`
- `rtutils!TracePrintfW` at `0x18003581b`
- `rtutils!TracePrintfW` at `0x180035848`
- `rtutils!TracePrintfW` at `0x18003591a`

## string_xrefs

- `0x180035721`: `mprmsg.dll`
- `0x180035807`: `CRasBindObject::HrFindOtherComponents`
- `0x180035834`: `CRasBindObject::HrFindOtherComponents`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UpgradeRouterConfigHelper(struct INetCfg *a1)
{
  struct INetCfg *v2; // rdi
  HMODULE Library; // rax
  CSteelhead *v4; // rcx
  HMODULE v5; // rsi
  CSteelhead *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  const struct _GUID **v9; // r8
  const unsigned __int16 *const *v10; // r9
  unsigned int updated; // ebx
  int v12; // eax
  int Components; // eax
  struct INetCfgComponent **v14; // rsi
  int i; // r14d
  int v16; // esi
  const WCHAR *v17; // rdx
  struct INetCfg *v19; // [rsp+38h] [rbp-4C0h] BYREF
  void **v20; // [rsp+40h] [rbp-4B8h] BYREF
  struct INetCfg *v21; // [rsp+48h] [rbp-4B0h]
  struct INetCfgComponent *v22[10]; // [rsp+50h] [rbp-4A8h] BYREF
  int v23; // [rsp+A0h] [rbp-458h]
  __int64 v24; // [rsp+A8h] [rbp-450h]
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-448h] BYREF
  WCHAR v26[256]; // [rsp+2B0h] [rbp-248h] BYREF
  int IsTransportAvailable; // [rsp+4B0h] [rbp-48h]
  int v28; // [rsp+4B4h] [rbp-44h]

  try
  {
    v2 = 0;
    v19 = 0;
    v23 = 0;
    v21 = 0;
    v20 = &CSteelhead::`vftable';
    v24 = 0;
    Library = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
    v5 = Library;
    if ( Library )
    {
      LoadStringW(Library, 0x4A38u, Buffer, 256);
      LoadStringW(v5, 0x4A39u, v26, 256);
      FreeLibrary(v5);
    }
    IsTransportAvailable = CSteelhead::IsTransportAvailable(v4, 0x21u);
    v28 = CSteelhead::IsTransportAvailable(v6, 0x57u);
    if ( !a1 )
    {
      updated = HrCreateAndInitializeINetCfg(v8, &v19);
      v2 = v19;
      if ( updated )
        goto LABEL_22;
      a1 = v19;
    }
    v21 = a1;
    if ( a1 )
    {
      ((void (__fastcall *)(struct INetCfg *))a1->lpVtbl->AddRef)(a1);
      a1 = v21;
    }
    v12 = v23;
    if ( v23 )
    {
      updated = 0;
LABEL_14:
      v23 = v12 + 1;
      TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "CRasBindObject::HrFindOtherComponents", updated);
      if ( !updated )
      {
        HrCleanRouterManagerEntries();
        HrCleanRouterInterfacesEntries();
        updated = CSteelhead::HrUpdateRouterConfiguration((CSteelhead *)&v20);
        if ( !--v23 )
        {
          v14 = v22;
          for ( i = 10; i; --i )
          {
            if ( *v14 )
              ((void (__fastcall *)(struct INetCfgComponent *))(*v14)->lpVtbl->Release)(*v14);
            *v14++ = 0;
          }
        }
        RegFlushKey(HKEY_LOCAL_MACHINE);
      }
      goto LABEL_22;
    }
    Components = HrFindComponents(a1, v7, v9, v10, v22);
    updated = Components;
    if ( Components >= 0 )
    {
      v12 = v23;
      goto LABEL_14;
    }
    TracePrintfW(
      g_dwTraceHandle,
      L"%hs failed : hr = %08lx",
      "CRasBindObject::HrFindOtherComponents",
      (unsigned int)Components);
LABEL_22:
    CSteelhead::~CSteelhead((CSteelhead *)&v20);
  }
  catch ( ... )
  {
    updated = -2147467259;
    v2 = v19;
  }
  if ( v2 )
  {
    v16 = ((__int64 (__fastcall *)(struct INetCfg *))v2->lpVtbl->Uninitialize)(v2);
    ((void (__fastcall *)(struct INetCfg *))v2->lpVtbl->Release)(v2);
    v17 = L"%hs succeeded : hr = %08lx";
    if ( v16 < 0 )
      v17 = L"%hs failed : hr = %08lx";
    TracePrintfW(g_dwTraceHandle, v17, "HrUninitializeAndReleaseINetCfg", (unsigned int)v16);
  }
  return updated;
}

```

## disassembly

```asm
0x1800356d0  push    rbx
0x1800356d2  push    rsi
0x1800356d3  push    rdi
0x1800356d4  push    r14
0x1800356d6  sub     rsp, 4D8h
0x1800356dd  mov     rax, cs:__security_cookie
0x1800356e4  xor     rax, rsp
0x1800356e7  mov     [rsp+4F8h+var_38], rax
0x1800356ef  mov     rbx, rcx
0x1800356f2  xor     edi, edi
0x1800356f4  mov     [rsp+4F8h+var_4C0], rdi
0x1800356f9  mov     [rsp+4F8h+var_458], edi
0x180035700  mov     [rsp+4F8h+var_4B0], rdi
0x180035705  lea     rax, ??_7CSteelhead@@6B@; const CSteelhead::`vftable'
0x18003570c  mov     [rsp+4F8h+var_4B8], rax
0x180035711  mov     [rsp+4F8h+var_450], rdi
0x180035719  xor     edx, edx; hFile
0x18003571b  mov     r8d, 800h; dwFlags
0x180035721  lea     rcx, LibFileName; "mprmsg.dll"
0x180035728  call    cs:__imp_LoadLibraryExW
0x18003572e  mov     rsi, rax
0x180035731  test    rax, rax
0x180035734  jz      short loc_180035777
0x180035736  mov     r14d, 100h
0x18003573c  mov     r9d, r14d; cchBufferMax
0x18003573f  lea     r8, [rsp+4F8h+Buffer]; lpBuffer
0x180035747  mov     edx, 4A38h; uID
0x18003574c  mov     rcx, rax; hInstance
0x18003574f  call    cs:__imp_LoadStringW
0x180035755  mov     r9d, r14d; cchBufferMax
0x180035758  lea     r8, [rsp+4F8h+var_248]; lpBuffer
0x180035760  mov     edx, 4A39h; uID
0x180035765  mov     rcx, rsi; hInstance
0x180035768  call    cs:__imp_LoadStringW
0x18003576e  mov     rcx, rsi; hLibModule
0x180035771  call    cs:__imp_FreeLibrary
0x180035777  mov     edx, 21h ; '!'; unsigned int
0x18003577c  call    ?IsTransportAvailable@CSteelhead@@AEAAHK@Z; CSteelhead::IsTransportAvailable(ulong)
0x180035781  mov     [rsp+4F8h+var_48], eax
0x180035788  mov     edx, 57h ; 'W'; unsigned int
0x18003578d  call    ?IsTransportAvailable@CSteelhead@@AEAAHK@Z; CSteelhead::IsTransportAvailable(ulong)
0x180035792  mov     [rsp+4F8h+var_44], eax
0x180035799  test    rbx, rbx
0x18003579c  jnz     short loc_1800357BA
0x18003579e  lea     rdx, [rsp+4F8h+var_4C0]
0x1800357a3  call    HrCreateAndInitializeINetCfg
0x1800357a8  mov     ebx, eax
0x1800357aa  mov     rdi, [rsp+4F8h+var_4C0]
0x1800357af  test    eax, eax
0x1800357b1  jnz     loc_1800358BD
0x1800357b7  mov     rbx, rdi
0x1800357ba  mov     [rsp+4F8h+var_4B0], rbx
0x1800357bf  test    rbx, rbx
0x1800357c2  jz      short loc_1800357D8
0x1800357c4  mov     rax, [rbx]
0x1800357c7  mov     rcx, rbx
0x1800357ca  mov     rax, [rax+8]
0x1800357ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357d3  mov     rbx, [rsp+4F8h+var_4B0]
0x1800357d8  mov     eax, [rsp+4F8h+var_458]
0x1800357df  test    eax, eax
0x1800357e1  jnz     short loc_180035826
0x1800357e3  lea     rax, [rsp+4F8h+var_4A8]
0x1800357e8  mov     [rsp+4F8h+var_4D8], rax; struct INetCfgComponent **
0x1800357ed  mov     rcx, rbx; struct INetCfg *
0x1800357f0  call    ?HrFindComponents@@YAJPEAUINetCfg@@KPEAPEBU_GUID@@PEBQEBGPEAPEAUINetCfgComponent@@@Z; HrFindComponents(INetCfg *,ulong,_GUID const * *,ushort const * const *,INetCfgComponent * *)
0x1800357f5  mov     ebx, eax
0x1800357f7  test    eax, eax
0x1800357f9  js      short loc_180035804
0x1800357fb  mov     eax, [rsp+4F8h+var_458]
0x180035802  jmp     short loc_180035828
0x180035804  mov     r9d, eax
0x180035807  lea     r8, aCrasbindobject; "CRasBindObject::HrFindOtherComponents"
0x18003580e  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180035815  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x18003581b  call    cs:__imp_TracePrintfW
0x180035821  jmp     loc_1800358BD
0x180035826  xor     ebx, ebx
0x180035828  inc     eax
0x18003582a  mov     [rsp+4F8h+var_458], eax
0x180035831  mov     r9d, ebx
0x180035834  lea     r8, aCrasbindobject; "CRasBindObject::HrFindOtherComponents"
0x18003583b  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035842  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035848  call    cs:__imp_TracePrintfW
0x18003584e  test    ebx, ebx
0x180035850  jnz     short loc_1800358BD
0x180035852  call    ?HrCleanRouterManagerEntries@@YAJXZ; HrCleanRouterManagerEntries(void)
0x180035857  call    ?HrCleanRouterInterfacesEntries@@YAJXZ; HrCleanRouterInterfacesEntries(void)
0x18003585c  lea     rcx, [rsp+4F8h+var_4B8]; this
0x180035861  call    ?HrUpdateRouterConfiguration@CSteelhead@@QEAAJXZ; CSteelhead::HrUpdateRouterConfiguration(void)
0x180035866  mov     ebx, eax
0x180035868  mov     eax, [rsp+4F8h+var_458]
0x18003586f  add     eax, 0FFFFFFFFh
0x180035872  mov     [rsp+4F8h+var_458], eax
0x180035879  jnz     short loc_1800358AF
0x18003587b  lea     rsi, [rsp+4F8h+var_4A8]
0x180035880  mov     r14d, 0Ah
0x180035886  test    r14d, r14d
0x180035889  jz      short loc_1800358AF
0x18003588b  mov     rcx, [rsi]
0x18003588e  test    rcx, rcx
0x180035891  jz      short loc_18003589F
0x180035893  mov     rax, [rcx]
0x180035896  mov     rax, [rax+10h]
0x18003589a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003589f  dec     r14d
0x1800358a2  mov     qword ptr [rsi], 0
0x1800358a9  add     rsi, 8
0x1800358ad  jmp     short loc_180035886
0x1800358af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800358b6  call    cs:__imp_RegFlushKey
0x1800358bc  nop
0x1800358bd  lea     rcx, [rsp+4F8h+var_4B8]; this
0x1800358c2  call    ??1CSteelhead@@QEAA@XZ; CSteelhead::~CSteelhead(void)
0x1800358c7  nop
0x1800358c8  jmp     short loc_1800358D3
0x1800358ca  mov     ebx, [rsp+4F8h+var_4C8]
0x1800358ce  mov     rdi, [rsp+4F8h+var_4C0]
0x1800358d3  test    rdi, rdi
0x1800358d6  jz      short loc_180035920
0x1800358d8  mov     rax, [rdi]
0x1800358db  mov     rcx, rdi
0x1800358de  mov     rax, [rax+20h]
0x1800358e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358e7  mov     esi, eax
0x1800358e9  mov     rdx, [rdi]
0x1800358ec  mov     rcx, rdi
0x1800358ef  mov     rax, [rdx+10h]
0x1800358f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358f8  mov     r9d, esi
0x1800358fb  lea     r8, aHruninitialize; "HrUninitializeAndReleaseINetCfg"
0x180035902  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180035908  test    esi, esi
0x18003590a  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180035911  jns     short loc_18003591A
0x180035913  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x18003591a  call    cs:__imp_TracePrintfW
0x180035920  mov     eax, ebx
0x180035922  mov     rcx, [rsp+4F8h+var_38]
0x18003592a  xor     rcx, rsp; StackCookie
0x18003592d  call    __security_check_cookie
0x180035932  add     rsp, 4D8h
0x180035939  pop     r14
0x18003593b  pop     rdi
0x18003593c  pop     rsi
0x18003593d  pop     rbx
0x18003593e  retn
```
