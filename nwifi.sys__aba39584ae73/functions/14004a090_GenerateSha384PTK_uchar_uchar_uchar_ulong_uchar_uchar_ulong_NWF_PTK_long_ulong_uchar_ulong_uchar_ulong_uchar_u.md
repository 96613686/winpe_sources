# GenerateSha384PTK(uchar *,uchar *,uchar *,ulong,uchar *,uchar *,ulong,NWF_PTK *,long (*)(ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *))

- ea: `0x14004a090`
- end: `0x14004a235`
- name: `?GenerateSha384PTK@@YAJPEAE00K00KPEAUNWF_PTK@@P6AJK0K0K0K0@Z@Z`
- size: `421`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned __int8 *@<rdx>, unsigned __int8 *@<r8>, unsigned int@<r9d>, unsigned __int8 *, unsigned __int8 *, unsigned int, struct NWF_PTK *, int (*)(unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140049b6c`

## callees

- `0x140020dc0`
- `0x140042104`
- `0x14004a090`
- `0x14008f834`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a0d6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14004a0d6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a201`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14004a201`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a212`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a212`

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
        WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids,
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
0x14004a090  push    rbp
0x14004a092  push    rbx
0x14004a093  push    rsi
0x14004a094  push    rdi
0x14004a095  push    r14
0x14004a097  push    r15
0x14004a099  mov     rbp, rsp
0x14004a09c  sub     rsp, 68h
0x14004a0a0  mov     r15, rcx
0x14004a0a3  mov     [rbp+arg_40], 0
0x14004a0ab  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14004a0b2  mov     [rbp+var_28], 0
0x14004a0ba  mov     rcx, rdi; Lookaside
0x14004a0bd  mov     [rbp+var_20], 0
0x14004a0c5  mov     ebx, r9d
0x14004a0c8  mov     [rbp+var_18], 0
0x14004a0d0  mov     rsi, r8
0x14004a0d3  mov     r14, rdx
0x14004a0d6  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14004a0dd  nop     dword ptr [rax+rax+00h]
0x14004a0e2  test    rax, rax
0x14004a0e5  jz      loc_14004A220
0x14004a0eb  mov     [rax], rdi
0x14004a0ee  lea     r9, [rbp+arg_40]; unsigned __int8 **
0x14004a0f2  lea     rdi, [rax+10h]
0x14004a0f6  mov     dword ptr [rax+8], 7A697377h
0x14004a0fd  lea     rax, [rbp+var_28]
0x14004a101  mov     r8d, 6; unsigned int
0x14004a107  mov     rdx, r14; unsigned __int8 *
0x14004a10a  mov     [rsp+68h+var_48], rax; unsigned __int8 **
0x14004a10f  mov     rcx, r15; unsigned __int8 *
0x14004a112  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x14004a117  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x14004a11b  lea     r9, [rbp+var_18]
0x14004a11f  mov     rcx, [rbp+arg_28]; unsigned __int8 *
0x14004a123  mov     r8d, 20h ; ' '; unsigned int
0x14004a129  mov     [rsp+68h+var_48], r9; unsigned __int8 **
0x14004a12e  lea     r9, [rbp+var_20]; unsigned __int8 **
0x14004a132  call    ?CompareData@@YAXPEAE0KPEAPEAE1@Z; CompareData(uchar *,uchar *,ulong,uchar * *,uchar * *)
0x14004a137  mov     rcx, [rbp+arg_40]
0x14004a13b  lea     r9, aPairwiseKeyExp; "Pairwise key expansion"
0x14004a142  mov     r8d, 16h
0x14004a148  mov     rdx, rsi
0x14004a14b  mov     eax, [rcx]
0x14004a14d  mov     [rdi], eax
0x14004a14f  movzx   eax, word ptr [rcx+4]
0x14004a153  mov     rcx, [rbp+var_28]
0x14004a157  mov     [rdi+4], ax
0x14004a15b  mov     eax, [rcx]
0x14004a15d  mov     [rdi+6], eax
0x14004a160  movzx   eax, word ptr [rcx+4]
0x14004a164  mov     rcx, [rbp+arg_38]
0x14004a168  mov     [rdi+0Ah], ax
0x14004a16c  add     rcx, 0Ch
0x14004a170  mov     rax, [rbp+var_20]
0x14004a174  mov     [rsp+68h+var_30], rcx
0x14004a179  mov     ecx, ebx
0x14004a17b  movups  xmm0, xmmword ptr [rax]
0x14004a17e  movups  xmmword ptr [rdi+0Ch], xmm0
0x14004a182  movups  xmm1, xmmword ptr [rax+10h]
0x14004a186  mov     rax, [rbp+var_18]
0x14004a18a  movups  xmmword ptr [rdi+1Ch], xmm1
0x14004a18e  movups  xmm0, xmmword ptr [rax]
0x14004a191  movups  xmmword ptr [rdi+2Ch], xmm0
0x14004a195  movups  xmm1, xmmword ptr [rax+10h]
0x14004a199  mov     eax, [rbp+arg_30]
0x14004a19c  add     eax, 38h ; '8'
0x14004a19f  mov     [rsp+68h+var_38], eax
0x14004a1a3  mov     [rsp+68h+var_40], rdi
0x14004a1a8  mov     dword ptr [rsp+68h+var_48], 4Ch ; 'L'
0x14004a1b0  movups  xmmword ptr [rdi+3Ch], xmm1
0x14004a1b4  call    SSN_SHA384_PRF
0x14004a1b9  mov     ebx, eax
0x14004a1bb  test    eax, eax
0x14004a1bd  jns     short loc_14004A1EA
0x14004a1bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a1c6  lea     rax, WPP_GLOBAL_Control
0x14004a1cd  cmp     rcx, rax
0x14004a1d0  jz      short loc_14004A1EA
0x14004a1d2  mov     rcx, [rcx+18h]
0x14004a1d6  lea     r8, WPP_f1f84e776f9f353cdff81b8bd8546bbf_Traceguids
0x14004a1dd  mov     edx, 1Ch
0x14004a1e2  mov     r9d, ebx
0x14004a1e5  call    WPP_SF_d
0x14004a1ea  test    rdi, rdi
0x14004a1ed  jz      short loc_14004A225
0x14004a1ef  lea     rcx, [rdi-10h]; P
0x14004a1f3  mov     rax, [rcx]
0x14004a1f6  test    rax, rax
0x14004a1f9  jz      short loc_14004A20F
0x14004a1fb  mov     rdx, rcx; Entry
0x14004a1fe  mov     rcx, rax; Lookaside
0x14004a201  call    cs:__imp_ExFreeToNPagedLookasideList
0x14004a208  nop     dword ptr [rax+rax+00h]
0x14004a20d  jmp     short loc_14004A225
0x14004a20f  mov     edx, [rcx+8]; Tag
0x14004a212  call    cs:__imp_ExFreePoolWithTag
0x14004a219  nop     dword ptr [rax+rax+00h]
0x14004a21e  jmp     short loc_14004A225
0x14004a220  mov     ebx, 0C000009Ah
0x14004a225  mov     eax, ebx
0x14004a227  add     rsp, 68h
0x14004a22b  pop     r15
0x14004a22d  pop     r14
0x14004a22f  pop     rdi
0x14004a230  pop     rsi
0x14004a231  pop     rbx
0x14004a232  pop     rbp
0x14004a233  retn
```
