# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180013220`
- end: `0x180013389`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180012a90`

## callees

- `0x18000fa2c`
- `0x18001267c`
- `0x180013220`
- `0x1800136dc`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  wil::details *v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989021, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor & 4) == 0 )
    {
      v17 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
               v13,
               &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(&qword_180022358, 58599553, (v14 >> 10) & 1, (v14 >> 11) & 1, &v16, 1, 0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180013220  mov     [rsp+arg_10], rbx
0x180013225  mov     [rsp+arg_0], rcx
0x18001322a  push    rbp
0x18001322b  push    rsi
0x18001322c  push    rdi
0x18001322d  sub     rsp, 40h
0x180013231  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180013238  mov     rbx, rdx
0x18001323b  test    rax, rax
0x18001323e  jz      short loc_180013253
0x180013240  mov     edx, 3
0x180013245  mov     ecx, 38419DDh
0x18001324a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001324f  mov     edx, eax
0x180013251  jmp     short loc_180013261
0x180013253  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001325a  test    rax, rax
0x18001325d  jnz     short loc_180013240
0x18001325f  xor     edx, edx
0x180013261  mov     r8d, edx
0x180013264  mov     qword ptr [rbx], 0
0x18001326b  and     r8d, 0FFFFFF3Fh
0x180013272  mov     eax, edx
0x180013274  and     edx, 80h
0x18001327a  mov     ecx, r8d
0x18001327d  and     ecx, 3
0x180013280  mov     ebp, 40h ; '@'
0x180013285  shl     ecx, 2
0x180013288  and     eax, ebp
0x18001328a  or      ecx, eax
0x18001328c  shl     ecx, 2
0x18001328f  or      ecx, edx
0x180013291  shl     ecx, 3
0x180013294  test    r8d, r8d
0x180013297  jnz     short loc_1800132A0
0x180013299  mov     edx, ebp
0x18001329b  mov     r8d, ebp
0x18001329e  jmp     short loc_1800132AC
0x1800132a0  xor     edx, edx
0x1800132a2  cmp     r8d, 2
0x1800132a6  cmovz   edx, ebp
0x1800132a9  mov     r8d, edx
0x1800132ac  mov     eax, ecx
0x1800132ae  mov     edi, 1
0x1800132b3  or      eax, r8d
0x1800132b6  or      ecx, edx
0x1800132b8  mov     [rbx], eax
0x1800132ba  bt      ecx, 0Ah
0x1800132be  jnb     short loc_1800132CD
0x1800132c0  cmp     ecx, 800h
0x1800132c6  jb      short loc_1800132CD
0x1800132c8  mov     sil, dil
0x1800132cb  jmp     short loc_1800132DB
0x1800132cd  xor     sil, sil
0x1800132d0  xor     dl, dl
0x1800132d2  test    bpl, cl
0x1800132d5  jz      loc_180013365
0x1800132db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x1800132e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1800132e7  test    al, al
0x1800132e9  jz      short loc_180013356
0x1800132eb  mov     rax, cs:Feature_Standalone_26_03_NonSec__descriptor
0x1800132f2  mov     r8d, [rax]
0x1800132f5  test    r8b, 4
0x1800132f9  jnz     short loc_180013310
0x1800132fb  lea     rdx, [rsp+58h+arg_8]
0x180013300  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)
0x180013305  mov     rcx, [rax]
0x180013308  mov     [rsp+58h+arg_8], rcx
0x18001330d  mov     r8d, ecx
0x180013310  xor     eax, eax
0x180013312  mov     word ptr [rsp+58h+arg_0+4], 3
0x180013319  mov     r9d, r8d
0x18001331c  mov     [rsp+58h+var_28], eax
0x180013320  mov     dword ptr [rsp+58h+arg_0], eax
0x180013324  lea     rcx, qword_180022358
0x18001332b  shr     r9d, 0Bh
0x18001332f  lea     rax, [rsp+58h+arg_0]
0x180013334  shr     r8d, 0Ah
0x180013338  and     r9d, edi
0x18001333b  and     r8d, edi
0x18001333e  mov     [rsp+58h+var_30], edi
0x180013342  mov     edx, 37E2881h
0x180013347  mov     [rsp+58h+var_38], rax
0x18001334c  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013351  mov     dl, dil
0x180013354  jmp     short loc_180013358
0x180013356  xor     dl, dl
0x180013358  test    sil, sil
0x18001335b  jz      short loc_180013365
0x18001335d  test    dl, dl
0x18001335f  jnz     short loc_180013365
0x180013361  btr     dword ptr [rbx], 0Ah
0x180013365  mov     eax, [rbx]
0x180013367  test    bpl, al
0x18001336a  jz      short loc_180013370
0x18001336c  test    dl, dl
0x18001336e  jnz     short loc_180013372
0x180013370  xor     edi, edi
0x180013372  and     eax, 0FFFFFFFEh
0x180013375  or      eax, edi
0x180013377  mov     [rbx], eax
0x180013379  mov     rax, rbx
0x18001337c  mov     rbx, [rsp+58h+arg_10]
0x180013381  add     rsp, 40h
0x180013385  pop     rdi
0x180013386  pop     rsi
0x180013387  pop     rbp
0x180013388  retn
```
