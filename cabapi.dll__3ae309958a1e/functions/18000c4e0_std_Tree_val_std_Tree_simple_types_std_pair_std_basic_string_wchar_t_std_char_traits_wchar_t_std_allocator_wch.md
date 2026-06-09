# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,void *> *>,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>,void *> * const)

- ea: `0x18000c4e0`
- end: `0x18000c709`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000af44`
- `0x18000dc30`
- `0x18000dd60`
- `0x18000debc`

## callees

- `0x18000c4e0`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Insert_node(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // r10
  _QWORD *v5; // rax
  __int64 v6; // rax
  _QWORD *i; // rdx
  __int64 v8; // rcx
  __int64 *v9; // r9
  __int64 v10; // rax
  _QWORD *v11; // r9
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  _QWORD *v14; // r9
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rax

  ++a1[1];
  v4 = (_QWORD *)*a1;
  v5 = *(_QWORD **)a2;
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a2;
  if ( v5 != v4 )
  {
    if ( *(_DWORD *)(a2 + 8) )
    {
      *v5 = a3;
      if ( v5 == (_QWORD *)*v4 )
        *v4 = a3;
    }
    else
    {
      v5[2] = a3;
      if ( v5 == (_QWORD *)v4[2] )
        v4[2] = a3;
    }
    v6 = *(_QWORD *)(a3 + 8);
    for ( i = (_QWORD *)a3; ; v6 = i[1] )
    {
      if ( *(_BYTE *)(v6 + 24) )
      {
        *(_BYTE *)(v4[1] + 24LL) = 1;
        return a3;
      }
      v8 = i[1];
      v9 = *(__int64 **)(v8 + 8);
      v10 = *v9;
      if ( v8 == *v9 )
      {
        v10 = v9[2];
        if ( !*(_BYTE *)(v10 + 24) )
          goto LABEL_29;
        v11 = *(_QWORD **)(v8 + 16);
        if ( i == v11 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)(v8 + 16) = *v11;
          if ( !*(_BYTE *)(*v11 + 25LL) )
            *(_QWORD *)(*v11 + 8LL) = v8;
          v11[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v11;
          }
          else
          {
            v12 = *(_QWORD **)(v8 + 8);
            if ( v8 == *v12 )
              *v12 = v11;
            else
              v12[2] = v11;
          }
          *v11 = v8;
          *(_QWORD *)(v8 + 8) = v11;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)*v13;
        *v13 = *(_QWORD *)(*v13 + 16LL);
        v15 = v14[2];
        if ( !*(_BYTE *)(v15 + 25) )
          *(_QWORD *)(v15 + 8) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v16 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)v16[2] )
            v16[2] = v14;
          else
            *v16 = v14;
        }
        v14[2] = v13;
      }
      else
      {
        if ( !*(_BYTE *)(v10 + 24) )
        {
LABEL_29:
          *(_BYTE *)(v8 + 24) = 1;
          *(_BYTE *)(v10 + 24) = 1;
          *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
          i = *(_QWORD **)(i[1] + 8LL);
          continue;
        }
        v17 = *(_QWORD **)v8;
        if ( i == *(_QWORD **)v8 )
        {
          i = (_QWORD *)i[1];
          *(_QWORD *)v8 = v17[2];
          v18 = v17[2];
          if ( !*(_BYTE *)(v18 + 25) )
            *(_QWORD *)(v18 + 8) = v8;
          v17[1] = *(_QWORD *)(v8 + 8);
          if ( v8 == *(_QWORD *)(*a1 + 8LL) )
          {
            *(_QWORD *)(*a1 + 8LL) = v17;
          }
          else
          {
            v19 = *(_QWORD **)(v8 + 8);
            if ( v8 == v19[2] )
              v19[2] = v17;
            else
              *v19 = v17;
          }
          v17[2] = v8;
          *(_QWORD *)(v8 + 8) = v17;
        }
        *(_BYTE *)(i[1] + 24LL) = 1;
        *(_BYTE *)(*(_QWORD *)(i[1] + 8LL) + 24LL) = 0;
        v13 = *(_QWORD **)(i[1] + 8LL);
        v14 = (_QWORD *)v13[2];
        v13[2] = *v14;
        if ( !*(_BYTE *)(*v14 + 25LL) )
          *(_QWORD *)(*v14 + 8LL) = v13;
        v14[1] = v13[1];
        if ( v13 == *(_QWORD **)(*a1 + 8LL) )
        {
          *(_QWORD *)(*a1 + 8LL) = v14;
        }
        else
        {
          v20 = (_QWORD *)v13[1];
          if ( v13 == (_QWORD *)*v20 )
            *v20 = v14;
          else
            v20[2] = v14;
        }
        *v14 = v13;
      }
      v13[1] = v14;
    }
  }
  *v4 = a3;
  v4[1] = a3;
  v4[2] = a3;
  *(_BYTE *)(a3 + 24) = 1;
  return a3;
}

```

