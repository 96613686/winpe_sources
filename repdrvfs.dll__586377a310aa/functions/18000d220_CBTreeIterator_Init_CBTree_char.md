# CBTreeIterator::Init(CBTree *,char *)

- ea: `0x18000d220`
- end: `0x18000d7d6`
- name: `?Init@CBTreeIterator@@QEAAKPEAVCBTree@@PEAD@Z`
- size: `1462`
- prototype: `unsigned int __fastcall(CBTreeIterator *__hidden this, struct CBTree *, char *)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c500`
- `0x18000cb50`
- `0x180028a74`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000d220`
- `0x18000d7e0`
- `0x18000fb70`
- `0x1800129a0`
- `0x180029d4c`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000d4ff`
- `wbemcomn!GetMemLogObject` at `0x18000d565`
- `wbemcomn!GetMemLogObject` at `0x18000d64e`
- `wbemcomn!GetMemLogObject` at `0x18000d697`
- `wbemcomn!GetMemLogObject` at `0x18000d6f6`
- `wbemcomn!GetMemLogObject` at `0x18000d737`
- `wbemcomn!GetMemLogObject` at `0x18000d785`
- `wbemcomn!GetMemLogObject` at `0x18000d4ff`
- `wbemcomn!GetMemLogObject` at `0x18000d565`
- `wbemcomn!GetMemLogObject` at `0x18000d64e`
- `wbemcomn!GetMemLogObject` at `0x18000d697`
- `wbemcomn!GetMemLogObject` at `0x18000d6f6`
- `wbemcomn!GetMemLogObject` at `0x18000d737`
- `wbemcomn!GetMemLogObject` at `0x18000d785`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d50a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d573`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d659`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d6a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d701`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d745`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d793`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d50a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d573`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d659`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d6a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d701`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d745`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d793`

## pseudocode

