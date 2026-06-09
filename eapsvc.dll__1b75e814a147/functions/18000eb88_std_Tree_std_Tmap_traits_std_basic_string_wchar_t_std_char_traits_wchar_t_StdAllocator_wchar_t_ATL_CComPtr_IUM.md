# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)

- ea: `0x18000eb88`
- end: `0x18000ec29`
- name: `??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@1@@Z`
- size: `161`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f77c`
- `0x18001129c`

## callees

- `0x18000d610`
- `0x18000eb88`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 *v5; // r9
  __int64 *v6; // rbx
  const wchar_t *v7; // rcx
  unsigned __int64 v8; // r14
  const wchar_t *v9; // rdx
  unsigned __int64 v10; // rbp
  size_t v11; // r8
  int v12; // eax
  int v13; // eax

  v5 = *(__int64 **)(*(_QWORD *)a1 + 8LL);
  *a2 = v5;
  v6 = v5;
  a2[1] = 0;
  for ( a2[2] = *(_QWORD *)a1; !*((_BYTE *)v6 + 25); v6 = (__int64 *)*v6 )
  {
    *a2 = v6;
    v7 = (const wchar_t *)(v6 + 4);
    v8 = *(_QWORD *)(a3 + 16);
    if ( *(_QWORD *)(a3 + 24) <= 7u )
      v9 = (const wchar_t *)a3;
    else
      v9 = *(const wchar_t **)a3;
    v10 = v6[6];
    if ( (unsigned __int64)v6[7] > 7 )
      v7 = *(const wchar_t **)v7;
    v11 = *(_QWORD *)(a3 + 16);
    if ( v8 >= v10 )
      v11 = v6[6];
    v12 = wmemcmp(v7, v9, v11);
    if ( v12 )
    {
      if ( v12 < 0 )
        goto LABEL_15;
    }
    else if ( v10 < v8 )
    {
LABEL_15:
      v6 += 2;
      v13 = 0;
      goto LABEL_12;
    }
    a2[2] = v6;
    v13 = 1;
LABEL_12:
    *((_DWORD *)a2 + 2) = v13;
  }
  return a2;
}

```

## disassembly

```asm
0x18000eb88  push    rbx
0x18000eb8a  push    rbp
0x18000eb8b  push    rsi
0x18000eb8c  push    rdi
0x18000eb8d  push    r14
0x18000eb8f  sub     rsp, 20h
0x18000eb93  mov     rax, [rcx]
0x18000eb96  mov     rsi, r8
0x18000eb99  mov     rdi, rdx
0x18000eb9c  mov     r9, [rax+8]
0x18000eba0  mov     [rdx], r9
0x18000eba3  mov     rbx, r9
0x18000eba6  mov     qword ptr [rdx+8], 0
0x18000ebae  mov     rax, [rcx]
0x18000ebb1  mov     [rdx+10h], rax
0x18000ebb5  cmp     byte ptr [r9+19h], 0
0x18000ebba  jnz     short loc_18000EC0E
0x18000ebbc  mov     [rdi], rbx
0x18000ebbf  lea     rcx, [rbx+20h]
0x18000ebc3  cmp     qword ptr [rsi+18h], 7
0x18000ebc8  mov     r14, [rsi+10h]
0x18000ebcc  jbe     short loc_18000EBD3
0x18000ebce  mov     rdx, [rsi]
0x18000ebd1  jmp     short loc_18000EBD6
0x18000ebd3  mov     rdx, rsi; S2
0x18000ebd6  cmp     qword ptr [rcx+18h], 7
0x18000ebdb  mov     rbp, [rbx+30h]
0x18000ebdf  jbe     short loc_18000EBE4
0x18000ebe1  mov     rcx, [rcx]; S1
0x18000ebe4  cmp     r14, rbp
0x18000ebe7  mov     r8, r14
0x18000ebea  cmovnb  r8, rbp; N
0x18000ebee  call    wmemcmp
0x18000ebf3  test    eax, eax
0x18000ebf5  jz      short loc_18000EC1C
0x18000ebf7  js      short loc_18000EC21
0x18000ebf9  mov     [rdi+10h], rbx
0x18000ebfd  mov     eax, 1
0x18000ec02  mov     [rdi+8], eax
0x18000ec05  mov     rbx, [rbx]
0x18000ec08  cmp     byte ptr [rbx+19h], 0
0x18000ec0c  jz      short loc_18000EBBC
0x18000ec0e  mov     rax, rdi
0x18000ec11  add     rsp, 20h
0x18000ec15  pop     r14
0x18000ec17  pop     rdi
0x18000ec18  pop     rsi
0x18000ec19  pop     rbp
0x18000ec1a  pop     rbx
0x18000ec1b  retn
0x18000ec1c  cmp     rbp, r14
0x18000ec1f  jnb     short loc_18000EBF9
0x18000ec21  add     rbx, 10h
0x18000ec25  xor     eax, eax
0x18000ec27  jmp     short loc_18000EC02
```
