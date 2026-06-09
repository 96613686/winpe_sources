# GenerateRSNPTK(uchar *,uchar *,uchar *,ulong,uchar *,uchar *,ulong,NWF_PTK *,long (*)(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong))

- ea: `0x140048c58`
- end: `0x140048e01`
- name: `?GenerateRSNPTK@@YAJPEAE00K00KPEAUNWF_PTK@@P6AJ0K0K0K0K@Z@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int8 *, unsigned int, struct NWF_PTK *, int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400488e4`

## callees

- `0x140020dc0`
- `0x140041668`
- `0x140048c58`
- `0x14009a410`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048c9e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048c9e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048dcd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048dcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048dde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048dde`

## pseudocode

```c
__int64 __fastcall GenerateRSNPTK(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        struct NWF_PTK *a8,
        int (*a9)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))
{
  _DWORD *v13; // rax
  char *v14; // rdi
  unsigned __int8 *v15; // rcx
  __int16 v16; // ax
  unsigned __int8 *v17; // rcx
  unsigned __int8 *v18; // rax
  __int128 v19; // xmm1
  unsigned __int8 *v20; // rax
  int v21; // ebx
  unsigned __int8 *v23; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int8 *v24; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int8 *v26; // [rsp+68h] [rbp-10h] BYREF

  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v13 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  if ( v13 )
  {
    *(_QWORD *)v13 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v14 = (char *)(v13 + 4);
    v13[2] = 2053731191;
    CompareData(a1, a2, 6u, &v23, &v24);
    CompareData(a6, a5, 0x20u, &v25, &v26);
    v15 = v23;
    *(_DWORD *)v14 = *(_DWORD *)v23;
    v16 = *((_WORD *)v15 + 2);
    v17 = v24;
    *((_WORD *)v14 + 2) = v16;
    *(_DWORD *)(v14 + 6) = *(_DWORD *)v17;
    *((_WORD *)v14 + 5) = *((_WORD *)v17 + 2);
    v18 = v25;
    *(_OWORD *)(v14 + 12) = *(_OWORD *)v25;
    v19 = *((_OWORD *)v18 + 1);
    v20 = v26;
    *(_OWORD *)(v14 + 28) = v19;
    *(_OWORD *)(v14 + 44) = *(_OWORD *)v20;
    *(_OWORD *)(v14 + 60) = *((_OWORD *)v20 + 1);
    v21 = ((__int64 (__fastcall *)(unsigned __int8 *, _QWORD, const char *, __int64, char *, int, unsigned __int8 *, unsigned int))a9)(
            a3,
            a4,
            "Pairwise key expansion",
            22,
            v14,
            76,
            a8->PTK,
            a7 + 32);
    if ( v21 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned int)v21);
    if ( v14 )
    {
      if ( *((_QWORD *)v14 - 2) )
        ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v14 - 2), v14 - 16);
      else
        ExFreePoolWithTag(v14 - 16, *((_DWORD *)v14 - 2));
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140048c58  push    rbp
0x140048c5a  push    rbx
0x140048c5b  push    rsi
0x140048c5c  push    rdi
0x140048c5d  push    r14
0x140048c5f  push    r15
0x140048c61  mov     rbp, rsp
0x140048c64  sub     rsp, 78h
0x140048c68  mov     r15, rcx
0x140048c6b  mov     [rbp+var_28], 0
0x140048c73  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140048c7a  mov     [rbp+var_20], 0
0x140048c82  mov     rcx, rdi; Lookaside
0x140048c85  mov     [rbp+var_18], 0
0x140048c8d  mov     ebx, r9d
0x140048c90  mov     [rbp+var_10], 0
0x140048c98  mov     rsi, r8
0x140048c9b  mov     r14, rdx
0x140048c9e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140048ca5  nop     dword ptr [rax+rax+00h]
0x140048caa  test    rax, rax
0x140048cad  jz      loc_140048DEC
0x140048cb3  mov     [rax], rdi
0x140048cb6  lea     r9, [rbp+var_28]; unsigned __int8 **
0x140048cba  lea     rdi, [rax+10h]
0x140048cbe  mov     dword ptr [rax+8], 7A697377h
0x140048cc5  lea     rax, [rbp+var_20]
0x140048cc9  mov     r8d, 6; unsigned int
0x140048ccf  mov     rdx, r14; unsigned __int8 *
0x140048cd2  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x140048cd7  mov     rcx, r15; unsigned __int8 *
0x140048cda  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140048cdf  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x140048ce3  lea     r9, [rbp+var_10]
0x140048ce7  mov     rcx, [rbp+arg_28]; unsigned __int8 *
0x140048ceb  mov     r8d, 20h ; ' '; unsigned int
0x140048cf1  mov     [rsp+78h+var_58], r9; unsigned __int8 **
0x140048cf6  lea     r9, [rbp+var_18]; unsigned __int8 **
0x140048cfa  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140048cff  mov     rcx, [rbp+var_28]
0x140048d03  lea     r8, aPairwiseKeyExp; "Pairwise key expansion"
0x140048d0a  mov     r9d, 16h
0x140048d10  mov     edx, ebx
0x140048d12  mov     eax, [rcx]
0x140048d14  mov     [rdi], eax
0x140048d16  movzx   eax, word ptr [rcx+4]
0x140048d1a  mov     rcx, [rbp+var_20]
0x140048d1e  mov     [rdi+4], ax
0x140048d22  mov     eax, [rcx]
0x140048d24  mov     [rdi+6], eax
0x140048d27  movzx   eax, word ptr [rcx+4]
0x140048d2b  mov     ecx, [rbp+arg_30]
0x140048d2e  mov     [rdi+0Ah], ax
0x140048d32  add     ecx, 20h ; ' '
0x140048d35  mov     rax, [rbp+var_18]
0x140048d39  mov     [rsp+78h+var_40], ecx
0x140048d3d  mov     rcx, rsi
0x140048d40  movups  xmm0, xmmword ptr [rax]
0x140048d43  movups  xmmword ptr [rdi+0Ch], xmm0
0x140048d47  movups  xmm1, xmmword ptr [rax+10h]
0x140048d4b  mov     rax, [rbp+var_10]
0x140048d4f  movups  xmmword ptr [rdi+1Ch], xmm1
0x140048d53  movups  xmm0, xmmword ptr [rax]
0x140048d56  movups  xmmword ptr [rdi+2Ch], xmm0
0x140048d5a  movups  xmm1, xmmword ptr [rax+10h]
0x140048d5e  mov     rax, [rbp+arg_38]
0x140048d62  add     rax, 0Ch
0x140048d66  mov     [rsp+78h+var_48], rax
0x140048d6b  mov     rax, [rbp+arg_40]
0x140048d6f  mov     [rsp+78h+var_50], 4Ch ; 'L'
0x140048d77  mov     [rsp+78h+var_58], rdi
0x140048d7c  movups  xmmword ptr [rdi+3Ch], xmm1
0x140048d80  call    _guard_dispatch_icall
0x140048d85  mov     ebx, eax
0x140048d87  test    eax, eax
0x140048d89  jns     short loc_140048DB6
0x140048d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048d92  lea     rax, WPP_GLOBAL_Control
0x140048d99  cmp     rcx, rax
0x140048d9c  jz      short loc_140048DB6
0x140048d9e  mov     rcx, [rcx+18h]
0x140048da2  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140048da9  mov     edx, 1Bh
0x140048dae  mov     r9d, ebx
0x140048db1  call    WPP_SF_d
0x140048db6  test    rdi, rdi
0x140048db9  jz      short loc_140048DF1
0x140048dbb  lea     rcx, [rdi-10h]; P
0x140048dbf  mov     rax, [rcx]
0x140048dc2  test    rax, rax
0x140048dc5  jz      short loc_140048DDB
0x140048dc7  mov     rdx, rcx; Entry
0x140048dca  mov     rcx, rax; Lookaside
0x140048dcd  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048dd4  nop     dword ptr [rax+rax+00h]
0x140048dd9  jmp     short loc_140048DF1
0x140048ddb  mov     edx, [rcx+8]; Tag
0x140048dde  call    cs:__imp_ExFreePoolWithTag
0x140048de5  nop     dword ptr [rax+rax+00h]
0x140048dea  jmp     short loc_140048DF1
0x140048dec  mov     ebx, 0C000009Ah
0x140048df1  mov     eax, ebx
0x140048df3  add     rsp, 78h
0x140048df7  pop     r15
0x140048df9  pop     r14
0x140048dfb  pop     rdi
0x140048dfc  pop     rsi
0x140048dfd  pop     rbx
0x140048dfe  pop     rbp
0x140048dff  retn
```