```c
__int64 __fastcall CBTreeIterator::Init(CBTreeIterator *this, struct CBTree *a2, char *a3)
{
  char *v3; // r14
  SIdxKeyTable *v4; // rbx
  __int64 v6; // rcx
  int v7; // esi
  struct SIdxKeyTable *v8; // rbp
  int v9; // eax
  int v10; // r13d
  int v11; // ebx
  __int64 v12; // rcx
  char *v13; // rdx
  __int64 v14; // r14
  __int64 v15; // r11
  __int64 v16; // rcx
  __int16 v17; // r10
  unsigned __int16 v18; // r11
  __int64 v19; // r15
  __int64 v20; // r12
  char *v21; // r8
  __int16 v22; // r10
  int v23; // ecx
  int v24; // eax
  int v25; // r9d
  int v26; // ecx
  __int64 v27; // r8
  unsigned int v28; // edx
  __int64 v29; // rcx
  unsigned int v30; // ebx
  __int64 v31; // rcx
  __int64 v33; // rcx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v35; // rcx
  __int64 v36; // rcx
  SIdxKeyTable *v37; // rdx
  unsigned int *i; // rax
  CMemoryLog *v39; // rax
  CVarObjHeap *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rdx
  volatile signed __int32 *v43; // rdx
  __int64 v44; // rcx
  unsigned int v45; // edx
  CBTree *v46; // rcx
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  CMemoryLog *v49; // rax
  CMemoryLog *v50; // rax
  CMemoryLog *v51; // rax
  SIdxKeyTable *v52; // [rsp+68h] [rbp+10h] BYREF
  char *v53; // [rsp+70h] [rbp+18h]
  struct SIdxKeyTable *v54; // [rsp+78h] [rbp+20h] BYREF

  v53 = a3;
  v52 = a2;
  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( v4 )
  {
    *(_QWORD *)this = v4;
    if ( !*((_QWORD *)v4 + 1) )
    {
      v30 = CBTree::RebuildCacheIfMissing(v4);
      if ( v30 )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, v30);
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v42 = 183;
LABEL_48:
          WPP_SF_d(*((_QWORD *)v35 + 2), v42, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, v30);
        }
        return v30;
      }
      v4 = v52;
    }
    v6 = *((int *)this + 2562);
    v7 = 0;
    *((_DWORD *)this + 2562) = v6 + 1;
    *((_QWORD *)this + v6 + 2) = 0;
    *((_WORD *)this + *((int *)this + 2562) + 4100) = 0;
    if ( v3 )
    {
      v8 = (struct SIdxKeyTable *)*((_QWORD *)v4 + 1);
      _InterlockedIncrement((volatile signed __int32 *)v8);
      while ( *v3 )
      {
        v9 = *((_DWORD *)v8 + 3);
        if ( v9 )
        {
          LOWORD(v10) = 0;
          v11 = v9 - 1;
          while ( 2 )
          {
            if ( v7 <= v11 )
            {
              v12 = *((_QWORD *)v8 + 2);
              v13 = v3;
              v14 = *((_QWORD *)v8 + 6);
              v10 = (v11 + v7) / 2;
              v54 = (struct SIdxKeyTable *)(unsigned __int16)v10;
              v15 = *(unsigned __int16 *)(v12 + 2LL * (unsigned __int16)v10);
              v16 = *((_QWORD *)v8 + 8);
              v17 = *(_WORD *)(v14 + 2 * v15);
              v18 = v15 + 1;
              v19 = *(_QWORD *)(v16 + 24);
              v20 = *(_QWORD *)(v16 + 8);
              v21 = (char *)(v19 + *(unsigned __int16 *)(v20 + 2LL * *(unsigned __int16 *)(v14 + 2LL * v18)));
              v22 = v17 - 1;
              while ( 1 )
              {
                v23 = *v21++;
                v24 = *v13;
                v25 = v23;
                if ( !(_BYTE)v23 && v22 )
                {
                  ++v18;
                  v25 = 92;
                  v21 = (char *)(v19 + *(unsigned __int16 *)(v20 + 2LL * *(unsigned __int16 *)(v14 + 2LL * v18)));
                  --v22;
                }
                v26 = v24 - v25;
                if ( v24 != v25 )
                  break;
                if ( !(_BYTE)v24 && !v25 )
                  goto LABEL_25;
                ++v13;
              }
              if ( v26 < 0 )
              {
                v3 = v53;
                v11 = v10 - 1;
                continue;
              }
              if ( v26 > 0 )
              {
                v3 = v53;
                v7 = ++v10;
                continue;
              }
LABEL_25:
              v31 = *((int *)this + 2562);
              *((_DWORD *)this + 2562) = v31 + 1;
              *((_QWORD *)this + v31 + 2) = v8;
              *((_WORD *)this + *((int *)this + 2562) + 4100) = (_WORD)v54;
              return 0;
            }
            break;
          }
          v4 = v52;
          v27 = (unsigned __int16)v10;
          v7 = 0;
        }
        else
        {
          v27 = 0;
        }
        v28 = *(_DWORD *)(*((_QWORD *)v8 + 5) + 4LL * (unsigned __int16)v27);
        v29 = *((int *)this + 2562);
        *((_DWORD *)this + 2562) = v29 + 1;
        *((_QWORD *)this + v29 + 2) = v8;
        *((_WORD *)this + *((int *)this + 2562) + 4100) = v27;
        if ( v28 == -1 )
        {
          v33 = *((int *)this + 2562);
          if ( *((_QWORD *)this + v33 + 1) )
          {
            while ( *((_WORD *)this + (int)v33 + 4100) == *(_WORD *)(*((_QWORD *)this + (int)v33 + 1) + 12LL) )
            {
              CBTreeIterator::Pop(this);
              v33 = *((int *)this + 2562);
              if ( !*((_QWORD *)this + v33 + 1) )
                return 0;
            }
          }
          return 0;
        }
        v54 = 0;
        LOBYTE(v27) = 1;
        v30 = CBTree::ReadIdxPage(v4, v28, v27, &v54);
        if ( v30 )
        {
          v49 = GetMemLogObject();
          CMemoryLog::Write(v49, v30);
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v42 = 187;
            goto LABEL_48;
          }
          return v30;
        }
        v8 = v54;
        v4 = v52;
      }
      v50 = GetMemLogObject();
      CMemoryLog::Write(v50, 87);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
      }
      v51 = GetMemLogObject();
      CMemoryLog::Write(v51, 87);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 186;
        goto LABEL_76;
      }
      return 87;
    }
    v43 = (volatile signed __int32 *)*((_QWORD *)v4 + 1);
    _InterlockedIncrement(v43);
    v44 = *((int *)this + 2562);
    *((_DWORD *)this + 2562) = v44 + 1;
    *((_QWORD *)this + v44 + 2) = v43;
    *((_WORD *)this + *((int *)this + 2562) + 4100) = 0;
    for ( i = *(unsigned int **)(*((_QWORD *)this + *((int *)this + 2562) + 1) + 40LL);
          ;
          i = (unsigned int *)*((_QWORD *)v37 + 5) )
    {
      v45 = *i;
      if ( *i == -1 )
        return 0;
      v46 = *(CBTree **)this;
      LOBYTE(a3) = 1;
      v52 = 0;
      v30 = CBTree::ReadIdxPage(v46, v45, (__int64)a3, &v52);
      if ( v30 )
        break;
      v36 = *((int *)this + 2562);
      if ( (_DWORD)v36 == 1023 )
      {
        SIdxKeyTable::Release(v52);
        v48 = GetMemLogObject();
        CMemoryLog::Write(v48, 122);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 122);
        }
        return 122;
      }
      v37 = v52;
      *((_DWORD *)this + 2562) = v36 + 1;
      *((_QWORD *)this + v36 + 2) = v37;
      *((_WORD *)this + *((int *)this + 2562) + 4100) = 0;
    }
    v47 = GetMemLogObject();
    CMemoryLog::Write(v47, v30);
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v42 = 184;
      goto LABEL_48;
    }
    return v30;
  }
  v39 = GetMemLogObject();
  CMemoryLog::Write(v39, 87);
  v40 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v41 = 182;
LABEL_76:
    WPP_SF_d(*((_QWORD *)v40 + 2), v41, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
  }
  return 87;
}

```

