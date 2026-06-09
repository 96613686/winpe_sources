# std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Wrapped_disjunction(void)

- ea: `0x180030638`
- end: `0x1800308ab`
- name: `?_Wrapped_disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAA_NXZ`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x18002c708`

## callees

- `0x180002fd4`
- `0x18002cde8`
- `0x18002de68`
- `0x18002ebe0`
- `0x18002eca0`
- `0x18002fc54`
- `0x180030434`
- `0x180030638`
- `0x1800311d0`

## pseudocode

```c
char __fastcall std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Wrapped_disjunction(
        __int64 a1)
{
  int v1; // edx
  int *v2; // rbx
  _WORD *v4; // r8
  _WORD *v5; // rcx
  _WORD *v6; // rdx
  int v7; // ebx
  _WORD *v8; // rcx
  int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int64 v18; // rbp
  __int64 v19; // rdx
  int v20; // ebx
  _QWORD *v21; // rax
  _QWORD *v22; // rdi
  __int64 v23; // rcx

  v1 = *(_DWORD *)(a1 + 128);
  v2 = (int *)(a1 + 124);
  ++*(_DWORD *)(a1 + 28);
  if ( (v1 & 0x8000000) == 0 && *v2 == 41 )
  {
    std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(a1, 5);
    JUMPOUT(0x1800308AALL);
  }
  if ( (v1 & 0x20) == 0 || *v2 != 63 )
  {
    v18 = a1 + 64;
    if ( (*(_DWORD *)(a1 + 112) & 0x200) == 0 )
    {
      v20 = ++*(_DWORD *)(a1 + 24);
      v21 = operator new(0x28u);
      v22 = v21;
      if ( v21 )
      {
        v21[1] = 13;
        v21[2] = 0;
        v21[3] = 0;
        *v21 = &std::_Node_endif::`vftable';
        *((_DWORD *)v21 + 8) = v20;
      }
      else
      {
        v22 = 0;
      }
      v22[3] = *(_QWORD *)(v18 + 8);
      v23 = *(_QWORD *)(*(_QWORD *)(v18 + 8) + 16LL);
      if ( v23 )
      {
        v22[2] = v23;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v18 + 8) + 16LL) + 24LL) = v22;
      }
      *(_QWORD *)(*(_QWORD *)(v18 + 8) + 16LL) = v22;
      *(_QWORD *)(v18 + 8) = v22;
      std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1, 0);
      std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v18, v22);
      std::vector<bool>::resize(a1 + 32, *(_DWORD *)(a1 + 24) + 1);
      *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4 * ((unsigned __int64)*((unsigned int *)v22 + 8) >> 5)) |= 1 << *((_DWORD *)v22 + 8);
      goto LABEL_39;
    }
    v12 = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(a1 + 64, 8);
    std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1, v19);
    v14 = v18;
LABEL_32:
    std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(v14, v12);
LABEL_39:
    --*(_DWORD *)(a1 + 28);
    return 1;
  }
  v4 = *(_WORD **)a1;
  if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
  {
    if ( *v4 != 92
      || (v5 = v4 + 1, v4 + 1 == *(_WORD **)(a1 + 16))
      || ((v1 & 8) != 0 || (unsigned __int16)(*v5 - 40) > 1u) && ((v1 & 0x10) != 0 || ((*v5 - 123) & 0xFFFD) != 0) )
    {
      v5 = v4;
    }
    *(_QWORD *)a1 = v5 + 1;
  }
  std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Trans(a1);
  v6 = *(_WORD **)a1;
  v7 = *v2;
  if ( *(_QWORD *)a1 != *(_QWORD *)(a1 + 16) )
  {
    if ( *v6 != 92
      || (v8 = v6 + 1, v6 + 1 == *(_WORD **)(a1 + 16))
      || ((v9 = *(_DWORD *)(a1 + 128), (v9 & 8) != 0) || (unsigned __int16)(*v8 - 40) > 1u)
      && ((v9 & 0x10) != 0 || ((*v8 - 123) & 0xFFFD) != 0) )
    {
      v8 = *(_WORD **)a1;
    }
    *(_QWORD *)a1 = v8 + 1;
  }
  std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Trans(a1);
  switch ( v7 )
  {
    case ':':
      v12 = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_New_node(
              a1 + 64,
              8);
      std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1, v13);
      v14 = a1 + 64;
      goto LABEL_32;
    case '!':
      LOBYTE(v10) = 1;
      break;
    case '=':
      v10 = 0;
      break;
    default:
      std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Error(v11, 14);
      __debugbreak();
  }
  v15 = std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Begin_assert_group(
          a1 + 64,
          v10);
  std::_Parser<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Disjunction(a1, v16);
  std::_Builder<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_End_group(a1 + 64, v15);
  *(_QWORD *)(a1 + 72) = v15;
  --*(_DWORD *)(a1 + 28);
  return 0;
}

```

## disassembly

```asm
0x180030638  mov     [rsp+arg_8], rbx
0x18003063d  mov     [rsp+arg_10], rbp
0x180030642  push    rsi
0x180030643  push    rdi
0x180030644  push    r14
0x180030646  sub     rsp, 20h
0x18003064a  mov     edx, [rcx+80h]
0x180030650  lea     rbx, [rcx+7Ch]
0x180030654  mov     r14d, 1
0x18003065a  mov     rsi, rcx
0x18003065d  add     [rcx+1Ch], r14d
0x180030661  bt      edx, 1Bh
0x180030665  jb      short loc_180030670
0x180030667  cmp     dword ptr [rbx], 29h ; ')'
0x18003066a  jz      loc_1800308A0
0x180030670  test    dl, 20h
0x180030673  jz      loc_180030797
0x180030679  cmp     dword ptr [rbx], 3Fh ; '?'
0x18003067c  jnz     loc_180030797
0x180030682  mov     r8, [rcx]
0x180030685  mov     edi, 28h ; '('
0x18003068a  mov     ebp, 0FFFDh
0x18003068f  cmp     r8, [rcx+10h]
0x180030693  jz      short loc_1800306D2
0x180030695  cmp     word ptr [r8], 5Ch ; '\'
0x18003069a  jnz     short loc_1800306C8
0x18003069c  lea     rcx, [r8+2]
0x1800306a0  cmp     rcx, [rsi+10h]
0x1800306a4  jz      short loc_1800306C8
0x1800306a6  test    dl, 8
0x1800306a9  jnz     short loc_1800306B7
0x1800306ab  movzx   eax, word ptr [rcx]
0x1800306ae  sub     ax, di
0x1800306b1  cmp     ax, r14w
0x1800306b5  jbe     short loc_1800306CB
0x1800306b7  test    dl, 10h
0x1800306ba  jnz     short loc_1800306C8
0x1800306bc  movzx   eax, word ptr [rcx]
0x1800306bf  sub     ax, 7Bh ; '{'
0x1800306c3  test    bp, ax
0x1800306c6  jz      short loc_1800306CB
0x1800306c8  mov     rcx, r8
0x1800306cb  lea     rax, [rcx+2]
0x1800306cf  mov     [rsi], rax
0x1800306d2  mov     rcx, rsi
0x1800306d5  call    ?_Trans@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Trans(void)
0x1800306da  mov     rdx, [rsi]
0x1800306dd  mov     ebx, [rbx]
0x1800306df  cmp     rdx, [rsi+10h]
0x1800306e3  jz      short loc_18003072A
0x1800306e5  cmp     word ptr [rdx], 5Ch ; '\'
0x1800306e9  jnz     short loc_180030720
0x1800306eb  lea     rcx, [rdx+2]
0x1800306ef  cmp     rcx, [rsi+10h]
0x1800306f3  jz      short loc_180030720
0x1800306f5  mov     r8d, [rsi+80h]
0x1800306fc  test    r8b, 8
0x180030700  jnz     short loc_18003070E
0x180030702  movzx   eax, word ptr [rcx]
0x180030705  sub     ax, di
0x180030708  cmp     ax, r14w
0x18003070c  jbe     short loc_180030723
0x18003070e  test    r8b, 10h
0x180030712  jnz     short loc_180030720
0x180030714  movzx   eax, word ptr [rcx]
0x180030717  sub     ax, 7Bh ; '{'
0x18003071b  test    bp, ax
0x18003071e  jz      short loc_180030723
0x180030720  mov     rcx, rdx
0x180030723  lea     rax, [rcx+2]
0x180030727  mov     [rsi], rax
0x18003072a  mov     rcx, rsi
0x18003072d  call    ?_Trans@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Trans(void)
0x180030732  cmp     ebx, 3Ah ; ':'
0x180030735  jnz     short loc_180030754
0x180030737  lea     edx, [rbx-32h]
0x18003073a  lea     rcx, [rsi+40h]
0x18003073e  call    ?_New_node@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x180030743  mov     rcx, rsi
0x180030746  mov     rbx, rax
0x180030749  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x18003074e  lea     rcx, [rsi+40h]
0x180030752  jmp     short loc_1800307BF
0x180030754  cmp     ebx, 21h ; '!'
0x180030757  jnz     short loc_18003078A
0x180030759  mov     dl, r14b
0x18003075c  lea     rcx, [rsi+40h]
0x180030760  call    ?_Begin_assert_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Node_base@2@_N@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_Begin_assert_group(bool)
0x180030765  mov     rcx, rsi
0x180030768  mov     rbx, rax
0x18003076b  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x180030770  mov     rdx, rbx
0x180030773  lea     rcx, [rsi+40h]
0x180030777  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x18003077c  mov     [rsi+48h], rbx
0x180030780  dec     dword ptr [rsi+1Ch]
0x180030783  xor     al, al
0x180030785  jmp     loc_180030881
0x18003078a  cmp     ebx, 3Dh ; '='
0x18003078d  jnz     loc_180030895
0x180030793  xor     edx, edx
0x180030795  jmp     short loc_18003075C
0x180030797  test    dword ptr [rcx+70h], 200h
0x18003079e  lea     rbp, [rcx+40h]
0x1800307a2  jz      short loc_1800307CC
0x1800307a4  mov     edx, 8
0x1800307a9  mov     rcx, rbp
0x1800307ac  call    ?_New_node@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@AEAAPEAV_Node_base@2@W4_Node_type@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_New_node(std::_Node_type)
0x1800307b1  mov     rcx, rsi
0x1800307b4  mov     rbx, rax
0x1800307b7  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x1800307bc  mov     rcx, rbp
0x1800307bf  mov     rdx, rbx
0x1800307c2  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x1800307c7  jmp     loc_18003087B
0x1800307cc  add     [rcx+18h], r14d
0x1800307d0  mov     ebx, [rcx+18h]
0x1800307d3  mov     ecx, 28h ; '('; Size
0x1800307d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800307dd  xor     edx, edx
0x1800307df  mov     [rsp+38h+arg_0], rax
0x1800307e4  mov     rdi, rax
0x1800307e7  test    rax, rax
0x1800307ea  jz      short loc_18003080B
0x1800307ec  mov     qword ptr [rax+8], 0Dh
0x1800307f4  mov     [rax+10h], rdx
0x1800307f8  mov     [rax+18h], rdx
0x1800307fc  lea     rax, ??_7_Node_endif@std@@6B@; const std::_Node_endif::`vftable'
0x180030803  mov     [rdi], rax
0x180030806  mov     [rdi+20h], ebx
0x180030809  jmp     short loc_18003080E
0x18003080b  mov     rdi, rdx
0x18003080e  mov     rax, [rbp+8]
0x180030812  mov     [rdi+18h], rax
0x180030816  mov     rax, [rbp+8]
0x18003081a  mov     rcx, [rax+10h]
0x18003081e  test    rcx, rcx
0x180030821  jz      short loc_180030833
0x180030823  mov     [rdi+10h], rcx
0x180030827  mov     rax, [rbp+8]
0x18003082b  mov     rcx, [rax+10h]
0x18003082f  mov     [rcx+18h], rdi
0x180030833  mov     rax, [rbp+8]
0x180030837  mov     rcx, rsi
0x18003083a  mov     [rax+10h], rdi
0x18003083e  mov     [rbp+8], rdi
0x180030842  call    ?_Disjunction@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXXZ; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Disjunction(void)
0x180030847  mov     rdx, rdi
0x18003084a  mov     rcx, rbp
0x18003084d  call    ?_End_group@?$_Builder@PEBGGV?$regex_traits@G@std@@@std@@QEAAXPEAV_Node_base@2@@Z; std::_Builder<ushort const *,ushort,std::regex_traits<ushort>>::_End_group(std::_Node_base *)
0x180030852  mov     eax, [rsi+18h]
0x180030855  lea     rcx, [rsi+20h]
0x180030859  add     eax, r14d
0x18003085c  movsxd  rdx, eax
0x18003085f  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180030864  mov     ecx, [rdi+20h]
0x180030867  mov     eax, r14d
0x18003086a  mov     rdx, [rsi+20h]
0x18003086e  mov     r8d, ecx
0x180030871  shr     r8, 5
0x180030875  shl     eax, cl
0x180030877  or      [rdx+r8*4], eax
0x18003087b  dec     dword ptr [rsi+1Ch]
0x18003087e  mov     al, r14b
0x180030881  mov     rbx, [rsp+38h+arg_8]
0x180030886  mov     rbp, [rsp+38h+arg_10]
0x18003088b  add     rsp, 20h
0x18003088f  pop     r14
0x180030891  pop     rdi
0x180030892  pop     rsi
0x180030893  retn
0x180030895  mov     edx, 0Eh
0x18003089a  call    ?_Error@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
0x18003089f  int     3; Trap to Debugger
0x1800308a0  mov     edx, 5
0x1800308a5  call    ?_Error@?$_Parser@PEBGGV?$regex_traits@G@std@@@std@@AEAAXW4error_type@regex_constants@2@@Z; std::_Parser<ushort const *,ushort,std::regex_traits<ushort>>::_Error(std::regex_constants::error_type)
```
