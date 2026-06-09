# CTxtEdit::MoveSelection(__int64,IUndoBuilder *)

- ea: `0x18004a97c`
- end: `0x18004ad7c`
- name: `?MoveSelection@CTxtEdit@@QEAAJ_JPEAVIUndoBuilder@@@Z`
- size: `1024`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, __int64, struct IUndoBuilder *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x180027b20`

## callees

- `0x1800066b0`
- `0x180015448`
- `0x180016470`
- `0x180016700`
- `0x1800182a0`
- `0x18002c5d8`
- `0x18002c650`
- `0x18003aa30`
- `0x180041cf8`
- `0x18004a284`
- `0x18004a97c`
- `0x18004ad84`
- `0x18004ae60`
- `0x18004b1dc`
- `0x18004b234`
- `0x18006e9a8`
- `0x18006f13c`
- `0x180073f6c`
- `0x180089fe0`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtEdit::MoveSelection(CTxtEdit *this, __int64 a2, struct IUndoBuilder *a3)
{
  int *Sel; // rax
  int *v7; // rdi
  unsigned int v8; // r14d
  int Expanded; // eax
  int v10; // eax
  unsigned int v11; // eax
  struct IDataObject *v12; // r12
  unsigned int v13; // ebx
  __int64 v14; // rax
  int v15; // r13d
  int v16; // ebx
  int v17; // eax
  int v18; // edi
  int v19; // ebx
  int v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  struct IDataObject *v26; // [rsp+50h] [rbp-B0h] BYREF
  CDisplay *v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[40]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B8h] [rbp-48h]
  __int16 v33; // [rsp+C2h] [rbp-3Eh]
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-20h]
  _BYTE v36[160]; // [rsp+F0h] [rbp-10h] BYREF
  int v37; // [rsp+1A0h] [rbp+A0h] BYREF
  int v38; // [rsp+1B8h] [rbp+B8h]

  v27 = (CDisplay *)*((_QWORD *)this + 8);
  CDisplay::Freeze(v27);
  Sel = (int *)CTxtEdit::GetSel(this);
  v7 = Sel;
  if ( Sel )
  {
    v25 = Sel[22];
    v37 = 0;
    v38 = Sel[10];
    v24 = 0;
    v26 = 0;
    CTxtRange::CTxtRange((CTxtRange *)v28, (const struct CTxtRange *)Sel);
    if ( a3 )
      (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a3 + 48LL))(a3);
    v8 = 1;
    CTxtRange::Expander((CTxtRange *)v28, 4, 1, 0, &v24, &v37);
    v35 = v30;
    v34 = v31;
    Expanded = CPFRunPtr::FindExpanded((CPFRunPtr *)&v34);
    if ( Expanded < 0 )
      Expanded = 0x3FFFFFFF;
    v33 |= 1u;
    CTxtRange::Advance((CTxtRange *)v28, Expanded);
    v10 = v29;
    if ( v32 < 0 )
      v10 = v29 - v32;
    v37 = v10;
    if ( a2 > 0 && v10 == *((_DWORD *)this + 68) )
    {
      CTxtEdit::Beep(this);
      CTxtRange::~CTxtRange((CTxtRange *)v28);
    }
    else
    {
      v11 = CLightDTEngine::RangeToDataObject((CTxtEdit *)((char *)this + 96), (struct CTxtRange *)v28, 2, &v26);
      v12 = v26;
      v13 = v11;
      if ( !v11 )
      {
        v14 = *(_QWORD *)v7;
        if ( a2 <= 0 )
          (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(v14 + 264))(v7, 4, 0, 0);
        else
          (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(v14 + 272))(v7, 4, 0, 0);
        v21 = v7[10];
        v13 = (*(__int64 (__fastcall **)(int *, __int64, _QWORD))(*(_QWORD *)v7 + 280LL))(v7, 4, (unsigned int)a2);
        if ( v7[10] == v21 )
        {
          CTxtRange::Set((CTxtRange *)v7, v38, v25);
          CTxtEdit::Beep(this);
        }
        else
        {
          v15 = 0;
          if ( v7[10] >= v21 )
          {
            if ( !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(v7 + 6)) )
            {
              *((_WORD *)v7 + 49) &= ~1u;
              CTxtRange::Advance((CTxtRange *)v7, 0x3FFFFFFF);
              CTxtRange::CTxtRange((CTxtRange *)v36, (const struct CTxtRange *)v7);
              CTxtRange::ReplaceRange(v36, 1, &szCR, a3, 1, 0, 0);
              CTxtRange::Advance((CTxtRange *)v7, 1);
              v15 = 1;
              CTxtRange::~CTxtRange((CTxtRange *)v36);
            }
          }
          else
          {
            (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 264LL))(v7, 4, 0, 0);
          }
          v22 = v7[10];
          v13 = CLightDTEngine::PasteDataObjectToRange(
                  (CTxtEdit *)((char *)this + 96),
                  v12,
                  (struct CTxtRange *)v7,
                  0,
                  0,
                  a3,
                  0);
          if ( !v13 )
          {
            if ( v15 )
            {
              CTxtRange::CTxtRange((CTxtRange *)v36, (const struct CTxtRange *)v7);
              CTxtRange::Delete((CTxtRange *)v36, 1, -1, (int *)&v26);
              CTxtRange::~CTxtRange((CTxtRange *)v36);
            }
            v16 = v7[10];
            CTxtRange::Set((CTxtRange *)v7, v22, 0);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v7, a3);
            CTxtRange::Set((CTxtRange *)v7, v16, 0);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v7, a3);
            v17 = v16 - (v37 - v24);
            v24 = v37 - v24;
            if ( v38 >= v22 )
              v17 = v16;
            v23 = v17;
            CTxtRange::Set((CTxtRange *)v7, v15 + v7[10], v24);
            v18 = v29;
            if ( v32 < 0 )
              v18 = v29 - v32;
            v19 = *((_DWORD *)this + 68);
            CTxtRange::ReplaceRange(v28, 0, 0, a3, 1, 0, 0);
            if ( v18 == v19 )
              CTxtRange::DeleteTerminatingEOP((CTxtRange *)v28, a3);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v28, a3);
            if ( a3 )
              HandleSelectionAEInfo(this, a3, (unsigned int)v38, (unsigned int)v25, v23, v24, 2);
            v13 = 0;
          }
        }
      }
      if ( v12 )
        ((void (__fastcall *)(struct IDataObject *))v12->lpVtbl->Release)(v12);
      CTxtRange::~CTxtRange((CTxtRange *)v28);
      v8 = v13;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CDisplay::Thaw(v27);
  return v8;
}

```

