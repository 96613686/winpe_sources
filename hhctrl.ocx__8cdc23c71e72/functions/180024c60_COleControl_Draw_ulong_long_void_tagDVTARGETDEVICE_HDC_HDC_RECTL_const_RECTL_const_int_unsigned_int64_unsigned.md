# COleControl::Draw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,int (*)(unsigned __int64),unsigned __int64)

- ea: `0x180024c60`
- end: `0x180024e57`
- name: `?Draw@COleControl@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3P6AH_K@Z4@Z`
- size: `503`
- prototype: `__int64 __fastcall(COleControl *__hidden this, unsigned int, int, void *, struct tagDVTARGETDEVICE *, HDC, HDC hdc, const struct _RECTL *, const struct _RECTL *, int (*)(unsigned __int64), unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180024c60`
- `0x18002517c`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `GDI32!SetMapMode` at `0x180024dad`
- `GDI32!SetMapMode` at `0x180024e49`
- `GDI32!SetMapMode` at `0x180024dad`
- `GDI32!SetMapMode` at `0x180024e49`
- `GDI32!DeleteDC` at `0x180024dbc`
- `GDI32!DeleteDC` at `0x180024dbc`
- `GDI32!GetDeviceCaps` at `0x180024cf2`
- `GDI32!GetDeviceCaps` at `0x180024cf2`
- `GDI32!LPtoDP` at `0x180024e17`
- `GDI32!LPtoDP` at `0x180024e17`
- `GDI32!SetViewportOrgEx` at `0x180024d8e`
- `GDI32!SetViewportOrgEx` at `0x180024e29`
- `GDI32!SetViewportOrgEx` at `0x180024d8e`
- `GDI32!SetViewportOrgEx` at `0x180024e29`
- `GDI32!SetWindowOrgEx` at `0x180024da1`
- `GDI32!SetWindowOrgEx` at `0x180024e3b`
- `GDI32!SetWindowOrgEx` at `0x180024da1`
- `GDI32!SetWindowOrgEx` at `0x180024e3b`

## pseudocode

```c
__int64 __fastcall COleControl::Draw(
        COleControl *this,
        unsigned int a2,
        __int64 a3,
        _BYTE *a4,
        struct tagDVTARGETDEVICE *a5,
        HDC a6,
        HDC hdc,
        const struct _RECTL *a8,
        const struct _RECTL *a9)
{
  HDC OleDC; // rdi
  int v13; // r14d
  char v14; // r12
  int v15; // r12d
  unsigned int v16; // esi
  char v17; // [rsp+40h] [rbp-49h]
  int x[2]; // [rsp+50h] [rbp-39h] BYREF
  int y[2]; // [rsp+58h] [rbp-31h] BYREF
  struct tagDVTARGETDEVICE *v21; // [rsp+60h] [rbp-29h]
  const struct _RECTL *v22; // [rsp+68h] [rbp-21h]
  struct tagPOINT pt[2]; // [rsp+70h] [rbp-19h] BYREF

  OleDC = a6;
  v21 = a5;
  v22 = a9;
  *(_QWORD *)x = 0;
  *(_QWORD *)y = 0;
  *(_OWORD *)&pt[0].x = 0;
  if ( a2 != 1 && a2 != 16 && a2 != 32 )
    return 2147745899LL;
  v13 = 0;
  v14 = 0;
  v17 = 0;
  if ( GetDeviceCaps(hdc, 2) == 5 )
  {
    v14 = 1;
    if ( !a6 )
    {
      OleDC = _CreateOleDC(v21);
      v17 = 1;
    }
  }
  if ( a4 && *(_DWORD *)a4 == 8 )
    v13 = a4[4] & 1;
  if ( (*((_BYTE *)this + 168) & 2) != 0 )
  {
    *(_OWORD *)&pt[0].x = *((_OWORD *)this + 8);
  }
  else
  {
    if ( !a8 )
      return 2147745805LL;
    *(struct _RECTL *)&pt[0].x = *a8;
    if ( !v14 )
    {
      LPtoDP(hdc, pt, 2);
      SetViewportOrgEx(hdc, 0, 0, (LPPOINT)x);
      SetWindowOrgEx(hdc, 0, 0, (LPPOINT)y);
      v15 = SetMapMode(hdc, 1);
      goto LABEL_14;
    }
  }
  v15 = 0;
LABEL_14:
  v16 = (*(__int64 (__fastcall **)(char *, _QWORD, HDC, struct tagPOINT *, const struct _RECTL *, HDC, int))(*((_QWORD *)this - 10) + 88LL))(
          (char *)this - 80,
          a2,
          hdc,
          pt,
          v22,
          OleDC,
          v13);
  if ( (*((_BYTE *)this + 168) & 2) == 0 )
  {
    SetViewportOrgEx(hdc, x[0], x[1], 0);
    SetWindowOrgEx(hdc, y[0], y[1], 0);
    SetMapMode(hdc, v15);
  }
  if ( v17 )
    DeleteDC(OleDC);
  return v16;
}

```

