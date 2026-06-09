# VIDMM_RECYCLE_HEAP::ResizeMultirangeToExcludeOverlap(VIDMM_RECYCLE_MULTIRANGE *,VIDMM_RECYCLE_MULTIRANGE *)

- ea: `0x1400f9690`
- end: `0x1400f9c8a`
- name: `?ResizeMultirangeToExcludeOverlap@VIDMM_RECYCLE_HEAP@@AEAAXPEAVVIDMM_RECYCLE_MULTIRANGE@@0@Z`
- size: `1530`
- prototype: `void(VIDMM_RECYCLE_HEAP *__hidden this, struct VIDMM_RECYCLE_MULTIRANGE *, struct VIDMM_RECYCLE_MULTIRANGE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400fb698`

## callees

- `0x1400f9690`
- `0x1400fa930`
- `0x1400fa96c`
- `0x1400faa38`
- `0x1400fabc0`
- `0x1400fac80`
- `0x1400faecc`

## import_xrefs

- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f9848`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x1400f9848`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f9a9c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400f9a9c`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f970a`
- `ntoskrnl!RtlAvlRemoveNode` at `0x1400f970a`
- `watchdog!WdLogSingleEntry2` at `0x1400f96d0`
- `watchdog!WdLogSingleEntry2` at `0x1400f97af`
- `watchdog!WdLogSingleEntry2` at `0x1400f96d0`
- `watchdog!WdLogSingleEntry2` at `0x1400f97af`
- `watchdog!WdLogSingleEntry5` at `0x1400f9bfd`
- `watchdog!WdLogSingleEntry5` at `0x1400f9c39`
- `watchdog!WdLogSingleEntry5` at `0x1400f9bfd`
- `watchdog!WdLogSingleEntry5` at `0x1400f9c39`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f9bd3`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f9c13`

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
        WdLogSingleEntry5(0, 270, 52, 16, (int)v59, 0);
        WdLogGlobalForLineNumber = 227;
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
  v4 = 0;
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
    WdLogSingleEntry5(0, 270, 52, 15, (int)v59, v4);
    WdLogGlobalForLineNumber = 227;
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
0x1400f9690  push    rbx
0x1400f9692  push    rbp
0x1400f9693  push    rsi
0x1400f9694  push    rdi
0x1400f9695  push    r12
0x1400f9697  push    r13
0x1400f9699  push    r14
0x1400f969b  push    r15
0x1400f969d  sub     rsp, 58h
0x1400f96a1  movsxd  rax, dword ptr [rdx+58h]
0x1400f96a5  mov     rsi, r8
0x1400f96a8  mov     r13, [rdx+20h]
0x1400f96ac  mov     rbx, rdx
0x1400f96af  mov     rdi, [rdx+28h]
0x1400f96b3  mov     rbp, rcx
0x1400f96b6  mov     r14, [r8+20h]
0x1400f96ba  mov     r12, [r8+28h]
0x1400f96be  mov     [rsp+98h+arg_8], eax
0x1400f96c5  mov     r8, rax
0x1400f96c8  mov     ecx, 4
0x1400f96cd  mov     r15, rax
0x1400f96d0  call    cs:__imp_WdLogSingleEntry2
0x1400f96d7  nop     dword ptr [rax+rax+00h]
0x1400f96dc  mov     ecx, r15d
0x1400f96df  mov     cs:WdLogGlobalForLineNumber, 2117h
0x1400f96e9  test    ecx, ecx
0x1400f96eb  jz      loc_1400F986A
0x1400f96f1  sub     ecx, 1
0x1400f96f4  jz      loc_1400F9979
0x1400f96fa  cmp     ecx, 1
0x1400f96fd  jnz     loc_1400F9BD3
0x1400f9703  lea     rcx, [rbp+40h]
0x1400f9707  mov     rdx, rbx
0x1400f970a  call    cs:__imp_RtlAvlRemoveNode
0x1400f9711  nop     dword ptr [rax+rax+00h]
0x1400f9716  mov     r8, [rbx+40h]
0x1400f971a  mov     dword ptr [rbx+58h], 3
0x1400f9721  cmp     r14, r13
0x1400f9724  ja      loc_1400F9873
0x1400f972a  cmp     r12, rdi
0x1400f972d  jnb     loc_1400F98EA
0x1400f9733  mov     r10, [rbx+28h]
0x1400f9737  xor     r13d, r13d
0x1400f973a  mov     r11, [rbx+48h]
0x1400f973e  mov     r9, [r8+20h]
0x1400f9742  cmp     r9, r10
0x1400f9745  jnb     short loc_1400F9781
0x1400f9747  cmp     [r8+28h], r12
0x1400f974b  jbe     short loc_1400F9781
0x1400f974d  cmp     r9, r12
0x1400f9750  jnz     short loc_1400F9756
0x1400f9752  mov     [rbx+40h], r8
0x1400f9756  cmp     [r8+28h], r10
0x1400f975a  jnz     short loc_1400F9760
0x1400f975c  mov     [rbx+48h], r8
0x1400f9760  cmp     r8, r11
0x1400f9763  jz      short loc_1400F9798
0x1400f9765  mov     rdx, [r8+78h]
0x1400f9769  mov     rcx, [r8+48h]
0x1400f976d  mov     r8, r13
0x1400f9770  add     rcx, 48h ; 'H'
0x1400f9774  cmp     rdx, rcx
0x1400f9777  lea     rax, [rdx-78h]
0x1400f977b  cmovnz  r8, rax
0x1400f977f  jmp     short loc_1400F973E
0x1400f9781  mov     edx, [rbx+90h]
0x1400f9787  test    edx, edx
0x1400f9789  jnz     loc_1400F98D5
0x1400f978f  mov     [r8+88h], r13
0x1400f9796  jmp     short loc_1400F974D
0x1400f9798  mov     [rbx+20h], r12
0x1400f979c  mov     [rbx+28h], r10
0x1400f97a0  mov     [rbx+30h], r12
0x1400f97a4  mov     r8, r15
0x1400f97a7  mov     rdx, rbx
0x1400f97aa  mov     ecx, 4
0x1400f97af  call    cs:__imp_WdLogSingleEntry2
0x1400f97b6  nop     dword ptr [rax+rax+00h]
0x1400f97bb  mov     cs:WdLogGlobalForLineNumber, 20E5h
0x1400f97c5  mov     r14d, r15d
0x1400f97c8  mov     rcx, [rbx+28h]
0x1400f97cc  sub     rcx, [rbx+20h]
0x1400f97d0  mov     rax, [rbx+38h]
0x1400f97d4  mov     [rsp+98h+var_68], rcx
0x1400f97d9  mov     ecx, r15d
0x1400f97dc  mov     [rsp+98h+var_60], rax
0x1400f97e1  mov     [rsp+98h+var_58], r13b
0x1400f97e6  test    r15d, r15d
0x1400f97e9  jz      loc_1400F9936
0x1400f97ef  sub     ecx, 1
0x1400f97f2  jz      loc_1400F9982
0x1400f97f8  cmp     ecx, 1
0x1400f97fb  jnz     loc_1400F9C13
0x1400f9801  mov     rsi, [rbp+40h]
0x1400f9805  mov     dil, r13b
0x1400f9808  test    rsi, rsi
0x1400f980b  jz      short loc_1400F983B
0x1400f980d  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f9810  lea     rcx, [rsp+98h+var_68]; void *
0x1400f9815  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f981a  test    eax, eax
0x1400f981c  js      short loc_1400F982C
0x1400f981e  mov     rax, [rsi+8]
0x1400f9822  test    rax, rax
0x1400f9825  jz      short loc_1400F9836
0x1400f9827  mov     rsi, rax
0x1400f982a  jmp     short loc_1400F980D
0x1400f982c  mov     rax, [rsi]
0x1400f982f  test    rax, rax
0x1400f9832  jnz     short loc_1400F9827
0x1400f9834  jmp     short loc_1400F983B
0x1400f9836  mov     edi, 1
0x1400f983b  lea     rcx, [rbp+40h]
0x1400f983f  mov     r9, rbx
0x1400f9842  mov     r8b, dil
0x1400f9845  mov     rdx, rsi
0x1400f9848  call    cs:__imp_RtlAvlInsertNodeEx
0x1400f984f  nop     dword ptr [rax+rax+00h]
0x1400f9854  mov     [rbx+58h], r14d
0x1400f9858  add     rsp, 58h
0x1400f985c  pop     r15
0x1400f985e  pop     r14
0x1400f9860  pop     r13
0x1400f9862  pop     r12
0x1400f9864  pop     rdi
0x1400f9865  pop     rsi
0x1400f9866  pop     rbp
0x1400f9867  pop     rbx
0x1400f9868  retn
0x1400f986a  lea     rcx, [rbp+30h]
0x1400f986e  jmp     loc_1400F9707
0x1400f9873  cmp     r12, rdi
0x1400f9876  jb      loc_1400F9AD7
0x1400f987c  mov     r9, [rbx+20h]
0x1400f9880  xor     edi, edi
0x1400f9882  mov     r11, [rbx+48h]
0x1400f9886  mov     r10, [r8+20h]
0x1400f988a  cmp     r10, r14
0x1400f988d  jnb     loc_1400F99C5
0x1400f9893  cmp     [r8+28h], r9
0x1400f9897  jbe     loc_1400F99C5
0x1400f989d  cmp     r10, r9
0x1400f98a0  jnz     short loc_1400F98A6
0x1400f98a2  mov     [rbx+40h], r8
0x1400f98a6  cmp     [r8+28h], r14
0x1400f98aa  jnz     short loc_1400F98B0
0x1400f98ac  mov     [rbx+48h], r8
0x1400f98b0  cmp     r8, r11
0x1400f98b3  jz      loc_1400F9A18
0x1400f98b9  mov     rdx, [r8+78h]
0x1400f98bd  mov     rcx, [r8+48h]
0x1400f98c1  mov     r8, rdi
0x1400f98c4  add     rcx, 48h ; 'H'
0x1400f98c8  cmp     rdx, rcx
0x1400f98cb  lea     rax, [rdx-78h]
0x1400f98cf  cmovnz  r8, rax
0x1400f98d3  jmp     short loc_1400F9886
0x1400f98d5  sub     edx, 1
0x1400f98d8  jnz     loc_1400F9B94
0x1400f98de  mov     [r8+90h], r13
0x1400f98e5  jmp     loc_1400F974D
0x1400f98ea  xor     r9d, r9d
0x1400f98ed  mov     ecx, [rbx+90h]
0x1400f98f3  test    ecx, ecx
0x1400f98f5  jz      short loc_1400F9909
0x1400f98f7  sub     ecx, 1
0x1400f98fa  jnz     loc_1400F9AC2
0x1400f9900  mov     [r8+90h], r9
0x1400f9907  jmp     short loc_1400F9910
0x1400f9909  mov     [r8+88h], r9
0x1400f9910  cmp     r8, [rbx+48h]
0x1400f9914  jz      loc_1400F99DF
0x1400f991a  mov     rdx, [r8+78h]
0x1400f991e  mov     rcx, [r8+48h]
0x1400f9922  mov     r8, r9
0x1400f9925  add     rcx, 48h ; 'H'
0x1400f9929  cmp     rdx, rcx
0x1400f992c  lea     rax, [rdx-78h]
0x1400f9930  cmovnz  r8, rax
0x1400f9934  jmp     short loc_1400F98ED
0x1400f9936  mov     rsi, [rbp+30h]
0x1400f993a  mov     dil, r13b
0x1400f993d  test    rsi, rsi
0x1400f9940  jz      short loc_1400F9970
0x1400f9942  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f9945  lea     rcx, [rsp+98h+var_68]; void *
0x1400f994a  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f994f  test    eax, eax
0x1400f9951  js      short loc_1400F9961
0x1400f9953  mov     rax, [rsi+8]
0x1400f9957  test    rax, rax
0x1400f995a  jz      short loc_1400F996B
0x1400f995c  mov     rsi, rax
0x1400f995f  jmp     short loc_1400F9942
0x1400f9961  mov     rax, [rsi]
0x1400f9964  test    rax, rax
0x1400f9967  jnz     short loc_1400F995C
0x1400f9969  jmp     short loc_1400F9970
0x1400f996b  mov     edi, 1
0x1400f9970  lea     rcx, [rbp+30h]
0x1400f9974  jmp     loc_1400F983F
0x1400f9979  lea     rcx, [rbp+38h]
0x1400f997d  jmp     loc_1400F9707
0x1400f9982  mov     rsi, [rbp+38h]
0x1400f9986  mov     dil, r13b
0x1400f9989  test    rsi, rsi
0x1400f998c  jz      short loc_1400F99BC
0x1400f998e  mov     rdx, rsi; struct _RTL_BALANCED_NODE *
0x1400f9991  lea     rcx, [rsp+98h+var_68]; void *
0x1400f9996  call    ?VidMmCompareForInsertAlignedRange@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; VidMmCompareForInsertAlignedRange(void *,_RTL_BALANCED_NODE *)
0x1400f999b  test    eax, eax
0x1400f999d  js      short loc_1400F99AD
0x1400f999f  mov     rax, [rsi+8]
0x1400f99a3  test    rax, rax
0x1400f99a6  jz      short loc_1400F99B7
0x1400f99a8  mov     rsi, rax
0x1400f99ab  jmp     short loc_1400F998E
0x1400f99ad  mov     rax, [rsi]
0x1400f99b0  test    rax, rax
0x1400f99b3  jnz     short loc_1400F99A8
0x1400f99b5  jmp     short loc_1400F99BC
0x1400f99b7  mov     edi, 1
0x1400f99bc  lea     rcx, [rbp+38h]
0x1400f99c0  jmp     loc_1400F983F
0x1400f99c5  mov     edx, [rbx+90h]
0x1400f99cb  test    edx, edx
0x1400f99cd  jnz     loc_1400F9AAD
0x1400f99d3  mov     [r8+88h], rdi
0x1400f99da  jmp     loc_1400F989D
0x1400f99df  mov     rsi, [rbp+8]
0x1400f99e3  mov     rcx, rbx; this
0x1400f99e6  call    ?Destroy@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::Destroy(void)
0x1400f99eb  mov     eax, [rsi+654h]
0x1400f99f1  cmp     eax, 4
0x1400f99f4  jnb     loc_1400F9A92
0x1400f99fa  mov     edi, 1
0x1400f99ff  mov     [rsi+rax*8+678h], rbx
0x1400f9a07  add     [rsi+654h], edi
0x1400f9a0d  dec     dword ptr [rsi+698h]
0x1400f9a13  jmp     loc_1400F9858
0x1400f9a18  mov     [rbx+20h], r9
0x1400f9a1c  mov     edx, r15d
0x1400f9a1f  mov     [rbx+28h], r14
0x1400f9a23  mov     [rbx+30h], r9
0x1400f9a27  jmp     short loc_1400F9A82
0x1400f9a29  mov     edi, [rsp+98h+arg_8]
0x1400f9a30  mov     r8, rbx
0x1400f9a33  mov     edx, edi
0x1400f9a35  mov     [rbx+20h], r10
0x1400f9a39  mov     rcx, rbp
0x1400f9a3c  mov     [rbx+28h], r14
0x1400f9a40  mov     [rbx+30h], r10
0x1400f9a44  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f9a49  mov     r8, [rbx+50h]
0x1400f9a4d  mov     r9, r12
0x1400f9a50  mov     edx, [rbx+90h]
0x1400f9a56  mov     rcx, [rbp+8]
0x1400f9a5a  mov     [rsp+98h+var_78], r13
0x1400f9a5f  call    ?CreateMultirange@VIDMM_RECYCLE_HEAP_MGR@@QEAAPEAVVIDMM_RECYCLE_MULTIRANGE@@W4VIDMM_RECYCLE_MULTIRANGE_STATE@@PEAVVIDMM_RECYCLE_BLOCK@@_K2@Z; VIDMM_RECYCLE_HEAP_MGR::CreateMultirange(VIDMM_RECYCLE_MULTIRANGE_STATE,VIDMM_RECYCLE_BLOCK *,unsigned __int64,unsigned __int64)
0x1400f9a64  mov     rbx, rax
0x1400f9a67  test    rax, rax
0x1400f9a6a  jz      loc_1400F9B6C
0x1400f9a70  mov     rcx, rax; this
0x1400f9a73  mov     [rax+40h], rsi
0x1400f9a77  mov     [rax+48h], r15
0x1400f9a7b  call    ?MarkAllRangesWithNewOwner@VIDMM_RECYCLE_MULTIRANGE@@QEAAXXZ; VIDMM_RECYCLE_MULTIRANGE::MarkAllRangesWithNewOwner(void)
0x1400f9a80  mov     edx, edi
0x1400f9a82  mov     r8, rbx
0x1400f9a85  mov     rcx, rbp
0x1400f9a88  call    ?AddMultirangeToTree@VIDMM_RECYCLE_HEAP@@QEAAXW4VIDMM_RECYCLE_HEAP_TREE@@PEAVVIDMM_RECYCLE_MULTIRANGE@@@Z; VIDMM_RECYCLE_HEAP::AddMultirangeToTree(VIDMM_RECYCLE_HEAP_TREE,VIDMM_RECYCLE_MULTIRANGE *)
0x1400f9a8d  jmp     loc_1400F9858
0x1400f9a92  mov     rcx, [rsi+528h]; Lookaside
0x1400f9a99  mov     rdx, rbx; Entry
0x1400f9a9c  call    cs:__imp_ExFreeToLookasideListEx
0x1400f9aa3  nop     dword ptr [rax+rax+00h]
0x1400f9aa8  jmp     loc_1400F9A0D
0x1400f9aad  sub     edx, 1
0x1400f9ab0  jnz     loc_1400F9BA9
0x1400f9ab6  mov     [r8+90h], rdi
0x1400f9abd  jmp     loc_1400F989D
0x1400f9ac2  cmp     ecx, 1
0x1400f9ac5  jnz     loc_1400F9910
0x1400f9acb  mov     [r8+98h], r9
0x1400f9ad2  jmp     loc_1400F9910
0x1400f9ad7  mov     rax, [rsi+48h]
0x1400f9adb  xor     r11d, r11d
0x1400f9ade  mov     r13, [rbx+28h]
0x1400f9ae2  mov     esi, r11d
0x1400f9ae5  mov     r15, [rbx+48h]
0x1400f9ae9  mov     r10, [rbx+20h]
0x1400f9aed  mov     rdx, [rax+78h]
0x1400f9af1  mov     rcx, [rax+48h]
0x1400f9af5  add     rcx, 48h ; 'H'
0x1400f9af9  cmp     rdx, rcx
0x1400f9afc  lea     rax, [rdx-78h]
0x1400f9b00  cmovnz  rsi, rax
0x1400f9b04  mov     r9, [r8+20h]
0x1400f9b08  cmp     r9, r14
0x1400f9b0b  jnb     short loc_1400F9B4B
0x1400f9b0d  cmp     [r8+28h], r10
  ... truncated ...
```
