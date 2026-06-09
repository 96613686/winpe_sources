# EngCreateFile

- ea: `0x1400927b8`
- end: `0x140092860`
- name: `EngCreateFile`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140092bf4`

## callees

- `0x140075de0`

## import_xrefs

- `win32u!NtGdiExtEscape` at `0x140092841`
- `win32u!NtGdiExtEscape` at `0x140092841`

## pseudocode

```c
const wchar_t *__fastcall EngCreateFile(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // [rsp+40h] [rbp+7h] BYREF
  const wchar_t *v5; // [rsp+48h] [rbp+Fh]
  __int64 v6; // [rsp+50h] [rbp+17h]
  int v7; // [rsp+58h] [rbp+1Fh]
  __int128 v8; // [rsp+5Ch] [rbp+23h]
  int v9; // [rsp+6Ch] [rbp+33h]
  __int128 v10; // [rsp+70h] [rbp+37h] BYREF
  wchar_t v11; // [rsp+80h] [rbp+47h]

  v7 = a3;
  v6 = a2;
  v5 = L"FAC.ATM";
  v11 = aUmfdhost[8];
  v4 = 15;
  v8 = 0;
  v9 = 0;
  v10 = *(_OWORD *)L"UmfdHost";
  ((void (__fastcall *)(_QWORD, __int128 *, __int64, __int64, int, __int64 *, int, __int64 *))NtGdiExtEscape)(
    0,
    &v10,
    9,
    19,
    48,
    &v4,
    48,
    &v4);
  return v5;
}

```

## disassembly

```asm
0x1400927b8  push    rbp
0x1400927ba  lea     rbp, [rsp-57h]
0x1400927bf  sub     rsp, 90h
0x1400927c6  mov     rax, cs:__security_cookie
0x1400927cd  xor     rax, rsp
0x1400927d0  mov     [rbp+57h+var_8], rax
0x1400927d4  mov     ecx, 30h ; '0'
0x1400927d9  mov     [rbp+57h+var_38], r8d
0x1400927dd  lea     rax, aFacAtm; "FAC.ATM"
0x1400927e4  mov     [rbp+57h+var_40], rdx
0x1400927e8  mov     [rbp+57h+var_48], rax
0x1400927ec  lea     rdx, [rbp+57h+var_20]
0x1400927f0  movzx   eax, word ptr cs:aUmfdhost+10h; ""
0x1400927f7  xorps   xmm0, xmm0
0x1400927fa  mov     [rbp+57h+var_10], ax
0x1400927fe  lea     r9d, [rcx-1Dh]
0x140092802  lea     rax, [rbp+57h+var_50]
0x140092806  mov     [rbp+57h+var_50], 0Fh
0x14009280e  mov     [rsp+90h+var_58], rax
0x140092813  lea     r8d, [rcx-27h]
0x140092817  mov     [rsp+90h+var_60], ecx
0x14009281b  lea     rax, [rbp+57h+var_50]
0x14009281f  movdqu  [rbp+57h+var_34], xmm0
0x140092824  mov     [rsp+90h+var_68], rax
0x140092829  movups  xmm0, xmmword ptr cs:aUmfdhost; "UmfdHost"
0x140092830  mov     [rsp+90h+var_70], ecx
0x140092834  xor     ecx, ecx
0x140092836  mov     [rbp+57h+var_24], 0
0x14009283d  movups  [rbp+57h+var_20], xmm0
0x140092841  call    cs:__imp_NtGdiExtEscape
0x140092847  mov     rax, [rbp+57h+var_48]
0x14009284b  mov     rcx, [rbp+57h+var_8]
0x14009284f  xor     rcx, rsp; StackCookie
0x140092852  call    __security_check_cookie
0x140092857  add     rsp, 90h
0x14009285e  pop     rbp
0x14009285f  retn
```
