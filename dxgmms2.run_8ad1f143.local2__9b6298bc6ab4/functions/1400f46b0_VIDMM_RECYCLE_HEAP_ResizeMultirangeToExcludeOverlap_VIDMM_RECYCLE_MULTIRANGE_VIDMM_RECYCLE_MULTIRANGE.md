# VIDMM_RECYCLE_HEAP::ResizeMultirangeToExcludeOverlap(VIDMM_RECYCLE_MULTIRANGE *,VIDMM_RECYCLE_MULTIRANGE *)

- ea: `0x1400f46b0`
- end: `0x1400f4caa`
- name: `?ResizeMultirangeToExcludeOverlap@VIDMM_RECYCLE_HEAP@@AEAAXPEAVVIDMM_RECYCLE_MULTIRANGE@@0@Z`
- size: `1530`
- prototype: `void(VIDMM_RECYCLE_HEAP *__hidden this, struct VIDMM_RECYCLE_MULTIRANGE *, struct VIDMM_RECYCLE_MULTIRANGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400f66b8`

## callees

- `0x1400f46b0`
- `0x1400f5950`
- `0x1400f598c`
- `0x1400f5a58`
- `0x1400f5be0`
- `0x1400f5ca0`
- `0x1400f5eec`

## import_xrefs

- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f4868`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f4868`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f472a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f472a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f4abc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f4abc`
- `watchdog!WdLogSingleEntry2` at `0x1400f46f0`
- `watchdog!WdLogSingleEntry2` at `0x1400f47cf`
- `watchdog!WdLogSingleEntry2` at `0x1400f46f0`
- `watchdog!WdLogSingleEntry2` at `0x1400f47cf`
- `watchdog!WdLogSingleEntry5` at `0x1400f4c1d`
- `watchdog!WdLogSingleEntry5` at `0x1400f4c59`
- `watchdog!WdLogSingleEntry5` at `0x1400f4c1d`
- `watchdog!WdLogSingleEntry5` at `0x1400f4c59`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f4bf3`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f4c33`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void __fastcall VIDMM_RECYCLE_HEAP::ResizeMultirangeToExcludeOverlap(
        VIDMM_RECYCLE_HEAP *this,
        struct VIDMM_RECYCLE_MULTIRANGE *a2,
        struct VIDMM_RECYCLE_MULTIRANGE *a3)
{
  struct VIDMM_RECYCLE_MULTIRANGE *v3; // rsi
  unsigned __int64 v4; // r13
  struct VIDMM_RECYCLE_MULTIRANGE *v5; // rbx
  unsigned __int64 v6; // rdi
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // r12
  struct VIDMM_RECYCLE_MULTIRANGE *v10; // r15
  char *v11; // rcx
  struct VIDMM_RECYCLE_MULTIRANGE *v12; // r8
  unsigned __int64 v13; // r10
  struct VIDMM_RECYCLE_MULTIRANGE *v14; // r11
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // r8
  __int64 v20; // rax
  struct _RTL_BALANCED_NODE *v21; // rsi
  char v22; // di
  struct _RTL_BALANCED_NODE *v23; // rax
  char *v24; // rcx
  unsigned __int64 v25; // r9
  struct VIDMM_RECYCLE_MULTIRANGE *v26; // r11
  unsigned __int64 v27; // r10
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // edx
  int v31; // ecx
  int v32; // ecx
  __int64 v33; // rdx
  __int64 v34; // rcx
  struct _RTL_BALANCED_NODE *v35; // rax
  struct _RTL_BALANCED_NODE *v36; // rax
  int v37; // edx
  __int64 v38; // rsi
  __int64 v39; // rax
  __int64 v40; // rdx
  struct VIDMM_RECYCLE_MULTIRANGE *Multirange; // rax
  int v42; // edx
  __int64 v43; // rax
  __int64 v44; // r13
  unsigned __int64 v45; // r10
  __int64 v46; // rdx
  unsigned __int64 v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rcx
  int v50; // edx
  int v51; // edx
  int v52; // ecx
  int v53; // ecx
  __int64 i; // rdx
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD v57[2]; // [rsp+30h] [rbp-68h] BYREF
  char v58; // [rsp+40h] [rbp-58h]
  unsigned int v59; // [rsp+A8h] [rbp+10h]

  v3 = a3;
  v4 = *((_QWORD *)a2 + 4);
  v5 = a2;
  v6 = *((_QWORD *)a2 + 5);
  v8 = *((_QWORD *)a3 + 4);
  v9 = *((_QWORD *)a3 + 5);
  v59 = *((_DWORD *)a2 + 22);
  v10 = (struct VIDMM_RECYCLE_MULTIRANGE *)(int)v59;
  WdLogSingleEntry2(4, a2, (int)v59);
  WdLogGlobalForLineNumber = 8471;
  if ( v59 )
  {
    if ( v59 == 1 )
    {
      v11 = (char *)this + 56;
    }
    else
    {
      if ( v59 != 2 )
      {
        g_DxgMmsBugcheckExportIndex = 1;
        WdLogSingleEntry5(0, 270, 52);
        WdLogGlobalForLineNumber = 222;
        goto LABEL_115;
      }
      v11 = (char *)this + 64;
    }
  }
  else
  {
    v11 = (char *)this + 48;
  }
  RtlAvlRemoveNode(v11, v5);
  v12 = (struct VIDMM_RECYCLE_MULTIRANGE *)*((_QWORD *)v5 + 8);
  *((_DWORD *)v5 + 22) = 3;
  if ( v8 > v4 )
  {
    if ( v9 < v6 )
    {
      v43 = *((_QWORD *)v3 + 9);
      v44 = *((_QWORD *)v5 + 5);
      v3 = 0;
      v10 = (struct VIDMM_RECYCLE_MULTIRANGE *)*((_QWORD *)v5 + 9);
      v45 = *((_QWORD *)v5 + 4);
      v46 = *(_QWORD *)(v43 + 120);
      if ( v46 != *(_QWORD *)(v43 + 72) + 72LL )
        v3 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v46 - 120);
      while ( 1 )
      {
        v47 = *((_QWORD *)v12 + 4);
        if ( v47 >= v8 || *((_QWORD *)v12 + 5) <= v45 )
        {
          v50 = *((_DWORD *)v5 + 36);
          if ( v50 )
          {
            v51 = v50 - 1;
            if ( v51 )
            {
              if ( v51 == 1 )
                *((_QWORD *)v12 + 19) = 0;
            }
            else
            {
              *((_QWORD *)v12 + 18) = 0;
            }
          }
          else
          {
            *((_QWORD *)v12 + 17) = 0;
          }
        }
        if ( v47 == v45 )
          *((_QWORD *)v5 + 8) = v12;
        if ( *((_QWORD *)v12 + 5) == v8 )
          *((_QWORD *)v5 + 9) = v12;
        if ( v12 == v10 )
          break;
        v48 = *((_QWORD *)v12 + 15);
        v49 = *((_QWORD *)v12 + 9);
        v12 = 0;
        if ( v48 != v49 + 72 )
          v12 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v48 - 120);
      }
      *((_QWORD *)v5 + 4) = v45;
      *((_QWORD *)v5 + 5) = v8;
      *((_QWORD *)v5 + 6) = v45;
      VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v59, v5);
      Multirange = (struct VIDMM_RECYCLE_MULTIRANGE *)VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(
                                                        *((_QWORD *)this + 1),
                                                        *((unsigned int *)v5 + 36),
                                                        *((_QWORD *)v5 + 10),
                                                        v9,
                                                        v44);
      v5 = Multirange;
      if ( !Multirange )
      {
        LODWORD(v6) = 1;
        goto LABEL_104;
      }
      *((_QWORD *)Multirange + 8) = v3;
      *((_QWORD *)Multirange + 9) = v10;
      VIDMM_RECYCLE_MULTIRANGE::MarkAllRangesWithNewOwner(Multirange);
      v40 = v59;
    }
    else
    {
      v25 = *((_QWORD *)v5 + 4);
      v26 = (struct VIDMM_RECYCLE_MULTIRANGE *)*((_QWORD *)v5 + 9);
      while ( 1 )
      {
        v27 = *((_QWORD *)v12 + 4);
        if ( v27 >= v8 || *((_QWORD *)v12 + 5) <= v25 )
        {
          v37 = *((_DWORD *)v5 + 36);
          if ( v37 )
          {
            v42 = v37 - 1;
            if ( v42 )
            {
              if ( v42 == 1 )
                *((_QWORD *)v12 + 19) = 0;
            }
            else
            {
              *((_QWORD *)v12 + 18) = 0;
            }
          }
          else
          {
            *((_QWORD *)v12 + 17) = 0;
          }
        }
        if ( v27 == v25 )
          *((_QWORD *)v5 + 8) = v12;
        if ( *((_QWORD *)v12 + 5) == v8 )
          *((_QWORD *)v5 + 9) = v12;
        if ( v12 == v26 )
          break;
        v28 = *((_QWORD *)v12 + 15);
        v29 = *((_QWORD *)v12 + 9);
        v12 = 0;
        if ( v28 != v29 + 72 )
          v12 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v28 - 120);
      }
      *((_QWORD *)v5 + 4) = v25;
      v40 = v59;
      *((_QWORD *)v5 + 5) = v8;
      *((_QWORD *)v5 + 6) = v25;
    }
    VIDMM_RECYCLE_HEAP::AddMultirangeToTree(this, v40, v5);
    return;
  }
  if ( v9 >= v6 )
  {
    while ( 1 )
    {
      v31 = *((_DWORD *)v5 + 36);
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          if ( v32 == 1 )
            *((_QWORD *)v12 + 19) = 0;
        }
        else
        {
          *((_QWORD *)v12 + 18) = 0;
        }
      }
      else
      {
        *((_QWORD *)v12 + 17) = 0;
      }
      if ( v12 == *((struct VIDMM_RECYCLE_MULTIRANGE **)v5 + 9) )
        break;
      v33 = *((_QWORD *)v12 + 15);
      v34 = *((_QWORD *)v12 + 9);
      v12 = 0;
      if ( v33 != v34 + 72 )
        v12 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v33 - 120);
    }
    v38 = *((_QWORD *)this + 1);
    VIDMM_RECYCLE_MULTIRANGE::Destroy(v5);
    v39 = *(unsigned int *)(v38 + 1620);
    if ( (unsigned int)v39 >= 4 )
    {
      ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(v38 + 1320), v5);
    }
    else
    {
      *(_QWORD *)(v38 + 8 * v39 + 1656) = v5;
      ++*(_DWORD *)(v38 + 1620);
    }
    --*(_DWORD *)(v38 + 1688);
    return;
  }
  v13 = *((_QWORD *)v5 + 5);
  v14 = (struct VIDMM_RECYCLE_MULTIRANGE *)*((_QWORD *)v5 + 9);
  while ( 1 )
  {
    v15 = *((_QWORD *)v12 + 4);
    if ( v15 >= v13 || *((_QWORD *)v12 + 5) <= v9 )
    {
      v18 = *((_DWORD *)v5 + 36);
      if ( v18 )
      {
        v30 = v18 - 1;
        if ( v30 )
        {
          if ( v30 == 1 )
            *((_QWORD *)v12 + 19) = 0;
        }
        else
        {
          *((_QWORD *)v12 + 18) = 0;
        }
      }
      else
      {
        *((_QWORD *)v12 + 17) = 0;
      }
    }
    if ( v15 == v9 )
      *((_QWORD *)v5 + 8) = v12;
    if ( *((_QWORD *)v12 + 5) == v13 )
      *((_QWORD *)v5 + 9) = v12;
    if ( v12 == v14 )
      break;
    v16 = *((_QWORD *)v12 + 15);
    v17 = *((_QWORD *)v12 + 9);
    v12 = 0;
    if ( v16 != v17 + 72 )
      v12 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v16 - 120);
  }
  *((_QWORD *)v5 + 4) = v9;
  *((_QWORD *)v5 + 5) = v13;
  *((_QWORD *)v5 + 6) = v9;
  WdLogSingleEntry2(4, v5, (int)v59);
  WdLogGlobalForLineNumber = 8421;
  v20 = *((_QWORD *)v5 + 7);
  v57[0] = *((_QWORD *)v5 + 5) - *((_QWORD *)v5 + 4);
  v57[1] = v20;
  v58 = 0;
  if ( !v59 )
  {
    v21 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)this + 6);
    v22 = 0;
    if ( v21 )
    {
      while ( 1 )
      {
        if ( (int)VidMmCompareForInsertAlignedRange(v57, v21) < 0 )
        {
          v35 = v21->Children[0];
          if ( !v21->Children[0] )
            break;
        }
        else
        {
          v35 = v21->Children[1];
          if ( !v35 )
          {
            v22 = 1;
            break;
          }
        }
        v21 = v35;
      }
    }
    v24 = (char *)this + 48;
    goto LABEL_31;
  }
  if ( v59 == 1 )
  {
    v21 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)this + 7);
    v22 = 0;
    if ( v21 )
    {
      while ( 1 )
      {
        if ( (int)VidMmCompareForInsertAlignedRange(v57, v21) < 0 )
        {
          v36 = v21->Children[0];
          if ( !v21->Children[0] )
            break;
        }
        else
        {
          v36 = v21->Children[1];
          if ( !v36 )
          {
            v22 = 1;
            break;
          }
        }
        v21 = v36;
      }
    }
    v24 = (char *)this + 56;
    goto LABEL_31;
  }
  if ( v59 != 2 )
  {
LABEL_115:
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
LABEL_116:
    for ( i = 0; ; i = 2 )
    {
LABEL_118:
      VIDMM_RECYCLE_HEAP::AddRangeToTree(this, i, v3);
      while ( 1 )
      {
        if ( v3 == v10 )
          return;
        v55 = *((_QWORD *)v3 + 15);
        v56 = *((_QWORD *)v3 + 9);
        v3 = 0;
        if ( v55 != v56 + 72 )
          v3 = (struct VIDMM_RECYCLE_MULTIRANGE *)(v55 - 120);
LABEL_104:
        v52 = *((_DWORD *)v3 + 16);
        if ( !v52 )
          break;
        v53 = v52 - 4;
        if ( !v53 )
          goto LABEL_116;
        if ( v53 == (_DWORD)v6 )
        {
          i = (unsigned int)v6;
          goto LABEL_118;
        }
      }
    }
  }
  v21 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)this + 8);
  v22 = 0;
  if ( !v21 )
    goto LABEL_30;
  while ( (int)VidMmCompareForInsertAlignedRange(v57, v21) < 0 )
  {
    v23 = v21->Children[0];
    if ( !v21->Children[0] )
      goto LABEL_30;
LABEL_26:
    v21 = v23;
  }
  v23 = v21->Children[1];
  if ( v23 )
    goto LABEL_26;
  v22 = 1;
LABEL_30:
  v24 = (char *)this + 64;
LABEL_31:
  LOBYTE(v19) = v22;
  RtlAvlInsertNodeEx(v24, v21, v19, v5);
  *((_DWORD *)v5 + 22) = v59;
}

```

