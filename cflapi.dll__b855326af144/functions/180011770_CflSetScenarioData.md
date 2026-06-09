# CflSetScenarioData

- ea: `0x180011770`
- end: `0x18001192d`
- name: `CflSetScenarioData`
- size: `445`
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
- `0x180011770`
- `0x180020378`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800117b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800117b9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800117d1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800117d1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800117d7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800117d7`

## string_xrefs

- `0x1800118d8`: `onecore\ds\security\cfl\api\dll\entrypoints.cpp`
- `0x1800118be`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CflSetScenarioData(IID *a1, const BYTE *a2, BYTE *a3, DWORD a4)
{
  HANDLE CurrentProcess; // rax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int lpData; // [rsp+20h] [rbp-3B8h]
  int lpDataa; // [rsp+20h] [rbp-3B8h]
  DWORD dwSize; // [rsp+30h] [rbp-3A8h] BYREF
  IID *rclsid; // [rsp+38h] [rbp-3A0h]
  const BYTE *v14; // [rsp+40h] [rbp-398h]
  __int64 CommandLineW; // [rsp+48h] [rbp-390h] BYREF
  _QWORD v16[42]; // [rsp+50h] [rbp-388h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+0h]

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
    v8 = 459;
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
    v8 = 465;
    goto LABEL_14;
  }
  if ( a4 )
    goto LABEL_12;
LABEL_9:
  v7 = CflApi::SetAllScenarioData(rclsid, 0, 0, v14, a3, a4);
  if ( (v7 & 0x80000000) == 0 )
  {
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v16);
    v16[0] = &CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable';
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v16);
    wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v16);
    return 0;
  }
  v8 = 474;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)v7,
    lpData);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F,
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
0x180011770  push    rbx
0x180011772  push    rdi
0x180011773  sub     rsp, 3C8h
0x18001177a  mov     rax, cs:__security_cookie
0x180011781  xor     rax, rsp
0x180011784  mov     [rsp+3D8h+var_28], rax
0x18001178c  mov     ebx, r9d
0x18001178f  mov     rdi, r8
0x180011792  mov     [rsp+3D8h+rclsid], rcx
0x180011797  mov     [rsp+3D8h+var_398], rdx
0x18001179c  xor     edx, edx; Val
0x18001179e  mov     r8d, 20Ah; Size
0x1800117a4  lea     rcx, [rsp+3D8h+ExeName]; void *
0x1800117ac  call    memset_0
0x1800117b1  mov     [rsp+3D8h+dwSize], 105h
0x1800117b9  call    cs:__imp_GetCurrentProcess
0x1800117bf  mov     rcx, rax; hProcess
0x1800117c2  lea     r9, [rsp+3D8h+dwSize]; lpdwSize
0x1800117c7  lea     r8, [rsp+3D8h+ExeName]; lpExeName
0x1800117cf  xor     edx, edx; dwFlags
0x1800117d1  call    cs:__imp_QueryFullProcessImageNameW
0x1800117d7  call    cs:__imp_GetCommandLineW
0x1800117dd  mov     [rsp+3D8h+var_390], rax
0x1800117e2  lea     rax, [rsp+3D8h+var_390]
0x1800117e7  mov     [rsp+3D8h+lpData], rax; int
0x1800117ec  lea     r9, [rsp+3D8h+ExeName]
0x1800117f4  lea     r8, [rsp+3D8h+var_398]
0x1800117f9  lea     rdx, [rsp+3D8h+rclsid]
0x1800117fe  lea     rcx, [rsp+3D8h+var_388]; this
0x180011803  call    ??$Start@AEAPEBU_GUID@@AEAPEBGAEAY0BAF@GPEAG@CflSetScenarioDataMeasure@CflApiTraceProvider@@SA?AV01@AEAPEBU_GUID@@AEAPEBGAEAY0BAF@G$$QEAPEAG@Z; CflApiTraceProvider::CflSetScenarioDataMeasure::Start<_GUID const * &,ushort const * &,ushort (&)[261],ushort *>(_GUID const * &,ushort const * &,ushort (&)[261],ushort * &&)
0x180011808  nop
0x180011809  mov     rcx, [rsp+3D8h+rclsid]; rclsid
0x18001180e  test    rcx, rcx
0x180011811  jz      loc_1800118AC
0x180011817  mov     r9, [rsp+3D8h+var_398]
0x18001181c  test    r9, r9
0x18001181f  jz      loc_1800118AC
0x180011825  xorps   xmm0, xmm0
0x180011828  movq    rax, xmm0
0x18001182d  cmp     [rcx], rax
0x180011830  jnz     short loc_180011842
0x180011832  psrldq  xmm0, 8
0x180011837  movq    rax, xmm0
0x18001183c  cmp     [rcx+8], rax
0x180011840  jz      short loc_1800118A0
0x180011842  test    rdi, rdi
0x180011845  jz      short loc_18001184D
0x180011847  test    ebx, ebx
0x180011849  jz      short loc_1800118A0
0x18001184b  jmp     short loc_180011851
0x18001184d  test    ebx, ebx
0x18001184f  jnz     short loc_1800118A0
0x180011851  mov     [rsp+3D8h+cbData], ebx; cbData
0x180011855  mov     [rsp+3D8h+lpData], rdi; lpData
0x18001185a  xor     r8d, r8d
0x18001185d  xor     edx, edx
0x18001185f  call    CflApi__SetAllScenarioData
0x180011864  mov     ebx, eax
0x180011866  test    eax, eax
0x180011868  jns     short loc_180011871
0x18001186a  mov     edx, 1DAh
0x18001186f  jmp     short loc_1800118B6
0x180011871  lea     rcx, [rsp+3D8h+var_388]
0x180011876  call    ?Stop@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001187b  nop
0x18001187c  lea     rax, ??_7CflSetScenarioDataMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable'
0x180011883  mov     [rsp+3D8h+var_388], rax
0x180011888  lea     rcx, [rsp+3D8h+var_388]
0x18001188d  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011892  lea     rcx, [rsp+3D8h+var_388]
0x180011897  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001189c  xor     eax, eax
0x18001189e  jmp     short loc_180011912
0x1800118a0  mov     ebx, 80070057h
0x1800118a5  mov     edx, 1D1h
0x1800118aa  jmp     short loc_1800118B6
0x1800118ac  mov     ebx, 80004003h
0x1800118b1  mov     edx, 1CBh; void *
0x1800118b6  mov     rcx, [rsp+3D8h]; this
0x1800118be  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800118c5  mov     r9d, ebx; char *
0x1800118c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118cd  mov     rcx, [rsp+3D8h]; this
0x1800118d5  mov     r9d, ebx; char *
0x1800118d8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cfl\\api\\dll\\e"...
0x1800118df  mov     edx, 8Fh; void *
0x1800118e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800118e9  nop
0x1800118ea  lea     rax, ??_7CflSetScenarioDataMeasure@CflApiTraceProvider@@6B@; const CflApiTraceProvider::CflSetScenarioDataMeasure::`vftable'
0x1800118f1  mov     [rsp+3D8h+var_388], rax
0x1800118f6  lea     rcx, [rsp+3D8h+var_388]
0x1800118fb  call    ?Destroy@?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180011900  lea     rcx, [rsp+3D8h+var_388]
0x180011905  call    ??1?$ActivityBase@VCflApiTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CflApiTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001190a  mov     eax, ebx
0x18001190c  jmp     short loc_180011912
0x18001190e  mov     eax, [rsp+3D8h+dwSize]
0x180011912  mov     rcx, [rsp+3D8h+var_28]
0x18001191a  xor     rcx, rsp; StackCookie
0x18001191d  call    __security_check_cookie
0x180011922  add     rsp, 3C8h
0x180011929  pop     rdi
0x18001192a  pop     rbx
0x18001192b  retn
```
