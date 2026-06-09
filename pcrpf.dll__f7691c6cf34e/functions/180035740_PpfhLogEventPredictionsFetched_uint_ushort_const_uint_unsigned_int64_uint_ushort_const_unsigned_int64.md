# PpfhLogEventPredictionsFetched(uint,ushort const *,uint,unsigned __int64,uint,ushort const *,unsigned __int64)

- ea: `0x180035740`
- end: `0x180035957`
- name: `?PpfhLogEventPredictionsFetched@@YAJIPEBGI_KI01@Z`
- size: `535`
- prototype: `int __fastcall(int, const unsigned __int16 *, int, __int64, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800141f4`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18003535c`
- `0x180035740`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035808`
- `ntdll!EtwEventWrite` at `0x180035913`
- `ntdll!EtwEventWrite` at `0x180035808`
- `ntdll!EtwEventWrite` at `0x180035913`

## pseudocode

```c
int __fastcall PpfhLogEventPredictionsFetched(
        int a1,
        const unsigned __int16 *a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        unsigned __int64 a7)
{
  const unsigned __int16 *v7; // rbx
  int v9; // edi
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  int v14; // ebx
  unsigned int v16; // [rsp+28h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+38h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+48h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+58h] [rbp-31h] BYREF
  __int64 *v20; // [rsp+68h] [rbp-21h]
  __int64 v21; // [rsp+70h] [rbp-19h]
  unsigned int *v22; // [rsp+78h] [rbp-11h]
  __int64 v23; // [rsp+80h] [rbp-9h]
  unsigned int *v24; // [rsp+88h] [rbp-1h]
  __int64 v25; // [rsp+90h] [rbp+7h]
  unsigned int *v26; // [rsp+98h] [rbp+Fh]
  __int64 v27; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+47h]
  int v29; // [rsp+D8h] [rbp+4Fh] BYREF
  int v30; // [rsp+E8h] [rbp+5Fh] BYREF
  __int64 v31; // [rsp+F0h] [rbp+67h] BYREF

  v31 = a4;
  v30 = a3;
  v29 = a1;
  v7 = a6;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    memset_0(&v17, 0, 0x70u);
    if ( !v7 )
      v7 = L"Default";
    v13 = InitializeEventDataDescWithStr(&v17, v7);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x168,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)v13,
        v16);
      return v14;
    }
    *(_QWORD *)&v18.Size = 4;
    v18.Ptr = (ULONGLONG)&v29;
    v9 = InitializeEventDataDescWithStr(&v19, a2);
    if ( v9 < 0 )
    {
      v10 = 362;
      goto LABEL_12;
    }
    v20 = (__int64 *)&v30;
    v21 = 4;
    v22 = (unsigned int *)&v31;
    v23 = 8;
    v24 = &a5;
    v16 = a7;
    v26 = &v16;
    v25 = 4;
    v27 = 4;
    v11 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_PREDICTIONS_FETCHED_V2, 7, &v17);
    if ( v11 )
    {
      v12 = 374;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v11,
               v16);
    }
  }
  else
  {
    memset_0(&v17, 0, 0x50u);
    *(_QWORD *)&v17.Size = 4;
    v17.Ptr = (ULONGLONG)&v29;
    v9 = InitializeEventDataDescWithStr(&v18, a2);
    if ( v9 < 0 )
    {
      v10 = 381;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)v9,
        v16);
      return v9;
    }
    v19.Ptr = (ULONGLONG)&v30;
    *(_QWORD *)&v19.Size = 4;
    v20 = &v31;
    v21 = 8;
    v22 = &a5;
    v23 = 4;
    v11 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_PREDICTIONS_FETCHED, 5, &v17);
    if ( v11 )
    {
      v12 = 386;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v11,
               v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035740  mov     rax, rsp
0x180035743  mov     [rax+20h], r9
0x180035747  mov     [rax+18h], r8d
0x18003574b  mov     [rax+8], ecx
0x18003574e  push    rbp
0x18003574f  push    rbx
0x180035750  push    rdi
0x180035751  lea     rbp, [rax-47h]
0x180035755  sub     rsp, 0B0h
0x18003575c  mov     rax, cs:__security_cookie
0x180035763  xor     rax, rsp
0x180035766  mov     [rbp+3Fh+var_20], rax
0x18003576a  mov     rbx, [rbp+3Fh+arg_28]
0x18003576e  mov     rdi, rdx
0x180035771  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180035778  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x18003577d  xor     edx, edx; Val
0x18003577f  test    al, al
0x180035781  jnz     loc_180035826
0x180035787  lea     r8d, [rdx+50h]; Size
0x18003578b  lea     rcx, [rbp+3Fh+var_90]; void *
0x18003578f  call    memset_0
0x180035794  lea     rax, [rbp+3Fh+arg_0]
0x180035798  mov     qword ptr [rbp+3Fh+var_90.Size], 4
0x1800357a0  mov     rdx, rdi; unsigned __int16 *
0x1800357a3  mov     [rbp+3Fh+var_90.Ptr], rax
0x1800357a7  lea     rcx, [rbp+3Fh+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x1800357ab  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800357b0  mov     edi, eax
0x1800357b2  test    eax, eax
0x1800357b4  jns     short loc_1800357C0
0x1800357b6  mov     edx, 17Dh
0x1800357bb  jmp     loc_18003589B
0x1800357c0  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800357c7  lea     rax, [rbp+3Fh+arg_10]
0x1800357cb  mov     [rbp+3Fh+var_70.Ptr], rax
0x1800357cf  lea     r9, [rbp+3Fh+var_90]
0x1800357d3  lea     rax, [rbp+3Fh+arg_18]
0x1800357d7  mov     qword ptr [rbp+3Fh+var_70.Size], 4
0x1800357df  mov     [rbp+3Fh+var_60], rax
0x1800357e3  lea     rdx, PCRPF_EVENT_PREDICTIONS_FETCHED
0x1800357ea  lea     rax, [rbp+3Fh+arg_20]
0x1800357ee  mov     [rbp+3Fh+var_58], 8
0x1800357f6  mov     r8d, 5
0x1800357fc  mov     [rbp+3Fh+var_50], rax
0x180035800  mov     [rbp+3Fh+var_48], 4
0x180035808  call    cs:__imp_EtwEventWrite
0x18003580f  nop     dword ptr [rax+rax+00h]
0x180035814  test    eax, eax
0x180035816  jz      loc_18003593D
0x18003581c  mov     edx, 182h
0x180035821  jmp     loc_180035928
0x180035826  mov     r8d, 70h ; 'p'; Size
0x18003582c  lea     rcx, [rbp+3Fh+var_90]; void *
0x180035830  call    memset_0
0x180035835  lea     rax, aDefault; "Default"
0x18003583c  test    rbx, rbx
0x18003583f  lea     rcx, [rbp+3Fh+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x180035843  cmovz   rbx, rax
0x180035847  mov     rdx, rbx; unsigned __int16 *
0x18003584a  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x18003584f  mov     ebx, eax
0x180035851  test    eax, eax
0x180035853  jns     short loc_180035874
0x180035855  mov     rcx, [rbp+47h]; this
0x180035859  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035860  mov     r9d, eax; char *
0x180035863  mov     edx, 168h; void *
0x180035868  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003586d  mov     eax, ebx
0x18003586f  jmp     loc_18003593F
0x180035874  lea     rax, [rbp+3Fh+arg_0]
0x180035878  mov     qword ptr [rbp+3Fh+var_80.Size], 4
0x180035880  mov     rdx, rdi; unsigned __int16 *
0x180035883  mov     [rbp+3Fh+var_80.Ptr], rax
0x180035887  lea     rcx, [rbp+3Fh+var_70]; struct _EVENT_DATA_DESCRIPTOR *
0x18003588b  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035890  mov     edi, eax
0x180035892  test    eax, eax
0x180035894  jns     short loc_1800358B5
0x180035896  mov     edx, 16Ah; void *
0x18003589b  mov     rcx, [rbp+47h]; this
0x18003589f  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800358a6  mov     r9d, edi; char *
0x1800358a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358ae  mov     eax, edi
0x1800358b0  jmp     loc_18003593F
0x1800358b5  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800358bc  lea     rax, [rbp+3Fh+arg_10]
0x1800358c0  mov     [rbp+3Fh+var_60], rax
0x1800358c4  lea     r9, [rbp+3Fh+var_90]
0x1800358c8  lea     rax, [rbp+3Fh+arg_18]
0x1800358cc  mov     [rbp+3Fh+var_58], 4
0x1800358d4  mov     [rbp+3Fh+var_50], rax
0x1800358d8  lea     rdx, PCRPF_EVENT_PREDICTIONS_FETCHED_V2
0x1800358df  lea     rax, [rbp+3Fh+arg_20]
0x1800358e3  mov     [rbp+3Fh+var_48], 8
0x1800358eb  mov     [rbp+3Fh+var_40], rax
0x1800358ef  mov     r8d, 7
0x1800358f5  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1800358f8  mov     [rbp+3Fh+var_A0], eax
0x1800358fb  lea     rax, [rbp+3Fh+var_A0]
0x1800358ff  mov     [rbp+3Fh+var_30], rax
0x180035903  mov     [rbp+3Fh+var_38], 4
0x18003590b  mov     [rbp+3Fh+var_28], 4
0x180035913  call    cs:__imp_EtwEventWrite
0x18003591a  nop     dword ptr [rax+rax+00h]
0x18003591f  test    eax, eax
0x180035921  jz      short loc_18003593D
0x180035923  mov     edx, 176h; void *
0x180035928  mov     rcx, [rbp+47h]; this
0x18003592c  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035933  mov     r9d, eax; char *
0x180035936  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003593b  jmp     short loc_18003593F
0x18003593d  xor     eax, eax
0x18003593f  mov     rcx, [rbp+3Fh+var_20]
0x180035943  xor     rcx, rsp; StackCookie
0x180035946  call    __security_check_cookie
0x18003594b  add     rsp, 0B0h
0x180035952  pop     rdi
0x180035953  pop     rbx
0x180035954  pop     rbp
0x180035955  retn
```