## disassembly

```asm
0x1400f46b0  push    rbx
0x1400f46b2  push    rbp
0x1400f46b3  push    rsi
0x1400f46b4  push    rdi
0x1400f46b5  push    r12
0x1400f46b7  push    r13
0x1400f46b9  push    r14
0x1400f46bb  push    r15
0x1400f46bd  sub     rsp, 58h
0x1400f46c1  movsxd  rax, dword ptr [rdx+58h]
0x1400f46c5  mov     rsi, r8
0x1400f46c8  mov     r13, [rdx+20h]
0x1400f46cc  mov     rbx, rdx
0x1400f46cf  mov     rdi, [rdx+28h]
0x1400f46d3  mov     rbp, rcx
0x1400f46d6  mov     r14, [r8+20h]
0x1400f46da  mov     r12, [r8+28h]
0x1400f46de  mov     [rsp+98h+arg_8], eax
0x1400f46e5  mov     r8, rax
0x1400f46e8  mov     ecx, 4
0x1400f46ed  mov     r15, rax
0x1400f46f0  call    cs:__imp_WdLogSingleEntry2
0x1400f46f7  nop     dword ptr [rax+rax+00h]
0x1400f46fc  mov     ecx, r15d
0x1400f46ff  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f4709  test    ecx, ecx
0x1400f470b  jz      loc_1400F488A
0x1400f4711  sub     ecx, 1
0x1400f4714  jz      loc_1400F4999
0x1400f471a  cmp     ecx, 1
0x1400f471d  jnz     loc_1400F4BF3
0x1400f4723  lea     rcx, [rbp+40h]
0x1400f4727  mov     rdx, rbx
0x1400f472a  call    cs:__imp_RtlAvlRemoveNode
0x1400f4731  nop     dword ptr [rax+rax+00h]
0x1400f4736  mov     r8, [rbx+40h]
0x1400f473a  mov     dword ptr [rbx+58h], 3
0x1400f4741  cmp     r14, r13
0x1400f4744  ja      loc_1400F4893
0x1400f474a  cmp     r12, rdi
0x1400f474d  jnb     loc_1400F490A
0x1400f4753  mov     r10, [rbx+28h]
0x1400f4757  xor     r13d, r13d
0x1400f475a  mov     r11, [rbx+48h]
0x1400f475e  mov     r9, [r8+20h]
0x1400f4762  cmp     r9, r10
0x1400f4765  jnb     short loc_1400F47A1
0x1400f4767  cmp     [r8+28h], r12
0x1400f476b  jbe     short loc_1400F47A1
0x1400f476d  cmp     r9, r12
0x1400f4770  jnz     short loc_1400F4776
0x1400f4772  mov     [rbx+40h], r8
0x1400f4776  cmp     [r8+28h], r10
0x1400f477a  jnz     short loc_1400F4780
0x1400f477c  mov     [rbx+48h], r8
0x1400f4780  cmp     r8, r11
0x1400f4783  jz      short loc_1400F47B8
0x1400f4785  mov     rdx, [r8+78h]
0x1400f4789  mov     rcx, [r8+48h]
0x1400f478d  mov     r8, r13
0x1400f4790  add     rcx, 48h ; 'H'
0x1400f4794  cmp     rdx, rcx
0x1400f4797  lea     rax, [rdx-78h]
0x1400f479b  cmovnz  r8, rax
0x1400f479f  jmp     short loc_1400F475E
0x1400f47a1  mov     edx, [rbx+90h]
0x1400f47a7  test    edx, edx
0x1400f47a9  jnz     loc_1400F48F5
0x1400f47af  mov     [r8+88h], r13
0x1400f47b6  jmp     short loc_1400F476D
0x1400f47b8  mov     [rbx+20h], r12
0x1400f47bc  mov     [rbx+28h], r10
0x1400f47c0  mov     [rbx+30h], r12
0x1400f47c4  mov     r8, r15
0x1400f47c7  mov     rdx, rbx
0x1400f47ca  mov     ecx, 4
0x1400f47cf  call    cs:__imp_WdLogSingleEntry2
0x1400f47d6  nop     dword ptr [rax+rax+00h]
0x1400f47db  mov     cs:WdLogGlobalForLineNumber, 20E5h
0x1400f47e5  mov     r14d, r15d
0x1400f47e8  mov     rcx, [rbx+28h]
0x1400f47ec  sub     rcx, [rbx+20h]
0x1400f47f0  mov     rax, [rbx+38h]
0x1400f47f4  mov     [rsp+98h+var_68], rcx
0x1400f47f9  mov     ecx, r15d
0x1400f47fc  mov     [rsp+98h+var_60], rax
0x1400f4801  mov     [rsp+98h+var_58], r13b
0x1400f4806  test    r15d, r15d
0x1400f4809  jz      loc_1400F4956
0x1400f480f  sub     ecx, 1
0x1400f4812  jz      loc_1400F49A2
0x1400f4818  cmp     ecx, 1
0x1400f481b  jnz     loc_1400F4C33
0x1400f4821  mov     rsi, [rbp+40h]
0x1400f4825  mov     dil, r13b
0x1400f4828  test    rsi, rsi
0x1400f482b  jz      short loc_1400F485B
0x1400f482d  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f4830  lea     rcx, [rsp+98h+var_68]; void *
0x1400f4835  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f483a  test    eax, eax
0x1400f483c  js      short loc_1400F484C
0x1400f483e  mov     rax, [rsi+8]
0x1400f4842  test    rax, rax
0x1400f4845  jz      short loc_1400F4856
0x1400f4847  mov     rsi, rax
0x1400f484a  jmp     short loc_1400F482D
0x1400f484c  mov     rax, [rsi]
0x1400f484f  test    rax, rax
0x1400f4852  jnz     short loc_1400F4847
0x1400f4854  jmp     short loc_1400F485B
0x1400f4856  mov     edi, 1
0x1400f485b  lea     rcx, [rbp+40h]
0x1400f485f  mov     r9, rbx
0x1400f4862  mov     r8b, dil
0x1400f4865  mov     rdx, rsi
0x1400f4868  call    cs:__imp_RtlAvlInsertNodeEx
0x1400f486f  nop     dword ptr [rax+rax+00h]
0x1400f4874  mov     [rbx+58h], r14d
0x1400f4878  add     rsp, 58h
0x1400f487c  pop     r15
0x1400f487e  pop     r14
0x1400f4880  pop     r13
0x1400f4882  pop     r12
0x1400f4884  pop     rdi
0x1400f4885  pop     rsi
0x1400f4886  pop     rbp
0x1400f4887  pop     rbx
0x1400f4888  retn
0x1400f488a  lea     rcx, [rbp+30h]
0x1400f488e  jmp     loc_1400F4727
0x1400f4893  cmp     r12, rdi
0x1400f4896  jb      loc_1400F4AF7
0x1400f489c  mov     r9, [rbx+20h]
0x1400f48a0  xor     edi, edi
0x1400f48a2  mov     r11, [rbx+48h]
0x1400f48a6  mov     r10, [r8+20h]
0x1400f48aa  cmp     r10, r14
0x1400f48ad  jnb     loc_1400F49E5
0x1400f48b3  cmp     [r8+28h], r9
0x1400f48b7  jbe     loc_1400F49E5
0x1400f48bd  cmp     r10, r9
0x1400f48c0  jnz     short loc_1400F48C6
0x1400f48c2  mov     [rbx+40h], r8
0x1400f48c6  cmp     [r8+28h], r14
0x1400f48ca  jnz     short loc_1400F48D0
0x1400f48cc  mov     [rbx+48h], r8
0x1400f48d0  cmp     r8, r11
0x1400f48d3  jz      loc_1400F4A38
0x1400f48d9  mov     rdx, [r8+78h]
0x1400f48dd  mov     rcx, [r8+48h]
0x1400f48e1  mov     r8, rdi
0x1400f48e4  add     rcx, 48h ; 'H'
0x1400f48e8  cmp     rdx, rcx
0x1400f48eb  lea     rax, [rdx-78h]
0x1400f48ef  cmovnz  r8, rax
0x1400f48f3  jmp     short loc_1400F48A6
0x1400f48f5  sub     edx, 1
0x1400f48f8  jnz     loc_1400F4BB4
0x1400f48fe  mov     [r8+90h], r13
0x1400f4905  jmp     loc_1400F476D
0x1400f490a  xor     r9d, r9d
0x1400f490d  mov     ecx, [rbx+90h]
0x1400f4913  test    ecx, ecx
0x1400f4915  jz      short loc_1400F4929
0x1400f4917  sub     ecx, 1
0x1400f491a  jnz     loc_1400F4AE2
0x1400f4920  mov     [r8+90h], r9
0x1400f4927  jmp     short loc_1400F4930
0x1400f4929  mov     [r8+88h], r9
0x1400f4930  cmp     r8, [rbx+48h]
0x1400f4934  jz      loc_1400F49FF
0x1400f493a  mov     rdx, [r8+78h]
0x1400f493e  mov     rcx, [r8+48h]
0x1400f4942  mov     r8, r9
0x1400f4945  add     rcx, 48h ; 'H'
0x1400f4949  cmp     rdx, rcx
0x1400f494c  lea     rax, [rdx-78h]
0x1400f4950  cmovnz  r8, rax
0x1400f4954  jmp     short loc_1400F490D
0x1400f4956  mov     rsi, [rbp+30h]
0x1400f495a  mov     dil, r13b
0x1400f495d  test    rsi, rsi
0x1400f4960  jz      short loc_1400F4990
0x1400f4962  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f4965  lea     rcx, [rsp+98h+var_68]; void *
0x1400f496a  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f496f  test    eax, eax
0x1400f4971  js      short loc_1400F4981
0x1400f4973  mov     rax, [rsi+8]
0x1400f4977  test    rax, rax
0x1400f497a  jz      short loc_1400F498B
0x1400f497c  mov     rsi, rax
0x1400f497f  jmp     short loc_1400F4962
0x1400f4981  mov     rax, [rsi]
0x1400f4984  test    rax, rax
0x1400f4987  jnz     short loc_1400F497C
0x1400f4989  jmp     short loc_1400F4990
0x1400f498b  mov     edi, 1
0x1400f4990  lea     rcx, [rbp+30h]
0x1400f4994  jmp     loc_1400F485F
0x1400f4999  lea     rcx, [rbp+38h]
0x1400f499d  jmp     loc_1400F4727
0x1400f49a2  mov     rsi, [rbp+38h]
0x1400f49a6  mov     dil, r13b
0x1400f49a9  test    rsi, rsi
0x1400f49ac  jz      short loc_1400F49DC
0x1400f49ae  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f49b1  lea     rcx, [rsp+98h+var_68]; void *
0x1400f49b6  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f49bb  test    eax, eax
0x1400f49bd  js      short loc_1400F49CD
0x1400f49bf  mov     rax, [rsi+8]
0x1400f49c3  test    rax, rax
0x1400f49c6  jz      short loc_1400F49D7
0x1400f49c8  mov     rsi, rax
0x1400f49cb  jmp     short loc_1400F49AE
0x1400f49cd  mov     rax, [rsi]
0x1400f49d0  test    rax, rax
0x1400f49d3  jnz     short loc_1400F49C8
0x1400f49d5  jmp     short loc_1400F49DC
0x1400f49d7  mov     edi, 1
0x1400f49dc  lea     rcx, [rbp+38h]
0x1400f49e0  jmp     loc_1400F485F
0x1400f49e5  mov     edx, [rbx+90h]
0x1400f49eb  test    edx, edx
0x1400f49ed  jnz     loc_1400F4ACD
0x1400f49f3  mov     [r8+88h], rdi
0x1400f49fa  jmp     loc_1400F48BD
0x1400f49ff  mov     rsi, [rbp+8]
0x1400f4a03  mov     rcx, rbx; this
0x1400f4a06  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f4a0b  mov     eax, [rsi+654h]
0x1400f4a11  cmp     eax, 4
0x1400f4a14  jnb     loc_1400F4AB2
0x1400f4a1a  mov     edi, 1
0x1400f4a1f  mov     [rsi+rax*8+678h], rbx
0x1400f4a27  add     [rsi+654h], edi
0x1400f4a2d  dec     dword ptr [rsi+698h]
0x1400f4a33  jmp     loc_1400F4878
0x1400f4a38  mov     [rbx+20h], r9
0x1400f4a3c  mov     edx, r15d
0x1400f4a3f  mov     [rbx+28h], r14
0x1400f4a43  mov     [rbx+30h], r9
0x1400f4a47  jmp     short loc_1400F4AA2
0x1400f4a49  mov     edi, [rsp+98h+arg_8]
0x1400f4a50  mov     r8, rbx
0x1400f4a53  mov     edx, edi
0x1400f4a55  mov     [rbx+20h], r10
0x1400f4a59  mov     rcx, rbp
0x1400f4a5c  mov     [rbx+28h], r14
0x1400f4a60  mov     [rbx+30h], r10
0x1400f4a64  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f4a69  mov     r8, [rbx+50h]
0x1400f4a6d  mov     r9, r12
0x1400f4a70  mov     edx, [rbx+90h]
0x1400f4a76  mov     rcx, [rbp+8]
0x1400f4a7a  mov     [rsp+98h+var_78], r13
0x1400f4a7f  call    ?CreateMultirange@VIDMM_RECYCLE_HEAP_MGR@@QEAAPEAVVIDMM_RECYCLE_MULTIRANGE@@W4VIDMM_RECYCLE_MULTIRANGE_STATE@@PEAVVIDMM_RECYCLE_BLOCK@@_K2@Z; VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(VIDMM_RECYCLE_MULTIRANGE_STATE,VIDMM_RECYCLE_BLOCK *,unsigned __int64,unsigned __int64)
0x1400f4a84  mov     rbx, rax
0x1400f4a87  test    rax, rax
0x1400f4a8a  jz      loc_1400F4B8C
0x1400f4a90  mov     rcx, rax; this
0x1400f4a93  mov     [rax+40h], rsi
0x1400f4a97  mov     [rax+48h], r15
0x1400f4a9b  call    ?MarkAllRangesWithNewOwner@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::MarkAllRangesWithNewOwner(void)
0x1400f4aa0  mov     edx, edi
0x1400f4aa2  mov     r8, rbx
0x1400f4aa5  mov     rcx, rbp
0x1400f4aa8  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f4aad  jmp     loc_1400F4878
0x1400f4ab2  mov     rcx, [rsi+528h]; Lookaside
0x1400f4ab9  mov     rdx, rbx; Entry
0x1400f4abc  call    cs:__imp_ExFreeToLookasideListEx
0x1400f4ac3  nop     dword ptr [rax+rax+00h]
0x1400f4ac8  jmp     loc_1400F4A2D
0x1400f4acd  sub     edx, 1
0x1400f4ad0  jnz     loc_1400F4BC9
0x1400f4ad6  mov     [r8+90h], rdi
0x1400f4add  jmp     loc_1400F48BD
0x1400f4ae2  cmp     ecx, 1
0x1400f4ae5  jnz     loc_1400F4930
0x1400f4aeb  mov     [r8+98h], r9
0x1400f4af2  jmp     loc_1400F4930
0x1400f4af7  mov     rax, [rsi+48h]
0x1400f4afb  xor     r11d, r11d
0x1400f4afe  mov     r13, [rbx+28h]
0x1400f4b02  mov     esi, r11d
0x1400f4b05  mov     r15, [rbx+48h]
0x1400f4b09  mov     r10, [rbx+20h]
0x1400f4b0d  mov     rdx, [rax+78h]
0x1400f4b11  mov     rcx, [rax+48h]
0x1400f4b15  add     rcx, 48h ; 'H'
0x1400f4b19  cmp     rdx, rcx
0x1400f4b1c  lea     rax, [rdx-78h]
0x1400f4b20  cmovnz  rsi, rax
0x1400f4b24  mov     r9, [r8+20h]
0x1400f4b28  cmp     r9, r14
0x1400f4b2b  jnb     short loc_1400F4B6B
0x1400f4b2d  cmp     [r8+28h], r10
  ... truncated ...
```
