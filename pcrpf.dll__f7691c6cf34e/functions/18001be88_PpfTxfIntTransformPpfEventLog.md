# PpfTxfIntTransformPpfEventLog

- ea: `0x18001be88`
- end: `0x18001c097`
- name: `PpfTxfIntTransformPpfEventLog`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, void *, unsigned int, int, struct PPF_TRANSFORM_CONTEXT *, enum PPF_TRANSFORM_RESULT *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800107e8`
- `0x1800141f4`
- `0x180016498`
- `0x180017650`
- `0x180017a80`

## callees

- `0x180009c64`
- `0x18001aff0`
- `0x18001be88`
- `0x18002d5ec`
- `0x180040270`
- `0x180040350`
- `0x180041df0`
- `0x180059010`

## string_xrefs

- `0x18001bf2c`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001bfc7`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001bfec`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall PpfTxfIntTransformPpfEventLog(
        unsigned __int8 *a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        int a5,
        struct PPF_TRANSFORM_CONTEXT *a6,
        enum PPF_TRANSFORM_RESULT *a7,
        unsigned __int8 **a8,
        unsigned int *a9,
        unsigned __int8 **a10,
        unsigned int *a11,
        unsigned int *a12)
{
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // edi
  int v19; // ebx
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-A8h]
  bool v23; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    return ((__int64 (__fastcall *)(unsigned __int8 *, _QWORD, void *, _QWORD, int, struct PPF_TRANSFORM_CONTEXT *, enum PPF_TRANSFORM_RESULT *, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, unsigned int *))off_180072070)(
             a1,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8,
             a9,
             a10,
             a11,
             a12);
  v16 = 0;
  while ( 1 )
  {
    v23 = 0;
    v17 = (*(&funcs_18001BEE3 + 6 * v16))(a3, a4, &v23);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E7,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v17,
        v22);
      return v18;
    }
    if ( v23 )
      break;
    if ( (unsigned int)++v16 >= 2 )
    {
      v19 = -920125435;
      v20 = 1521;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v19,
        v22);
      return (unsigned int)v19;
    }
  }
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
    0x5EAu,
    "PpfTxfIntTransformPpfEventLog",
    "Transform is of format: %s",
    (const char *)*(&g_transformProviders + 6 * v16));
  v22 = a5;
  v19 = ((__int64 (__fastcall *)(unsigned __int8 *, _QWORD, void *, _QWORD))funcs_18001BFAF[6 * v16])(a1, a2, a3, a4);
  if ( v19 < 0 )
  {
    v20 = 1517;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18001be88  push    rbx
0x18001be8a  push    rbp
0x18001be8b  push    rsi
0x18001be8c  push    rdi
0x18001be8d  push    r12
0x18001be8f  push    r13
0x18001be91  push    r14
0x18001be93  push    r15
0x18001be95  sub     rsp, 88h
0x18001be9c  mov     ebp, r9d
0x18001be9f  mov     r14, r8
0x18001bea2  mov     r15d, edx
0x18001bea5  mov     r12, rcx
0x18001bea8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x18001beaf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x18001beb4  test    al, al
0x18001beb6  jz      loc_18001C004
0x18001bebc  xor     ebx, ebx
0x18001bebe  lea     r13, ?g_transformProviders@@3PAUPPF_TRANSFORM_FORMAT_PROVIDER@@A; PPF_TRANSFORM_FORMAT_PROVIDER near * g_transformProviders
0x18001bec5  movsxd  rax, ebx
0x18001bec8  lea     r8, [rsp+0C8h+var_58]; bool *
0x18001becd  mov     edx, ebp; unsigned int
0x18001becf  mov     [rsp+0C8h+var_58], 0
0x18001bed4  mov     rcx, r14; void *
0x18001bed7  lea     rsi, [rax+rax*2]
0x18001bedb  add     rsi, rsi
0x18001bede  mov     rax, (funcs_18001BEE3 - 180072000h)[r13+rsi*8]
0x18001bee3  call    _guard_dispatch_icall$thunk$10345483385596137414; PpfTxfBinIsOfFormat(void *,uint,bool *) ...
0x18001bee8  mov     edi, eax
0x18001beea  test    eax, eax
0x18001beec  js      loc_18001BFE4
0x18001bef2  cmp     [rsp+0C8h+var_58], 0
0x18001bef7  jnz     short loc_18001BF0F
0x18001bef9  inc     ebx
0x18001befb  cmp     ebx, 2
0x18001befe  jb      short loc_18001BEC5
0x18001bf00  mov     ebx, 0C9280005h
0x18001bf05  mov     edx, 5F1h
0x18001bf0a  jmp     loc_18001BFBF
0x18001bf0f  mov     rax, [r13+rsi*8+0]
0x18001bf14  lea     r9, aTransformIsOfF; "Transform is of format: %s"
0x18001bf1b  lea     r8, aPpftxfinttrans; "PpfTxfIntTransformPpfEventLog"
0x18001bf22  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18001bf27  mov     edx, 5EAh; unsigned int
0x18001bf2c  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001bf33  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001bf38  mov     rax, [rsp+0C8h+arg_58]
0x18001bf40  mov     r9d, ebp; unsigned int
0x18001bf43  mov     rcx, [rsp+0C8h+arg_40]
0x18001bf4b  mov     r8, r14; void *
0x18001bf4e  mov     [rsp+0C8h+var_70], rax; unsigned int *
0x18001bf53  mov     edx, r15d; unsigned int
0x18001bf56  mov     rax, [rsp+0C8h+arg_50]
0x18001bf5e  mov     [rsp+0C8h+var_78], rax; unsigned int *
0x18001bf63  mov     rax, [rsp+0C8h+arg_48]
0x18001bf6b  mov     [rsp+0C8h+var_80], rax; unsigned __int8 **
0x18001bf70  mov     rax, (funcs_18001BFAF - 180072000h)[r13+rsi*8]
0x18001bf75  mov     [rsp+0C8h+var_88], rcx; unsigned int *
0x18001bf7a  mov     rcx, [rsp+0C8h+arg_38]
0x18001bf82  mov     [rsp+0C8h+var_90], rcx; unsigned __int8 **
0x18001bf87  mov     rcx, [rsp+0C8h+arg_30]
0x18001bf8f  mov     [rsp+0C8h+var_98], rcx; enum PPF_TRANSFORM_RESULT *
0x18001bf94  mov     rcx, [rsp+0C8h+arg_28]
0x18001bf9c  mov     [rsp+0C8h+var_A0], rcx; struct PPF_TRANSFORM_CONTEXT *
0x18001bfa1  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x18001bfa8  mov     dword ptr [rsp+0C8h+var_A8], ecx; int
0x18001bfac  mov     rcx, r12; unsigned __int8 *
0x18001bfaf  call    _guard_dispatch_icall$thunk$10345483385596137414; PpfTxfBinTransformPpfEventLog(uchar *,uint,void *,uint,uint,PPF_TRANSFORM_CONTEXT *,PPF_TRANSFORM_RESULT *,uchar * *,uint *,uchar * *,uint *,uint *) ...
0x18001bfb4  mov     ebx, eax
0x18001bfb6  test    eax, eax
0x18001bfb8  jns     short loc_18001BFDD
0x18001bfba  mov     edx, 5EDh; void *
0x18001bfbf  mov     rcx, [rsp+0C8h]; this
0x18001bfc7  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001bfce  mov     r9d, ebx; char *
0x18001bfd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bfd6  mov     eax, ebx
0x18001bfd8  jmp     loc_18001C082
0x18001bfdd  xor     eax, eax
0x18001bfdf  jmp     loc_18001C082
0x18001bfe4  mov     rcx, [rsp+0C8h]; this
0x18001bfec  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001bff3  mov     r9d, edi; char *
0x18001bff6  mov     edx, 5E7h; void *
0x18001bffb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c000  mov     eax, edi
0x18001c002  jmp     short loc_18001C082
0x18001c004  mov     rax, [rsp+0C8h+arg_58]
0x18001c00c  mov     r9d, ebp
0x18001c00f  mov     rcx, [rsp+0C8h+arg_40]
0x18001c017  mov     r8, r14
0x18001c01a  mov     [rsp+0C8h+var_70], rax
0x18001c01f  mov     edx, r15d
0x18001c022  mov     rax, [rsp+0C8h+arg_50]
0x18001c02a  mov     [rsp+0C8h+var_78], rax
0x18001c02f  mov     rax, [rsp+0C8h+arg_48]
0x18001c037  mov     [rsp+0C8h+var_80], rax
0x18001c03c  mov     rax, cs:off_180072070
0x18001c043  mov     [rsp+0C8h+var_88], rcx
0x18001c048  mov     rcx, [rsp+0C8h+arg_38]
0x18001c050  mov     [rsp+0C8h+var_90], rcx
0x18001c055  mov     rcx, [rsp+0C8h+arg_30]
0x18001c05d  mov     [rsp+0C8h+var_98], rcx
0x18001c062  mov     rcx, [rsp+0C8h+arg_28]
0x18001c06a  mov     [rsp+0C8h+var_A0], rcx
0x18001c06f  mov     ecx, dword ptr [rsp+0C8h+arg_20]
0x18001c076  mov     dword ptr [rsp+0C8h+var_A8], ecx
0x18001c07a  mov     rcx, r12
0x18001c07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c082  add     rsp, 88h
0x18001c089  pop     r15
0x18001c08b  pop     r14
0x18001c08d  pop     r13
0x18001c08f  pop     r12
0x18001c091  pop     rdi
0x18001c092  pop     rsi
0x18001c093  pop     rbp
0x18001c094  pop     rbx
0x18001c095  retn
```
