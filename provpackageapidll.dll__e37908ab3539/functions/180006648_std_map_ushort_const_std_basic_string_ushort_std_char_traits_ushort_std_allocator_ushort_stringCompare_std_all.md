# std::map<ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stringCompare,std::allocator<std::pair<ushort const * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::operator[](ushort const * &&)

- ea: `0x180006648`
- end: `0x18000677a`
- name: `??A?$map@PEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UstringCompare@@V?$allocator@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAPEBG@Z`
- size: `306`
- prototype: `__int64 __fastcall(__int64 *, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007040`
- `0x180007370`
- `0x180007710`
- `0x1800077b0`
- `0x180007850`
- `0x180007c30`
- `0x180007d50`
- `0x180007ee0`
- `0x180012b94`

## callees

- `0x180002110`
- `0x180006648`
- `0x1800093f4`
- `0x18000964c`

## pseudocode

```c
__int64 __fastcall std::map<unsigned short const *,std::wstring,stringCompare,std::allocator<std::pair<unsigned short const * const,std::wstring>>>::operator[](
        __int64 *a1,
        unsigned __int16 **a2)
{
  __int64 v4; // rsi
  __int64 *v5; // rbp
  unsigned int v6; // ebx
  __int64 inserted; // r8
  __int64 v8; // rax
  char *v9; // rcx
  __int64 v10; // r10
  int v11; // r9d
  int v12; // edx
  unsigned __int16 *v13; // rax
  int v14; // r9d
  int v15; // ecx
  char *v16; // rax
  __int64 *v18; // [rsp+20h] [rbp-48h] BYREF
  __int64 v19; // [rsp+28h] [rbp-40h]

  v4 = *a1;
  v5 = *(__int64 **)(*a1 + 8);
  v6 = 0;
  inserted = *a1;
  v8 = (__int64)v5;
  if ( !*((_BYTE *)v5 + 25) )
  {
    do
    {
      v5 = (__int64 *)v8;
      v9 = *(char **)(v8 + 32);
      v10 = (char *)*a2 - v9;
      do
      {
        v11 = *(unsigned __int16 *)&v9[v10];
        v12 = *(unsigned __int16 *)v9 - v11;
        if ( v12 )
          break;
        v9 += 2;
      }
      while ( v11 );
      if ( v12 >= 0 )
      {
        v6 = 1;
        inserted = v8;
        v8 = *(_QWORD *)v8;
      }
      else
      {
        v6 = 0;
        v8 = *(_QWORD *)(v8 + 16);
      }
    }
    while ( !*(_BYTE *)(v8 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) )
    goto LABEL_14;
  v13 = *a2;
  do
  {
    v14 = *(unsigned __int16 *)((char *)v13 + *(_QWORD *)(inserted + 32) - (_QWORD)*a2);
    v15 = *v13 - v14;
    if ( v15 )
      break;
    ++v13;
  }
  while ( v14 );
  if ( v15 < 0 )
  {
LABEL_14:
    if ( a1[1] == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v18 = a1;
    v19 = 0;
    v16 = (char *)operator new(0x48u);
    *((_QWORD *)v16 + 4) = *a2;
    *(_OWORD *)(v16 + 40) = 0;
    *((_QWORD *)v16 + 7) = 0;
    *((_QWORD *)v16 + 8) = 7;
    *((_WORD *)v16 + 20) = 0;
    *(_QWORD *)v16 = v4;
    *((_QWORD *)v16 + 1) = v4;
    *((_QWORD *)v16 + 2) = v4;
    *((_WORD *)v16 + 12) = 0;
    v18 = v5;
    v19 = v6;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const * const,std::wstring>>>::_Insert_node(
                 a1,
                 &v18);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x180006648  push    rbx
0x18000664a  push    rbp
0x18000664b  push    rsi
0x18000664c  push    rdi
0x18000664d  push    r12
0x18000664f  push    r14
0x180006651  sub     rsp, 38h
0x180006655  mov     r14, rdx
0x180006658  mov     rdi, rcx
0x18000665b  mov     rsi, [rcx]
0x18000665e  mov     rbp, [rsi+8]
0x180006662  xor     ebx, ebx
0x180006664  xor     r12d, r12d
0x180006667  mov     r8, rsi
0x18000666a  mov     rax, rbp
0x18000666d  cmp     [rbp+19h], bl
0x180006670  jnz     short loc_1800066B2
0x180006672  mov     rbp, rax
0x180006675  mov     rcx, [rax+20h]
0x180006679  mov     r10, [r14]
0x18000667c  sub     r10, rcx
0x18000667f  movzx   edx, word ptr [rcx]
0x180006682  movzx   r9d, word ptr [rcx+r10]
0x180006687  sub     edx, r9d
0x18000668a  jnz     short loc_180006695
0x18000668c  add     rcx, 2
0x180006690  test    r9d, r9d
0x180006693  jnz     short loc_18000667F
0x180006695  test    edx, edx
0x180006697  jns     short loc_1800066A1
0x180006699  xor     ebx, ebx
0x18000669b  mov     rax, [rax+10h]
0x18000669f  jmp     short loc_1800066AC
0x1800066a1  mov     ebx, 1
0x1800066a6  mov     r8, rax
0x1800066a9  mov     rax, [rax]
0x1800066ac  cmp     [rax+19h], r12b
0x1800066b0  jz      short loc_180006672
0x1800066b2  cmp     [r8+19h], r12b
0x1800066b6  jnz     short loc_1800066E0
0x1800066b8  mov     rax, [r14]
0x1800066bb  mov     rdx, [r8+20h]
0x1800066bf  sub     rdx, rax
0x1800066c2  movzx   ecx, word ptr [rax]
0x1800066c5  movzx   r9d, word ptr [rax+rdx]
0x1800066ca  sub     ecx, r9d
0x1800066cd  jnz     short loc_1800066D8
0x1800066cf  add     rax, 2
0x1800066d3  test    r9d, r9d
0x1800066d6  jnz     short loc_1800066C2
0x1800066d8  test    ecx, ecx
0x1800066da  jns     loc_180006763
0x1800066e0  mov     rax, 38E38E38E38E38Eh
0x1800066ea  cmp     [rdi+8], rax
0x1800066ee  jz      loc_180006774
0x1800066f4  mov     [rsp+68h+var_48], rdi
0x1800066f9  mov     [rsp+68h+var_40], 0
0x180006702  mov     ecx, 48h ; 'H'; Size
0x180006707  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000670c  mov     r8, rax
0x18000670f  mov     rax, [r14]
0x180006712  mov     [r8+20h], rax
0x180006716  xorps   xmm0, xmm0
0x180006719  movups  xmmword ptr [r8+28h], xmm0
0x18000671e  mov     qword ptr [r8+38h], 0
0x180006726  mov     qword ptr [r8+40h], 7
0x18000672e  xor     eax, eax
0x180006730  mov     [r8+28h], ax
0x180006735  mov     [r8], rsi
0x180006738  mov     [r8+8], rsi
0x18000673c  mov     [r8+10h], rsi
0x180006740  mov     [r8+18h], ax
0x180006745  mov     [rsp+68h+var_48], rbp
0x18000674a  mov     dword ptr [rsp+68h+var_40], ebx
0x18000674e  mov     dword ptr [rsp+68h+var_40+4], r12d
0x180006753  lea     rdx, [rsp+68h+var_48]
0x180006758  mov     rcx, rdi
0x18000675b  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@QEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const * const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *> *>,std::_Tree_node<std::pair<ushort const * const,std::wstring>,void *> * const)
0x180006760  mov     r8, rax
0x180006763  lea     rax, [r8+28h]
0x180006767  add     rsp, 38h
0x18000676b  pop     r14
0x18000676d  pop     r12
0x18000676f  pop     rdi
0x180006770  pop     rsi
0x180006771  pop     rbp
0x180006772  pop     rbx
0x180006773  retn
0x180006774  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
