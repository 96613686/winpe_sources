# StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x180006fdc`
- end: `0x18000700b`
- name: `?StringCchCopyW@@YAJPEA_W_KPEB_W@Z`
- size: `47`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x180004010`
- `0x1800074d4`
- `0x18000fcf0`
- `0x180011c14`
- `0x1800120b0`
- `0x1800138d4`
- `0x180015e08`
- `0x1800163ec`
- `0x180016944`
- `0x180017edc`
- `0x180019450`
- `0x180023434`

## callees

- `0x180006fdc`
- `0x1800070b0`
- `0x18000715c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(wchar_t *a1, size_t a2, const wchar_t *a3)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  HRESULT v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(a1, a2, (const size_t)a3);
  if ( v6 < 0 )
  {
    if ( v3 )
      *v4 = 0;
  }
  else
  {
    return (unsigned int)StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006fdc  sub     rsp, 38h
0x180006fe0  call    StringValidateDestW
0x180006fe5  mov     r9d, eax
0x180006fe8  test    eax, eax
0x180006fea  js      short loc_180006FF9
0x180006fec  mov     r9, r8; pszSrc
0x180006fef  call    StringCopyWorkerW
0x180006ff4  mov     r9d, eax
0x180006ff7  jmp     short loc_180007003
0x180006ff9  test    rdx, rdx
0x180006ffc  jz      short loc_180007003
0x180006ffe  xor     eax, eax
0x180007000  mov     [rcx], ax
0x180007003  mov     eax, r9d
0x180007006  add     rsp, 38h
0x18000700a  retn
```
