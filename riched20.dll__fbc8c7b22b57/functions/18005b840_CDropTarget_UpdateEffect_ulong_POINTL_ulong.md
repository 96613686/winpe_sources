# CDropTarget::UpdateEffect(ulong,_POINTL,ulong *)

- ea: `0x18005b840`
- end: `0x18005bab1`
- name: `?UpdateEffect@CDropTarget@@AEAAXKU_POINTL@@PEAK@Z`
- size: `625`
- prototype: `void __fastcall(CDropTarget *__hidden this, unsigned int, struct _POINTL, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18005b000`
- `0x18005b350`

## callees

- `0x180026344`
- `0x18002c5d8`
- `0x18002dce0`
- `0x180047ba8`
- `0x18004b234`
- `0x1800559d8`
- `0x1800578cc`
- `0x18005b6c0`
- `0x18005b77c`
- `0x18005b840`
- `0x180095010`

## pseudocode

```c
void __fastcall CDropTarget::UpdateEffect(CDropTarget *this, unsigned int a2, struct _POINTL a3, unsigned int *a4)
{
  struct IRichEditOleCallback *RECallback; // rax
  struct tagPOINT v8; // r8
  __int64 v9; // rcx
  struct IRichEditOleCallback *v10; // r12
  int v11; // eax
  CDropCaret *v12; // rcx
  unsigned __int16 v13; // r14
  int v14; // eax
  CDropCaret *v15; // rcx
  int v16; // r15d
  struct CTxtEdit *v17; // rdx
  int IsProtected; // r14d
  int v19; // eax
  CTxtEdit *v20; // rcx
  int v21; // edx
  int v22; // ecx
  _BYTE v23[112]; // [rsp+50h] [rbp-39h] BYREF
  struct tagPOINT v24; // [rsp+F0h] [rbp+67h] BYREF

  v24 = 0;
  RECallback = CTxtEdit::GetRECallback(*((CTxtEdit **)this + 2));
  v24 = v8;
  v10 = RECallback;
  (*(void (__fastcall **)(_QWORD, struct tagPOINT *))(**(_QWORD **)(v9 + 48) + 160LL))(*(_QWORD *)(v9 + 48), &v24);
  v11 = (*(__int64 (__fastcall **)(_QWORD, struct tagPOINT, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 64LL) + 232LL))(
          *(_QWORD *)(*((_QWORD *)this + 2) + 64LL),
          v24,
          0,
          0,
          0,
          0,
          0,
          0,
          0);
  *((_DWORD *)this + 3) &= ~0x20000000u;
  *((_DWORD *)this + 14) = v11;
  if ( v11 > *((_DWORD *)this + 10) && v11 < *((_DWORD *)this + 11) )
    *((_DWORD *)this + 3) |= 0x20000000u;
  v12 = (CDropCaret *)*((_QWORD *)this + 8);
  v13 = CW32System::_nScrollInset;
  if ( v12 )
    CDropCaret::HideCaret(v12);
  v14 = CDisplay::AutoScroll(*(CDisplay **)(*((_QWORD *)this + 2) + 64LL), v24, v13, v13);
  v15 = (CDropCaret *)*((_QWORD *)this + 8);
  v16 = v14;
  if ( v15 )
  {
    if ( (*((_DWORD *)this + 3) & 0x20000000) != 0 || v14 )
      *((_DWORD *)v15 + 5) = -1;
    else
      CDropCaret::ShowCaret(v15);
  }
  v17 = (struct CTxtEdit *)*((_QWORD *)this + 2);
  if ( (*((_BYTE *)v17 + 180) & 1) != 0 )
  {
    CTxtRange::CTxtRange((CTxtRange *)v23, v17, *((_DWORD *)this + 14), 0);
    IsProtected = CTxtRange::IsProtected((CTxtRange *)v23, 1);
    if ( (IsProtected & 0xFFFFFFFD) == 0 )
    {
      CTxtRange::Advance((CTxtRange *)v23, -1);
      if ( !*((_DWORD *)this + 14) )
        goto LABEL_41;
      v19 = CTxtRange::IsProtected((CTxtRange *)v23, -1);
      IsProtected = v19;
      if ( !v19 )
      {
LABEL_19:
        *a4 = 0;
        CTxtRange::~CTxtRange((CTxtRange *)v23);
        goto LABEL_33;
      }
      if ( v19 == 2 )
      {
LABEL_41:
        if ( !IsProtected )
          goto LABEL_19;
        v20 = (CTxtEdit *)*((_QWORD *)this + 2);
        if ( (*((_DWORD *)v20 + 44) & 0x200000) == 0
          || (unsigned int)CTxtEdit::QueryUseProtection(v20, (struct CTxtRange *)v23, 0x200u, 0, 0) )
        {
          goto LABEL_19;
        }
      }
    }
    CTxtRange::~CTxtRange((CTxtRange *)v23);
  }
  if ( v10 )
  {
    ((void (__fastcall *)(struct IRichEditOleCallback *, _QWORD, _QWORD, unsigned int *))v10->lpVtbl->GetDragDropEffect)(
      v10,
      0,
      a2,
      a4);
    if ( ((*a4 - 1) & *a4) == 0 )
      goto LABEL_33;
  }
  v21 = *((_DWORD *)this + 3);
  v22 = v21 & 0x40000000;
  if ( v21 >= 0 && (!v22 || (*(_BYTE *)(*((_QWORD *)this + 2) + 180LL) & 4) != 0) )
  {
    *a4 = 0;
    *((_DWORD *)this + 14) = -1;
    return;
  }
  if ( (v21 & 0x20000000) != 0 || !v22 )
    goto LABEL_32;
  if ( (a2 & 8) != 0 )
  {
    if ( (a2 & 4) != 0 )
    {
LABEL_32:
      *a4 = 0;
      goto LABEL_33;
    }
  }
  else if ( (*(_BYTE *)a4 & 2) != 0 )
  {
    *a4 = 2;
    goto LABEL_33;
  }
  if ( (*(_BYTE *)a4 & 1) == 0 )
    goto LABEL_32;
  *a4 = 1;
LABEL_33:
  if ( v16 )
    *a4 |= 0x80000000;
}

```

