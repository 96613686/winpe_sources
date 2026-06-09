# GetWindowsSystemDirectory(void)

- ea: `0x180030ca8`
- end: `0x180030de9`
- name: `?GetWindowsSystemDirectory@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@XZ`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001fdf4`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x180030088`
- `0x1800302bc`
- `0x1800302e0`
- `0x180030994`
- `0x180030c84`
- `0x180030ca8`
- `0x180035138`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180030d12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180030d85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180030d12`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180030d85`

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
  LPWSTR lpBuffer; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v10; // [rsp+38h] [rbp-C8h]
  WCHAR v11[260]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+248h] [rbp+148h]

  lpBuffer = v11;
  v10 = 520;
  v12 = 0;
  memset_0(v11, 0, 0x104u);
  SystemDirectoryW = GetSystemDirectoryW(v11, 0x104u);
  if ( SystemDirectoryW >= 0x104 )
  {
    if ( 2 * (unsigned __int64)SystemDirectoryW <= v10 )
    {
      v5 = lpBuffer;
    }
    else
    {
      v3 = v12;
      v4 = (WCHAR *)Heap::AllocNoThrow((Heap *)&HeapAllocator::heap, 2LL * SystemDirectoryW);
      v5 = v4;
      if ( !v4 )
        ThrowNewFailure();
      memcpy_0(v4, lpBuffer, 2 * v3);
      TempBuffer<520>::Destroy(&lpBuffer);
      lpBuffer = v5;
      v10 = 2LL * SystemDirectoryW;
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
  TempBuffer<520>::Destroy(&lpBuffer);
  return a1;
}

```

## disassembly

```asm
0x180030ca8  push    rbp
0x180030caa  push    rbx
0x180030cab  push    rsi
0x180030cac  push    rdi
0x180030cad  push    r14
0x180030caf  push    r15
0x180030cb1  lea     rbp, [rsp-168h]
0x180030cb9  sub     rsp, 268h
0x180030cc0  mov     rax, cs:__security_cookie
0x180030cc7  xor     rax, rsp
0x180030cca  mov     [rbp+190h+var_40], rax
0x180030cd1  mov     r14, rcx
0x180030cd4  mov     [rsp+290h+var_268], rcx
0x180030cd9  lea     rax, [rsp+290h+var_250]
0x180030cde  mov     [rsp+290h+lpBuffer], rax
0x180030ce3  mov     [rsp+290h+var_258], 208h
0x180030cec  mov     [rbp+190h+var_48], 0
0x180030cf7  mov     ebx, 104h
0x180030cfc  mov     r8d, ebx; Size
0x180030cff  xor     edx, edx; Val
0x180030d01  lea     rcx, [rsp+290h+var_250]; void *
0x180030d06  call    memset_0
0x180030d0b  mov     edx, ebx; uSize
0x180030d0d  mov     rcx, [rsp+290h+lpBuffer]; lpBuffer
0x180030d12  call    cs:__imp_GetSystemDirectoryW
0x180030d19  nop     dword ptr [rax+rax+00h]
0x180030d1e  mov     edi, eax
0x180030d20  cmp     eax, ebx
0x180030d22  jb      short loc_180030D93
0x180030d24  mov     ebx, edi
0x180030d26  add     rbx, rbx
0x180030d29  cmp     rbx, [rsp+290h+var_258]
0x180030d2e  jbe     short loc_180030D7B
0x180030d30  mov     r15, [rbp+190h+var_48]
0x180030d37  mov     rdx, rbx; unsigned __int64
0x180030d3a  lea     rcx, ?heap@HeapAllocator@@0V?$StaticObject@VHeap@@@@A; this
0x180030d41  call    ?AllocNoThrow@Heap@@QEAAPEAX_K@Z; Heap::AllocNoThrow(unsigned __int64)
0x180030d46  mov     rsi, rax
0x180030d49  test    rax, rax
0x180030d4c  jz      short loc_180030D75
0x180030d4e  lea     r8, [r15+r15]; Size
0x180030d52  mov     rdx, [rsp+290h+lpBuffer]; Src
0x180030d57  mov     rcx, rax; void *
0x180030d5a  call    memcpy_0
0x180030d5f  lea     rcx, [rsp+290h+lpBuffer]
0x180030d64  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x180030d69  mov     [rsp+290h+lpBuffer], rsi
0x180030d6e  mov     [rsp+290h+var_258], rbx
0x180030d73  jmp     short loc_180030D80
0x180030d75  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
0x180030d7b  mov     rsi, [rsp+290h+lpBuffer]
0x180030d80  mov     edx, edi; uSize
0x180030d82  mov     rcx, rsi; lpBuffer
0x180030d85  call    cs:__imp_GetSystemDirectoryW
0x180030d8c  nop     dword ptr [rax+rax+00h]
0x180030d91  mov     edi, eax
0x180030d93  test    edi, edi
0x180030d95  jnz     short loc_180030DAB
0x180030d97  call    cs:__imp_GetLastError
0x180030d9e  nop     dword ptr [rax+rax+00h]
0x180030da3  mov     edx, eax
0x180030da5  call    ??$Throw@K@SystemError@@SAXPEB_WK@Z; SystemError::Throw<ulong>(wchar_t const *,ulong)
0x180030dab  mov     r8d, edi
0x180030dae  mov     rdx, [rsp+290h+lpBuffer]
0x180030db3  mov     rcx, r14
0x180030db6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const,unsigned __int64)
0x180030dbb  nop
0x180030dbc  lea     rcx, [rsp+290h+lpBuffer]
0x180030dc1  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x180030dc6  mov     rax, r14
0x180030dc9  mov     rcx, [rbp+190h+var_40]
0x180030dd0  xor     rcx, rsp; StackCookie
0x180030dd3  call    __security_check_cookie
0x180030dd8  add     rsp, 268h
0x180030ddf  pop     r15
0x180030de1  pop     r14
0x180030de3  pop     rdi
0x180030de4  pop     rsi
0x180030de5  pop     rbx
0x180030de6  pop     rbp
0x180030de7  retn
```
