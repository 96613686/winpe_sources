# CMagellanBMPStateWrap::CMagellanBMPStateWrap(CTxtEdit &,HDC__ *)

- ea: `0x18003b054`
- end: `0x18003b1fa`
- name: `??0CMagellanBMPStateWrap@@QEAA@AEAVCTxtEdit@@PEAUHDC__@@@Z`
- size: `422`
- prototype: `CMagellanBMPStateWrap *__fastcall(CMagellanBMPStateWrap *__hidden this, struct CTxtEdit *, HDC)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e200`
- `0x18003ad78`
- `0x180082420`

## callees

- `0x18003b054`
- `0x18003e5c8`
- `0x18003f3d8`

## import_xrefs

- `GDI32!BitBlt` at `0x18003b1ba`
- `GDI32!BitBlt` at `0x18003b1ba`
- `GDI32!DeleteDC` at `0x18003b1da`
- `GDI32!DeleteDC` at `0x18003b1da`
- `GDI32!CreateCompatibleDC` at `0x18003b0f7`
- `GDI32!CreateCompatibleDC` at `0x18003b0f7`
- `GDI32!SelectObject` at `0x18003b110`
- `GDI32!SelectObject` at `0x18003b110`
- `GDI32!DPtoLP` at `0x18003b15b`
- `GDI32!DPtoLP` at `0x18003b173`
- `GDI32!DPtoLP` at `0x18003b15b`
- `GDI32!DPtoLP` at `0x18003b173`
- `GDI32!GetMapMode` at `0x18003b119`
- `GDI32!GetMapMode` at `0x18003b119`
- `GDI32!SetMapMode` at `0x18003b124`
- `GDI32!SetMapMode` at `0x18003b124`
- `GDI32!GetObjectA` at `0x18003b137`
- `GDI32!GetObjectA` at `0x18003b137`

## pseudocode

```c
CMagellanBMPStateWrap *__fastcall CMagellanBMPStateWrap::CMagellanBMPStateWrap(
        CMagellanBMPStateWrap *this,
        struct CTxtEdit *a2,
        HDC a3)
{
  char *v4; // rbx
  int v5; // esi
  __int16 v6; // r12
  __int64 v8; // r13
  HDC DC; // rax
  HDC v10; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r15
  int MapMode; // eax
  _OWORD pv[2]; // [rsp+50h] [rbp-20h] BYREF
  struct tagPOINT pt; // [rsp+B0h] [rbp+40h] BYREF
  struct tagPOINT x1; // [rsp+B8h] [rbp+48h] BYREF

  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 2) = a2;
  v4 = (char *)a2 + 24;
  v5 = 1;
  if ( !a3 || (*v4 & 1) == 0 )
  {
    v6 = *(_WORD *)v4 & 1;
    if ( (*(_WORD *)v4 & 1) != 0 )
    {
      if ( *((_QWORD *)a2 + 4) )
      {
        v8 = *((_QWORD *)a2 + 8);
        memset(pv, 0, sizeof(pv));
        pt = 0;
        x1 = 0;
        DC = CDevDesc::GetDC((CDevDesc *)(v8 + 16));
        v10 = DC;
        if ( DC )
        {
          CompatibleDC = CreateCompatibleDC(DC);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            SelectObject(CompatibleDC, *((HGDIOBJ *)v4 + 1));
            MapMode = GetMapMode(v10);
            SetMapMode(hdcSrc, MapMode);
            if ( GetObjectA(*((HANDLE *)v4 + 1), 32, pv) )
            {
              pt = *(struct tagPOINT *)((char *)pv + 4);
              DPtoLP(v10, &pt, 1);
              x1 = 0;
              DPtoLP(hdcSrc, &x1, 1);
              BitBlt(
                v10,
                *((_DWORD *)v4 + 4) + ~(pt.x >> 1),
                *((_DWORD *)v4 + 5) - (pt.y >> 1) + 1,
                pt.x,
                pt.y,
                hdcSrc,
                x1.x,
                x1.y,
                0x990066u);
              *(_WORD *)v4 = *(_WORD *)v4 & 0xFFFE | v6 ^ 1;
            }
            DeleteDC(hdcSrc);
          }
          CDevDesc::ReleaseDC((CDevDesc *)(v8 + 16), v10);
        }
      }
      a2 = (struct CTxtEdit *)*((_QWORD *)this + 2);
    }
    else
    {
      v5 = 0;
    }
  }
  *(_DWORD *)this = v5;
  *((_WORD *)a2 + 12) &= ~1u;
  return this;
}

```

## disassembly

