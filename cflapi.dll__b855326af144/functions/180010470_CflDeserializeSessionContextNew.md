# CflDeserializeSessionContextNew

- ea: `0x180010470`
- end: `0x1800105f8`
- name: `CflDeserializeSessionContextNew`
- size: `392`
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
- `0x180010470`
- `0x180028cc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800104db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800104db`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800104f3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800104f3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800104f9`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800104f9`

## string_xrefs

- `0x180010502`: `CflDeserializeSessionContextActivity`
- `0x18001056b`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflDeserializeSessionContextNew(
        CflApiNew *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int16 **a7)
{
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned __int8 **v16; // [rsp+20h] [rbp-3D8h]
  DWORD dwSize; // [rsp+40h] [rbp-3B8h] BYREF
  unsigned __int16 **v18; // [rsp+48h] [rbp-3B0h]
  _QWORD v19[42]; // [rsp+50h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v18 = a7;
  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "CflDeserializeSessionContextActivity");
  v19[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
  CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(
    (CflApiTraceProvider::CflDeserializeSessionContextActivity *)v19,
    ExeName,
    CommandLineW);
  v13 = CflApiNew::DeserializeSessionContext(this, a2, a3, a4, a5, a6, v18);
  v14 = v13;
  if ( v13 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
    v19[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v19);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v13,
      (int)v16);
    v19[0] = &CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v19);
    return v14;
  }
}

```

## disassembly

```asm
0x180010470  push    rbx
0x180010472  push    rsi
0x180010473  push    rdi
0x180010474  push    r12
0x180010476  push    r13
0x180010478  push    r14
0x18001047a  push    r15
0x18001047c  sub     rsp, 3C0h
0x180010483  mov     rax, cs:__security_cookie
0x18001048a  xor     rax, rsp
0x18001048d  mov     [rsp+3F8h+var_48], rax
0x180010495  mov     r15, r9
0x180010498  mov     r14, r8
0x18001049b  mov     rsi, rdx
0x18001049e  mov     rdi, rcx
0x1800104a1  mov     r12, [rsp+3F8h+arg_20]
0x1800104a9  mov     r13, [rsp+3F8h+arg_28]
0x1800104b1  mov     rax, [rsp+3F8h+arg_30]
0x1800104b9  mov     [rsp+3F8h+var_3B0], rax
0x1800104be  xor     edx, edx; Val
0x1800104c0  mov     r8d, 20Ah; Size
0x1800104c6  lea     rcx, [rsp+3F8h+ExeName]; void *
0x1800104ce  call    memset_0
0x1800104d3  mov     [rsp+3F8h+dwSize], 105h
0x1800104db  call    cs:__imp_GetCurrentProcess
0x1800104e1  mov     rcx, rax; hProcess
0x1800104e4  lea     r9, [rsp+3F8h+dwSize]; lpdwSize
0x1800104e9  lea     r8, [rsp+3F8h+ExeName]; lpExeName
0x1800104f1  xor     edx, edx; dwFlags
0x1800104f3  call    cs:__imp_QueryFullProcessImageNameW
0x1800104f9  call    cs:__imp_GetCommandLineW
0x1800104ff  mov     rbx, rax
0x180010502  lea     rdx, aCfldeserialize_1; "CflDeserializeSessionContextActivity"
0x180010509  lea     rcx, [rsp+3F8h+var_3A8]
0x18001050e  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180010513  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x18001051a  mov     [rsp+3F8h+var_3A8], rax
0x18001051f  mov     r8, rbx; unsigned __int16 *
0x180010522  lea     rdx, [rsp+3F8h+ExeName]; unsigned __int16 *
0x18001052a  lea     rcx, [rsp+3F8h+var_3A8]; this
0x18001052f  call    ?StartActivity@CflDeserializeSessionContextActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflDeserializeSessionContextActivity::StartActivity(ushort const *,ushort const *)
0x180010534  nop
0x180010535  mov     rax, [rsp+3F8h+var_3B0]
0x18001053a  mov     [rsp+3F8h+var_3C8], rax; unsigned __int16 **
0x18001053f  mov     [rsp+3F8h+var_3D0], r13; unsigned int *
0x180010544  mov     [rsp+3F8h+var_3D8], r12; int
0x180010549  mov     r9, r15; unsigned __int16 **
0x18001054c  mov     r8, r14; unsigned __int16 *
0x18001054f  mov     rdx, rsi; struct _GUID *
0x180010552  mov     rcx, rdi; this
0x180010555  call    ?DeserializeSessionContext@CflApiNew@@YAJPEBU_GUID@@PEBGPEAPEAGPEAPEAEPEAK24@Z; CflApiNew::DeserializeSessionContext(_GUID const *,ushort const *,ushort * *,uchar * *,ulong *,ushort * *,ulong *)
0x18001055a  mov     ebx, eax
0x18001055c  test    eax, eax
0x18001055e  jns     short loc_1800105A1
0x180010560  mov     rcx, [rsp+3F8h]; this
0x180010568  mov     r9d, eax; char *
0x18001056b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180010572  mov     edx, 191h; void *
0x180010577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001057c  nop
0x18001057d  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x180010584  mov     [rsp+3F8h+var_3A8], rax
0x180010589  lea     rcx, [rsp+3F8h+var_3A8]
0x18001058e  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010593  lea     rcx, [rsp+3F8h+var_3A8]
0x180010598  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001059d  mov     eax, ebx
0x18001059f  jmp     short loc_1800105D4
0x1800105a1  lea     rcx, [rsp+3F8h+var_3A8]
0x1800105a6  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800105ab  nop
0x1800105ac  lea     rax, ??_7CflDeserializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflDeserializeSessionContextActivity::`vftable'
0x1800105b3  mov     [rsp+3F8h+var_3A8], rax
0x1800105b8  lea     rcx, [rsp+3F8h+var_3A8]
0x1800105bd  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800105c2  lea     rcx, [rsp+3F8h+var_3A8]
0x1800105c7  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800105cc  xor     eax, eax
0x1800105ce  jmp     short loc_1800105D4
0x1800105d0  mov     eax, [rsp+3F8h+dwSize]
0x1800105d4  mov     rcx, [rsp+3F8h+var_48]
0x1800105dc  xor     rcx, rsp; StackCookie
0x1800105df  call    __security_check_cookie
0x1800105e4  add     rsp, 3C0h
0x1800105eb  pop     r15
0x1800105ed  pop     r14
0x1800105ef  pop     r13
0x1800105f1  pop     r12
0x1800105f3  pop     rdi
0x1800105f4  pop     rsi
0x1800105f5  pop     rbx
0x1800105f6  retn
```
