# RtlStringCbPrintfW

- ea: `0x14000572c`
- end: `0x1400057a6`
- name: `RtlStringCbPrintfW`
- size: `122`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400111d0`
- `0x1400159c0`

## callees

- `0x14000572c`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x140005763`
- `ntoskrnl!_vsnwprintf` at `0x140005763`

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
0x14000572c  mov     [rsp+arg_10], r8
0x140005731  mov     qword ptr [rsp+Args], r9
0x140005736  push    rbx
0x140005737  push    rsi
0x140005738  push    rdi
0x140005739  sub     rsp, 30h
0x14000573d  xor     ebx, ebx
0x14000573f  mov     rsi, rcx
0x140005742  shr     rdx, 1
0x140005745  jz      short loc_140005790
0x140005747  cmp     rdx, 7FFFFFFFh
0x14000574e  jbe     short loc_140005757
0x140005750  mov     eax, 0C000000Dh
0x140005755  jmp     short loc_14000579A
0x140005757  lea     rdi, [rdx-1]
0x14000575b  mov     rdx, rdi; Count
0x14000575e  lea     r9, [rsp+48h+Args]; Args
0x140005763  call    cs:__imp__vsnwprintf
0x14000576a  nop     dword ptr [rax+rax+00h]
0x14000576f  test    eax, eax
0x140005771  js      short loc_140005785
0x140005773  movsxd  rcx, eax
0x140005776  cmp     rcx, rdi
0x140005779  ja      short loc_140005785
0x14000577b  mov     eax, ebx
0x14000577d  jnz     short loc_14000579D
0x14000577f  mov     [rsi+rdi*2], bx
0x140005783  jmp     short loc_14000579D
0x140005785  mov     [rsi+rdi*2], bx
0x140005789  mov     eax, 80000005h
0x14000578e  jmp     short loc_14000579D
0x140005790  mov     eax, 0C000000Dh
0x140005795  test    rdx, rdx
0x140005798  jz      short loc_14000579D
0x14000579a  mov     [rcx], bx
0x14000579d  add     rsp, 30h
0x1400057a1  pop     rdi
0x1400057a2  pop     rsi
0x1400057a3  pop     rbx
0x1400057a4  retn
```