## disassembly

```asm
0x180024c60  mov     [rsp-8+arg_10], rbx
0x180024c65  push    rbp
0x180024c66  push    rsi
0x180024c67  push    rdi
0x180024c68  push    r12
0x180024c6a  push    r13
0x180024c6c  push    r14
0x180024c6e  push    r15
0x180024c70  lea     rbp, [rsp-7]
0x180024c75  sub     rsp, 90h
0x180024c7c  mov     rax, cs:__security_cookie
0x180024c83  xor     rax, rsp
0x180024c86  mov     [rbp+37h+var_40], rax
0x180024c8a  mov     rax, [rbp+37h+arg_20]
0x180024c8e  mov     r15, rcx
0x180024c91  mov     rdi, [rbp+37h+arg_28]
0x180024c95  xor     ecx, ecx
0x180024c97  mov     rbx, [rbp+37h+hdc]
0x180024c9b  xorps   xmm0, xmm0
0x180024c9e  mov     r13, [rbp+37h+arg_38]
0x180024ca2  mov     rsi, r9
0x180024ca5  mov     [rbp+37h+var_60], rax
0x180024ca9  mov     rax, [rbp+37h+arg_40]
0x180024cb0  mov     [rbp+37h+var_58], rax
0x180024cb4  mov     eax, edx
0x180024cb6  mov     [rbp+37h+var_78], edx
0x180024cb9  mov     qword ptr [rbp+37h+x], rcx
0x180024cbd  mov     qword ptr [rbp+37h+y], rcx
0x180024cc1  movups  xmmword ptr [rbp+37h+pt.x], xmm0
0x180024cc5  sub     eax, 1
0x180024cc8  jz      short loc_180024CDE
0x180024cca  sub     eax, 0Fh
0x180024ccd  jz      short loc_180024CDE
0x180024ccf  cmp     eax, 10h
0x180024cd2  jz      short loc_180024CDE
0x180024cd4  mov     eax, 8004006Bh
0x180024cd9  jmp     loc_180024DC4
0x180024cde  mov     r14d, ecx
0x180024ce1  mov     [rbp+37h+iMode], ecx
0x180024ce4  mov     r12b, cl
0x180024ce7  mov     [rbp+37h+var_80], cl
0x180024cea  mov     rcx, rbx; hdc
0x180024ced  mov     edx, 2; index
0x180024cf2  call    cs:__imp_GetDeviceCaps
0x180024cf8  cmp     eax, 5
0x180024cfb  jnz     short loc_180024D15
0x180024cfd  mov     r12b, 1
0x180024d00  test    rdi, rdi
0x180024d03  jnz     short loc_180024D15
0x180024d05  mov     rcx, [rbp+37h+var_60]; struct tagDVTARGETDEVICE *
0x180024d09  call    ?_CreateOleDC@@YAPEAUHDC__@@PEAUtagDVTARGETDEVICE@@@Z; _CreateOleDC(tagDVTARGETDEVICE *)
0x180024d0e  mov     rdi, rax
0x180024d11  mov     [rbp+37h+var_80], r12b
0x180024d15  test    rsi, rsi
0x180024d18  jz      short loc_180024D28
0x180024d1a  cmp     dword ptr [rsi], 8
0x180024d1d  jnz     short loc_180024D28
0x180024d1f  movzx   r14d, byte ptr [rsi+4]
0x180024d24  and     r14d, 1
0x180024d28  test    byte ptr [r15+0A8h], 2
0x180024d30  jz      loc_180024DEB
0x180024d36  movups  xmm0, xmmword ptr [r15+80h]
0x180024d3e  movdqu  xmmword ptr [rbp+37h+pt.x], xmm0
0x180024d43  mov     r12d, [rbp+37h+iMode]
0x180024d47  mov     r8, [r15-50h]
0x180024d4b  lea     r9, [rbp+37h+pt]
0x180024d4f  mov     rcx, [rbp+37h+var_58]
0x180024d53  mov     edx, [rbp+37h+var_78]
0x180024d56  mov     [rsp+0C0h+var_90], r14d
0x180024d5b  mov     rax, [r8+58h]
0x180024d5f  mov     r8, rbx
0x180024d62  mov     [rsp+0C0h+var_98], rdi
0x180024d67  mov     [rsp+0C0h+var_A0], rcx
0x180024d6c  lea     rcx, [r15-50h]
0x180024d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d75  test    byte ptr [r15+0A8h], 2
0x180024d7d  mov     esi, eax
0x180024d7f  jnz     short loc_180024DB3
0x180024d81  mov     r8d, [rbp+37h+x+4]; y
0x180024d85  xor     r9d, r9d; lppt
0x180024d88  mov     edx, [rbp+37h+x]; x
0x180024d8b  mov     rcx, rbx; hdc
0x180024d8e  call    cs:__imp_SetViewportOrgEx
0x180024d94  mov     r8d, [rbp+37h+y+4]; y
0x180024d98  xor     r9d, r9d; lppt
0x180024d9b  mov     edx, [rbp+37h+y]; x
0x180024d9e  mov     rcx, rbx; hdc
0x180024da1  call    cs:__imp_SetWindowOrgEx
0x180024da7  mov     edx, r12d; iMode
0x180024daa  mov     rcx, rbx; hdc
0x180024dad  call    cs:__imp_SetMapMode
0x180024db3  cmp     [rbp+37h+var_80], 0
0x180024db7  jz      short loc_180024DC2
0x180024db9  mov     rcx, rdi; hdc
0x180024dbc  call    cs:__imp_DeleteDC
0x180024dc2  mov     eax, esi
0x180024dc4  mov     rcx, [rbp+37h+var_40]
0x180024dc8  xor     rcx, rsp; StackCookie
0x180024dcb  call    __security_check_cookie
0x180024dd0  mov     rbx, [rsp+0C0h+arg_10]
0x180024dd8  add     rsp, 90h
0x180024ddf  pop     r15
0x180024de1  pop     r14
0x180024de3  pop     r13
0x180024de5  pop     r12
0x180024de7  pop     rdi
0x180024de8  pop     rsi
0x180024de9  pop     rbp
0x180024dea  retn
0x180024deb  test    r13, r13
0x180024dee  jnz     short loc_180024DF7
0x180024df0  mov     eax, 8004000Dh
0x180024df5  jmp     short loc_180024DC4
0x180024df7  movups  xmm0, xmmword ptr [r13+0]
0x180024dfc  movdqu  xmmword ptr [rbp+37h+pt.x], xmm0
0x180024e01  test    r12b, r12b
0x180024e04  jnz     loc_180024D43
0x180024e0a  mov     r8d, 2; c
0x180024e10  lea     rdx, [rbp+37h+pt]; lppt
0x180024e14  mov     rcx, rbx; hdc
0x180024e17  call    cs:__imp_LPtoDP
0x180024e1d  lea     r9, [rbp+37h+x]; lppt
0x180024e21  xor     r8d, r8d; y
0x180024e24  xor     edx, edx; x
0x180024e26  mov     rcx, rbx; hdc
0x180024e29  call    cs:__imp_SetViewportOrgEx
0x180024e2f  lea     r9, [rbp+37h+y]; lppt
0x180024e33  xor     r8d, r8d; y
0x180024e36  xor     edx, edx; x
0x180024e38  mov     rcx, rbx; hdc
0x180024e3b  call    cs:__imp_SetWindowOrgEx
0x180024e41  mov     edx, 1; iMode
0x180024e46  mov     rcx, rbx; hdc
0x180024e49  call    cs:__imp_SetMapMode
0x180024e4f  mov     r12d, eax
0x180024e52  jmp     loc_180024D47
```
