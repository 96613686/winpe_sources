# CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)

- ea: `0x180016470`
- end: `0x1800166f7`
- name: `?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z`
- size: `647`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x180040500`
- `0x18004a97c`
- `0x18008bea0`

## callees

- `0x180009970`
- `0x18000f280`
- `0x18000fe40`
- `0x180016470`
- `0x180016d90`
- `0x180017230`
- `0x1800267a0`
- `0x180035b80`
- `0x180041cf8`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtRange::ReplaceRange(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 *a3,
        struct IUndoBuilder *a4,
        int a5,
        int *a6,
        unsigned int a7)
{
  __int64 v8; // r9
  struct IFormatCache *v11; // r12
  int v12; // r14d
  int v13; // eax
  bool v14; // sf
  char v15; // bp
  unsigned __int16 *v16; // r9
  int v17; // edx
  unsigned int v18; // edi
  CRunPtrBase *v20; // rcx
  CFormatRunPtr *v21; // rcx
  int Format; // edx
  void (__fastcall **v23)(struct IFormatCache *); // rax
  __int64 v24; // r8
  int v25; // ecx
  int v26; // eax
  const struct CCharFormat *CharFormat; // rax
  __int128 v28; // xmm1
  void (__fastcall **v29)(struct IFormatCache *); // rax
  int v30; // [rsp+28h] [rbp-80h]
  int *v31; // [rsp+30h] [rbp-78h]
  _OWORD v32[2]; // [rsp+40h] [rbp-68h] BYREF
  __int64 v33; // [rsp+60h] [rbp-48h]
  int v34; // [rsp+B8h] [rbp+10h] BYREF
  unsigned __int16 *v35; // [rsp+C0h] [rbp+18h]

  v35 = a3;
  v8 = *(unsigned int *)(a1 + 88);
  v34 = *(__int16 *)(a1 + 96);
  if ( a2 | (unsigned int)v8 )
  {
    v11 = qword_1800A72D0;
    v12 = 0;
    if ( a4 && a5 )
    {
      v24 = *(unsigned int *)(a1 + 40);
      v25 = *(_DWORD *)(a1 + 40);
      if ( (int)v8 > 0 )
        v25 = v24 - v8;
      HandleSelectionAEInfo(*(_QWORD *)(a1 + 48), a4, v24, v8, a2 + v25, 0, 1);
    }
    v13 = *(_DWORD *)(a1 + 88);
    v14 = v13 < 0;
    if ( v13 > 0 )
    {
      CRchTxtPtr::Advance((CRchTxtPtr *)(a1 + 8), -v13);
      v26 = -*(_DWORD *)(a1 + 88);
      *(_DWORD *)(a1 + 88) = v26;
      v14 = v26 < 0;
    }
    if ( v14 && (unsigned int)CRunPtrBase::IsValid((CRunPtrBase *)(a1 + 56)) && (*(_BYTE *)(a1 + 98) & 0x30) == 0 )
    {
      CRunPtrBase::AdjustForward(v20);
      Format = CFormatRunPtr::GetFormat(v21);
      v23 = *(void (__fastcall ***)(struct IFormatCache *))v11;
      v34 = Format;
      (*v23)(v11);
      v12 = 1;
    }
    v15 = a7;
    *(_WORD *)(a1 + 98) &= ~0x20u;
    if ( (v15 & 0x10) != 0 )
    {
      CharFormat = CTxtArray::GetCharFormat((CTxtArray *)(*(_QWORD *)(a1 + 48) + 248LL), v34);
      if ( (*(_DWORD *)CharFormat & 0x100) != 0 )
      {
        v28 = *((_OWORD *)CharFormat + 1);
        v32[0] = *(_OWORD *)CharFormat;
        v33 = *((_QWORD *)CharFormat + 4);
        v32[1] = v28;
        if ( v12 )
          (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, (unsigned int)v34);
        v29 = *(void (__fastcall ***)(struct IFormatCache *))v11;
        LODWORD(v32[0]) &= ~0x100u;
        ((void (__fastcall *)(struct IFormatCache *, _OWORD *, int *))v29[3])(v11, v32, &v34);
        v12 = 1;
      }
    }
    v16 = v35;
    v17 = -*(_DWORD *)(a1 + 88);
    v31 = a6;
    v30 = v34;
    *(_DWORD *)(a1 + 88) = 0;
    v18 = CRchTxtPtr::ReplaceRange((CRchTxtPtr *)(a1 + 8), v17, a2, v16, a4, v30, v31, v15);
    if ( v18 )
      *(_WORD *)(a1 + 98) &= ~0x40u;
    if ( v12 )
    {
      CTxtRange::Update_iFormat((CTxtRange *)a1, v34);
      (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, (unsigned int)v34);
    }
    else
    {
      CTxtRange::Update_iFormat((CTxtRange *)a1, -1);
    }
    return v18;
  }
  else
  {
    if ( a6 )
      *a6 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180016470  mov     r11, rsp
0x180016473  mov     [r11+18h], r8
0x180016477  push    rbx
0x180016478  push    rsi
0x180016479  push    rdi
0x18001647a  push    r15
0x18001647c  sub     rsp, 88h
0x180016483  movsx   eax, word ptr [rcx+60h]
0x180016487  mov     rsi, r9
0x18001648a  mov     r9d, [rcx+58h]
0x18001648e  mov     r15d, edx
0x180016491  mov     [r11+10h], eax
0x180016495  mov     rbx, rcx
0x180016498  mov     eax, r9d
0x18001649b  or      eax, edx
0x18001649d  jz      loc_1800165A0
0x1800164a3  mov     [r11+8], rbp
0x1800164a7  xor     edi, edi
0x1800164a9  mov     [r11-28h], r12
0x1800164ad  mov     r12, cs:qword_1800A72D0
0x1800164b4  mov     [r11-30h], r13
0x1800164b8  mov     [r11-38h], r14
0x1800164bc  mov     r14d, edi
0x1800164bf  test    rsi, rsi
0x1800164c2  jnz     loc_18001660C
0x1800164c8  mov     eax, [rbx+58h]
0x1800164cb  test    eax, eax
0x1800164cd  jg      loc_180016650
0x1800164d3  js      loc_1800165BD
0x1800164d9  mov     ebp, [rsp+0A8h+arg_30]
0x1800164e0  mov     eax, 0FFDFh
0x1800164e5  and     [rbx+62h], ax
0x1800164e9  test    bpl, 10h
0x1800164ed  jnz     loc_18001666C
0x1800164f3  mov     rax, [rsp+0A8h+arg_28]
0x1800164fb  lea     rcx, [rbx+8]; this
0x1800164ff  mov     edx, [rbx+58h]
0x180016502  mov     r8d, r15d; int
0x180016505  mov     r9, [rsp+0A8h+arg_10]; unsigned __int16 *
0x18001650d  neg     edx; int
0x18001650f  mov     [rsp+0A8h+var_70], ebp; unsigned int
0x180016513  mov     [rsp+0A8h+var_78], rax; int *
0x180016518  mov     eax, [rsp+0A8h+arg_8]
0x18001651f  mov     [rsp+0A8h+var_80], eax; int
0x180016523  mov     [rsp+0A8h+var_88], rsi; struct IUndoBuilder *
0x180016528  mov     [rbx+58h], edi
0x18001652b  call    ?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z; CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)
0x180016530  mov     r13, [rsp+0A8h+var_30]
0x180016535  mov     edi, eax
0x180016537  mov     rbp, [rsp+0A8h+arg_0]
0x18001653f  test    eax, eax
0x180016541  jz      short loc_18001654C
0x180016543  mov     eax, 0FFBFh
0x180016548  and     [rbx+62h], ax
0x18001654c  test    r14d, r14d
0x18001654f  mov     rcx, rbx; this
0x180016552  mov     r14, [rsp+0A8h+var_38]
0x180016557  jnz     short loc_18001657B
0x180016559  mov     edx, 0FFFFFFFFh; int
0x18001655e  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180016563  mov     r12, [rsp+0A8h+var_28]
0x18001656b  mov     eax, edi
0x18001656d  add     rsp, 88h
0x180016574  pop     r15
0x180016576  pop     rdi
0x180016577  pop     rsi
0x180016578  pop     rbx
0x180016579  retn
0x18001657b  mov     edx, [rsp+0A8h+arg_8]; int
0x180016582  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180016587  mov     rdx, [r12]
0x18001658b  mov     rcx, r12
0x18001658e  mov     rax, [rdx+8]
0x180016592  mov     edx, [rsp+0A8h+arg_8]
0x180016599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659e  jmp     short loc_180016563
0x1800165a0  mov     rax, [rsp+0A8h+arg_28]
0x1800165a8  test    rax, rax
0x1800165ab  jnz     short loc_180016606
0x1800165ad  xor     eax, eax
0x1800165af  add     rsp, 88h
0x1800165b6  pop     r15
0x1800165b8  pop     rdi
0x1800165b9  pop     rsi
0x1800165ba  pop     rbx
0x1800165bb  retn
0x1800165bd  lea     rcx, [rbx+38h]; this
0x1800165c1  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x1800165c6  test    eax, eax
0x1800165c8  jz      loc_1800164D9
0x1800165ce  test    byte ptr [rbx+62h], 30h
0x1800165d2  jnz     loc_1800164D9
0x1800165d8  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x1800165dd  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x1800165e2  movsx   edx, ax
0x1800165e5  mov     rcx, r12
0x1800165e8  mov     rax, [r12]
0x1800165ec  mov     [rsp+0A8h+arg_8], edx
0x1800165f3  mov     rax, [rax]
0x1800165f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165fb  mov     r14d, 1
0x180016601  jmp     loc_1800164D9
0x180016606  xor     edi, edi
0x180016608  mov     [rax], edi
0x18001660a  jmp     short loc_1800165AD
0x18001660c  cmp     [rsp+0A8h+arg_20], edi
0x180016613  jz      loc_1800164C8
0x180016619  mov     r8d, [rcx+28h]
0x18001661d  mov     rdx, rsi
0x180016620  mov     ecx, r8d
0x180016623  mov     dword ptr [rsp+0A8h+var_78], 1
0x18001662b  mov     eax, r8d
0x18001662e  mov     [rsp+0A8h+var_80], edi
0x180016632  sub     eax, r9d
0x180016635  test    r9d, r9d
0x180016638  cmovg   ecx, eax
0x18001663b  add     ecx, r15d
0x18001663e  mov     dword ptr [rsp+0A8h+var_88], ecx
0x180016642  mov     rcx, [rbx+30h]
0x180016646  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x18001664b  jmp     loc_1800164C8
0x180016650  neg     eax
0x180016652  lea     rcx, [rbx+8]; this
0x180016656  mov     edx, eax; int
0x180016658  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x18001665d  mov     eax, [rbx+58h]
0x180016660  neg     eax
0x180016662  mov     [rbx+58h], eax
0x180016665  test    eax, eax
0x180016667  jmp     loc_1800164D3
0x18001666c  mov     rcx, [rbx+30h]
0x180016670  mov     edx, [rsp+0A8h+arg_8]; int
0x180016677  add     rcx, 0F8h; this
0x18001667e  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x180016683  test    dword ptr [rax], 100h
0x180016689  jz      loc_1800164F3
0x18001668f  movups  xmm0, xmmword ptr [rax]
0x180016692  movups  xmm1, xmmword ptr [rax+10h]
0x180016696  movups  [rsp+0A8h+var_68], xmm0
0x18001669b  movsd   xmm0, qword ptr [rax+20h]
0x1800166a0  movsd   [rsp+0A8h+var_48], xmm0
0x1800166a6  movups  [rsp+0A8h+var_58], xmm1
0x1800166ab  test    r14d, r14d
0x1800166ae  jz      short loc_1800166C7
0x1800166b0  mov     rax, [r12]
0x1800166b4  mov     rcx, r12
0x1800166b7  mov     edx, [rsp+0A8h+arg_8]
0x1800166be  mov     rax, [rax+8]
0x1800166c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166c7  mov     rax, [r12]
0x1800166cb  lea     r8, [rsp+0A8h+arg_8]
0x1800166d3  and     dword ptr [rsp+0A8h+var_68], 0FFFFFEFFh
0x1800166db  lea     rdx, [rsp+0A8h+var_68]
0x1800166e0  mov     rcx, r12
0x1800166e3  mov     rax, [rax+18h]
0x1800166e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ec  mov     r14d, 1
0x1800166f2  jmp     loc_1800164F3
```
