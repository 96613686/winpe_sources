# RtlStringCbPrintfW

- ea: `0x1400012b0`
- end: `0x14000132e`
- name: `RtlStringCbPrintfW`
- size: `126`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140010890`
- `0x140011d50`

## callees

- `0x1400012b0`
- `0x140001440`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v3; // rdx
  unsigned __int64 v5; // rbx
  NTSTATUS v6; // edi
  int v7; // eax
  NTSTATUS result; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v3 = cbDest >> 1;
  if ( !v3 )
    return -1073741811;
  if ( v3 > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v5 = v3 - 1;
    v6 = 0;
    v7 = vsnwprintf(pszDest, v3 - 1, pszFormat, Args);
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
  return result;
}

```

## disassembly

```asm
0x1400012b0  mov     [rsp+arg_10], r8
0x1400012b5  mov     qword ptr [rsp+Args], r9
0x1400012ba  push    rsi
0x1400012bb  push    rdi
0x1400012bc  sub     rsp, 38h
0x1400012c0  shr     rdx, 1
0x1400012c3  mov     rsi, rcx
0x1400012c6  jz      short loc_14000131D
0x1400012c8  cmp     rdx, 7FFFFFFFh
0x1400012cf  ja      short loc_140001305
0x1400012d1  mov     [rsp+48h+var_18], rbx
0x1400012d6  lea     r9, [rsp+48h+Args]; Args
0x1400012db  lea     rbx, [rdx-1]
0x1400012df  xor     edi, edi
0x1400012e1  mov     rdx, rbx; Count
0x1400012e4  call    _vsnwprintf
0x1400012e9  test    eax, eax
0x1400012eb  js      short loc_140001312
0x1400012ed  cdqe
0x1400012ef  cmp     rax, rbx
0x1400012f2  ja      short loc_140001312
0x1400012f4  jz      short loc_14000130C
0x1400012f6  mov     rbx, [rsp+48h+var_18]
0x1400012fb  mov     eax, edi
0x1400012fd  add     rsp, 38h
0x140001301  pop     rdi
0x140001302  pop     rsi
0x140001303  retn
0x140001305  mov     eax, 0C000000Dh
0x14000130a  jmp     short loc_140001327
0x14000130c  mov     [rsi+rbx*2], di
0x140001310  jmp     short loc_1400012F6
0x140001312  mov     [rsi+rbx*2], di
0x140001316  mov     edi, 80000005h
0x14000131b  jmp     short loc_1400012F6
0x14000131d  mov     eax, 0C000000Dh
0x140001322  test    rdx, rdx
0x140001325  jz      short loc_1400012FD
0x140001327  xor     edi, edi
0x140001329  mov     [rcx], di
0x14000132c  jmp     short loc_1400012FD
```