## disassembly

```asm
0x18000c4e0  mov     [rsp+arg_0], rbx
0x18000c4e5  inc     qword ptr [rcx+8]
0x18000c4e9  mov     r11, rcx
0x18000c4ec  mov     r10, [rcx]
0x18000c4ef  mov     rax, [rdx]
0x18000c4f2  mov     [r8+8], rax
0x18000c4f6  cmp     rax, r10
0x18000c4f9  jnz     short loc_18000C510
0x18000c4fb  mov     [r10], r8
0x18000c4fe  mov     [r10+8], r8
0x18000c502  mov     [r10+10h], r8
0x18000c506  mov     byte ptr [r8+18h], 1
0x18000c50b  jmp     loc_18000C700
0x18000c510  xor     ebx, ebx
0x18000c512  cmp     [rdx+8], ebx
0x18000c515  jnz     short loc_18000C527
0x18000c517  mov     [rax+10h], r8
0x18000c51b  cmp     rax, [r10+10h]
0x18000c51f  jnz     short loc_18000C532
0x18000c521  mov     [r10+10h], r8
0x18000c525  jmp     short loc_18000C532
0x18000c527  mov     [rax], r8
0x18000c52a  cmp     rax, [r10]
0x18000c52d  jnz     short loc_18000C532
0x18000c52f  mov     [r10], r8
0x18000c532  mov     rax, [r8+8]
0x18000c536  mov     rdx, r8
0x18000c539  jmp     loc_18000C6EF
0x18000c53e  mov     rcx, [rdx+8]
0x18000c542  mov     r9, [rcx+8]
0x18000c546  mov     rax, [r9]
0x18000c549  cmp     rcx, rax
0x18000c54c  jnz     loc_18000C613
0x18000c552  mov     rax, [r9+10h]
0x18000c556  cmp     [rax+18h], bl
0x18000c559  jz      loc_18000C618
0x18000c55f  mov     r9, [rcx+10h]
0x18000c563  cmp     rdx, r9
0x18000c566  jnz     short loc_18000C5AE
0x18000c568  mov     rax, [r9]
0x18000c56b  mov     rdx, rcx
0x18000c56e  mov     [rcx+10h], rax
0x18000c572  mov     rax, [r9]
0x18000c575  cmp     [rax+19h], bl
0x18000c578  jnz     short loc_18000C57E
0x18000c57a  mov     [rax+8], rcx
0x18000c57e  mov     rax, [rcx+8]
0x18000c582  mov     [r9+8], rax
0x18000c586  mov     rax, [r11]
0x18000c589  cmp     rcx, [rax+8]
0x18000c58d  jnz     short loc_18000C595
0x18000c58f  mov     [rax+8], r9
0x18000c593  jmp     short loc_18000C5A7
0x18000c595  mov     rax, [rcx+8]
0x18000c599  cmp     rcx, [rax]
0x18000c59c  jnz     short loc_18000C5A3
0x18000c59e  mov     [rax], r9
0x18000c5a1  jmp     short loc_18000C5A7
0x18000c5a3  mov     [rax+10h], r9
0x18000c5a7  mov     [r9], rcx
0x18000c5aa  mov     [rcx+8], r9
0x18000c5ae  mov     rax, [rdx+8]
0x18000c5b2  mov     byte ptr [rax+18h], 1
0x18000c5b6  mov     rax, [rdx+8]
0x18000c5ba  mov     rcx, [rax+8]
0x18000c5be  mov     [rcx+18h], bl
0x18000c5c1  mov     rax, [rdx+8]
0x18000c5c5  mov     rcx, [rax+8]
0x18000c5c9  mov     r9, [rcx]
0x18000c5cc  mov     rax, [r9+10h]
0x18000c5d0  mov     [rcx], rax
0x18000c5d3  mov     rax, [r9+10h]
0x18000c5d7  cmp     [rax+19h], bl
0x18000c5da  jnz     short loc_18000C5E0
0x18000c5dc  mov     [rax+8], rcx
0x18000c5e0  mov     rax, [rcx+8]
0x18000c5e4  mov     [r9+8], rax
0x18000c5e8  mov     rax, [r11]
0x18000c5eb  cmp     rcx, [rax+8]
0x18000c5ef  jnz     short loc_18000C5F7
0x18000c5f1  mov     [rax+8], r9
0x18000c5f5  jmp     short loc_18000C60A
0x18000c5f7  mov     rax, [rcx+8]
0x18000c5fb  cmp     rcx, [rax+10h]
0x18000c5ff  jnz     short loc_18000C607
0x18000c601  mov     [rax+10h], r9
0x18000c605  jmp     short loc_18000C60A
0x18000c607  mov     [rax], r9
0x18000c60a  mov     [r9+10h], rcx
0x18000c60e  jmp     loc_18000C6E7
0x18000c613  cmp     [rax+18h], bl
0x18000c616  jnz     short loc_18000C638
0x18000c618  mov     byte ptr [rcx+18h], 1
0x18000c61c  mov     byte ptr [rax+18h], 1
0x18000c620  mov     rax, [rdx+8]
0x18000c624  mov     rcx, [rax+8]
0x18000c628  mov     [rcx+18h], bl
0x18000c62b  mov     rax, [rdx+8]
0x18000c62f  mov     rdx, [rax+8]
0x18000c633  jmp     loc_18000C6EB
0x18000c638  mov     r9, [rcx]
0x18000c63b  cmp     rdx, r9
0x18000c63e  jnz     short loc_18000C689
0x18000c640  mov     rax, [r9+10h]
0x18000c644  mov     rdx, rcx
0x18000c647  mov     [rcx], rax
0x18000c64a  mov     rax, [r9+10h]
0x18000c64e  cmp     [rax+19h], bl
0x18000c651  jnz     short loc_18000C657
0x18000c653  mov     [rax+8], rcx
0x18000c657  mov     rax, [rcx+8]
0x18000c65b  mov     [r9+8], rax
0x18000c65f  mov     rax, [r11]
0x18000c662  cmp     rcx, [rax+8]
0x18000c666  jnz     short loc_18000C66E
0x18000c668  mov     [rax+8], r9
0x18000c66c  jmp     short loc_18000C681
0x18000c66e  mov     rax, [rcx+8]
0x18000c672  cmp     rcx, [rax+10h]
0x18000c676  jnz     short loc_18000C67E
0x18000c678  mov     [rax+10h], r9
0x18000c67c  jmp     short loc_18000C681
0x18000c67e  mov     [rax], r9
0x18000c681  mov     [r9+10h], rcx
0x18000c685  mov     [rcx+8], r9
0x18000c689  mov     rax, [rdx+8]
0x18000c68d  mov     byte ptr [rax+18h], 1
0x18000c691  mov     rax, [rdx+8]
0x18000c695  mov     rcx, [rax+8]
0x18000c699  mov     [rcx+18h], bl
0x18000c69c  mov     rax, [rdx+8]
0x18000c6a0  mov     rcx, [rax+8]
0x18000c6a4  mov     r9, [rcx+10h]
0x18000c6a8  mov     rax, [r9]
0x18000c6ab  mov     [rcx+10h], rax
0x18000c6af  mov     rax, [r9]
0x18000c6b2  cmp     [rax+19h], bl
0x18000c6b5  jnz     short loc_18000C6BB
0x18000c6b7  mov     [rax+8], rcx
0x18000c6bb  mov     rax, [rcx+8]
0x18000c6bf  mov     [r9+8], rax
0x18000c6c3  mov     rax, [r11]
0x18000c6c6  cmp     rcx, [rax+8]
0x18000c6ca  jnz     short loc_18000C6D2
0x18000c6cc  mov     [rax+8], r9
0x18000c6d0  jmp     short loc_18000C6E4
0x18000c6d2  mov     rax, [rcx+8]
0x18000c6d6  cmp     rcx, [rax]
0x18000c6d9  jnz     short loc_18000C6E0
0x18000c6db  mov     [rax], r9
0x18000c6de  jmp     short loc_18000C6E4
0x18000c6e0  mov     [rax+10h], r9
0x18000c6e4  mov     [r9], rcx
0x18000c6e7  mov     [rcx+8], r9
0x18000c6eb  mov     rax, [rdx+8]
0x18000c6ef  cmp     [rax+18h], bl
0x18000c6f2  jz      loc_18000C53E
0x18000c6f8  mov     rax, [r10+8]
0x18000c6fc  mov     byte ptr [rax+18h], 1
0x18000c700  mov     rbx, [rsp+arg_0]
0x18000c705  mov     rax, r8
0x18000c708  retn
```
