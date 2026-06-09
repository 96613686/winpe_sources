# CflSerializeSessionContext

- ea: `0x180011230`
- end: `0x1800113a1`
- name: `CflSerializeSessionContext`
- size: `369`
- prototype: ``
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
- `0x18000cf3c`
- `0x18000d8d8`
- `0x180011230`
- `0x18001fb28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001128e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001128e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800112a6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800112a6`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800112ac`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800112ac`

## string_xrefs

- `0x180011314`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CflSerializeSessionContext(
        CflApi *this,
        struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  unsigned int v6; // r15d
  HANDLE CurrentProcess; // rax
  const unsigned __int16 *CommandLineW; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int v15[2]; // [rsp+20h] [rbp-3C8h]
  unsigned __int16 **dwSize; // [rsp+30h] [rbp-3B8h] BYREF
  _QWORD v17[42]; // [rsp+40h] [rbp-3A8h] BYREF
  WCHAR ExeName[264]; // [rsp+190h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  v6 = (unsigned int)a4;
  memset_0(ExeName, 0, 0x20Au);
  LODWORD(dwSize) = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, (PDWORD)&dwSize);
  CommandLineW = GetCommandLineW();
  wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "CflSerializeSessionContextActivity");
  v17[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
  CflApiTraceProvider::CflSerializeSessionContextActivity::StartActivity(
    (CflApiTraceProvider::CflSerializeSessionContextActivity *)v17,
    ExeName,
    CommandLineW);
  v12 = CflApi::SerializeSessionContext(this, a2, a3, (const unsigned __int8 *)v6, a5, a6, dwSize);
  v13 = v12;
  if ( v12 >= 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
    v17[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
      (const char *)(unsigned int)v12,
      v15[0]);
    v17[0] = &CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable';
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return v13;
  }
}

```

## disassembly

```asm
0x180011230  push    rbx
0x180011232  push    rsi
0x180011233  push    rdi
0x180011234  push    r12
0x180011236  push    r13
0x180011238  push    r14
0x18001123a  push    r15
0x18001123c  sub     rsp, 3B0h
0x180011243  mov     rax, cs:__security_cookie
0x18001124a  xor     rax, rsp
0x18001124d  mov     [rsp+3E8h+var_48], rax
0x180011255  mov     r15d, r9d
0x180011258  mov     r14, r8
0x18001125b  mov     rsi, rdx
0x18001125e  mov     rdi, rcx
0x180011261  mov     r12, qword ptr [rsp+3E8h+arg_20]
0x180011269  mov     r13, [rsp+3E8h+arg_28]
0x180011271  xor     edx, edx; Val
0x180011273  mov     r8d, 20Ah; Size
0x180011279  lea     rcx, [rsp+3E8h+ExeName]; void *
0x180011281  call    memset_0
0x180011286  mov     dword ptr [rsp+3E8h+dwSize], 105h; unsigned __int16 **
0x18001128e  call    cs:__imp_GetCurrentProcess
0x180011294  mov     rcx, rax; hProcess
0x180011297  lea     r9, [rsp+3E8h+dwSize]; lpdwSize
0x18001129c  lea     r8, [rsp+3E8h+ExeName]; lpExeName
0x1800112a4  xor     edx, edx; dwFlags
0x1800112a6  call    cs:__imp_QueryFullProcessImageNameW
0x1800112ac  call    cs:__imp_GetCommandLineW
0x1800112b2  mov     rbx, rax
0x1800112b5  lea     rdx, aCflserializese_1; "CflSerializeSessionContextActivity"
0x1800112bc  lea     rcx, [rsp+3E8h+var_3A8]
0x1800112c1  call    ??0?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800112c6  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x1800112cd  mov     [rsp+3E8h+var_3A8], rax
0x1800112d2  mov     r8, rbx; unsigned __int16 *
0x1800112d5  lea     rdx, [rsp+3E8h+ExeName]; unsigned __int16 *
0x1800112dd  lea     rcx, [rsp+3E8h+var_3A8]; this
0x1800112e2  call    ?StartActivity@CflSerializeSessionContextActivity@CflApiTraceProvider@@QEAAXPEBG0@Z; CflApiTraceProvider::CflSerializeSessionContextActivity::StartActivity(ushort const *,ushort const *)
0x1800112e7  nop
0x1800112e8  mov     [rsp+3E8h+var_3C0], r13; unsigned __int16 *
0x1800112ed  mov     qword ptr [rsp+3E8h+var_3C8], r12; int
0x1800112f2  mov     r9d, r15d; unsigned __int8 *
0x1800112f5  mov     r8, r14; unsigned __int16 *
0x1800112f8  mov     rdx, rsi; struct _GUID *
0x1800112fb  mov     rcx, rdi; this
0x1800112fe  call    ?SerializeSessionContext@CflApi@@YAJPEBU_GUID@@PEBGPEBEK1PEAPEAG@Z; CflApi::SerializeSessionContext(_GUID const *,ushort const *,uchar const *,ulong,ushort const *,ushort * *)
0x180011303  mov     ebx, eax
0x180011305  test    eax, eax
0x180011307  jns     short loc_18001134A
0x180011309  mov     rcx, [rsp+3E8h]; this
0x180011311  mov     r9d, eax; char *
0x180011314  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x18001131b  mov     edx, 142h; void *
0x180011320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011325  nop
0x180011326  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x18001132d  mov     [rsp+3E8h+var_3A8], rax
0x180011332  lea     rcx, [rsp+3E8h+var_3A8]
0x180011337  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001133c  lea     rcx, [rsp+3E8h+var_3A8]
0x180011341  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011346  mov     eax, ebx
0x180011348  jmp     short loc_18001137D
0x18001134a  lea     rcx, [rsp+3E8h+var_3A8]
0x18001134f  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011354  nop
0x180011355  lea     rax, ??_7CflSerializeSessionContextActivity@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSerializeSessionContextActivity::`vftable'
0x18001135c  mov     [rsp+3E8h+var_3A8], rax
0x180011361  lea     rcx, [rsp+3E8h+var_3A8]
0x180011366  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001136b  lea     rcx, [rsp+3E8h+var_3A8]
0x180011370  call    ??1?$ActivityBase@VCflApiTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011375  xor     eax, eax
0x180011377  jmp     short loc_18001137D
0x180011379  mov     eax, dword ptr [rsp+3E8h+dwSize]
0x18001137d  mov     rcx, [rsp+3E8h+var_48]
0x180011385  xor     rcx, rsp; StackCookie
0x180011388  call    __security_check_cookie
0x18001138d  add     rsp, 3B0h
0x180011394  pop     r15
0x180011396  pop     r14
0x180011398  pop     r13
0x18001139a  pop     r12
0x18001139c  pop     rdi
0x18001139d  pop     rsi
0x18001139e  pop     rbx
0x18001139f  retn
```
