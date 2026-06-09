# CTxtEdit::RectChangeHelper(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,tagRECT const * *,tagRECT *)

- ea: `0x18003f37c`
- end: `0x18003f579`
- name: `?RectChangeHelper@CTxtEdit@@QEAAJPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@3PEAPEBUtagRECT@@PEAU5@@Z`
- size: `509`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, struct CDrawInfo *, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC hdc, HDC, const struct tagRECT **, LPPOINT lppt)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180085250`

## callees

- `0x18003b500`
- `0x18003e42c`
- `0x18003f37c`
- `0x180042f94`
- `0x180058104`
- `0x18008455c`
- `0x180095010`

## import_xrefs

- `GDI32!LPtoDP` at `0x18003f47d`
- `GDI32!LPtoDP` at `0x18003f47d`
- `GDI32!GetDeviceCaps` at `0x18003f450`
- `GDI32!GetDeviceCaps` at `0x18003f450`
- `GDI32!DeleteDC` at `0x18003f525`
- `GDI32!DeleteDC` at `0x18003f525`
- `GDI32!RestoreDC` at `0x18003f511`
- `GDI32!RestoreDC` at `0x18003f511`
- `GDI32!GetMapMode` at `0x18003f432`
- `GDI32!GetMapMode` at `0x18003f432`

## pseudocode

```c
__int64 __fastcall CTxtEdit::RectChangeHelper(
        CTxtEdit *this,
        struct CDrawInfo *a2,
        unsigned int a3,
        int a4,
        void *a5,
        struct tagDVTARGETDEVICE *a6,
        HDC hdc,
        HDC a8,
        struct tagRECT **a9,
        struct tagRECT *lppt)
{
  unsigned int v12; // r15d
  HDC v13; // r12
  HDC v14; // rdi
  HDC IC; // rax
  HDC v17; // rdx
  int v21; // [rsp+C0h] [rbp+48h]

  if ( !a9 )
    return (unsigned int)-2147024809;
  v12 = 0;
  if ( !*a9 )
  {
    if ( (*((_BYTE *)this + 180) & 8) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, struct tagRECT *))(**((_QWORD **)this + 6) + 192LL))(*((_QWORD *)this + 6), lppt);
      *a9 = lppt;
      return v12;
    }
    return (unsigned int)-2147024809;
  }
  v13 = a8;
  v14 = 0;
  if ( !a8 && a6 )
  {
    IC = CW32System::CreateIC(
           (unsigned __int16 *)((char *)a6 + a6->tdDriverNameOffset),
           (unsigned __int16 *)((char *)a6 + a6->tdDeviceNameOffset),
           (unsigned __int16 *)((char *)a6 + a6->tdPortNameOffset),
           (const struct _devicemodeW *)((char *)a6 + a6->tdExtDevmodeOffset));
    v14 = IC;
    if ( !IC )
      return 2147500037LL;
    v13 = IC;
  }
  v21 = 0;
  *lppt = **a9;
  if ( GetMapMode(hdc) != 1 && GetDeviceCaps(hdc, 2) != 5 )
  {
    v21 = 1;
    LPtoDP(hdc, (LPPOINT)lppt, 2);
    *a9 = lppt;
    ConvertDrawDCMapping(hdc);
  }
  CDevDesc::SetDC((CDevDesc *)(*((_QWORD *)this + 8) + 16LL), hdc, -1, -1);
  CDisplay::SetDrawInfo(*((CDisplay **)this + 8), a2, a3, a4, a5, a6, v13);
  CDisplay::ReDrawOnRectChange(*((CDisplay **)this + 8), v17, *a9);
  if ( v21 )
    RestoreDC(hdc, -1);
  if ( v14 )
    DeleteDC(v14);
  return v12;
}

