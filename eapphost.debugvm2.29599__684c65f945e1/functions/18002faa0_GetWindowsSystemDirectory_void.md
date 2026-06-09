# GetWindowsSystemDirectory(void)

- ea: `0x18002faa0`
- end: `0x18002fbe2`
- name: `?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001f2b4`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x1800072cc`
- `0x18002ef80`
- `0x18002f184`
- `0x18002f1a8`
- `0x18002f7ec`
- `0x18002faa0`
- `0x180033d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002fb0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002fb81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002fb0a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002fb81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetWindowsSystemDirectory(__int64 a1)
{
  UINT SystemDirectoryW; // edi
  __int64 v3; // r15
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // eax
  __int64 v7; // rcx
  LPWSTR lpBuffer; // [rsp+30h] [rbp-D0h]
  WCHAR v10[260]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v11; // [rsp+248h] [rbp+148h]

  lpBuffer = v10;
  v11 = 0;
  memset_0(v10, 0, 0x104u);
  SystemDirectoryW = GetSystemDirectoryW(v10, 0x104u);
  if ( SystemDirectoryW >= 0x104 )
  {
    if ( 2 * (unsigned __int64)SystemDirectoryW <= 0x208 )
    {
      v5 = v10;
    }
    else
    {
      v3 = v11;
      v4 = (WCHAR *)Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 2LL * SystemDirectoryW);
      v5 = v4;
      if ( !v4 )
        ThrowNewFailure();
      memcpy_0(v4, v10, 2 * v3);
      lpBuffer = v5;
    }
    SystemDirectoryW = GetSystemDirectoryW(v5, SystemDirectoryW);
  }
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    SystemError::Throw<unsigned long>(v7, LastError);
  }
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    a1,
    lpBuffer,
    SystemDirectoryW);
  if ( lpBuffer != v10 )
    HeapAllocator::Free(lpBuffer);
  return a1;
}

```

## disassembly

```asm
0x18002faa0  push    rbp
0x18002faa2  push    rbx
0x18002faa3  push    rsi
0x18002faa4  push    rdi
0x18002faa5  push    r14
0x18002faa7  push    r15
0x18002faa9  lea     rbp, [rsp-168h]
0x18002fab1  sub     rsp, 268h
0x18002fab8  mov     rax, cs:__security_cookie
0x18002fabf  xor     rax, rsp
0x18002fac2  mov     [rbp+190h+var_40], rax
0x18002fac9  mov     r14, rcx
0x18002facc  mov     [rsp+290h+var_268], rcx
0x18002fad1  lea     rax, [rsp+290h+var_250]
0x18002fad6  mov     [rsp+290h+lpBuffer], rax
0x18002fadb  mov     [rsp+290h+var_258], 208h
0x18002fae4  mov     [rbp+190h+var_48], 0
0x18002faef  mov     ebx, 104h
0x18002faf4  mov     r8d, ebx; Size
0x18002faf7  xor     edx, edx; Val
0x18002faf9  lea     rcx, [rsp+290h+var_250]; void *
0x18002fafe  call    memset_0
0x18002fb03  mov     edx, ebx; uSize
0x18002fb05  mov     rcx, [rsp+290h+lpBuffer]; lpBuffer
0x18002fb0a  call    cs:__imp_GetSystemDirectoryW
0x18002fb10  mov     edi, eax
0x18002fb12  cmp     eax, ebx
0x18002fb14  jb      short loc_18002FB89
0x18002fb16  mov     ebx, edi
0x18002fb18  add     rbx, rbx
0x18002fb1b  cmp     rbx, [rsp+290h+var_258]
0x18002fb20  jbe     short loc_18002FB77
0x18002fb22  mov     r15, [rbp+190h+var_48]
0x18002fb29  mov     rdx, rbx; unsigned __int64
0x18002fb2c  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x18002fb33  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x18002fb38  mov     rsi, rax
0x18002fb3b  test    rax, rax
0x18002fb3e  jz      short loc_18002FB71
0x18002fb40  lea     r8, [r15+r15]; Size
0x18002fb44  mov     rdx, [rsp+290h+lpBuffer]; Src
0x18002fb49  mov     rcx, rax; void *
0x18002fb4c  call    memcpy_0
0x18002fb51  lea     rax, [rsp+290h+var_250]
0x18002fb56  mov     rcx, [rsp+290h+lpBuffer]; void *
0x18002fb5b  cmp     rcx, rax
0x18002fb5e  jz      short loc_18002FB65
0x18002fb60  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002fb65  mov     [rsp+290h+lpBuffer], rsi
0x18002fb6a  mov     [rsp+290h+var_258], rbx
0x18002fb6f  jmp     short loc_18002FB7C
0x18002fb71  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
0x18002fb77  mov     rsi, [rsp+290h+lpBuffer]
0x18002fb7c  mov     edx, edi; uSize
0x18002fb7e  mov     rcx, rsi; lpBuffer
0x18002fb81  call    cs:__imp_GetSystemDirectoryW
0x18002fb87  mov     edi, eax
0x18002fb89  test    edi, edi
0x18002fb8b  jnz     short loc_18002FB9B
0x18002fb8d  call    cs:__imp_GetLastError
0x18002fb93  mov     edx, eax
0x18002fb95  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x18002fb9b  mov     r8d, edi
0x18002fb9e  mov     rdx, [rsp+290h+lpBuffer]
0x18002fba3  mov     rcx, r14
0x18002fba6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x18002fbab  nop
0x18002fbac  lea     rax, [rsp+290h+var_250]
0x18002fbb1  mov     rcx, [rsp+290h+lpBuffer]; void *
0x18002fbb6  cmp     rcx, rax
0x18002fbb9  jz      short loc_18002FBC0
0x18002fbbb  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002fbc0  mov     rax, r14
0x18002fbc3  mov     rcx, [rbp+190h+var_40]
0x18002fbca  xor     rcx, rsp; StackCookie
0x18002fbcd  call    __security_check_cookie
0x18002fbd2  add     rsp, 268h
0x18002fbd9  pop     r15
0x18002fbdb  pop     r14
0x18002fbdd  pop     rdi
0x18002fbde  pop     rsi
0x18002fbdf  pop     rbx
0x18002fbe0  pop     rbp
0x18002fbe1  retn
```
