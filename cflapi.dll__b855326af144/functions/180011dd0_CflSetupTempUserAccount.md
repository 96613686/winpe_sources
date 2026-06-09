# CflSetupTempUserAccount

- ea: `0x180011dd0`
- end: `0x180011f0b`
- name: `CflSetupTempUserAccount`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000d47c`
- `0x18000d8d8`
- `0x180011dd0`
- `0x180020a54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e15`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011e2d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180011e2d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011e33`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180011e33`

## string_xrefs

- `0x180011e3c`: `CflSetupTempUserAccountActivity`
- `0x180011e8b`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflSetupTempUserAccount(CflApi *this, unsigned __int8 **a2)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  unsigned int *v6; // r8
  int v7; // eax
  unsigned int v8; // ebx
  DWORD dwSize[4]; // [rsp+20h] [rbp-398h] BYREF
  _QWORD v11[42]; // [rsp+30h] [rbp-388h] BYREF
  WCHAR ExeName[264]; // [rsp+180h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3B8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v11,
    "CflSetupTempUserAccountActivity");
  v11[0] = &CflApiTraceProvider::CflSetupTempUserAccountActivity::`vftable';
  CflApiTraceProvider::CflSetupTempUserAccountActivity::StartActivity(
    (CflApiTraceProvider::CflSetupTempUserAccountActivity *)v11,
    ExeName,
    CommandLineW);
  v7 = CflApi::SetupTempUserAccount(this, a2, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v11);
    v11[0] = &CflApiTraceProvider::CflSetupTempUserAccountActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v11);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v7,
      dwSize[0]);
    v11[0] = &CflApiTraceProvider::CflSetupTempUserAccountActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v11);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v11);
    return v8;
  }
}

```

## disassembly

```asm
0x180011dd0  mov     [rsp+arg_10], rbx
0x180011dd5  push    rsi
0x180011dd6  push    rdi
0x180011dd7  push    r14
0x180011dd9  sub     rsp, 3A0h
0x180011de0  mov     rax, cs:__security_cookie
0x180011de7  xor     rax, rsp
0x180011dea  mov     [rsp+3B8h+var_28], rax
0x180011df2  mov     rsi, rdx
0x180011df5  mov     rdi, rcx
0x180011df8  xor     edx, edx; Val
0x180011dfa  mov     r8d, 20Ah; Size
0x180011e00  lea     rcx, [rsp+3B8h+ExeName]; void *
0x180011e08  call    memset_0
0x180011e0d  mov     [rsp+3B8h+dwSize], 105h; int
0x180011e15  call    cs:__imp_GetCurrentProcess
0x180011e1b  mov     rcx, rax; hProcess
0x180011e1e  lea     r9, [rsp+3B8h+dwSize]; lpdwSize
0x180011e23  lea     r8, [rsp+3B8h+ExeName]; lpExeName
0x180011e2b  xor     edx, edx; dwFlags
0x180011e2d  call    cs:__imp_QueryFullProcessImageNameW
0x180011e33  call    cs:__imp_GetCommandLineW
0x180011e39  mov     rbx, rax
0x180011e3c  lea     rdx, aCflsetuptempus_0; "CflSetupTempUserAccountActivity"
0x180011e43  lea     rcx, [rsp+3B8h+var_388]
0x180011e48  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011e4d  lea     r14, ??_7CflSetupTempUserAccountActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetupTempUserAccountActivity::`vftable'
0x180011e54  mov     [rsp+3B8h+var_388], r14
0x180011e59  mov     r8, rbx; unsigned __int16 *
0x180011e5c  lea     rdx, [rsp+3B8h+ExeName]; unsigned __int16 *
0x180011e64  lea     rcx, [rsp+3B8h+var_388]; this
0x180011e69  call    ?StartActivity@CflSetupTempUserAccountActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflSetupTempUserAccountActivity::StartActivity(ushort const *,ushort const *)
0x180011e6e  nop
0x180011e6f  mov     rdx, rsi; unsigned __int8 **
0x180011e72  mov     rcx, rdi; this
0x180011e75  call    ?SetupTempUserAccount@CflApi@@YAJPEAPEAEPEAK@Z; CflApi::SetupTempUserAccount(uchar * *,ulong *)
0x180011e7a  mov     ebx, eax
0x180011e7c  test    eax, eax
0x180011e7e  jns     short loc_180011EBA
0x180011e80  mov     rcx, [rsp+3B8h]; this
0x180011e88  mov     r9d, eax; char *
0x180011e8b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180011e92  mov     edx, 21h ; '!'; void *
0x180011e97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e9c  nop
0x180011e9d  mov     [rsp+3B8h+var_388], r14
0x180011ea2  lea     rcx, [rsp+3B8h+var_388]
0x180011ea7  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011eac  lea     rcx, [rsp+3B8h+var_388]
0x180011eb1  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011eb6  mov     eax, ebx
0x180011eb8  jmp     short loc_180011EE6
0x180011eba  lea     rcx, [rsp+3B8h+var_388]
0x180011ebf  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011ec4  nop
0x180011ec5  mov     [rsp+3B8h+var_388], r14
0x180011eca  lea     rcx, [rsp+3B8h+var_388]
0x180011ecf  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011ed4  lea     rcx, [rsp+3B8h+var_388]
0x180011ed9  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011ede  xor     eax, eax
0x180011ee0  jmp     short loc_180011EE6
0x180011ee2  mov     eax, [rsp+3B8h+dwSize]
0x180011ee6  mov     rcx, [rsp+3B8h+var_28]
0x180011eee  xor     rcx, rsp; StackCookie
0x180011ef1  call    __security_check_cookie
0x180011ef6  mov     rbx, [rsp+3B8h+arg_10]
0x180011efe  add     rsp, 3A0h
0x180011f05  pop     r14
0x180011f07  pop     rdi
0x180011f08  pop     rsi
0x180011f09  retn
```
