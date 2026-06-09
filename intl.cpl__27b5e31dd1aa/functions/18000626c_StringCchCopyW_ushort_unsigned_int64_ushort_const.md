# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000626c`
- end: `0x1800062a9`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047f4`
- `0x1800064e4`
- `0x180007520`
- `0x1800077dc`
- `0x18000849c`
- `0x18000a0f4`
- `0x18000b8c8`
- `0x18000c454`
- `0x18000fe2c`
- `0x180011040`
- `0x1800119d8`
- `0x180011d6c`
- `0x180017e60`
- `0x180017e90`
- `0x180017f00`
- `0x180018630`
- `0x180018830`
- `0x180018bbc`
- `0x18001acb4`
- `0x18001b3f0`
- `0x18001f95c`
- `0x180021828`
- `0x1800235c8`
- `0x180023bd0`
- `0x18002554c`
- `0x1800258c8`
- `0x180027260`
- `0x180027958`
- `0x180027c28`

## callees

- `0x18000626c`
- `0x18000635c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
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
0x18000626c  sub     rsp, 38h
0x180006270  mov     rax, rdx
0x180006273  test    rdx, rdx
0x180006276  jz      short loc_180006293
0x180006278  cmp     rax, 7FFFFFFFh
0x18000627e  jbe     short loc_180006287
0x180006280  mov     edx, 80070057h; cchDest
0x180006285  jmp     short loc_18000629D
0x180006287  mov     r9, r8; pszSrc
0x18000628a  call    StringCopyWorkerW
0x18000628f  mov     edx, eax
0x180006291  jmp     short loc_1800062A2
0x180006293  mov     edx, 80070057h
0x180006298  test    rax, rax
0x18000629b  jz      short loc_1800062A2
0x18000629d  xor     eax, eax
0x18000629f  mov     [rcx], ax
0x1800062a2  mov     eax, edx
0x1800062a4  add     rsp, 38h
0x1800062a8  retn
```
