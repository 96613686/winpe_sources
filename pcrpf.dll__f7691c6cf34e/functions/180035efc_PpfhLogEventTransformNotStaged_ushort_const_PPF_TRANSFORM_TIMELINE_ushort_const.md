# PpfhLogEventTransformNotStaged(ushort const *,PPF_TRANSFORM_TIMELINE,ushort const *)

- ea: `0x180035efc`
- end: `0x18003606b`
- name: `?PpfhLogEventTransformNotStaged@@YAJPEBGW4PPF_TRANSFORM_TIMELINE@@0@Z`
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
- `0x180035efc`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035f80`
- `ntdll!EtwEventWrite` at `0x180036022`
- `ntdll!EtwEventWrite` at `0x180035f80`
- `ntdll!EtwEventWrite` at `0x180036022`

## pseudocode

```c
int __fastcall PpfhLogEventTransformNotStaged(const unsigned __int16 *a1, unsigned int a2, const unsigned __int16 *a3)
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
      v7 = 191;
      goto LABEL_10;
    }
    v6 = InitializeEventDataDescWithStr(&v13, a1);
    if ( v6 < 0 )
    {
      v7 = 192;
      goto LABEL_10;
    }
    *(_QWORD *)&v14 = &v11;
    v11 = a2;
    *((_QWORD *)&v14 + 1) = 4;
    v8 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_NOT_STAGED_V2, 3, &v12);
    if ( v8 )
    {
      v9 = 196;
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
      v7 = 202;
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
    v8 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_TRANSFORM_NOT_STAGED, 2, &v12);
    if ( v8 )
    {
      v9 = 206;
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
0x180035efc  mov     [rsp-18h+arg_8], rbx
0x180035f01  push    rbp
0x180035f02  push    rsi
0x180035f03  push    rdi
0x180035f04  mov     rbp, rsp
0x180035f07  sub     rsp, 60h
0x180035f0b  mov     rax, cs:__security_cookie
0x180035f12  xor     rax, rsp
0x180035f15  mov     [rbp+var_8], rax
0x180035f19  mov     rbx, r8
0x180035f1c  mov     esi, edx
0x180035f1e  mov     rdi, rcx
0x180035f21  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180035f28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180035f2d  xorps   xmm0, xmm0
0x180035f30  movups  xmmword ptr [rbp+var_38.Ptr], xmm0
0x180035f34  movups  xmmword ptr [rbp+var_28.Ptr], xmm0
0x180035f38  test    al, al
0x180035f3a  jnz     short loc_180035F9E
0x180035f3c  mov     rdx, rdi; unsigned __int16 *
0x180035f3f  lea     rcx, [rbp+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180035f43  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035f48  mov     ebx, eax
0x180035f4a  test    eax, eax
0x180035f4c  jns     short loc_180035F55
0x180035f4e  mov     edx, 0CAh
0x180035f53  jmp     short loc_180035FC7
0x180035f55  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035f5c  lea     rax, [rbp+var_40]
0x180035f60  lea     r9, [rbp+var_38]
0x180035f64  mov     [rbp+var_28.Ptr], rax
0x180035f68  mov     r8d, 2
0x180035f6e  mov     [rbp+var_40], esi
0x180035f71  lea     rdx, PCRPF_EVENT_TRANSFORM_NOT_STAGED
0x180035f78  mov     qword ptr [rbp+var_28.Size], 4
0x180035f80  call    cs:__imp_EtwEventWrite
0x180035f87  nop     dword ptr [rax+rax+00h]
0x180035f8c  test    eax, eax
0x180035f8e  jz      loc_18003604C
0x180035f94  mov     edx, 0CEh
0x180035f99  jmp     loc_180036037
0x180035f9e  lea     rax, aDefault; "Default"
0x180035fa5  test    rbx, rbx
0x180035fa8  lea     rcx, [rbp+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x180035fac  cmovz   rbx, rax
0x180035fb0  mov     rdx, rbx; unsigned __int16 *
0x180035fb3  movups  [rbp+var_18], xmm0
0x180035fb7  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035fbc  mov     ebx, eax
0x180035fbe  test    eax, eax
0x180035fc0  jns     short loc_180035FDE
0x180035fc2  mov     edx, 0BFh; void *
0x180035fc7  mov     rcx, [rbp+18h]; this
0x180035fcb  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035fd2  mov     r9d, ebx; char *
0x180035fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035fda  mov     eax, ebx
0x180035fdc  jmp     short loc_18003604E
0x180035fde  mov     rdx, rdi; unsigned __int16 *
0x180035fe1  lea     rcx, [rbp+var_28]; struct _EVENT_DATA_DESCRIPTOR *
0x180035fe5  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035fea  mov     ebx, eax
0x180035fec  test    eax, eax
0x180035fee  jns     short loc_180035FF7
0x180035ff0  mov     edx, 0C0h
0x180035ff5  jmp     short loc_180035FC7
0x180035ff7  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035ffe  lea     rax, [rbp+var_40]
0x180036002  lea     r9, [rbp+var_38]
0x180036006  mov     qword ptr [rbp+var_18], rax
0x18003600a  mov     r8d, 3
0x180036010  mov     [rbp+var_40], esi
0x180036013  lea     rdx, PCRPF_EVENT_TRANSFORM_NOT_STAGED_V2
0x18003601a  mov     qword ptr [rbp+var_18+8], 4
0x180036022  call    cs:__imp_EtwEventWrite
0x180036029  nop     dword ptr [rax+rax+00h]
0x18003602e  test    eax, eax
0x180036030  jz      short loc_18003604C
0x180036032  mov     edx, 0C4h; void *
0x180036037  mov     rcx, [rbp+18h]; this
0x18003603b  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180036042  mov     r9d, eax; char *
0x180036045  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003604a  jmp     short loc_18003604E
0x18003604c  xor     eax, eax
0x18003604e  mov     rcx, [rbp+var_8]
0x180036052  xor     rcx, rsp; StackCookie
0x180036055  call    __security_check_cookie
0x18003605a  mov     rbx, [rsp+60h+arg_8]
0x180036062  add     rsp, 60h
0x180036066  pop     rdi
0x180036067  pop     rsi
0x180036068  pop     rbp
0x180036069  retn
```
