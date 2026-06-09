# std::_Tree_val<std::_Tree_simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,void *> *>,std::_Tree_node<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,void *> * const)

- ea: `0x140009aac`
- end: `0x140009cd5`
- name: `?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@2@QEAU32@@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000549c`
- `0x14000588c`
- `0x140006424`

## callees

- `0x140009aac`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tree_simple_types<std::wstring *>>::_Insert_node(
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
0x140009aac  mov     [rsp+arg_0], rbx
0x140009ab1  inc     qword ptr [rcx+8]
0x140009ab5  mov     r11, rcx
0x140009ab8  mov     r10, [rcx]
0x140009abb  mov     rax, [rdx]
0x140009abe  mov     [r8+8], rax
0x140009ac2  cmp     rax, r10
0x140009ac5  jnz     short loc_140009ADC
0x140009ac7  mov     [r10], r8
0x140009aca  mov     [r10+8], r8
0x140009ace  mov     [r10+10h], r8
0x140009ad2  mov     byte ptr [r8+18h], 1
0x140009ad7  jmp     loc_140009CCC
0x140009adc  xor     ebx, ebx
0x140009ade  cmp     [rdx+8], ebx
0x140009ae1  jnz     short loc_140009AF3
0x140009ae3  mov     [rax+10h], r8
0x140009ae7  cmp     rax, [r10+10h]
0x140009aeb  jnz     short loc_140009AFE
0x140009aed  mov     [r10+10h], r8
0x140009af1  jmp     short loc_140009AFE
0x140009af3  mov     [rax], r8
0x140009af6  cmp     rax, [r10]
0x140009af9  jnz     short loc_140009AFE
0x140009afb  mov     [r10], r8
0x140009afe  mov     rax, [r8+8]
0x140009b02  mov     rdx, r8
0x140009b05  jmp     loc_140009CBB
0x140009b0a  mov     rcx, [rdx+8]
0x140009b0e  mov     r9, [rcx+8]
0x140009b12  mov     rax, [r9]
0x140009b15  cmp     rcx, rax
0x140009b18  jnz     loc_140009BDF
0x140009b1e  mov     rax, [r9+10h]
0x140009b22  cmp     [rax+18h], bl
0x140009b25  jz      loc_140009BE4
0x140009b2b  mov     r9, [rcx+10h]
0x140009b2f  cmp     rdx, r9
0x140009b32  jnz     short loc_140009B7A
0x140009b34  mov     rax, [r9]
0x140009b37  mov     rdx, rcx
0x140009b3a  mov     [rcx+10h], rax
0x140009b3e  mov     rax, [r9]
0x140009b41  cmp     [rax+19h], bl
0x140009b44  jnz     short loc_140009B4A
0x140009b46  mov     [rax+8], rcx
0x140009b4a  mov     rax, [rcx+8]
0x140009b4e  mov     [r9+8], rax
0x140009b52  mov     rax, [r11]
0x140009b55  cmp     rcx, [rax+8]
0x140009b59  jnz     short loc_140009B61
0x140009b5b  mov     [rax+8], r9
0x140009b5f  jmp     short loc_140009B73
0x140009b61  mov     rax, [rcx+8]
0x140009b65  cmp     rcx, [rax]
0x140009b68  jnz     short loc_140009B6F
0x140009b6a  mov     [rax], r9
0x140009b6d  jmp     short loc_140009B73
0x140009b6f  mov     [rax+10h], r9
0x140009b73  mov     [r9], rcx
0x140009b76  mov     [rcx+8], r9
0x140009b7a  mov     rax, [rdx+8]
0x140009b7e  mov     byte ptr [rax+18h], 1
0x140009b82  mov     rax, [rdx+8]
0x140009b86  mov     rcx, [rax+8]
0x140009b8a  mov     [rcx+18h], bl
0x140009b8d  mov     rax, [rdx+8]
0x140009b91  mov     rcx, [rax+8]
0x140009b95  mov     r9, [rcx]
0x140009b98  mov     rax, [r9+10h]
0x140009b9c  mov     [rcx], rax
0x140009b9f  mov     rax, [r9+10h]
0x140009ba3  cmp     [rax+19h], bl
0x140009ba6  jnz     short loc_140009BAC
0x140009ba8  mov     [rax+8], rcx
0x140009bac  mov     rax, [rcx+8]
0x140009bb0  mov     [r9+8], rax
0x140009bb4  mov     rax, [r11]
0x140009bb7  cmp     rcx, [rax+8]
0x140009bbb  jnz     short loc_140009BC3
0x140009bbd  mov     [rax+8], r9
0x140009bc1  jmp     short loc_140009BD6
0x140009bc3  mov     rax, [rcx+8]
0x140009bc7  cmp     rcx, [rax+10h]
0x140009bcb  jnz     short loc_140009BD3
0x140009bcd  mov     [rax+10h], r9
0x140009bd1  jmp     short loc_140009BD6
0x140009bd3  mov     [rax], r9
0x140009bd6  mov     [r9+10h], rcx
0x140009bda  jmp     loc_140009CB3
0x140009bdf  cmp     [rax+18h], bl
0x140009be2  jnz     short loc_140009C04
0x140009be4  mov     byte ptr [rcx+18h], 1
0x140009be8  mov     byte ptr [rax+18h], 1
0x140009bec  mov     rax, [rdx+8]
0x140009bf0  mov     rcx, [rax+8]
0x140009bf4  mov     [rcx+18h], bl
0x140009bf7  mov     rax, [rdx+8]
0x140009bfb  mov     rdx, [rax+8]
0x140009bff  jmp     loc_140009CB7
0x140009c04  mov     r9, [rcx]
0x140009c07  cmp     rdx, r9
0x140009c0a  jnz     short loc_140009C55
0x140009c0c  mov     rax, [r9+10h]
0x140009c10  mov     rdx, rcx
0x140009c13  mov     [rcx], rax
0x140009c16  mov     rax, [r9+10h]
0x140009c1a  cmp     [rax+19h], bl
0x140009c1d  jnz     short loc_140009C23
0x140009c1f  mov     [rax+8], rcx
0x140009c23  mov     rax, [rcx+8]
0x140009c27  mov     [r9+8], rax
0x140009c2b  mov     rax, [r11]
0x140009c2e  cmp     rcx, [rax+8]
0x140009c32  jnz     short loc_140009C3A
0x140009c34  mov     [rax+8], r9
0x140009c38  jmp     short loc_140009C4D
0x140009c3a  mov     rax, [rcx+8]
0x140009c3e  cmp     rcx, [rax+10h]
0x140009c42  jnz     short loc_140009C4A
0x140009c44  mov     [rax+10h], r9
0x140009c48  jmp     short loc_140009C4D
0x140009c4a  mov     [rax], r9
0x140009c4d  mov     [r9+10h], rcx
0x140009c51  mov     [rcx+8], r9
0x140009c55  mov     rax, [rdx+8]
0x140009c59  mov     byte ptr [rax+18h], 1
0x140009c5d  mov     rax, [rdx+8]
0x140009c61  mov     rcx, [rax+8]
0x140009c65  mov     [rcx+18h], bl
0x140009c68  mov     rax, [rdx+8]
0x140009c6c  mov     rcx, [rax+8]
0x140009c70  mov     r9, [rcx+10h]
0x140009c74  mov     rax, [r9]
0x140009c77  mov     [rcx+10h], rax
0x140009c7b  mov     rax, [r9]
0x140009c7e  cmp     [rax+19h], bl
0x140009c81  jnz     short loc_140009C87
0x140009c83  mov     [rax+8], rcx
0x140009c87  mov     rax, [rcx+8]
0x140009c8b  mov     [r9+8], rax
0x140009c8f  mov     rax, [r11]
0x140009c92  cmp     rcx, [rax+8]
0x140009c96  jnz     short loc_140009C9E
0x140009c98  mov     [rax+8], r9
0x140009c9c  jmp     short loc_140009CB0
0x140009c9e  mov     rax, [rcx+8]
0x140009ca2  cmp     rcx, [rax]
0x140009ca5  jnz     short loc_140009CAC
0x140009ca7  mov     [rax], r9
0x140009caa  jmp     short loc_140009CB0
0x140009cac  mov     [rax+10h], r9
0x140009cb0  mov     [r9], rcx
0x140009cb3  mov     [rcx+8], r9
0x140009cb7  mov     rax, [rdx+8]
0x140009cbb  cmp     [rax+18h], bl
0x140009cbe  jz      loc_140009B0A
0x140009cc4  mov     rax, [r10+8]
0x140009cc8  mov     byte ptr [rax+18h], 1
0x140009ccc  mov     rbx, [rsp+arg_0]
0x140009cd1  mov     rax, r8
0x140009cd4  retn
```
