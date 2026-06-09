# GenerateRSNPTK(uchar *,uchar *,uchar *,ulong,uchar *,uchar *,ulong,NWF_PTK *,long (*)(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong))

- ea: `0x140049ee0`
- end: `0x14004a089`
- name: `?GenerateRSNPTK@@YAJPEAE00K00KPEAUNWF_PTK@@P6AJ0K0K0K0K@Z@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int8 *, unsigned int, struct NWF_PTK *, int (*)(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int))`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140049b6c`

## callees

- `0x140020dc0`
- `0x140042104`
- `0x140049ee0`
- `0x14009bbf0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140049f26`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140049f26`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a055`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a055`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a066`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a066`

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
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
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
0x140049ee0  push    rbp
0x140049ee2  push    rbx
0x140049ee3  push    rsi
0x140049ee4  push    rdi
0x140049ee5  push    r14
0x140049ee7  push    r15
0x140049ee9  mov     rbp, rsp
0x140049eec  sub     rsp, 78h
0x140049ef0  mov     r15, rcx
0x140049ef3  mov     [rbp+var_28], 0
0x140049efb  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140049f02  mov     [rbp+var_20], 0
0x140049f0a  mov     rcx, rdi; Lookaside
0x140049f0d  mov     [rbp+var_18], 0
0x140049f15  mov     ebx, r9d
0x140049f18  mov     [rbp+var_10], 0
0x140049f20  mov     rsi, r8
0x140049f23  mov     r14, rdx
0x140049f26  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140049f2d  nop     dword ptr [rax+rax+00h]
0x140049f32  test    rax, rax
0x140049f35  jz      loc_14004A074
0x140049f3b  mov     [rax], rdi
0x140049f3e  lea     r9, [rbp+var_28]; unsigned __int8 **
0x140049f42  lea     rdi, [rax+10h]
0x140049f46  mov     dword ptr [rax+8], 7A697377h
0x140049f4d  lea     rax, [rbp+var_20]
0x140049f51  mov     r8d, 6; unsigned int
0x140049f57  mov     rdx, r14; unsigned __int8 *
0x140049f5a  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x140049f5f  mov     rcx, r15; unsigned __int8 *
0x140049f62  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140049f67  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x140049f6b  lea     r9, [rbp+var_10]
0x140049f6f  mov     rcx, [rbp+arg_28]; unsigned __int8 *
0x140049f73  mov     r8d, 20h ; ' '; unsigned int
0x140049f79  mov     [rsp+78h+var_58], r9; unsigned __int8 **
0x140049f7e  lea     r9, [rbp+var_18]; unsigned __int8 **
0x140049f82  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140049f87  mov     rcx, [rbp+var_28]
0x140049f8b  lea     r8, aPairwiseKeyExp; "Pairwise key expansion"
0x140049f92  mov     r9d, 16h
0x140049f98  mov     edx, ebx
0x140049f9a  mov     eax, [rcx]
0x140049f9c  mov     [rdi], eax
0x140049f9e  movzx   eax, word ptr [rcx+4]
0x140049fa2  mov     rcx, [rbp+var_20]
0x140049fa6  mov     [rdi+4], ax
0x140049faa  mov     eax, [rcx]
0x140049fac  mov     [rdi+6], eax
0x140049faf  movzx   eax, word ptr [rcx+4]
0x140049fb3  mov     ecx, [rbp+arg_30]
0x140049fb6  mov     [rdi+0Ah], ax
0x140049fba  add     ecx, 20h ; ' '
0x140049fbd  mov     rax, [rbp+var_18]
0x140049fc1  mov     [rsp+78h+var_40], ecx
0x140049fc5  mov     rcx, rsi
0x140049fc8  movups  xmm0, xmmword ptr [rax]
0x140049fcb  movups  xmmword ptr [rdi+0Ch], xmm0
0x140049fcf  movups  xmm1, xmmword ptr [rax+10h]
0x140049fd3  mov     rax, [rbp+var_10]
0x140049fd7  movups  xmmword ptr [rdi+1Ch], xmm1
0x140049fdb  movups  xmm0, xmmword ptr [rax]
0x140049fde  movups  xmmword ptr [rdi+2Ch], xmm0
0x140049fe2  movups  xmm1, xmmword ptr [rax+10h]
0x140049fe6  mov     rax, [rbp+arg_38]
0x140049fea  add     rax, 0Ch
0x140049fee  mov     [rsp+78h+var_48], rax
0x140049ff3  mov     rax, [rbp+arg_40]
0x140049ff7  mov     [rsp+78h+var_50], 4Ch ; 'L'
0x140049fff  mov     [rsp+78h+var_58], rdi
0x14004a004  movups  xmmword ptr [rdi+3Ch], xmm1
0x14004a008  call    _guard_dispatch_icall
0x14004a00d  mov     ebx, eax
0x14004a00f  test    eax, eax
0x14004a011  jns     short loc_14004A03E
0x14004a013  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a01a  lea     rax, WPP_GLOBAL_Control
0x14004a021  cmp     rcx, rax
0x14004a024  jz      short loc_14004A03E
0x14004a026  mov     rcx, [rcx+18h]
0x14004a02a  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004a031  mov     edx, 1Bh
0x14004a036  mov     r9d, ebx
0x14004a039  call    WPP_SF_d
0x14004a03e  test    rdi, rdi
0x14004a041  jz      short loc_14004A079
0x14004a043  lea     rcx, [rdi-10h]; P
0x14004a047  mov     rax, [rcx]
0x14004a04a  test    rax, rax
0x14004a04d  jz      short loc_14004A063
0x14004a04f  mov     rdx, rcx; Entry
0x14004a052  mov     rcx, rax; Lookaside
0x14004a055  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004a05c  nop     dword ptr [rax+rax+00h]
0x14004a061  jmp     short loc_14004A079
0x14004a063  mov     edx, [rcx+8]; Tag
0x14004a066  call    cs:__imp_ExFreePoolWithTag
0x14004a06d  nop     dword ptr [rax+rax+00h]
0x14004a072  jmp     short loc_14004A079
0x14004a074  mov     ebx, 0C000009Ah
0x14004a079  mov     eax, ebx
0x14004a07b  add     rsp, 78h
0x14004a07f  pop     r15
0x14004a081  pop     r14
0x14004a083  pop     rdi
0x14004a084  pop     rsi
0x14004a085  pop     rbx
0x14004a086  pop     rbp
0x14004a087  retn
```
