# RtlStringCchPrintfW

- ea: `0x1400031a0`
- end: `0x14000322a`
- name: `RtlStringCchPrintfW`
- size: `138`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140011438`
- `0x140014f00`
- `0x140015350`

## callees

- `0x1400031a0`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x1400031db`
- `ntoskrnl!_vsnwprintf` at `0x1400031db`

## pseudocode

```c
NTSTATUS RtlStringCchPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  NTSTATUS result; // eax
  size_t v5; // rsi
  NTSTATUS v6; // ebx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = 0;
    v7 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v7 < 0 || v7 > v5 )
    {
      pszDest[v5] = 0;
      return -2147483643;
    }
    else if ( v7 == v5 )
    {
      pszDest[v5] = 0;
    }
    return v6;
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400031a0  mov     [rsp+arg_10], r8
0x1400031a5  mov     qword ptr [rsp+Args], r9
0x1400031aa  push    rbx
0x1400031ab  push    rdi
0x1400031ac  sub     rsp, 38h
0x1400031b0  mov     rdi, rcx
0x1400031b3  test    rdx, rdx
0x1400031b6  jz      short loc_140003213
0x1400031b8  cmp     rdx, 7FFFFFFFh
0x1400031bf  jbe     short loc_1400031C8
0x1400031c1  mov     eax, 0C000000Dh
0x1400031c6  jmp     short loc_14000321D
0x1400031c8  mov     [rsp+48h+var_18], rsi
0x1400031cd  lea     r9, [rsp+48h+Args]; Args
0x1400031d2  lea     rsi, [rdx-1]
0x1400031d6  xor     ebx, ebx
0x1400031d8  mov     rdx, rsi; Count
0x1400031db  call    cs:__imp__vsnwprintf
0x1400031e2  nop     dword ptr [rax+rax+00h]
0x1400031e7  test    eax, eax
0x1400031e9  js      short loc_1400031FB
0x1400031eb  movsxd  rcx, eax
0x1400031ee  cmp     rcx, rsi
0x1400031f1  ja      short loc_1400031FB
0x1400031f3  jnz     short loc_140003204
0x1400031f5  mov     [rdi+rsi*2], bx
0x1400031f9  jmp     short loc_140003204
0x1400031fb  mov     [rdi+rsi*2], bx
0x1400031ff  mov     ebx, 80000005h
0x140003204  mov     rsi, [rsp+48h+var_18]
0x140003209  mov     eax, ebx
0x14000320b  add     rsp, 38h
0x14000320f  pop     rdi
0x140003210  pop     rbx
0x140003211  retn
0x140003213  mov     eax, 0C000000Dh
0x140003218  test    rdx, rdx
0x14000321b  jz      short loc_140003222
0x14000321d  xor     ebx, ebx
0x14000321f  mov     [rcx], bx
0x140003222  add     rsp, 38h
0x140003226  pop     rdi
0x140003227  pop     rbx
0x140003228  retn
```
