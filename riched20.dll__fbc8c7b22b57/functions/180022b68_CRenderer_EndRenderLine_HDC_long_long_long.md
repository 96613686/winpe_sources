# CRenderer::EndRenderLine(HDC__ *,long,long,long)

- ea: `0x180022b68`
- end: `0x180022e1a`
- name: `?EndRenderLine@CRenderer@@QEAAXPEAUHDC__@@JJJ@Z`
- size: `690`
- prototype: `void __usercall(CRenderer *__hidden this@<rcx>, HDC hdc@<rdx>, int@<r8d>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800219fc`
- `0x1800224c4`

## callees

- `0x180022b68`
- `0x18002327c`
- `0x18003b0a8`
- `0x180045fe4`

## import_xrefs

- `GDI32!LineTo` at `0x180022cc5`
- `GDI32!LineTo` at `0x180022d01`
- `GDI32!LineTo` at `0x180022d50`
- `GDI32!LineTo` at `0x180022cc5`
- `GDI32!LineTo` at `0x180022d01`
- `GDI32!LineTo` at `0x180022d50`
- `GDI32!MoveToEx` at `0x180022ca8`
- `GDI32!MoveToEx` at `0x180022ce8`
- `GDI32!MoveToEx` at `0x180022d38`
- `GDI32!MoveToEx` at `0x180022ca8`
- `GDI32!MoveToEx` at `0x180022ce8`
- `GDI32!MoveToEx` at `0x180022d38`
- `GDI32!CreatePen` at `0x180022bed`
- `GDI32!CreatePen` at `0x180022bed`
- `GDI32!DeleteObject` at `0x180022dad`
- `GDI32!DeleteObject` at `0x180022dad`
- `GDI32!SelectObject` at `0x180022c82`
- `GDI32!SelectObject` at `0x180022d9c`
- `GDI32!SelectObject` at `0x180022c82`
- `GDI32!SelectObject` at `0x180022d9c`
- `GDI32!SetBkColor` at `0x180022df0`
- `GDI32!SetBkColor` at `0x180022df0`

## pseudocode

```c
void __fastcall CRenderer::EndRenderLine(CRenderer *this, HDC hdc, int a3, int a4, int a5)
{
  __int64 v5; // r10
  int v7; // eax
  HDC v8; // r14
  __int64 v9; // r10
  const int *v10; // r15
  __int64 v11; // rdx
  COLORREF v12; // r8d
  HPEN Pen; // rsi
  int v14; // ebx
  int v15; // ebp
  int v16; // eax
  int v17; // r13d
  int v18; // ebp
  int v19; // ebx
  int v20; // esi
  int i; // ebp
  int v22; // edx
  COLORREF v23; // edx
  int v24; // [rsp+24h] [rbp-64h]
  HGDIOBJ h; // [rsp+28h] [rbp-60h]
  HPEN ho; // [rsp+30h] [rbp-58h]
  int y; // [rsp+90h] [rbp+8h]
  int x; // [rsp+A0h] [rbp+18h]

  x = a3;
  v5 = *((_QWORD *)this + 18);
  v7 = a4;
  v8 = hdc;
  if ( (*(_WORD *)(v5 + 2) & 0x4000) != 0 && (*((_BYTE *)this + 101) & 0x10) != 0 )
  {
    v10 = CTabsArray::Deref(qword_1800A72C0, *(__int16 *)(v5 + 18));
    v11 = *(_DWORD *)(v9 + 52) & 0x1F;
    if ( (unsigned int)(v11 - 1) > 0xF )
      v12 = *((_DWORD *)this + 59);
    else
      v12 = *((_DWORD *)&g_Colors + v11 - 1);
    Pen = CreatePen(0, 0, v12);
    ho = Pen;
    v14 = CMeasurer::LXtoDX(this, *(_DWORD *)(*((_QWORD *)this + 18) + 12LL));
    v15 = CMeasurer::LXtoDX(this, *(_DWORD *)(*((_QWORD *)this + 18) + 4LL));
    v24 = v15;
    v16 = CMeasurer::LXtoDX(this, v10[*(unsigned __int8 *)(*((_QWORD *)this + 18) + 17LL) - 1] & 0xFFFFFF);
    if ( Pen )
    {
      v17 = a5 - v14;
      v18 = v16 - v15 + a5 - v14;
      y = *((_DWORD *)this + 77);
      v19 = y + *((__int16 *)this + 46);
      h = SelectObject(*((HDC *)this + 35), Pen);
      MoveToEx(*((HDC *)this + 35), v17, y, 0);
      LineTo(*((HDC *)this + 35), v18, y);
      if ( (*((_BYTE *)this + 103) & 0x20) == 0 )
      {
        MoveToEx(*((HDC *)this + 35), v17, v19 - 1, 0);
        LineTo(*((HDC *)this + 35), v18, v19 - 1);
      }
      v20 = 0;
      for ( i = *(unsigned __int8 *)(*((_QWORD *)this + 18) + 17LL); i >= 0; --i )
      {
        MoveToEx(*((HDC *)this + 35), v20 + v17, y, 0);
        LineTo(*((HDC *)this + 35), v20 + v17, v19);
        if ( i )
        {
          v22 = *v10++ & 0xFFFFFF;
          v20 = CMeasurer::LXtoDX(this, v22) - v24;
        }
      }
      v8 = hdc;
      if ( h )
        SelectObject(*((HDC *)this + 35), h);
      DeleteObject(ho);
    }
    a3 = x;
    v7 = a4;
  }
  if ( v8 )
    CRenderer::RenderOffScreenBitmap(this, v8, a3, v7);
  v23 = *((_DWORD *)this + 56);
  if ( v23 != *((_DWORD *)this + 60) )
  {
    SetBkColor(*((HDC *)this + 35), v23);
    *((_DWORD *)this + 60) = *((_DWORD *)this + 56);
  }
}

```

