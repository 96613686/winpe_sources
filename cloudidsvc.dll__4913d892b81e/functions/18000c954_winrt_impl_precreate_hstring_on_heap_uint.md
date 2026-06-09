# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18000c954`
- end: `0x18000ca42`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `238`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000cd9c`

## callees

- `0x1800023f6`
- `0x1800024fc`
- `0x180002568`
- `0x180002574`
- `0x18000c954`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(winrt::impl *this)
{
  __int64 v1; // rbx
  SIZE_T v2; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  const char *v5; // [rsp+20h] [rbp-38h] BYREF
  char v6; // [rsp+28h] [rbp-30h]
  int v7; // [rsp+29h] [rbp-2Fh]
  __int16 v8; // [rsp+2Dh] [rbp-2Bh]
  char v9; // [rsp+2Fh] [rbp-29h]
  void **pExceptionObject; // [rsp+30h] [rbp-28h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h] BYREF

  v1 = (unsigned int)this;
  v2 = 2LL * (unsigned int)this + 32;
  if ( v2 > 0xFFFFFFFF )
  {
    pExceptionObject = &std::exception::`vftable';
    v5 = "length";
    v6 = 1;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    v11 = 0;
    o___std_exception_copy_0(&v5, &v11);
    pExceptionObject = &std::logic_error::`vftable';
    throw (std::invalid_argument *)&pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v2);
  if ( !result )
  {
    *((_QWORD *)&v11 + 1) = 0;
    *(_QWORD *)&v11 = "bad allocation";
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
0x18000c954  push    rbp
0x18000c956  push    rbx
0x18000c957  push    rsi
0x18000c958  push    rdi
0x18000c959  mov     rbp, rsp
0x18000c95c  sub     rsp, 58h
0x18000c960  mov     ebx, ecx
0x18000c962  mov     eax, 0FFFFFFFFh
0x18000c967  lea     rsi, ds:20h[rbx*2]
0x18000c96f  cmp     rsi, rax
0x18000c972  jbe     short loc_18000C9CE
0x18000c974  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18000c97b  xorps   xmm0, xmm0
0x18000c97e  mov     [rbp+pExceptionObject], rax
0x18000c982  lea     rdx, [rbp+var_20]
0x18000c986  lea     rax, aLength; "length"
0x18000c98d  mov     [rbp+var_38], rax
0x18000c991  lea     rcx, [rbp+var_38]
0x18000c995  mov     eax, 1
0x18000c99a  mov     [rbp+var_30], al
0x18000c99d  xor     eax, eax
0x18000c99f  mov     [rbp+var_2F], eax
0x18000c9a2  mov     [rbp+var_2B], ax
0x18000c9a6  mov     [rbp+var_29], al
0x18000c9a9  movups  [rbp+var_20], xmm0
0x18000c9ad  call    _o___std_exception_copy_0
0x18000c9b2  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18000c9b9  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000c9c0  mov     [rbp+pExceptionObject], rax
0x18000c9c4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000c9c8  call    _CxxThrowException_0
0x18000c9ce  call    WINRT_IMPL_GetProcessHeap
0x18000c9d3  mov     rcx, rax; hHeap
0x18000c9d6  mov     r8, rsi; dwBytes
0x18000c9d9  xor     edx, edx; dwFlags
0x18000c9db  call    WINRT_IMPL_HeapAlloc
0x18000c9e0  mov     rcx, rax
0x18000c9e3  test    rax, rax
0x18000c9e6  jnz     short loc_18000CA16
0x18000c9e8  xorps   xmm0, xmm0
0x18000c9eb  lea     rax, aBadAllocation; "bad allocation"
0x18000c9f2  movups  [rbp+var_20], xmm0
0x18000c9f6  mov     qword ptr [rbp+var_20], rax
0x18000c9fa  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000ca01  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000ca08  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ca0c  mov     [rbp+pExceptionObject], rax
0x18000ca10  call    _CxxThrowException_0
0x18000ca16  mov     dword ptr [rax], 0
0x18000ca1c  mov     [rax+4], ebx
0x18000ca1f  add     rax, 1Ch
0x18000ca23  mov     [rcx+10h], rax
0x18000ca27  mov     eax, 1
0x18000ca2c  xchg    eax, [rcx+18h]
0x18000ca2f  xor     eax, eax
0x18000ca31  mov     [rcx+rbx*2+1Ch], ax
0x18000ca36  mov     rax, rcx
0x18000ca39  add     rsp, 58h
0x18000ca3d  pop     rdi
0x18000ca3e  pop     rsi
0x18000ca3f  pop     rbx
0x18000ca40  pop     rbp
0x18000ca41  retn
```
