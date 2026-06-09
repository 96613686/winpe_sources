# CDropTarget::UpdateEffect(ulong,_POINTL,ulong *)

- ea: `0x18005a1f8`
- end: `0x18005a47c`
- name: `?UpdateEffect@CDropTarget@@AEAAXKU_POINTL@@PEAK@Z`
- size: `644`
- prototype: `void __fastcall(CDropTarget *__hidden this, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180059a20`
- `0x180059d40`

## callees

- `0x18002bb70`
- `0x1800319c0`
- `0x180033060`
- `0x180046b1c`
- `0x18004a0c8`
- `0x18005634c`
- `0x18005a0a0`
- `0x18005a15c`
- `0x18005a1f8`
- `0x180092010`

## pseudocode

```c
void __fastcall CDropTarget::UpdateEffect(CDropTarget *this, unsigned int a2, struct _POINTL a3, unsigned int *a4)
{
  __int64 v5; // rcx
  __int64 v8; // rax
  __int64 v9; // r15
  int v10; // eax
  CDropCaret *v11; // rcx
  unsigned __int16 v12; // r14
  int v13; // eax
  CDropCaret *v14; // rcx
  int v15; // r12d
  struct CTxtEdit *v16; // rdx
  int IsProtected; // r14d
  int v18; // eax
  CTxtEdit *v19; // rcx
  int v20; // edx
  int v21; // ecx
  _BYTE v22[112]; // [rsp+50h] [rbp-39h] BYREF
  struct tagPOINT v23; // [rsp+F0h] [rbp+67h] BYREF

  v23 = 0;
  v5 = *((_QWORD *)this + 2);
  v8 = *(_QWORD *)(v5 + 136);
  if ( v8 )
    v9 = *(_QWORD *)(v8 + 32);
  else
    v9 = 0;
  v23 = (struct tagPOINT)a3;
  (*(void (__fastcall **)(_QWORD, struct tagPOINT *))(**(_QWORD **)(v5 + 48) + 160LL))(*(_QWORD *)(v5 + 48), &v23);
  v10 = (*(__int64 (__fastcall **)(_QWORD, struct tagPOINT, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 64LL) + 232LL))(
          *(_QWORD *)(*((_QWORD *)this + 2) + 64LL),
          v23,
          0,
          0,
          0,
          0,
          0,
          0,
          0);
  *((_DWORD *)this + 3) &= ~0x20000000u;
  *((_DWORD *)this + 14) = v10;
  if ( v10 > *((_DWORD *)this + 10) && v10 < *((_DWORD *)this + 11) )
    *((_DWORD *)this + 3) |= 0x20000000u;
  v11 = (CDropCaret *)*((_QWORD *)this + 8);
  v12 = CW32System::_nScrollInset;
  if ( v11 )
    CDropCaret::HideCaret(v11);
  v13 = CDisplay::AutoScroll(*(CDisplay **)(*((_QWORD *)this + 2) + 64LL), v23, v12, v12);
  v14 = (CDropCaret *)*((_QWORD *)this + 8);
  v15 = v13;
  if ( v14 )
  {
    if ( (*((_DWORD *)this + 3) & 0x20000000) != 0 || v13 )
      *((_DWORD *)v14 + 5) = -1;
    else
      CDropCaret::ShowCaret(v14);
  }
  v16 = (struct CTxtEdit *)*((_QWORD *)this + 2);
  if ( (*((_BYTE *)v16 + 180) & 1) != 0 )
  {
    CTxtRange::CTxtRange((CTxtRange *)v22, v16, *((_DWORD *)this + 14), 0);
    IsProtected = CTxtRange::IsProtected((CTxtRange *)v22, 1);
    if ( (IsProtected & 0xFFFFFFFD) == 0 )
    {
      CTxtRange::Advance((CTxtRange *)v22, -1);
      if ( !*((_DWORD *)this + 14) )
        goto LABEL_44;
      v18 = CTxtRange::IsProtected((CTxtRange *)v22, -1);
      IsProtected = v18;
      if ( !v18 )
      {
LABEL_22:
        *a4 = 0;
        CTxtRange::~CTxtRange((CTxtRange *)v22);
        goto LABEL_36;
      }
      if ( v18 == 2 )
      {
LABEL_44:
        if ( !IsProtected )
          goto LABEL_22;
        v19 = (CTxtEdit *)*((_QWORD *)this + 2);
        if ( (*((_DWORD *)v19 + 44) & 0x200000) == 0
          || (unsigned int)CTxtEdit::QueryUseProtection(v19, (struct CTxtRange *)v22, 0x200u, 0, 0) )
        {
          goto LABEL_22;
        }
      }
    }
    CTxtRange::~CTxtRange((CTxtRange *)v22);
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v9 + 88LL))(v9, 0, a2, a4);
    if ( ((*a4 - 1) & *a4) == 0 )
      goto LABEL_36;
  }
  v20 = *((_DWORD *)this + 3);
  v21 = v20 & 0x40000000;
  if ( v20 >= 0 && (!v21 || (*(_BYTE *)(*((_QWORD *)this + 2) + 180LL) & 4) != 0) )
  {
    *a4 = 0;
    *((_DWORD *)this + 14) = -1;
    return;
  }
  if ( (v20 & 0x20000000) != 0 || !v21 )
    goto LABEL_35;
  if ( (a2 & 8) != 0 )
  {
    if ( (a2 & 4) != 0 )
    {
LABEL_35:
      *a4 = 0;
      goto LABEL_36;
    }
  }
  else if ( (*(_BYTE *)a4 & 2) != 0 )
  {
    *a4 = 2;
    goto LABEL_36;
  }
  if ( (*(_BYTE *)a4 & 1) == 0 )
    goto LABEL_35;
  *a4 = 1;
LABEL_36:
  if ( v15 )
    *a4 |= 0x80000000;
}

```

