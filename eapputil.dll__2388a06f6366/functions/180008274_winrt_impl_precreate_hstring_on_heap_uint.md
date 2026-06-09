# winrt::impl::precreate_hstring_on_heap(uint)

- ea: `0x180008274`
- end: `0x180008316`
- name: `?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z`
- size: `162`
- prototype: `struct winrt::impl::shared_hstring_header *__fastcall(winrt::impl *this, const char *)`
- caller_count: `43`
- callee_count: `6`
- tags: ``

## callers

- `0x180007f3c`
- `0x18000c61c`
- `0x18000d500`
- `0x18000e740`
- `0x18000f480`
- `0x18000f4d0`
- `0x18000f520`
- `0x18000f570`
- `0x180012050`
- `0x1800120a0`
- `0x1800120f0`
- `0x180017e44`
- `0x180017fb8`
- `0x18001aee0`
- `0x18001c070`
- `0x18001c0c0`
- `0x18001c110`
- `0x18001c160`
- `0x18001c1b0`
- `0x18001e980`
- `0x18001ebb4`
- `0x18001eda4`
- `0x180024770`
- `0x180024800`
- `0x1800253d0`
- `0x180025954`
- `0x1800266d0`
- `0x180027a08`
- `0x180027f70`
- `0x180027fc0`
- `0x180028010`
- `0x180028060`
- `0x1800280b0`
- `0x180029814`
- `0x180029aa4`
- `0x18002a2a8`
- `0x18002b0b0`
- `0x18002b28c`
- `0x18002ba80`
- `0x18002bb70`
- `0x18002c670`
- `0x18002c6c0`
- `0x18002c710`

## callees

- `0x180002ccf`
- `0x180002ce7`
- `0x18000395a`
- `0x180008004`
- `0x180008070`
- `0x180008274`

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
0x180008274  mov     [rsp+arg_0], rbx
0x180008279  mov     [rsp+arg_8], rsi
0x18000827e  push    rdi
0x18000827f  sub     rsp, 40h
0x180008283  mov     ebx, ecx
0x180008285  mov     eax, 0FFFFFFFFh
0x18000828a  lea     rsi, ds:20h[rbx*2]
0x180008292  cmp     rsi, rax
0x180008295  ja      short loc_1800082FA
0x180008297  call    WINRT_IMPL_GetProcessHeap
0x18000829c  mov     rcx, rax; hHeap
0x18000829f  mov     r8, rsi; dwBytes
0x1800082a2  xor     edx, edx; dwFlags
0x1800082a4  call    WINRT_IMPL_HeapAlloc
0x1800082a9  xor     ecx, ecx
0x1800082ab  mov     rdx, rax
0x1800082ae  test    rax, rax
0x1800082b1  jz      short loc_1800082DE
0x1800082b3  mov     rsi, [rsp+48h+arg_8]
0x1800082b8  mov     [rax+4], ebx
0x1800082bb  mov     [rax], ecx
0x1800082bd  add     rax, 1Ch
0x1800082c1  mov     [rdx+10h], rax
0x1800082c5  lea     eax, [rcx+1]
0x1800082c8  xchg    eax, [rdx+18h]
0x1800082cb  mov     [rdx+rbx*2+1Ch], cx
0x1800082d0  mov     rax, rdx
0x1800082d3  mov     rbx, [rsp+48h+arg_0]
0x1800082d8  add     rsp, 40h
0x1800082dc  pop     rdi
0x1800082dd  retn
0x1800082de  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800082e3  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1800082e8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800082ef  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800082f4  call    _CxxThrowException_0
0x1800082fa  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800082ff  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180008304  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x18000830b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008310  call    _CxxThrowException_0
```
