# std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::_Insert_at<std::pair<ulong const,CounterHelper *> &,std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *>(bool,std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *,std::pair<ulong const,CounterHelper *> &,std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)

- ea: `0x180004220`
- end: `0x18000449c`
- name: `??$_Insert_at@AEAU?$pair@$$CBKPEAVCounterHelper@@@std@@PEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@1@AEAU?$pair@$$CBKPEAVCounterHelper@@@1@1@Z`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800044a4`
- `0x18000469c`

## callees

- `0x180002128`
- `0x180004220`
- `0x180008f28`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::_Insert_at<std::pair<unsigned long const,CounterHelper *> &,std::_Tree_node<std::pair<unsigned long const,CounterHelper *>,void *> *>(
        _QWORD *a1,
        _QWORD *a2,
        char a3,
        _QWORD *a4,
        int a5,
        __int64 a6)
{
  unsigned __int64 v6; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 *v13; // r8
  __int64 *v14; // rax
  __int64 *v15; // r8
  __int64 **v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  if ( v6 >= 0x555555555555554LL )
  {
    std::_Tree_buy<std::pair<unsigned long const,CounterHelper *>>::_Freenode0(0x555555555555554LL, a6);
    std::_Xlength_error("map/set<T> too long");
  }
  a1[1] = v6 + 1;
  *(_QWORD *)(a6 + 8) = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8LL) = a6;
    *(_QWORD *)*a1 = a6;
    v9 = *a1;
LABEL_8:
    *(_QWORD *)(v9 + 16) = a6;
    goto LABEL_9;
  }
  if ( a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_9;
  }
  a4[2] = a6;
  v9 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16LL) )
    goto LABEL_8;
LABEL_9:
  v10 = *(_QWORD *)(a6 + 8);
  v11 = a6;
  while ( !*(_BYTE *)(v10 + 24) )
  {
    v12 = *(__int64 **)(v11 + 8);
    v13 = (__int64 *)v12[1];
    v14 = (__int64 *)*v13;
    if ( v12 == (__int64 *)*v13 )
    {
      v14 = (__int64 *)v13[2];
      if ( !*((_BYTE *)v14 + 24) )
        goto LABEL_30;
      v15 = (__int64 *)v12[2];
      if ( (__int64 *)v11 == v15 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        v12[2] = *v15;
        if ( !*(_BYTE *)(*v15 + 25) )
          *(_QWORD *)(*v15 + 8) = v12;
        v15[1] = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v15;
        }
        else
        {
          v16 = (__int64 **)v12[1];
          if ( v12 == *v16 )
            *v16 = v15;
          else
            v16[2] = v15;
        }
        *v15 = (__int64)v12;
        v12[1] = (__int64)v15;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)*v17;
      *v17 = *(_QWORD *)(*v17 + 16LL);
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 25) )
        *(_QWORD *)(v19 + 8) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v20 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)v20[2] )
          v20[2] = v18;
        else
          *v20 = v18;
      }
      v18[2] = v17;
    }
    else
    {
      if ( !*((_BYTE *)v14 + 24) )
      {
LABEL_30:
        *((_BYTE *)v12 + 24) = 1;
        *((_BYTE *)v14 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
        v11 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
        goto LABEL_49;
      }
      v21 = *v12;
      if ( v11 == *v12 )
      {
        v11 = *(_QWORD *)(v11 + 8);
        *v12 = *(_QWORD *)(v21 + 16);
        v22 = *(_QWORD *)(v21 + 16);
        if ( !*(_BYTE *)(v22 + 25) )
          *(_QWORD *)(v22 + 8) = v12;
        *(_QWORD *)(v21 + 8) = v12[1];
        if ( v12 == *(__int64 **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v21;
        }
        else
        {
          v23 = (_QWORD *)v12[1];
          if ( v12 == (__int64 *)v23[2] )
            v23[2] = v21;
          else
            *v23 = v21;
        }
        *(_QWORD *)(v21 + 16) = v12;
        v12[1] = v21;
      }
      *(_BYTE *)(*(_QWORD *)(v11 + 8) + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL) + 24LL) = 0;
      v17 = *(_QWORD **)(*(_QWORD *)(v11 + 8) + 8LL);
      v18 = (_QWORD *)v17[2];
      v17[2] = *v18;
      if ( !*(_BYTE *)(*v18 + 25LL) )
        *(_QWORD *)(*v18 + 8LL) = v17;
      v18[1] = v17[1];
      if ( v17 == *(_QWORD **)(*a1 + 8LL) )
      {
        *(_QWORD *)(*a1 + 8LL) = v18;
      }
      else
      {
        v24 = (_QWORD *)v17[1];
        if ( v17 == (_QWORD *)*v24 )
          *v24 = v18;
        else
          v24[2] = v18;
      }
      *v18 = v17;
    }
    v17[1] = v18;
LABEL_49:
    v10 = *(_QWORD *)(v11 + 8);
  }
  v25 = *a1;
  *a2 = a6;
  v26 = *(_QWORD *)(v25 + 8);
  result = a2;
  *(_BYTE *)(v26 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  push    rdi
0x180004226  sub     rsp, 20h
0x18000422a  mov     rax, [rcx+8]
0x18000422e  mov     r11, rcx
0x180004231  mov     rcx, 555555555555554h
0x18000423b  mov     r10, r9
0x18000423e  mov     rbx, rdx
0x180004241  cmp     rax, rcx
0x180004244  jnb     loc_180004485
0x18000424a  mov     r9, [rsp+28h+arg_28]
0x18000424f  inc     rax
0x180004252  mov     [r11+8], rax
0x180004256  xor     edi, edi
0x180004258  mov     [r9+8], r10
0x18000425c  mov     rax, [r11]
0x18000425f  cmp     r10, rax
0x180004262  jnz     short loc_180004273
0x180004264  mov     [rax+8], r9
0x180004268  mov     rax, [r11]
0x18000426b  mov     [rax], r9
0x18000426e  mov     rax, [r11]
0x180004271  jmp     short loc_180004295
0x180004273  test    r8b, r8b
0x180004276  jz      short loc_180004288
0x180004278  mov     [r10], r9
0x18000427b  mov     rax, [r11]
0x18000427e  cmp     r10, [rax]
0x180004281  jnz     short loc_180004299
0x180004283  mov     [rax], r9
0x180004286  jmp     short loc_180004299
0x180004288  mov     [r10+10h], r9
0x18000428c  mov     rax, [r11]
0x18000428f  cmp     r10, [rax+10h]
0x180004293  jnz     short loc_180004299
0x180004295  mov     [rax+10h], r9
0x180004299  mov     rax, [r9+8]
0x18000429d  mov     rdx, r9
0x1800042a0  jmp     loc_18000445F
0x1800042a5  mov     rcx, [rdx+8]
0x1800042a9  mov     r8, [rcx+8]
0x1800042ad  mov     rax, [r8]
0x1800042b0  cmp     rcx, rax
0x1800042b3  jnz     loc_18000437E
0x1800042b9  mov     rax, [r8+10h]
0x1800042bd  cmp     [rax+18h], dil
0x1800042c1  jz      loc_180004384
0x1800042c7  mov     r8, [rcx+10h]
0x1800042cb  cmp     rdx, r8
0x1800042ce  jnz     short loc_180004317
0x1800042d0  mov     rax, [r8]
0x1800042d3  mov     rdx, rcx
0x1800042d6  mov     [rcx+10h], rax
0x1800042da  mov     rax, [r8]
0x1800042dd  cmp     [rax+19h], dil
0x1800042e1  jnz     short loc_1800042E7
0x1800042e3  mov     [rax+8], rcx
0x1800042e7  mov     rax, [rcx+8]
0x1800042eb  mov     [r8+8], rax
0x1800042ef  mov     rax, [r11]
0x1800042f2  cmp     rcx, [rax+8]
0x1800042f6  jnz     short loc_1800042FE
0x1800042f8  mov     [rax+8], r8
0x1800042fc  jmp     short loc_180004310
0x1800042fe  mov     rax, [rcx+8]
0x180004302  cmp     rcx, [rax]
0x180004305  jnz     short loc_18000430C
0x180004307  mov     [rax], r8
0x18000430a  jmp     short loc_180004310
0x18000430c  mov     [rax+10h], r8
0x180004310  mov     [r8], rcx
0x180004313  mov     [rcx+8], r8
0x180004317  mov     rax, [rdx+8]
0x18000431b  mov     byte ptr [rax+18h], 1
0x18000431f  mov     rax, [rdx+8]
0x180004323  mov     rcx, [rax+8]
0x180004327  mov     [rcx+18h], dil
0x18000432b  mov     rax, [rdx+8]
0x18000432f  mov     rcx, [rax+8]
0x180004333  mov     r8, [rcx]
0x180004336  mov     rax, [r8+10h]
0x18000433a  mov     [rcx], rax
0x18000433d  mov     rax, [r8+10h]
0x180004341  cmp     [rax+19h], dil
0x180004345  jnz     short loc_18000434B
0x180004347  mov     [rax+8], rcx
0x18000434b  mov     rax, [rcx+8]
0x18000434f  mov     [r8+8], rax
0x180004353  mov     rax, [r11]
0x180004356  cmp     rcx, [rax+8]
0x18000435a  jnz     short loc_180004362
0x18000435c  mov     [rax+8], r8
0x180004360  jmp     short loc_180004375
0x180004362  mov     rax, [rcx+8]
0x180004366  cmp     rcx, [rax+10h]
0x18000436a  jnz     short loc_180004372
0x18000436c  mov     [rax+10h], r8
0x180004370  jmp     short loc_180004375
0x180004372  mov     [rax], r8
0x180004375  mov     [r8+10h], rcx
0x180004379  jmp     loc_180004457
0x18000437e  cmp     [rax+18h], dil
0x180004382  jnz     short loc_1800043A5
0x180004384  mov     byte ptr [rcx+18h], 1
0x180004388  mov     byte ptr [rax+18h], 1
0x18000438c  mov     rax, [rdx+8]
0x180004390  mov     rcx, [rax+8]
0x180004394  mov     [rcx+18h], dil
0x180004398  mov     rax, [rdx+8]
0x18000439c  mov     rdx, [rax+8]
0x1800043a0  jmp     loc_18000445B
0x1800043a5  mov     r8, [rcx]
0x1800043a8  cmp     rdx, r8
0x1800043ab  jnz     short loc_1800043F7
0x1800043ad  mov     rax, [r8+10h]
0x1800043b1  mov     rdx, rcx
0x1800043b4  mov     [rcx], rax
0x1800043b7  mov     rax, [r8+10h]
0x1800043bb  cmp     [rax+19h], dil
0x1800043bf  jnz     short loc_1800043C5
0x1800043c1  mov     [rax+8], rcx
0x1800043c5  mov     rax, [rcx+8]
0x1800043c9  mov     [r8+8], rax
0x1800043cd  mov     rax, [r11]
0x1800043d0  cmp     rcx, [rax+8]
0x1800043d4  jnz     short loc_1800043DC
0x1800043d6  mov     [rax+8], r8
0x1800043da  jmp     short loc_1800043EF
0x1800043dc  mov     rax, [rcx+8]
0x1800043e0  cmp     rcx, [rax+10h]
0x1800043e4  jnz     short loc_1800043EC
0x1800043e6  mov     [rax+10h], r8
0x1800043ea  jmp     short loc_1800043EF
0x1800043ec  mov     [rax], r8
0x1800043ef  mov     [r8+10h], rcx
0x1800043f3  mov     [rcx+8], r8
0x1800043f7  mov     rax, [rdx+8]
0x1800043fb  mov     byte ptr [rax+18h], 1
0x1800043ff  mov     rax, [rdx+8]
0x180004403  mov     rcx, [rax+8]
0x180004407  mov     [rcx+18h], dil
0x18000440b  mov     rax, [rdx+8]
0x18000440f  mov     rcx, [rax+8]
0x180004413  mov     r8, [rcx+10h]
0x180004417  mov     rax, [r8]
0x18000441a  mov     [rcx+10h], rax
0x18000441e  mov     rax, [r8]
0x180004421  cmp     [rax+19h], dil
0x180004425  jnz     short loc_18000442B
0x180004427  mov     [rax+8], rcx
0x18000442b  mov     rax, [rcx+8]
0x18000442f  mov     [r8+8], rax
0x180004433  mov     rax, [r11]
0x180004436  cmp     rcx, [rax+8]
0x18000443a  jnz     short loc_180004442
0x18000443c  mov     [rax+8], r8
0x180004440  jmp     short loc_180004454
0x180004442  mov     rax, [rcx+8]
0x180004446  cmp     rcx, [rax]
0x180004449  jnz     short loc_180004450
0x18000444b  mov     [rax], r8
0x18000444e  jmp     short loc_180004454
0x180004450  mov     [rax+10h], r8
0x180004454  mov     [r8], rcx
0x180004457  mov     [rcx+8], r8
0x18000445b  mov     rax, [rdx+8]
0x18000445f  cmp     [rax+18h], dil
0x180004463  jz      loc_1800042A5
0x180004469  mov     rax, [r11]
0x18000446c  mov     [rbx], r9
0x18000446f  mov     rcx, [rax+8]
0x180004473  mov     rax, rbx
0x180004476  mov     rbx, [rsp+28h+arg_0]
0x18000447b  mov     byte ptr [rcx+18h], 1
0x18000447f  add     rsp, 20h
0x180004483  pop     rdi
0x180004484  retn
0x180004485  mov     rdx, [rsp+28h+arg_28]
0x18000448a  call    ?_Freenode0@?$_Tree_buy@U?$pair@$$CBKPEAVCounterHelper@@@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVCounterHelper@@@std@@PEAX@2@@Z; std::_Tree_buy<std::pair<ulong const,CounterHelper *>>::_Freenode0(std::_Tree_node<std::pair<ulong const,CounterHelper *>,void *> *)
0x18000448f  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180004496  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
