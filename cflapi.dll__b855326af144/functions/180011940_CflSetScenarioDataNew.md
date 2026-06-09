# CflSetScenarioDataNew

- ea: `0x180011940`
- end: `0x180011b08`
- name: `CflSetScenarioDataNew`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002490`
- `0x180002ef8`
- `0x1800067c4`
- `0x1800081e8`
- `0x1800087f0`
- `0x1800099c4`
- `0x18000d78c`
- `0x180011940`
- `0x18002ba10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011989`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011989`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800119a1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800119a1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800119a7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800119a7`

## string_xrefs

- `0x180011ab3`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x180011a99`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CflSetScenarioDataNew(IID *a1, const BYTE *a2, BYTE *a3, DWORD a4)
{
  HANDLE CurrentProcess; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int lpData; // [rsp+20h] [rbp-3C8h]
  int lpDataa; // [rsp+20h] [rbp-3C8h]
  DWORD dwSize; // [rsp+40h] [rbp-3A8h] BYREF
  IID *rclsid; // [rsp+48h] [rbp-3A0h]
  const BYTE *v14; // [rsp+50h] [rbp-398h]
  __int64 CommandLineW; // [rsp+58h] [rbp-390h] BYREF
  _QWORD v16[42]; // [rsp+60h] [rbp-388h] BYREF
  WCHAR ExeName[264]; // [rsp+1B0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+0h]

  rclsid = a1;
  v14 = a2;
  memset_0(ExeName, 0, 0x20Au);
  dwSize = 261;
  CurrentProcess = GetCurrentProcess();
  QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize);
  CommandLineW = (__int64)GetCommandLineW();
  CflApiTraceProvider::CflSetScenarioDataMeasure::Start<_GUID const * &,unsigned short const * &,unsigned short (&)[261],unsigned short *>(
    (CflApiTraceProvider::CflSetScenarioDataMeasure *)v16,
    (__int64)&CommandLineW);
  if ( !rclsid || !v14 )
  {
    v7 = -2147467261;
    v8 = 164;
    goto LABEL_14;
  }
  if ( !*(_QWORD *)&rclsid->Data1 && *(_QWORD *)rclsid->Data4 == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    goto LABEL_12;
  if ( a3 )
  {
    if ( a4 )
      goto LABEL_9;
LABEL_12:
    v7 = -2147024809;
    v8 = 170;
    goto LABEL_14;
  }
  if ( a4 )
    goto LABEL_12;
LABEL_9:
  v7 = CflApiNew::SetAllScenarioData(rclsid, 0, 0, v14, a3, a4);
  if ( (v7 & 0x80000000) == 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
    v16[0] = &CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable';
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return 0;
  }
  v8 = 180;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
    (const char *)v7,
    lpData);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAE,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\dll\\entrypoints.cpp",
    (const char *)v7,
    lpDataa);
  v16[0] = &CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable';
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
  wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
  return v7;
}

