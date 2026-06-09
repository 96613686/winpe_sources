# CRenderer::StartRender(tagRECT const &,tagRECT const &,long)

- ea: `0x18002e440`
- end: `0x18002e766`
- name: `?StartRender@CRenderer@@QEAAHAEBUtagRECT@@0J@Z`
- size: `806`
- prototype: `int(CRenderer *__hidden this, const struct tagRECT *, const struct tagRECT *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e060`
- `0x18005a300`

## callees

- `0x18002e440`
- `0x18002e76c`
- `0x18002e7e4`
- `0x180095010`

## import_xrefs

- `GDI32!SetTextAlign` at `0x18002e5c7`
- `GDI32!SetTextAlign` at `0x18002e5c7`
- `GDI32!CreateCompatibleDC` at `0x18002e671`
- `GDI32!CreateCompatibleDC` at `0x18002e671`
- `GDI32!GetCurrentObject` at `0x18002e62f`
- `GDI32!GetCurrentObject` at `0x18002e62f`
- `GDI32!SelectObject` at `0x18002e6b3`
- `GDI32!SelectObject` at `0x18002e6b3`
- `GDI32!RealizePalette` at `0x18002e70c`
- `GDI32!RealizePalette` at `0x18002e70c`
- `GDI32!SelectPalette` at `0x18002e6f9`
- `GDI32!SelectPalette` at `0x18002e6f9`
- `GDI32!SetBkColor` at `0x18002e52d`
- `GDI32!SetBkColor` at `0x18002e6d2`
- `GDI32!SetBkColor` at `0x18002e52d`
- `GDI32!SetBkColor` at `0x18002e6d2`
- `GDI32!SetBkMode` at `0x18002e5df`
- `GDI32!SetBkMode` at `0x18002e5df`
- `GDI32!CreateCompatibleBitmap` at `0x18002e694`
- `GDI32!CreateCompatibleBitmap` at `0x18002e694`
- `GDI32!ExtTextOutA` at `0x18002e5b2`
- `GDI32!ExtTextOutA` at `0x18002e5b2`

## pseudocode

