# CVidCtl::OnDrawAdvanced(ATL_DRAWINFO &)

- ea: `0x1800cd560`
- end: `0x1800cd92e`
- name: `?OnDrawAdvanced@CVidCtl@@UEAAJAEAUATL_DRAWINFO@@@Z`
- size: `974`
- prototype: `__int64 __fastcall(CVidCtl *__hidden this, struct ATL_DRAWINFO *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004640`
- `0x1800054c8`
- `0x180070aec`
- `0x1800c287c`
- `0x1800c5574`
- `0x1800c740c`
- `0x1800cb4c0`
- `0x1800cd560`
- `0x1800d2024`
- `0x1800f8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800cd7ad`
- `KERNEL32!GetLastError` at `0x1800cd7ec`
- `KERNEL32!GetLastError` at `0x1800cd8ba`
- `KERNEL32!GetLastError` at `0x1800cd7ad`
- `KERNEL32!GetLastError` at `0x1800cd7ec`
- `KERNEL32!GetLastError` at `0x1800cd8ba`
- `USER32!FillRect` at `0x1800cd7a3`
- `USER32!FillRect` at `0x1800cd7e2`
- `USER32!FillRect` at `0x1800cd8b0`
- `USER32!FillRect` at `0x1800cd7a3`
- `USER32!FillRect` at `0x1800cd7e2`
- `USER32!FillRect` at `0x1800cd8b0`
- `USER32!CopyRect` at `0x1800cd66c`
- `USER32!CopyRect` at `0x1800cd66c`
- `GDI32!CreateSolidBrush` at `0x1800cd769`
- `GDI32!CreateSolidBrush` at `0x1800cd879`
- `GDI32!CreateSolidBrush` at `0x1800cd769`
- `GDI32!CreateSolidBrush` at `0x1800cd879`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CVidCtl::OnDrawAdvanced(COLORREF *this, struct ATL_DRAWINFO *a2)
{
  bool v4; // r15
  __int64 v5; // rcx
  HDC v7; // rdi
  COLORREF v8; // r14d
  bool IsStopped; // al
  CVidCtl *v10; // rcx
  HBRUSH SolidBrush; // rax
  HBRUSH v12; // rbx
  signed int LastError; // eax
  unsigned int v14; // ebx
  signed int v15; // eax
  HBRUSH v16; // rax
  signed int v17; // eax
  _QWORD v18[2]; // [rsp+30h] [rbp-108h] BYREF
  struct tagSIZE v19; // [rsp+40h] [rbp-F8h] BYREF
  int pExceptionObject; // [rsp+48h] [rbp-F0h] BYREF
  int v21; // [rsp+4Ch] [rbp-ECh] BYREF
  struct tagRECT v22; // [rsp+58h] [rbp-E0h] BYREF
  __int128 v23; // [rsp+68h] [rbp-D0h]
  struct tagRECT rcDst; // [rsp+80h] [rbp-B8h] BYREF
  RECT v25; // [rsp+90h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-98h]
  RECT rc; // [rsp+B0h] [rbp-88h] BYREF
  char v28; // [rsp+C0h] [rbp-78h]
  __int64 v29; // [rsp+C8h] [rbp-70h]
  RECT v30; // [rsp+D0h] [rbp-68h] BYREF
  char v31; // [rsp+E0h] [rbp-58h]
  __int64 v32; // [rsp+E8h] [rbp-50h]

  CVidCtl::SetTimer((CVidCtl *)this);
  v4 = 0;
  v5 = *((_QWORD *)this + 88);
  if ( v5 )
  {
    LOWORD(v18[0]) = 0;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v5 + 176LL))(v5, v18);
    v4 = LOWORD(v18[0]) != 0;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 88) + 216LL))(*((_QWORD *)this + 88), this[200]);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 88) + 272LL))(*((_QWORD *)this + 88), this[196]);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 88) + 288LL))(
      *((_QWORD *)this + 88),
      *((unsigned __int16 *)this + 404));
  }
  if ( *((_DWORD *)a2 + 1) != 1 )
    return 2147745899LL;
  if ( !*((_QWORD *)a2 + 4) )
    return 0;
  v19 = 0;
  CVidCtl::GetSourceSize((CVidCtl *)this, &v19);
  v18[0] = 0;
  v18[1] = v19;
  CopyRect(&rcDst, *((const RECT **)a2 + 5));
  v22 = rcDst;
  LOBYTE(v23) = 1;
  *((_QWORD *)&v23 + 1) = -1;
  v25 = rcDst;
  v26 = v23;
  rc = 0;
  v28 = 1;
  v29 = -1;
  v30 = 0;
  v31 = 1;
  v32 = -1;
  v7 = (HDC)*((_QWORD *)a2 + 4);
  *(_QWORD *)&rcDst.left = v7;
  v8 = this[196];
  if ( (this[26] & 4) != 0 && *((_QWORD *)this + 71) )
  {
    IsStopped = DSGraph::IsStopped((DSGraph *)(this + 140));
    if ( v4 )
    {
      if ( !IsStopped )
      {
        v8 = this[200];
        if ( *((_WORD *)this + 404) )
        {
          CVidCtl::ComputeAspectRatioAdjustedRects(
            v10,
            (const struct WTL::CRect *)v18,
            (const struct WTL::CRect *)&v22,
            (struct WTL::CRect *)&v25,
            (struct WTL::CRect *)&rc,
            (struct WTL::CRect *)&v30);
          SolidBrush = CreateSolidBrush(this[196]);
          v12 = SolidBrush;
          v18[0] = SolidBrush;
          if ( !SolidBrush )
          {
            pExceptionObject = -2147418113;
            throw (ComException *)&pExceptionObject;
          }
          if ( !FillRect(v7, &rc, SolidBrush) )
          {
            LastError = GetLastError();
            v14 = LastError;
            if ( LastError > 0 )
              v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_32:
            WTL::CBrushT<1>::~CBrushT<1>(v18);
            return v14;
          }
          if ( !FillRect(v7, &v30, v12) )
          {
            v15 = GetLastError();
            v14 = v15;
            if ( v15 > 0 )
              v14 = (unsigned __int16)v15 | 0x80070000;
            goto LABEL_32;
          }
          WTL::CBrushT<1>::~CBrushT<1>(v18);
        }
      }
    }
    else if ( !IsStopped )
    {
      if ( *((_QWORD *)this + 88) )
      {
        CVidCtl::CheckSurfaceStateChanged((CVidCtl *)this, (struct CScalingRect *)&v25);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 88) + 312LL))(
          *((_QWORD *)this + 88),
          *((_QWORD *)a2 + 4));
        return 0;
      }
      v8 = this[200];
    }
  }
  CVidCtl::CheckSurfaceStateChanged((CVidCtl *)this, (struct CScalingRect *)&v25);
  v16 = CreateSolidBrush(v8);
  v18[0] = v16;
  if ( !v16 )
  {
    v21 = -2147418113;
    throw (ComException *)&v21;
  }
  if ( !FillRect(v7, &v25, v16) )
  {
    v17 = GetLastError();
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_32;
  }
  WTL::CBrushT<1>::~CBrushT<1>(v18);
  return 0;
}

