# CPackage::GetFileDescriptor(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x1800089f8`
- end: `0x180008b8b`
- name: `?GetFileDescriptor@CPackage@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(CPackage *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800049f0`

## callees

- `0x180004124`
- `0x1800089f8`
- `0x18000ae20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008a29`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180008a29`

## pseudocode

```c
__int64 __fastcall CPackage::GetFileDescriptor(CPackage *this, const struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  HBITMAP v6; // rax
  HBITMAP v7; // rdi
  unsigned int v8; // ebx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  _OWORD *v11; // rcx
  __int128 v12; // xmm1
  _WORD *v13; // r9
  _WORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  _WORD *v17; // rdx

  if ( (a2->tymed & 1) == 0 )
    return 2147745892LL;
  a3->tymed = 1;
  v6 = (HBITMAP)GlobalAlloc(0x40u, 0x254u);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  a3->hBitmap = v6;
  v8 = 0;
  *(_DWORD *)v6 = 1;
  if ( *((_DWORD *)this + 26) == 1 )
  {
    v13 = v6 + 19;
    v14 = (_WORD *)(*((_QWORD *)this + 12) + 528LL);
    v15 = 2147483646;
    v16 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v14 )
        break;
      *v13++ = *v14++;
      --v15;
      --v16;
    }
    while ( v16 );
    v17 = v13 - 1;
    v8 = v16 == 0 ? 0x8007007A : 0;
    if ( v16 )
      v17 = v13;
    *v17 = 0;
    if ( v16 )
      v8 = StringCchCatW((unsigned __int16 *)v7 + 38, (unsigned __int64)v17, L".lnk");
    *((_DWORD *)v7 + 1) = 0x8000;
  }
  else if ( *((_DWORD *)this + 26) == 3 )
  {
    v9 = (_OWORD *)*((_QWORD *)this + 14);
    if ( v9 )
    {
      v10 = 4;
      v11 = v7 + 1;
      do
      {
        *v11 = *v9;
        v11[1] = v9[1];
        v11[2] = v9[2];
        v11[3] = v9[3];
        v11[4] = v9[4];
        v11[5] = v9[5];
        v11[6] = v9[6];
        v12 = v9[7];
        v9 += 8;
        v11[7] = v12;
        v11 += 8;
        --v10;
      }
      while ( v10 );
      *v11 = *v9;
      v11[1] = v9[1];
      v11[2] = v9[2];
      v11[3] = v9[3];
      v11[4] = v9[4];
      GetDisplayName((unsigned __int16 *)v7 + 38, (const unsigned __int16 *)(*((_QWORD *)this + 14) + 72LL));
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800089f8  push    rbx
0x1800089fa  push    rsi
0x1800089fb  push    rdi
0x1800089fc  push    r14
0x1800089fe  sub     rsp, 28h
0x180008a02  test    byte ptr [rdx+18h], 1
0x180008a06  mov     r14, r8
0x180008a09  mov     rsi, rcx
0x180008a0c  jnz     short loc_180008A18
0x180008a0e  mov     eax, 80040064h
0x180008a13  jmp     loc_180008B81
0x180008a18  mov     edx, 254h; dwBytes
0x180008a1d  mov     dword ptr [r8], 1
0x180008a24  mov     ecx, 40h ; '@'; uFlags
0x180008a29  call    cs:__imp_GlobalAlloc
0x180008a2f  xor     r11d, r11d
0x180008a32  mov     rdi, rax
0x180008a35  test    rax, rax
0x180008a38  jnz     short loc_180008A44
0x180008a3a  mov     eax, 8007000Eh
0x180008a3f  jmp     loc_180008B81
0x180008a44  mov     [r14+8], rdi
0x180008a48  mov     ebx, r11d
0x180008a4b  mov     dword ptr [rax], 1
0x180008a51  mov     ecx, [rsi+68h]
0x180008a54  sub     ecx, 1
0x180008a57  jz      loc_180008B0A
0x180008a5d  cmp     ecx, 2
0x180008a60  jnz     loc_180008B7F
0x180008a66  mov     rax, [rsi+70h]
0x180008a6a  test    rax, rax
0x180008a6d  jz      loc_180008B03
0x180008a73  mov     edx, 4
0x180008a78  lea     rcx, [rdi+4]
0x180008a7c  lea     r8d, [rdx+7Ch]
0x180008a80  movups  xmm0, xmmword ptr [rax]
0x180008a83  movups  xmmword ptr [rcx], xmm0
0x180008a86  movups  xmm1, xmmword ptr [rax+10h]
0x180008a8a  movups  xmmword ptr [rcx+10h], xmm1
0x180008a8e  movups  xmm0, xmmword ptr [rax+20h]
0x180008a92  movups  xmmword ptr [rcx+20h], xmm0
0x180008a96  movups  xmm1, xmmword ptr [rax+30h]
0x180008a9a  movups  xmmword ptr [rcx+30h], xmm1
0x180008a9e  movups  xmm0, xmmword ptr [rax+40h]
0x180008aa2  movups  xmmword ptr [rcx+40h], xmm0
0x180008aa6  movups  xmm1, xmmword ptr [rax+50h]
0x180008aaa  movups  xmmword ptr [rcx+50h], xmm1
0x180008aae  movups  xmm0, xmmword ptr [rax+60h]
0x180008ab2  movups  xmmword ptr [rcx+60h], xmm0
0x180008ab6  movups  xmm1, xmmword ptr [rax+70h]
0x180008aba  add     rax, r8
0x180008abd  movups  xmmword ptr [rcx+70h], xmm1
0x180008ac1  add     rcx, r8
0x180008ac4  sub     rdx, 1
0x180008ac8  jnz     short loc_180008A80
0x180008aca  movups  xmm0, xmmword ptr [rax]
0x180008acd  movups  xmmword ptr [rcx], xmm0
0x180008ad0  movups  xmm1, xmmword ptr [rax+10h]
0x180008ad4  movups  xmmword ptr [rcx+10h], xmm1
0x180008ad8  movups  xmm0, xmmword ptr [rax+20h]
0x180008adc  movups  xmmword ptr [rcx+20h], xmm0
0x180008ae0  movups  xmm1, xmmword ptr [rax+30h]
0x180008ae4  movups  xmmword ptr [rcx+30h], xmm1
0x180008ae8  movups  xmm0, xmmword ptr [rax+40h]
0x180008aec  movups  xmmword ptr [rcx+40h], xmm0
0x180008af0  mov     rdx, [rsi+70h]
0x180008af4  lea     rcx, [rdi+4Ch]; unsigned __int16 *
0x180008af8  add     rdx, 48h ; 'H'; unsigned __int16 *
0x180008afc  call    ?GetDisplayName@@YAXPEAGPEBG@Z; GetDisplayName(ushort *,ushort const *)
0x180008b01  jmp     short loc_180008B7F
0x180008b03  mov     ebx, 80004005h
0x180008b08  jmp     short loc_180008B7F
0x180008b0a  mov     rax, [rsi+60h]
0x180008b0e  lea     r9, [rdi+4Ch]
0x180008b12  add     rax, 210h
0x180008b18  mov     ecx, 7FFFFFFEh
0x180008b1d  mov     r8d, 104h
0x180008b23  test    rcx, rcx
0x180008b26  jz      short loc_180008B45
0x180008b28  movzx   edx, word ptr [rax]
0x180008b2b  test    dx, dx
0x180008b2e  jz      short loc_180008B45
0x180008b30  mov     [r9], dx
0x180008b34  add     rax, 2
0x180008b38  add     r9, 2
0x180008b3c  dec     rcx
0x180008b3f  sub     r8, 1
0x180008b43  jnz     short loc_180008B23
0x180008b45  mov     rax, r8
0x180008b48  lea     rdx, [r9-2]
0x180008b4c  neg     rax
0x180008b4f  sbb     ebx, ebx
0x180008b51  not     ebx
0x180008b53  and     ebx, 8007007Ah
0x180008b59  test    r8, r8
0x180008b5c  cmovnz  rdx, r9; unsigned __int64
0x180008b60  mov     [rdx], r11w
0x180008b64  jz      short loc_180008B78
0x180008b66  lea     r8, aLnk; ".lnk"
0x180008b6d  lea     rcx, [rdi+4Ch]; unsigned __int16 *
0x180008b71  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b76  mov     ebx, eax
0x180008b78  mov     dword ptr [rdi+4], 8000h
0x180008b7f  mov     eax, ebx
0x180008b81  add     rsp, 28h
0x180008b85  pop     r14
0x180008b87  pop     rdi
0x180008b88  pop     rsi
0x180008b89  pop     rbx
0x180008b8a  retn
```