```c
__int64 __fastcall CRenderer::StartRender(CRenderer *this, const struct tagRECT *a2, const struct tagRECT *a3, int a4)
{
  __int64 v4; // rax
  __int64 v6; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // ebp
  int v13; // esi
  int v14; // ebp
  unsigned int v15; // eax
  COLORREF v16; // edx
  HDC v17; // rcx
  int v18; // esi
  __int64 v19; // rcx
  HPALETTE CurrentObject; // rax
  HPALETTE v21; // rsi
  HDC v22; // r14
  HDC *v23; // rdi
  COLORREF v24; // r15d
  int v25; // ebp
  int v26; // r12d
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v29; // rax
  HPALETTE v30; // rax
  HDC v31; // rcx

  v4 = *((_QWORD *)this + 15);
  v6 = *((_QWORD *)this + 5);
  v10 = *(_QWORD *)(v4 + 16);
  v11 = *(_QWORD *)(v4 + 24);
  v12 = *(_DWORD *)(v6 + 180);
  v13 = *(_DWORD *)(v10 + 180);
  if ( !v11 )
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 48) + 24LL))(*(_QWORD *)(v10 + 48));
  *((_QWORD *)this + 35) = v11;
  *(struct tagRECT *)((char *)this + 168) = *a2;
  *(struct tagRECT *)((char *)this + 184) = *a3;
  v14 = v12 & 0x8000000;
  if ( v14 && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 120LL))(*((_QWORD *)this + 15)) )
  {
    *((_DWORD *)this + 56) = dword_1800A6FA0;
    v15 = dword_1800A6FA4;
  }
  else
  {
    *((_DWORD *)this + 56) = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 48) + 224LL))(
                               *(_QWORD *)(v6 + 48),
                               5);
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 48) + 224LL))(*(_QWORD *)(v6 + 48), 8);
  }
  v16 = *((_DWORD *)this + 56);
  v17 = (HDC)*((_QWORD *)this + 35);
  *((_DWORD *)this + 59) = v15;
  SetBkColor(v17, v16);
  *((_DWORD *)this + 72) &= ~2u;
  v18 = v13 & 0x400;
  *((_DWORD *)this + 60) = *((_DWORD *)this + 56);
  *((_DWORD *)this + 72) |= v18 == 0 ? 2 : 0;
  v19 = *((_QWORD *)this + 15);
  if ( *(_QWORD *)(v19 + 24) && *(_DWORD *)(v19 + 32)
    || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 112LL))(v19) )
  {
    *((_DWORD *)this + 72) &= 0xFFFFFFBD;
    if ( !v18 )
      ExtTextOutA(*((HDC *)this + 35), 0, 0, 2u, a3, 0, 0, 0);
  }
  SetTextAlign(*((HDC *)this + 35), 0);
  SetBkMode(*((HDC *)this + 35), 1);
  *((_DWORD *)this + 72) &= ~0x20u;
  if ( !a4 )
    goto LABEL_27;
  if ( !v14 )
  {
    CurrentObject = (HPALETTE)GetCurrentObject(*((HDC *)this + 35), 5u);
    goto LABEL_18;
  }
  if ( (*(_DWORD *)(v6 + 180) & 0x2000000) != 0 )
  {
    CurrentObject = (HPALETTE)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 48) + 360LL))(*(_QWORD *)(v6 + 48));
LABEL_18:
    v21 = CurrentObject;
    goto LABEL_19;
  }
  v21 = 0;
LABEL_19:
  v22 = (HDC)*((_QWORD *)this + 35);
  v23 = (HDC *)((char *)this + 248);
  v24 = *((_DWORD *)this + 56);
  v25 = *((_DWORD *)this + 48);
  v26 = *((_DWORD *)this + 46);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  CompatibleDC = CreateCompatibleDC(v22);
  *((_QWORD *)this + 31) = CompatibleDC;
  if ( CompatibleDC )
  {
    CompatibleBitmap = CreateCompatibleBitmap(v22, v25 - v26, a4);
    *((_QWORD *)this + 33) = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      v29 = SelectObject(*v23, CompatibleBitmap);
      *((_QWORD *)this + 32) = v29;
      if ( v29 )
      {
        if ( SetBkColor(*v23, v24) != -1 && *v23 )
        {
          if ( v21 )
          {
            v30 = SelectPalette(*v23, v21, 1);
            v31 = *v23;
            *((_QWORD *)this + 34) = v30;
            RealizePalette(v31);
          }
          *((_DWORD *)this + 72) |= 0x20u;
LABEL_27:
          *((_DWORD *)this + 72) ^= ((unsigned __int16)*((_DWORD *)this + 72)
                                   ^ (unsigned __int16)((unsigned __int16)CW32System::IsEnhancedMetafileDC(*((HDC *)this + 35)) << 8))
                                  & 0x100;
          return 1;
        }
      }
    }
  }
  COffScreenDC::FreeData((CRenderer *)((char *)this + 248));
  return 0;
}

```

## disassembly

