# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x18002219c`
- end: `0x18002223e`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800222c4`

## callees

- `0x180014ffc`
- `0x180015124`
- `0x180015130`
- `0x180021df4`
- `0x180021e44`
- `0x18002219c`

## pseudocode

```c
struct winrt::impl::shared_hstring_header *__fastcall winrt::impl::precreate_hstring_on_heap(
        winrt::impl *this,
        const char *a2)
{
  __int64 v2; // rbx
  SIZE_T v3; // rsi
  HANDLE ProcessHeap; // rax
  struct winrt::impl::shared_hstring_header *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = (unsigned int)this;
  v3 = 2LL * (unsigned int)this + 32;
  if ( v3 > 0xFFFFFFFF )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, a2);
    throw (std::invalid_argument *)pExceptionObject;
  }
  ProcessHeap = WINRT_IMPL_GetProcessHeap();
  result = (struct winrt::impl::shared_hstring_header *)WINRT_IMPL_HeapAlloc(ProcessHeap, 0, v3);
  if ( !result )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_DWORD *)result + 1) = v2;
  *(_DWORD *)result = 0;
  *((_QWORD *)result + 2) = (char *)result + 28;
  _InterlockedExchange((volatile __int32 *)result + 6, 1);
  *((_WORD *)result + v2 + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x18002219c  mov     [rsp+arg_0], rbx
0x1800221a1  mov     [rsp+arg_8], rsi
0x1800221a6  push    rdi
0x1800221a7  sub     rsp, 40h
0x1800221ab  mov     ebx, ecx
0x1800221ad  mov     eax, 0FFFFFFFFh
0x1800221b2  lea     rsi, ds:20h[rbx*2]
0x1800221ba  cmp     rsi, rax
0x1800221bd  ja      short loc_180022222
0x1800221bf  call    WINRT_IMPL_GetProcessHeap
0x1800221c4  mov     rcx, rax; hHeap
0x1800221c7  mov     r8, rsi; dwBytes
0x1800221ca  xor     edx, edx; dwFlags
0x1800221cc  call    WINRT_IMPL_HeapAlloc
0x1800221d1  xor     ecx, ecx
0x1800221d3  mov     rdx, rax
0x1800221d6  test    rax, rax
0x1800221d9  jz      short loc_180022206
0x1800221db  mov     rsi, [rsp+48h+arg_8]
0x1800221e0  mov     [rax+4], ebx
0x1800221e3  mov     [rax], ecx
0x1800221e5  add     rax, 1Ch
0x1800221e9  mov     [rdx+10h], rax
0x1800221ed  lea     eax, [rcx+1]
0x1800221f0  xchg    eax, [rdx+18h]
0x1800221f3  mov     [rdx+rbx*2+1Ch], cx
0x1800221f8  mov     rax, rdx
0x1800221fb  mov     rbx, [rsp+48h+arg_0]
0x180022200  add     rsp, 40h
0x180022204  pop     rdi
0x180022205  retn
0x180022206  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002220b  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x180022210  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180022217  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002221c  call    _CxxThrowException_0
0x180022222  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180022227  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x18002222c  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180022233  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180022238  call    _CxxThrowException_0
```
