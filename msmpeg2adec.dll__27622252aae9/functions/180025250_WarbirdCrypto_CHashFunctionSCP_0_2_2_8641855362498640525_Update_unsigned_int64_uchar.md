# WarbirdCrypto::CHashFunctionSCP<0,2,2,8641855362498640525>::Update(unsigned __int64 *,uchar)

- ea: `0x180025250`
- end: `0x1800252d6`
- name: `?Update@?$CHashFunctionSCP@$0A@$01$01$0HHOOAJKKGKAJDKIN@@WarbirdCrypto@@UEAAXPEA_KE@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall WarbirdCrypto::CHashFunctionSCP<0,2,2,8641855362498640525>::Update(
        __int64 a1,
        _DWORD *a2,
        unsigned __int8 a3)
{
  int v3; // r9d
  unsigned int v4; // eax
  int v5; // eax
  int v6; // eax
  __int64 result; // rax

  v3 = a3 + 1778989709;
  v4 = __ROR4__(1778989709 * (v3 + a2[1]), 10);
  v5 = 1778989709 * v4
     + 2 * ((1778989709 * (unsigned __int64)v4) >> 32)
     - (((int)(1778989709 * v4) >> 31) & 0x7FFFFFFF)
     - 0x7FFFFFFF;
  v6 = 1778989709 * (((v5 >> 31) & 0x7FFFFFFF) + v5)
     + 2 * ((1778989709 * (unsigned __int64)(((v5 >> 31) & 0x7FFFFFFFu) + v5)) >> 32)
     - (((1778989709 * (((v5 >> 31) & 0x7FFFFFFF) + v5)) >> 31) & 0x7FFFFFFF)
     - 0x7FFFFFFF
     + (((int)(1778989709 * (((v5 >> 31) & 0x7FFFFFFF) + v5)
             + 2 * ((1778989709 * (unsigned __int64)(((v5 >> 31) & 0x7FFFFFFFu) + v5)) >> 32)
             - (((1778989709 * (((v5 >> 31) & 0x7FFFFFFF) + v5)) >> 31) & 0x7FFFFFFF)
             - 0x7FFFFFFF) >> 31)
      & 0x7FFFFFFF);
  a2[1] = v6;
  result = (unsigned int)(v3 + v6);
  *a2 += result;
  return result;
}

```

## disassembly

```asm
0x180025250  mov     ecx, [rdx+4]
0x180025253  mov     r10, rdx
0x180025256  movzx   r9d, r8b
0x18002525a  add     r9d, 6A093A8Dh
0x180025261  add     ecx, r9d
0x180025264  imul    eax, ecx, 6A093A8Dh
0x18002526a  ror     eax, 0Ah
0x18002526d  imul    r8, rax, 6A093A8Dh
0x180025274  mov     eax, r8d
0x180025277  mov     rcx, r8
0x18002527a  sar     eax, 1Fh
0x18002527d  btr     eax, 1Fh
0x180025281  shr     rcx, 20h
0x180025285  add     ecx, ecx
0x180025287  sub     ecx, eax
0x180025289  lea     eax, [rcx-7FFFFFFFh]
0x18002528f  add     eax, r8d
0x180025292  mov     ecx, eax
0x180025294  sar     ecx, 1Fh
0x180025297  btr     ecx, 1Fh
0x18002529b  add     eax, ecx
0x18002529d  imul    rdx, rax, 6A093A8Dh
0x1800252a4  mov     ecx, edx
0x1800252a6  mov     rax, rdx
0x1800252a9  shr     rax, 20h
0x1800252ad  add     eax, eax
0x1800252af  sar     ecx, 1Fh
0x1800252b2  btr     ecx, 1Fh
0x1800252b6  sub     eax, ecx
0x1800252b8  lea     ecx, [rax-7FFFFFFFh]
0x1800252be  add     ecx, edx
0x1800252c0  mov     eax, ecx
0x1800252c2  sar     eax, 1Fh
0x1800252c5  btr     eax, 1Fh
0x1800252c9  add     eax, ecx
0x1800252cb  mov     [r10+4], eax
0x1800252cf  add     eax, r9d
0x1800252d2  add     [r10], eax
0x1800252d5  retn
```