```

## disassembly

```asm
0x18003f37c  mov     [rsp+arg_18], r9d
0x18003f381  mov     [rsp+arg_10], r8d
0x18003f386  mov     [rsp+arg_8], rdx
0x18003f38b  push    rbx
0x18003f38c  push    rsi
0x18003f38d  push    rdi
0x18003f38e  push    r12
0x18003f390  push    r13
0x18003f392  push    r14
0x18003f394  push    r15
0x18003f396  sub     rsp, 40h
0x18003f39a  mov     rsi, [rsp+78h+arg_40]
0x18003f3a2  mov     r14, rcx
0x18003f3a5  test    rsi, rsi
0x18003f3a8  jz      loc_18003F55F
0x18003f3ae  xor     r15d, r15d
0x18003f3b1  cmp     [rsi], r15
0x18003f3b4  jz      loc_18003F533
0x18003f3ba  mov     r12, [rsp+78h+arg_38]
0x18003f3c2  xor     edi, edi
0x18003f3c4  mov     rbx, [rsp+78h+arg_28]
0x18003f3cc  test    r12, r12
0x18003f3cf  jnz     short loc_18003F40E
0x18003f3d1  test    rbx, rbx
0x18003f3d4  jz      short loc_18003F40E
0x18003f3d6  movzx   r9d, word ptr [rbx+0Ah]
0x18003f3db  movzx   r8d, word ptr [rbx+8]
0x18003f3e0  add     r9, rbx; struct _devicemodeW *
0x18003f3e3  movzx   edx, word ptr [rbx+6]
0x18003f3e7  add     r8, rbx; unsigned __int16 *
0x18003f3ea  movzx   ecx, word ptr [rbx+4]
0x18003f3ee  add     rdx, rbx; unsigned __int16 *
0x18003f3f1  add     rcx, rbx; unsigned __int16 *
0x18003f3f4  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x18003f3f9  mov     rdi, rax
0x18003f3fc  test    rax, rax
0x18003f3ff  jnz     short loc_18003F40B
0x18003f401  mov     eax, 80004005h
0x18003f406  jmp     loc_18003F568
0x18003f40b  mov     r12, rax
0x18003f40e  mov     rax, [rsi]
0x18003f411  mov     r13, [rsp+78h+lppt]
0x18003f419  mov     rcx, [rsp+78h+hdc]; hdc
0x18003f421  mov     dword ptr [rsp+78h+arg_40], r15d
0x18003f429  movups  xmm0, xmmword ptr [rax]
0x18003f42c  movdqu  xmmword ptr [r13+0], xmm0
0x18003f432  call    cs:__imp_GetMapMode
0x18003f439  nop     dword ptr [rax+rax+00h]
0x18003f43e  cmp     eax, 1
0x18003f441  jz      short loc_18003F499
0x18003f443  mov     rcx, [rsp+78h+hdc]; hdc
0x18003f44b  mov     edx, 2; index
0x18003f450  call    cs:__imp_GetDeviceCaps
0x18003f457  nop     dword ptr [rax+rax+00h]
0x18003f45c  cmp     eax, 5
0x18003f45f  jz      short loc_18003F499
0x18003f461  mov     rcx, [rsp+78h+hdc]; hdc
0x18003f469  mov     r8d, 2; c
0x18003f46f  mov     rdx, r13; lppt
0x18003f472  mov     dword ptr [rsp+78h+arg_40], 1
0x18003f47d  call    cs:__imp_LPtoDP
0x18003f484  nop     dword ptr [rax+rax+00h]
0x18003f489  mov     rcx, [rsp+78h+hdc]; hdc
0x18003f491  mov     [rsi], r13
0x18003f494  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x18003f499  mov     rcx, [r14+40h]
0x18003f49d  or      r13d, 0FFFFFFFFh
0x18003f4a1  mov     rdx, [rsp+78h+hdc]; HDC
0x18003f4a9  add     rcx, 10h; this
0x18003f4ad  mov     r9d, r13d; int
0x18003f4b0  mov     r8d, r13d; int
0x18003f4b3  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x18003f4b8  mov     rax, [rsp+78h+arg_20]
0x18003f4c0  mov     r9d, [rsp+78h+arg_18]; int
0x18003f4c8  mov     r8d, [rsp+78h+arg_10]; unsigned int
0x18003f4d0  mov     rdx, [rsp+78h+arg_8]; struct CDrawInfo *
0x18003f4d8  mov     rcx, [r14+40h]; this
0x18003f4dc  mov     [rsp+78h+var_48], r12; HDC
0x18003f4e1  mov     [rsp+78h+var_50], rbx; struct tagDVTARGETDEVICE *
0x18003f4e6  mov     [rsp+78h+var_58], rax; void *
0x18003f4eb  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x18003f4f0  mov     r8, [rsi]; struct tagRECT *
0x18003f4f3  mov     rcx, [r14+40h]; this
0x18003f4f7  call    ?ReDrawOnRectChange@CDisplay@@QEAAXPEAUHDC__@@PEBUtagRECT@@@Z; CDisplay::ReDrawOnRectChange(HDC__ *,tagRECT const *)
0x18003f4fc  cmp     dword ptr [rsp+78h+arg_40], r15d
0x18003f504  jz      short loc_18003F51D
0x18003f506  mov     rcx, [rsp+78h+hdc]; hdc
0x18003f50e  mov     edx, r13d; nSavedDC
0x18003f511  call    cs:__imp_RestoreDC
0x18003f518  nop     dword ptr [rax+rax+00h]
0x18003f51d  test    rdi, rdi
0x18003f520  jz      short loc_18003F565
0x18003f522  mov     rcx, rdi; hdc
0x18003f525  call    cs:__imp_DeleteDC
0x18003f52c  nop     dword ptr [rax+rax+00h]
0x18003f531  jmp     short loc_18003F565
0x18003f533  test    byte ptr [rcx+0B4h], 8
0x18003f53a  jz      short loc_18003F55F
0x18003f53c  mov     rcx, [rcx+30h]
0x18003f540  mov     rbx, [rsp+78h+lppt]
0x18003f548  mov     rdx, rbx
0x18003f54b  mov     rax, [rcx]
0x18003f54e  mov     rax, [rax+0C0h]
0x18003f555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f55a  mov     [rsi], rbx
0x18003f55d  jmp     short loc_18003F565
0x18003f55f  mov     r15d, 80070057h
0x18003f565  mov     eax, r15d
0x18003f568  add     rsp, 40h
0x18003f56c  pop     r15
0x18003f56e  pop     r14
0x18003f570  pop     r13
0x18003f572  pop     r12
0x18003f574  pop     rdi
0x18003f575  pop     rsi
0x18003f576  pop     rbx
0x18003f577  retn
```