## disassembly

```asm
0x18005b840  mov     [rsp-8+arg_8], rbx
0x18005b845  mov     [rsp-8+arg_10], rsi
0x18005b84a  push    rbp
0x18005b84b  push    rdi
0x18005b84c  push    r12
0x18005b84e  push    r14
0x18005b850  push    r15
0x18005b852  lea     rbp, [rsp-37h]
0x18005b857  sub     rsp, 0C0h
0x18005b85e  mov     rdi, rcx
0x18005b861  mov     qword ptr [rbp+57h+arg_0.x], 0
0x18005b869  mov     rcx, [rcx+10h]; this
0x18005b86d  mov     rbx, r9
0x18005b870  mov     esi, edx
0x18005b872  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18005b877  mov     qword ptr [rbp+57h+arg_0.x], r8
0x18005b87b  lea     rdx, [rbp+57h+arg_0]
0x18005b87f  mov     rcx, [rcx+30h]
0x18005b883  mov     r12, rax
0x18005b886  mov     r8, [rcx]
0x18005b889  mov     rax, [r8+0A0h]
0x18005b890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b895  mov     rcx, [rdi+10h]
0x18005b899  xor     r9d, r9d
0x18005b89c  mov     [rsp+0E0h+var_A0], 0
0x18005b8a5  xor     r8d, r8d
0x18005b8a8  mov     [rsp+0E0h+var_A8], 0
0x18005b8b1  mov     [rsp+0E0h+var_B0], 0
0x18005b8ba  mov     rcx, [rcx+40h]
0x18005b8be  mov     [rsp+0E0h+var_B8], 0
0x18005b8c6  mov     [rsp+0E0h+var_C0], 0
0x18005b8cf  mov     rdx, [rcx]
0x18005b8d2  mov     rax, [rdx+0E8h]
0x18005b8d9  mov     rdx, qword ptr [rbp+57h+arg_0.x]
0x18005b8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b8e2  btr     dword ptr [rdi+0Ch], 1Dh
0x18005b8e7  mov     [rdi+38h], eax
0x18005b8ea  cmp     eax, [rdi+28h]
0x18005b8ed  jle     short loc_18005B8F9
0x18005b8ef  cmp     eax, [rdi+2Ch]
0x18005b8f2  jge     short loc_18005B8F9
0x18005b8f4  bts     dword ptr [rdi+0Ch], 1Dh
0x18005b8f9  mov     rcx, [rdi+40h]; this
0x18005b8fd  movzx   r14d, cs:?_nScrollInset@CW32System@@0GA; ushort CW32System::_nScrollInset
0x18005b905  test    rcx, rcx
0x18005b908  jz      short loc_18005B90F
0x18005b90a  call    ?HideCaret@CDropCaret@@QEAAXXZ; CDropCaret::HideCaret(void)
0x18005b90f  mov     rcx, [rdi+10h]
0x18005b913  movzx   r9d, r14w; unsigned __int16
0x18005b917  mov     rdx, qword ptr [rbp+57h+arg_0.x]; struct tagPOINT
0x18005b91b  movzx   r8d, r14w; unsigned __int16
0x18005b91f  mov     rcx, [rcx+40h]; this
0x18005b923  call    ?AutoScroll@CDisplay@@QEAAHUtagPOINT@@GG@Z; CDisplay::AutoScroll(tagPOINT,ushort,ushort)
0x18005b928  mov     rcx, [rdi+40h]; this
0x18005b92c  mov     r15d, eax
0x18005b92f  test    rcx, rcx
0x18005b932  jz      short loc_18005B94F
0x18005b934  test    dword ptr [rdi+0Ch], 20000000h
0x18005b93b  jnz     short loc_18005B948
0x18005b93d  test    eax, eax
0x18005b93f  jnz     short loc_18005B948
0x18005b941  call    ?ShowCaret@CDropCaret@@QEAAXXZ; CDropCaret::ShowCaret(void)
0x18005b946  jmp     short loc_18005B94F
0x18005b948  mov     dword ptr [rcx+14h], 0FFFFFFFFh
0x18005b94f  mov     rdx, [rdi+10h]; struct CTxtEdit *
0x18005b953  test    byte ptr [rdx+0B4h], 1
0x18005b95a  jz      loc_18005BA00
0x18005b960  mov     r8d, [rdi+38h]; int
0x18005b964  lea     rcx, [rbp+57h+var_90]; this
0x18005b968  xor     r9d, r9d; int
0x18005b96b  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x18005b970  mov     edx, 1; int
0x18005b975  lea     rcx, [rbp+57h+var_90]; this
0x18005b979  call    ?IsProtected@CTxtRange@@QEAAHJ@Z; CTxtRange::IsProtected(long)
0x18005b97e  mov     r14d, eax
0x18005b981  test    eax, 0FFFFFFFDh
0x18005b986  jnz     short loc_18005B9F7
0x18005b988  or      edx, 0FFFFFFFFh; int
0x18005b98b  lea     rcx, [rbp+57h+var_90]; this
0x18005b98f  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18005b994  cmp     dword ptr [rdi+38h], 0
0x18005b998  jz      short loc_18005B9B2
0x18005b99a  or      edx, 0FFFFFFFFh; int
0x18005b99d  lea     rcx, [rbp+57h+var_90]; this
0x18005b9a1  call    ?IsProtected@CTxtRange@@QEAAHJ@Z; CTxtRange::IsProtected(long)
0x18005b9a6  mov     r14d, eax
0x18005b9a9  test    eax, eax
0x18005b9ab  jz      short loc_18005B9E6
0x18005b9ad  cmp     eax, 2
0x18005b9b0  jnz     short loc_18005B9F7
0x18005b9b2  test    r14d, r14d
0x18005b9b5  jz      short loc_18005B9E6
0x18005b9b7  mov     rcx, [rdi+10h]; this
0x18005b9bb  test    dword ptr [rcx+0B0h], 200000h
0x18005b9c5  jz      short loc_18005B9E6
0x18005b9c7  xor     r9d, r9d; unsigned __int64
0x18005b9ca  mov     [rsp+0E0h+var_C0], 0; __int64
0x18005b9d3  mov     r8d, 200h; unsigned int
0x18005b9d9  lea     rdx, [rbp+57h+var_90]; struct CTxtRange *
0x18005b9dd  call    ?QueryUseProtection@CTxtEdit@@QEAAHPEAVCTxtRange@@I_K_J@Z; CTxtEdit::QueryUseProtection(CTxtRange *,uint,unsigned __int64,__int64)
0x18005b9e2  test    eax, eax
0x18005b9e4  jz      short loc_18005B9F7
0x18005b9e6  lea     rcx, [rbp+57h+var_90]; this
0x18005b9ea  mov     dword ptr [rbx], 0
0x18005b9f0  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18005b9f5  jmp     short loc_18005BA76
0x18005b9f7  lea     rcx, [rbp+57h+var_90]; this
0x18005b9fb  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18005ba00  test    r12, r12
0x18005ba03  jz      short loc_18005BA26
0x18005ba05  mov     rax, [r12]
0x18005ba09  mov     r9, rbx
0x18005ba0c  mov     r8d, esi
0x18005ba0f  xor     edx, edx
0x18005ba11  mov     rcx, r12
0x18005ba14  mov     rax, [rax+58h]
0x18005ba18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba1d  mov     ecx, [rbx]
0x18005ba1f  lea     eax, [rcx-1]
0x18005ba22  test    ecx, eax
0x18005ba24  jz      short loc_18005BA76
0x18005ba26  mov     edx, [rdi+0Ch]
0x18005ba29  mov     ecx, edx
0x18005ba2b  and     ecx, 40000000h
0x18005ba31  test    edx, edx
0x18005ba33  js      short loc_18005BA55
0x18005ba35  test    ecx, ecx
0x18005ba37  jz      short loc_18005BA46
0x18005ba39  mov     rax, [rdi+10h]
0x18005ba3d  test    byte ptr [rax+0B4h], 4
0x18005ba44  jz      short loc_18005BA55
0x18005ba46  mov     dword ptr [rbx], 0
0x18005ba4c  mov     dword ptr [rdi+38h], 0FFFFFFFFh
0x18005ba53  jmp     short loc_18005BA7F
0x18005ba55  bt      edx, 1Dh
0x18005ba59  jb      short loc_18005BA70
0x18005ba5b  test    ecx, ecx
0x18005ba5d  jz      short loc_18005BA70
0x18005ba5f  test    sil, 8
0x18005ba63  jz      short loc_18005BA9C
0x18005ba65  test    sil, 4
0x18005ba69  jnz     short loc_18005BA70
0x18005ba6b  test    byte ptr [rbx], 1
0x18005ba6e  jnz     short loc_18005BAA9
0x18005ba70  mov     dword ptr [rbx], 0
0x18005ba76  test    r15d, r15d
0x18005ba79  jz      short loc_18005BA7F
0x18005ba7b  bts     dword ptr [rbx], 1Fh
0x18005ba7f  lea     r11, [rsp+0E0h+var_20]
0x18005ba87  mov     rbx, [r11+38h]
0x18005ba8b  mov     rsi, [r11+40h]
0x18005ba8f  mov     rsp, r11
0x18005ba92  pop     r15
0x18005ba94  pop     r14
0x18005ba96  pop     r12
0x18005ba98  pop     rdi
0x18005ba99  pop     rbp
0x18005ba9a  retn
0x18005ba9c  test    byte ptr [rbx], 2
0x18005ba9f  jz      short loc_18005BA6B
0x18005baa1  mov     dword ptr [rbx], 2
0x18005baa7  jmp     short loc_18005BA76
0x18005baa9  mov     dword ptr [rbx], 1
0x18005baaf  jmp     short loc_18005BA76
```
