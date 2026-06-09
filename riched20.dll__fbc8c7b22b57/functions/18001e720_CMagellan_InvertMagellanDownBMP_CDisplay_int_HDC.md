# CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)

- ea: `0x18001e720`
- end: `0x18001e8f2`
- name: `?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z`
- size: `466`
- prototype: `int(CMagellan *__hidden this, struct CDisplay *, int, HDC)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e5e4`
- `0x1800200d0`
- `0x180060458`
- `0x180070470`
- `0x180084910`

## callees

- `0x18001e720`
- `0x18003f11c`
- `0x18003ff34`

## import_xrefs

- `GDI32!BitBlt` at `0x18001e8a2`
- `GDI32!BitBlt` at `0x18001e8a2`
- `GDI32!DeleteDC` at `0x18001e8cd`
- `GDI32!DeleteDC` at `0x18001e8cd`
- `GDI32!CreateCompatibleDC` at `0x18001e7af`
- `GDI32!CreateCompatibleDC` at `0x18001e7af`
- `GDI32!SelectObject` at `0x18001e7ce`
- `GDI32!SelectObject` at `0x18001e7ce`
- `GDI32!DPtoLP` at `0x18001e834`
- `GDI32!DPtoLP` at `0x18001e855`
- `GDI32!DPtoLP` at `0x18001e834`
- `GDI32!DPtoLP` at `0x18001e855`
- `GDI32!GetMapMode` at `0x18001e7dd`
- `GDI32!GetMapMode` at `0x18001e7dd`
- `GDI32!SetMapMode` at `0x18001e7ee`
- `GDI32!SetMapMode` at `0x18001e7ee`
- `GDI32!GetObjectA` at `0x18001e807`
- `GDI32!GetObjectA` at `0x18001e807`

## pseudocode

```c
__int64 __fastcall CMagellan::InvertMagellanDownBMP(HGDIOBJ *this, struct CDisplay *a2, int a3, HDC a4)
{
  unsigned int v5; // edi
  CDevDesc *v8; // r12
  HDC DC; // rbx
  HDC CompatibleDC; // rax
  HDC hdcSrc; // r14
  int MapMode; // eax
  struct tagPOINT x1; // [rsp+50h] [rbp-30h] BYREF
  _OWORD pv[2]; // [rsp+58h] [rbp-28h] BYREF
  tagPOINT pt; // [rsp+B0h] [rbp+30h] BYREF

  v5 = *(_WORD *)this & 1;
  if ( v5 != a3 && this[1] )
  {
    pt = 0;
    x1 = 0;
    v8 = (struct CDisplay *)((char *)a2 + 16);
    memset(pv, 0, sizeof(pv));
    if ( a4 )
    {
      DC = a4;
    }
    else
    {
      DC = CDevDesc::GetDC((struct CDisplay *)((char *)a2 + 16));
      if ( !DC )
        return v5;
    }
    CompatibleDC = CreateCompatibleDC(DC);
    hdcSrc = CompatibleDC;
    if ( CompatibleDC )
    {
      SelectObject(CompatibleDC, this[1]);
      MapMode = GetMapMode(DC);
      SetMapMode(hdcSrc, MapMode);
      if ( GetObjectA(this[1], 32, pv) )
      {
        pt = *(tagPOINT *)((char *)pv + 4);
        DPtoLP(DC, &pt, 1);
        x1 = 0;
        DPtoLP(hdcSrc, &x1, 1);
        BitBlt(
          DC,
          *((_DWORD *)this + 4) + ~(pt.x >> 1),
          *((_DWORD *)this + 5) - (pt.y >> 1) + 1,
          pt.x,
          pt.y,
          hdcSrc,
          x1.x,
          x1.y,
          0x990066u);
        *(_WORD *)this = *(_WORD *)this & 0xFFFE | v5 ^ 1;
      }
      DeleteDC(hdcSrc);
    }
    if ( !a4 )
      CDevDesc::ReleaseDC(v8, DC);
  }
  return v5;
}

```

## disassembly

