# CDropTarget::DragEnter(IDataObject *,ulong,_POINTL,ulong *)

- ea: `0x1800597a0`
- end: `0x18005995f`
- name: `?DragEnter@CDropTarget@@UEAAJPEAUIDataObject@@KU_POINTL@@PEAK@Z`
- size: `447`
- prototype: `int(CDropTarget *__hidden this, struct IDataObject *, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180022780`
- `0x18002fb90`
- `0x180031a38`
- `0x180033328`
- `0x18003e5c8`
- `0x180059750`
- `0x180059778`
- `0x1800597a0`
- `0x18006c128`
- `0x180092010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x18005988f`
- `GDI32!GetDeviceCaps` at `0x18005988f`

## pseudocode

```c
__int64 __fastcall CDropTarget::DragEnter(
        CDropTarget *this,
        struct IDataObject *a2,
        unsigned int a3,
        struct _POINTL a4,
        unsigned int *a5)
{
  bool v5; // zf
  CCallMgr *v11; // rax
  unsigned int v12; // ebp
  unsigned int CanPaste; // eax
  unsigned int v14; // edx
  _QWORD *v15; // rax
  unsigned int v16; // edx
  _QWORD *v17; // rsi
  HDC DC; // rax
  int DeviceCaps; // eax
  HDC v20; // rdx
  CDropCaret *v21; // rcx
  struct CTxtSelection *Sel; // rax
  __int64 v23; // rax
  CCallMgr *v24; // rcx

  v5 = *((_QWORD *)this + 2) == 0;
  *((_DWORD *)this + 14) = -1;
  if ( v5 )
    return 2147746303LL;
  v11 = (CCallMgr *)CW32System::PvAlloc(0x20u, 0x40u);
  if ( v11 )
    v11 = CCallMgr::CCallMgr(v11, *((struct CTxtEdit **)this + 2));
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 2147942414LL;
  v12 = 1;
  CanPaste = CLightDTEngine::CanPaste((CLightDTEngine *)(*((_QWORD *)this + 2) + 96LL), a2, 0, 1u);
  if ( CanPaste )
  {
    if ( CanPaste == 0x80000000 )
      *((_DWORD *)this + 3) |= 0x80000000;
    v15 = CW32System::PvAlloc(0x48u, 0x40u);
    v17 = v15;
    if ( v15 )
    {
      *v15 = *((_QWORD *)this + 2);
      v15[1] = 0;
      *((_DWORD *)v15 + 5) = -1;
      v15[5] = 0;
    }
    else
    {
      v17 = 0;
    }
    *((_QWORD *)this + 8) = v17;
    if ( !v17
      || (DC = CDevDesc::GetDC((CDevDesc *)(*(_QWORD *)(*v17 + 64LL) + 16LL)), (v17[1] = DC) == 0)
      || (DeviceCaps = GetDeviceCaps(DC, 90),
          v20 = (HDC)v17[1],
          *((_DWORD *)v17 + 4) = DeviceCaps,
          *((_DWORD *)v17 + 6) = 32,
          !COffScreenDC::Init((COffScreenDC *)(v17 + 5), v20, 1, 32, 0xFFFFFFFF)) )
    {
      v21 = (CDropCaret *)*((_QWORD *)this + 8);
      if ( v21 )
        CDropCaret::`scalar deleting destructor'(v21, v16);
      *((_QWORD *)this + 8) = 0;
    }
    Sel = CTxtEdit::GetSel(*((CTxtEdit **)this + 2));
    if ( Sel )
    {
      *((_DWORD *)this + 12) = *((_DWORD *)Sel + 10);
      *((_DWORD *)this + 13) = *((_DWORD *)Sel + 22);
    }
    v23 = *(_QWORD *)this;
    *((_DWORD *)this + 3) |= 0x40000000u;
    v12 = (*(__int64 (__fastcall **)(CDropTarget *, _QWORD, struct _POINTL, unsigned int *))(v23 + 32))(
            this,
            a3,
            a4,
            a5);
    if ( !v12 )
      return v12;
    goto LABEL_22;
  }
  if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 180LL) & 0x8000000) == 0 )
  {
LABEL_22:
    v24 = (CCallMgr *)*((_QWORD *)this + 3);
    if ( v24 )
      CCallMgr::`scalar deleting destructor'(v24, v14);
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 3) = 0;
    return v12;
  }
  v12 = 0;
  *a5 = 0;
  return v12;
}

```

## disassembly

```asm
0x1800597a0  push    rbx
0x1800597a2  push    rbp
0x1800597a3  push    rsi
0x1800597a4  push    rdi
0x1800597a5  push    r14
0x1800597a7  sub     rsp, 30h
0x1800597ab  cmp     qword ptr [rcx+10h], 0
0x1800597b0  mov     rbx, r9
0x1800597b3  mov     r14d, r8d
0x1800597b6  mov     dword ptr [rcx+38h], 0FFFFFFFFh
0x1800597bd  mov     rsi, rdx
0x1800597c0  mov     rdi, rcx
0x1800597c3  jnz     short loc_1800597CF
0x1800597c5  mov     eax, 800401FFh
0x1800597ca  jmp     loc_180059936
0x1800597cf  mov     edx, 40h ; '@'; unsigned int
0x1800597d4  lea     ecx, [rdx-20h]; unsigned int
0x1800597d7  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x1800597dc  test    rax, rax
0x1800597df  jz      short loc_1800597ED
0x1800597e1  mov     rdx, [rdi+10h]; struct CTxtEdit *
0x1800597e5  mov     rcx, rax; this
0x1800597e8  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x1800597ed  mov     [rdi+18h], rax
0x1800597f1  test    rax, rax
0x1800597f4  jnz     short loc_180059800
0x1800597f6  mov     eax, 8007000Eh
0x1800597fb  jmp     loc_180059936
0x180059800  mov     rcx, [rdi+10h]
0x180059804  xor     r8d, r8d; unsigned __int16
0x180059807  add     rcx, 60h ; '`'; this
0x18005980b  mov     rdx, rsi; struct IDataObject *
0x18005980e  lea     ebp, [r8+1]
0x180059812  mov     r9d, ebp; unsigned int
0x180059815  call    ?CanPaste@CLightDTEngine@@QEAAKPEAUIDataObject@@GK@Z; CLightDTEngine::CanPaste(IDataObject *,ushort,ulong)
0x18005981a  test    eax, eax
0x18005981c  jz      loc_180059941
0x180059822  mov     ecx, 80000000h
0x180059827  cmp     eax, ecx
0x180059829  jnz     short loc_18005982E
0x18005982b  or      [rdi+0Ch], ecx
0x18005982e  mov     edx, 40h ; '@'; unsigned int
0x180059833  lea     ecx, [rdx+8]; unsigned int
0x180059836  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18005983b  mov     rsi, rax
0x18005983e  test    rax, rax
0x180059841  jz      short loc_180059863
0x180059843  mov     rcx, [rdi+10h]
0x180059847  mov     [rax], rcx
0x18005984a  mov     qword ptr [rax+8], 0
0x180059852  mov     dword ptr [rax+14h], 0FFFFFFFFh
0x180059859  mov     qword ptr [rax+28h], 0
0x180059861  jmp     short loc_180059865
0x180059863  xor     esi, esi
0x180059865  mov     [rdi+40h], rsi
0x180059869  test    rsi, rsi
0x18005986c  jz      short loc_1800598BF
0x18005986e  mov     rax, [rsi]
0x180059871  mov     rcx, [rax+40h]
0x180059875  add     rcx, 10h; this
0x180059879  call    ?GetDC@CDevDesc@@QEBAPEAUHDC__@@XZ; CDevDesc::GetDC(void)
0x18005987e  mov     [rsi+8], rax
0x180059882  test    rax, rax
0x180059885  jz      short loc_1800598BF
0x180059887  mov     edx, 5Ah ; 'Z'; index
0x18005988c  mov     rcx, rax; hdc
0x18005988f  call    cs:__imp_GetDeviceCaps
0x180059895  mov     rdx, [rsi+8]; hdc
0x180059899  lea     rcx, [rsi+28h]; this
0x18005989d  mov     r9d, 20h ; ' '; cy
0x1800598a3  mov     [rsi+10h], eax
0x1800598a6  mov     r8d, ebp; cx
0x1800598a9  mov     [rsi+18h], r9d
0x1800598ad  mov     [rsp+58h+color], 0FFFFFFFFh; color
0x1800598b5  call    ?Init@COffScreenDC@@QEAAPEAUHDC__@@PEAU2@JJK@Z; COffScreenDC::Init(HDC__ *,long,long,ulong)
0x1800598ba  test    rax, rax
0x1800598bd  jnz     short loc_1800598D5
0x1800598bf  mov     rcx, [rdi+40h]; this
0x1800598c3  test    rcx, rcx
0x1800598c6  jz      short loc_1800598CD
0x1800598c8  call    ??_GCDropCaret@@QEAAPEAXI@Z; CDropCaret::`scalar deleting destructor'(uint)
0x1800598cd  mov     qword ptr [rdi+40h], 0
0x1800598d5  mov     rcx, [rdi+10h]; this
0x1800598d9  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x1800598de  test    rax, rax
0x1800598e1  jz      short loc_1800598EF
0x1800598e3  mov     ecx, [rax+28h]
0x1800598e6  mov     [rdi+30h], ecx
0x1800598e9  mov     eax, [rax+58h]
0x1800598ec  mov     [rdi+34h], eax
0x1800598ef  mov     rax, [rdi]
0x1800598f2  mov     r8, rbx
0x1800598f5  mov     r9, [rsp+58h+arg_20]
0x1800598fd  mov     edx, r14d
0x180059900  bts     dword ptr [rdi+0Ch], 1Eh
0x180059905  mov     rcx, rdi
0x180059908  mov     rax, [rax+20h]
0x18005990c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059911  mov     ebp, eax
0x180059913  test    eax, eax
0x180059915  jz      short loc_180059934
0x180059917  mov     rcx, [rdi+18h]; this
0x18005991b  test    rcx, rcx
0x18005991e  jz      short loc_180059925
0x180059920  call    ??_GCCallMgr@@QEAAPEAXI@Z; CCallMgr::`scalar deleting destructor'(uint)
0x180059925  mov     qword ptr [rdi+18h], 0
0x18005992d  mov     dword ptr [rdi+0Ch], 0
0x180059934  mov     eax, ebp
0x180059936  add     rsp, 30h
0x18005993a  pop     r14
0x18005993c  pop     rdi
0x18005993d  pop     rsi
0x18005993e  pop     rbp
0x18005993f  pop     rbx
0x180059940  retn
0x180059941  mov     rax, [rdi+10h]
0x180059945  test    dword ptr [rax+0B4h], 8000000h
0x18005994f  jz      short loc_180059917
0x180059951  mov     rax, [rsp+58h+arg_20]
0x180059959  xor     ebp, ebp
0x18005995b  mov     [rax], ebp
0x18005995d  jmp     short loc_180059934
```
