# GetMSACloudExperienceHostInfo(ushort * *,bool *)

- ea: `0x140015c60`
- end: `0x140015e17`
- name: `?GetMSACloudExperienceHostInfo@@YAJPEAPEAGPEA_N@Z`
- size: `439`
- prototype: `__int64 __fastcall(unsigned __int16 **, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400a08d0`
- `0x1401ab4e0`

## callees

- `0x140015c60`
- `0x140015e20`
- `0x140086b94`
- `0x140087550`
- `0x140087664`
- `0x14009ac68`
- `0x140111588`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015d51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015d7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015dab`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015d51`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015d7b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140015dab`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140015cdb`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140015d23`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140015cdb`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x140015d23`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x140015d04`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x140015d04`

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
0x140015c60  mov     [rsp-18h+arg_10], rbx
0x140015c65  mov     [rsp-18h+arg_18], rsi
0x140015c6a  push    rbp
0x140015c6b  push    rdi
0x140015c6c  push    r12
0x140015c6e  mov     rbp, rsp
0x140015c71  sub     rsp, 30h
0x140015c75  mov     rdi, rdx
0x140015c78  mov     rsi, rcx
0x140015c7b  mov     qword ptr [rcx], 0
0x140015c82  mov     byte ptr [rdx], 0
0x140015c85  call    IsCflGetScenarioDataPresent
0x140015c8a  test    al, al
0x140015c8c  jnz     short loc_140015CB0
0x140015c8e  mov     rcx, [rbp+18h]; this
0x140015c92  mov     ebx, 80090011h
0x140015c97  mov     r9d, ebx; char *
0x140015c9a  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x140015ca1  mov     edx, 9Dh; void *
0x140015ca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015cab  jmp     loc_140015E01
0x140015cb0  mov     [rbp+lpString1], 0
0x140015cb8  mov     dl, 1
0x140015cba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADPinResetV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2> `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl(void)'::`2'::impl
0x140015cc1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140015cc6  mov     rbx, [rbp+lpString1]
0x140015cca  test    rbx, rbx
0x140015ccd  jz      short loc_140015CF0
0x140015ccf  lea     rcx, [rbp+arg_8]; this
0x140015cd3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140015cd8  mov     rcx, rbx
0x140015cdb  call    cs:__imp_CflFreeBuffer
0x140015ce2  nop     dword ptr [rax+rax+00h]
0x140015ce7  lea     rcx, [rbp+arg_8]; this
0x140015ceb  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140015cf0  mov     [rbp+lpString1], 0
0x140015cf8  xor     r9d, r9d
0x140015cfb  xor     r8d, r8d
0x140015cfe  xor     edx, edx
0x140015d00  lea     rcx, [rbp+lpString1]
0x140015d04  call    cs:__imp_CflGetScenarioDataNew
0x140015d0b  nop     dword ptr [rax+rax+00h]
0x140015d10  mov     ebx, eax
0x140015d12  test    eax, eax
0x140015d14  jns     short loc_140015D34
0x140015d16  mov     rcx, [rbp+lpString1]
0x140015d1a  test    rcx, rcx
0x140015d1d  jz      loc_140015E01
0x140015d23  call    cs:__imp_CflFreeBuffer
0x140015d2a  nop     dword ptr [rax+rax+00h]
0x140015d2f  jmp     loc_140015E01
0x140015d34  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x140015d3c  or      r12d, 0FFFFFFFFh
0x140015d40  mov     r9d, r12d; cchCount2
0x140015d43  lea     r8, String2; "ms-cxh://MSASSPR"
0x140015d4a  mov     edx, r12d; cchCount1
0x140015d4d  mov     rcx, [rbp+lpString1]; lpString1
0x140015d51  call    cs:__imp_CompareStringOrdinal
0x140015d58  nop     dword ptr [rax+rax+00h]
0x140015d5d  cmp     eax, 2
0x140015d60  jz      short loc_140015D90
0x140015d62  mov     [rsp+30h+bIgnoreCase], 1; bIgnoreCase
0x140015d6a  mov     r9d, r12d; cchCount2
0x140015d6d  lea     r8, aMsCxhMsacflpin; "ms-cxh://MSACFLPINRESETSIGNIN"
0x140015d74  mov     edx, r12d; cchCount1
0x140015d77  mov     rcx, [rbp+lpString1]; lpString1
0x140015d7b  call    cs:__imp_CompareStringOrdinal
0x140015d82  nop     dword ptr [rax+rax+00h]
0x140015d87  cmp     eax, 2
0x140015d8a  jz      short loc_140015D90
0x140015d8c  xor     bl, bl
0x140015d8e  jmp     short loc_140015D92
0x140015d90  mov     bl, 1
0x140015d92  mov     [rsp+30h+bIgnoreCase], 1; int
0x140015d9a  mov     r9d, r12d; cchCount2
0x140015d9d  lea     r8, aMsCxhMsacflpin_0; "ms-cxh://MSACFLPINRESET"
0x140015da4  mov     edx, r12d; cchCount1
0x140015da7  mov     rcx, [rbp+lpString1]; lpString1
0x140015dab  call    cs:__imp_CompareStringOrdinal
0x140015db2  nop     dword ptr [rax+rax+00h]
0x140015db7  cmp     eax, 2
0x140015dba  setz    cl
0x140015dbd  test    bl, bl
0x140015dbf  jnz     short loc_140015DE5
0x140015dc1  cmp     eax, 2
0x140015dc4  jz      short loc_140015DE5
0x140015dc6  mov     rcx, [rbp+18h]; this
0x140015dca  mov     ebx, 80090011h
0x140015dcf  mov     r9d, ebx; char *
0x140015dd2  lea     r8, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x140015dd9  mov     edx, 0B3h; void *
0x140015dde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015de3  jmp     short loc_140015DF8
0x140015de5  mov     rax, [rbp+lpString1]
0x140015de9  mov     [rbp+lpString1], 0
0x140015df1  mov     [rsi], rax
0x140015df4  mov     [rdi], cl
0x140015df6  xor     ebx, ebx
0x140015df8  lea     rcx, [rbp+lpString1]
0x140015dfc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CflFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140015e01  mov     eax, ebx
0x140015e03  mov     rbx, [rsp+30h+arg_10]
0x140015e08  mov     rsi, [rsp+30h+arg_18]
0x140015e0d  add     rsp, 30h
0x140015e11  pop     r12
0x140015e13  pop     rdi
0x140015e14  pop     rbp
0x140015e15  retn
```
