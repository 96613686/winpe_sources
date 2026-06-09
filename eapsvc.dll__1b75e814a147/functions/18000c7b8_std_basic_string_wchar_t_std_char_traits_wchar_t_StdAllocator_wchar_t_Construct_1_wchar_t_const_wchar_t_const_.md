# std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)

- ea: `0x18000c7b8`
- end: `0x18000c877`
- name: `??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXQEB_W_K@Z`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d0f8`
- `0x18000dfb0`
- `0x18000ee60`
- `0x180011698`
- `0x180011cb0`
- `0x1800122b8`

## callees

- `0x18000aafc`
- `0x18000c7b8`
- `0x18000d388`
- `0x18000dc0c`
- `0x180014e8c`

## pseudocode

```c
__int64 __fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Construct<1,wchar_t const *>(
        _QWORD *a1,
        const void *a2,
        unsigned __int64 a3)
{
  __int64 v6; // rbx
  __int64 result; // rax
  unsigned __int64 v8; // rbx
  _WORD *v9; // rax
  _WORD *v10; // rdi

  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 > 7 )
  {
    v8 = a3 | 7;
    if ( (a3 | 7) > 0x7FFFFFFFFFFFFFFELL )
      goto LABEL_10;
    if ( v8 < 0xA )
      v8 = 10;
    if ( v8 + 1 > 0x7FFFFFFF )
LABEL_10:
      LowMemoryError::Throw(L"Possible integer overflow while allocation");
    v9 = operator new(2 * (v8 + 1));
    a1[3] = v8;
    *a1 = v9;
    a1[2] = a3;
    v10 = v9;
    memcpy_0(v9, a2, 2 * a3);
    result = 0;
    v10[a3] = 0;
  }
  else
  {
    v6 = 2 * a3;
    a1[2] = a3;
    a1[3] = 7;
    memcpy_0(a1, a2, 2 * a3);
    result = 0;
    *(_WORD *)((char *)a1 + v6) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000c7b8  push    rbx
0x18000c7ba  push    rbp
0x18000c7bb  push    rsi
0x18000c7bc  push    rdi
0x18000c7bd  push    r14
0x18000c7bf  sub     rsp, 20h
0x18000c7c3  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000c7cd  mov     rsi, r8
0x18000c7d0  mov     rbp, rdx
0x18000c7d3  mov     r14, rcx
0x18000c7d6  cmp     r8, rax
0x18000c7d9  ja      loc_18000C864
0x18000c7df  cmp     r8, 7
0x18000c7e3  ja      short loc_18000C80F
0x18000c7e5  lea     rbx, [r8+r8]
0x18000c7e9  mov     [rcx+10h], r8
0x18000c7ed  mov     r8, rbx; Size
0x18000c7f0  mov     qword ptr [rcx+18h], 7
0x18000c7f8  call    memcpy_0
0x18000c7fd  xor     eax, eax
0x18000c7ff  mov     [rbx+r14], ax
0x18000c804  add     rsp, 20h
0x18000c808  pop     r14
0x18000c80a  pop     rdi
0x18000c80b  pop     rsi
0x18000c80c  pop     rbp
0x18000c80d  pop     rbx
0x18000c80e  retn
0x18000c80f  mov     rbx, rsi
0x18000c812  or      rbx, 7
0x18000c816  cmp     rbx, rax
0x18000c819  ja      short loc_18000C86A
0x18000c81b  mov     eax, 0Ah
0x18000c820  cmp     rbx, rax
0x18000c823  cmovb   rbx, rax
0x18000c827  lea     rcx, [rbx+1]
0x18000c82b  cmp     rcx, 7FFFFFFFh
0x18000c832  ja      short loc_18000C86A
0x18000c834  add     rcx, rcx; dwBytes
0x18000c837  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c83c  mov     [r14+18h], rbx
0x18000c840  mov     rdx, rbp; Src
0x18000c843  lea     rbx, [rsi+rsi]
0x18000c847  mov     [r14], rax
0x18000c84a  mov     r8, rbx; Size
0x18000c84d  mov     [r14+10h], rsi
0x18000c851  mov     rcx, rax; void *
0x18000c854  mov     rdi, rax
0x18000c857  call    memcpy_0
0x18000c85c  xor     eax, eax
0x18000c85e  mov     [rbx+rdi], ax
0x18000c862  jmp     short loc_18000C804
0x18000c864  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000c86a  lea     rcx, aPossibleIntege; "Possible integer overflow while allocat"...
0x18000c871  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
```
