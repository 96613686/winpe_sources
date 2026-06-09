# CopySurface(tagRECT const &,ParameterBase const *)

- ea: `0x180021790`
- end: `0x18002183d`
- name: `?CopySurface@@YAJAEBUtagRECT@@PEBUParameterBase@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(const struct tagRECT *, const struct ParameterBase *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180021790`

## import_xrefs

- `MFPlat!MFCopyImage` at `0x1800217d0`
- `MFPlat!MFCopyImage` at `0x180021835`
- `MFPlat!MFCopyImage` at `0x1800217d0`
- `MFPlat!MFCopyImage` at `0x180021835`

## pseudocode

```c
__int64 __fastcall CopySurface(const struct tagRECT *a1, const struct ParameterBase *a2)
{
  const BYTE *v2; // r12
  __int64 v3; // r13
  LONG v4; // r14d
  signed int dwWidthInBytes; // r15d
  signed int dwLines; // edi
  LONG v7; // ebp
  int v8; // ebx
  int v9; // esi

  v2 = (const BYTE *)*((_QWORD *)a2 + 2);
  v3 = *(_QWORD *)a2;
  v4 = *((_DWORD *)a2 + 6);
  dwWidthInBytes = *((_DWORD *)a2 + 20);
  dwLines = *((_DWORD *)a2 + 7);
  v7 = *((_DWORD *)a2 + 2);
  v8 = *((_DWORD *)a2 + 21);
  v9 = *((_DWORD *)a2 + 22);
  if ( !MFCopyImage(*(BYTE **)a2, v7, v2, v4, dwWidthInBytes, dwLines) && v8 > 0 && v9 > 0 )
    MFCopyImage((BYTE *)(v3 + v7 * dwLines), v7 / v8, &v2[v4 * dwLines], v4 / v8, dwWidthInBytes / v8, dwLines / v9);
  return 0;
}

```

## disassembly

```asm
0x180021790  push    rbx
0x180021792  push    rbp
0x180021793  push    rsi
0x180021794  push    rdi
0x180021795  push    r12
0x180021797  push    r13
0x180021799  push    r14
0x18002179b  push    r15
0x18002179d  sub     rsp, 38h
0x1800217a1  mov     r12, [rdx+10h]
0x1800217a5  mov     r13, [rdx]
0x1800217a8  mov     r8, r12; pSrc
0x1800217ab  mov     r14d, [rdx+18h]
0x1800217af  mov     rcx, r13; pDest
0x1800217b2  mov     r15d, [rdx+50h]
0x1800217b6  mov     r9d, r14d; lSrcStride
0x1800217b9  mov     edi, [rdx+1Ch]
0x1800217bc  mov     ebp, [rdx+8]
0x1800217bf  mov     ebx, [rdx+54h]
0x1800217c2  mov     esi, [rdx+58h]
0x1800217c5  mov     edx, ebp; lDestStride
0x1800217c7  mov     [rsp+78h+dwLines], edi; dwLines
0x1800217cb  mov     [rsp+78h+dwWidthInBytes], r15d; dwWidthInBytes
0x1800217d0  call    cs:__imp_MFCopyImage
0x1800217d6  test    eax, eax
0x1800217d8  jnz     short loc_1800217DE
0x1800217da  test    ebx, ebx
0x1800217dc  jg      short loc_1800217F1
0x1800217de  xor     eax, eax
0x1800217e0  add     rsp, 38h
0x1800217e4  pop     r15
0x1800217e6  pop     r14
0x1800217e8  pop     r13
0x1800217ea  pop     r12
0x1800217ec  pop     rdi
0x1800217ed  pop     rsi
0x1800217ee  pop     rbp
0x1800217ef  pop     rbx
0x1800217f0  retn
0x1800217f1  test    esi, esi
0x1800217f3  jle     short loc_1800217DE
0x1800217f5  mov     eax, edi
0x1800217f7  mov     ecx, edi
0x1800217f9  cdq
0x1800217fa  imul    ecx, r14d
0x1800217fe  idiv    esi
0x180021800  movsxd  r8, ecx
0x180021803  mov     r11d, eax
0x180021806  imul    edi, ebp
0x180021809  mov     eax, r15d
0x18002180c  mov     [rsp+78h+dwLines], r11d; dwLines
0x180021811  cdq
0x180021812  add     r8, r12; pSrc
0x180021815  idiv    ebx
0x180021817  movsxd  rcx, edi
0x18002181a  mov     r10d, eax
0x18002181d  add     rcx, r13; pDest
0x180021820  mov     eax, r14d
0x180021823  mov     [rsp+78h+dwWidthInBytes], r10d; dwWidthInBytes
0x180021828  cdq
0x180021829  idiv    ebx
0x18002182b  mov     r9d, eax; lSrcStride
0x18002182e  mov     eax, ebp
0x180021830  cdq
0x180021831  idiv    ebx
0x180021833  mov     edx, eax; lDestStride
0x180021835  call    cs:__imp_MFCopyImage
0x18002183b  jmp     short loc_1800217DE
```
