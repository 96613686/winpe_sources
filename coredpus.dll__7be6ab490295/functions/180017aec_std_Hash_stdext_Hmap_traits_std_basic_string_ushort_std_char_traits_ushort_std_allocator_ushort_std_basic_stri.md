# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180017aec`
- end: `0x180017bbb`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800060a0`
- `0x1800116a0`
- `0x180017e94`
- `0x180023d60`
- `0x180023ed4`

## callees

- `0x1800138e0`
- `0x180017aec`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4)
{
  __int64 v5; // r8
  _QWORD *v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rbp
  _QWORD *v10; // r14
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // r9
  int v14; // eax

  v5 = a1[3];
  v7 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v7 )
  {
    *a2 = v7;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( 1 )
    {
      v10 = v8 + 2;
      v11 = v8[5] <= 7u ? (__int64)(v8 + 2) : *v10;
      v12 = a3[3] <= 7u ? a3 : (_QWORD *)*a3;
      if ( (int)std::_Traits_compare<std::char_traits<unsigned short>>(v12, a3[2], v11, v8[4]) >= 0 )
        break;
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    v13 = a3[2];
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    if ( v8[5] > 7u )
      v10 = (_QWORD *)*v10;
    v14 = std::_Traits_compare<std::char_traits<unsigned short>>(v10, v8[4], a3, v13);
    *a2 = *v8;
    if ( v14 >= 0 )
    {
      a2[1] = v8;
      return a2;
    }
  }
LABEL_3:
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180017aec  push    rbx
0x180017aee  push    rbp
0x180017aef  push    rsi
0x180017af0  push    rdi
0x180017af1  push    r14
0x180017af3  sub     rsp, 20h
0x180017af7  mov     rax, [rcx+30h]
0x180017afb  mov     rsi, r8
0x180017afe  mov     r8, [rcx+18h]
0x180017b02  and     rax, r9
0x180017b05  add     rax, rax
0x180017b08  mov     rbx, rdx
0x180017b0b  mov     rdx, [rcx+8]
0x180017b0f  mov     rdi, [r8+rax*8+8]
0x180017b14  cmp     rdi, rdx
0x180017b17  jnz     short loc_180017B29
0x180017b19  mov     [rbx], rdx
0x180017b1c  mov     qword ptr [rbx+8], 0
0x180017b24  jmp     loc_180017BAC
0x180017b29  mov     rbp, [r8+rax*8]
0x180017b2d  cmp     qword ptr [rdi+28h], 7
0x180017b32  lea     r14, [rdi+10h]
0x180017b36  jbe     short loc_180017B3D
0x180017b38  mov     r8, [r14]
0x180017b3b  jmp     short loc_180017B40
0x180017b3d  mov     r8, r14
0x180017b40  cmp     qword ptr [rsi+18h], 7
0x180017b45  jbe     short loc_180017B4C
0x180017b47  mov     rcx, [rsi]
0x180017b4a  jmp     short loc_180017B4F
0x180017b4c  mov     rcx, rsi
0x180017b4f  mov     r9, [rdi+20h]
0x180017b53  mov     rdx, [rsi+10h]
0x180017b57  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180017b5c  test    eax, eax
0x180017b5e  jns     short loc_180017B70
0x180017b60  cmp     rdi, rbp
0x180017b63  jz      short loc_180017B6B
0x180017b65  mov     rdi, [rdi+8]
0x180017b69  jmp     short loc_180017B2D
0x180017b6b  mov     [rbx], rdi
0x180017b6e  jmp     short loc_180017B1C
0x180017b70  cmp     qword ptr [rsi+18h], 7
0x180017b75  mov     r9, [rsi+10h]
0x180017b79  jbe     short loc_180017B7E
0x180017b7b  mov     rsi, [rsi]
0x180017b7e  cmp     qword ptr [r14+18h], 7
0x180017b83  mov     rdx, [r14+10h]
0x180017b87  jbe     short loc_180017B8C
0x180017b89  mov     r14, [r14]
0x180017b8c  mov     r8, rsi
0x180017b8f  mov     rcx, r14
0x180017b92  call    ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180017b97  mov     rcx, [rdi]
0x180017b9a  shr     eax, 1Fh
0x180017b9d  mov     [rbx], rcx
0x180017ba0  test    al, al
0x180017ba2  jnz     loc_180017B1C
0x180017ba8  mov     [rbx+8], rdi
0x180017bac  mov     rax, rbx
0x180017baf  add     rsp, 20h
0x180017bb3  pop     r14
0x180017bb5  pop     rdi
0x180017bb6  pop     rsi
0x180017bb7  pop     rbp
0x180017bb8  pop     rbx
0x180017bb9  retn
```
