# _lambda_ae1d8ede72b8928ed4ee48978e64dbf4_::operator()

- ea: `0x18001a698`
- end: `0x18001a77f`
- name: `_lambda_ae1d8ede72b8928ed4ee48978e64dbf4_::operator()`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019784`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x18001a698`
- `0x18001aae8`
- `0x180022ef4`
- `0x18002308c`

## string_xrefs

- `0x18001a74a`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_ae1d8ede72b8928ed4ee48978e64dbf4_::operator()(enum DelayRetryAction ***a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int RegistryDwordValue; // eax
  enum DelayRetryAction *v8; // rdx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  enum DelayRetryAction v12; // [rsp+48h] [rbp+10h] BYREF
  bool v13; // [rsp+50h] [rbp+18h] BYREF
  HKEY v14; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v14,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        L"AIKCertEnroll",
                                        (unsigned __int16 *)&v14);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v12 = DelayRetryUnknown;
    RegistryDwordValue = NgcUtils::GetRegistryDwordValue(
                           (NgcUtils *)0xFFFFFFFF80000002LL,
                           (const WCHAR *)v14,
                           L"RetryAction",
                           (unsigned __int16 *)&v12);
    v8 = **a1;
    if ( RegistryDwordValue >= 0 )
    {
      *v8 = v12;
    }
    else
    {
      *v8 = DelayRetryUnknown;
      LOBYTE(v12) = 0;
      NgcStateSeparatedRegistryLocation = ClaimPregenKey(
                                            (const struct _PregenParms *)&s_pregenParamsAik,
                                            **a1,
                                            &v13,
                                            0,
                                            0,
                                            (bool *)&v12);
      v5 = NgcStateSeparatedRegistryLocation;
      if ( NgcStateSeparatedRegistryLocation < 0 )
      {
        v6 = 798;
        goto LABEL_6;
      }
    }
    v5 = 0;
    goto LABEL_9;
  }
  v6 = 773;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    v10);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  return v5;
}

```

## disassembly

```asm
0x18001a698  mov     [rsp+arg_0], rbx
0x18001a69d  push    rdi
0x18001a69e  sub     rsp, 30h
0x18001a6a2  mov     rdi, rcx
0x18001a6a5  mov     [rsp+38h+arg_18], 0
0x18001a6ae  xor     edx, edx
0x18001a6b0  lea     rcx, [rsp+38h+arg_18]
0x18001a6b5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001a6ba  lea     r9, [rsp+38h+arg_18]; unsigned __int16 *
0x18001a6bf  lea     r8, aAikcertenroll; "AIKCertEnroll"
0x18001a6c6  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001a6cb  mov     ebx, eax
0x18001a6cd  test    eax, eax
0x18001a6cf  jns     short loc_18001A6D8
0x18001a6d1  mov     edx, 305h
0x18001a6d6  jmp     short loc_18001A74A
0x18001a6d8  mov     [rsp+38h+arg_8], 0
0x18001a6e0  lea     r9, [rsp+38h+arg_8]; unsigned __int16 *
0x18001a6e5  lea     r8, aRetryaction; "RetryAction"
0x18001a6ec  mov     rdx, [rsp+38h+arg_18]; HKEY
0x18001a6f1  mov     rcx, 0FFFFFFFF80000002h; this
0x18001a6f8  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001a6fd  mov     rcx, [rdi]
0x18001a700  mov     rdx, [rcx]
0x18001a703  test    eax, eax
0x18001a705  jns     short loc_18001A760
0x18001a707  mov     dword ptr [rdx], 0
0x18001a70d  mov     byte ptr [rsp+38h+arg_8], 0
0x18001a712  mov     rdx, [rdi]
0x18001a715  lea     rax, [rsp+38h+arg_8]
0x18001a71a  mov     [rsp+38h+var_10], rax; bool *
0x18001a71f  mov     [rsp+38h+var_18], 0; int
0x18001a728  xor     r9d, r9d; unsigned __int16 **
0x18001a72b  lea     r8, [rsp+38h+arg_10]; bool *
0x18001a730  mov     rdx, [rdx]; enum DelayRetryAction *
0x18001a733  lea     rcx, ?s_pregenParamsAik@@3U_PregenParms@@A; struct _PregenParms *
0x18001a73a  call    ?ClaimPregenKey@@YAJPEBU_PregenParms@@PEAW4DelayRetryAction@@PEA_NPEAPEAGPEAU_NgcPregenState@@2@Z; ClaimPregenKey(_PregenParms const *,DelayRetryAction *,bool *,ushort * *,_NgcPregenState *,bool *)
0x18001a73f  mov     ebx, eax
0x18001a741  test    eax, eax
0x18001a743  jns     short loc_18001A766
0x18001a745  mov     edx, 31Eh; void *
0x18001a74a  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001a751  mov     r9d, eax; char *
0x18001a754  mov     rcx, [rsp+38h]; this
0x18001a759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a75e  jmp     short loc_18001A768
0x18001a760  mov     eax, [rsp+38h+arg_8]
0x18001a764  mov     [rdx], eax
0x18001a766  xor     ebx, ebx
0x18001a768  lea     rcx, [rsp+38h+arg_18]
0x18001a76d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a772  mov     eax, ebx
0x18001a774  mov     rbx, [rsp+38h+arg_0]
0x18001a779  add     rsp, 30h
0x18001a77d  pop     rdi
0x18001a77e  retn
```
