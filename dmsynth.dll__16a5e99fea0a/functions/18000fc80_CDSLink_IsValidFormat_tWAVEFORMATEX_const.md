# CDSLink::IsValidFormat(tWAVEFORMATEX const *)

- ea: `0x18000fc80`
- end: `0x18000fcde`
- name: `?IsValidFormat@CDSLink@@AEAAHPEBUtWAVEFORMATEX@@@Z`
- size: `94`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, const struct tWAVEFORMATEX *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f010`
- `0x18000fb80`
- `0x1800101c0`

## callees

- `0x18000fc80`

## pseudocode

```c
_BOOL8 __fastcall CDSLink::IsValidFormat(CDSLink *this, const struct tWAVEFORMATEX *a2)
{
  int nChannels; // r9d
  DWORD nSamplesPerSec; // ecx
  _BOOL8 result; // rax

  result = a2
        && a2->wFormatTag == 1
        && (nChannels = a2->nChannels, (unsigned __int16)(nChannels - 1) <= 1u)
        && ((nSamplesPerSec = a2->nSamplesPerSec, nSamplesPerSec == 44100)
         || nSamplesPerSec == 22050
         || nSamplesPerSec == 11025)
        && a2->wBitsPerSample == 16
        && __PAIR64__(a2->nBlockAlign, a2->nAvgBytesPerSec) == __PAIR64__(
                                                                 2 * nChannels,
                                                                 nSamplesPerSec * a2->nBlockAlign);
  return result;
}

```

## disassembly

```asm
0x18000fc80  test    rdx, rdx
0x18000fc83  jz      short loc_18000FCDB
0x18000fc85  cmp     word ptr [rdx], 1
0x18000fc89  jnz     short loc_18000FCDB
0x18000fc8b  movzx   r9d, word ptr [rdx+2]
0x18000fc90  lea     eax, [r9-1]
0x18000fc94  cmp     ax, 1
0x18000fc98  ja      short loc_18000FCDB
0x18000fc9a  mov     ecx, [rdx+4]
0x18000fc9d  cmp     ecx, 0AC44h
0x18000fca3  jz      short loc_18000FCB5
0x18000fca5  cmp     ecx, 5622h
0x18000fcab  jz      short loc_18000FCB5
0x18000fcad  cmp     ecx, 2B11h
0x18000fcb3  jnz     short loc_18000FCDB
0x18000fcb5  cmp     word ptr [rdx+0Eh], 10h
0x18000fcba  jnz     short loc_18000FCDB
0x18000fcbc  movzx   r8d, word ptr [rdx+0Ch]
0x18000fcc1  mov     eax, r9d
0x18000fcc4  add     eax, eax
0x18000fcc6  cmp     r8d, eax
0x18000fcc9  jnz     short loc_18000FCDB
0x18000fccb  imul    r8d, ecx
0x18000fccf  cmp     [rdx+8], r8d
0x18000fcd3  jnz     short loc_18000FCDB
0x18000fcd5  mov     eax, 1
0x18000fcda  retn
0x18000fcdb  xor     eax, eax
0x18000fcdd  retn
```
