# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *> *>,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,CachedAdapterInformation>,void *> * const)

- ea: `0x140010130`
- end: `0x140010359`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCachedAdapterInformation@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004d34`

## callees

- `0x140010130`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CachedAdapterInformation>>>::_Insert_node(
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
0x140010130  mov     [rsp+arg_0], rbx
0x140010135  inc     qword ptr [rcx+8]
0x140010139  mov     r11, rcx
0x14001013c  mov     r10, [rcx]
0x14001013f  mov     rax, [rdx]
0x140010142  mov     [r8+8], rax
0x140010146  cmp     rax, r10
0x140010149  jnz     short loc_140010160
0x14001014b  mov     [r10], r8
0x14001014e  mov     [r10+8], r8
0x140010152  mov     [r10+10h], r8
0x140010156  mov     byte ptr [r8+18h], 1
0x14001015b  jmp     loc_140010350
0x140010160  xor     ebx, ebx
0x140010162  cmp     [rdx+8], ebx
0x140010165  jnz     short loc_140010177
0x140010167  mov     [rax+10h], r8
0x14001016b  cmp     rax, [r10+10h]
0x14001016f  jnz     short loc_140010182
0x140010171  mov     [r10+10h], r8
0x140010175  jmp     short loc_140010182
0x140010177  mov     [rax], r8
0x14001017a  cmp     rax, [r10]
0x14001017d  jnz     short loc_140010182
0x14001017f  mov     [r10], r8
0x140010182  mov     rax, [r8+8]
0x140010186  mov     rdx, r8
0x140010189  jmp     loc_14001033F
0x14001018e  mov     rcx, [rdx+8]
0x140010192  mov     r9, [rcx+8]
0x140010196  mov     rax, [r9]
0x140010199  cmp     rcx, rax
0x14001019c  jnz     loc_140010263
0x1400101a2  mov     rax, [r9+10h]
0x1400101a6  cmp     [rax+18h], bl
0x1400101a9  jz      loc_140010268
0x1400101af  mov     r9, [rcx+10h]
0x1400101b3  cmp     rdx, r9
0x1400101b6  jnz     short loc_1400101FE
0x1400101b8  mov     rax, [r9]
0x1400101bb  mov     rdx, rcx
0x1400101be  mov     [rcx+10h], rax
0x1400101c2  mov     rax, [r9]
0x1400101c5  cmp     [rax+19h], bl
0x1400101c8  jnz     short loc_1400101CE
0x1400101ca  mov     [rax+8], rcx
0x1400101ce  mov     rax, [rcx+8]
0x1400101d2  mov     [r9+8], rax
0x1400101d6  mov     rax, [r11]
0x1400101d9  cmp     rcx, [rax+8]
0x1400101dd  jnz     short loc_1400101E5
0x1400101df  mov     [rax+8], r9
0x1400101e3  jmp     short loc_1400101F7
0x1400101e5  mov     rax, [rcx+8]
0x1400101e9  cmp     rcx, [rax]
0x1400101ec  jnz     short loc_1400101F3
0x1400101ee  mov     [rax], r9
0x1400101f1  jmp     short loc_1400101F7
0x1400101f3  mov     [rax+10h], r9
0x1400101f7  mov     [r9], rcx
0x1400101fa  mov     [rcx+8], r9
0x1400101fe  mov     rax, [rdx+8]
0x140010202  mov     byte ptr [rax+18h], 1
0x140010206  mov     rax, [rdx+8]
0x14001020a  mov     rcx, [rax+8]
0x14001020e  mov     [rcx+18h], bl
0x140010211  mov     rax, [rdx+8]
0x140010215  mov     rcx, [rax+8]
0x140010219  mov     r9, [rcx]
0x14001021c  mov     rax, [r9+10h]
0x140010220  mov     [rcx], rax
0x140010223  mov     rax, [r9+10h]
0x140010227  cmp     [rax+19h], bl
0x14001022a  jnz     short loc_140010230
0x14001022c  mov     [rax+8], rcx
0x140010230  mov     rax, [rcx+8]
0x140010234  mov     [r9+8], rax
0x140010238  mov     rax, [r11]
0x14001023b  cmp     rcx, [rax+8]
0x14001023f  jnz     short loc_140010247
0x140010241  mov     [rax+8], r9
0x140010245  jmp     short loc_14001025A
0x140010247  mov     rax, [rcx+8]
0x14001024b  cmp     rcx, [rax+10h]
0x14001024f  jnz     short loc_140010257
0x140010251  mov     [rax+10h], r9
0x140010255  jmp     short loc_14001025A
0x140010257  mov     [rax], r9
0x14001025a  mov     [r9+10h], rcx
0x14001025e  jmp     loc_140010337
0x140010263  cmp     [rax+18h], bl
0x140010266  jnz     short loc_140010288
0x140010268  mov     byte ptr [rcx+18h], 1
0x14001026c  mov     byte ptr [rax+18h], 1
0x140010270  mov     rax, [rdx+8]
0x140010274  mov     rcx, [rax+8]
0x140010278  mov     [rcx+18h], bl
0x14001027b  mov     rax, [rdx+8]
0x14001027f  mov     rdx, [rax+8]
0x140010283  jmp     loc_14001033B
0x140010288  mov     r9, [rcx]
0x14001028b  cmp     rdx, r9
0x14001028e  jnz     short loc_1400102D9
0x140010290  mov     rax, [r9+10h]
0x140010294  mov     rdx, rcx
0x140010297  mov     [rcx], rax
0x14001029a  mov     rax, [r9+10h]
0x14001029e  cmp     [rax+19h], bl
0x1400102a1  jnz     short loc_1400102A7
0x1400102a3  mov     [rax+8], rcx
0x1400102a7  mov     rax, [rcx+8]
0x1400102ab  mov     [r9+8], rax
0x1400102af  mov     rax, [r11]
0x1400102b2  cmp     rcx, [rax+8]
0x1400102b6  jnz     short loc_1400102BE
0x1400102b8  mov     [rax+8], r9
0x1400102bc  jmp     short loc_1400102D1
0x1400102be  mov     rax, [rcx+8]
0x1400102c2  cmp     rcx, [rax+10h]
0x1400102c6  jnz     short loc_1400102CE
0x1400102c8  mov     [rax+10h], r9
0x1400102cc  jmp     short loc_1400102D1
0x1400102ce  mov     [rax], r9
0x1400102d1  mov     [r9+10h], rcx
0x1400102d5  mov     [rcx+8], r9
0x1400102d9  mov     rax, [rdx+8]
0x1400102dd  mov     byte ptr [rax+18h], 1
0x1400102e1  mov     rax, [rdx+8]
0x1400102e5  mov     rcx, [rax+8]
0x1400102e9  mov     [rcx+18h], bl
0x1400102ec  mov     rax, [rdx+8]
0x1400102f0  mov     rcx, [rax+8]
0x1400102f4  mov     r9, [rcx+10h]
0x1400102f8  mov     rax, [r9]
0x1400102fb  mov     [rcx+10h], rax
0x1400102ff  mov     rax, [r9]
0x140010302  cmp     [rax+19h], bl
0x140010305  jnz     short loc_14001030B
0x140010307  mov     [rax+8], rcx
0x14001030b  mov     rax, [rcx+8]
0x14001030f  mov     [r9+8], rax
0x140010313  mov     rax, [r11]
0x140010316  cmp     rcx, [rax+8]
0x14001031a  jnz     short loc_140010322
0x14001031c  mov     [rax+8], r9
0x140010320  jmp     short loc_140010334
0x140010322  mov     rax, [rcx+8]
0x140010326  cmp     rcx, [rax]
0x140010329  jnz     short loc_140010330
0x14001032b  mov     [rax], r9
0x14001032e  jmp     short loc_140010334
0x140010330  mov     [rax+10h], r9
0x140010334  mov     [r9], rcx
0x140010337  mov     [rcx+8], r9
0x14001033b  mov     rax, [rdx+8]
0x14001033f  cmp     [rax+18h], bl
0x140010342  jz      loc_14001018E
0x140010348  mov     rax, [r10+8]
0x14001034c  mov     byte ptr [rax+18h], 1
0x140010350  mov     rbx, [rsp+arg_0]
0x140010355  mov     rax, r8
0x140010358  retn
```
