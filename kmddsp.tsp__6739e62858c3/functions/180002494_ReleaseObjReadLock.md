# ReleaseObjReadLock

- ea: `0x180002494`
- end: `0x180002502`
- name: `ReleaseObjReadLock`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `32`
- callee_count: `3`
- tags: ``

## callers

- `0x180003294`
- `0x18000338c`
- `0x180003720`
- `0x1800037a8`
- `0x180003890`
- `0x180003ba8`
- `0x180004310`
- `0x180004400`
- `0x180004670`
- `0x180004880`
- `0x1800049a0`
- `0x180004bc0`
- `0x180004d30`
- `0x180004ec0`
- `0x1800051d0`
- `0x180005320`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005db0`
- `0x180006140`
- `0x1800062b0`
- `0x1800063b0`
- `0x1800066e0`
- `0x180006d40`
- `0x180006e30`
- `0x180006fb0`
- `0x1800070c0`
- `0x1800071b0`
- `0x1800072e0`
- `0x1800074c0`
- `0x1800075b0`

## callees

- `0x180002494`
- `0x18000257c`
- `0x180007df8`

## string_xrefs

- `0x1800024e6`: `ReleaseObjReadLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall ReleaseObjReadLock(const void *a1, __int64 a2)
{
  __int64 v3; // r8
  char *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9

  if ( (unsigned __int16)((unsigned int)a1 >> 1) < (unsigned int)dword_18000E2FC
    && (v3 = (unsigned int)a1 >> 17,
        v4 = (char *)hMem + 80 * (unsigned __int16)((unsigned int)a1 >> 1),
        (_WORD)v3 == *((_WORD *)v4 + 36))
    && *((_QWORD *)v4 + 7) )
  {
    ReleaseReadLock(v4, a2, v3, a1);
    ReleaseReadLock(&CriticalSection, v5, v6, v7);
    return 0;
  }
  else
  {
    TspLog(2, "ReleaseObjReadLock: bad handle(%p)", a1);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180002494  sub     rsp, 28h
0x180002498  mov     r8d, ecx
0x18000249b  mov     r9, rcx
0x18000249e  shr     r8d, 1
0x1800024a1  movzx   eax, r8w
0x1800024a5  cmp     eax, cs:dword_18000E2FC
0x1800024ab  jnb     short loc_1800024E3
0x1800024ad  lea     rcx, [rax+rax*4]
0x1800024b1  shr     r8d, 10h
0x1800024b5  shl     rcx, 4
0x1800024b9  add     rcx, cs:hMem
0x1800024c0  cmp     r8w, [rcx+48h]
0x1800024c5  jnz     short loc_1800024E3
0x1800024c7  cmp     qword ptr [rcx+38h], 0
0x1800024cc  jz      short loc_1800024E3
0x1800024ce  call    ReleaseReadLock
0x1800024d3  lea     rcx, CriticalSection
0x1800024da  call    ReleaseReadLock
0x1800024df  xor     eax, eax
0x1800024e1  jmp     short loc_1800024FC
0x1800024e3  mov     r8, r9
0x1800024e6  lea     rdx, aReleaseobjread; "ReleaseObjReadLock: bad handle(%p)"
0x1800024ed  mov     ecx, 2
0x1800024f2  call    TspLog
0x1800024f7  mov     eax, 80000048h
0x1800024fc  add     rsp, 28h
0x180002500  retn
```
