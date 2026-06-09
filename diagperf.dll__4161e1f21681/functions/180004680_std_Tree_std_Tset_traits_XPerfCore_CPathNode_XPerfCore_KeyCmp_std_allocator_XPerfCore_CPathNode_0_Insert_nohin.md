# std::_Tree<std::_Tset_traits<XPerfCore::CPathNode *,XPerfCore::KeyCmp,std::allocator<XPerfCore::CPathNode *>,0>>::_Insert_nohint<XPerfCore::CPathNode *,std::_Nil>(bool,XPerfCore::CPathNode * &&,std::_Nil)

- ea: `0x180004680`
- end: `0x180004d4e`
- name: `??$_Insert_nohint@PEAVCPathNode@XPerfCore@@U_Nil@std@@@?$_Tree@V?$_Tset_traits@PEAVCPathNode@XPerfCore@@UKeyCmp@2@V?$allocator@PEAVCPathNode@XPerfCore@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAVCPathNode@XPerfCore@@@std@@@std@@@std@@_N@1@_N$$QEAPEAVCPathNode@XPerfCore@@U_Nil@1@@Z`
- size: `1742`
- prototype: `__int64 __fastcall(__int64 **, __int64, __int64, const wchar_t ***)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800044b0`

## callees

- `0x180004680`
- `0x180004f6c`
- `0x180056d00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800046b4`
- `msvcrt!_wcsicmp` at `0x1800046e6`
- `msvcrt!_wcsicmp` at `0x1800046b4`
- `msvcrt!_wcsicmp` at `0x1800046e6`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<XPerfCore::CPathNode *,XPerfCore::KeyCmp,std::allocator<XPerfCore::CPathNode *>,0>>::_Insert_nohint<XPerfCore::CPathNode *,std::_Nil>(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        const wchar_t ***a4)
{
  __int64 *j; // rbx
  __int64 *v8; // rdi
  int v9; // eax
  unsigned int v10; // esi
  __int64 *v11; // rdi
  __int64 *i; // rax
  __int64 v14; // rax
  __int64 v15; // r9
  _QWORD *v16; // rdx
  __int64 v17; // rcx
  __int64 *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // r8
  __int64 v22; // rcx
  _QWORD *v23; // r8
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // r8
  _QWORD *v27; // rdx
  __int64 v28; // rcx
  __int64 *v29; // r9
  __int64 v30; // rax
  _QWORD *v31; // r8
  _QWORD *v32; // rax
  _QWORD *v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rax
  _QWORD *v36; // rax
  __int64 v37; // rax
  _QWORD *v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // r9
  __int64 v41; // rcx
  _QWORD *v42; // r9
  _QWORD *v43; // rax
  _QWORD *v44; // r9
  _QWORD *v45; // rax
  _QWORD *v46; // rcx
  __int64 v47; // r9
  __int64 v48; // rax
  _QWORD *v49; // rax
  __int64 v50; // rax
  _QWORD *v51; // rax

  j = *a1;
  v8 = (__int64 *)(*a1)[1];
  if ( *((_BYTE *)v8 + 25) )
  {
    LOBYTE(v10) = 1;
    v11 = *a1;
  }
  else
  {
    do
    {
      j = v8;
      v9 = _wcsicmp(**a4, *(const wchar_t **)v8[4]);
      v10 = (unsigned int)v9 >> 31;
      if ( v9 >= 0 )
        v8 = (__int64 *)v8[2];
      else
        v8 = (__int64 *)*v8;
    }
    while ( !*((_BYTE *)v8 + 25) );
    v11 = j;
    if ( v9 >= 0 )
    {
LABEL_6:
      if ( _wcsicmp(*(const wchar_t **)j[4], **a4) < 0 )
      {
        if ( (unsigned __int64)a1[1] >= 0x666666666666665LL )
          std::_Xlength_error("map/set<T> too long");
        v25 = std::_Tree_buy<XPerfCore::CPathNode *>::_Buynode<XPerfCore::CPathNode *>((__int64)a1, a4);
        v26 = v25;
        a1[1] = (__int64 *)((char *)a1[1] + 1);
        *(_QWORD *)(v25 + 8) = v11;
        if ( v11 == *a1 )
        {
          (*a1)[1] = v25;
          **a1 = v25;
          (*a1)[2] = v25;
        }
        else if ( (_BYTE)v10 )
        {
          *v11 = v25;
          if ( v11 == (__int64 *)**a1 )
            **a1 = v25;
        }
        else
        {
          v11[2] = v25;
          if ( v11 == (__int64 *)(*a1)[2] )
            (*a1)[2] = v25;
        }
        v27 = (_QWORD *)v25;
        while ( !*(_BYTE *)(v27[1] + 24LL) )
        {
          v28 = v27[1];
          v29 = *(__int64 **)(v28 + 8);
          v30 = *v29;
          if ( v28 == *v29 )
          {
            v39 = v29[2];
            if ( *(_BYTE *)(v39 + 24) )
            {
              v44 = *(_QWORD **)(v28 + 16);
              if ( v27 == v44 )
              {
                v27 = (_QWORD *)v27[1];
                *(_QWORD *)(v28 + 16) = *v44;
                if ( !*(_BYTE *)(*v44 + 25LL) )
                  *(_QWORD *)(*v44 + 8LL) = v28;
                v44[1] = *(_QWORD *)(v28 + 8);
                if ( v28 == (*a1)[1] )
                {
                  (*a1)[1] = (__int64)v44;
                }
                else
                {
                  v45 = *(_QWORD **)(v28 + 8);
                  if ( v28 == *v45 )
                    *v45 = v44;
                  else
                    v45[2] = v44;
                }
                *v44 = v28;
                *(_QWORD *)(v28 + 8) = v44;
              }
              *(_BYTE *)(v27[1] + 24LL) = 1;
              *(_BYTE *)(*(_QWORD *)(v27[1] + 8LL) + 24LL) = 0;
              v46 = *(_QWORD **)(v27[1] + 8LL);
              v47 = *v46;
              *v46 = *(_QWORD *)(*v46 + 16LL);
              v48 = *(_QWORD *)(v47 + 16);
              if ( !*(_BYTE *)(v48 + 25) )
                *(_QWORD *)(v48 + 8) = v46;
              *(_QWORD *)(v47 + 8) = v46[1];
              if ( v46 == (_QWORD *)(*a1)[1] )
              {
                (*a1)[1] = v47;
                *(_QWORD *)(v47 + 16) = v46;
                v46[1] = v47;
              }
              else
              {
                v49 = (_QWORD *)v46[1];
                if ( v46 == (_QWORD *)v49[2] )
                  v49[2] = v47;
                else
                  *v49 = v47;
                *(_QWORD *)(v47 + 16) = v46;
                v46[1] = v47;
              }
            }
            else
            {
              *(_BYTE *)(v28 + 24) = 1;
              *(_BYTE *)(v39 + 24) = 1;
              *(_BYTE *)(*(_QWORD *)(v27[1] + 8LL) + 24LL) = 0;
              v27 = *(_QWORD **)(v27[1] + 8LL);
            }
          }
          else if ( *(_BYTE *)(v30 + 24) )
          {
            v40 = *(_QWORD **)v28;
            if ( v27 == *(_QWORD **)v28 )
            {
              v27 = (_QWORD *)v27[1];
              *(_QWORD *)v28 = v40[2];
              v50 = v40[2];
              if ( !*(_BYTE *)(v50 + 25) )
                *(_QWORD *)(v50 + 8) = v28;
              v40[1] = *(_QWORD *)(v28 + 8);
              if ( v28 == (*a1)[1] )
              {
                (*a1)[1] = (__int64)v40;
                v40[2] = v28;
                *(_QWORD *)(v28 + 8) = v40;
              }
              else
              {
                v51 = *(_QWORD **)(v28 + 8);
                if ( v28 == v51[2] )
                  v51[2] = v40;
                else
                  *v51 = v40;
                v40[2] = v28;
                *(_QWORD *)(v28 + 8) = v40;
              }
            }
            *(_BYTE *)(v27[1] + 24LL) = 1;
            *(_BYTE *)(*(_QWORD *)(v27[1] + 8LL) + 24LL) = 0;
            v41 = *(_QWORD *)(v27[1] + 8LL);
            v42 = *(_QWORD **)(v41 + 16);
            *(_QWORD *)(v41 + 16) = *v42;
            if ( !*(_BYTE *)(*v42 + 25LL) )
              *(_QWORD *)(*v42 + 8LL) = v41;
            v42[1] = *(_QWORD *)(v41 + 8);
            if ( v41 == (*a1)[1] )
            {
              (*a1)[1] = (__int64)v42;
              *v42 = v41;
              *(_QWORD *)(v41 + 8) = v42;
            }
            else
            {
              v43 = *(_QWORD **)(v41 + 8);
              if ( v41 == *v43 )
                *v43 = v42;
              else
                v43[2] = v42;
              *v42 = v41;
              *(_QWORD *)(v41 + 8) = v42;
            }
          }
          else
          {
            *(_BYTE *)(v28 + 24) = 1;
            *(_BYTE *)(v30 + 24) = 1;
            *(_BYTE *)(*(_QWORD *)(v27[1] + 8LL) + 24LL) = 0;
            v27 = *(_QWORD **)(v27[1] + 8LL);
          }
        }
        *(_BYTE *)((*a1)[1] + 24) = 1;
        *(_QWORD *)a2 = v26;
        *(_BYTE *)(a2 + 8) = 1;
        return a2;
      }
      else
      {
        *(_QWORD *)a2 = j;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
    }
  }
  if ( v11 != (__int64 *)**a1 )
  {
    if ( *((_BYTE *)v11 + 25) )
    {
      j = (__int64 *)v11[2];
    }
    else if ( *(_BYTE *)(*v11 + 25) )
    {
      for ( i = (__int64 *)v11[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
      {
        if ( j != (__int64 *)*i )
          break;
        j = i;
      }
      if ( !*((_BYTE *)j + 25) )
        j = i;
    }
    else
    {
      for ( j = (__int64 *)*v11; !*(_BYTE *)(j[2] + 25); j = (__int64 *)j[2] )
        ;
    }
    goto LABEL_6;
  }
  if ( (unsigned __int64)a1[1] >= 0x666666666666665LL )
    std::_Xlength_error("map/set<T> too long");
  try
  {
    v14 = std::_Tree_buy<XPerfCore::CPathNode *>::_Buynode<XPerfCore::CPathNode *>((__int64)a1, a4);
  }
  catch ( ... )
  {
    throw;
  }
  v15 = v14;
  a1[1] = (__int64 *)((char *)a1[1] + 1);
  *(_QWORD *)(v14 + 8) = v11;
  if ( v11 == *a1 )
  {
    (*a1)[1] = v14;
    **a1 = v14;
    (*a1)[2] = v14;
  }
  else
  {
    *v11 = v14;
    if ( v11 == (__int64 *)**a1 )
      **a1 = v14;
  }
  v16 = (_QWORD *)v14;
  while ( !*(_BYTE *)(v16[1] + 24LL) )
  {
    v17 = v16[1];
    v18 = *(__int64 **)(v17 + 8);
    v19 = *v18;
    if ( v17 == *v18 )
    {
      v20 = v18[2];
      if ( *(_BYTE *)(v20 + 24) )
      {
        v31 = *(_QWORD **)(v17 + 16);
        if ( v16 == v31 )
        {
          v16 = (_QWORD *)v16[1];
          *(_QWORD *)(v17 + 16) = *v31;
          if ( !*(_BYTE *)(*v31 + 25LL) )
            *(_QWORD *)(*v31 + 8LL) = v17;
          v31[1] = *(_QWORD *)(v17 + 8);
          if ( v17 == (*a1)[1] )
          {
            (*a1)[1] = (__int64)v31;
          }
          else
          {
            v32 = *(_QWORD **)(v17 + 8);
            if ( v17 == *v32 )
              *v32 = v31;
            else
              v32[2] = v31;
          }
          *v31 = v17;
          *(_QWORD *)(v17 + 8) = v31;
        }
        *(_BYTE *)(v16[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(v16[1] + 8LL) + 24LL) = 0;
        v33 = *(_QWORD **)(v16[1] + 8LL);
        v34 = *v33;
        *v33 = *(_QWORD *)(*v33 + 16LL);
        v35 = *(_QWORD *)(v34 + 16);
        if ( !*(_BYTE *)(v35 + 25) )
          *(_QWORD *)(v35 + 8) = v33;
        *(_QWORD *)(v34 + 8) = v33[1];
        if ( v33 == (_QWORD *)(*a1)[1] )
        {
          (*a1)[1] = v34;
          *(_QWORD *)(v34 + 16) = v33;
          v33[1] = v34;
        }
        else
        {
          v36 = (_QWORD *)v33[1];
          if ( v33 == (_QWORD *)v36[2] )
            v36[2] = v34;
          else
            *v36 = v34;
          *(_QWORD *)(v34 + 16) = v33;
          v33[1] = v34;
        }
      }
      else
      {
        *(_BYTE *)(v17 + 24) = 1;
        *(_BYTE *)(v20 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(v16[1] + 8LL) + 24LL) = 0;
        v16 = *(_QWORD **)(v16[1] + 8LL);
      }
    }
    else if ( *(_BYTE *)(v19 + 24) )
    {
      v21 = *(_QWORD **)v17;
      if ( v16 == *(_QWORD **)v17 )
      {
        v16 = (_QWORD *)v16[1];
        *(_QWORD *)v17 = v21[2];
        v37 = v21[2];
        if ( !*(_BYTE *)(v37 + 25) )
          *(_QWORD *)(v37 + 8) = v17;
        v21[1] = *(_QWORD *)(v17 + 8);
        if ( v17 == (*a1)[1] )
        {
          (*a1)[1] = (__int64)v21;
          v21[2] = v17;
          *(_QWORD *)(v17 + 8) = v21;
        }
        else
        {
          v38 = *(_QWORD **)(v17 + 8);
          if ( v17 == v38[2] )
            v38[2] = v21;
          else
            *v38 = v21;
          v21[2] = v17;
          *(_QWORD *)(v17 + 8) = v21;
        }
      }
      *(_BYTE *)(v16[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v16[1] + 8LL) + 24LL) = 0;
      v22 = *(_QWORD *)(v16[1] + 8LL);
      v23 = *(_QWORD **)(v22 + 16);
      *(_QWORD *)(v22 + 16) = *v23;
      if ( !*(_BYTE *)(*v23 + 25LL) )
        *(_QWORD *)(*v23 + 8LL) = v22;
      v23[1] = *(_QWORD *)(v22 + 8);
      if ( v22 == (*a1)[1] )
      {
        (*a1)[1] = (__int64)v23;
        *v23 = v22;
        *(_QWORD *)(v22 + 8) = v23;
      }
      else
      {
        v24 = *(_QWORD **)(v22 + 8);
        if ( v22 == *v24 )
          *v24 = v23;
        else
          v24[2] = v23;
        *v23 = v22;
        *(_QWORD *)(v22 + 8) = v23;
      }
    }
    else
    {
      *(_BYTE *)(v17 + 24) = 1;
      *(_BYTE *)(v19 + 24) = 1;
      *(_BYTE *)(*(_QWORD *)(v16[1] + 8LL) + 24LL) = 0;
      v16 = *(_QWORD **)(v16[1] + 8LL);
    }
  }
  *(_BYTE *)((*a1)[1] + 24) = 1;
  *(_QWORD *)a2 = v15;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x180004680  push    rbx
0x180004682  push    rsi
0x180004683  push    rdi
0x180004684  push    r12
0x180004686  push    r14
0x180004688  push    r15
0x18000468a  sub     rsp, 28h
0x18000468e  mov     r15, r9
0x180004691  mov     r14, rdx
0x180004694  mov     r12, rcx
0x180004697  mov     rbx, [rcx]
0x18000469a  mov     rdi, [rbx+8]
0x18000469e  cmp     byte ptr [rdi+19h], 0
0x1800046a2  jnz     short loc_18000470D
0x1800046a4  mov     rbx, rdi
0x1800046a7  mov     rdx, [rdi+20h]
0x1800046ab  mov     rcx, [r15]
0x1800046ae  mov     rdx, [rdx]; String2
0x1800046b1  mov     rcx, [rcx]; String1
0x1800046b4  call    cs:__imp__wcsicmp
0x1800046ba  mov     esi, eax
0x1800046bc  shr     esi, 1Fh
0x1800046bf  test    sil, sil
0x1800046c2  jz      loc_1800047A1
0x1800046c8  mov     rdi, [rdi]
0x1800046cb  cmp     byte ptr [rdi+19h], 0
0x1800046cf  jz      short loc_1800046A4
0x1800046d1  mov     rdi, rbx
0x1800046d4  test    sil, sil
0x1800046d7  jnz     short loc_180004713
0x1800046d9  mov     rdx, [r15]
0x1800046dc  mov     rcx, [rbx+20h]
0x1800046e0  mov     rdx, [rdx]; String2
0x1800046e3  mov     rcx, [rcx]; String1
0x1800046e6  call    cs:__imp__wcsicmp
0x1800046ec  test    eax, eax
0x1800046ee  js      loc_1800048C0
0x1800046f4  mov     [r14], rbx
0x1800046f7  mov     byte ptr [r14+8], 0
0x1800046fc  mov     rax, r14
0x1800046ff  add     rsp, 28h
0x180004703  pop     r15
0x180004705  pop     r14
0x180004707  pop     r12
0x180004709  pop     rdi
0x18000470a  pop     rsi
0x18000470b  pop     rbx
0x18000470c  retn
0x18000470d  mov     sil, 1
0x180004710  mov     rdi, rbx
0x180004713  mov     rax, [r12]
0x180004717  cmp     rdi, [rax]
0x18000471a  jz      short loc_18000475B
0x18000471c  cmp     byte ptr [rdi+19h], 0
0x180004720  jnz     loc_180004D13
0x180004726  mov     rax, [rdi]
0x180004729  cmp     byte ptr [rax+19h], 0
0x18000472d  jz      loc_180004D1C
0x180004733  mov     rax, [rdi+8]
0x180004737  cmp     byte ptr [rax+19h], 0
0x18000473b  jnz     short loc_180004742
0x18000473d  cmp     rbx, [rax]
0x180004740  jz      short loc_18000474C
0x180004742  cmp     byte ptr [rbx+19h], 0
0x180004746  cmovz   rbx, rax
0x18000474a  jmp     short loc_1800046D9
0x18000474c  mov     rbx, rax
0x18000474f  mov     rax, [rax+8]
0x180004753  cmp     byte ptr [rax+19h], 0
0x180004757  jz      short loc_18000473D
0x180004759  jmp     short loc_180004742
0x18000475b  mov     rax, 666666666666665h
0x180004765  cmp     [r12+8], rax
0x18000476a  jnb     loc_180004D07
0x180004770  mov     rdx, r15
0x180004773  mov     rcx, r12
0x180004776  call    ??$_Buynode@PEAVCPathNode@XPerfCore@@@?$_Tree_buy@PEAVCPathNode@XPerfCore@@V?$allocator@PEAVCPathNode@XPerfCore@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVCPathNode@XPerfCore@@PEAX@1@$$QEAPEAVCPathNode@XPerfCore@@@Z; std::_Tree_buy<XPerfCore::CPathNode *>::_Buynode<XPerfCore::CPathNode *>(XPerfCore::CPathNode * &&)
0x18000477b  mov     r9, rax
0x18000477e  inc     qword ptr [r12+8]
0x180004783  mov     [rax+8], rdi
0x180004787  mov     rax, [r12]
0x18000478b  cmp     rdi, rax
0x18000478e  jz      short loc_1800047AA
0x180004790  mov     [rdi], r9
0x180004793  mov     rax, [r12]
0x180004797  cmp     rdi, [rax]
0x18000479a  jnz     short loc_1800047BD
0x18000479c  mov     [rax], r9
0x18000479f  jmp     short loc_1800047BD
0x1800047a1  mov     rdi, [rdi+10h]
0x1800047a5  jmp     loc_1800046CB
0x1800047aa  mov     [rax+8], r9
0x1800047ae  mov     rcx, [r12]
0x1800047b2  mov     [rcx], r9
0x1800047b5  mov     rcx, [r12]
0x1800047b9  mov     [rcx+10h], r9
0x1800047bd  mov     rdx, r9
0x1800047c0  mov     rax, [r9+8]
0x1800047c4  cmp     byte ptr [rax+18h], 0
0x1800047c8  jnz     short loc_180004806
0x1800047ca  mov     rcx, [rdx+8]
0x1800047ce  mov     r8, [rcx+8]
0x1800047d2  mov     rax, [r8]
0x1800047d5  cmp     rcx, rax
0x1800047d8  jz      short loc_180004822
0x1800047da  cmp     byte ptr [rax+18h], 0
0x1800047de  jnz     short loc_18000484E
0x1800047e0  mov     byte ptr [rcx+18h], 1
0x1800047e4  mov     byte ptr [rax+18h], 1
0x1800047e8  mov     rax, [rdx+8]
0x1800047ec  mov     rcx, [rax+8]
0x1800047f0  mov     byte ptr [rcx+18h], 0
0x1800047f4  mov     rax, [rdx+8]
0x1800047f8  mov     rdx, [rax+8]
0x1800047fc  mov     rax, [rdx+8]
0x180004800  cmp     byte ptr [rax+18h], 0
0x180004804  jz      short loc_1800047CA
0x180004806  mov     rax, [r12]
0x18000480a  mov     rcx, [rax+8]
0x18000480e  mov     byte ptr [rcx+18h], 1
0x180004812  mov     [r14], r9
0x180004815  mov     byte ptr [r14+8], 1
0x18000481a  mov     rax, r14
0x18000481d  jmp     loc_1800046FF
0x180004822  mov     rax, [r8+10h]
0x180004826  cmp     byte ptr [rax+18h], 0
0x18000482a  jnz     loc_180004981
0x180004830  mov     byte ptr [rcx+18h], 1
0x180004834  mov     byte ptr [rax+18h], 1
0x180004838  mov     rax, [rdx+8]
0x18000483c  mov     rcx, [rax+8]
0x180004840  mov     byte ptr [rcx+18h], 0
0x180004844  mov     rax, [rdx+8]
0x180004848  mov     rdx, [rax+8]
0x18000484c  jmp     short loc_1800047FC
0x18000484e  mov     r8, [rcx]
0x180004851  cmp     rdx, r8
0x180004854  jz      loc_180004A37
0x18000485a  mov     rax, [rdx+8]
0x18000485e  mov     byte ptr [rax+18h], 1
0x180004862  mov     rax, [rdx+8]
0x180004866  mov     rcx, [rax+8]
0x18000486a  mov     byte ptr [rcx+18h], 0
0x18000486e  mov     rax, [rdx+8]
0x180004872  mov     rcx, [rax+8]
0x180004876  mov     r8, [rcx+10h]
0x18000487a  mov     rax, [r8]
0x18000487d  mov     [rcx+10h], rax
0x180004881  mov     rax, [r8]
0x180004884  cmp     byte ptr [rax+19h], 0
0x180004888  jnz     short loc_18000488E
0x18000488a  mov     [rax+8], rcx
0x18000488e  mov     rax, [rcx+8]
0x180004892  mov     [r8+8], rax
0x180004896  mov     rax, [r12]
0x18000489a  cmp     rcx, [rax+8]
0x18000489e  jz      loc_180004C4F
0x1800048a4  mov     rax, [rcx+8]
0x1800048a8  cmp     rcx, [rax]
0x1800048ab  jnz     loc_180004AB3
0x1800048b1  mov     [rax], r8
0x1800048b4  mov     [r8], rcx
0x1800048b7  mov     [rcx+8], r8
0x1800048bb  jmp     loc_1800047FC
0x1800048c0  mov     rax, 666666666666665h
0x1800048ca  cmp     [r12+8], rax
0x1800048cf  jnb     loc_180004D40
0x1800048d5  mov     rdx, r15
0x1800048d8  mov     rcx, r12
0x1800048db  call    ??$_Buynode@PEAVCPathNode@XPerfCore@@@?$_Tree_buy@PEAVCPathNode@XPerfCore@@V?$allocator@PEAVCPathNode@XPerfCore@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAVCPathNode@XPerfCore@@PEAX@1@$$QEAPEAVCPathNode@XPerfCore@@@Z; std::_Tree_buy<XPerfCore::CPathNode *>::_Buynode<XPerfCore::CPathNode *>(XPerfCore::CPathNode * &&)
0x1800048e0  mov     r8, rax
0x1800048e3  inc     qword ptr [r12+8]
0x1800048e8  mov     [rax+8], rdi
0x1800048ec  mov     rax, [r12]
0x1800048f0  cmp     rdi, rax
0x1800048f3  jz      loc_180004B47
0x1800048f9  test    sil, sil
0x1800048fc  jnz     loc_180004B5F
0x180004902  mov     [rdi+10h], r8
0x180004906  mov     rax, [r12]
0x18000490a  cmp     rdi, [rax+10h]
0x18000490e  jnz     short loc_180004914
0x180004910  mov     [rax+10h], r8
0x180004914  mov     rdx, r8
0x180004917  mov     rax, [r8+8]
0x18000491b  cmp     byte ptr [rax+18h], 0
0x18000491f  jnz     short loc_180004965
0x180004921  mov     rcx, [rdx+8]
0x180004925  mov     r9, [rcx+8]
0x180004929  mov     rax, [r9]
0x18000492c  cmp     rcx, rax
0x18000492f  jz      loc_180004A84
0x180004935  cmp     byte ptr [rax+18h], 0
0x180004939  jnz     loc_180004ABC
0x18000493f  mov     byte ptr [rcx+18h], 1
0x180004943  mov     byte ptr [rax+18h], 1
0x180004947  mov     rax, [rdx+8]
0x18000494b  mov     rcx, [rax+8]
0x18000494f  mov     byte ptr [rcx+18h], 0
0x180004953  mov     rax, [rdx+8]
0x180004957  mov     rdx, [rax+8]
0x18000495b  mov     rax, [rdx+8]
0x18000495f  cmp     byte ptr [rax+18h], 0
0x180004963  jz      short loc_180004921
0x180004965  mov     rax, [r12]
0x180004969  mov     rcx, [rax+8]
0x18000496d  mov     byte ptr [rcx+18h], 1
0x180004971  mov     [r14], r8
0x180004974  mov     byte ptr [r14+8], 1
0x180004979  mov     rax, r14
0x18000497c  jmp     loc_1800046FF
0x180004981  mov     r8, [rcx+10h]
0x180004985  cmp     rdx, r8
0x180004988  jnz     short loc_1800049CE
0x18000498a  mov     rdx, rcx
0x18000498d  mov     rax, [r8]
0x180004990  mov     [rcx+10h], rax
0x180004994  mov     rax, [r8]
0x180004997  cmp     byte ptr [rax+19h], 0
0x18000499b  jnz     short loc_1800049A1
0x18000499d  mov     [rax+8], rcx
0x1800049a1  mov     rax, [rcx+8]
0x1800049a5  mov     [r8+8], rax
0x1800049a9  mov     rax, [r12]
0x1800049ad  cmp     rcx, [rax+8]
0x1800049b1  jz      loc_180004CAD
0x1800049b7  mov     rax, [rcx+8]
0x1800049bb  cmp     rcx, [rax]
0x1800049be  jnz     loc_180004C2D
0x1800049c4  mov     [rax], r8
0x1800049c7  mov     [r8], rcx
0x1800049ca  mov     [rcx+8], r8
0x1800049ce  mov     rax, [rdx+8]
0x1800049d2  mov     byte ptr [rax+18h], 1
0x1800049d6  mov     rax, [rdx+8]
0x1800049da  mov     rcx, [rax+8]
0x1800049de  mov     byte ptr [rcx+18h], 0
0x1800049e2  mov     rax, [rdx+8]
0x1800049e6  mov     rcx, [rax+8]
0x1800049ea  mov     r8, [rcx]
0x1800049ed  mov     rax, [r8+10h]
0x1800049f1  mov     [rcx], rax
0x1800049f4  mov     rax, [r8+10h]
0x1800049f8  cmp     byte ptr [rax+19h], 0
0x1800049fc  jnz     short loc_180004A02
0x1800049fe  mov     [rax+8], rcx
0x180004a02  mov     rax, [rcx+8]
0x180004a06  mov     [r8+8], rax
0x180004a0a  mov     rax, [r12]
0x180004a0e  cmp     rcx, [rax+8]
0x180004a12  jz      loc_180004B2E
0x180004a18  mov     rax, [rcx+8]
0x180004a1c  cmp     rcx, [rax+10h]
0x180004a20  jnz     loc_180004B3F
0x180004a26  mov     [rax+10h], r8
0x180004a2a  mov     [r8+10h], rcx
0x180004a2e  mov     [rcx+8], r8
0x180004a32  jmp     loc_1800047FC
0x180004a37  mov     rdx, rcx
0x180004a3a  mov     rax, [r8+10h]
0x180004a3e  mov     [rcx], rax
0x180004a41  mov     rax, [r8+10h]
0x180004a45  cmp     byte ptr [rax+19h], 0
0x180004a49  jnz     short loc_180004A4F
0x180004a4b  mov     [rax+8], rcx
0x180004a4f  mov     rax, [rcx+8]
0x180004a53  mov     [r8+8], rax
0x180004a57  mov     rax, [r12]
0x180004a5b  cmp     rcx, [rax+8]
0x180004a5f  jz      loc_180004C36
0x180004a65  mov     rax, [rcx+8]
0x180004a69  cmp     rcx, [rax+10h]
0x180004a6d  jnz     loc_180004C47
0x180004a73  mov     [rax+10h], r8
0x180004a77  mov     [r8+10h], rcx
0x180004a7b  mov     [rcx+8], r8
0x180004a7f  jmp     loc_18000485A
0x180004a84  mov     rax, [r9+10h]
0x180004a88  cmp     byte ptr [rax+18h], 0
0x180004a8c  jnz     loc_180004B77
0x180004a92  mov     byte ptr [rcx+18h], 1
0x180004a96  mov     byte ptr [rax+18h], 1
0x180004a9a  mov     rax, [rdx+8]
0x180004a9e  mov     rcx, [rax+8]
0x180004aa2  mov     byte ptr [rcx+18h], 0
0x180004aa6  mov     rax, [rdx+8]
0x180004aaa  mov     rdx, [rax+8]
0x180004aae  jmp     loc_18000495B
0x180004ab3  mov     [rax+10h], r8
0x180004ab7  jmp     loc_1800048B4
0x180004abc  mov     r9, [rcx]
0x180004abf  cmp     rdx, r9
0x180004ac2  jz      loc_180004C5F
0x180004ac8  mov     rax, [rdx+8]
0x180004acc  mov     byte ptr [rax+18h], 1
0x180004ad0  mov     rax, [rdx+8]
0x180004ad4  mov     rcx, [rax+8]
0x180004ad8  mov     byte ptr [rcx+18h], 0
0x180004adc  mov     rax, [rdx+8]
0x180004ae0  mov     rcx, [rax+8]
  ... truncated ...
```