## disassembly

```asm
0x18005a1f8  mov     [rsp-8+arg_8], rbx
0x18005a1fd  mov     [rsp-8+arg_10], rsi
0x18005a202  push    rbp
0x18005a203  push    rdi
0x18005a204  push    r12
0x18005a206  push    r14
0x18005a208  push    r15
0x18005a20a  lea     rbp, [rsp-37h]
0x18005a20f  sub     rsp, 0C0h
0x18005a216  mov     rbx, rcx
0x18005a219  mov     qword ptr [rbp+57h+arg_0.x], 0
0x18005a221  mov     rcx, [rcx+10h]
0x18005a225  mov     rdi, r9
0x18005a228  mov     esi, edx
0x18005a22a  mov     rax, [rcx+88h]
0x18005a231  test    rax, rax
0x18005a234  jz      short loc_18005A23C
0x18005a236  mov     r15, [rax+20h]
0x18005a23a  jmp     short loc_18005A23F
0x18005a23c  xor     r15d, r15d
0x18005a23f  mov     [rbp+57h+arg_0.x], r8d
0x18005a243  lea     rdx, [rbp+57h+arg_0]
0x18005a247  shr     r8, 20h
0x18005a24b  mov     [rbp+57h+arg_0.y], r8d
0x18005a24f  mov     rcx, [rcx+30h]
0x18005a253  mov     rax, [rcx]
0x18005a256  mov     rax, [rax+0A0h]
0x18005a25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a262  mov     rax, [rbx+10h]
0x18005a266  xor     r9d, r9d
0x18005a269  mov     rdx, qword ptr [rbp+57h+arg_0.x]
0x18005a26d  xor     r8d, r8d
0x18005a270  mov     [rsp+0E0h+var_A0], 0
0x18005a279  mov     [rsp+0E0h+var_A8], 0
0x18005a282  mov     rcx, [rax+40h]
0x18005a286  mov     [rsp+0E0h+var_B0], 0
0x18005a28f  mov     [rsp+0E0h+var_B8], 0
0x18005a297  mov     [rsp+0E0h+var_C0], 0
0x18005a2a0  mov     rax, [rcx]
0x18005a2a3  mov     rax, [rax+0E8h]
0x18005a2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2af  btr     dword ptr [rbx+0Ch], 1Dh
0x18005a2b4  mov     [rbx+38h], eax
0x18005a2b7  cmp     eax, [rbx+28h]
0x18005a2ba  jle     short loc_18005A2C6
0x18005a2bc  cmp     eax, [rbx+2Ch]
0x18005a2bf  jge     short loc_18005A2C6
0x18005a2c1  bts     dword ptr [rbx+0Ch], 1Dh
0x18005a2c6  mov     rcx, [rbx+40h]; this
0x18005a2ca  movzx   r14d, cs:?_nScrollInset@CW32System@@0GA; ushort CW32System::_nScrollInset
0x18005a2d2  test    rcx, rcx
0x18005a2d5  jz      short loc_18005A2DC
0x18005a2d7  call    ?HideCaret@CDropCaret@@QEAAXXZ; CDropCaret::HideCaret(void)
0x18005a2dc  mov     rcx, [rbx+10h]
0x18005a2e0  movzx   r9d, r14w; unsigned __int16
0x18005a2e4  mov     rdx, qword ptr [rbp+57h+arg_0.x]; struct tagPOINT
0x18005a2e8  movzx   r8d, r14w; unsigned __int16
0x18005a2ec  mov     rcx, [rcx+40h]; this
0x18005a2f0  call    ?AutoScroll@CDisplay@@QEAAHUtagPOINT@@GG@Z; CDisplay::AutoScroll(tagPOINT,ushort,ushort)
0x18005a2f5  mov     rcx, [rbx+40h]; this
0x18005a2f9  mov     r12d, eax
0x18005a2fc  test    rcx, rcx
0x18005a2ff  jz      short loc_18005A31C
0x18005a301  test    dword ptr [rbx+0Ch], 20000000h
0x18005a308  jnz     short loc_18005A315
0x18005a30a  test    eax, eax
0x18005a30c  jnz     short loc_18005A315
0x18005a30e  call    ?ShowCaret@CDropCaret@@QEAAXXZ; CDropCaret::ShowCaret(void)
0x18005a313  jmp     short loc_18005A31C
0x18005a315  mov     dword ptr [rcx+14h], 0FFFFFFFFh
0x18005a31c  mov     rdx, [rbx+10h]; struct CTxtEdit *
0x18005a320  test    byte ptr [rdx+0B4h], 1
0x18005a327  jz      loc_18005A3CD
0x18005a32d  mov     r8d, [rbx+38h]; int
0x18005a331  lea     rcx, [rbp+57h+var_90]; this
0x18005a335  xor     r9d, r9d; int
0x18005a338  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x18005a33d  mov     edx, 1; int
0x18005a342  lea     rcx, [rbp+57h+var_90]; this
0x18005a346  call    ?IsProtected@CTxtRange@@QEAAHJ@Z; CTxtRange::IsProtected(long)
0x18005a34b  mov     r14d, eax
0x18005a34e  test    eax, 0FFFFFFFDh
0x18005a353  jnz     short loc_18005A3C4
0x18005a355  or      edx, 0FFFFFFFFh; int
0x18005a358  lea     rcx, [rbp+57h+var_90]; this
0x18005a35c  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18005a361  cmp     dword ptr [rbx+38h], 0
0x18005a365  jz      short loc_18005A37F
0x18005a367  or      edx, 0FFFFFFFFh; int
0x18005a36a  lea     rcx, [rbp+57h+var_90]; this
0x18005a36e  call    ?IsProtected@CTxtRange@@QEAAHJ@Z; CTxtRange::IsProtected(long)
0x18005a373  mov     r14d, eax
0x18005a376  test    eax, eax
0x18005a378  jz      short loc_18005A3B3
0x18005a37a  cmp     eax, 2
0x18005a37d  jnz     short loc_18005A3C4
0x18005a37f  test    r14d, r14d
0x18005a382  jz      short loc_18005A3B3
0x18005a384  mov     rcx, [rbx+10h]; this
0x18005a388  test    dword ptr [rcx+0B0h], 200000h
0x18005a392  jz      short loc_18005A3B3
0x18005a394  xor     r9d, r9d; unsigned __int64
0x18005a397  mov     [rsp+0E0h+var_C0], 0; __int64
0x18005a3a0  mov     r8d, 200h; unsigned int
0x18005a3a6  lea     rdx, [rbp+57h+var_90]; struct CTxtRange *
0x18005a3aa  call    ?QueryUseProtection@CTxtEdit@@QEAAHPEAVCTxtRange@@I_K_J@Z; CTxtEdit::QueryUseProtection(CTxtRange *,uint,unsigned __int64,__int64)
0x18005a3af  test    eax, eax
0x18005a3b1  jz      short loc_18005A3C4
0x18005a3b3  lea     rcx, [rbp+57h+var_90]; this
0x18005a3b7  mov     dword ptr [rdi], 0
0x18005a3bd  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18005a3c2  jmp     short loc_18005A442
0x18005a3c4  lea     rcx, [rbp+57h+var_90]; this
0x18005a3c8  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18005a3cd  test    r15, r15
0x18005a3d0  jz      short loc_18005A3F2
0x18005a3d2  mov     rax, [r15]
0x18005a3d5  mov     r9, rdi
0x18005a3d8  mov     r8d, esi
0x18005a3db  xor     edx, edx
0x18005a3dd  mov     rcx, r15
0x18005a3e0  mov     rax, [rax+58h]
0x18005a3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3e9  mov     ecx, [rdi]
0x18005a3eb  lea     eax, [rcx-1]
0x18005a3ee  test    ecx, eax
0x18005a3f0  jz      short loc_18005A442
0x18005a3f2  mov     edx, [rbx+0Ch]
0x18005a3f5  mov     ecx, edx
0x18005a3f7  and     ecx, 40000000h
0x18005a3fd  test    edx, edx
0x18005a3ff  js      short loc_18005A421
0x18005a401  test    ecx, ecx
0x18005a403  jz      short loc_18005A412
0x18005a405  mov     rax, [rbx+10h]
0x18005a409  test    byte ptr [rax+0B4h], 4
0x18005a410  jz      short loc_18005A421
0x18005a412  mov     dword ptr [rdi], 0
0x18005a418  mov     dword ptr [rbx+38h], 0FFFFFFFFh
0x18005a41f  jmp     short loc_18005A44B
0x18005a421  bt      edx, 1Dh
0x18005a425  jb      short loc_18005A43C
0x18005a427  test    ecx, ecx
0x18005a429  jz      short loc_18005A43C
0x18005a42b  test    sil, 8
0x18005a42f  jz      short loc_18005A467
0x18005a431  test    sil, 4
0x18005a435  jnz     short loc_18005A43C
0x18005a437  test    byte ptr [rdi], 1
0x18005a43a  jnz     short loc_18005A474
0x18005a43c  mov     dword ptr [rdi], 0
0x18005a442  test    r12d, r12d
0x18005a445  jz      short loc_18005A44B
0x18005a447  bts     dword ptr [rdi], 1Fh
0x18005a44b  lea     r11, [rsp+0E0h+var_20]
0x18005a453  mov     rbx, [r11+38h]
0x18005a457  mov     rsi, [r11+40h]
0x18005a45b  mov     rsp, r11
0x18005a45e  pop     r15
0x18005a460  pop     r14
0x18005a462  pop     r12
0x18005a464  pop     rdi
0x18005a465  pop     rbp
0x18005a466  retn
0x18005a467  test    byte ptr [rdi], 2
0x18005a46a  jz      short loc_18005A437
0x18005a46c  mov     dword ptr [rdi], 2
0x18005a472  jmp     short loc_18005A442
0x18005a474  mov     dword ptr [rdi], 1
0x18005a47a  jmp     short loc_18005A442
```
