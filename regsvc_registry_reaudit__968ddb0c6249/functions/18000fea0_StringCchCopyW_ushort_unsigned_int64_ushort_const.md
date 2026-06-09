# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000fea0`
- end: `0x18000fecf`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `47`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001520`
- `0x180002810`
- `0x18000e1a8`
- `0x1800113b0`
- `0x1800158e8`
- `0x1800166cc`

## callees

- `0x180007104`
- `0x180007120`
- `0x18000fea0`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3)
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
0x18000fea0  sub     rsp, 38h
0x18000fea4  call    StringValidateDestW
0x18000fea9  mov     r9d, eax
0x18000feac  test    eax, eax
0x18000feae  js      short loc_18000FEBD
0x18000feb0  mov     r9, r8; pszSrc
0x18000feb3  call    StringCopyWorkerW
0x18000feb8  mov     r9d, eax
0x18000febb  jmp     short loc_18000FEC7
0x18000febd  test    rdx, rdx
0x18000fec0  jz      short loc_18000FEC7
0x18000fec2  xor     eax, eax
0x18000fec4  mov     [rcx], ax
0x18000fec7  mov     eax, r9d
0x18000feca  add     rsp, 38h
0x18000fece  retn
```
