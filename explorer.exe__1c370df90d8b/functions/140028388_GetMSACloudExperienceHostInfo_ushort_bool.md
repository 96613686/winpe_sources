# GetMSACloudExperienceHostInfo(ushort * *,bool *)

- ea: `0x140028388`
- end: `0x14002851a`
- name: `?GetMSACloudExperienceHostInfo@@YAJPEAPEAGPEA_N@Z`
- size: `402`
- prototype: `__int64 __fastcall(unsigned __int16 **, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14009d5c0`
- `0x1401ab210`

## callees

- `0x140028388`
- `0x140028520`
- `0x1400811ac`
- `0x14008192c`
- `0x14008194c`
- `0x1400954e0`
- `0x140107518`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140028467`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002848b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400284b5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140028467`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14002848b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1400284b5`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140028403`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x14002843f`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140028403`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x14002843f`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x140028426`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x140028426`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetMSACloudExperienceHostInfo(unsigned __int16 **a1, bool *a2)
{
  __int64 v4; // rdx
  int ScenarioDataNew; // ebx
  LPCWCH v6; // rbx
  bool v7; // bl
  int v8; // eax
  bool v9; // cl
  unsigned __int16 *v10; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-10h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPCWCH lpString1; // [rsp+50h] [rbp+20h] BYREF
  char v16; // [rsp+58h] [rbp+28h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( (unsigned __int8)IsCflGetScenarioDataPresent() )
  {
    lpString1 = 0;
    LOBYTE(v4) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl'::`2'::impl,
      v4);
    v6 = lpString1;
    if ( lpString1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
      CflFreeBuffer(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
    }
    lpString1 = 0;
    ScenarioDataNew = CflGetScenarioDataNew(&lpString1, 0, 0, 0);
    if ( ScenarioDataNew >= 0 )
    {
      v7 = CompareStringOrdinal(lpString1, -1, L"ms-cxh://MSASSPR", -1, 1) == 2
        || CompareStringOrdinal(lpString1, -1, L"ms-cxh://MSACFLPINRESETSIGNIN", -1, 1) == 2;
      v8 = CompareStringOrdinal(lpString1, -1, L"ms-cxh://MSACFLPINRESET", -1, 1);
      v9 = v8 == 2;
      if ( v7 || v8 == 2 )
      {
        v10 = (unsigned __int16 *)lpString1;
        lpString1 = 0;
        *a1 = v10;
        *a2 = v9;
        ScenarioDataNew = 0;
      }
      else
      {
        ScenarioDataNew = -2146893807;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB3,
          (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
          (const char *)0x80090011LL,
          bIgnoreCasea);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    }
    else if ( lpString1 )
    {
      CflFreeBuffer(lpString1);
    }
  }
  else
  {
    ScenarioDataNew = -2146893807;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)0x80090011LL,
      bIgnoreCase);
  }
  return (unsigned int)ScenarioDataNew;
}

