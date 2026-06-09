# CTxtEdit::OnTxMouseMove(int,int,ulong,IUndoBuilder *)

- ea: `0x18002c17c`
- end: `0x18002c585`
- name: `?OnTxMouseMove@CTxtEdit@@AEAAJHHKPEAVIUndoBuilder@@@Z`
- size: `1033`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct IUndoBuilder *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180027b20`
- `0x180041df8`

## callees

- `0x18002c17c`
- `0x18002c58c`
- `0x18002c5d8`
- `0x18002c650`
- `0x18002dce0`
- `0x180041200`
- `0x18004ae60`
- `0x18004c338`
- `0x180057cec`
- `0x18005ce20`
- `0x18005dac4`
- `0x18005f424`
- `0x18005f68c`
- `0x18008178c`
- `0x180095010`

## import_xrefs

- `USER32!GetAsyncKeyState` at `0x18002c3ff`
- `USER32!GetAsyncKeyState` at `0x18002c417`
- `USER32!GetAsyncKeyState` at `0x18002c42d`
- `USER32!GetAsyncKeyState` at `0x18002c3ff`
- `USER32!GetAsyncKeyState` at `0x18002c417`
- `USER32!GetAsyncKeyState` at `0x18002c42d`
- `USER32!GetSystemMetrics` at `0x18002c3e5`
- `USER32!GetSystemMetrics` at `0x18002c3e5`

## pseudocode

```c
__int64 __fastcall CTxtEdit::OnTxMouseMove(CDisplay **this, int a2, int a3, unsigned int a4, struct IUndoBuilder *a5)
{
  unsigned __int64 v5; // r13
  int v10; // edx
  struct tagPOINT *v11; // r15
  _DWORD *v12; // r8
  int v13; // r10d
  int v14; // r9d
  int v15; // eax
  int v16; // eax
  int v17; // r12d
  bool v18; // zf
  CDisplay *v19; // rcx
  int v20; // eax
  int v21; // r8d
  int v22; // r8d
  int AcpFromCp; // eax
  CDisplay *v24; // rcx
  int v25; // ebx
  int SystemMetrics; // eax
  int v27; // ebx
  unsigned int v28; // r9d
  int v29; // ecx
  CDisplay *v30; // rcx
  CDisplay *v31; // rax
  struct tagPOINT v32; // rdx
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+54h] [rbp-ACh] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  struct tagPOINT v36; // [rsp+60h] [rbp-A0h] BYREF
  struct CTxtSelection *Sel; // [rsp+68h] [rbp-98h]
  HWND v38[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v39[2]; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  _BYTE v42[176]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a4;
  Sel = CTxtEdit::GetSel((CTxtEdit *)this);
  if ( !Sel )
    return 2147942414LL;
  v10 = *((_DWORD *)this + 45);
  if ( (v10 & 0x80u) != 0 )
  {
    v11 = (struct tagPOINT *)(this + 26);
    v12 = (_DWORD *)this + 53;
    if ( (v10 & 0x20002) != 0 )
    {
      v13 = CW32System::_nDragMinDist + 3;
      v14 = *v12 - a3;
      if ( *v12 <= a3 )
        v14 = a3 - *v12;
      v15 = v11->x - a2;
      if ( v11->x <= a2 )
        v15 = a2 - v11->x;
      if ( v15 < v13 && v14 < v13 )
      {
        *((_BYTE *)this + 199) = v5;
        return 0;
      }
      v16 = v10 ^ (v10 ^ (v10 << 13)) & 0x40000000;
      *((_DWORD *)this + 45) = v16;
    }
    else
    {
      LOBYTE(v16) = *((_DWORD *)this + 45);
    }
    v17 = (unsigned __int16)a3 << 16;
    v18 = ((_DWORD)this[22] & 0x4000000) == 0;
    v11->x = a2;
    *v12 = a3;
    v41 = (unsigned __int16)a2;
    if ( !v18 && (v16 & 8) != 0 )
    {
      v36.y = (unsigned __int16)a3;
      v19 = this[8];
      v33 = 0;
      v36.x = (unsigned __int16)a2;
      v20 = (*(__int64 (__fastcall **)(CDisplay *, struct tagPOINT, _QWORD, _QWORD, _QWORD, _DWORD, int *, _QWORD, _QWORD))(*(_QWORD *)v19 + 232LL))(
              v19,
              v36,
              0,
              0,
              0,
              0,
              &v33,
              0,
              0);
      if ( v33 == 7 )
      {
        v34 = 0;
        v35 = 0;
        v40 = 0;
        *(_OWORD *)v38 = 0;
        memset(v39, 0, sizeof(v39));
        CTxtRange::CTxtRange((CTxtRange *)v42, (struct CTxtEdit *)this, v20, 0);
        v18 = (*((_DWORD *)this + 45) & 0x8000000) == 0;
        *(_OWORD *)v38 = 0;
        v40 = 0;
        memset(v39, 0, sizeof(v39));
        if ( !v18 )
        {
          (*((void (__fastcall **)(char *, HWND *))this[2] + 38))((char *)this + 16, v38);
          v38[1] = (HWND)(int)CW32System::GetWindowLong(v38[0], -12);
        }
        LODWORD(v39[0]) = 1803;
        CTxtRange::Expander((CTxtRange *)v42, -2147483616, 1, 0, &v34, &v35);
        DWORD2(v39[0]) = 512;
        *(_QWORD *)((char *)v39 + 12) = 0;
        *(_QWORD *)((char *)&v39[1] + 4) = (unsigned __int16)a2 | (unsigned __int64)(unsigned int)v17;
        HIDWORD(v39[1]) = CTxtEdit::GetAcpFromCp((CTxtEdit *)this, v34, v21);
        AcpFromCp = CTxtEdit::GetAcpFromCp((CTxtEdit *)this, v35, v22);
        v24 = this[6];
        v40 = AcpFromCp;
        v25 = (*(__int64 (__fastcall **)(CDisplay *, __int64, HWND *))(*(_QWORD *)v24 + 304LL))(v24, 1803, v38);
        CTxtRange::~CTxtRange((CTxtRange *)v42);
        if ( v25 == 1 )
          return 0;
      }
    }
    SystemMetrics = GetSystemMetrics(23);
    v27 = -(SystemMetrics != 0);
    if ( GetAsyncKeyState((SystemMetrics != 0) + 1) >= 0 && GetAsyncKeyState(v27 + 2) >= 0 )
    {
      if ( GetAsyncKeyState(4) >= 0 && ((_BYTE)this[3] & 2) == 0 )
      {
        if ( (*((_DWORD *)this + 45) & 0x1000000) != 0 )
          CTxtEdit::OnTxMButtonUp((CTxtEdit *)this, a2, a3, v28);
        if ( (*((_DWORD *)this + 45) & 0x200) != 0 )
          CTxtEdit::OnTxLButtonUp((CTxtEdit *)this, a2, a3, v5, 1);
      }
      goto LABEL_37;
    }
    v29 = *((_DWORD *)this + 45);
    if ( (v29 & 0x20010) == 0x20000 )
    {
      if ( !(unsigned int)CTxtEdit::IsProtected((CTxtEdit *)this, (v29 & 4 | 0xC00u) >> 2, v5, v41 | v17) )
      {
        (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)this[6] + 120LL))(this[6], 434);
        CLightDTEngine::StartDrag((CLightDTEngine *)(this + 12), Sel, a5);
        v30 = this[6];
        *((_DWORD *)this + 45) &= ~0x200u;
        (*(void (__fastcall **)(CDisplay *, _QWORD))(*(_QWORD *)v30 + 136LL))(v30, 0);
        *((_DWORD *)this + 45) &= ~2u;
LABEL_37:
        *((_DWORD *)this + 45) &= ~0x20000u;
        return 0;
      }
      v29 = *((_DWORD *)this + 45);
    }
    if ( (v29 & 0x200) != 0 )
    {
      v31 = this[13];
      v32 = *v11;
      v36 = *v11;
      if ( v31 && *((_QWORD *)v31 + 3) )
      {
        CDisplay::DragScroll(this[8], &v36);
        v32 = v36;
      }
      CTxtSelection::ExtendSelection(Sel, v32);
      CTxtEdit::CheckInstallContinuousScroll((CTxtEdit *)this);
    }
    goto LABEL_37;
  }
  return 0;
}