```

## disassembly

```asm
0x1800cd560  mov     [rsp+arg_10], rbx
0x1800cd565  push    rsi
0x1800cd566  push    rdi
0x1800cd567  push    r12
0x1800cd569  push    r14
0x1800cd56b  push    r15
0x1800cd56d  sub     rsp, 110h
0x1800cd574  mov     rax, cs:__security_cookie
0x1800cd57b  xor     rax, rsp
0x1800cd57e  mov     [rsp+138h+var_38], rax
0x1800cd586  mov     rbx, rdx
0x1800cd589  mov     rsi, rcx
0x1800cd58c  call    ?SetTimer@CVidCtl@@IEAA_KXZ; CVidCtl::SetTimer(void)
0x1800cd591  xor     r12d, r12d
0x1800cd594  mov     r15b, r12b
0x1800cd597  mov     rcx, [rsi+2C0h]
0x1800cd59e  test    rcx, rcx
0x1800cd5a1  jz      short loc_1800CD61C
0x1800cd5a3  mov     word ptr [rsp+138h+var_108], r12w
0x1800cd5a9  mov     rax, [rcx]
0x1800cd5ac  lea     rdx, [rsp+138h+var_108]
0x1800cd5b1  mov     rax, [rax+0B0h]
0x1800cd5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5bd  cmp     word ptr [rsp+138h+var_108], r12w
0x1800cd5c3  setnz   r15b
0x1800cd5c7  mov     rcx, [rsi+2C0h]
0x1800cd5ce  mov     rax, [rcx]
0x1800cd5d1  mov     edx, [rsi+320h]
0x1800cd5d7  mov     rax, [rax+0D8h]
0x1800cd5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5e3  mov     rcx, [rsi+2C0h]
0x1800cd5ea  mov     rax, [rcx]
0x1800cd5ed  mov     edx, [rsi+310h]
0x1800cd5f3  mov     rax, [rax+110h]
0x1800cd5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd5ff  mov     rcx, [rsi+2C0h]
0x1800cd606  mov     rax, [rcx]
0x1800cd609  movzx   edx, word ptr [rsi+328h]
0x1800cd610  mov     rax, [rax+120h]
0x1800cd617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd61c  cmp     dword ptr [rbx+4], 1
0x1800cd620  jz      short loc_1800CD62C
0x1800cd622  mov     eax, 8004006Bh
0x1800cd627  jmp     loc_1800CD905
0x1800cd62c  cmp     [rbx+20h], r12
0x1800cd630  jnz     short loc_1800CD639
0x1800cd632  xor     eax, eax
0x1800cd634  jmp     loc_1800CD905
0x1800cd639  mov     qword ptr [rsp+138h+var_F8.cx], r12
0x1800cd63e  lea     rdx, [rsp+138h+var_F8]; struct tagSIZE *
0x1800cd643  mov     rcx, rsi; this
0x1800cd646  call    ?GetSourceSize@CVidCtl@@IEAAXAEAUtagSIZE@@@Z; CVidCtl::GetSourceSize(tagSIZE &)
0x1800cd64b  mov     [rsp+138h+var_108], r12
0x1800cd650  mov     eax, [rsp+138h+var_F8.cx]
0x1800cd654  mov     dword ptr [rsp+138h+var_100], eax
0x1800cd658  mov     eax, [rsp+138h+var_F8.cy]
0x1800cd65c  mov     dword ptr [rsp+138h+var_100+4], eax
0x1800cd660  mov     rdx, [rbx+28h]; lprcSrc
0x1800cd664  lea     rcx, [rsp+138h+rcDst]; lprcDst
0x1800cd66c  call    cs:__imp_CopyRect
0x1800cd672  movups  xmm0, xmmword ptr [rsp+138h+rcDst.left]
0x1800cd67a  movups  [rsp+138h+var_E0], xmm0
0x1800cd67f  mov     byte ptr [rsp+138h+var_D0], 1
0x1800cd684  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800cd688  mov     qword ptr [rsp+138h+var_D0+8], rax
0x1800cd68d  movups  xmmword ptr [rsp+138h+var_A8.left], xmm0
0x1800cd695  movups  xmm0, [rsp+138h+var_D0]
0x1800cd69a  movups  [rsp+138h+var_98], xmm0
0x1800cd6a2  xorps   xmm1, xmm1
0x1800cd6a5  movups  xmmword ptr [rsp+138h+rc.left], xmm1
0x1800cd6ad  mov     [rsp+138h+var_78], 1
0x1800cd6b5  mov     [rsp+138h+var_70], rax
0x1800cd6bd  xorps   xmm0, xmm0
0x1800cd6c0  movups  xmmword ptr [rsp+138h+var_68.left], xmm0
0x1800cd6c8  mov     [rsp+138h+var_58], 1
0x1800cd6d0  mov     [rsp+138h+var_50], rax
0x1800cd6d8  mov     rdi, [rbx+20h]
0x1800cd6dc  mov     qword ptr [rsp+138h+rcDst.left], rdi
0x1800cd6e4  mov     r14d, [rsi+310h]
0x1800cd6eb  test    byte ptr [rsi+68h], 4
0x1800cd6ef  jz      loc_1800CD865
0x1800cd6f5  lea     rcx, [rsi+230h]; this
0x1800cd6fc  cmp     [rcx+8], r12
0x1800cd700  jz      loc_1800CD865
0x1800cd706  call    ?IsStopped@DSGraph@@QEAA_NXZ; DSGraph::IsStopped(void)
0x1800cd70b  test    r15b, r15b
0x1800cd70e  jz      loc_1800CD81F
0x1800cd714  test    al, al
0x1800cd716  jnz     loc_1800CD865
0x1800cd71c  mov     r14d, [rsi+320h]
0x1800cd723  cmp     [rsi+328h], r12w
0x1800cd72b  jz      loc_1800CD865
0x1800cd731  lea     rax, [rsp+138h+var_68]
0x1800cd739  mov     [rsp+138h+var_110], rax; struct WTL::CRect *
0x1800cd73e  lea     rax, [rsp+138h+rc]
0x1800cd746  mov     [rsp+138h+var_118], rax; struct WTL::CRect *
0x1800cd74b  lea     r9, [rsp+138h+var_A8]; struct WTL::CRect *
0x1800cd753  lea     r8, [rsp+138h+var_E0]; struct WTL::CRect *
0x1800cd758  lea     rdx, [rsp+138h+var_108]; struct WTL::CRect *
0x1800cd75d  call    ?ComputeAspectRatioAdjustedRects@CVidCtl@@QEAAXAEBVCRect@WTL@@0AEAV23@11@Z; CVidCtl::ComputeAspectRatioAdjustedRects(WTL::CRect const &,WTL::CRect const &,WTL::CRect &,WTL::CRect &,WTL::CRect &)
0x1800cd762  nop
0x1800cd763  mov     ecx, [rsi+310h]; color
0x1800cd769  call    cs:__imp_CreateSolidBrush
0x1800cd76f  mov     rbx, rax
0x1800cd772  mov     [rsp+138h+var_108], rax
0x1800cd777  test    rax, rax
0x1800cd77a  jnz     short loc_1800CD795
0x1800cd77c  mov     [rsp+138h+pExceptionObject], 8000FFFFh
0x1800cd784  lea     rdx, _TI1?AVComException@@; pThrowInfo
0x1800cd78b  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x1800cd790  call    _CxxThrowException_0
0x1800cd795  mov     r8, rbx; hbr
0x1800cd798  lea     rdx, [rsp+138h+rc]; lprc
0x1800cd7a0  mov     rcx, rdi; hDC
0x1800cd7a3  call    cs:__imp_FillRect
0x1800cd7a9  test    eax, eax
0x1800cd7ab  jnz     short loc_1800CD7D4
0x1800cd7ad  call    cs:__imp_GetLastError
0x1800cd7b3  mov     ebx, eax
0x1800cd7b5  test    eax, eax
0x1800cd7b7  jle     short loc_1800CD7C2
0x1800cd7b9  movzx   ebx, ax
0x1800cd7bc  or      ebx, 80070000h
0x1800cd7c2  lea     rcx, [rsp+138h+var_108]
0x1800cd7c7  call    ??1?$CBrushT@$00@WTL@@QEAA@XZ; WTL::CBrushT<1>::~CBrushT<1>(void)
0x1800cd7cc  nop
0x1800cd7cd  mov     eax, ebx
0x1800cd7cf  jmp     loc_1800CD905
0x1800cd7d4  mov     r8, rbx; hbr
0x1800cd7d7  lea     rdx, [rsp+138h+var_68]; lprc
0x1800cd7df  mov     rcx, rdi; hDC
0x1800cd7e2  call    cs:__imp_FillRect
0x1800cd7e8  test    eax, eax
0x1800cd7ea  jnz     short loc_1800CD813
0x1800cd7ec  call    cs:__imp_GetLastError
0x1800cd7f2  mov     ebx, eax
0x1800cd7f4  test    eax, eax
0x1800cd7f6  jle     short loc_1800CD801
0x1800cd7f8  movzx   ebx, ax
0x1800cd7fb  or      ebx, 80070000h
0x1800cd801  lea     rcx, [rsp+138h+var_108]
0x1800cd806  call    ??1?$CBrushT@$00@WTL@@QEAA@XZ; WTL::CBrushT<1>::~CBrushT<1>(void)
0x1800cd80b  nop
0x1800cd80c  mov     eax, ebx
0x1800cd80e  jmp     loc_1800CD905
0x1800cd813  lea     rcx, [rsp+138h+var_108]
0x1800cd818  call    ??1?$CBrushT@$00@WTL@@QEAA@XZ; WTL::CBrushT<1>::~CBrushT<1>(void)
0x1800cd81d  jmp     short loc_1800CD865
0x1800cd81f  test    al, al
0x1800cd821  jnz     short loc_1800CD865
0x1800cd823  cmp     [rsi+2C0h], r12
0x1800cd82a  jz      short loc_1800CD85E
0x1800cd82c  lea     rdx, [rsp+138h+var_A8]; struct CScalingRect *
0x1800cd834  mov     rcx, rsi; this
0x1800cd837  call    ?CheckSurfaceStateChanged@CVidCtl@@IEAA_NAEAVCScalingRect@@@Z; CVidCtl::CheckSurfaceStateChanged(CScalingRect &)
0x1800cd83c  mov     rcx, [rsi+2C0h]
0x1800cd843  mov     rax, [rcx]
0x1800cd846  mov     rdx, [rbx+20h]
0x1800cd84a  mov     rax, [rax+138h]
0x1800cd851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd856  nop
0x1800cd857  xor     eax, eax
0x1800cd859  jmp     loc_1800CD905
0x1800cd85e  mov     r14d, [rsi+320h]
0x1800cd865  lea     rdx, [rsp+138h+var_A8]; struct CScalingRect *
0x1800cd86d  mov     rcx, rsi; this
0x1800cd870  call    ?CheckSurfaceStateChanged@CVidCtl@@IEAA_NAEAVCScalingRect@@@Z; CVidCtl::CheckSurfaceStateChanged(CScalingRect &)
0x1800cd875  nop
0x1800cd876  mov     ecx, r14d; color
0x1800cd879  call    cs:__imp_CreateSolidBrush
0x1800cd87f  mov     [rsp+138h+var_108], rax
0x1800cd884  test    rax, rax
0x1800cd887  jnz     short loc_1800CD8A2
0x1800cd889  mov     [rsp+138h+var_EC], 8000FFFFh
0x1800cd891  lea     rdx, _TI1?AVComException@@; pThrowInfo
0x1800cd898  lea     rcx, [rsp+138h+var_EC]; pExceptionObject
0x1800cd89d  call    _CxxThrowException_0
0x1800cd8a2  mov     r8, rax; hbr
0x1800cd8a5  lea     rdx, [rsp+138h+var_A8]; lprc
0x1800cd8ad  mov     rcx, rdi; hDC
0x1800cd8b0  call    cs:__imp_FillRect
0x1800cd8b6  test    eax, eax
0x1800cd8b8  jnz     short loc_1800CD8DE
0x1800cd8ba  call    cs:__imp_GetLastError
0x1800cd8c0  mov     ebx, eax
0x1800cd8c2  test    eax, eax
0x1800cd8c4  jle     short loc_1800CD8CF
0x1800cd8c6  movzx   ebx, ax
0x1800cd8c9  or      ebx, 80070000h
0x1800cd8cf  lea     rcx, [rsp+138h+var_108]
0x1800cd8d4  call    ??1?$CBrushT@$00@WTL@@QEAA@XZ; WTL::CBrushT<1>::~CBrushT<1>(void)
0x1800cd8d9  nop
0x1800cd8da  mov     eax, ebx
0x1800cd8dc  jmp     short loc_1800CD905
0x1800cd8de  lea     rcx, [rsp+138h+var_108]
0x1800cd8e3  call    ??1?$CBrushT@$00@WTL@@QEAA@XZ; WTL::CBrushT<1>::~CBrushT<1>(void)
0x1800cd8e8  nop
0x1800cd8e9  xor     eax, eax
0x1800cd8eb  jmp     short loc_1800CD905
0x1800cd8ed  mov     eax, [rsp+138h+var_E8]
0x1800cd8f1  jmp     short loc_1800CD8FE
0x1800cd8f3  mov     eax, dword ptr [rsp+138h+var_108]
0x1800cd8f7  jmp     short loc_1800CD8FE
0x1800cd8f9  mov     eax, 8007000Eh
0x1800cd8fe  jmp     short loc_1800CD905
0x1800cd900  mov     eax, 8000FFFFh
0x1800cd905  mov     rcx, [rsp+138h+var_38]
0x1800cd90d  xor     rcx, rsp; StackCookie
0x1800cd910  call    __security_check_cookie
0x1800cd915  mov     rbx, [rsp+138h+arg_10]
0x1800cd91d  add     rsp, 110h
0x1800cd924  pop     r15
0x1800cd926  pop     r14
0x1800cd928  pop     r12
0x1800cd92a  pop     rdi
0x1800cd92b  pop     rsi
0x1800cd92c  retn
```
