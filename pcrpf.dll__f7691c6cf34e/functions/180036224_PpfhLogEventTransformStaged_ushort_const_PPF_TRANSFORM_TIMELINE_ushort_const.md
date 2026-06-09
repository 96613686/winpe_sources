# PpfhLogEventTransformStaged(ushort const *,PPF_TRANSFORM_TIMELINE,ushort const *)

- ea: `0x180036224`
- end: `0x180036393`
- name: `?PpfhLogEventTransformStaged@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@0@Z`
- size: `367`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180016498`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18003535c`
- `0x180036224`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800362a8`
- `ntdll!EtwEventWrite` at `0x18003634a`
- `ntdll!EtwEventWrite` at `0x1800362a8`
- `ntdll!EtwEventWrite` at `0x18003634a`

## pseudocode

```c
int __fastcall PpfhLogEventTransformStaged(const unsigned __int16 *a1, unsigned int a2, const unsigned __int16 *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v11; // [rsp+20h] [rbp-40h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+28h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+38h] [rbp-28h] BYREF
  __int128 v14; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v12 = 0;
  v13 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    if ( !a3 )
      a3 = L"Default";
    v14 = 0;
    v6 = InitializeEventDataDescWithStr(&v12, a3);
    if ( v6 < 0 )
    {
      v7 = 161;
      goto LABEL_10;
    }
    v6 = InitializeEventDataDescWithStr(&v13, a1);
    if ( v6 < 0 )
    {
      v7 = 162;
      goto LABEL_10;
    }
    *(_QWORD *)&v14 = &v11;
    v11 = a2;
    *((_QWORD *)&v14 + 1) = 4;
    v8 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_STAGED_V2, 3, &v12);
    if ( v8 )
    {
      v9 = 166;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v8,
               v11);
    }
  }
  else
  {
    v6 = InitializeEventDataDescWithStr(&v12, a1);
    if ( v6 < 0 )
    {
      v7 = 172;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)v6,
        v11);
      return v6;
    }
    v13.Ptr = (ULONGLONG)&v11;
    v11 = a2;
    *(_QWORD *)&v13.Size = 4;
    v8 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_STAGED, 2, &v12);
    if ( v8 )
    {
      v9 = 176;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v8,
               v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180036224  mov     [rsp-18h+arg_8], rbx
0x180036229  push    rbp
0x18003622a  push    rsi
0x18003622b  push    rdi
0x18003622c  mov     rbp, rsp
0x18003622f  sub     rsp, 60h
0x180036233  mov     rax, cs:__security_cookie
0x18003623a  xor     rax, rsp
0x18003623d  mov     [rbp+var_8], rax
0x180036241  mov     rbx, r8
0x180036244  mov     esi, edx
0x180036246  mov     rdi, rcx
0x180036249  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180036250  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180036255  xorps   xmm0, xmm0
0x180036258  movups  xmmword ptr [rbp+var_38.Ptr], xmm0
0x18003625c  movups  xmmword ptr [rbp+var_28.Ptr], xmm0
0x180036260  test    al, al
0x180036262  jnz     short loc_1800362C6
0x180036264  mov     rdx, rdi; unsigned __int16 *
0x180036267  lea     rcx, [rbp+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x18003626b  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180036270  mov     ebx, eax
0x180036272  test    eax, eax
0x180036274  jns     short loc_18003627D
0x180036276  mov     edx, 0ACh
0x18003627b  jmp     short loc_1800362EF
0x18003627d  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180036284  lea     rax, [rbp+var_40]
0x180036288  lea     r9, [rbp+var_38]
0x18003628c  mov     [rbp+var_28.Ptr], rax
0x180036290  mov     r8d, 2
0x180036296  mov     [rbp+var_40], esi
0x180036299  lea     rdx, PCRPF_EVENT_TRANSFORM_STAGED
0x1800362a0  mov     qword ptr [rbp+var_28.Size], 4
0x1800362a8  call    cs:__imp_EtwEventWrite
0x1800362af  nop     dword ptr [rax+rax+00h]
0x1800362b4  test    eax, eax
0x1800362b6  jz      loc_180036374
0x1800362bc  mov     edx, 0B0h
0x1800362c1  jmp     loc_18003635F
0x1800362c6  lea     rax, aDefault; "Default"
0x1800362cd  test    rbx, rbx
0x1800362d0  lea     rcx, [rbp+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x1800362d4  cmovz   rbx, rax
0x1800362d8  mov     rdx, rbx; unsigned __int16 *
0x1800362db  movups  [rbp+var_18], xmm0
0x1800362df  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800362e4  mov     ebx, eax
0x1800362e6  test    eax, eax
0x1800362e8  jns     short loc_180036306
0x1800362ea  mov     edx, 0A1h; void *
0x1800362ef  mov     rcx, [rbp+18h]; this
0x1800362f3  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800362fa  mov     r9d, ebx; char *
0x1800362fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036302  mov     eax, ebx
0x180036304  jmp     short loc_180036376
0x180036306  mov     rdx, rdi; unsigned __int16 *
0x180036309  lea     rcx, [rbp+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x18003630d  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180036312  mov     ebx, eax
0x180036314  test    eax, eax
0x180036316  jns     short loc_18003631F
0x180036318  mov     edx, 0A2h
0x18003631d  jmp     short loc_1800362EF
0x18003631f  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180036326  lea     rax, [rbp+var_40]
0x18003632a  lea     r9, [rbp+var_38]
0x18003632e  mov     qword ptr [rbp+var_18], rax
0x180036332  mov     r8d, 3
0x180036338  mov     [rbp+var_40], esi
0x18003633b  lea     rdx, PCRPF_EVENT_TRANSFORM_STAGED_V2
0x180036342  mov     qword ptr [rbp+var_18+8], 4
0x18003634a  call    cs:__imp_EtwEventWrite
0x180036351  nop     dword ptr [rax+rax+00h]
0x180036356  test    eax, eax
0x180036358  jz      short loc_180036374
0x18003635a  mov     edx, 0A6h; void *
0x18003635f  mov     rcx, [rbp+18h]; this
0x180036363  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003636a  mov     r9d, eax; char *
0x18003636d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180036372  jmp     short loc_180036376
0x180036374  xor     eax, eax
0x180036376  mov     rcx, [rbp+var_8]
0x18003637a  xor     rcx, rsp; StackCookie
0x18003637d  call    __security_check_cookie
0x180036382  mov     rbx, [rsp+60h+arg_8]
0x18003638a  add     rsp, 60h
0x18003638e  pop     rdi
0x18003638f  pop     rsi
0x180036390  pop     rbp
0x180036391  retn
```
