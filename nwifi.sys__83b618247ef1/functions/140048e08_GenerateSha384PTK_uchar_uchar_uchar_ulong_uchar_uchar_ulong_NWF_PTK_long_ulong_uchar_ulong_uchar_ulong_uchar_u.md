# GenerateSha384PTK(uchar *,uchar *,uchar *,ulong,uchar *,uchar *,ulong,NWF_PTK *,long (*)(ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *))

- ea: `0x140048e08`
- end: `0x140048fad`
- name: `?GenerateSha384PTK@@YAJPEAE00K00KPEAUNWF_PTK@@P6AJK0K0K0K0@Z@Z`
- size: `421`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int8 *, unsigned int, struct NWF_PTK *, int (*)(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400488e4`

## callees

- `0x140020dc0`
- `0x140041668`
- `0x140048e08`
- `0x14008e004`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048e4e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140048e4e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f79`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048f79`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048f8a`

## pseudocode

```c
__int64 __fastcall GenerateSha384PTK(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned __int8 *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        struct NWF_PTK *a8,
        int (*a9)(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))
{
  int v11; // esi
  _DWORD *v13; // rax
  __int64 v14; // rdi
  int (*v15)(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *); // rcx
  __int16 v16; // ax
  unsigned __int8 *v17; // rcx
  unsigned __int8 *v18; // rax
  __int128 v19; // xmm1
  unsigned __int8 *v20; // rax
  int v21; // ebx
  unsigned __int8 *v23; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int8 *v24; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int8 *v25; // [rsp+50h] [rbp-18h] BYREF

  a9 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v11 = (int)a3;
  v13 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  if ( v13 )
  {
    *(_QWORD *)v13 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    v14 = (__int64)(v13 + 4);
    v13[2] = 2053731191;
    CompareData(a1, a2, 6u, (unsigned __int8 **)&a9, &v23);
    CompareData(a6, a5, 0x20u, &v24, &v25);
    v15 = a9;
    *(_DWORD *)v14 = *(_DWORD *)a9;
    v16 = *((_WORD *)v15 + 2);
    v17 = v23;
    *(_WORD *)(v14 + 4) = v16;
    *(_DWORD *)(v14 + 6) = *(_DWORD *)v17;
    *(_WORD *)(v14 + 10) = *((_WORD *)v17 + 2);
    v18 = v24;
    *(_OWORD *)(v14 + 12) = *(_OWORD *)v24;
    v19 = *((_OWORD *)v18 + 1);
    v20 = v25;
    *(_OWORD *)(v14 + 28) = v19;
    *(_OWORD *)(v14 + 44) = *(_OWORD *)v20;
    *(_OWORD *)(v14 + 60) = *((_OWORD *)v20 + 1);
    v21 = SSN_SHA384_PRF(a4, v11, 22, (unsigned int)"Pairwise key expansion", 76, v14, a7 + 56, (__int64)a8->PTK);
    if ( v21 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_e90d411d816e312466897e39e745b158_Traceguids,
        (unsigned int)v21);
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v14 - 16), (PVOID)(v14 - 16));
      else
        ExFreePoolWithTag((PVOID)(v14 - 16), *(_DWORD *)(v14 - 16 + 8));
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
0x140048e08  push    rbp
0x140048e0a  push    rbx
0x140048e0b  push    rsi
0x140048e0c  push    rdi
0x140048e0d  push    r14
0x140048e0f  push    r15
0x140048e11  mov     rbp, rsp
0x140048e14  sub     rsp, 68h
0x140048e18  mov     r15, rcx
0x140048e1b  mov     [rbp+arg_40], 0
0x140048e23  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140048e2a  mov     [rbp+var_28], 0
0x140048e32  mov     rcx, rdi; Lookaside
0x140048e35  mov     [rbp+var_20], 0
0x140048e3d  mov     ebx, r9d
0x140048e40  mov     [rbp+var_18], 0
0x140048e48  mov     rsi, r8
0x140048e4b  mov     r14, rdx
0x140048e4e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140048e55  nop     dword ptr [rax+rax+00h]
0x140048e5a  test    rax, rax
0x140048e5d  jz      loc_140048F98
0x140048e63  mov     [rax], rdi
0x140048e66  lea     r9, [rbp+arg_40]; unsigned __int8 **
0x140048e6a  lea     rdi, [rax+10h]
0x140048e6e  mov     dword ptr [rax+8], 7A697377h
0x140048e75  lea     rax, [rbp+var_28]
0x140048e79  mov     r8d, 6; unsigned int
0x140048e7f  mov     rdx, r14; unsigned __int8 *
0x140048e82  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x140048e87  mov     rcx, r15; unsigned __int8 *
0x140048e8a  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140048e8f  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x140048e93  lea     r9, [rbp+var_18]
0x140048e97  mov     rcx, [rbp+arg_28]; unsigned __int8 *
0x140048e9b  mov     r8d, 20h ; ' '; unsigned int
0x140048ea1  mov     [rsp+68h+var_48], r9; unsigned __int8 **
0x140048ea6  lea     r9, [rbp+var_20]; unsigned __int8 **
0x140048eaa  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x140048eaf  mov     rcx, [rbp+arg_40]
0x140048eb3  lea     r9, aPairwiseKeyExp; "Pairwise key expansion"
0x140048eba  mov     r8d, 16h
0x140048ec0  mov     rdx, rsi
0x140048ec3  mov     eax, [rcx]
0x140048ec5  mov     [rdi], eax
0x140048ec7  movzx   eax, word ptr [rcx+4]
0x140048ecb  mov     rcx, [rbp+var_28]
0x140048ecf  mov     [rdi+4], ax
0x140048ed3  mov     eax, [rcx]
0x140048ed5  mov     [rdi+6], eax
0x140048ed8  movzx   eax, word ptr [rcx+4]
0x140048edc  mov     rcx, [rbp+arg_38]
0x140048ee0  mov     [rdi+0Ah], ax
0x140048ee4  add     rcx, 0Ch
0x140048ee8  mov     rax, [rbp+var_20]
0x140048eec  mov     [rsp+68h+var_30], rcx
0x140048ef1  mov     ecx, ebx
0x140048ef3  movups  xmm0, xmmword ptr [rax]
0x140048ef6  movups  xmmword ptr [rdi+0Ch], xmm0
0x140048efa  movups  xmm1, xmmword ptr [rax+10h]
0x140048efe  mov     rax, [rbp+var_18]
0x140048f02  movups  xmmword ptr [rdi+1Ch], xmm1
0x140048f06  movups  xmm0, xmmword ptr [rax]
0x140048f09  movups  xmmword ptr [rdi+2Ch], xmm0
0x140048f0d  movups  xmm1, xmmword ptr [rax+10h]
0x140048f11  mov     eax, [rbp+arg_30]
0x140048f14  add     eax, 38h ; '8'
0x140048f17  mov     [rsp+68h+var_38], eax
0x140048f1b  mov     [rsp+68h+var_40], rdi
0x140048f20  mov     dword ptr [rsp+68h+var_48], 4Ch ; 'L'
0x140048f28  movups  xmmword ptr [rdi+3Ch], xmm1
0x140048f2c  call    SSN_SHA384_PRF
0x140048f31  mov     ebx, eax
0x140048f33  test    eax, eax
0x140048f35  jns     short loc_140048F62
0x140048f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140048f3e  lea     rax, WPP_GLOBAL_Control
0x140048f45  cmp     rcx, rax
0x140048f48  jz      short loc_140048F62
0x140048f4a  mov     rcx, [rcx+18h]
0x140048f4e  lea     r8, WPP_e90d411d816e312466897e39e745b158_Traceguids
0x140048f55  mov     edx, 1Ch
0x140048f5a  mov     r9d, ebx
0x140048f5d  call    WPP_SF_d
0x140048f62  test    rdi, rdi
0x140048f65  jz      short loc_140048F9D
0x140048f67  lea     rcx, [rdi-10h]; P
0x140048f6b  mov     rax, [rcx]
0x140048f6e  test    rax, rax
0x140048f71  jz      short loc_140048F87
0x140048f73  mov     rdx, rcx; Entry
0x140048f76  mov     rcx, rax; Lookaside
0x140048f79  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048f80  nop     dword ptr [rax+rax+00h]
0x140048f85  jmp     short loc_140048F9D
0x140048f87  mov     edx, [rcx+8]; Tag
0x140048f8a  call    cs:__imp_ExFreePoolWithTag
0x140048f91  nop     dword ptr [rax+rax+00h]
0x140048f96  jmp     short loc_140048F9D
0x140048f98  mov     ebx, 0C000009Ah
0x140048f9d  mov     eax, ebx
0x140048f9f  add     rsp, 68h
0x140048fa3  pop     r15
0x140048fa5  pop     r14
0x140048fa7  pop     rdi
0x140048fa8  pop     rsi
0x140048fa9  pop     rbx
0x140048faa  pop     rbp
0x140048fab  retn
```