```

## disassembly

```asm
0x140028388  mov     [rsp-18h+arg_10], rbx
0x14002838d  mov     [rsp-18h+arg_18], rsi
0x140028392  push    rbp
0x140028393  push    rdi
0x140028394  push    r12
0x140028396  mov     rbp, rsp
0x140028399  sub     rsp, 30h
0x14002839d  mov     rdi, rdx
0x1400283a0  mov     rsi, rcx
0x1400283a3  mov     qword ptr [rcx], 0
0x1400283aa  mov     byte ptr [rdx], 0
0x1400283ad  call    IsCflGetScenarioDataPresent
0x1400283b2  test    al, al
0x1400283b4  jnz     short loc_1400283D8
0x1400283b6  mov     rcx, [rbp+18h]; this
0x1400283ba  mov     ebx, 80090011h
0x1400283bf  mov     r9d, ebx; char *
0x1400283c2  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x1400283c9  mov     edx, 9Dh; void *
0x1400283ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400283d3  jmp     loc_140028505
0x1400283d8  mov     [rbp+lpString1], 0
0x1400283e0  mov     dl, 1
0x1400283e2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADPinResetV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2> `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl(void)'::`2'::impl
0x1400283e9  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400283ee  mov     rbx, [rbp+lpString1]
0x1400283f2  test    rbx, rbx
0x1400283f5  jz      short loc_140028412
0x1400283f7  lea     rcx, [rbp+arg_8]; this
0x1400283fb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140028400  mov     rcx, rbx
0x140028403  call    cs:__imp_CflFreeBuffer
0x140028409  lea     rcx, [rbp+arg_8]; this
0x14002840d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140028412  mov     [rbp+lpString1], 0
0x14002841a  xor     r9d, r9d
0x14002841d  xor     r8d, r8d
0x140028420  xor     edx, edx
0x140028422  lea     rcx, [rbp+lpString1]
0x140028426  call    cs:__imp_CflGetScenarioDataNew
0x14002842c  mov     ebx, eax
0x14002842e  test    eax, eax
0x140028430  jns     short loc_14002844A
0x140028432  mov     rcx, [rbp+lpString1]
0x140028436  test    rcx, rcx
0x140028439  jz      loc_140028505
0x14002843f  call    cs:__imp_CflFreeBuffer
0x140028445  jmp     loc_140028505
0x14002844a  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x140028452  or      r12d, 0FFFFFFFFh
0x140028456  mov     r9d, r12d; cchCount2
0x140028459  lea     r8, aMsCxhMsasspr; "ms-cxh://MSASSPR"
0x140028460  mov     edx, r12d; cchCount1
0x140028463  mov     rcx, [rbp+lpString1]; lpString1
0x140028467  call    cs:__imp_CompareStringOrdinal
0x14002846d  cmp     eax, 2
0x140028470  jz      short loc_14002849A
0x140028472  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x14002847a  mov     r9d, r12d; cchCount2
0x14002847d  lea     r8, aMsCxhMsacflpin; "ms-cxh://MSACFLPINRESETSIGNIN"
0x140028484  mov     edx, r12d; cchCount1
0x140028487  mov     rcx, [rbp+lpString1]; lpString1
0x14002848b  call    cs:__imp_CompareStringOrdinal
0x140028491  cmp     eax, 2
0x140028494  jz      short loc_14002849A
0x140028496  xor     bl, bl
0x140028498  jmp     short loc_14002849C
0x14002849a  mov     bl, 1
0x14002849c  mov     [rsp+30h+bIgnoreCase], 1; int
0x1400284a4  mov     r9d, r12d; cchCount2
0x1400284a7  lea     r8, aMsCxhMsacflpin_0; "ms-cxh://MSACFLPINRESET"
0x1400284ae  mov     edx, r12d; cchCount1
0x1400284b1  mov     rcx, [rbp+lpString1]; lpString1
0x1400284b5  call    cs:__imp_CompareStringOrdinal
0x1400284bb  cmp     eax, 2
0x1400284be  setz    cl
0x1400284c1  test    bl, bl
0x1400284c3  jnz     short loc_1400284E9
0x1400284c5  cmp     eax, 2
0x1400284c8  jz      short loc_1400284E9
0x1400284ca  mov     rcx, [rbp+18h]; this
0x1400284ce  mov     ebx, 80090011h
0x1400284d3  mov     r9d, ebx; char *
0x1400284d6  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x1400284dd  mov     edx, 0B3h; void *
0x1400284e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400284e7  jmp     short loc_1400284FC
0x1400284e9  mov     rax, [rbp+lpString1]
0x1400284ed  mov     [rbp+lpString1], 0
0x1400284f5  mov     [rsi], rax
0x1400284f8  mov     [rdi], cl
0x1400284fa  xor     ebx, ebx
0x1400284fc  lea     rcx, [rbp+lpString1]
0x140028500  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CflFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140028505  mov     eax, ebx
0x140028507  mov     rbx, [rsp+30h+arg_10]
0x14002850c  mov     rsi, [rsp+30h+arg_18]
0x140028511  add     rsp, 30h
0x140028515  pop     r12
0x140028517  pop     rdi
0x140028518  pop     rbp
0x140028519  retn
```
