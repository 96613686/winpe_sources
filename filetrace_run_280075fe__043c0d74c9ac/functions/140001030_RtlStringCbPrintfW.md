# RtlStringCbPrintfW

- ea: `0x140001030`
- end: `0x1400010aa`
- name: `RtlStringCbPrintfW`
- size: `122`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e2f0`

## callees

- `0x140001030`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140001067`
- `ntoskrnl!_vsnwprintf` at `0x140001067`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v4; // rdx
  NTSTATUS result; // eax
  unsigned __int64 v6; // rdi
  int v7; // eax
  bool v8; // zf
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !v4 )
    return -1073741811;
  if ( v4 <= 0x7FFFFFFF )
  {
    v6 = v4 - 1;
    v7 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v7 < 0 || (v8 = v7 == v6, v7 > v6) )
    {
      pszDest[v6] = 0;
      return -2147483643;
    }
    else
    {
      result = 0;
      if ( v8 )
        pszDest[v6] = 0;
    }
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
0x140001030  mov     [rsp+arg_10], r8
0x140001035  mov     qword ptr [rsp+Args], r9
0x14000103a  push    rbx
0x14000103b  push    rsi
0x14000103c  push    rdi
0x14000103d  sub     rsp, 30h
0x140001041  xor     ebx, ebx
0x140001043  mov     rsi, rcx
0x140001046  shr     rdx, 1
0x140001049  jz      short loc_140001094
0x14000104b  cmp     rdx, 7FFFFFFFh
0x140001052  jbe     short loc_14000105B
0x140001054  mov     eax, 0C000000Dh
0x140001059  jmp     short loc_14000109E
0x14000105b  lea     rdi, [rdx-1]
0x14000105f  mov     rdx, rdi; Count
0x140001062  lea     r9, [rsp+48h+Args]; Args
0x140001067  call    cs:__imp__vsnwprintf
0x14000106e  nop     dword ptr [rax+rax+00h]
0x140001073  test    eax, eax
0x140001075  js      short loc_140001089
0x140001077  movsxd  rcx, eax
0x14000107a  cmp     rcx, rdi
0x14000107d  ja      short loc_140001089
0x14000107f  mov     eax, ebx
0x140001081  jnz     short loc_1400010A1
0x140001083  mov     [rsi+rdi*2], bx
0x140001087  jmp     short loc_1400010A1
0x140001089  mov     [rsi+rdi*2], bx
0x14000108d  mov     eax, 80000005h
0x140001092  jmp     short loc_1400010A1
0x140001094  mov     eax, 0C000000Dh
0x140001099  test    rdx, rdx
0x14000109c  jz      short loc_1400010A1
0x14000109e  mov     [rcx], bx
0x1400010a1  add     rsp, 30h
0x1400010a5  pop     rdi
0x1400010a6  pop     rsi
0x1400010a7  pop     rbx
0x1400010a8  retn
```
