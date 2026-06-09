# CTxtEdit::RectChangeHelper(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,tagRECT const * *,tagRECT *)

- ea: `0x18003e7c8`
- end: `0x18003e9a6`
- name: `?RectChangeHelper@CTxtEdit@@QEAAJPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@3PEAPEBUtagRECT@@PEAU5@@Z`
- size: `478`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, struct CDrawInfo *, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC hdc, HDC, const struct tagRECT **, LPPOINT lppt)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180082d10`

## callees

- `0x18003a4d0`
- `0x18003d61c`
- `0x18003e7c8`
- `0x1800420a4`
- `0x180056b70`
- `0x18008209c`
- `0x180092010`

## import_xrefs

- `GDI32!LPtoDP` at `0x18003e8bd`
- `GDI32!LPtoDP` at `0x18003e8bd`
- `GDI32!GetDeviceCaps` at `0x18003e896`
- `GDI32!GetDeviceCaps` at `0x18003e896`
- `GDI32!DeleteDC` at `0x18003e959`
- `GDI32!DeleteDC` at `0x18003e959`
- `GDI32!RestoreDC` at `0x18003e94b`
- `GDI32!RestoreDC` at `0x18003e94b`
- `GDI32!GetMapMode` at `0x18003e87e`
- `GDI32!GetMapMode` at `0x18003e87e`

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
0x18003e7c8  mov     [rsp+arg_18], r9d
0x18003e7cd  mov     [rsp+arg_10], r8d
0x18003e7d2  mov     [rsp+arg_8], rdx
0x18003e7d7  push    rbx
0x18003e7d8  push    rsi
0x18003e7d9  push    rdi
0x18003e7da  push    r12
0x18003e7dc  push    r13
0x18003e7de  push    r14
0x18003e7e0  push    r15
0x18003e7e2  sub     rsp, 40h
0x18003e7e6  mov     rsi, [rsp+78h+arg_40]
0x18003e7ee  mov     r14, rcx
0x18003e7f1  test    rsi, rsi
0x18003e7f4  jz      loc_18003E98D
0x18003e7fa  xor     r15d, r15d
0x18003e7fd  cmp     [rsi], r15
0x18003e800  jz      loc_18003E961
0x18003e806  mov     r12, [rsp+78h+arg_38]
0x18003e80e  xor     edi, edi
0x18003e810  mov     rbx, [rsp+78h+arg_28]
0x18003e818  test    r12, r12
0x18003e81b  jnz     short loc_18003E85A
0x18003e81d  test    rbx, rbx
0x18003e820  jz      short loc_18003E85A
0x18003e822  movzx   r9d, word ptr [rbx+0Ah]
0x18003e827  movzx   r8d, word ptr [rbx+8]
0x18003e82c  add     r9, rbx; struct _devicemodeW *
0x18003e82f  movzx   edx, word ptr [rbx+6]
0x18003e833  add     r8, rbx; unsigned __int16 *
0x18003e836  movzx   ecx, word ptr [rbx+4]
0x18003e83a  add     rdx, rbx; unsigned __int16 *
0x18003e83d  add     rcx, rbx; unsigned __int16 *
0x18003e840  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x18003e845  mov     rdi, rax
0x18003e848  test    rax, rax
0x18003e84b  jnz     short loc_18003E857
0x18003e84d  mov     eax, 80004005h
0x18003e852  jmp     loc_18003E996
0x18003e857  mov     r12, rax
0x18003e85a  mov     rax, [rsi]
0x18003e85d  mov     r13, [rsp+78h+lppt]
0x18003e865  mov     rcx, [rsp+78h+hdc]; hdc
0x18003e86d  mov     dword ptr [rsp+78h+arg_40], r15d
0x18003e875  movups  xmm0, xmmword ptr [rax]
0x18003e878  movdqu  xmmword ptr [r13+0], xmm0
0x18003e87e  call    cs:__imp_GetMapMode
0x18003e884  cmp     eax, 1
0x18003e887  jz      short loc_18003E8D3
0x18003e889  mov     rcx, [rsp+78h+hdc]; hdc
0x18003e891  mov     edx, 2; index
0x18003e896  call    cs:__imp_GetDeviceCaps
0x18003e89c  cmp     eax, 5
0x18003e89f  jz      short loc_18003E8D3
0x18003e8a1  mov     rcx, [rsp+78h+hdc]; hdc
0x18003e8a9  mov     r8d, 2; c
0x18003e8af  mov     rdx, r13; lppt
0x18003e8b2  mov     dword ptr [rsp+78h+arg_40], 1
0x18003e8bd  call    cs:__imp_LPtoDP
0x18003e8c3  mov     rcx, [rsp+78h+hdc]; hdc
0x18003e8cb  mov     [rsi], r13
0x18003e8ce  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x18003e8d3  mov     rcx, [r14+40h]
0x18003e8d7  or      r13d, 0FFFFFFFFh
0x18003e8db  mov     rdx, [rsp+78h+hdc]; HDC
0x18003e8e3  add     rcx, 10h; this
0x18003e8e7  mov     r9d, r13d; int
0x18003e8ea  mov     r8d, r13d; int
0x18003e8ed  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x18003e8f2  mov     rax, [rsp+78h+arg_20]
0x18003e8fa  mov     r9d, [rsp+78h+arg_18]; int
0x18003e902  mov     r8d, [rsp+78h+arg_10]; unsigned int
0x18003e90a  mov     rdx, [rsp+78h+arg_8]; struct CDrawInfo *
0x18003e912  mov     rcx, [r14+40h]; this
0x18003e916  mov     [rsp+78h+var_48], r12; HDC
0x18003e91b  mov     [rsp+78h+var_50], rbx; struct tagDVTARGETDEVICE *
0x18003e920  mov     [rsp+78h+var_58], rax; void *
0x18003e925  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x18003e92a  mov     r8, [rsi]; struct tagRECT *
0x18003e92d  mov     rcx, [r14+40h]; this
0x18003e931  call    ?ReDrawOnRectChange@CDisplay@@QEAAXPEAUHDC__@@PEBUtagRECT@@@Z; CDisplay::ReDrawOnRectChange(HDC__ *,tagRECT const *)
0x18003e936  cmp     dword ptr [rsp+78h+arg_40], r15d
0x18003e93e  jz      short loc_18003E951
0x18003e940  mov     rcx, [rsp+78h+hdc]; hdc
0x18003e948  mov     edx, r13d; nSavedDC
0x18003e94b  call    cs:__imp_RestoreDC
0x18003e951  test    rdi, rdi
0x18003e954  jz      short loc_18003E993
0x18003e956  mov     rcx, rdi; hdc
0x18003e959  call    cs:__imp_DeleteDC
0x18003e95f  jmp     short loc_18003E993
0x18003e961  test    byte ptr [rcx+0B4h], 8
0x18003e968  jz      short loc_18003E98D
0x18003e96a  mov     rcx, [rcx+30h]
0x18003e96e  mov     rbx, [rsp+78h+lppt]
0x18003e976  mov     rdx, rbx
0x18003e979  mov     rax, [rcx]
0x18003e97c  mov     rax, [rax+0C0h]
0x18003e983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e988  mov     [rsi], rbx
0x18003e98b  jmp     short loc_18003E993
0x18003e98d  mov     r15d, 80070057h
0x18003e993  mov     eax, r15d
0x18003e996  add     rsp, 40h
0x18003e99a  pop     r15
0x18003e99c  pop     r14
0x18003e99e  pop     r13
0x18003e9a0  pop     r12
0x18003e9a2  pop     rdi
0x18003e9a3  pop     rsi
0x18003e9a4  pop     rbx
0x18003e9a5  retn
```
