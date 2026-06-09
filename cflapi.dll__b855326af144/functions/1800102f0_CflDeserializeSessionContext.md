# CflDeserializeSessionContext

- ea: `0x1800102f0`
- end: `0x180010461`
- name: `CflDeserializeSessionContext`
- size: `369`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800084d4`
- `0x180008868`
- `0x180009adc`
- `0x18000cb1c`
- `0x18000d8d8`
- `0x1800102f0`
- `0x18001cb44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001034e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001034e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010366`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010366`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001036c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18001036c`

## string_xrefs

- `0x180010375`: `CflDeserializeSessionContextActivity`
- `0x1800103d4`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflDeserializeSessionContext(
        CflApi *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  unsigned __int8 **v15; // [rsp+20h] [rbp-3C8h]
  DWORD dwSize[4]; // [rsp+30h] [rbp-3B8h] BYREF
  _QWORD v17[42]; // [rsp+40h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+190h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  memset_0(ExeName, 0, 0x20Au);
  dwSize[0] = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "CflDeserializeSessionContextActivity");
  v17[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
  CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(
    (CflApiTraceProvider::CflDeserializeSessionContextActivity *)v17,
    ExeName,
    CommandLineW);
  v12 = CflApi::DeserializeSessionContext(this, a2, a3, a4, a5, a6);
  v13 = v12;
  if ( v12 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    v17[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v12,
      (int)v15);
    v17[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return v13;
  }
}

```

## disassembly

```asm
0x1800102f0  push    rbx
0x1800102f2  push    rsi
0x1800102f3  push    rdi
0x1800102f4  push    r12
0x1800102f6  push    r13
0x1800102f8  push    r14
0x1800102fa  push    r15
0x1800102fc  sub     rsp, 3B0h
0x180010303  mov     rax, cs:__security_cookie
0x18001030a  xor     rax, rsp
0x18001030d  mov     [rsp+3E8h+var_48], rax
0x180010315  mov     r15, r9
0x180010318  mov     r14, r8
0x18001031b  mov     rsi, rdx
0x18001031e  mov     rdi, rcx
0x180010321  mov     r12, [rsp+3E8h+arg_20]
0x180010329  mov     r13, [rsp+3E8h+arg_28]
0x180010331  xor     edx, edx; Val
0x180010333  mov     r8d, 20Ah; Size
0x180010339  lea     rcx, [rsp+3E8h+ExeName]; void *
0x180010341  call    memset_0
0x180010346  mov     [rsp+3E8h+dwSize], 105h; unsigned __int16 **
0x18001034e  call    cs:__imp_GetCurrentProcess
0x180010354  mov     rcx, rax; hProcess
0x180010357  lea     r9, [rsp+3E8h+dwSize]; lpdwSize
0x18001035c  lea     r8, [rsp+3E8h+ExeName]; lpExeName
0x180010364  xor     edx, edx; dwFlags
0x180010366  call    cs:__imp_QueryFullProcessImageNameW
0x18001036c  call    cs:__imp_GetCommandLineW
0x180010372  mov     rbx, rax
0x180010375  lea     rdx, aCfldeserialize_1; "CflDeserializeSessionContextActivity"
0x18001037c  lea     rcx, [rsp+3E8h+var_3A8]
0x180010381  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010386  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x18001038d  mov     [rsp+3E8h+var_3A8], rax
0x180010392  mov     r8, rbx; unsigned __int16 *
0x180010395  lea     rdx, [rsp+3E8h+ExeName]; unsigned __int16 *
0x18001039d  lea     rcx, [rsp+3E8h+var_3A8]; this
0x1800103a2  call    ?StartActivity@CflDeserializeSessionContextActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(ushort const *,ushort const *)
0x1800103a7  nop
0x1800103a8  mov     [rsp+3E8h+var_3C0], r13; unsigned int *
0x1800103ad  mov     [rsp+3E8h+var_3C8], r12; int
0x1800103b2  mov     r9, r15; unsigned __int16 **
0x1800103b5  mov     r8, r14; unsigned __int16 *
0x1800103b8  mov     rdx, rsi; struct _GUID *
0x1800103bb  mov     rcx, rdi; this
0x1800103be  call    ?DeserializeSessionContext@CflApi@@YAJPEBU_GUID@@PEBGPEAPEAGPEAPEAEPEAK2@Z; CflApi::DeserializeSessionContext(_GUID const *,ushort const *,ushort * *,uchar * *,ulong *,ushort * *)
0x1800103c3  mov     ebx, eax
0x1800103c5  test    eax, eax
0x1800103c7  jns     short loc_18001040A
0x1800103c9  mov     rcx, [rsp+3E8h]; this
0x1800103d1  mov     r9d, eax; char *
0x1800103d4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x1800103db  mov     edx, 176h; void *
0x1800103e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103e5  nop
0x1800103e6  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x1800103ed  mov     [rsp+3E8h+var_3A8], rax
0x1800103f2  lea     rcx, [rsp+3E8h+var_3A8]
0x1800103f7  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800103fc  lea     rcx, [rsp+3E8h+var_3A8]
0x180010401  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010406  mov     eax, ebx
0x180010408  jmp     short loc_18001043D
0x18001040a  lea     rcx, [rsp+3E8h+var_3A8]
0x18001040f  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180010414  nop
0x180010415  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x18001041c  mov     [rsp+3E8h+var_3A8], rax
0x180010421  lea     rcx, [rsp+3E8h+var_3A8]
0x180010426  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001042b  lea     rcx, [rsp+3E8h+var_3A8]
0x180010430  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180010435  xor     eax, eax
0x180010437  jmp     short loc_18001043D
0x180010439  mov     eax, [rsp+3E8h+dwSize]
0x18001043d  mov     rcx, [rsp+3E8h+var_48]
0x180010445  xor     rcx, rsp; StackCookie
0x180010448  call    __security_check_cookie
0x18001044d  add     rsp, 3B0h
0x180010454  pop     r15
0x180010456  pop     r14
0x180010458  pop     r13
0x18001045a  pop     r12
0x18001045c  pop     rdi
0x18001045d  pop     rsi
0x18001045e  pop     rbx
0x18001045f  retn
```
