# GetWindowsSystemDirectory(void)

- ea: `0x180011d8c`
- end: `0x180011ece`
- name: `?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `322`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800141b0`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x18000439c`
- `0x180011ac4`
- `0x180011c0c`
- `0x180011c30`
- `0x180011d8c`
- `0x1800127c0`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011df6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011e6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011df6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180011e6d`

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
0x180011d8c  push    rbp
0x180011d8e  push    rbx
0x180011d8f  push    rsi
0x180011d90  push    rdi
0x180011d91  push    r14
0x180011d93  push    r15
0x180011d95  lea     rbp, [rsp-168h]
0x180011d9d  sub     rsp, 268h
0x180011da4  mov     rax, cs:__security_cookie
0x180011dab  xor     rax, rsp
0x180011dae  mov     [rbp+190h+var_40], rax
0x180011db5  mov     r14, rcx
0x180011db8  mov     [rsp+290h+var_268], rcx
0x180011dbd  lea     rax, [rsp+290h+var_250]
0x180011dc2  mov     [rsp+290h+lpBuffer], rax
0x180011dc7  mov     [rsp+290h+var_258], 208h
0x180011dd0  mov     [rbp+190h+var_48], 0
0x180011ddb  mov     ebx, 104h
0x180011de0  mov     r8d, ebx; Size
0x180011de3  xor     edx, edx; Val
0x180011de5  lea     rcx, [rsp+290h+var_250]; void *
0x180011dea  call    memset_0
0x180011def  mov     edx, ebx; uSize
0x180011df1  mov     rcx, [rsp+290h+lpBuffer]; lpBuffer
0x180011df6  call    cs:__imp_GetSystemDirectoryW
0x180011dfc  mov     edi, eax
0x180011dfe  cmp     eax, ebx
0x180011e00  jb      short loc_180011E75
0x180011e02  mov     ebx, edi
0x180011e04  add     rbx, rbx
0x180011e07  cmp     rbx, [rsp+290h+var_258]
0x180011e0c  jbe     short loc_180011E63
0x180011e0e  mov     r15, [rbp+190h+var_48]
0x180011e15  mov     rdx, rbx; unsigned __int64
0x180011e18  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180011e1f  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180011e24  mov     rsi, rax
0x180011e27  test    rax, rax
0x180011e2a  jz      short loc_180011E5D
0x180011e2c  lea     r8, [r15+r15]; Size
0x180011e30  mov     rdx, [rsp+290h+lpBuffer]; Src
0x180011e35  mov     rcx, rax; void *
0x180011e38  call    memcpy_0
0x180011e3d  lea     rax, [rsp+290h+var_250]
0x180011e42  mov     rcx, [rsp+290h+lpBuffer]; void *
0x180011e47  cmp     rcx, rax
0x180011e4a  jz      short loc_180011E51
0x180011e4c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180011e51  mov     [rsp+290h+lpBuffer], rsi
0x180011e56  mov     [rsp+290h+var_258], rbx
0x180011e5b  jmp     short loc_180011E68
0x180011e5d  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
0x180011e63  mov     rsi, [rsp+290h+lpBuffer]
0x180011e68  mov     edx, edi; uSize
0x180011e6a  mov     rcx, rsi; lpBuffer
0x180011e6d  call    cs:__imp_GetSystemDirectoryW
0x180011e73  mov     edi, eax
0x180011e75  test    edi, edi
0x180011e77  jnz     short loc_180011E87
0x180011e79  call    cs:__imp_GetLastError
0x180011e7f  mov     edx, eax
0x180011e81  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x180011e87  mov     r8d, edi
0x180011e8a  mov     rdx, [rsp+290h+lpBuffer]
0x180011e8f  mov     rcx, r14
0x180011e92  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x180011e97  nop
0x180011e98  lea     rax, [rsp+290h+var_250]
0x180011e9d  mov     rcx, [rsp+290h+lpBuffer]; void *
0x180011ea2  cmp     rcx, rax
0x180011ea5  jz      short loc_180011EAC
0x180011ea7  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180011eac  mov     rax, r14
0x180011eaf  mov     rcx, [rbp+190h+var_40]
0x180011eb6  xor     rcx, rsp; StackCookie
0x180011eb9  call    __security_check_cookie
0x180011ebe  add     rsp, 268h
0x180011ec5  pop     r15
0x180011ec7  pop     r14
0x180011ec9  pop     rdi
0x180011eca  pop     rsi
0x180011ecb  pop     rbx
0x180011ecc  pop     rbp
0x180011ecd  retn
```
