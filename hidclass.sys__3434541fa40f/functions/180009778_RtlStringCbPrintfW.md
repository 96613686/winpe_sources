# RtlStringCbPrintfW

- ea: `0x180009778`
- end: `0x1800097f2`
- name: `RtlStringCbPrintfW`
- size: `122`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a430`
- `0x180019d28`
- `0x18003a1c0`
- `0x18003a590`
- `0x18003da1c`
- `0x18003e210`
- `0x18003fbbc`

## callees

- `0x180009778`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x1800097a8`
- `ntoskrnl!_vsnwprintf` at `0x1800097a8`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  size_t v4; // rdx
  unsigned __int64 v5; // rdi
  int v6; // eax
  bool v7; // zf
  NTSTATUS result; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  v4 = cbDest >> 1;
  if ( !v4 )
    return -1073741811;
  if ( v4 > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v5 = v4 - 1;
    v6 = _vsnwprintf(pszDest, v4 - 1, pszFormat, Args);
    if ( v6 < 0 || (v7 = v6 == v5, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147483643;
    }
    else
    {
      result = 0;
      if ( v7 )
        pszDest[v5] = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009778  mov     [rsp+arg_10], r8
0x18000977d  mov     qword ptr [rsp+Args], r9
0x180009782  push    rbx
0x180009783  push    rsi
0x180009784  push    rdi
0x180009785  sub     rsp, 30h
0x180009789  xor     ebx, ebx
0x18000978b  mov     rsi, rcx
0x18000978e  shr     rdx, 1
0x180009791  jz      short loc_1800097E3
0x180009793  cmp     rdx, 7FFFFFFFh
0x18000979a  ja      short loc_1800097DC
0x18000979c  lea     rdi, [rdx-1]
0x1800097a0  mov     rdx, rdi; Count
0x1800097a3  lea     r9, [rsp+48h+Args]; Args
0x1800097a8  call    cs:__imp__vsnwprintf
0x1800097af  nop     dword ptr [rax+rax+00h]
0x1800097b4  test    eax, eax
0x1800097b6  js      short loc_1800097D1
0x1800097b8  movsxd  rcx, eax
0x1800097bb  cmp     rcx, rdi
0x1800097be  ja      short loc_1800097D1
0x1800097c0  mov     eax, ebx
0x1800097c2  jnz     short loc_1800097C8
0x1800097c4  mov     [rsi+rdi*2], bx
0x1800097c8  add     rsp, 30h
0x1800097cc  pop     rdi
0x1800097cd  pop     rsi
0x1800097ce  pop     rbx
0x1800097cf  retn
0x1800097d1  mov     [rsi+rdi*2], bx
0x1800097d5  mov     eax, 80000005h
0x1800097da  jmp     short loc_1800097C8
0x1800097dc  mov     eax, 0C000000Dh
0x1800097e1  jmp     short loc_1800097ED
0x1800097e3  mov     eax, 0C000000Dh
0x1800097e8  test    rdx, rdx
0x1800097eb  jz      short loc_1800097C8
0x1800097ed  mov     [rcx], bx
0x1800097f0  jmp     short loc_1800097C8
```
