# GrowToolbar

- ea: `0x180025d1c`
- end: `0x180025edb`
- name: `GrowToolbar`
- size: `447`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800263e8`
- `0x180028800`
- `0x18002aab0`

## callees

- `0x180025d1c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180025e59`
- `GDI32!DeleteObject` at `0x180025e59`
- `GDI32!GetObjectW` at `0x180025e1b`
- `GDI32!GetObjectW` at `0x180025e1b`
- `GDI32!CreateBitmap` at `0x180025e42`
- `GDI32!CreateBitmap` at `0x180025e42`
- `USER32!InvalidateRect` at `0x180025e8c`
- `USER32!InvalidateRect` at `0x180025e8c`

## pseudocode

```c
HBITMAP __fastcall GrowToolbar(__int64 a1, int a2, int a3, char a4)
{
  int v4; // eax
  int v5; // esi
  int v8; // r15d
  int v9; // edi
  int *v10; // r14
  int v11; // edi
  void *v12; // rcx
  HBITMAP result; // rax
  HBITMAP v14; // rbp
  void *v15; // rcx
  char v16; // al
  _OWORD pv[5]; // [rsp+30h] [rbp-58h] BYREF

  v4 = 24;
  v5 = 22;
  if ( a2 )
    v4 = a2;
  if ( a3 )
    v5 = a3;
  v8 = a4 & 1;
  if ( (a4 & 1) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 )
      v9 = v4 + *(_DWORD *)(a1 + 172) + *(_DWORD *)(a1 + 224);
    else
      v9 = v4;
    v5 += *(_DWORD *)(a1 + 220);
    v10 = (int *)(a1 + 180);
    v11 = *(_DWORD *)(a1 + 216) + v9;
    if ( v11 < *(_DWORD *)(a1 + 180) && *(_DWORD *)(a1 + 160) && (*(__int64 *)(a1 + 40) < 5 || *(int *)(a1 + 164) > 0) )
      v11 = *v10;
  }
  else
  {
    if ( v5 == -1 )
      v5 = *(_DWORD *)(a1 + 184);
    if ( v4 == -1 )
      v11 = *(_DWORD *)(a1 + 180);
    else
      v11 = v4;
    v10 = (int *)(a1 + 180);
    if ( v5 < *(_DWORD *)(a1 + 176) + *(_DWORD *)(a1 + 220) )
      v5 = *(_DWORD *)(a1 + 176) + *(_DWORD *)(a1 + 220);
    if ( v11 < *(_DWORD *)(a1 + 172) + *(_DWORD *)(a1 + 216) )
      v11 = *(_DWORD *)(a1 + 172) + *(_DWORD *)(a1 + 216);
  }
  v12 = *(void **)(a1 + 72);
  if ( !v12 || v11 > *v10 || v5 > *(_DWORD *)(a1 + 184) )
  {
    memset(pv, 0, 32);
    if ( !v12 || (GetObjectW(v12, 32, pv), v11 > SDWORD1(pv[0])) || v5 > SDWORD2(pv[0]) )
    {
      result = CreateBitmap(v11 + 8, v5 + 8, 1u, 1u, 0);
      v14 = result;
      if ( !result )
        return result;
      v15 = *(void **)(a1 + 72);
      if ( v15 )
        DeleteObject(v15);
      *(_QWORD *)(a1 + 72) = v14;
    }
  }
  if ( (a4 & 2) == 0 )
  {
    if ( !v8 && (*v10 != v11 || *(_DWORD *)(a1 + 184) != v5) )
      InvalidateRect(*(HWND *)a1, 0, 1);
    v16 = ~(unsigned __int8)(*(_DWORD *)(a1 + 16) >> 10);
    *v10 = v11;
    *(_DWORD *)(a1 + 184) = v5;
    *(_DWORD *)(a1 + 196) = v16 & 2;
    *(_DWORD *)(a1 + 316) &= ~0x10000u;
    *(_DWORD *)(a1 + 316) |= 0x10u;
    *(_DWORD *)(a1 + 232) = -1;
    *(_DWORD *)(a1 + 236) = -1;
  }
  return (HBITMAP)1;
}

