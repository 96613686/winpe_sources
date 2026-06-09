# CRenderer::RenderOutlineSymbol(void)

- ea: `0x180075bc0`
- end: `0x180075dfc`
- name: `?RenderOutlineSymbol@CRenderer@@QEAAHXZ`
- size: `572`
- prototype: `__int64 __fastcall(CRenderer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006ef4`

## callees

- `0x180006570`
- `0x1800301a0`
- `0x180037b10`
- `0x1800383c0`
- `0x18003b0a8`
- `0x180061450`
- `0x1800614b8`
- `0x18007591c`
- `0x180075bc0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180075dcb`
- `GDI32!DeleteDC` at `0x180075dcb`
- `GDI32!StretchBlt` at `0x180075daa`
- `GDI32!StretchBlt` at `0x180075daa`
- `GDI32!CreateCompatibleDC` at `0x180075c2f`
- `GDI32!CreateCompatibleDC` at `0x180075c2f`
- `GDI32!SelectObject` at `0x180075d15`
- `GDI32!SelectObject` at `0x180075dbc`
- `GDI32!SelectObject` at `0x180075d15`
- `GDI32!SelectObject` at `0x180075dbc`

## pseudocode

```c
__int64 __fastcall CRenderer::RenderOutlineSymbol(CRenderer *this)
{
  int v2; // r13d
  int v3; // r12d
  HDC hdcSrc; // r14
  HGDIOBJ v5; // rdi
  int wSrc; // r15d
  __int64 v7; // rax
  int CchLeft; // eax
  int EOP; // r8d
  __int128 v10; // xmm1
  int v11; // ebx
  HGDIOBJ v12; // rsi
  int hDest; // edi
  int v14; // ebx
  int v15; // r9d
  int v16; // eax
  __int128 v18; // [rsp+60h] [rbp-78h] BYREF
  __int64 v19; // [rsp+70h] [rbp-68h]
  _OWORD v20[6]; // [rsp+78h] [rbp-60h] BYREF
  int v21; // [rsp+E0h] [rbp+8h]
  int v22; // [rsp+E8h] [rbp+10h]

  v2 = CMeasurer::LXtoDX(this, 360 * *(unsigned __int8 *)(*((_QWORD *)this + 18) + 35LL));
  v3 = *((_DWORD *)this + 76);
  v22 = *((_DWORD *)this + 21);
  v21 = *((_DWORD *)this + 77);
  if ( !h && (unsigned int)InitializeOutlineBitmaps() )
    return 0;
  hdcSrc = CreateCompatibleDC(*((HDC *)this + 35));
  if ( !hdcSrc )
    return 0;
  if ( (*(_BYTE *)(*((_QWORD *)this + 18) + 35LL) & 1) != 0 )
  {
    v5 = h;
    wSrc = 4;
  }
  else
  {
    v7 = *((_QWORD *)this + 5);
    v5 = qword_1800A7310;
    wSrc = 10;
    v18 = *((_OWORD *)this + 4);
    v19 = v7;
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v18);
    if ( EOP < CchLeft )
    {
      v10 = *((_OWORD *)this + 2);
      v20[0] = *((_OWORD *)this + 1);
      v20[1] = v10;
      EOP = CTxtPtr::FindEOP((CTxtPtr *)v20, 0x3FFFFFFF, 0);
    }
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v18, EOP);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v18) )
    {
      v5 = qword_1800A7318;
    }
    else
    {
      v11 = *(unsigned __int8 *)(*((_QWORD *)this + 18) + 35LL);
      if ( v11 < (int)CPFRunPtr::GetOutlineLevel((CPFRunPtr *)&v18) )
        v5 = qword_1800A7320;
    }
  }
  if ( !v5 )
    return 0;
  v12 = SelectObject(hdcSrc, v5);
  hDest = CDisplay::Zoom(*((CDisplay **)this + 15), wSrc);
  v14 = *((__int16 *)this + 46) - *((__int16 *)this + 47) - hDest;
  v15 = CDisplay::Zoom(*((CDisplay **)this + 15), wSrc);
  v16 = v14 / 2;
  if ( v14 <= 0 )
    v16 = -v14;
  StretchBlt(*((HDC *)this + 35), v3 - v22 + v2, v21 + v16, v15, hDest, hdcSrc, 0, 0, wSrc, wSrc, 0xCC0020u);
  SelectObject(hdcSrc, v12);
  DeleteDC(hdcSrc);
  return 1;
}

```