```

## disassembly

```asm
0x180011940  push    rbx
0x180011942  push    rdi
0x180011943  sub     rsp, 3D8h
0x18001194a  mov     rax, cs:__security_cookie
0x180011951  xor     rax, rsp
0x180011954  mov     [rsp+3E8h+var_28], rax
0x18001195c  mov     ebx, r9d
0x18001195f  mov     rdi, r8
0x180011962  mov     [rsp+3E8h+rclsid], rcx
0x180011967  mov     [rsp+3E8h+var_398], rdx
0x18001196c  xor     edx, edx; Val
0x18001196e  mov     r8d, 20Ah; Size
0x180011974  lea     rcx, [rsp+3E8h+ExeName]; void *
0x18001197c  call    memset_0
0x180011981  mov     [rsp+3E8h+dwSize], 105h
0x180011989  call    cs:__imp_GetCurrentProcess
0x18001198f  mov     rcx, rax; hProcess
0x180011992  lea     r9, [rsp+3E8h+dwSize]; lpdwSize
0x180011997  lea     r8, [rsp+3E8h+ExeName]; lpExeName
0x18001199f  xor     edx, edx; dwFlags
0x1800119a1  call    cs:__imp_QueryFullProcessImageNameW
0x1800119a7  call    cs:__imp_GetCommandLineW
0x1800119ad  mov     [rsp+3E8h+var_390], rax
0x1800119b2  lea     rax, [rsp+3E8h+var_390]
0x1800119b7  mov     [rsp+3E8h+lpData], rax; int
0x1800119bc  lea     r9, [rsp+3E8h+ExeName]
0x1800119c4  lea     r8, [rsp+3E8h+var_398]
0x1800119c9  lea     rdx, [rsp+3E8h+rclsid]
0x1800119ce  lea     rcx, [rsp+3E8h+var_388]; this
0x1800119d3  call    ??$Start@AEAPEBU_GUID@@AEAPEBGAEAY0BAF@GPEAG@CflSetScenarioDataMeasure@CflApiTraceProvider@@SA?AV01@AEAPEBU_GUID@@AEAPEBGAEAY0BAF@G$$QEAPEAG@Z; CflApiTraceProvider::CflSetScenarioDataMeasure::Start<_GUID const * &,ushort const * &,ushort (&)[261],ushort *>(_GUID const * &,ushort const * &,ushort (&)[261],ushort * &&)
0x1800119d8  nop
0x1800119d9  mov     rcx, [rsp+3E8h+rclsid]; rclsid
0x1800119de  test    rcx, rcx
0x1800119e1  jz      loc_180011A87
0x1800119e7  mov     r9, [rsp+3E8h+var_398]
0x1800119ec  test    r9, r9
0x1800119ef  jz      loc_180011A87
0x1800119f5  xorps   xmm0, xmm0
0x1800119f8  movq    rax, xmm0
0x1800119fd  cmp     [rcx], rax
0x180011a00  jnz     short loc_180011A12
0x180011a02  psrldq  xmm0, 8
0x180011a07  movq    rax, xmm0
0x180011a0c  cmp     [rcx+8], rax
0x180011a10  jz      short loc_180011A7B
0x180011a12  test    rdi, rdi
0x180011a15  jz      short loc_180011A1D
0x180011a17  test    ebx, ebx
0x180011a19  jz      short loc_180011A7B
0x180011a1b  jmp     short loc_180011A21
0x180011a1d  test    ebx, ebx
0x180011a1f  jnz     short loc_180011A7B
0x180011a21  mov     eax, dword ptr [rsp+3E8h+arg_20]
0x180011a28  mov     dword ptr [rsp+3E8h+Data], eax; Data
0x180011a2c  mov     [rsp+3E8h+cbData], ebx; cbData
0x180011a30  mov     [rsp+3E8h+lpData], rdi; lpData
0x180011a35  xor     r8d, r8d
0x180011a38  xor     edx, edx
0x180011a3a  call    CflApiNew__SetAllScenarioData
0x180011a3f  mov     ebx, eax
0x180011a41  test    eax, eax
0x180011a43  jns     short loc_180011A4C
0x180011a45  mov     edx, 0B4h
0x180011a4a  jmp     short loc_180011A91
0x180011a4c  lea     rcx, [rsp+3E8h+var_388]
0x180011a51  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180011a56  nop
0x180011a57  lea     rax, ??_7CflSetScenarioDataMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable'
0x180011a5e  mov     [rsp+3E8h+var_388], rax
0x180011a63  lea     rcx, [rsp+3E8h+var_388]
0x180011a68  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011a6d  lea     rcx, [rsp+3E8h+var_388]
0x180011a72  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011a77  xor     eax, eax
0x180011a79  jmp     short loc_180011AED
0x180011a7b  mov     ebx, 80070057h
0x180011a80  mov     edx, 0AAh
0x180011a85  jmp     short loc_180011A91
0x180011a87  mov     ebx, 80004003h
0x180011a8c  mov     edx, 0A4h; void *
0x180011a91  mov     rcx, [rsp+3E8h]; this
0x180011a99  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180011aa0  mov     r9d, ebx; char *
0x180011aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011aa8  mov     rcx, [rsp+3E8h]; this
0x180011ab0  mov     r9d, ebx; char *
0x180011ab3  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x180011aba  mov     edx, 0AEh; void *
0x180011abf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ac4  nop
0x180011ac5  lea     rax, ??_7CflSetScenarioDataMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable'
0x180011acc  mov     [rsp+3E8h+var_388], rax
0x180011ad1  lea     rcx, [rsp+3E8h+var_388]
0x180011ad6  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011adb  lea     rcx, [rsp+3E8h+var_388]
0x180011ae0  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180011ae5  mov     eax, ebx
0x180011ae7  jmp     short loc_180011AED
0x180011ae9  mov     eax, [rsp+3E8h+dwSize]
0x180011aed  mov     rcx, [rsp+3E8h+var_28]
0x180011af5  xor     rcx, rsp; StackCookie
0x180011af8  call    __security_check_cookie
0x180011afd  add     rsp, 3D8h
0x180011b04  pop     rdi
0x180011b05  pop     rbx
0x180011b06  retn
```