```

## disassembly

```asm
0x18002c17c  push    rbp
0x18002c17e  push    rbx
0x18002c17f  push    rsi
0x18002c180  push    rdi
0x18002c181  push    r12
0x18002c183  push    r13
0x18002c185  push    r14
0x18002c187  push    r15
0x18002c189  lea     rbp, [rsp-28h]
0x18002c18e  sub     rsp, 128h
0x18002c195  mov     r13d, r9d
0x18002c198  mov     esi, r8d
0x18002c19b  mov     r14d, edx
0x18002c19e  mov     rdi, rcx
0x18002c1a1  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18002c1a6  xor     r9d, r9d
0x18002c1a9  mov     [rsp+160h+var_F8], rax
0x18002c1ae  test    rax, rax
0x18002c1b1  jnz     short loc_18002C1BD
0x18002c1b3  mov     eax, 8007000Eh
0x18002c1b8  jmp     loc_18002C570
0x18002c1bd  mov     edx, [rdi+0B4h]
0x18002c1c3  test    dl, dl
0x18002c1c5  jns     loc_18002C56E
0x18002c1cb  lea     r15, [rdi+0D0h]
0x18002c1d2  lea     r8, [rdi+0D4h]
0x18002c1d9  test    edx, 20002h
0x18002c1df  jz      short loc_18002C240
0x18002c1e1  movzx   r10d, cs:?_nDragMinDist@CW32System@@0GA; ushort CW32System::_nDragMinDist
0x18002c1e9  mov     eax, esi
0x18002c1eb  sub     eax, [r8]
0x18002c1ee  add     r10d, 3
0x18002c1f2  mov     r9d, [r8]
0x18002c1f5  mov     ecx, r14d
0x18002c1f8  sub     r9d, esi
0x18002c1fb  cmp     [r8], esi
0x18002c1fe  cmovle  r9d, eax
0x18002c202  sub     ecx, [r15]
0x18002c205  mov     eax, [r15]
0x18002c208  sub     eax, r14d
0x18002c20b  cmp     [r15], r14d
0x18002c20e  cmovle  eax, ecx
0x18002c211  cmp     eax, r10d
0x18002c214  jge     short loc_18002C227
0x18002c216  cmp     r9d, r10d
0x18002c219  jge     short loc_18002C227
0x18002c21b  mov     [rdi+0C7h], r13b
0x18002c222  jmp     loc_18002C56E
0x18002c227  mov     eax, edx
0x18002c229  shl     eax, 0Dh
0x18002c22c  xor     eax, edx
0x18002c22e  and     eax, 40000000h
0x18002c233  xor     eax, edx
0x18002c235  mov     [rdi+0B4h], eax
0x18002c23b  xor     r9d, r9d
0x18002c23e  jmp     short loc_18002C242
0x18002c240  mov     eax, edx
0x18002c242  movzx   ecx, si
0x18002c245  mov     r12d, ecx
0x18002c248  movzx   edx, r14w
0x18002c24c  shl     r12d, 10h
0x18002c250  test    dword ptr [rdi+0B0h], 4000000h
0x18002c25a  mov     [r15], r14d
0x18002c25d  mov     [r8], esi
0x18002c260  mov     [rbp+60h+var_B8], rdx
0x18002c264  jz      loc_18002C3E0
0x18002c26a  test    al, 8
0x18002c26c  jz      loc_18002C3E0
0x18002c272  mov     [rsp+160h+var_120], r9
0x18002c277  xor     r8d, r8d
0x18002c27a  mov     [rsp+160h+var_128], r9
0x18002c27f  mov     [rsp+160h+var_100.y], ecx
0x18002c283  mov     rcx, [rdi+40h]
0x18002c287  mov     [rsp+160h+var_110], r9d
0x18002c28c  mov     ebx, r12d
0x18002c28f  or      rbx, rdx
0x18002c292  lea     rdx, [rsp+160h+var_110]
0x18002c297  mov     [rsp+160h+var_130], rdx
0x18002c29c  mov     dword ptr [rsp+160h+var_138], r9d
0x18002c2a1  movzx   eax, bx
0x18002c2a4  mov     [rsp+160h+var_100.x], eax
0x18002c2a8  mov     rax, [rcx]
0x18002c2ab  mov     rdx, qword ptr [rsp+160h+var_100.x]
0x18002c2b0  mov     [rsp+160h+var_140], r9
0x18002c2b5  xor     r9d, r9d
0x18002c2b8  mov     rax, [rax+0E8h]
0x18002c2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2c4  cmp     [rsp+160h+var_110], 7
0x18002c2c9  jnz     loc_18002C3E0
0x18002c2cf  xor     ecx, ecx
0x18002c2d1  xorps   xmm0, xmm0
0x18002c2d4  mov     [rsp+160h+var_10C], ecx
0x18002c2d8  xor     r9d, r9d; int
0x18002c2db  mov     [rsp+160h+var_108], ecx
0x18002c2df  mov     r8d, eax; int
0x18002c2e2  mov     [rbp+60h+var_C0], ecx
0x18002c2e5  mov     rdx, rdi; struct CTxtEdit *
0x18002c2e8  lea     rcx, [rbp+60h+var_B0]; this
0x18002c2ec  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x18002c2f1  movups  [rbp+60h+var_E0], xmm0
0x18002c2f5  movups  [rbp+60h+var_D0], xmm0
0x18002c2f9  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x18002c2fe  xorps   xmm0, xmm0
0x18002c301  xor     eax, eax
0x18002c303  test    dword ptr [rdi+0B4h], 8000000h
0x18002c30d  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x18002c312  mov     [rbp+60h+var_C0], eax
0x18002c315  movups  [rbp+60h+var_E0], xmm0
0x18002c319  movups  [rbp+60h+var_D0], xmm0
0x18002c31d  jz      short loc_18002C34E
0x18002c31f  lea     rcx, [rdi+10h]
0x18002c323  mov     rax, [rcx]
0x18002c326  lea     rdx, [rsp+160h+var_F0]
0x18002c32b  mov     rax, [rax+130h]
0x18002c332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c337  mov     rcx, [rsp+160h+var_F0]; HWND
0x18002c33c  mov     edx, 0FFFFFFF4h; int
0x18002c341  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18002c346  movsxd  rcx, eax
0x18002c349  mov     [rsp+160h+var_F0+8], rcx
0x18002c34e  xor     r9d, r9d; int *
0x18002c351  mov     dword ptr [rbp+60h+var_E0], 70Bh
0x18002c358  lea     rax, [rsp+160h+var_108]
0x18002c35d  mov     edx, 80000020h; int
0x18002c362  mov     [rsp+160h+var_138], rax; int *
0x18002c367  lea     rcx, [rbp+60h+var_B0]; this
0x18002c36b  lea     rax, [rsp+160h+var_10C]
0x18002c370  lea     r8d, [r9+1]; int
0x18002c374  mov     [rsp+160h+var_140], rax; int *
0x18002c379  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18002c37e  mov     edx, [rsp+160h+var_10C]; int
0x18002c382  mov     rcx, rdi; this
0x18002c385  mov     dword ptr [rbp+60h+var_E0+8], 200h
0x18002c38c  mov     qword ptr [rbp+60h+var_E0+0Ch], 0
0x18002c394  mov     qword ptr [rbp+60h+var_D0+4], rbx
0x18002c398  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18002c39d  mov     edx, [rsp+160h+var_108]; int
0x18002c3a1  mov     rcx, rdi; this
0x18002c3a4  mov     dword ptr [rbp+60h+var_D0+0Ch], eax
0x18002c3a7  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18002c3ac  mov     rcx, [rdi+30h]
0x18002c3b0  lea     r8, [rsp+160h+var_F0]
0x18002c3b5  mov     [rbp+60h+var_C0], eax
0x18002c3b8  mov     edx, 70Bh
0x18002c3bd  mov     rax, [rcx]
0x18002c3c0  mov     rax, [rax+130h]
0x18002c3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c3cc  lea     rcx, [rbp+60h+var_B0]; this
0x18002c3d0  mov     ebx, eax
0x18002c3d2  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18002c3d7  cmp     ebx, 1
0x18002c3da  jz      loc_18002C56E
0x18002c3e0  mov     ecx, 17h; nIndex
0x18002c3e5  call    cs:__imp_GetSystemMetrics
0x18002c3ec  nop     dword ptr [rax+rax+00h]
0x18002c3f1  mov     ecx, eax
0x18002c3f3  neg     ecx
0x18002c3f5  sbb     ebx, ebx
0x18002c3f7  neg     eax
0x18002c3f9  sbb     ecx, ecx
0x18002c3fb  neg     ecx
0x18002c3fd  inc     ecx; vKey
0x18002c3ff  call    cs:__imp_GetAsyncKeyState
0x18002c406  nop     dword ptr [rax+rax+00h]
0x18002c40b  test    ax, ax
0x18002c40e  js      loc_18002C494
0x18002c414  lea     ecx, [rbx+2]; vKey
0x18002c417  call    cs:__imp_GetAsyncKeyState
0x18002c41e  nop     dword ptr [rax+rax+00h]
0x18002c423  xor     ebx, ebx
0x18002c425  test    ax, ax
0x18002c428  js      short loc_18002C496
0x18002c42a  lea     ecx, [rbx+4]; vKey
0x18002c42d  call    cs:__imp_GetAsyncKeyState
0x18002c434  nop     dword ptr [rax+rax+00h]
0x18002c439  test    ax, ax
0x18002c43c  js      loc_18002C566
0x18002c442  test    byte ptr [rdi+18h], 2
0x18002c446  jnz     loc_18002C566
0x18002c44c  test    dword ptr [rdi+0B4h], 1000000h
0x18002c456  jz      short loc_18002C466
0x18002c458  mov     r8d, esi; int
0x18002c45b  mov     edx, r14d; int
0x18002c45e  mov     rcx, rdi; this
0x18002c461  call    ?OnTxMButtonUp@CTxtEdit@@AEAAJHHK@Z; CTxtEdit::OnTxMButtonUp(int,int,ulong)
0x18002c466  test    dword ptr [rdi+0B4h], 200h
0x18002c470  jz      loc_18002C566
0x18002c476  mov     r9d, r13d; unsigned int
0x18002c479  mov     dword ptr [rsp+160h+var_140], 1; int
0x18002c481  mov     r8d, esi; int
0x18002c484  mov     edx, r14d; int
0x18002c487  mov     rcx, rdi; this
0x18002c48a  call    ?OnTxLButtonUp@CTxtEdit@@AEAAJHHKH@Z; CTxtEdit::OnTxLButtonUp(int,int,ulong,int)
0x18002c48f  jmp     loc_18002C566
0x18002c494  xor     ebx, ebx
0x18002c496  mov     ecx, [rdi+0B4h]
0x18002c49c  mov     eax, ecx
0x18002c49e  and     eax, 20010h
0x18002c4a3  cmp     eax, 20000h
0x18002c4a8  jnz     short loc_18002C524
0x18002c4aa  and     ecx, 4
0x18002c4ad  movsxd  r9, r12d
0x18002c4b0  or      r9, [rbp+60h+var_B8]; __int64
0x18002c4b4  or      ecx, 0C00h
0x18002c4ba  shr     ecx, 2
0x18002c4bd  mov     r8, r13; unsigned __int64
0x18002c4c0  mov     edx, ecx; unsigned int
0x18002c4c2  mov     rcx, rdi; this
0x18002c4c5  call    ?IsProtected@CTxtEdit@@QEAAHI_K_J@Z; CTxtEdit::IsProtected(uint,unsigned __int64,__int64)
0x18002c4ca  test    eax, eax
0x18002c4cc  jnz     short loc_18002C51E
0x18002c4ce  mov     rcx, [rdi+30h]
0x18002c4d2  mov     edx, 1B2h
0x18002c4d7  mov     rax, [rcx]
0x18002c4da  mov     rax, [rax+78h]
0x18002c4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4e3  mov     r8, [rbp+60h+arg_20]; struct IUndoBuilder *
0x18002c4ea  lea     rcx, [rdi+60h]; this
0x18002c4ee  mov     rdx, [rsp+160h+var_F8]; struct CTxtSelection *
0x18002c4f3  call    ?StartDrag@CLightDTEngine@@QEAAJPEAVCTxtSelection@@PEAVIUndoBuilder@@@Z; CLightDTEngine::StartDrag(CTxtSelection *,IUndoBuilder *)
0x18002c4f8  mov     rcx, [rdi+30h]
0x18002c4fc  xor     edx, edx
0x18002c4fe  btr     dword ptr [rdi+0B4h], 9
0x18002c506  mov     rax, [rcx]
0x18002c509  mov     rax, [rax+88h]
0x18002c510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c515  and     dword ptr [rdi+0B4h], 0FFFFFFFDh
0x18002c51c  jmp     short loc_18002C566
0x18002c51e  mov     ecx, [rdi+0B4h]
0x18002c524  bt      ecx, 9
0x18002c528  jnb     short loc_18002C566
0x18002c52a  mov     rax, [rdi+68h]
0x18002c52e  mov     rdx, [r15]
0x18002c531  mov     qword ptr [rsp+160h+var_100.x], rdx
0x18002c536  test    rax, rax
0x18002c539  jz      short loc_18002C554
0x18002c53b  cmp     [rax+18h], rbx
0x18002c53f  jz      short loc_18002C554
0x18002c541  mov     rcx, [rdi+40h]; this
0x18002c545  lea     rdx, [rsp+160h+var_100]; struct tagPOINT *
0x18002c54a  call    ?DragScroll@CDisplay@@QEAAHPEBUtagPOINT@@@Z; CDisplay::DragScroll(tagPOINT const *)
0x18002c54f  mov     rdx, qword ptr [rsp+160h+var_100.x]; struct tagPOINT
0x18002c554  mov     rcx, [rsp+160h+var_F8]; this
0x18002c559  call    ?ExtendSelection@CTxtSelection@@QEAAXUtagPOINT@@@Z; CTxtSelection::ExtendSelection(tagPOINT)
0x18002c55e  mov     rcx, rdi; this
0x18002c561  call    ?CheckInstallContinuousScroll@CTxtEdit@@AEAAXXZ; CTxtEdit::CheckInstallContinuousScroll(void)
0x18002c566  btr     dword ptr [rdi+0B4h], 11h
0x18002c56e  xor     eax, eax
0x18002c570  add     rsp, 128h
0x18002c577  pop     r15
0x18002c579  pop     r14
0x18002c57b  pop     r13
0x18002c57d  pop     r12
0x18002c57f  pop     rdi
0x18002c580  pop     rsi
0x18002c581  pop     rbx
0x18002c582  pop     rbp
0x18002c583  retn
```
