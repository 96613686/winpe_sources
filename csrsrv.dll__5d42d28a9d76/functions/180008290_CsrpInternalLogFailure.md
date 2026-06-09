# CsrpInternalLogFailure

- ea: `0x180008290`
- end: `0x18000839f`
- name: `CsrpInternalLogFailure`
- size: `271`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001140`
- `0x1800035c0`
- `0x180008ca4`

## callees

- `0x180008290`
- `0x180008d94`

## pseudocode

```c
__int64 __fastcall CsrpInternalLogFailure(STRSAFE_LPCSTR pszSrc, size_t a2, int a3, __int64 a4)
{
  __int64 v4; // r10
  HRESULT v5; // eax
  __int64 result; // rax

  *(_DWORD *)(a4 + 192) = a3;
  v4 = a4;
  *(_DWORD *)(a4 + 200) = a2;
  if ( pszSrc )
  {
    v5 = StringCbCopyA((STRSAFE_LPSTR)a4, a2, pszSrc);
    if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147024774 )
      *(_BYTE *)v4 = 0;
  }
  result = 204LL * (_InterlockedIncrement(&dword_18000F024) % 16);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 8] = *(_OWORD *)v4;
  *(_OWORD *)&CsrpBlackboxBuffer[result + 24] = *(_OWORD *)(v4 + 16);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 40] = *(_OWORD *)(v4 + 32);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 56] = *(_OWORD *)(v4 + 48);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 72] = *(_OWORD *)(v4 + 64);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 88] = *(_OWORD *)(v4 + 80);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 104] = *(_OWORD *)(v4 + 96);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 120] = *(_OWORD *)(v4 + 112);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 136] = *(_OWORD *)(v4 + 128);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 152] = *(_OWORD *)(v4 + 144);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 168] = *(_OWORD *)(v4 + 160);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 184] = *(_OWORD *)(v4 + 176);
  *(_OWORD *)&CsrpBlackboxBuffer[result + 196] = *(_OWORD *)(v4 + 188);
  return result;
}

```

## disassembly

```asm
0x180008290  sub     rsp, 28h
0x180008294  mov     [r9+0C0h], r8d
0x18000829b  mov     r10, r9
0x18000829e  mov     [r9+0C8h], edx
0x1800082a5  test    rcx, rcx
0x1800082a8  jz      short loc_1800082CC
0x1800082aa  mov     r8, rcx; pszSrc
0x1800082ad  mov     rcx, r9; pszDest
0x1800082b0  call    StringCbCopyA
0x1800082b5  mov     edx, 80000000h
0x1800082ba  lea     ecx, [rax+rdx]
0x1800082bd  test    edx, ecx
0x1800082bf  jnz     short loc_1800082CC
0x1800082c1  cmp     eax, 8007007Ah
0x1800082c6  jz      short loc_1800082CC
0x1800082c8  mov     byte ptr [r10], 0
0x1800082cc  mov     eax, 1
0x1800082d1  lock xadd cs:dword_18000F024, eax
0x1800082d9  inc     eax
0x1800082db  and     eax, 8000000Fh
0x1800082e0  jge     short loc_1800082E9
0x1800082e2  dec     eax
0x1800082e4  or      eax, 0FFFFFFF0h
0x1800082e7  inc     eax
0x1800082e9  movups  xmm0, xmmword ptr [r10]
0x1800082ed  movsxd  rcx, eax
0x1800082f0  imul    rax, rcx, 0CCh
0x1800082f7  lea     rcx, CsrpBlackboxBuffer
0x1800082fe  movups  xmmword ptr [rax+rcx+8], xmm0
0x180008303  movups  xmm1, xmmword ptr [r10+10h]
0x180008308  movups  xmmword ptr [rax+rcx+18h], xmm1
0x18000830d  movups  xmm0, xmmword ptr [r10+20h]
0x180008312  movups  xmmword ptr [rax+rcx+28h], xmm0
0x180008317  movups  xmm1, xmmword ptr [r10+30h]
0x18000831c  movups  xmmword ptr [rax+rcx+38h], xmm1
0x180008321  movups  xmm0, xmmword ptr [r10+40h]
0x180008326  movups  xmmword ptr [rax+rcx+48h], xmm0
0x18000832b  movups  xmm1, xmmword ptr [r10+50h]
0x180008330  movups  xmmword ptr [rax+rcx+58h], xmm1
0x180008335  movups  xmm0, xmmword ptr [r10+60h]
0x18000833a  movups  xmmword ptr [rax+rcx+68h], xmm0
0x18000833f  movups  xmm1, xmmword ptr [r10+70h]
0x180008344  movups  xmmword ptr [rax+rcx+78h], xmm1
0x180008349  movups  xmm0, xmmword ptr [r10+80h]
0x180008351  movups  xmmword ptr [rax+rcx+88h], xmm0
0x180008359  movups  xmm1, xmmword ptr [r10+90h]
0x180008361  movups  xmmword ptr [rax+rcx+98h], xmm1
0x180008369  movups  xmm0, xmmword ptr [r10+0A0h]
0x180008371  movups  xmmword ptr [rax+rcx+0A8h], xmm0
0x180008379  movups  xmm1, xmmword ptr [r10+0B0h]
0x180008381  movups  xmmword ptr [rax+rcx+0B8h], xmm1
0x180008389  movups  xmm0, xmmword ptr [r10+0BCh]
0x180008391  movups  xmmword ptr [rax+rcx+0C4h], xmm0
0x180008399  add     rsp, 28h
0x18000839d  retn
```