## disassembly

```asm
0x180075bc0  mov     [rsp+arg_10], rbx
0x180075bc5  push    rbp
0x180075bc6  push    rsi
0x180075bc7  push    rdi
0x180075bc8  push    r12
0x180075bca  push    r13
0x180075bcc  push    r14
0x180075bce  push    r15
0x180075bd0  sub     rsp, 0A0h
0x180075bd7  mov     rax, [rcx+90h]
0x180075bde  mov     rbp, rcx
0x180075be1  movzx   edx, byte ptr [rax+23h]
0x180075be5  imul    edx, 168h; int
0x180075beb  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180075bf0  cmp     cs:h, 0
0x180075bf8  mov     r13d, eax
0x180075bfb  mov     eax, [rbp+54h]
0x180075bfe  mov     r12d, [rbp+130h]
0x180075c05  mov     [rsp+0D8h+arg_8], eax
0x180075c0c  mov     eax, [rbp+134h]
0x180075c12  mov     [rsp+0D8h+arg_0], eax
0x180075c19  jnz     short loc_180075C28
0x180075c1b  call    ?InitializeOutlineBitmaps@@YAJXZ; InitializeOutlineBitmaps(void)
0x180075c20  test    eax, eax
0x180075c22  jnz     loc_180075DDE
0x180075c28  mov     rcx, [rbp+118h]; hdc
0x180075c2f  call    cs:__imp_CreateCompatibleDC
0x180075c36  nop     dword ptr [rax+rax+00h]
0x180075c3b  mov     r14, rax
0x180075c3e  test    rax, rax
0x180075c41  jz      loc_180075DDE
0x180075c47  mov     rcx, [rbp+90h]
0x180075c4e  test    byte ptr [rcx+23h], 1
0x180075c52  jz      short loc_180075C66
0x180075c54  mov     rdi, cs:h
0x180075c5b  mov     r15d, 4
0x180075c61  jmp     loc_180075D06
0x180075c66  mov     rax, [rbp+28h]
0x180075c6a  lea     rcx, [rsp+0D8h+var_78]; this
0x180075c6f  movups  xmm0, xmmword ptr [rbp+40h]
0x180075c73  mov     rdi, cs:qword_1800A7310
0x180075c7a  mov     r15d, 0Ah
0x180075c80  mov     r8d, [rbp+50h]
0x180075c84  movdqu  [rsp+0D8h+var_78], xmm0
0x180075c8a  mov     [rsp+0D8h+var_68], rax
0x180075c8f  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x180075c94  cmp     r8d, eax
0x180075c97  jge     short loc_180075CC3
0x180075c99  movups  xmm0, xmmword ptr [rbp+10h]
0x180075c9d  xor     r8d, r8d; int *
0x180075ca0  mov     edx, 3FFFFFFFh; int
0x180075ca5  movups  xmm1, xmmword ptr [rbp+20h]
0x180075ca9  lea     rcx, [rsp+0D8h+var_60]; this
0x180075cae  movups  [rsp+0D8h+var_60], xmm0
0x180075cb3  movups  [rsp+0D8h+var_50], xmm1
0x180075cbb  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180075cc0  mov     r8d, eax
0x180075cc3  mov     edx, r8d; int
0x180075cc6  lea     rcx, [rsp+0D8h+var_78]; this
0x180075ccb  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x180075cd0  lea     rcx, [rsp+0D8h+var_78]; this
0x180075cd5  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180075cda  test    eax, eax
0x180075cdc  jz      short loc_180075CE7
0x180075cde  mov     rdi, cs:qword_1800A7318
0x180075ce5  jmp     short loc_180075D06
0x180075ce7  mov     rax, [rbp+90h]
0x180075cee  lea     rcx, [rsp+0D8h+var_78]; this
0x180075cf3  movzx   ebx, byte ptr [rax+23h]
0x180075cf7  call    ?GetOutlineLevel@CPFRunPtr@@QEAAJXZ; CPFRunPtr::GetOutlineLevel(void)
0x180075cfc  cmp     ebx, eax
0x180075cfe  cmovl   rdi, cs:qword_1800A7320
0x180075d06  test    rdi, rdi
0x180075d09  jz      loc_180075DDE
0x180075d0f  mov     rdx, rdi; h
0x180075d12  mov     rcx, r14; hdc
0x180075d15  call    cs:__imp_SelectObject
0x180075d1c  nop     dword ptr [rax+rax+00h]
0x180075d21  mov     rcx, [rbp+78h]; this
0x180075d25  mov     edx, r15d; int
0x180075d28  mov     rsi, rax
0x180075d2b  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180075d30  movsx   ecx, word ptr [rbp+5Eh]
0x180075d34  mov     edx, r15d; int
0x180075d37  movsx   ebx, word ptr [rbp+5Ch]
0x180075d3b  mov     edi, eax
0x180075d3d  sub     ebx, ecx
0x180075d3f  mov     rcx, [rbp+78h]; this
0x180075d43  sub     ebx, eax
0x180075d45  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180075d4a  mov     r9d, eax; wDest
0x180075d4d  mov     [rsp+0D8h+rop], 0CC0020h; rop
0x180075d55  mov     [rsp+0D8h+hSrc], r15d; hSrc
0x180075d5a  mov     r8d, 2
0x180075d60  mov     eax, ebx
0x180075d62  mov     [rsp+0D8h+wSrc], r15d; wSrc
0x180075d67  cdq
0x180075d68  mov     [rsp+0D8h+ySrc], 0; ySrc
0x180075d70  idiv    r8d
0x180075d73  mov     ecx, ebx
0x180075d75  mov     [rsp+0D8h+xSrc], 0; xSrc
0x180075d7d  neg     ecx
0x180075d7f  mov     [rsp+0D8h+hdcSrc], r14; hdcSrc
0x180075d84  test    ebx, ebx
0x180075d86  mov     [rsp+0D8h+hDest], edi; hDest
0x180075d8a  cmovle  eax, ecx
0x180075d8d  sub     r12d, [rsp+0D8h+arg_8]
0x180075d95  add     eax, [rsp+0D8h+arg_0]
0x180075d9c  mov     rcx, [rbp+118h]; hdcDest
0x180075da3  mov     r8d, eax; yDest
0x180075da6  lea     edx, [r12+r13]; xDest
0x180075daa  call    cs:__imp_StretchBlt
0x180075db1  nop     dword ptr [rax+rax+00h]
0x180075db6  mov     rdx, rsi; h
0x180075db9  mov     rcx, r14; hdc
0x180075dbc  call    cs:__imp_SelectObject
0x180075dc3  nop     dword ptr [rax+rax+00h]
0x180075dc8  mov     rcx, r14; hdc
0x180075dcb  call    cs:__imp_DeleteDC
0x180075dd2  nop     dword ptr [rax+rax+00h]
0x180075dd7  mov     eax, 1
0x180075ddc  jmp     short loc_180075DE0
0x180075dde  xor     eax, eax
0x180075de0  mov     rbx, [rsp+0D8h+arg_10]
0x180075de8  add     rsp, 0A0h
0x180075def  pop     r15
0x180075df1  pop     r14
0x180075df3  pop     r13
0x180075df5  pop     r12
0x180075df7  pop     rdi
0x180075df8  pop     rsi
0x180075df9  pop     rbp
0x180075dfa  retn
```
