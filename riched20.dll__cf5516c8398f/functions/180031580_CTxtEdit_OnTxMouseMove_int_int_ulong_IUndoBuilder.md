# CTxtEdit::OnTxMouseMove(int,int,ulong,IUndoBuilder *)

- ea: `0x180031580`
- end: `0x18003196c`
- name: `?OnTxMouseMove@CTxtEdit@@AEAAJHHKPEAVIUndoBuilder@@@Z`
- size: `1004`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, struct IUndoBuilder *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x18002cfd0`
- `0x1800412d4`

## callees

- `0x180031580`
- `0x180031974`
- `0x1800319c0`
- `0x180031a38`
- `0x180033060`
- `0x1800404ac`
- `0x180049cf4`
- `0x18004b168`
- `0x180056764`
- `0x18005b7c0`
- `0x18005c450`
- `0x18005dd30`
- `0x18005df90`
- `0x18007f31c`
- `0x180092010`

## import_xrefs

- `USER32!GetAsyncKeyState` at `0x1800317fd`
- `USER32!GetAsyncKeyState` at `0x18003180b`
- `USER32!GetAsyncKeyState` at `0x18003181b`
- `USER32!GetAsyncKeyState` at `0x1800317fd`
- `USER32!GetAsyncKeyState` at `0x18003180b`
- `USER32!GetAsyncKeyState` at `0x18003181b`
- `USER32!GetSystemMetrics` at `0x1800317e9`
- `USER32!GetSystemMetrics` at `0x1800317e9`

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
0x180031580  push    rbp
0x180031582  push    rbx
0x180031583  push    rsi
0x180031584  push    rdi
0x180031585  push    r12
0x180031587  push    r13
0x180031589  push    r14
0x18003158b  push    r15
0x18003158d  lea     rbp, [rsp-28h]
0x180031592  sub     rsp, 128h
0x180031599  mov     r13d, r9d
0x18003159c  mov     esi, r8d
0x18003159f  mov     r14d, edx
0x1800315a2  mov     rdi, rcx
0x1800315a5  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x1800315aa  xor     r9d, r9d
0x1800315ad  mov     [rsp+160h+var_F8], rax
0x1800315b2  test    rax, rax
0x1800315b5  jnz     short loc_1800315C1
0x1800315b7  mov     eax, 8007000Eh
0x1800315bc  jmp     loc_180031958
0x1800315c1  mov     edx, [rdi+0B4h]
0x1800315c7  test    dl, dl
0x1800315c9  jns     loc_180031956
0x1800315cf  lea     r15, [rdi+0D0h]
0x1800315d6  lea     r8, [rdi+0D4h]
0x1800315dd  test    edx, 20002h
0x1800315e3  jz      short loc_180031644
0x1800315e5  movzx   r10d, cs:?_nDragMinDist@CW32System@@0GA; ushort CW32System::_nDragMinDist
0x1800315ed  mov     eax, esi
0x1800315ef  sub     eax, [r8]
0x1800315f2  add     r10d, 3
0x1800315f6  mov     r9d, [r8]
0x1800315f9  mov     ecx, r14d
0x1800315fc  sub     r9d, esi
0x1800315ff  cmp     [r8], esi
0x180031602  cmovle  r9d, eax
0x180031606  sub     ecx, [r15]
0x180031609  mov     eax, [r15]
0x18003160c  sub     eax, r14d
0x18003160f  cmp     [r15], r14d
0x180031612  cmovle  eax, ecx
0x180031615  cmp     eax, r10d
0x180031618  jge     short loc_18003162B
0x18003161a  cmp     r9d, r10d
0x18003161d  jge     short loc_18003162B
0x18003161f  mov     [rdi+0C7h], r13b
0x180031626  jmp     loc_180031956
0x18003162b  mov     eax, edx
0x18003162d  shl     eax, 0Dh
0x180031630  xor     eax, edx
0x180031632  and     eax, 40000000h
0x180031637  xor     eax, edx
0x180031639  mov     [rdi+0B4h], eax
0x18003163f  xor     r9d, r9d
0x180031642  jmp     short loc_180031646
0x180031644  mov     eax, edx
0x180031646  movzx   ecx, si
0x180031649  mov     r12d, ecx
0x18003164c  movzx   edx, r14w
0x180031650  shl     r12d, 10h
0x180031654  test    dword ptr [rdi+0B0h], 4000000h
0x18003165e  mov     [r15], r14d
0x180031661  mov     [r8], esi
0x180031664  mov     [rbp+60h+var_B8], rdx
0x180031668  jz      loc_1800317E4
0x18003166e  test    al, 8
0x180031670  jz      loc_1800317E4
0x180031676  mov     [rsp+160h+var_120], r9
0x18003167b  xor     r8d, r8d
0x18003167e  mov     [rsp+160h+var_128], r9
0x180031683  mov     [rsp+160h+var_100.y], ecx
0x180031687  mov     rcx, [rdi+40h]
0x18003168b  mov     [rsp+160h+var_110], r9d
0x180031690  mov     ebx, r12d
0x180031693  or      rbx, rdx
0x180031696  lea     rdx, [rsp+160h+var_110]
0x18003169b  mov     [rsp+160h+var_130], rdx
0x1800316a0  mov     dword ptr [rsp+160h+var_138], r9d
0x1800316a5  movzx   eax, bx
0x1800316a8  mov     [rsp+160h+var_100.x], eax
0x1800316ac  mov     rax, [rcx]
0x1800316af  mov     rdx, qword ptr [rsp+160h+var_100.x]
0x1800316b4  mov     [rsp+160h+var_140], r9
0x1800316b9  xor     r9d, r9d
0x1800316bc  mov     rax, [rax+0E8h]
0x1800316c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316c8  cmp     [rsp+160h+var_110], 7
0x1800316cd  jnz     loc_1800317E4
0x1800316d3  xor     ecx, ecx
0x1800316d5  xorps   xmm0, xmm0
0x1800316d8  mov     [rsp+160h+var_10C], ecx
0x1800316dc  xor     r9d, r9d; int
0x1800316df  mov     [rsp+160h+var_108], ecx
0x1800316e3  mov     r8d, eax; int
0x1800316e6  mov     [rbp+60h+var_C0], ecx
0x1800316e9  mov     rdx, rdi; struct CTxtEdit *
0x1800316ec  lea     rcx, [rbp+60h+var_B0]; this
0x1800316f0  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x1800316f5  movups  [rbp+60h+var_E0], xmm0
0x1800316f9  movups  [rbp+60h+var_D0], xmm0
0x1800316fd  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x180031702  xorps   xmm0, xmm0
0x180031705  xor     eax, eax
0x180031707  test    dword ptr [rdi+0B4h], 8000000h
0x180031711  movups  xmmword ptr [rsp+160h+var_F0], xmm0
0x180031716  mov     [rbp+60h+var_C0], eax
0x180031719  movups  [rbp+60h+var_E0], xmm0
0x18003171d  movups  [rbp+60h+var_D0], xmm0
0x180031721  jz      short loc_180031752
0x180031723  lea     rcx, [rdi+10h]
0x180031727  mov     rax, [rcx]
0x18003172a  lea     rdx, [rsp+160h+var_F0]
0x18003172f  mov     rax, [rax+130h]
0x180031736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003173b  mov     rcx, [rsp+160h+var_F0]; HWND
0x180031740  mov     edx, 0FFFFFFF4h; int
0x180031745  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x18003174a  movsxd  rcx, eax
0x18003174d  mov     [rsp+160h+var_F0+8], rcx
0x180031752  xor     r9d, r9d; int *
0x180031755  mov     dword ptr [rbp+60h+var_E0], 70Bh
0x18003175c  lea     rax, [rsp+160h+var_108]
0x180031761  mov     edx, 80000020h; int
0x180031766  mov     [rsp+160h+var_138], rax; int *
0x18003176b  lea     rcx, [rbp+60h+var_B0]; this
0x18003176f  lea     rax, [rsp+160h+var_10C]
0x180031774  lea     r8d, [r9+1]; int
0x180031778  mov     [rsp+160h+var_140], rax; int *
0x18003177d  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x180031782  mov     edx, [rsp+160h+var_10C]; int
0x180031786  mov     rcx, rdi; this
0x180031789  mov     dword ptr [rbp+60h+var_E0+8], 200h
0x180031790  mov     qword ptr [rbp+60h+var_E0+0Ch], 0
0x180031798  mov     qword ptr [rbp+60h+var_D0+4], rbx
0x18003179c  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x1800317a1  mov     edx, [rsp+160h+var_108]; int
0x1800317a5  mov     rcx, rdi; this
0x1800317a8  mov     dword ptr [rbp+60h+var_D0+0Ch], eax
0x1800317ab  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x1800317b0  mov     rcx, [rdi+30h]
0x1800317b4  lea     r8, [rsp+160h+var_F0]
0x1800317b9  mov     [rbp+60h+var_C0], eax
0x1800317bc  mov     edx, 70Bh
0x1800317c1  mov     rax, [rcx]
0x1800317c4  mov     rax, [rax+130h]
0x1800317cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800317d0  lea     rcx, [rbp+60h+var_B0]; this
0x1800317d4  mov     ebx, eax
0x1800317d6  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x1800317db  cmp     ebx, 1
0x1800317de  jz      loc_180031956
0x1800317e4  mov     ecx, 17h; nIndex
0x1800317e9  call    cs:__imp_GetSystemMetrics
0x1800317ef  mov     ecx, eax
0x1800317f1  neg     ecx
0x1800317f3  sbb     ebx, ebx
0x1800317f5  neg     eax
0x1800317f7  sbb     ecx, ecx
0x1800317f9  neg     ecx
0x1800317fb  inc     ecx; vKey
0x1800317fd  call    cs:__imp_GetAsyncKeyState
0x180031803  test    ax, ax
0x180031806  js      short loc_18003187C
0x180031808  lea     ecx, [rbx+2]; vKey
0x18003180b  call    cs:__imp_GetAsyncKeyState
0x180031811  xor     ebx, ebx
0x180031813  test    ax, ax
0x180031816  js      short loc_18003187E
0x180031818  lea     ecx, [rbx+4]; vKey
0x18003181b  call    cs:__imp_GetAsyncKeyState
0x180031821  test    ax, ax
0x180031824  js      loc_18003194E
0x18003182a  test    byte ptr [rdi+18h], 2
0x18003182e  jnz     loc_18003194E
0x180031834  test    dword ptr [rdi+0B4h], 1000000h
0x18003183e  jz      short loc_18003184E
0x180031840  mov     r8d, esi; int
0x180031843  mov     edx, r14d; int
0x180031846  mov     rcx, rdi; this
0x180031849  call    ?OnTxMButtonUp@CTxtEdit@@AEAAJHHK@Z; CTxtEdit::OnTxMButtonUp(int,int,ulong)
0x18003184e  test    dword ptr [rdi+0B4h], 200h
0x180031858  jz      loc_18003194E
0x18003185e  mov     r9d, r13d; unsigned int
0x180031861  mov     dword ptr [rsp+160h+var_140], 1; int
0x180031869  mov     r8d, esi; int
0x18003186c  mov     edx, r14d; int
0x18003186f  mov     rcx, rdi; this
0x180031872  call    ?OnTxLButtonUp@CTxtEdit@@AEAAJHHKH@Z; CTxtEdit::OnTxLButtonUp(int,int,ulong,int)
0x180031877  jmp     loc_18003194E
0x18003187c  xor     ebx, ebx
0x18003187e  mov     ecx, [rdi+0B4h]
0x180031884  mov     eax, ecx
0x180031886  and     eax, 20010h
0x18003188b  cmp     eax, 20000h
0x180031890  jnz     short loc_18003190C
0x180031892  and     ecx, 4
0x180031895  movsxd  r9, r12d
0x180031898  or      r9, [rbp+60h+var_B8]; __int64
0x18003189c  or      ecx, 0C00h
0x1800318a2  shr     ecx, 2
0x1800318a5  mov     r8, r13; unsigned __int64
0x1800318a8  mov     edx, ecx; unsigned int
0x1800318aa  mov     rcx, rdi; this
0x1800318ad  call    ?IsProtected@CTxtEdit@@QEAAHI_K_J@Z; CTxtEdit::IsProtected(uint,unsigned __int64,__int64)
0x1800318b2  test    eax, eax
0x1800318b4  jnz     short loc_180031906
0x1800318b6  mov     rcx, [rdi+30h]
0x1800318ba  mov     edx, 1B2h
0x1800318bf  mov     rax, [rcx]
0x1800318c2  mov     rax, [rax+78h]
0x1800318c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318cb  mov     r8, [rbp+60h+arg_20]; struct IUndoBuilder *
0x1800318d2  lea     rcx, [rdi+60h]; this
0x1800318d6  mov     rdx, [rsp+160h+var_F8]; struct CTxtSelection *
0x1800318db  call    ?StartDrag@CLightDTEngine@@QEAAJPEAVCTxtSelection@@PEAVIUndoBuilder@@@Z; CLightDTEngine::StartDrag(CTxtSelection *,IUndoBuilder *)
0x1800318e0  mov     rcx, [rdi+30h]
0x1800318e4  xor     edx, edx
0x1800318e6  btr     dword ptr [rdi+0B4h], 9
0x1800318ee  mov     rax, [rcx]
0x1800318f1  mov     rax, [rax+88h]
0x1800318f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318fd  and     dword ptr [rdi+0B4h], 0FFFFFFFDh
0x180031904  jmp     short loc_18003194E
0x180031906  mov     ecx, [rdi+0B4h]
0x18003190c  bt      ecx, 9
0x180031910  jnb     short loc_18003194E
0x180031912  mov     rax, [rdi+68h]
0x180031916  mov     rdx, [r15]
0x180031919  mov     qword ptr [rsp+160h+var_100.x], rdx
0x18003191e  test    rax, rax
0x180031921  jz      short loc_18003193C
0x180031923  cmp     [rax+18h], rbx
0x180031927  jz      short loc_18003193C
0x180031929  mov     rcx, [rdi+40h]; this
0x18003192d  lea     rdx, [rsp+160h+var_100]; struct tagPOINT *
0x180031932  call    ?DragScroll@CDisplay@@QEAAHPEBUtagPOINT@@@Z; CDisplay::DragScroll(tagPOINT const *)
0x180031937  mov     rdx, qword ptr [rsp+160h+var_100.x]; struct tagPOINT
0x18003193c  mov     rcx, [rsp+160h+var_F8]; this
0x180031941  call    ?ExtendSelection@CTxtSelection@@QEAAXUtagPOINT@@@Z; CTxtSelection::ExtendSelection(tagPOINT)
0x180031946  mov     rcx, rdi; this
0x180031949  call    ?CheckInstallContinuousScroll@CTxtEdit@@AEAAXXZ; CTxtEdit::CheckInstallContinuousScroll(void)
0x18003194e  btr     dword ptr [rdi+0B4h], 11h
0x180031956  xor     eax, eax
0x180031958  add     rsp, 128h
0x18003195f  pop     r15
0x180031961  pop     r14
0x180031963  pop     r13
0x180031965  pop     r12
0x180031967  pop     rdi
0x180031968  pop     rsi
0x180031969  pop     rbx
0x18003196a  pop     rbp
0x18003196b  retn
```