```asm
0x18002e440  push    rbx
0x18002e442  push    rbp
0x18002e443  push    rsi
0x18002e444  push    rdi
0x18002e445  push    r12
0x18002e447  push    r13
0x18002e449  push    r14
0x18002e44b  push    r15
0x18002e44d  sub     rsp, 48h
0x18002e451  mov     rax, [rcx+78h]
0x18002e455  mov     rbx, rcx
0x18002e458  mov     rdi, [rcx+28h]
0x18002e45c  xor     r12d, r12d
0x18002e45f  mov     r13d, r9d
0x18002e462  mov     r14, r8
0x18002e465  mov     r15, rdx
0x18002e468  mov     rcx, [rax+10h]
0x18002e46c  mov     rax, [rax+18h]
0x18002e470  mov     ebp, [rdi+0B4h]
0x18002e476  mov     esi, [rcx+0B4h]
0x18002e47c  test    rax, rax
0x18002e47f  jnz     short loc_18002E491
0x18002e481  mov     rcx, [rcx+30h]
0x18002e485  mov     rax, [rcx]
0x18002e488  mov     rax, [rax+18h]
0x18002e48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e491  mov     [rbx+118h], rax
0x18002e498  movups  xmm0, xmmword ptr [r15]
0x18002e49c  mov     r15d, 5
0x18002e4a2  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x18002e4aa  movups  xmm1, xmmword ptr [r14]
0x18002e4ae  movdqu  xmmword ptr [rbx+0B8h], xmm1
0x18002e4b6  and     ebp, 8000000h
0x18002e4bc  jz      short loc_18002E4E6
0x18002e4be  mov     rcx, [rbx+78h]
0x18002e4c2  mov     rax, [rcx]
0x18002e4c5  mov     rax, [rax+78h]
0x18002e4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4ce  test    eax, eax
0x18002e4d0  jz      short loc_18002E4E6
0x18002e4d2  mov     eax, cs:dword_1800A6FA0
0x18002e4d8  mov     [rbx+0E0h], eax
0x18002e4de  mov     eax, cs:dword_1800A6FA4
0x18002e4e4  jmp     short loc_18002E51A
0x18002e4e6  mov     rcx, [rdi+30h]
0x18002e4ea  mov     edx, r15d
0x18002e4ed  mov     rax, [rcx]
0x18002e4f0  mov     rax, [rax+0E0h]
0x18002e4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4fc  mov     [rbx+0E0h], eax
0x18002e502  mov     edx, 8
0x18002e507  mov     rcx, [rdi+30h]
0x18002e50b  mov     rax, [rcx]
0x18002e50e  mov     rax, [rax+0E0h]
0x18002e515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e51a  mov     edx, [rbx+0E0h]; color
0x18002e520  mov     rcx, [rbx+118h]; hdc
0x18002e527  mov     [rbx+0ECh], eax
0x18002e52d  call    cs:__imp_SetBkColor
0x18002e534  nop     dword ptr [rax+rax+00h]
0x18002e539  and     dword ptr [rbx+120h], 0FFFFFFFDh
0x18002e540  and     esi, 400h
0x18002e546  mov     eax, [rbx+0E0h]
0x18002e54c  mov     [rbx+0F0h], eax
0x18002e552  mov     eax, esi
0x18002e554  neg     eax
0x18002e556  sbb     ecx, ecx
0x18002e558  not     ecx
0x18002e55a  and     ecx, 2
0x18002e55d  or      [rbx+120h], ecx
0x18002e563  mov     rcx, [rbx+78h]
0x18002e567  cmp     [rcx+18h], r12
0x18002e56b  jz      short loc_18002E573
0x18002e56d  cmp     [rcx+20h], r12d
0x18002e571  jnz     short loc_18002E583
0x18002e573  mov     rax, [rcx]
0x18002e576  mov     rax, [rax+70h]
0x18002e57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e57f  test    eax, eax
0x18002e581  jnz     short loc_18002E5BE
0x18002e583  and     dword ptr [rbx+120h], 0FFFFFFBDh
0x18002e58a  test    esi, esi
0x18002e58c  jnz     short loc_18002E5BE
0x18002e58e  mov     rcx, [rbx+118h]; hdc
0x18002e595  lea     r9d, [rsi+2]; options
0x18002e599  mov     [rsp+88h+lpDx], r12; lpDx
0x18002e59e  xor     r8d, r8d; y
0x18002e5a1  mov     [rsp+88h+c], r12d; c
0x18002e5a6  xor     edx, edx; x
0x18002e5a8  mov     [rsp+88h+lpString], r12; lpString
0x18002e5ad  mov     [rsp+88h+lprect], r14; lprect
0x18002e5b2  call    cs:__imp_ExtTextOutA
0x18002e5b9  nop     dword ptr [rax+rax+00h]
0x18002e5be  mov     rcx, [rbx+118h]; hdc
0x18002e5c5  xor     edx, edx; align
0x18002e5c7  call    cs:__imp_SetTextAlign
0x18002e5ce  nop     dword ptr [rax+rax+00h]
0x18002e5d3  mov     rcx, [rbx+118h]; hdc
0x18002e5da  mov     edx, 1; mode
0x18002e5df  call    cs:__imp_SetBkMode
0x18002e5e6  nop     dword ptr [rax+rax+00h]
0x18002e5eb  and     dword ptr [rbx+120h], 0FFFFFFDFh
0x18002e5f2  test    r13d, r13d
0x18002e5f5  jz      loc_18002E71F
0x18002e5fb  test    ebp, ebp
0x18002e5fd  jz      short loc_18002E625
0x18002e5ff  test    dword ptr [rdi+0B4h], 2000000h
0x18002e609  jz      short loc_18002E620
0x18002e60b  mov     rcx, [rdi+30h]
0x18002e60f  mov     rax, [rcx]
0x18002e612  mov     rax, [rax+168h]
0x18002e619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e61e  jmp     short loc_18002E63B
0x18002e620  mov     rsi, r12
0x18002e623  jmp     short loc_18002E63E
0x18002e625  mov     rcx, [rbx+118h]; hdc
0x18002e62c  mov     edx, r15d; type
0x18002e62f  call    cs:__imp_GetCurrentObject
0x18002e636  nop     dword ptr [rax+rax+00h]
0x18002e63b  mov     rsi, rax
0x18002e63e  mov     r14, [rbx+118h]
0x18002e645  lea     rdi, [rbx+0F8h]
0x18002e64c  mov     r15d, [rbx+0E0h]
0x18002e653  xor     eax, eax
0x18002e655  mov     ebp, [rbx+0C0h]
0x18002e65b  mov     rcx, r14; hdc
0x18002e65e  mov     r12d, [rbx+0B8h]
0x18002e665  mov     [rdi+8], rax
0x18002e669  mov     [rdi+10h], rax
0x18002e66d  mov     [rdi+18h], rax
0x18002e671  call    cs:__imp_CreateCompatibleDC
0x18002e678  nop     dword ptr [rax+rax+00h]
0x18002e67d  mov     [rdi], rax
0x18002e680  test    rax, rax
0x18002e683  jz      loc_18002E75A
0x18002e689  sub     ebp, r12d
0x18002e68c  mov     r8d, r13d; cy
0x18002e68f  mov     edx, ebp; cx
0x18002e691  mov     rcx, r14; hdc
0x18002e694  call    cs:__imp_CreateCompatibleBitmap
0x18002e69b  nop     dword ptr [rax+rax+00h]
0x18002e6a0  mov     [rdi+10h], rax
0x18002e6a4  test    rax, rax
0x18002e6a7  jz      loc_18002E75A
0x18002e6ad  mov     rcx, [rdi]; hdc
0x18002e6b0  mov     rdx, rax; h
0x18002e6b3  call    cs:__imp_SelectObject
0x18002e6ba  nop     dword ptr [rax+rax+00h]
0x18002e6bf  mov     [rdi+8], rax
0x18002e6c3  test    rax, rax
0x18002e6c6  jz      loc_18002E75A
0x18002e6cc  mov     rcx, [rdi]; hdc
0x18002e6cf  mov     edx, r15d; color
0x18002e6d2  call    cs:__imp_SetBkColor
0x18002e6d9  nop     dword ptr [rax+rax+00h]
0x18002e6de  cmp     eax, 0FFFFFFFFh
0x18002e6e1  jz      short loc_18002E75A
0x18002e6e3  mov     rcx, [rdi]; hdc
0x18002e6e6  test    rcx, rcx
0x18002e6e9  jz      short loc_18002E75A
0x18002e6eb  test    rsi, rsi
0x18002e6ee  jz      short loc_18002E718
0x18002e6f0  mov     r8d, 1; bForceBkgd
0x18002e6f6  mov     rdx, rsi; hPal
0x18002e6f9  call    cs:__imp_SelectPalette
0x18002e700  nop     dword ptr [rax+rax+00h]
0x18002e705  mov     rcx, [rdi]; hdc
0x18002e708  mov     [rdi+18h], rax
0x18002e70c  call    cs:__imp_RealizePalette
0x18002e713  nop     dword ptr [rax+rax+00h]
0x18002e718  or      dword ptr [rbx+120h], 20h
0x18002e71f  mov     rcx, [rbx+118h]; hdc
0x18002e726  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x18002e72b  mov     ecx, [rbx+120h]
0x18002e731  shl     eax, 8
0x18002e734  xor     eax, ecx
0x18002e736  and     eax, 100h
0x18002e73b  xor     eax, ecx
0x18002e73d  mov     [rbx+120h], eax
0x18002e743  mov     eax, 1
0x18002e748  add     rsp, 48h
0x18002e74c  pop     r15
0x18002e74e  pop     r14
0x18002e750  pop     r13
0x18002e752  pop     r12
0x18002e754  pop     rdi
0x18002e755  pop     rsi
0x18002e756  pop     rbp
0x18002e757  pop     rbx
0x18002e758  retn
0x18002e75a  mov     rcx, rdi; this
0x18002e75d  call    ?FreeData@COffScreenDC@@AEAAXXZ; COffScreenDC::FreeData(void)
0x18002e762  xor     eax, eax
0x18002e764  jmp     short loc_18002E748
```