```asm
0x18003b054  mov     [rsp-38h+arg_10], rbx
0x18003b059  push    rbp
0x18003b05a  push    rsi
0x18003b05b  push    rdi
0x18003b05c  push    r12
0x18003b05e  push    r13
0x18003b060  push    r14
0x18003b062  push    r15
0x18003b064  mov     rbp, rsp
0x18003b067  sub     rsp, 70h
0x18003b06b  xor     r15d, r15d
0x18003b06e  mov     [rcx+8], r8
0x18003b072  mov     [rcx+10h], rdx
0x18003b076  mov     rdi, rcx
0x18003b079  lea     rbx, [rdx+18h]
0x18003b07d  mov     eax, 0FFFEh
0x18003b082  mov     esi, 1
0x18003b087  test    r8, r8
0x18003b08a  jz      short loc_18003B091
0x18003b08c  test    [rbx], sil
0x18003b08f  jnz     short loc_18003B09D
0x18003b091  movzx   r12d, word ptr [rbx]
0x18003b095  and     r12d, esi
0x18003b098  jnz     short loc_18003B0BE
0x18003b09a  mov     esi, r15d
0x18003b09d  mov     rbx, [rsp+70h+arg_10]
0x18003b0a5  mov     [rdi], esi
0x18003b0a7  and     [rdx+18h], ax
0x18003b0ab  mov     rax, rdi
0x18003b0ae  add     rsp, 70h
0x18003b0b2  pop     r15
0x18003b0b4  pop     r14
0x18003b0b6  pop     r13
0x18003b0b8  pop     r12
0x18003b0ba  pop     rdi
0x18003b0bb  pop     rsi
0x18003b0bc  pop     rbp
0x18003b0bd  retn
0x18003b0be  cmp     [rbx+8], r15
0x18003b0c2  jz      loc_18003B1F1
0x18003b0c8  mov     r13, [rdx+40h]
0x18003b0cc  xorps   xmm0, xmm0
0x18003b0cf  movups  [rbp+pv], xmm0
0x18003b0d3  mov     qword ptr [rbp+pt.x], r15
0x18003b0d7  movups  [rbp+var_10], xmm0
0x18003b0db  lea     rcx, [r13+10h]; this
0x18003b0df  mov     qword ptr [rbp+arg_8.x], r15
0x18003b0e3  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18003b0e8  mov     r14, rax
0x18003b0eb  test    rax, rax
0x18003b0ee  jz      loc_18003B1EC
0x18003b0f4  mov     rcx, rax; hdc
0x18003b0f7  call    cs:__imp_CreateCompatibleDC
0x18003b0fd  mov     r15, rax
0x18003b100  test    rax, rax
0x18003b103  jz      loc_18003B1E0
0x18003b109  mov     rdx, [rbx+8]; h
0x18003b10d  mov     rcx, rax; hdc
0x18003b110  call    cs:__imp_SelectObject
0x18003b116  mov     rcx, r14; hdc
0x18003b119  call    cs:__imp_GetMapMode
0x18003b11f  mov     edx, eax; iMode
0x18003b121  mov     rcx, r15; hdc
0x18003b124  call    cs:__imp_SetMapMode
0x18003b12a  mov     rcx, [rbx+8]; h
0x18003b12e  lea     r8, [rbp+pv]; pv
0x18003b132  mov     edx, 20h ; ' '; c
0x18003b137  call    cs:__imp_GetObjectA
0x18003b13d  test    eax, eax
0x18003b13f  jz      loc_18003B1D7
0x18003b145  mov     eax, dword ptr [rbp+pv+4]
0x18003b148  lea     rdx, [rbp+pt]; lppt
0x18003b14c  mov     [rbp+pt.x], eax
0x18003b14f  mov     r8d, esi; c
0x18003b152  mov     eax, dword ptr [rbp+pv+8]
0x18003b155  mov     rcx, r14; hdc
0x18003b158  mov     [rbp+pt.y], eax
0x18003b15b  call    cs:__imp_DPtoLP
0x18003b161  mov     r8d, esi; c
0x18003b164  mov     qword ptr [rbp+arg_8.x], 0
0x18003b16c  lea     rdx, [rbp+arg_8]; lppt
0x18003b170  mov     rcx, r15; hdc
0x18003b173  call    cs:__imp_DPtoLP
0x18003b179  mov     ecx, [rbp+pt.y]
0x18003b17c  mov     eax, ecx
0x18003b17e  mov     r8d, [rbx+14h]
0x18003b182  mov     r9d, [rbp+pt.x]; cx
0x18003b186  mov     edx, r9d
0x18003b189  sar     eax, 1
0x18003b18b  sub     r8d, eax
0x18003b18e  mov     [rsp+70h+rop], 990066h; rop
0x18003b196  mov     eax, [rbp+arg_8.y]
0x18003b199  add     r8d, esi; y
0x18003b19c  mov     [rsp+70h+y1], eax; y1
0x18003b1a0  mov     eax, [rbp+arg_8.x]
0x18003b1a3  sar     edx, 1
0x18003b1a5  mov     [rsp+70h+x1], eax; x1
0x18003b1a9  not     edx
0x18003b1ab  add     edx, [rbx+10h]; x
0x18003b1ae  mov     [rsp+70h+hdcSrc], r15; hdcSrc
0x18003b1b3  mov     [rsp+70h+cy], ecx; cy
0x18003b1b7  mov     rcx, r14; hdc
0x18003b1ba  call    cs:__imp_BitBlt
0x18003b1c0  movzx   eax, word ptr [rbx]
0x18003b1c3  mov     ecx, 0FFFEh
0x18003b1c8  and     ax, cx
0x18003b1cb  xor     r12w, si
0x18003b1cf  or      r12w, ax
0x18003b1d3  mov     [rbx], r12w
0x18003b1d7  mov     rcx, r15; hdc
0x18003b1da  call    cs:__imp_DeleteDC
0x18003b1e0  mov     rdx, r14; HDC
0x18003b1e3  lea     rcx, [r13+10h]; this
0x18003b1e7  call    ?ReleaseDC@CDevDesc@@QEBAXPEAUHDC__@@@Z; CDevDesc::ReleaseDC(HDC__ *)
0x18003b1ec  mov     eax, 0FFFEh
0x18003b1f1  mov     rdx, [rdi+10h]
0x18003b1f5  jmp     loc_18003B09D
```
