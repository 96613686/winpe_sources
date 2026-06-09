# PpfhLogEventTransformCancelled(ushort const *,ushort const *)

- ea: `0x180035b18`
- end: `0x180035c5c`
- name: `?PpfhLogEventTransformCancelled@@YAJPEBG0@Z`
- size: `324`
- prototype: `int __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180013ef4`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000dfe0`
- `0x18001aff0`
- `0x18003535c`
- `0x180035b18`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035b82`
- `ntdll!EtwEventWrite` at `0x180035c16`
- `ntdll!EtwEventWrite` at `0x180035b82`
- `ntdll!EtwEventWrite` at `0x180035c16`

## pseudocode

```c
int __fastcall PpfhLogEventTransformCancelled(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rdx
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+20h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
      a2 = L"Default";
    v10 = 0;
    v4 = InitializeEventDataDescWithStr(&v9, a2);
    if ( v4 < 0 )
    {
      v5 = 253;
      goto LABEL_10;
    }
    v4 = InitializeEventDataDescWithStr(&v10, a1);
    if ( v4 < 0 )
    {
      v5 = 254;
      goto LABEL_10;
    }
    v6 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_CANCELLED_V2, 2, &v9);
    if ( v6 )
    {
      v7 = 256;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v6,
               v9.Ptr);
    }
  }
  else
  {
    v4 = InitializeEventDataDescWithStr(&v9, a1);
    if ( v4 < 0 )
    {
      v5 = 262;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)(unsigned int)v4,
        v9.Ptr);
      return v4;
    }
    v6 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_CANCELLED, 1, &v9);
    if ( v6 )
    {
      v7 = 264;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
               (const char *)v6,
               v9.Ptr);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180035b18  mov     [rsp+arg_10], rbx
0x180035b1d  push    rdi
0x180035b1e  sub     rsp, 50h
0x180035b22  mov     rax, cs:__security_cookie
0x180035b29  xor     rax, rsp
0x180035b2c  mov     [rsp+58h+var_18], rax
0x180035b31  mov     rbx, rdx
0x180035b34  mov     rdi, rcx
0x180035b37  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180035b3e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180035b43  xorps   xmm0, xmm0
0x180035b46  movups  xmmword ptr [rsp+58h+var_38.Ptr], xmm0; unsigned int
0x180035b4b  test    al, al
0x180035b4d  jnz     short loc_180035BA0
0x180035b4f  mov     rdx, rdi; unsigned __int16 *
0x180035b52  lea     rcx, [rsp+58h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180035b57  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035b5c  mov     ebx, eax
0x180035b5e  test    eax, eax
0x180035b60  jns     short loc_180035B69
0x180035b62  mov     edx, 106h
0x180035b67  jmp     short loc_180035BCB
0x180035b69  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035b70  lea     r9, [rsp+58h+var_38]
0x180035b75  mov     r8d, 1
0x180035b7b  lea     rdx, PCRPF_EVENT_TRANSFORM_CANCELLED
0x180035b82  call    cs:__imp_EtwEventWrite
0x180035b89  nop     dword ptr [rax+rax+00h]
0x180035b8e  test    eax, eax
0x180035b90  jz      loc_180035C41
0x180035b96  mov     edx, 108h
0x180035b9b  jmp     loc_180035C2B
0x180035ba0  lea     rax, aDefault; "Default"
0x180035ba7  test    rbx, rbx
0x180035baa  lea     rcx, [rsp+58h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180035baf  cmovz   rbx, rax
0x180035bb3  mov     rdx, rbx; unsigned __int16 *
0x180035bb6  movups  xmmword ptr [rsp+58h+var_28.Ptr], xmm0
0x180035bbb  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035bc0  mov     ebx, eax
0x180035bc2  test    eax, eax
0x180035bc4  jns     short loc_180035BE3
0x180035bc6  mov     edx, 0FDh; void *
0x180035bcb  mov     rcx, [rsp+58h]; this
0x180035bd0  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035bd7  mov     r9d, ebx; char *
0x180035bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035bdf  mov     eax, ebx
0x180035be1  jmp     short loc_180035C43
0x180035be3  mov     rdx, rdi; unsigned __int16 *
0x180035be6  lea     rcx, [rsp+58h+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x180035beb  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035bf0  mov     ebx, eax
0x180035bf2  test    eax, eax
0x180035bf4  jns     short loc_180035BFD
0x180035bf6  mov     edx, 0FEh
0x180035bfb  jmp     short loc_180035BCB
0x180035bfd  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035c04  lea     r9, [rsp+58h+var_38]
0x180035c09  mov     r8d, 2
0x180035c0f  lea     rdx, PCRPF_EVENT_TRANSFORM_CANCELLED_V2
0x180035c16  call    cs:__imp_EtwEventWrite
0x180035c1d  nop     dword ptr [rax+rax+00h]
0x180035c22  test    eax, eax
0x180035c24  jz      short loc_180035C41
0x180035c26  mov     edx, 100h; void *
0x180035c2b  mov     rcx, [rsp+58h]; this
0x180035c30  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035c37  mov     r9d, eax; char *
0x180035c3a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035c3f  jmp     short loc_180035C43
0x180035c41  xor     eax, eax
0x180035c43  mov     rcx, [rsp+58h+var_18]
0x180035c48  xor     rcx, rsp; StackCookie
0x180035c4b  call    __security_check_cookie
0x180035c50  mov     rbx, [rsp+58h+arg_10]
0x180035c55  add     rsp, 50h
0x180035c59  pop     rdi
0x180035c5a  retn
```
