# std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(ulong const &)

- ea: `0x1800095e8`
- end: `0x1800096d9`
- name: `?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA_KAEBK@Z`
- size: `241`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005be0`
- `0x180007ecc`
- `0x180007f88`

## callees

- `0x18000906c`
- `0x1800095e8`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
        __int64 ***a1,
        unsigned int *a2)
{
  __int64 *v2; // r11
  __int64 v4; // r9
  __int64 v5; // rax
  __int64 v6; // r8
  unsigned int v7; // r10d
  __int64 v8; // rbx
  __int64 *v9; // rax
  __int64 i; // rcx
  __int64 v11; // rdx
  __int64 *v13; // [rsp+30h] [rbp+8h] BYREF

  v2 = (__int64 *)*a1;
  v4 = (__int64)*a1;
  v5 = (__int64)(*a1)[1];
  v6 = v5;
  if ( !*(_BYTE *)(v5 + 25) )
  {
    v7 = *a2;
    do
    {
      if ( *(_DWORD *)(v6 + 32) >= v7 )
      {
        if ( *(_BYTE *)(v4 + 25) && v7 < *(_DWORD *)(v6 + 32) )
          v4 = v6;
        v2 = (__int64 *)v6;
        v6 = *(_QWORD *)v6;
      }
      else
      {
        v6 = *(_QWORD *)(v6 + 16);
      }
    }
    while ( !*(_BYTE *)(v6 + 25) );
  }
  if ( !*(_BYTE *)(v4 + 25) )
    v5 = *(_QWORD *)v4;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    if ( *a2 >= *(_DWORD *)(v5 + 32) )
    {
      v5 = *(_QWORD *)(v5 + 16);
    }
    else
    {
      v4 = v5;
      v5 = *(_QWORD *)v5;
    }
  }
  v8 = 0;
  v9 = v2;
  while ( v9 != (__int64 *)v4 )
  {
    ++v8;
    if ( !*((_BYTE *)v9 + 25) )
    {
      i = v9[2];
      if ( *(_BYTE *)(i + 25) )
      {
        for ( i = v9[1]; !*(_BYTE *)(i + 25) && v9 == *(__int64 **)(i + 16); i = *(_QWORD *)(i + 8) )
          v9 = (__int64 *)i;
LABEL_28:
        v9 = (__int64 *)i;
      }
      else
      {
        v11 = *(_QWORD *)i;
        if ( *(_BYTE *)(*(_QWORD *)i + 25LL) )
          goto LABEL_28;
        do
        {
          v9 = (__int64 *)v11;
          v11 = *(_QWORD *)v11;
        }
        while ( !*(_BYTE *)(v11 + 25) );
      }
    }
  }
  std::_Tree<std::_Tmap_traits<unsigned long,CounterHelper *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,CounterHelper *>>,0>>::erase(
    a1,
    &v13,
    v2,
    (__int64 *)v4);
  return v8;
}

```

## disassembly

```asm
0x1800095e8  mov     [rsp+arg_8], rbx
0x1800095ed  mov     [rsp+arg_10], rsi
0x1800095f2  push    rdi
0x1800095f3  sub     rsp, 20h
0x1800095f7  mov     r11, [rcx]
0x1800095fa  xor     esi, esi
0x1800095fc  mov     rdi, rcx
0x1800095ff  mov     r9, r11
0x180009602  mov     rax, [r11+8]
0x180009606  mov     r8, rax
0x180009609  cmp     [rax+19h], sil
0x18000960d  jnz     short loc_180009638
0x18000960f  mov     r10d, [rdx]
0x180009612  cmp     [r8+20h], r10d
0x180009616  jnb     short loc_18000961E
0x180009618  mov     r8, [r8+10h]
0x18000961c  jmp     short loc_180009632
0x18000961e  cmp     [r9+19h], sil
0x180009622  jz      short loc_18000962C
0x180009624  cmp     r10d, [r8+20h]
0x180009628  cmovb   r9, r8
0x18000962c  mov     r11, r8
0x18000962f  mov     r8, [r8]
0x180009632  cmp     [r8+19h], sil
0x180009636  jz      short loc_180009612
0x180009638  cmp     [r9+19h], sil
0x18000963c  jnz     short loc_180009641
0x18000963e  mov     rax, [r9]
0x180009641  cmp     [rax+19h], sil
0x180009645  jnz     short loc_180009660
0x180009647  mov     ecx, [rdx]
0x180009649  cmp     ecx, [rax+20h]
0x18000964c  jnb     short loc_180009656
0x18000964e  mov     r9, rax
0x180009651  mov     rax, [rax]
0x180009654  jmp     short loc_18000965A
0x180009656  mov     rax, [rax+10h]
0x18000965a  cmp     [rax+19h], sil
0x18000965e  jz      short loc_180009649
0x180009660  mov     rbx, rsi
0x180009663  mov     rax, r11
0x180009666  cmp     rax, r9
0x180009669  jz      short loc_1800096B6
0x18000966b  inc     rbx
0x18000966e  cmp     [rax+19h], sil
0x180009672  jnz     short loc_180009666
0x180009674  mov     rcx, [rax+10h]
0x180009678  cmp     [rcx+19h], sil
0x18000967c  jnz     short loc_180009698
0x18000967e  mov     rdx, [rcx]
0x180009681  cmp     [rdx+19h], sil
0x180009685  jnz     short loc_1800096B1
0x180009687  mov     rcx, [rdx]
0x18000968a  mov     rax, rdx
0x18000968d  mov     rdx, rcx
0x180009690  cmp     [rcx+19h], sil
0x180009694  jz      short loc_180009687
0x180009696  jmp     short loc_180009666
0x180009698  mov     rcx, [rax+8]
0x18000969c  jmp     short loc_1800096AB
0x18000969e  cmp     rax, [rcx+10h]
0x1800096a2  jnz     short loc_1800096B1
0x1800096a4  mov     rax, rcx
0x1800096a7  mov     rcx, [rcx+8]
0x1800096ab  cmp     [rcx+19h], sil
0x1800096af  jz      short loc_18000969E
0x1800096b1  mov     rax, rcx
0x1800096b4  jmp     short loc_180009666
0x1800096b6  mov     r8, r11
0x1800096b9  lea     rdx, [rsp+28h+arg_0]
0x1800096be  mov     rcx, rdi
0x1800096c1  call    ?erase@?$_Tree@V?$_Tmap_traits@KPEAVCounterHelper@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAVCounterHelper@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCounterHelper@@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<ulong,CounterHelper *,std::less<ulong>,std::allocator<std::pair<ulong const,CounterHelper *>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CounterHelper *>>>>)
0x1800096c6  mov     rsi, [rsp+28h+arg_10]
0x1800096cb  mov     rax, rbx
0x1800096ce  mov     rbx, [rsp+28h+arg_8]
0x1800096d3  add     rsp, 20h
0x1800096d7  pop     rdi
0x1800096d8  retn
```
