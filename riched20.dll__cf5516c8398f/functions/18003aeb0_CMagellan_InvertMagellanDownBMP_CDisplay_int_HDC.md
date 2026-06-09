# CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)

- ea: `0x18003aeb0`
- end: `0x18003b04b`
- name: `?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z`
- size: `411`
- prototype: `int(CMagellan *__hidden this, struct CDisplay *, int, HDC)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e200`
- `0x18003ad78`
- `0x18005ed34`
- `0x18006e61c`
- `0x180082420`

## callees

- `0x18003aeb0`
- `0x18003e5c8`
- `0x18003f3d8`

## import_xrefs

- `GDI32!BitBlt` at `0x18003b007`
- `GDI32!BitBlt` at `0x18003b007`
- `GDI32!DeleteDC` at `0x18003b02c`
- `GDI32!DeleteDC` at `0x18003b02c`
- `GDI32!CreateCompatibleDC` at `0x18003af3e`
- `GDI32!CreateCompatibleDC` at `0x18003af3e`
- `GDI32!SelectObject` at `0x18003af57`
- `GDI32!SelectObject` at `0x18003af57`
- `GDI32!DPtoLP` at `0x18003afa5`
- `GDI32!DPtoLP` at `0x18003afc0`
- `GDI32!DPtoLP` at `0x18003afa5`
- `GDI32!DPtoLP` at `0x18003afc0`
- `GDI32!GetMapMode` at `0x18003af60`
- `GDI32!GetMapMode` at `0x18003af60`
- `GDI32!SetMapMode` at `0x18003af6b`
- `GDI32!SetMapMode` at `0x18003af6b`
- `GDI32!GetObjectA` at `0x18003af7e`
- `GDI32!GetObjectA` at `0x18003af7e`

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
  struct tagPOINT pt; // [rsp+B0h] [rbp+30h] BYREF

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
        pt = *(struct tagPOINT *)((char *)pv + 4);
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
0x18003aeb0  mov     [rsp-28h+arg_8], rbx
0x18003aeb5  mov     [rsp-28h+arg_10], rsi
0x18003aeba  push    rbp
0x18003aebb  push    rdi
0x18003aebc  push    r12
0x18003aebe  push    r14
0x18003aec0  push    r15
0x18003aec2  mov     rbp, rsp
0x18003aec5  sub     rsp, 80h
0x18003aecc  movzx   edi, word ptr [rcx]
0x18003aecf  mov     r15, r9
0x18003aed2  and     edi, 1
0x18003aed5  mov     rsi, rcx
0x18003aed8  cmp     edi, r8d
0x18003aedb  jnz     short loc_18003AEFB
0x18003aedd  lea     r11, [rsp+80h+var_s0]
0x18003aee5  mov     eax, edi
0x18003aee7  mov     rbx, [r11+38h]
0x18003aeeb  mov     rsi, [r11+40h]
0x18003aeef  mov     rsp, r11
0x18003aef2  pop     r15
0x18003aef4  pop     r14
0x18003aef6  pop     r12
0x18003aef8  pop     rdi
0x18003aef9  pop     rbp
0x18003aefa  retn
0x18003aefb  cmp     qword ptr [rcx+8], 0
0x18003af00  jz      short loc_18003AEDD
0x18003af02  mov     qword ptr [rbp+pt.x], 0
0x18003af0a  xorps   xmm0, xmm0
0x18003af0d  mov     qword ptr [rbp+var_30.x], 0
0x18003af15  lea     r12, [rdx+10h]
0x18003af19  movups  [rbp+pv], xmm0
0x18003af1d  movups  [rbp+var_18], xmm0
0x18003af21  test    r15, r15
0x18003af24  jz      short loc_18003AF2B
0x18003af26  mov     rbx, r15
0x18003af29  jmp     short loc_18003AF3B
0x18003af2b  mov     rcx, r12; this
0x18003af2e  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18003af33  mov     rbx, rax
0x18003af36  test    rax, rax
0x18003af39  jz      short loc_18003AEDD
0x18003af3b  mov     rcx, rbx; hdc
0x18003af3e  call    cs:__imp_CreateCompatibleDC
0x18003af44  mov     r14, rax
0x18003af47  test    rax, rax
0x18003af4a  jz      loc_18003B032
0x18003af50  mov     rdx, [rsi+8]; h
0x18003af54  mov     rcx, rax; hdc
0x18003af57  call    cs:__imp_SelectObject
0x18003af5d  mov     rcx, rbx; hdc
0x18003af60  call    cs:__imp_GetMapMode
0x18003af66  mov     edx, eax; iMode
0x18003af68  mov     rcx, r14; hdc
0x18003af6b  call    cs:__imp_SetMapMode
0x18003af71  mov     rcx, [rsi+8]; h
0x18003af75  lea     r8, [rbp+pv]; pv
0x18003af79  mov     edx, 20h ; ' '; c
0x18003af7e  call    cs:__imp_GetObjectA
0x18003af84  test    eax, eax
0x18003af86  jz      loc_18003B029
0x18003af8c  mov     eax, dword ptr [rbp+pv+4]
0x18003af8f  lea     rdx, [rbp+pt]; lppt
0x18003af93  mov     [rbp+pt.x], eax
0x18003af96  mov     r8d, 1; c
0x18003af9c  mov     eax, dword ptr [rbp+pv+8]
0x18003af9f  mov     rcx, rbx; hdc
0x18003afa2  mov     [rbp+pt.y], eax
0x18003afa5  call    cs:__imp_DPtoLP
0x18003afab  mov     r8d, 1; c
0x18003afb1  mov     qword ptr [rbp+var_30.x], 0
0x18003afb9  lea     rdx, [rbp+var_30]; lppt
0x18003afbd  mov     rcx, r14; hdc
0x18003afc0  call    cs:__imp_DPtoLP
0x18003afc6  mov     ecx, [rbp+pt.y]
0x18003afc9  mov     eax, ecx
0x18003afcb  mov     r8d, [rsi+14h]
0x18003afcf  mov     r9d, [rbp+pt.x]; cx
0x18003afd3  mov     edx, r9d
0x18003afd6  sar     eax, 1
0x18003afd8  sub     r8d, eax
0x18003afdb  mov     [rsp+80h+rop], 990066h; rop
0x18003afe3  mov     eax, [rbp+var_30.y]
0x18003afe6  inc     r8d; y
0x18003afe9  mov     [rsp+80h+y1], eax; y1
0x18003afed  mov     eax, [rbp+var_30.x]
0x18003aff0  sar     edx, 1
0x18003aff2  mov     [rsp+80h+x1], eax; x1
0x18003aff6  not     edx
0x18003aff8  add     edx, [rsi+10h]; x
0x18003affb  mov     [rsp+80h+hdcSrc], r14; hdcSrc
0x18003b000  mov     [rsp+80h+cy], ecx; cy
0x18003b004  mov     rcx, rbx; hdc
0x18003b007  call    cs:__imp_BitBlt
0x18003b00d  movzx   eax, word ptr [rsi]
0x18003b010  movzx   r8d, di
0x18003b014  mov     ecx, 0FFFEh
0x18003b019  xor     r8w, 1
0x18003b01e  and     ax, cx
0x18003b021  or      r8w, ax
0x18003b025  mov     [rsi], r8w
0x18003b029  mov     rcx, r14; hdc
0x18003b02c  call    cs:__imp_DeleteDC
0x18003b032  test    r15, r15
0x18003b035  jnz     loc_18003AEDD
0x18003b03b  mov     rdx, rbx; HDC
0x18003b03e  mov     rcx, r12; this
0x18003b041  call    ?ReleaseDC@CDevDesc@@QEBAXPEAUHDC__@@@Z; CDevDesc::ReleaseDC(HDC__ *)
0x18003b046  jmp     loc_18003AEDD
```