## disassembly

```asm
0x18004a97c  mov     [rsp-8+arg_8], rbx
0x18004a981  push    rbp
0x18004a982  push    rsi
0x18004a983  push    rdi
0x18004a984  push    r12
0x18004a986  push    r13
0x18004a988  push    r14
0x18004a98a  push    r15
0x18004a98c  lea     rbp, [rsp-60h]
0x18004a991  sub     rsp, 160h
0x18004a998  mov     rax, [rcx+40h]
0x18004a99c  mov     r15, rcx
0x18004a99f  mov     rcx, rax; this
0x18004a9a2  mov     [rsp+190h+var_138], rax
0x18004a9a7  mov     rsi, r8
0x18004a9aa  mov     r13, rdx
0x18004a9ad  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18004a9b2  mov     rcx, r15; this
0x18004a9b5  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18004a9ba  xor     ebx, ebx
0x18004a9bc  mov     rdi, rax
0x18004a9bf  test    rax, rax
0x18004a9c2  jnz     short loc_18004A9CF
0x18004a9c4  mov     r14d, 8007000Eh
0x18004a9ca  jmp     loc_18004AD53
0x18004a9cf  mov     eax, [rax+58h]
0x18004a9d2  lea     rcx, [rsp+190h+var_130]; this
0x18004a9d7  mov     [rsp+190h+var_148], eax
0x18004a9db  mov     rdx, rdi; struct CTxtRange *
0x18004a9de  mov     [rbp+90h+arg_0], ebx
0x18004a9e4  mov     eax, [rdi+28h]
0x18004a9e7  mov     [rbp+90h+arg_18], eax
0x18004a9ed  mov     [rsp+190h+var_14C], ebx
0x18004a9f1  mov     [rsp+190h+var_140], rbx
0x18004a9f6  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x18004a9fb  test    rsi, rsi
0x18004a9fe  jz      short loc_18004AA0F
0x18004aa00  mov     rax, [rsi]
0x18004aa03  mov     rcx, rsi
0x18004aa06  mov     rax, [rax+30h]
0x18004aa0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa0f  xor     r9d, r9d; int *
0x18004aa12  lea     rax, [rbp+90h+arg_0]
0x18004aa19  mov     [rsp+190h+var_168], rax; int *
0x18004aa1e  lea     rcx, [rsp+190h+var_130]; this
0x18004aa23  lea     rax, [rsp+190h+var_14C]
0x18004aa28  mov     [rsp+190h+var_170], rax; int *
0x18004aa2d  lea     r14d, [r9+1]
0x18004aa31  mov     r8d, r14d; int
0x18004aa34  lea     edx, [r9+4]; int
0x18004aa38  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18004aa3d  movups  xmm0, [rbp+90h+var_E8]
0x18004aa41  mov     rax, [rbp+90h+var_100]
0x18004aa45  lea     rcx, [rbp+90h+var_C0]; this
0x18004aa49  mov     [rbp+90h+var_B0], rax
0x18004aa4d  movdqu  [rbp+90h+var_C0], xmm0
0x18004aa52  call    ?FindExpanded@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpanded(void)
0x18004aa57  test    eax, eax
0x18004aa59  mov     ecx, 3FFFFFFFh
0x18004aa5e  cmovs   eax, ecx
0x18004aa61  or      [rbp+90h+var_CE], r14w
0x18004aa66  mov     edx, eax; int
0x18004aa68  lea     rcx, [rsp+190h+var_130]; this
0x18004aa6d  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18004aa72  mov     ecx, [rbp+90h+var_D8]
0x18004aa75  mov     eax, [rbp+90h+var_108]
0x18004aa78  test    ecx, ecx
0x18004aa7a  jns     short loc_18004AA7E
0x18004aa7c  sub     eax, ecx
0x18004aa7e  mov     [rbp+90h+arg_0], eax
0x18004aa84  test    r13, r13
0x18004aa87  jle     short loc_18004AAA9
0x18004aa89  cmp     eax, [r15+110h]
0x18004aa90  jnz     short loc_18004AAA9
0x18004aa92  mov     rcx, r15; this
0x18004aa95  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18004aa9a  lea     rcx, [rsp+190h+var_130]; this
0x18004aa9f  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18004aaa4  jmp     loc_18004AD53
0x18004aaa9  lea     rcx, [r15+60h]; this
0x18004aaad  mov     r8d, 2; int
0x18004aab3  lea     r9, [rsp+190h+var_140]; struct IDataObject **
0x18004aab8  lea     rdx, [rsp+190h+var_130]; struct CTxtRange *
0x18004aabd  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x18004aac2  mov     r12, [rsp+190h+var_140]
0x18004aac7  mov     ebx, eax
0x18004aac9  test    eax, eax
0x18004aacb  jnz     loc_18004AD31
0x18004aad1  mov     rax, [rdi]
0x18004aad4  lea     edx, [rbx+4]
0x18004aad7  xor     r9d, r9d
0x18004aada  xor     r8d, r8d
0x18004aadd  mov     rcx, rdi
0x18004aae0  test    r13, r13
0x18004aae3  jle     short loc_18004AAEE
0x18004aae5  mov     rax, [rax+110h]
0x18004aaec  jmp     short loc_18004AAF5
0x18004aaee  mov     rax, [rax+108h]
0x18004aaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aafa  mov     eax, [rdi+28h]
0x18004aafd  xor     r9d, r9d
0x18004ab00  mov     [rsp+190h+var_150], eax
0x18004ab04  mov     r8d, r13d
0x18004ab07  mov     rax, [rdi]
0x18004ab0a  mov     rcx, rdi
0x18004ab0d  lea     edx, [r9+4]
0x18004ab11  mov     rax, [rax+118h]
0x18004ab18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab1d  mov     ebx, eax
0x18004ab1f  mov     eax, [rsp+190h+var_150]
0x18004ab23  cmp     [rdi+28h], eax
0x18004ab26  jnz     short loc_18004AB48
0x18004ab28  mov     r8d, [rsp+190h+var_148]; int
0x18004ab2d  mov     rcx, rdi; this
0x18004ab30  mov     edx, [rbp+90h+arg_18]; int
0x18004ab36  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18004ab3b  mov     rcx, r15; this
0x18004ab3e  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18004ab43  jmp     loc_18004AD31
0x18004ab48  xor     ebx, ebx
0x18004ab4a  mov     r13d, ebx
0x18004ab4d  cmp     [rdi+28h], eax
0x18004ab50  jge     short loc_18004AB6F
0x18004ab52  mov     rax, [rdi]
0x18004ab55  lea     edx, [rbx+4]
0x18004ab58  xor     r9d, r9d
0x18004ab5b  xor     r8d, r8d
0x18004ab5e  mov     rcx, rdi
0x18004ab61  mov     rax, [rax+108h]
0x18004ab68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab6d  jmp     short loc_18004ABD9
0x18004ab6f  lea     rcx, [rdi+18h]; this
0x18004ab73  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18004ab78  test    eax, eax
0x18004ab7a  jnz     short loc_18004ABD9
0x18004ab7c  mov     eax, 0FFFEh
0x18004ab81  mov     edx, 3FFFFFFFh; int
0x18004ab86  and     [rdi+62h], ax
0x18004ab8a  mov     rcx, rdi; this
0x18004ab8d  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18004ab92  mov     rdx, rdi; struct CTxtRange *
0x18004ab95  lea     rcx, [rbp+90h+var_A0]; this
0x18004ab99  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x18004ab9e  mov     [rsp+190h+var_160], ebx
0x18004aba2  lea     r8, ?szCR@@3QBGB; ushort const near * const szCR
0x18004aba9  mov     [rsp+190h+var_168], rbx
0x18004abae  lea     rcx, [rbp+90h+var_A0]
0x18004abb2  mov     r9, rsi
0x18004abb5  mov     dword ptr [rsp+190h+var_170], r14d
0x18004abba  mov     edx, r14d
0x18004abbd  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x18004abc2  mov     edx, r14d; int
0x18004abc5  mov     rcx, rdi; this
0x18004abc8  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18004abcd  lea     rcx, [rbp+90h+var_A0]; this
0x18004abd1  mov     r13d, r14d
0x18004abd4  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18004abd9  mov     eax, [rdi+28h]
0x18004abdc  lea     rcx, [r15+60h]; this
0x18004abe0  mov     [rsp+190h+var_160], ebx; unsigned int
0x18004abe4  xor     r9d, r9d; unsigned __int16
0x18004abe7  mov     [rsp+190h+var_168], rsi; struct IUndoBuilder *
0x18004abec  mov     r8, rdi; struct CTxtRange *
0x18004abef  mov     rdx, r12; struct IDataObject *
0x18004abf2  mov     [rsp+190h+var_170], rbx; struct _repastespecial *
0x18004abf7  mov     [rsp+190h+var_150], eax
0x18004abfb  call    ?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z; CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)
0x18004ac00  mov     ebx, eax
0x18004ac02  test    eax, eax
0x18004ac04  jnz     loc_18004AD31
0x18004ac0a  test    r13d, r13d
0x18004ac0d  jz      short loc_18004AC39
0x18004ac0f  mov     rdx, rdi; struct CTxtRange *
0x18004ac12  lea     rcx, [rbp+90h+var_A0]; this
0x18004ac16  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x18004ac1b  lea     r9, [rsp+190h+var_140]; int *
0x18004ac20  or      r8d, 0FFFFFFFFh; int
0x18004ac24  mov     edx, r14d; int
0x18004ac27  lea     rcx, [rbp+90h+var_A0]; this
0x18004ac2b  call    ?Delete@CTxtRange@@UEAAJJJPEAJ@Z; CTxtRange::Delete(long,long,long *)
0x18004ac30  lea     rcx, [rbp+90h+var_A0]; this
0x18004ac34  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18004ac39  mov     edx, [rsp+190h+var_150]; int
0x18004ac3d  xor     r8d, r8d; int
0x18004ac40  mov     ebx, [rdi+28h]
0x18004ac43  mov     rcx, rdi; this
0x18004ac46  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18004ac4b  mov     rdx, rsi; struct IUndoBuilder *
0x18004ac4e  mov     rcx, rdi; this
0x18004ac51  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x18004ac56  xor     r8d, r8d; int
0x18004ac59  mov     edx, ebx; int
0x18004ac5b  mov     rcx, rdi; this
0x18004ac5e  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18004ac63  mov     rdx, rsi; struct IUndoBuilder *
0x18004ac66  mov     rcx, rdi; this
0x18004ac69  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x18004ac6e  mov     edx, [rsp+190h+var_150]
0x18004ac72  mov     eax, ebx
0x18004ac74  mov     ecx, [rbp+90h+arg_0]
0x18004ac7a  sub     ecx, [rsp+190h+var_14C]
0x18004ac7e  sub     eax, ecx
0x18004ac80  mov     [rsp+190h+var_14C], ecx
0x18004ac84  cmp     [rbp+90h+arg_18], edx
0x18004ac8a  mov     r8d, ecx; int
0x18004ac8d  mov     edx, [rdi+28h]
0x18004ac90  mov     rcx, rdi; this
0x18004ac93  cmovge  eax, ebx
0x18004ac96  add     edx, r13d; int
0x18004ac99  mov     [rsp+190h+var_150], eax
0x18004ac9d  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18004aca2  mov     eax, [rbp+90h+var_D8]
0x18004aca5  mov     edi, [rbp+90h+var_108]
0x18004aca8  test    eax, eax
0x18004acaa  jns     short loc_18004ACAE
0x18004acac  sub     edi, eax
0x18004acae  mov     ebx, [r15+110h]
0x18004acb5  lea     rcx, [rsp+190h+var_130]
0x18004acba  mov     [rsp+190h+var_160], 0
0x18004acc2  mov     r9, rsi
0x18004acc5  mov     [rsp+190h+var_168], 0
0x18004acce  xor     r8d, r8d
0x18004acd1  xor     edx, edx
0x18004acd3  mov     dword ptr [rsp+190h+var_170], r14d
0x18004acd8  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x18004acdd  cmp     edi, ebx
0x18004acdf  jnz     short loc_18004ACEE
0x18004ace1  mov     rdx, rsi; struct IUndoBuilder *
0x18004ace4  lea     rcx, [rsp+190h+var_130]; this
0x18004ace9  call    ?DeleteTerminatingEOP@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::DeleteTerminatingEOP(IUndoBuilder *)
0x18004acee  mov     rdx, rsi; struct IUndoBuilder *
0x18004acf1  lea     rcx, [rsp+190h+var_130]; this
0x18004acf6  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x18004acfb  test    rsi, rsi
0x18004acfe  jz      short loc_18004AD2F
0x18004ad00  mov     eax, [rsp+190h+var_14C]
0x18004ad04  mov     rdx, rsi
0x18004ad07  mov     r9d, [rsp+190h+var_148]
0x18004ad0c  mov     rcx, r15
0x18004ad0f  mov     r8d, [rbp+90h+arg_18]
0x18004ad16  mov     [rsp+190h+var_160], 2
0x18004ad1e  mov     dword ptr [rsp+190h+var_168], eax
0x18004ad22  mov     eax, [rsp+190h+var_150]
0x18004ad26  mov     dword ptr [rsp+190h+var_170], eax
0x18004ad2a  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x18004ad2f  xor     ebx, ebx
0x18004ad31  test    r12, r12
0x18004ad34  jz      short loc_18004AD46
0x18004ad36  mov     rax, [r12]
0x18004ad3a  mov     rcx, r12
0x18004ad3d  mov     rax, [rax+10h]
0x18004ad41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ad46  lea     rcx, [rsp+190h+var_130]; this
0x18004ad4b  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18004ad50  mov     r14d, ebx
0x18004ad53  mov     rcx, [rsp+190h+var_138]; this
0x18004ad58  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x18004ad5d  mov     rbx, [rsp+190h+arg_8]
0x18004ad65  mov     eax, r14d
0x18004ad68  add     rsp, 160h
0x18004ad6f  pop     r15
0x18004ad71  pop     r14
0x18004ad73  pop     r13
0x18004ad75  pop     r12
0x18004ad77  pop     rdi
0x18004ad78  pop     rsi
0x18004ad79  pop     rbp
0x18004ad7a  retn
```
