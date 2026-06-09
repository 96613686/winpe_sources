# CflClearTempUserAccount

- ea: `0x1800101c0`
- end: `0x1800102e9`
- name: `CflClearTempUserAccount`
- size: `297`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000c9bc`
- `0x18000d8d8`
- `0x1800101c0`
- `0x18001c500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800101fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800101fc`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010214`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010214`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001021a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001021a`

## string_xrefs

- `0x180010223`: `CflClearTempUserAccountActivity`
- `0x18001026c`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 CflClearTempUserAccount()
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  CflApi *v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  DWORD dwSize[4]; // [rsp+20h] [rbp-388h] BYREF
  _QWORD v7[42]; // [rsp+30h] [rbp-378h] BYREF
  WCHAR ExeName[264]; // [rsp+180h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v7,
    "CflClearTempUserAccountActivity");
  v7[0] = &CflApiTraceProvider::CflClearTempUserAccountActivity::`vftable';
  CflApiTraceProvider::CflClearTempUserAccountActivity::StartActivity(
    (CflApiTraceProvider::CflClearTempUserAccountActivity *)v7,
    ExeName,
    CommandLineW);
  v3 = CflApi::ClearTempUserAccount(v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v7);
    v7[0] = &CflApiTraceProvider::CflClearTempUserAccountActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v7);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v3,
      dwSize[0]);
    v7[0] = &CflApiTraceProvider::CflClearTempUserAccountActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v7);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v7);
    return v4;
  }
}

```

## disassembly

```asm
0x1800101c0  mov     [rsp+arg_0], rbx
0x1800101c5  push    rdi
0x1800101c6  sub     rsp, 3A0h
0x1800101cd  mov     rax, cs:__security_cookie
0x1800101d4  xor     rax, rsp
0x1800101d7  mov     [rsp+3A8h+var_18], rax
0x1800101df  xor     edx, edx; Val
0x1800101e1  mov     r8d, 20Ah; Size
0x1800101e7  lea     rcx, [rsp+3A8h+ExeName]; void *
0x1800101ef  call    memset_0
0x1800101f4  mov     [rsp+3A8h+dwSize], 105h; int
0x1800101fc  call    cs:__imp_GetCurrentProcess
0x180010202  mov     rcx, rax; hProcess
0x180010205  lea     r9, [rsp+3A8h+dwSize]; lpdwSize
0x18001020a  lea     r8, [rsp+3A8h+ExeName]; lpExeName
0x180010212  xor     edx, edx; dwFlags
0x180010214  call    cs:__imp_QueryFullProcessImageNameW
0x18001021a  call    cs:__imp_GetCommandLineW
0x180010220  mov     rbx, rax
0x180010223  lea     rdx, aCflcleartempus_0; "CflClearTempUserAccountActivity"
0x18001022a  lea     rcx, [rsp+3A8h+var_378]
0x18001022f  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010234  lea     rdi, ??_7CflClearTempUserAccountActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflClearTempUserAccountActivity::`vftable'
0x18001023b  mov     [rsp+3A8h+var_378], rdi
0x180010240  mov     r8, rbx; unsigned __int16 *
0x180010243  lea     rdx, [rsp+3A8h+ExeName]; unsigned __int16 *
0x18001024b  lea     rcx, [rsp+3A8h+var_378]; this
0x180010250  call    ?StartActivity@CflClearTempUserAccountActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflClearTempUserAccountActivity::StartActivity(ushort const *,ushort const *)
0x180010255  nop
0x180010256  call    ?ClearTempUserAccount@CflApi@@YAJXZ; CflApi::ClearTempUserAccount(void)
0x18001025b  mov     ebx, eax
0x18001025d  test    eax, eax
0x18001025f  jns     short loc_18001029B
0x180010261  mov     rcx, [rsp+3A8h]; this
0x180010269  mov     r9d, eax; char *
0x18001026c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010273  mov     edx, 33h ; '3'; void *
0x180010278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001027d  nop
0x18001027e  mov     [rsp+3A8h+var_378], rdi
0x180010283  lea     rcx, [rsp+3A8h+var_378]
0x180010288  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001028d  lea     rcx, [rsp+3A8h+var_378]
0x180010292  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010297  mov     eax, ebx
0x180010299  jmp     short loc_1800102C7
0x18001029b  lea     rcx, [rsp+3A8h+var_378]
0x1800102a0  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800102a5  nop
0x1800102a6  mov     [rsp+3A8h+var_378], rdi
0x1800102ab  lea     rcx, [rsp+3A8h+var_378]
0x1800102b0  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800102b5  lea     rcx, [rsp+3A8h+var_378]
0x1800102ba  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800102bf  xor     eax, eax
0x1800102c1  jmp     short loc_1800102C7
0x1800102c3  mov     eax, [rsp+3A8h+dwSize]
0x1800102c7  mov     rcx, [rsp+3A8h+var_18]
0x1800102cf  xor     rcx, rsp; StackCookie
0x1800102d2  call    __security_check_cookie
0x1800102d7  mov     rbx, [rsp+3A8h+arg_0]
0x1800102df  add     rsp, 3A0h
0x1800102e6  pop     rdi
0x1800102e7  retn
```