```asm
0x18001e720  mov     [rsp-28h+arg_8], rbx
0x18001e725  mov     [rsp-28h+arg_10], rsi
0x18001e72a  push    rbp
0x18001e72b  push    rdi
0x18001e72c  push    r12
0x18001e72e  push    r14
0x18001e730  push    r15
0x18001e732  mov     rbp, rsp
0x18001e735  sub     rsp, 80h
0x18001e73c  movzx   edi, word ptr [rcx]
0x18001e73f  mov     r15, r9
0x18001e742  and     edi, 1
0x18001e745  mov     rsi, rcx
0x18001e748  cmp     edi, r8d
0x18001e74b  jnz     short loc_18001E76C
0x18001e74d  lea     r11, [rsp+80h+var_s0]
0x18001e755  mov     eax, edi
0x18001e757  mov     rbx, [r11+38h]
0x18001e75b  mov     rsi, [r11+40h]
0x18001e75f  mov     rsp, r11
0x18001e762  pop     r15
0x18001e764  pop     r14
0x18001e766  pop     r12
0x18001e768  pop     rdi
0x18001e769  pop     rbp
0x18001e76a  retn
0x18001e76c  cmp     qword ptr [rcx+8], 0
0x18001e771  jz      short loc_18001E74D
0x18001e773  mov     qword ptr [rbp+pt.x], 0
0x18001e77b  xorps   xmm0, xmm0
0x18001e77e  mov     qword ptr [rbp+var_30.x], 0
0x18001e786  lea     r12, [rdx+10h]
0x18001e78a  movups  [rbp+pv], xmm0
0x18001e78e  movups  [rbp+var_18], xmm0
0x18001e792  test    r15, r15
0x18001e795  jz      short loc_18001E79C
0x18001e797  mov     rbx, r15
0x18001e79a  jmp     short loc_18001E7AC
0x18001e79c  mov     rcx, r12; this
0x18001e79f  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18001e7a4  mov     rbx, rax
0x18001e7a7  test    rax, rax
0x18001e7aa  jz      short loc_18001E74D
0x18001e7ac  mov     rcx, rbx; hdc
0x18001e7af  call    cs:__imp_CreateCompatibleDC
0x18001e7b6  nop     dword ptr [rax+rax+00h]
0x18001e7bb  mov     r14, rax
0x18001e7be  test    rax, rax
0x18001e7c1  jz      loc_18001E8D9
0x18001e7c7  mov     rdx, [rsi+8]; h
0x18001e7cb  mov     rcx, rax; hdc
0x18001e7ce  call    cs:__imp_SelectObject
0x18001e7d5  nop     dword ptr [rax+rax+00h]
0x18001e7da  mov     rcx, rbx; hdc
0x18001e7dd  call    cs:__imp_GetMapMode
0x18001e7e4  nop     dword ptr [rax+rax+00h]
0x18001e7e9  mov     edx, eax; iMode
0x18001e7eb  mov     rcx, r14; hdc
0x18001e7ee  call    cs:__imp_SetMapMode
0x18001e7f5  nop     dword ptr [rax+rax+00h]
0x18001e7fa  mov     rcx, [rsi+8]; h
0x18001e7fe  lea     r8, [rbp+pv]; pv
0x18001e802  mov     edx, 20h ; ' '; c
0x18001e807  call    cs:__imp_GetObjectA
0x18001e80e  nop     dword ptr [rax+rax+00h]
0x18001e813  test    eax, eax
0x18001e815  jz      loc_18001E8CA
0x18001e81b  mov     eax, dword ptr [rbp+pv+4]
0x18001e81e  lea     rdx, [rbp+pt]; lppt
0x18001e822  mov     [rbp+pt.x], eax
0x18001e825  mov     r8d, 1; c
0x18001e82b  mov     eax, dword ptr [rbp+pv+8]
0x18001e82e  mov     rcx, rbx; hdc
0x18001e831  mov     [rbp+pt.y], eax
0x18001e834  call    cs:__imp_DPtoLP
0x18001e83b  nop     dword ptr [rax+rax+00h]
0x18001e840  mov     r8d, 1; c
0x18001e846  mov     qword ptr [rbp+var_30.x], 0
0x18001e84e  lea     rdx, [rbp+var_30]; lppt
0x18001e852  mov     rcx, r14; hdc
0x18001e855  call    cs:__imp_DPtoLP
0x18001e85c  nop     dword ptr [rax+rax+00h]
0x18001e861  mov     ecx, [rbp+pt.y]
0x18001e864  mov     eax, ecx
0x18001e866  mov     r8d, [rsi+14h]
0x18001e86a  mov     r9d, [rbp+pt.x]; cx
0x18001e86e  mov     edx, r9d
0x18001e871  sar     eax, 1
0x18001e873  sub     r8d, eax
0x18001e876  mov     [rsp+80h+rop], 990066h; rop
0x18001e87e  mov     eax, [rbp+var_30.y]
0x18001e881  inc     r8d; y
0x18001e884  mov     [rsp+80h+y1], eax; y1
0x18001e888  mov     eax, [rbp+var_30.x]
0x18001e88b  sar     edx, 1
0x18001e88d  mov     [rsp+80h+x1], eax; x1
0x18001e891  not     edx
0x18001e893  add     edx, [rsi+10h]; x
0x18001e896  mov     [rsp+80h+hdcSrc], r14; hdcSrc
0x18001e89b  mov     [rsp+80h+cy], ecx; cy
0x18001e89f  mov     rcx, rbx; hdc
0x18001e8a2  call    cs:__imp_BitBlt
0x18001e8a9  nop     dword ptr [rax+rax+00h]
0x18001e8ae  movzx   eax, word ptr [rsi]
0x18001e8b1  movzx   r8d, di
0x18001e8b5  mov     ecx, 0FFFEh
0x18001e8ba  xor     r8w, 1
0x18001e8bf  and     ax, cx
0x18001e8c2  or      r8w, ax
0x18001e8c6  mov     [rsi], r8w
0x18001e8ca  mov     rcx, r14; hdc
0x18001e8cd  call    cs:__imp_DeleteDC
0x18001e8d4  nop     dword ptr [rax+rax+00h]
0x18001e8d9  test    r15, r15
0x18001e8dc  jnz     loc_18001E74D
0x18001e8e2  mov     rdx, rbx; HDC
0x18001e8e5  mov     rcx, r12; this
0x18001e8e8  call    ?ReleaseDC@CDevDesc@@QEBAXPEAUHDC__@@@Z; CDevDesc::ReleaseDC(HDC__ *)
0x18001e8ed  jmp     loc_18001E74D
```
