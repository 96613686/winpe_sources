# winrt::Windows::Internal::Eap::Utility::implementation::ExportTlsOnePointThreeAndAboveKeyMaterialUsingRfc5705(_SecHandle * const,winrt::Windows::Internal::Eap::Utility::EapKeyMaterialType,gsl::span<uchar,-1>)

- ea: `0x18002faec`
- end: `0x18002fb65`
- name: `?ExportTlsOnePointThreeAndAboveKeyMaterialUsingRfc5705@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@QEAU_SecHandle@@W4EapKeyMaterialType@23456@V?$span@E$0?0@gsl@@@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int128 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ab00`
- `0x18001abf0`

## callees

- `0x180004380`
- `0x1800101c4`
- `0x18002f8bc`
- `0x18002faec`

## string_xrefs

- `0x18002fb16`: `EXPORTER: Inner Methods Compound Keys`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::ExportTlsOnePointThreeAndAboveKeyMaterialUsingRfc5705(
        __int64 a1,
        __int64 a2,
        int a3,
        __int128 *a4)
{
  int v5; // r8d
  __int128 v6; // xmm0
  __int64 v7; // r9
  const char *v8; // r8
  unsigned int v10; // eax
  int v11; // [rsp+20h] [rbp-38h]
  __int128 v12; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a3 - 4;
  if ( v5 )
  {
    if ( v5 != 1 )
    {
      v10 = wil::verify_hresult<long>(0x80004001);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\exporteapkeymaterialusingrfc5705.cpp",
        (const char *)v10,
        v11);
    }
    v6 = *a4;
    v7 = 64;
    v8 = "EXPORTER: Session Key Generating Function";
  }
  else
  {
    v6 = *a4;
    v8 = "EXPORTER: Inner Methods Compound Keys";
    v7 = 60;
  }
  v12 = v6;
  winrt::Windows::Internal::Eap::Utility::implementation::ExportGenericKeyMaterialUsingRfc5705(a1, a2, v8, v7, &v12);
  return a1;
}

```

## disassembly

```asm
0x18002faec  push    rbx
0x18002faee  sub     rsp, 50h
0x18002faf2  mov     rbx, rcx
0x18002faf5  sub     r8d, 4
0x18002faf9  jz      short loc_18002FB12
0x18002fafb  cmp     r8d, 1
0x18002faff  jnz     short loc_18002FB41
0x18002fb01  movaps  xmm0, xmmword ptr [r9]
0x18002fb05  lea     r9d, [r8+3Fh]
0x18002fb09  lea     r8, aExporterSessio; "EXPORTER: Session Key Generating Functi"...
0x18002fb10  jmp     short loc_18002FB23
0x18002fb12  movaps  xmm0, xmmword ptr [r9]
0x18002fb16  lea     r8, aExporterInnerM; "EXPORTER: Inner Methods Compound Keys"
0x18002fb1d  mov     r9d, 3Ch ; '<'
0x18002fb23  lea     rax, [rsp+58h+var_18]
0x18002fb28  movdqa  [rsp+58h+var_18], xmm0
0x18002fb2e  mov     qword ptr [rsp+58h+var_38], rax
0x18002fb33  call    ?ExportGenericKeyMaterialUsingRfc5705@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@QEAU_SecHandle@@PEADIV?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::ExportGenericKeyMaterialUsingRfc5705(_SecHandle * const,char *,uint,gsl::span<uchar,-1>)
0x18002fb38  mov     rax, rbx
0x18002fb3b  add     rsp, 50h
0x18002fb3f  pop     rbx
0x18002fb40  retn
0x18002fb41  mov     ecx, 80004001h
0x18002fb46  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002fb4b  mov     rcx, [rsp+58h]; this
0x18002fb50  lea     r8, aOnecoreuapNetE_0; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002fb57  mov     r9d, eax; char *
0x18002fb5a  mov     edx, 0ABh; void *
0x18002fb5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