## disassembly

```asm
0x18000d220  mov     [rsp+arg_10], r8
0x18000d225  mov     [rsp+arg_8], rdx
0x18000d22a  push    rbx
0x18000d22b  push    rdi
0x18000d22c  push    r14
0x18000d22e  push    r15
0x18000d230  sub     rsp, 38h
0x18000d234  mov     r14, r8
0x18000d237  mov     rbx, rdx
0x18000d23a  mov     rdi, rcx
0x18000d23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d244  lea     r15, WPP_GLOBAL_Control
0x18000d24b  cmp     rcx, r15
0x18000d24e  jnz     loc_18000D47C
0x18000d254  mov     [rsp+58h+arg_0], rbp
0x18000d259  mov     [rsp+58h+var_28], rsi
0x18000d25e  mov     [rsp+58h+var_30], r12
0x18000d263  mov     [rsp+58h+var_38], r13
0x18000d268  test    rbx, rbx
0x18000d26b  jz      loc_18000D565
0x18000d271  mov     [rdi], rbx
0x18000d274  cmp     qword ptr [rbx+8], 0
0x18000d279  jz      loc_18000D4ED
0x18000d27f  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d286  xor     esi, esi
0x18000d288  lea     eax, [rcx+1]
0x18000d28b  mov     [rdi+2808h], eax
0x18000d291  mov     [rdi+rcx*8+10h], rsi
0x18000d296  movsxd  rax, dword ptr [rdi+2808h]
0x18000d29d  lea     rcx, [rdi+rax*2]
0x18000d2a1  mov     [rcx+2008h], si
0x18000d2a8  test    r14, r14
0x18000d2ab  jz      loc_18000D5E9
0x18000d2b1  mov     rbp, [rbx+8]
0x18000d2b5  lock inc dword ptr [rbp+0]
0x18000d2b9  cmp     byte ptr [r14], 0
0x18000d2bd  mov     r9d, 0FFFFh
0x18000d2c3  jz      loc_18000D737
0x18000d2c9  mov     eax, [rbp+0Ch]
0x18000d2cc  test    eax, eax
0x18000d2ce  jz      loc_18000D474
0x18000d2d4  mov     r13d, esi
0x18000d2d7  lea     ebx, [rax-1]
0x18000d2da  cmp     esi, ebx
0x18000d2dc  jg      loc_18000D3B5
0x18000d2e2  mov     rcx, [rbp+10h]
0x18000d2e6  lea     eax, [rbx+rsi]
0x18000d2e9  cdq
0x18000d2ea  sub     eax, edx
0x18000d2ec  mov     rdx, r14
0x18000d2ef  mov     r14, [rbp+30h]
0x18000d2f3  sar     eax, 1
0x18000d2f5  mov     r13d, eax
0x18000d2f8  movzx   eax, ax
0x18000d2fb  mov     [rsp+58h+arg_18], rax
0x18000d300  movzx   r11d, word ptr [rcx+rax*2]
0x18000d305  mov     rcx, [rbp+40h]
0x18000d309  movzx   r10d, word ptr [r14+r11*2]
0x18000d30e  inc     r11w
0x18000d312  mov     r15, [rcx+18h]
0x18000d316  mov     r12, [rcx+8]
0x18000d31a  movzx   eax, r11w
0x18000d31e  movzx   ecx, word ptr [r14+rax*2]
0x18000d323  movzx   r8d, word ptr [r12+rcx*2]
0x18000d328  add     r8, r15
0x18000d32b  add     r10w, r9w
0x18000d32f  nop
0x18000d330  movsx   ecx, byte ptr [r8]
0x18000d334  inc     r8
0x18000d337  movsx   eax, byte ptr [rdx]
0x18000d33a  mov     r9d, ecx
0x18000d33d  test    cl, cl
0x18000d33f  jz      short loc_18000D355
0x18000d341  mov     ecx, eax
0x18000d343  sub     ecx, r9d
0x18000d346  jnz     short loc_18000D381
0x18000d348  test    al, al
0x18000d34a  jz      loc_18000D6E8
0x18000d350  inc     rdx
0x18000d353  jmp     short loc_18000D330
0x18000d355  test    r10w, r10w
0x18000d359  jz      short loc_18000D341
0x18000d35b  inc     r11w
0x18000d35f  mov     r9d, 5Ch ; '\'
0x18000d365  movzx   ecx, r11w
0x18000d369  movzx   ecx, word ptr [r14+rcx*2]
0x18000d36e  movzx   r8d, word ptr [r12+rcx*2]
0x18000d373  mov     ecx, 0FFFFh
0x18000d378  add     r8, r15
0x18000d37b  add     r10w, cx
0x18000d37f  jmp     short loc_18000D341
0x18000d381  test    ecx, ecx
0x18000d383  jns     short loc_18000D399
0x18000d385  mov     r14, [rsp+58h+arg_10]
0x18000d38a  lea     ebx, [r13-1]
0x18000d38e  mov     r9d, 0FFFFh
0x18000d394  jmp     loc_18000D2DA
0x18000d399  jle     loc_18000D42A
0x18000d39f  mov     r14, [rsp+58h+arg_10]
0x18000d3a4  inc     r13d
0x18000d3a7  mov     esi, r13d
0x18000d3aa  mov     r9d, 0FFFFh
0x18000d3b0  jmp     loc_18000D2DA
0x18000d3b5  mov     rbx, [rsp+58h+arg_8]
0x18000d3ba  movzx   r8d, r13w
0x18000d3be  xor     esi, esi
0x18000d3c0  mov     rax, [rbp+28h]
0x18000d3c4  movzx   ecx, r8w
0x18000d3c8  mov     edx, [rax+rcx*4]; unsigned int
0x18000d3cb  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d3d2  lea     eax, [rcx+1]
0x18000d3d5  mov     [rdi+2808h], eax
0x18000d3db  lea     rcx, [rdi+rcx*8]
0x18000d3df  mov     [rcx+10h], rbp
0x18000d3e3  movsxd  rax, dword ptr [rdi+2808h]
0x18000d3ea  mov     [rdi+rax*2+2008h], r8w
0x18000d3f3  cmp     edx, 0FFFFFFFFh
0x18000d3f6  jz      loc_18000D4AA
0x18000d3fc  lea     r9, [rsp+58h+arg_18]; struct SIdxKeyTable **
0x18000d401  mov     [rsp+58h+arg_18], rsi
0x18000d406  mov     r8b, 1; bool
0x18000d409  mov     rcx, rbx; this
0x18000d40c  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x18000d411  mov     ebx, eax
0x18000d413  test    eax, eax
0x18000d415  jnz     loc_18000D6F6
0x18000d41b  mov     rbp, [rsp+58h+arg_18]
0x18000d420  mov     rbx, [rsp+58h+arg_8]
0x18000d425  jmp     loc_18000D2B9
0x18000d42a  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d431  lea     eax, [rcx+1]
0x18000d434  mov     [rdi+2808h], eax
0x18000d43a  mov     [rdi+rcx*8+10h], rbp
0x18000d43f  movsxd  rax, dword ptr [rdi+2808h]
0x18000d446  mov     rcx, [rsp+58h+arg_18]
0x18000d44b  mov     [rdi+rax*2+2008h], cx
0x18000d453  xor     eax, eax
0x18000d455  mov     r13, [rsp+58h+var_38]
0x18000d45a  mov     r12, [rsp+58h+var_30]
0x18000d45f  mov     rsi, [rsp+58h+var_28]
0x18000d464  mov     rbp, [rsp+58h+arg_0]
0x18000d469  add     rsp, 38h
0x18000d46d  pop     r15
0x18000d46f  pop     r14
0x18000d471  pop     rdi
0x18000d472  pop     rbx
0x18000d473  retn
0x18000d474  mov     r8d, esi
0x18000d477  jmp     loc_18000D3C0
0x18000d47c  test    byte ptr [rcx+1Ch], 1
0x18000d480  jz      loc_18000D254
0x18000d486  cmp     byte ptr [rcx+19h], 5
0x18000d48a  jb      loc_18000D254
0x18000d490  mov     rcx, [rcx+10h]
0x18000d494  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d49b  mov     edx, 0B5h
0x18000d4a0  call    WPP_SF_
0x18000d4a5  jmp     loc_18000D254
0x18000d4aa  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d4b1  cmp     qword ptr [rdi+rcx*8+8], 0
0x18000d4b7  jz      short loc_18000D453
0x18000d4b9  movsxd  rdx, ecx
0x18000d4bc  mov     rax, [rdi+rdx*8+8]
0x18000d4c1  movzx   ecx, word ptr [rax+0Ch]
0x18000d4c5  cmp     [rdi+rdx*2+2008h], cx
0x18000d4cd  jnz     short loc_18000D453
0x18000d4cf  mov     rcx, rdi; this
0x18000d4d2  call    ?Pop@CBTreeIterator@@AEAAXXZ; CBTreeIterator::Pop(void)
0x18000d4d7  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d4de  cmp     qword ptr [rdi+rcx*8+8], 0
0x18000d4e4  jnz     short loc_18000D4B9
0x18000d4e6  xor     eax, eax
0x18000d4e8  jmp     loc_18000D455
0x18000d4ed  mov     rcx, rbx; this
0x18000d4f0  call    ?RebuildCacheIfMissing@CBTree@@AEAAKXZ; CBTree::RebuildCacheIfMissing(void)
0x18000d4f5  mov     ebx, eax
0x18000d4f7  test    eax, eax
0x18000d4f9  jz      loc_18000D5DF
0x18000d4ff  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d505  mov     rcx, rax
0x18000d508  mov     edx, ebx
0x18000d50a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d510  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d517  cmp     rcx, r15
0x18000d51a  jnz     loc_18000D5A7
0x18000d520  mov     eax, ebx
0x18000d522  jmp     loc_18000D455
0x18000d527  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d52e  cmp     ecx, 3FFh
0x18000d534  jz      loc_18000D68D
0x18000d53a  mov     rdx, [rsp+58h+arg_8]
0x18000d53f  lea     eax, [rcx+1]
0x18000d542  mov     [rdi+2808h], eax
0x18000d548  mov     [rdi+rcx*8+10h], rdx
0x18000d54d  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d554  mov     [rdi+rcx*2+2008h], si
0x18000d55c  mov     rax, [rdx+28h]
0x18000d560  jmp     loc_18000D624
0x18000d565  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d56b  mov     rcx, rax
0x18000d56e  mov     edx, 57h ; 'W'
0x18000d573  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d580  cmp     rcx, r15
0x18000d583  jz      loc_18000D7CC
0x18000d589  test    byte ptr [rcx+1Ch], 1
0x18000d58d  jz      loc_18000D7CC
0x18000d593  cmp     byte ptr [rcx+19h], 2
0x18000d597  jb      loc_18000D7CC
0x18000d59d  mov     edx, 0B6h
0x18000d5a2  jmp     loc_18000D7B6
0x18000d5a7  test    byte ptr [rcx+1Ch], 1
0x18000d5ab  jz      loc_18000D520
0x18000d5b1  cmp     byte ptr [rcx+19h], 2
0x18000d5b5  jb      loc_18000D520
0x18000d5bb  mov     edx, 0B7h
0x18000d5c0  jmp     short loc_18000D5C7
0x18000d5c2  mov     edx, 0BBh
0x18000d5c7  mov     rcx, [rcx+10h]
0x18000d5cb  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d5d2  mov     r9d, ebx
0x18000d5d5  call    WPP_SF_d
0x18000d5da  jmp     loc_18000D520
0x18000d5df  mov     rbx, [rsp+58h+arg_8]
0x18000d5e4  jmp     loc_18000D27F
0x18000d5e9  mov     rdx, [rbx+8]
0x18000d5ed  lock inc dword ptr [rdx]
0x18000d5f0  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d5f7  lea     eax, [rcx+1]
0x18000d5fa  mov     [rdi+2808h], eax
0x18000d600  mov     [rdi+rcx*8+10h], rdx
0x18000d605  movsxd  rcx, dword ptr [rdi+2808h]
0x18000d60c  mov     [rdi+rcx*2+2008h], si
0x18000d614  movsxd  rax, dword ptr [rdi+2808h]
0x18000d61b  mov     rcx, [rdi+rax*8+8]
0x18000d620  mov     rax, [rcx+28h]
0x18000d624  mov     edx, [rax]; unsigned int
0x18000d626  cmp     edx, 0FFFFFFFFh
0x18000d629  jz      loc_18000D453
0x18000d62f  mov     rcx, [rdi]; this
0x18000d632  lea     r9, [rsp+58h+arg_8]; struct SIdxKeyTable **
0x18000d637  mov     r8b, 1; bool
0x18000d63a  mov     [rsp+58h+arg_8], rsi
0x18000d63f  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x18000d644  mov     ebx, eax
0x18000d646  test    eax, eax
0x18000d648  jz      loc_18000D527
0x18000d64e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d654  mov     rcx, rax
0x18000d657  mov     edx, ebx
0x18000d659  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d65f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d666  cmp     rcx, r15
0x18000d669  jz      loc_18000D520
0x18000d66f  test    byte ptr [rcx+1Ch], 1
0x18000d673  jz      loc_18000D520
0x18000d679  cmp     byte ptr [rcx+19h], 2
0x18000d67d  jb      loc_18000D520
0x18000d683  mov     edx, 0B8h
0x18000d688  jmp     loc_18000D5C7
0x18000d68d  mov     rcx, [rsp+58h+arg_8]; this
0x18000d692  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x18000d697  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d69d  mov     rcx, rax
0x18000d6a0  mov     edx, 7Ah ; 'z'
0x18000d6a5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6b2  cmp     rcx, r15
0x18000d6b5  jz      short loc_18000D6DE
0x18000d6b7  test    byte ptr [rcx+1Ch], 1
0x18000d6bb  jz      short loc_18000D6DE
0x18000d6bd  cmp     byte ptr [rcx+19h], 2
0x18000d6c1  jb      short loc_18000D6DE
0x18000d6c3  mov     rcx, [rcx+10h]
0x18000d6c7  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000d6ce  mov     edx, 0B9h
0x18000d6d3  mov     r9d, 7Ah ; 'z'
0x18000d6d9  call    WPP_SF_d
0x18000d6de  mov     eax, 7Ah ; 'z'
0x18000d6e3  jmp     loc_18000D455
0x18000d6e8  test    r9d, r9d
0x18000d6eb  jz      loc_18000D42A
0x18000d6f1  jmp     loc_18000D350
0x18000d6f6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d6fc  mov     rcx, rax
0x18000d6ff  mov     edx, ebx
0x18000d701  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000d707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d70e  lea     rax, WPP_GLOBAL_Control
0x18000d715  cmp     rcx, rax
0x18000d718  jz      loc_18000D520
0x18000d71e  test    byte ptr [rcx+1Ch], 1
0x18000d722  jz      loc_18000D520
0x18000d728  cmp     byte ptr [rcx+19h], 2
0x18000d72c  jb      loc_18000D520
0x18000d732  jmp     loc_18000D5C2
0x18000d737  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000d73d  mov     rcx, rax
0x18000d740  mov     edx, 57h ; 'W'
0x18000d745  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
  ... truncated ...
```
