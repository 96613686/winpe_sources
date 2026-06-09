# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180005fac`
- end: `0x18000609a`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `238`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c00`
- `0x1800034c4`

## callees

- `0x180001e9e`
- `0x1800022f2`
- `0x18000239c`
- `0x1800023b4`
- `0x180005fac`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  void **pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  __int128 v6; // [rsp+38h] [rbp-20h]

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    v6 = 0;
    o___std_exception_copy_0();
    pExceptionObject = &std::logic_error::`vftable';
    throw (std::invalid_argument *)&pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    *((_QWORD *)&v6 + 1) = 0;
    *(_QWORD *)&v6 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  *(_DWORD *)result = 0;
  *((_DWORD *)result + 1) = v1;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v1 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x180005fac  push    rbp
0x180005fae  push    rbx
0x180005faf  push    rsi
0x180005fb0  push    rdi
0x180005fb1  mov     rbp, rsp
0x180005fb4  sub     rsp, 58h
0x180005fb8  mov     ebx, ecx
0x180005fba  mov     eax, 0FFFFFFFFh
0x180005fbf  lea     rsi, ds:20h[rbx*2]
0x180005fc7  cmp     rsi, rax
0x180005fca  jbe     short loc_180006026
0x180005fcc  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x180005fd3  xorps   xmm0, xmm0
0x180005fd6  mov     [rbp+pExceptionObject], rax
0x180005fda  lea     rdx, [rbp+var_20]
0x180005fde  lea     rax, aLength; "length"
0x180005fe5  mov     [rbp+var_38], rax
0x180005fe9  lea     rcx, [rbp+var_38]
0x180005fed  mov     eax, 1
0x180005ff2  mov     [rbp+var_30], al
0x180005ff5  xor     eax, eax
0x180005ff7  mov     [rbp+var_2F], eax
0x180005ffa  mov     [rbp+var_2B], ax
0x180005ffe  mov     [rbp+var_29], al
0x180006001  movups  [rbp+var_20], xmm0
0x180006005  call    _o___std_exception_copy_0
0x18000600a  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x180006011  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180006018  mov     [rbp+pExceptionObject], rax
0x18000601c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006020  call    _CxxThrowException_0
0x180006026  call    WINRT_IMPL_GetProcessHeap
0x18000602b  mov     rcx, rax; hHeap
0x18000602e  mov     r8, rsi; dwBytes
0x180006031  xor     edx, edx; dwFlags
0x180006033  call    WINRT_IMPL_HeapAlloc
0x180006038  mov     rcx, rax
0x18000603b  test    rax, rax
0x18000603e  jnz     short loc_18000606E
0x180006040  xorps   xmm0, xmm0
0x180006043  lea     rax, aBadAllocation; "bad allocation"
0x18000604a  movups  [rbp+var_20], xmm0
0x18000604e  mov     qword ptr [rbp+var_20], rax
0x180006052  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006059  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006060  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006064  mov     [rbp+pExceptionObject], rax
0x180006068  call    _CxxThrowException_0
0x18000606e  mov     dword ptr [rax], 0
0x180006074  mov     [rax+4], ebx
0x180006077  add     rax, 1Ch
0x18000607b  mov     [rcx+10h], rax
0x18000607f  mov     eax, 1
0x180006084  xchg    eax, [rcx+18h]
0x180006087  xor     eax, eax
0x180006089  mov     [rcx+rbx*2+1Ch], ax
0x18000608e  mov     rax, rcx
0x180006091  add     rsp, 58h
0x180006095  pop     rdi
0x180006096  pop     rsi
0x180006097  pop     rbx
0x180006098  pop     rbp
0x180006099  retn
```