## disassembly

```asm
0x180022b68  mov     [rsp+arg_18], r9d
0x180022b6d  mov     [rsp+x], r8d
0x180022b72  mov     [rsp+arg_8], rdx
0x180022b77  push    rbx
0x180022b78  push    rbp
0x180022b79  push    rsi
0x180022b7a  push    rdi
0x180022b7b  push    r12
0x180022b7d  push    r13
0x180022b7f  push    r14
0x180022b81  push    r15
0x180022b83  sub     rsp, 48h
0x180022b87  mov     r10, [rcx+90h]
0x180022b8e  mov     rdi, rcx
0x180022b91  mov     ecx, 4000h
0x180022b96  mov     eax, r9d
0x180022b99  mov     r14, rdx
0x180022b9c  test    [r10+2], cx
0x180022ba1  jz      loc_180022DC8
0x180022ba7  test    byte ptr [rdi+65h], 10h
0x180022bab  jz      loc_180022DC8
0x180022bb1  movsx   edx, word ptr [r10+12h]; int
0x180022bb6  mov     rcx, cs:qword_1800A72C0; this
0x180022bbd  call    ?Deref@CTabsArray@@QEBAPEBJJ@Z; CTabsArray::Deref(long)
0x180022bc2  mov     edx, [r10+34h]
0x180022bc6  mov     r15, rax
0x180022bc9  and     edx, 1Fh
0x180022bcc  lea     ecx, [rdx-1]
0x180022bcf  cmp     ecx, 0Fh
0x180022bd2  ja      short loc_180022BE2
0x180022bd4  lea     r8, ?g_Colors@@3QBKB; ulong const near * const g_Colors
0x180022bdb  mov     r8d, [r8+rdx*4-4]
0x180022be0  jmp     short loc_180022BE9
0x180022be2  mov     r8d, [rdi+0ECh]; color
0x180022be9  xor     edx, edx; cWidth
0x180022beb  xor     ecx, ecx; iStyle
0x180022bed  call    cs:__imp_CreatePen
0x180022bf4  nop     dword ptr [rax+rax+00h]
0x180022bf9  mov     rdx, [rdi+90h]
0x180022c00  mov     rcx, rdi; this
0x180022c03  mov     rsi, rax
0x180022c06  mov     [rsp+88h+ho], rax
0x180022c0b  mov     edx, [rdx+0Ch]; int
0x180022c0e  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180022c13  mov     rdx, [rdi+90h]
0x180022c1a  mov     rcx, rdi; this
0x180022c1d  mov     ebx, eax
0x180022c1f  mov     edx, [rdx+4]; int
0x180022c22  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180022c27  mov     rcx, [rdi+90h]
0x180022c2e  mov     ebp, eax
0x180022c30  mov     [rsp+88h+var_64], eax
0x180022c34  movzx   edx, byte ptr [rcx+11h]
0x180022c38  mov     rcx, rdi; this
0x180022c3b  mov     edx, [r15+rdx*4-4]
0x180022c40  and     edx, 0FFFFFFh; int
0x180022c46  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180022c4b  test    rsi, rsi
0x180022c4e  jz      loc_180022DB9
0x180022c54  mov     r13d, [rsp+88h+arg_20]
0x180022c5c  sub     eax, ebp
0x180022c5e  mov     rcx, [rdi+118h]; hdc
0x180022c65  sub     r13d, ebx
0x180022c68  movsx   ebx, word ptr [rdi+5Ch]
0x180022c6c  mov     rdx, rsi; h
0x180022c6f  lea     ebp, [rax+r13]
0x180022c73  mov     eax, [rdi+134h]
0x180022c79  mov     [rsp+88h+y], eax
0x180022c80  add     ebx, eax
0x180022c82  call    cs:__imp_SelectObject
0x180022c89  nop     dword ptr [rax+rax+00h]
0x180022c8e  mov     r8d, [rsp+88h+y]; y
0x180022c96  xor     r9d, r9d; lppt
0x180022c99  mov     rcx, [rdi+118h]; hdc
0x180022ca0  mov     edx, r13d; x
0x180022ca3  mov     [rsp+88h+h], rax
0x180022ca8  call    cs:__imp_MoveToEx
0x180022caf  nop     dword ptr [rax+rax+00h]
0x180022cb4  mov     r8d, [rsp+88h+y]; y
0x180022cbc  mov     edx, ebp; x
0x180022cbe  mov     rcx, [rdi+118h]; hdc
0x180022cc5  call    cs:__imp_LineTo
0x180022ccc  nop     dword ptr [rax+rax+00h]
0x180022cd1  test    byte ptr [rdi+67h], 20h
0x180022cd5  jnz     short loc_180022D0D
0x180022cd7  mov     rcx, [rdi+118h]; hdc
0x180022cde  lea     r8d, [rbx-1]; y
0x180022ce2  xor     r9d, r9d; lppt
0x180022ce5  mov     edx, r13d; x
0x180022ce8  call    cs:__imp_MoveToEx
0x180022cef  nop     dword ptr [rax+rax+00h]
0x180022cf4  mov     rcx, [rdi+118h]; hdc
0x180022cfb  lea     r8d, [rbx-1]; y
0x180022cff  mov     edx, ebp; x
0x180022d01  call    cs:__imp_LineTo
0x180022d08  nop     dword ptr [rax+rax+00h]
0x180022d0d  mov     rax, [rdi+90h]
0x180022d14  xor     esi, esi
0x180022d16  mov     r12d, [rsp+88h+y]
0x180022d1e  mov     r14d, ebx
0x180022d21  movzx   ebp, byte ptr [rax+11h]
0x180022d25  mov     rcx, [rdi+118h]; hdc
0x180022d2c  lea     ebx, [rsi+r13]
0x180022d30  mov     edx, ebx; x
0x180022d32  xor     r9d, r9d; lppt
0x180022d35  mov     r8d, r12d; y
0x180022d38  call    cs:__imp_MoveToEx
0x180022d3f  nop     dword ptr [rax+rax+00h]
0x180022d44  mov     rcx, [rdi+118h]; hdc
0x180022d4b  mov     r8d, r14d; y
0x180022d4e  mov     edx, ebx; x
0x180022d50  call    cs:__imp_LineTo
0x180022d57  nop     dword ptr [rax+rax+00h]
0x180022d5c  test    ebp, ebp
0x180022d5e  jz      short loc_180022D7B
0x180022d60  mov     edx, [r15]
0x180022d63  mov     rcx, rdi; this
0x180022d66  and     edx, 0FFFFFFh; int
0x180022d6c  add     r15, 4
0x180022d70  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180022d75  mov     esi, eax
0x180022d77  sub     esi, [rsp+88h+var_64]
0x180022d7b  sub     ebp, 1
0x180022d7e  jns     short loc_180022D25
0x180022d80  mov     r12, [rsp+88h+h]
0x180022d85  mov     r14, [rsp+88h+arg_8]
0x180022d8d  test    r12, r12
0x180022d90  jz      short loc_180022DA8
0x180022d92  mov     rcx, [rdi+118h]; hdc
0x180022d99  mov     rdx, r12; h
0x180022d9c  call    cs:__imp_SelectObject
0x180022da3  nop     dword ptr [rax+rax+00h]
0x180022da8  mov     rcx, [rsp+88h+ho]; ho
0x180022dad  call    cs:__imp_DeleteObject
0x180022db4  nop     dword ptr [rax+rax+00h]
0x180022db9  mov     r8d, [rsp+88h+x]; x
0x180022dc1  mov     eax, [rsp+88h+arg_18]
0x180022dc8  test    r14, r14
0x180022dcb  jz      short loc_180022DDB
0x180022dcd  mov     r9d, eax; y
0x180022dd0  mov     rdx, r14; hdc
0x180022dd3  mov     rcx, rdi; this
0x180022dd6  call    ?RenderOffScreenBitmap@CRenderer@@QEAAXPEAUHDC__@@JJ@Z; CRenderer::RenderOffScreenBitmap(HDC__ *,long,long)
0x180022ddb  mov     edx, [rdi+0E0h]; color
0x180022de1  cmp     edx, [rdi+0F0h]
0x180022de7  jz      short loc_180022E08
0x180022de9  mov     rcx, [rdi+118h]; hdc
0x180022df0  call    cs:__imp_SetBkColor
0x180022df7  nop     dword ptr [rax+rax+00h]
0x180022dfc  mov     eax, [rdi+0E0h]
0x180022e02  mov     [rdi+0F0h], eax
0x180022e08  add     rsp, 48h
0x180022e0c  pop     r15
0x180022e0e  pop     r14
0x180022e10  pop     r13
0x180022e12  pop     r12
0x180022e14  pop     rdi
0x180022e15  pop     rsi
0x180022e16  pop     rbp
0x180022e17  pop     rbx
0x180022e18  retn
```
