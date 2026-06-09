# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x1800112e0`
- end: `0x18001131d`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `61`
- prototype: `int(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800169a0`
- `0x180019eec`
- `0x18001db50`
- `0x18001e750`
- `0x18001fafc`
- `0x18001fd54`
- `0x1800200a4`
- `0x180020854`

## callees

- `0x1800112e0`
- `0x1800113b0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, size_t a2, wchar_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v3 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, (size_t *)a3, a3, v5);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1800112e0  sub     rsp, 38h
0x1800112e4  mov     rax, rdx
0x1800112e7  test    rdx, rdx
0x1800112ea  jz      short loc_18001130C
0x1800112ec  cmp     rax, 7FFFFFFFh
0x1800112f2  ja      short loc_180011305
0x1800112f4  mov     r9, r8; pszSrc
0x1800112f7  call    StringCopyWorkerW
0x1800112fc  mov     edx, eax
0x1800112fe  mov     eax, edx
0x180011300  add     rsp, 38h
0x180011304  retn
0x180011305  mov     edx, 80070057h
0x18001130a  jmp     short loc_180011316
0x18001130c  mov     edx, 80070057h
0x180011311  test    rax, rax
0x180011314  jz      short loc_1800112FE
0x180011316  xor     eax, eax
0x180011318  mov     [rcx], ax
0x18001131b  jmp     short loc_1800112FE
```