```

## disassembly

```asm
0x180025d1c  push    rbx
0x180025d1e  push    rbp
0x180025d1f  push    rsi
0x180025d20  push    rdi
0x180025d21  push    r12
0x180025d23  push    r14
0x180025d25  push    r15
0x180025d27  sub     rsp, 50h
0x180025d2b  test    edx, edx
0x180025d2d  mov     eax, 18h
0x180025d32  mov     esi, 16h
0x180025d37  mov     r15d, r9d
0x180025d3a  cmovnz  eax, edx
0x180025d3d  mov     ebp, 1
0x180025d42  test    r8d, r8d
0x180025d45  mov     r12d, r9d
0x180025d48  mov     rbx, rcx
0x180025d4b  cmovnz  esi, r8d
0x180025d4f  and     r15d, ebp
0x180025d52  jz      short loc_180025DA5
0x180025d54  test    dword ptr [rcx+10h], 1000h
0x180025d5b  jz      short loc_180025D6D
0x180025d5d  mov     edi, [rcx+0E0h]
0x180025d63  add     edi, [rcx+0ACh]
0x180025d69  add     edi, eax
0x180025d6b  jmp     short loc_180025D6F
0x180025d6d  mov     edi, eax
0x180025d6f  add     esi, [rcx+0DCh]
0x180025d75  lea     r14, [rcx+0B4h]
0x180025d7c  add     edi, [rcx+0D8h]
0x180025d82  cmp     edi, [r14]
0x180025d85  jge     short loc_180025DE9
0x180025d87  cmp     dword ptr [rcx+0A0h], 0
0x180025d8e  jz      short loc_180025DE9
0x180025d90  cmp     qword ptr [rcx+28h], 5
0x180025d95  jl      short loc_180025DA0
0x180025d97  cmp     dword ptr [rcx+0A4h], 0
0x180025d9e  jle     short loc_180025DE9
0x180025da0  mov     edi, [r14]
0x180025da3  jmp     short loc_180025DE9
0x180025da5  cmp     esi, 0FFFFFFFFh
0x180025da8  jnz     short loc_180025DB0
0x180025daa  mov     esi, [rcx+0B8h]
0x180025db0  cmp     eax, 0FFFFFFFFh
0x180025db3  jnz     short loc_180025DBD
0x180025db5  mov     edi, [rcx+0B4h]
0x180025dbb  jmp     short loc_180025DBF
0x180025dbd  mov     edi, eax
0x180025dbf  mov     edx, [rcx+0DCh]
0x180025dc5  lea     r14, [rcx+0B4h]
0x180025dcc  add     edx, [rcx+0B0h]
0x180025dd2  cmp     esi, edx
0x180025dd4  cmovl   esi, edx
0x180025dd7  mov     edx, [rcx+0D8h]
0x180025ddd  add     edx, [rcx+0ACh]
0x180025de3  cmp     edi, edx
0x180025de5  jge     short loc_180025DE9
0x180025de7  mov     edi, edx
0x180025de9  mov     rcx, [rcx+48h]; h
0x180025ded  test    rcx, rcx
0x180025df0  jz      short loc_180025DFF
0x180025df2  cmp     edi, [r14]
0x180025df5  jg      short loc_180025DFF
0x180025df7  cmp     esi, [rbx+0B8h]
0x180025dfd  jle     short loc_180025E68
0x180025dff  xorps   xmm0, xmm0
0x180025e02  movups  [rsp+88h+pv], xmm0
0x180025e07  movups  [rsp+88h+var_48], xmm0
0x180025e0c  test    rcx, rcx
0x180025e0f  jz      short loc_180025E2D
0x180025e11  lea     r8, [rsp+88h+pv]; pv
0x180025e16  mov     edx, 20h ; ' '; c
0x180025e1b  call    cs:__imp_GetObjectW
0x180025e21  cmp     edi, dword ptr [rsp+88h+pv+4]
0x180025e25  jg      short loc_180025E2D
0x180025e27  cmp     esi, dword ptr [rsp+88h+pv+8]
0x180025e2b  jle     short loc_180025E68
0x180025e2d  lea     edx, [rsi+8]; nHeight
0x180025e30  mov     [rsp+88h+lpBits], 0; lpBits
0x180025e39  lea     ecx, [rdi+8]; nWidth
0x180025e3c  mov     r9d, ebp; nBitCount
0x180025e3f  mov     r8d, ebp; nPlanes
0x180025e42  call    cs:__imp_CreateBitmap
0x180025e48  mov     rbp, rax
0x180025e4b  test    rax, rax
0x180025e4e  jz      short loc_180025ECC
0x180025e50  mov     rcx, [rbx+48h]; ho
0x180025e54  test    rcx, rcx
0x180025e57  jz      short loc_180025E5F
0x180025e59  call    cs:__imp_DeleteObject
0x180025e5f  mov     [rbx+48h], rbp
0x180025e63  mov     ebp, 1
0x180025e68  test    r12b, 2
0x180025e6c  jz      short loc_180025E72
0x180025e6e  mov     eax, ebp
0x180025e70  jmp     short loc_180025ECC
0x180025e72  test    r15d, r15d
0x180025e75  jnz     short loc_180025E92
0x180025e77  cmp     [r14], edi
0x180025e7a  jnz     short loc_180025E84
0x180025e7c  cmp     [rbx+0B8h], esi
0x180025e82  jz      short loc_180025E92
0x180025e84  mov     rcx, [rbx]; hWnd
0x180025e87  mov     r8d, ebp; bErase
0x180025e8a  xor     edx, edx; lpRect
0x180025e8c  call    cs:__imp_InvalidateRect
0x180025e92  mov     eax, [rbx+10h]
0x180025e95  shr     eax, 0Ah
0x180025e98  not     eax
0x180025e9a  mov     [r14], edi
0x180025e9d  and     eax, 2
0x180025ea0  mov     [rbx+0B8h], esi
0x180025ea6  mov     [rbx+0C4h], eax
0x180025eac  btr     dword ptr [rbx+13Ch], 10h
0x180025eb4  or      dword ptr [rbx+13Ch], 10h
0x180025ebb  or      eax, 0FFFFFFFFh
0x180025ebe  mov     [rbx+0E8h], eax
0x180025ec4  mov     [rbx+0ECh], eax
0x180025eca  jmp     short loc_180025E6E
0x180025ecc  add     rsp, 50h
0x180025ed0  pop     r15
0x180025ed2  pop     r14
0x180025ed4  pop     r12
0x180025ed6  pop     rdi
0x180025ed7  pop     rsi
0x180025ed8  pop     rbp
0x180025ed9  pop     rbx
0x180025eda  retn
```
