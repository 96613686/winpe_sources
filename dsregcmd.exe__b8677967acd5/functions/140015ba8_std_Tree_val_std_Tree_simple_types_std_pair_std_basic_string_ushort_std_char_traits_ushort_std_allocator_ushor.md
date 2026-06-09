# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>,void *> *>,std::_Tree_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,JsonValue const *>,void *> * const)

- ea: `0x140015ba8`
- end: `0x140015dd1`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVJsonValue@@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140014730`
- `0x14001cac4`
- `0x14001e938`
- `0x14001f008`

## callees

- `0x140015ba8`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,JsonValue const *>>>::_Insert_node(
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
0x140015ba8  mov     [rsp+arg_0], rbx
0x140015bad  inc     qword ptr [rcx+8]
0x140015bb1  mov     r11, rcx
0x140015bb4  mov     r10, [rcx]
0x140015bb7  mov     rax, [rdx]
0x140015bba  mov     [r8+8], rax
0x140015bbe  cmp     rax, r10
0x140015bc1  jnz     short loc_140015BD8
0x140015bc3  mov     [r10], r8
0x140015bc6  mov     [r10+8], r8
0x140015bca  mov     [r10+10h], r8
0x140015bce  mov     byte ptr [r8+18h], 1
0x140015bd3  jmp     loc_140015DC8
0x140015bd8  xor     ebx, ebx
0x140015bda  cmp     [rdx+8], ebx
0x140015bdd  jnz     short loc_140015BEF
0x140015bdf  mov     [rax+10h], r8
0x140015be3  cmp     rax, [r10+10h]
0x140015be7  jnz     short loc_140015BFA
0x140015be9  mov     [r10+10h], r8
0x140015bed  jmp     short loc_140015BFA
0x140015bef  mov     [rax], r8
0x140015bf2  cmp     rax, [r10]
0x140015bf5  jnz     short loc_140015BFA
0x140015bf7  mov     [r10], r8
0x140015bfa  mov     rax, [r8+8]
0x140015bfe  mov     rdx, r8
0x140015c01  jmp     loc_140015DB7
0x140015c06  mov     rcx, [rdx+8]
0x140015c0a  mov     r9, [rcx+8]
0x140015c0e  mov     rax, [r9]
0x140015c11  cmp     rcx, rax
0x140015c14  jnz     loc_140015CDB
0x140015c1a  mov     rax, [r9+10h]
0x140015c1e  cmp     [rax+18h], bl
0x140015c21  jz      loc_140015CE0
0x140015c27  mov     r9, [rcx+10h]
0x140015c2b  cmp     rdx, r9
0x140015c2e  jnz     short loc_140015C76
0x140015c30  mov     rax, [r9]
0x140015c33  mov     rdx, rcx
0x140015c36  mov     [rcx+10h], rax
0x140015c3a  mov     rax, [r9]
0x140015c3d  cmp     [rax+19h], bl
0x140015c40  jnz     short loc_140015C46
0x140015c42  mov     [rax+8], rcx
0x140015c46  mov     rax, [rcx+8]
0x140015c4a  mov     [r9+8], rax
0x140015c4e  mov     rax, [r11]
0x140015c51  cmp     rcx, [rax+8]
0x140015c55  jnz     short loc_140015C5D
0x140015c57  mov     [rax+8], r9
0x140015c5b  jmp     short loc_140015C6F
0x140015c5d  mov     rax, [rcx+8]
0x140015c61  cmp     rcx, [rax]
0x140015c64  jnz     short loc_140015C6B
0x140015c66  mov     [rax], r9
0x140015c69  jmp     short loc_140015C6F
0x140015c6b  mov     [rax+10h], r9
0x140015c6f  mov     [r9], rcx
0x140015c72  mov     [rcx+8], r9
0x140015c76  mov     rax, [rdx+8]
0x140015c7a  mov     byte ptr [rax+18h], 1
0x140015c7e  mov     rax, [rdx+8]
0x140015c82  mov     rcx, [rax+8]
0x140015c86  mov     [rcx+18h], bl
0x140015c89  mov     rax, [rdx+8]
0x140015c8d  mov     rcx, [rax+8]
0x140015c91  mov     r9, [rcx]
0x140015c94  mov     rax, [r9+10h]
0x140015c98  mov     [rcx], rax
0x140015c9b  mov     rax, [r9+10h]
0x140015c9f  cmp     [rax+19h], bl
0x140015ca2  jnz     short loc_140015CA8
0x140015ca4  mov     [rax+8], rcx
0x140015ca8  mov     rax, [rcx+8]
0x140015cac  mov     [r9+8], rax
0x140015cb0  mov     rax, [r11]
0x140015cb3  cmp     rcx, [rax+8]
0x140015cb7  jnz     short loc_140015CBF
0x140015cb9  mov     [rax+8], r9
0x140015cbd  jmp     short loc_140015CD2
0x140015cbf  mov     rax, [rcx+8]
0x140015cc3  cmp     rcx, [rax+10h]
0x140015cc7  jnz     short loc_140015CCF
0x140015cc9  mov     [rax+10h], r9
0x140015ccd  jmp     short loc_140015CD2
0x140015ccf  mov     [rax], r9
0x140015cd2  mov     [r9+10h], rcx
0x140015cd6  jmp     loc_140015DAF
0x140015cdb  cmp     [rax+18h], bl
0x140015cde  jnz     short loc_140015D00
0x140015ce0  mov     byte ptr [rcx+18h], 1
0x140015ce4  mov     byte ptr [rax+18h], 1
0x140015ce8  mov     rax, [rdx+8]
0x140015cec  mov     rcx, [rax+8]
0x140015cf0  mov     [rcx+18h], bl
0x140015cf3  mov     rax, [rdx+8]
0x140015cf7  mov     rdx, [rax+8]
0x140015cfb  jmp     loc_140015DB3
0x140015d00  mov     r9, [rcx]
0x140015d03  cmp     rdx, r9
0x140015d06  jnz     short loc_140015D51
0x140015d08  mov     rax, [r9+10h]
0x140015d0c  mov     rdx, rcx
0x140015d0f  mov     [rcx], rax
0x140015d12  mov     rax, [r9+10h]
0x140015d16  cmp     [rax+19h], bl
0x140015d19  jnz     short loc_140015D1F
0x140015d1b  mov     [rax+8], rcx
0x140015d1f  mov     rax, [rcx+8]
0x140015d23  mov     [r9+8], rax
0x140015d27  mov     rax, [r11]
0x140015d2a  cmp     rcx, [rax+8]
0x140015d2e  jnz     short loc_140015D36
0x140015d30  mov     [rax+8], r9
0x140015d34  jmp     short loc_140015D49
0x140015d36  mov     rax, [rcx+8]
0x140015d3a  cmp     rcx, [rax+10h]
0x140015d3e  jnz     short loc_140015D46
0x140015d40  mov     [rax+10h], r9
0x140015d44  jmp     short loc_140015D49
0x140015d46  mov     [rax], r9
0x140015d49  mov     [r9+10h], rcx
0x140015d4d  mov     [rcx+8], r9
0x140015d51  mov     rax, [rdx+8]
0x140015d55  mov     byte ptr [rax+18h], 1
0x140015d59  mov     rax, [rdx+8]
0x140015d5d  mov     rcx, [rax+8]
0x140015d61  mov     [rcx+18h], bl
0x140015d64  mov     rax, [rdx+8]
0x140015d68  mov     rcx, [rax+8]
0x140015d6c  mov     r9, [rcx+10h]
0x140015d70  mov     rax, [r9]
0x140015d73  mov     [rcx+10h], rax
0x140015d77  mov     rax, [r9]
0x140015d7a  cmp     [rax+19h], bl
0x140015d7d  jnz     short loc_140015D83
0x140015d7f  mov     [rax+8], rcx
0x140015d83  mov     rax, [rcx+8]
0x140015d87  mov     [r9+8], rax
0x140015d8b  mov     rax, [r11]
0x140015d8e  cmp     rcx, [rax+8]
0x140015d92  jnz     short loc_140015D9A
0x140015d94  mov     [rax+8], r9
0x140015d98  jmp     short loc_140015DAC
0x140015d9a  mov     rax, [rcx+8]
0x140015d9e  cmp     rcx, [rax]
0x140015da1  jnz     short loc_140015DA8
0x140015da3  mov     [rax], r9
0x140015da6  jmp     short loc_140015DAC
0x140015da8  mov     [rax+10h], r9
0x140015dac  mov     [r9], rcx
0x140015daf  mov     [rcx+8], r9
0x140015db3  mov     rax, [rdx+8]
0x140015db7  cmp     [rax+18h], bl
0x140015dba  jz      loc_140015C06
0x140015dc0  mov     rax, [r10+8]
0x140015dc4  mov     byte ptr [rax+18h], 1
0x140015dc8  mov     rbx, [rsp+arg_0]
0x140015dcd  mov     rax, r8
0x140015dd0  retn
```
