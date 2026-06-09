# CNameSpaceInfo::CNameSpaceStacks::OpenStack(basic_xstr_t<wchar_t> const &)

- ea: `0x180020488`
- end: `0x180020548`
- name: `?OpenStack@CNameSpaceStacks@CNameSpaceInfo@@AEAAAEAV?$List@VCNsUriNode@@$0A@@@AEBV?$basic_xstr_t@_W@@@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180020550`

## callees

- `0x180020220`
- `0x180020488`
- `0x180020930`
- `0x180020e7c`
- `0x180021010`
- `0x180023c42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CNameSpaceInfo::CNameSpaceStacks::OpenStack(__int64 a1, const void **a2)
{
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rbx
  int v6; // ebp
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  char v12[16]; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+30h] [rbp-48h] BYREF
  _QWORD *v14; // [rsp+40h] [rbp-38h]
  _QWORD *v15; // [rsp+80h] [rbp+8h] BYREF

  v3 = a1 + 16;
  v4 = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(a1 + 16);
  v5 = v4;
  if ( v4 != *(_QWORD *)(v3 + 8) )
  {
    v6 = *(_DWORD *)(v4 + 24);
    v7 = *(_DWORD *)a2;
    if ( *(_DWORD *)a2 >= v6 )
      v7 = v6;
    v8 = memcmp_0(a2[1], *(const void **)(v5 + 32), 2LL * v7);
    if ( v8 )
    {
      if ( v8 < 0 )
        goto LABEL_6;
    }
    else if ( *(_DWORD *)a2 < v6 )
    {
      goto LABEL_6;
    }
    return *(_QWORD **)(v5 + 40);
  }
LABEL_6:
  v9 = MmAllocate(0x10u);
  v10 = v9;
  v15 = v9;
  if ( v9 )
  {
    *v9 = v9;
    v9[1] = v9;
  }
  else
  {
    v10 = 0;
  }
  v15 = v10;
  v13 = *(_OWORD *)a2;
  v14 = v10;
  std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::insert(
    v3,
    v12,
    &v13);
  v15 = 0;
  P<List<CNsUriNode,0>>::~P<List<CNsUriNode,0>>(&v15);
  return v10;
}

```

## disassembly

```asm
0x180020488  push    rbx
0x18002048a  push    rbp
0x18002048b  push    rsi
0x18002048c  push    rdi
0x18002048d  sub     rsp, 58h
0x180020491  mov     rdi, rdx
0x180020494  lea     rsi, [rcx+10h]
0x180020498  mov     rcx, rsi
0x18002049b  call    ?_Lbound@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEBAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@AEBV?$basic_xstr_t@_W@@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(basic_xstr_t<wchar_t> const &)
0x1800204a0  mov     rbx, rax
0x1800204a3  cmp     rax, [rsi+8]
0x1800204a7  jz      short loc_1800204CC
0x1800204a9  mov     ebp, [rax+18h]
0x1800204ac  mov     eax, [rdi]
0x1800204ae  cmp     eax, ebp
0x1800204b0  cmovge  eax, ebp
0x1800204b3  movsxd  r8, eax
0x1800204b6  add     r8, r8; Size
0x1800204b9  mov     rdx, [rbx+20h]; Buf2
0x1800204bd  mov     rcx, [rdi+8]; Buf1
0x1800204c1  call    memcmp_0
0x1800204c6  test    eax, eax
0x1800204c8  jz      short loc_1800204EF
0x1800204ca  jns     short loc_1800204F3
0x1800204cc  mov     ecx, 10h; unsigned __int64
0x1800204d1  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800204d6  mov     rbx, rax
0x1800204d9  mov     [rsp+78h+arg_0], rax
0x1800204e1  test    rax, rax
0x1800204e4  jz      short loc_1800204F9
0x1800204e6  mov     [rax], rax
0x1800204e9  mov     [rax+8], rax
0x1800204ed  jmp     short loc_1800204FB
0x1800204ef  cmp     [rdi], ebp
0x1800204f1  jl      short loc_1800204CC
0x1800204f3  mov     rax, [rbx+28h]
0x1800204f7  jmp     short loc_18002053F
0x1800204f9  xor     ebx, ebx
0x1800204fb  mov     [rsp+78h+arg_0], rbx
0x180020503  movups  xmm0, xmmword ptr [rdi]
0x180020506  movdqu  [rsp+78h+var_48], xmm0
0x18002050c  mov     [rsp+78h+var_38], rbx
0x180020511  lea     r8, [rsp+78h+var_48]
0x180020516  lea     rdx, [rsp+78h+var_58]
0x18002051b  mov     rcx, rsi
0x18002051e  call    ?insert@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::insert(std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &)
0x180020523  mov     [rsp+78h+arg_0], 0
0x18002052f  lea     rcx, [rsp+78h+arg_0]
0x180020537  call    ??1?$P@V?$List@VCNsUriNode@@$0A@@@@@QEAA@XZ; P<List<CNsUriNode,0>>::~P<List<CNsUriNode,0>>(void)
0x18002053c  mov     rax, rbx
0x18002053f  add     rsp, 58h
0x180020543  pop     rdi
0x180020544  pop     rsi
0x180020545  pop     rbp
0x180020546  pop     rbx
0x180020547  retn
```
