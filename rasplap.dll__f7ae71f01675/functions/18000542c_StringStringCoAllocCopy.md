# _StringStringCoAllocCopy

- ea: `0x18000542c`
- end: `0x1800054a3`
- name: `_StringStringCoAllocCopy`
- size: `119`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800040f0`
- `0x180004e74`

## callees

- `0x18000542c`
- `0x1800056d4`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000545a`
- `ole32!CoTaskMemAlloc` at `0x18000545a`
- `ole32!CoTaskMemFree` at `0x180005484`
- `ole32!CoTaskMemFree` at `0x180005484`

## pseudocode

```c
__int64 __fastcall StringStringCoAllocCopy(STRSAFE_LPCWSTR pszSrc, _QWORD *a2)
{
  unsigned __int64 v2; // rax
  size_t v5; // rbx
  wchar_t *v6; // rax
  HRESULT v7; // ebx
  void *v8; // r11

  v2 = -1;
  do
    ++v2;
  while ( pszSrc[v2] );
  if ( v2 > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    v5 = v2 + 1;
    v6 = (wchar_t *)CoTaskMemAlloc(2 * (v2 + 1));
    if ( v6 )
    {
      v7 = StringCchCopyW(v6, v5, pszSrc);
      if ( v7 < 0 )
        CoTaskMemFree(v8);
      else
        *a2 = v8;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000542c  push    rbx
0x18000542e  push    rbp
0x18000542f  push    rsi
0x180005430  push    rdi
0x180005431  sub     rsp, 28h
0x180005435  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005439  mov     rsi, rdx
0x18000543c  xor     ebp, ebp
0x18000543e  mov     rdi, rcx
0x180005441  inc     rax
0x180005444  cmp     [rcx+rax*2], bp
0x180005448  jnz     short loc_180005441
0x18000544a  cmp     rax, 7FFFFFFEh
0x180005450  ja      short loc_180005493
0x180005452  lea     rbx, [rax+1]
0x180005456  lea     rcx, [rbx+rbx]; cb
0x18000545a  call    cs:__imp_CoTaskMemAlloc
0x180005460  mov     r11, rax
0x180005463  test    rax, rax
0x180005466  jz      short loc_18000548C
0x180005468  mov     r8, rdi; pszSrc
0x18000546b  mov     rdx, rbx; cchDest
0x18000546e  mov     rcx, rax; pszDest
0x180005471  call    StringCchCopyW
0x180005476  mov     ebx, eax
0x180005478  test    eax, eax
0x18000547a  js      short loc_180005481
0x18000547c  mov     [rsi], r11
0x18000547f  jmp     short loc_180005498
0x180005481  mov     rcx, r11; pv
0x180005484  call    cs:__imp_CoTaskMemFree
0x18000548a  jmp     short loc_180005498
0x18000548c  mov     ebx, 8007000Eh
0x180005491  jmp     short loc_180005498
0x180005493  mov     ebx, 80070216h
0x180005498  mov     eax, ebx
0x18000549a  add     rsp, 28h
0x18000549e  pop     rdi
0x18000549f  pop     rsi
0x1800054a0  pop     rbp
0x1800054a1  pop     rbx
0x1800054a2  retn
```
