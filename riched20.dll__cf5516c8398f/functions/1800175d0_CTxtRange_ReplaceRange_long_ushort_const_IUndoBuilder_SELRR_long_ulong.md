# CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)

- ea: `0x1800175d0`
- end: `0x180017855`
- name: `?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z`
- size: `645`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18003f9c0`
- `0x180049814`
- `0x180089840`

## callees

- `0x180009860`
- `0x180010510`
- `0x1800110b0`
- `0x1800175d0`
- `0x180017ef0`
- `0x180018390`
- `0x180026e20`
- `0x18002c900`
- `0x1800411d4`
- `0x180092010`

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
    v11 = qword_1800A41F0;
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
0x1800175d0  mov     r11, rsp
0x1800175d3  mov     [r11+18h], r8
0x1800175d7  push    rbx
0x1800175d8  push    rsi
0x1800175d9  push    rdi
0x1800175da  push    r15
0x1800175dc  sub     rsp, 88h
0x1800175e3  movsx   eax, word ptr [rcx+60h]
0x1800175e7  mov     rsi, r9
0x1800175ea  mov     r9d, [rcx+58h]
0x1800175ee  mov     r15d, edx
0x1800175f1  mov     [r11+10h], eax
0x1800175f5  mov     rbx, rcx
0x1800175f8  mov     eax, r9d
0x1800175fb  or      eax, edx
0x1800175fd  jz      loc_1800176FF
0x180017603  mov     [r11+8], rbp
0x180017607  xor     edi, edi
0x180017609  mov     [r11-28h], r12
0x18001760d  mov     r12, cs:qword_1800A41F0
0x180017614  mov     [r11-30h], r13
0x180017618  mov     [r11-38h], r14
0x18001761c  mov     r14d, edi
0x18001761f  test    rsi, rsi
0x180017622  jnz     loc_18001776A
0x180017628  mov     eax, [rbx+58h]
0x18001762b  test    eax, eax
0x18001762d  jg      loc_1800177AE
0x180017633  js      loc_18001771B
0x180017639  mov     ebp, [rsp+0A8h+arg_30]
0x180017640  mov     eax, 0FFDFh
0x180017645  and     [rbx+62h], ax
0x180017649  test    bpl, 10h
0x18001764d  jnz     loc_1800177CA
0x180017653  mov     rax, [rsp+0A8h+arg_28]
0x18001765b  lea     rcx, [rbx+8]; this
0x18001765f  mov     edx, [rbx+58h]
0x180017662  mov     r8d, r15d; int
0x180017665  mov     r9, [rsp+0A8h+arg_10]; unsigned __int16 *
0x18001766d  neg     edx; int
0x18001766f  mov     [rsp+0A8h+var_70], ebp; unsigned int
0x180017673  mov     [rsp+0A8h+var_78], rax; int *
0x180017678  mov     eax, [rsp+0A8h+arg_8]
0x18001767f  mov     [rsp+0A8h+var_80], eax; int
0x180017683  mov     [rsp+0A8h+var_88], rsi; struct IUndoBuilder *
0x180017688  mov     [rbx+58h], edi
0x18001768b  call    ?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z; CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)
0x180017690  mov     r13, [rsp+0A8h+var_30]
0x180017695  mov     edi, eax
0x180017697  mov     rbp, [rsp+0A8h+arg_0]
0x18001769f  test    eax, eax
0x1800176a1  jz      short loc_1800176AC
0x1800176a3  mov     eax, 0FFBFh
0x1800176a8  and     [rbx+62h], ax
0x1800176ac  test    r14d, r14d
0x1800176af  mov     rcx, rbx; this
0x1800176b2  mov     r14, [rsp+0A8h+var_38]
0x1800176b7  jnz     short loc_1800176DA
0x1800176b9  mov     edx, 0FFFFFFFFh; int
0x1800176be  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x1800176c3  mov     r12, [rsp+0A8h+var_28]
0x1800176cb  mov     eax, edi
0x1800176cd  add     rsp, 88h
0x1800176d4  pop     r15
0x1800176d6  pop     rdi
0x1800176d7  pop     rsi
0x1800176d8  pop     rbx
0x1800176d9  retn
0x1800176da  mov     edx, [rsp+0A8h+arg_8]; int
0x1800176e1  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x1800176e6  mov     rdx, [r12]
0x1800176ea  mov     rcx, r12
0x1800176ed  mov     rax, [rdx+8]
0x1800176f1  mov     edx, [rsp+0A8h+arg_8]
0x1800176f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176fd  jmp     short loc_1800176C3
0x1800176ff  mov     rax, [rsp+0A8h+arg_28]
0x180017707  test    rax, rax
0x18001770a  jnz     short loc_180017764
0x18001770c  xor     eax, eax
0x18001770e  add     rsp, 88h
0x180017715  pop     r15
0x180017717  pop     rdi
0x180017718  pop     rsi
0x180017719  pop     rbx
0x18001771a  retn
0x18001771b  lea     rcx, [rbx+38h]; this
0x18001771f  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x180017724  test    eax, eax
0x180017726  jz      loc_180017639
0x18001772c  test    byte ptr [rbx+62h], 30h
0x180017730  jnz     loc_180017639
0x180017736  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18001773b  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x180017740  movsx   edx, ax
0x180017743  mov     rcx, r12
0x180017746  mov     rax, [r12]
0x18001774a  mov     [rsp+0A8h+arg_8], edx
0x180017751  mov     rax, [rax]
0x180017754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017759  mov     r14d, 1
0x18001775f  jmp     loc_180017639
0x180017764  xor     edi, edi
0x180017766  mov     [rax], edi
0x180017768  jmp     short loc_18001770C
0x18001776a  cmp     [rsp+0A8h+arg_20], edi
0x180017771  jz      loc_180017628
0x180017777  mov     r8d, [rcx+28h]
0x18001777b  mov     rdx, rsi
0x18001777e  mov     ecx, r8d
0x180017781  mov     dword ptr [rsp+0A8h+var_78], 1
0x180017789  mov     eax, r8d
0x18001778c  mov     [rsp+0A8h+var_80], edi
0x180017790  sub     eax, r9d
0x180017793  test    r9d, r9d
0x180017796  cmovg   ecx, eax
0x180017799  add     ecx, r15d
0x18001779c  mov     dword ptr [rsp+0A8h+var_88], ecx
0x1800177a0  mov     rcx, [rbx+30h]
0x1800177a4  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x1800177a9  jmp     loc_180017628
0x1800177ae  neg     eax
0x1800177b0  lea     rcx, [rbx+8]; this
0x1800177b4  mov     edx, eax; int
0x1800177b6  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x1800177bb  mov     eax, [rbx+58h]
0x1800177be  neg     eax
0x1800177c0  mov     [rbx+58h], eax
0x1800177c3  test    eax, eax
0x1800177c5  jmp     loc_180017633
0x1800177ca  mov     rcx, [rbx+30h]
0x1800177ce  mov     edx, [rsp+0A8h+arg_8]; int
0x1800177d5  add     rcx, 0F8h; this
0x1800177dc  call    ?GetCharFormat@CTxtArray@@QEAAPEBVCCharFormat@@J@Z; CTxtArray::GetCharFormat(long)
0x1800177e1  test    dword ptr [rax], 100h
0x1800177e7  jz      loc_180017653
0x1800177ed  movups  xmm0, xmmword ptr [rax]
0x1800177f0  movups  xmm1, xmmword ptr [rax+10h]
0x1800177f4  movups  [rsp+0A8h+var_68], xmm0
0x1800177f9  movsd   xmm0, qword ptr [rax+20h]
0x1800177fe  movsd   [rsp+0A8h+var_48], xmm0
0x180017804  movups  [rsp+0A8h+var_58], xmm1
0x180017809  test    r14d, r14d
0x18001780c  jz      short loc_180017825
0x18001780e  mov     rax, [r12]
0x180017812  mov     rcx, r12
0x180017815  mov     edx, [rsp+0A8h+arg_8]
0x18001781c  mov     rax, [rax+8]
0x180017820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017825  mov     rax, [r12]
0x180017829  lea     r8, [rsp+0A8h+arg_8]
0x180017831  and     dword ptr [rsp+0A8h+var_68], 0FFFFFEFFh
0x180017839  lea     rdx, [rsp+0A8h+var_68]
0x18001783e  mov     rcx, r12
0x180017841  mov     rax, [rax+18h]
0x180017845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001784a  mov     r14d, 1
0x180017850  jmp     loc_180017653
```
