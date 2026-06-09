# std::make_pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &)

- ea: `0x18001140c`
- end: `0x1800114f8`
- name: `??$make_pair@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAV?$CComPtr@UIUMBusPDO@@@ATL@@@std@@YA?AU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@AEAV?$CComPtr@UIUMBusPDO@@@ATL@@@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180012cf8`

## callees

- `0x18000aafc`
- `0x18000d388`
- `0x18000dc0c`
- `0x18001140c`
- `0x180014e8c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall std::make_pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &,ATL::CComPtr<IUMBusPDO> &>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  _OWORD *v4; // r14
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // rdi
  void *v8; // rax
  __int64 v9; // rcx

  v4 = (_OWORD *)a2;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v6 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v4 = *(_OWORD **)a2;
  if ( v6 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v6 > 7 )
  {
    v7 = v6 | 7;
    if ( (v6 | 7) > 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_15;
    if ( v7 < 0xA )
      v7 = 10;
    if ( v7 + 1 > 0x7FFFFFFF )
LABEL_15:
      LowMemoryError::Throw(L"Possible integer overflow while allocation");
    v8 = operator new(2 * (v7 + 1));
    *(_QWORD *)a1 = v8;
    *(_QWORD *)(a1 + 16) = v6;
    *(_QWORD *)(a1 + 24) = v7;
    memcpy_0(v8, v4, 2 * v6 + 2);
  }
  else
  {
    *(_QWORD *)(a1 + 16) = v6;
    *(_QWORD *)(a1 + 24) = 7;
    *(_OWORD *)a1 = *v4;
  }
  v9 = *a3;
  *(_QWORD *)(a1 + 32) = *a3;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  return a1;
}

```

## disassembly

```asm
0x18001140c  push    rbx
0x18001140e  push    rsi
0x18001140f  push    rdi
0x180011410  push    r14
0x180011412  push    r15
0x180011414  sub     rsp, 30h
0x180011418  mov     r15, r8
0x18001141b  mov     r14, rdx
0x18001141e  mov     rbx, rcx
0x180011421  xorps   xmm0, xmm0
0x180011424  movups  xmmword ptr [rcx], xmm0
0x180011427  mov     qword ptr [rcx+10h], 0
0x18001142f  mov     qword ptr [rcx+18h], 0
0x180011437  mov     rsi, [rdx+10h]
0x18001143b  mov     eax, 7
0x180011440  cmp     [rdx+18h], rax
0x180011444  jbe     short loc_180011449
0x180011446  mov     r14, [rdx]
0x180011449  mov     rcx, 7FFFFFFFFFFFFFFEh
0x180011453  cmp     rsi, rcx
0x180011456  ja      loc_1800114E5
0x18001145c  cmp     rsi, rax
0x18001145f  ja      short loc_180011473
0x180011461  mov     [rbx+10h], rsi
0x180011465  mov     [rbx+18h], rax
0x180011469  movups  xmm0, xmmword ptr [r14]
0x18001146d  movdqu  xmmword ptr [rbx], xmm0
0x180011471  jmp     short loc_1800114BD
0x180011473  mov     rdi, rsi
0x180011476  or      rdi, rax
0x180011479  cmp     rdi, rcx
0x18001147c  ja      short loc_1800114EB
0x18001147e  mov     eax, 0Ah
0x180011483  cmp     rdi, rax
0x180011486  cmovb   rdi, rax
0x18001148a  lea     rcx, [rdi+1]
0x18001148e  cmp     rcx, 7FFFFFFFh
0x180011495  ja      short loc_1800114EB
0x180011497  add     rcx, rcx; dwBytes
0x18001149a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001149f  mov     [rbx], rax
0x1800114a2  mov     [rbx+10h], rsi
0x1800114a6  mov     [rbx+18h], rdi
0x1800114aa  lea     r8, ds:2[rsi*2]; Size
0x1800114b2  mov     rdx, r14; Src
0x1800114b5  mov     rcx, rax; void *
0x1800114b8  call    memcpy_0
0x1800114bd  mov     rcx, [r15]
0x1800114c0  mov     [rbx+20h], rcx
0x1800114c4  test    rcx, rcx
0x1800114c7  jz      short loc_1800114D6
0x1800114c9  mov     rax, [rcx]
0x1800114cc  mov     rax, [rax+8]
0x1800114d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114d5  nop
0x1800114d6  mov     rax, rbx
0x1800114d9  add     rsp, 30h
0x1800114dd  pop     r15
0x1800114df  pop     r14
0x1800114e1  pop     rdi
0x1800114e2  pop     rsi
0x1800114e3  pop     rbx
0x1800114e4  retn
0x1800114e5  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800114eb  lea     rcx, aPossibleIntege; "Possible integer overflow while allocat"...
0x1800114f2  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
```
