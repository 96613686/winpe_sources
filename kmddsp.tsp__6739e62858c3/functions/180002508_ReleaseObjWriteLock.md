# ReleaseObjWriteLock

- ea: `0x180002508`
- end: `0x180002576`
- name: `ReleaseObjWriteLock`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180003310`
- `0x18000381c`
- `0x180003ba8`
- `0x180004520`
- `0x180004670`
- `0x180004d30`
- `0x180004ec0`
- `0x1800066e0`

## callees

- `0x180002508`
- `0x18000257c`
- `0x1800025c4`
- `0x180007df8`

## string_xrefs

- `0x18000255a`: `ReleaseObjWriteLock: bad handle(%p)`

## pseudocode

```c
__int64 __fastcall ReleaseObjWriteLock(const void *a1)
{
  unsigned int v2; // r8d
  char *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9

  v2 = (unsigned int)a1 >> 1;
  if ( (unsigned __int16)((unsigned int)a1 >> 1) < (unsigned int)dword_18000E2FC
    && (v3 = (char *)hMem + 80 * (unsigned __int16)((unsigned int)a1 >> 1), HIWORD(v2) == *((_WORD *)v3 + 36))
    && *((_QWORD *)v3 + 7) )
  {
    ReleaseWriteLock(v3);
    ReleaseReadLock(&CriticalSection, v4, v5, v6);
    return 0;
  }
  else
  {
    TspLog(2, "ReleaseObjWriteLock: bad handle(%p)", a1);
    return 2147483720LL;
  }
}

```

## disassembly

```asm
0x180002508  sub     rsp, 28h
0x18000250c  mov     r8d, ecx
0x18000250f  mov     r9, rcx
0x180002512  shr     r8d, 1
0x180002515  movzx   eax, r8w
0x180002519  cmp     eax, cs:dword_18000E2FC
0x18000251f  jnb     short loc_180002557
0x180002521  lea     rcx, [rax+rax*4]
0x180002525  shr     r8d, 10h
0x180002529  shl     rcx, 4
0x18000252d  add     rcx, cs:hMem
0x180002534  cmp     r8w, [rcx+48h]
0x180002539  jnz     short loc_180002557
0x18000253b  cmp     qword ptr [rcx+38h], 0
0x180002540  jz      short loc_180002557
0x180002542  call    ReleaseWriteLock
0x180002547  lea     rcx, CriticalSection
0x18000254e  call    ReleaseReadLock
0x180002553  xor     eax, eax
0x180002555  jmp     short loc_180002570
0x180002557  mov     r8, r9
0x18000255a  lea     rdx, aReleaseobjwrit; "ReleaseObjWriteLock: bad handle(%p)"
0x180002561  mov     ecx, 2
0x180002566  call    TspLog
0x18000256b  mov     eax, 80000048h
0x180002570  add     rsp, 28h
0x180002574  retn
```
