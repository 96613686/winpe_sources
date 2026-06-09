# GenADTG::CreateAccessors(unsigned __int64 *)

- ea: `0x180006218`
- end: `0x180006608`
- name: `?CreateAccessors@GenADTG@@QEAAXPEA_K@Z`
- size: `1008`
- prototype: `void(GenADTG *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1800071b0`

## callees

- `0x180001dd4`
- `0x180002770`
- `0x1800028b8`
- `0x180003c38`
- `0x180004338`
- `0x180004384`
- `0x180006218`
- `0x180009d98`
- `0x180009e30`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0aa`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GenADTG::CreateAccessors(GenADTG *this, unsigned __int64 *a2)
{
  CMetaData *v4; // r15
  unsigned __int128 v5; // rax
  unsigned __int8 *v6; // rax
  unsigned __int128 v7; // rax
  unsigned __int8 *v8; // rax
  int v9; // eax
  int v10; // edi
  unsigned __int16 v11; // bp
  unsigned int v12; // esi
  unsigned __int16 v13; // r14
  unsigned __int16 i; // di
  unsigned __int16 v15; // dx
  unsigned __int16 v16; // dx
  __int16 v17; // r9
  __int16 v18; // r10
  unsigned int v19; // r11d
  unsigned int Size; // r12d
  unsigned __int64 v21; // rcx
  __int64 v22; // r9
  struct tagDBBINDING *v23; // r8
  unsigned int v24; // eax
  unsigned __int128 v25; // rax
  unsigned __int8 *v26; // rax
  void **v27; // r14
  unsigned int v28; // edx
  unsigned __int16 v29; // di
  unsigned int v30; // edx
  unsigned __int16 j; // di
  unsigned __int16 v32; // r8
  unsigned __int16 v33; // r9
  int v34; // esi
  unsigned int v35; // eax
  unsigned __int8 *v36; // rax
  unsigned int v37; // eax
  unsigned int v38; // edx
  unsigned __int8 *v39; // rax
  __int64 v40; // rax
  __int64 v41; // [rsp+90h] [rbp+8h] BYREF

  v41 = 0;
  v4 = (GenADTG *)((char *)this + 128);
  v5 = *((unsigned __int16 *)this + 64) * (unsigned __int128)0x58uLL;
  if ( !is_mul_ok(*((unsigned __int16 *)this + 64), 0x58u) )
    LODWORD(v5) = -1;
  v6 = MMMAlloc(v5, DWORD2(v5));
  *((_QWORD *)this + 7) = v6;
  OnNullThrowOOM(v6);
  v7 = *(unsigned __int16 *)v4 * (unsigned __int128)2u;
  if ( !is_mul_ok(*(unsigned __int16 *)v4, 2u) )
    LODWORD(v7) = -1;
  v8 = MMMAlloc(v7, DWORD2(v7));
  *((_QWORD *)this + 32) = v8;
  OnNullThrowOOM(v8);
  *((_WORD *)this + 32) = 0;
  *((_WORD *)this + 102) = 0;
  v9 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IAccessor,
         &v41);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180049578[0] )
        bidTraceW(off_1800491C0[0], 1718272, off_180049578[0], (unsigned int)v9, 1678);
    }
    ThrowHR(v10);
  }
  v11 = 0;
  v12 = 1;
  v13 = 0;
  for ( i = 0; i < *(_WORD *)v4; i += v19 )
  {
    CMetaData::mdGetFlags(v4, i);
    CMetaData::mdGetType(v4, v15);
    Size = CMetaData::mdGetSize(v4, v16);
    if ( (v18 & 0x2000) != 0 || v17 == 136 )
      v21 = v19;
    else
      v21 = 0;
    if ( !*((_DWORD *)this + 50) || !(_DWORD)v21 )
    {
      if ( (v18 & 0x60) != 0 || (_DWORD)v21 )
      {
        v21 = *((unsigned __int16 *)this + 102);
        *(_WORD *)(*((_QWORD *)this + 32) + 2 * v21) = v13;
        *((_WORD *)this + 102) += v19;
      }
      v22 = *((_QWORD *)this + 20);
      v23 = (struct tagDBBINDING *)(*((_QWORD *)this + 7) + 88LL * v13);
      if ( v22 )
        GenADTG::SetupDBBinding((GenADTG *)v21, (struct tagCOLRSDATA *)(v22 + 9648LL * i), v23, a2);
      else
        GenADTG::SetupDBBinding((GenADTG *)v21, (struct tagDBCOLUMNINFO *)(*((_QWORD *)this + 17) + 168LL * i), v23, a2);
      if ( Size > 0xFF && !v11 )
        v11 = v13;
      LOWORD(v19) = 1;
      ++v13;
      v24 = v12 + 1;
      if ( !v11 )
        v24 = v12;
      v12 = v24;
    }
  }
  *((_WORD *)this + 32) = v13;
  v25 = v12 * (unsigned __int128)8uLL;
  if ( !is_mul_ok(v12, 8u) )
    LODWORD(v25) = -1;
  v26 = MMMAlloc(v25, DWORD2(v25));
  v27 = (void **)((char *)this + 72);
  *((_QWORD *)this + 9) = v26;
  OnNullThrowOOM(v26);
  v29 = 0;
  if ( v12 >= 2 && (*v27 > v27 || (char *)*v27 + 8 * (unsigned __int16)(v12 - 1) < (char *)v27) )
  {
    v30 = v12 & 0xFFFFFFFE;
    do
      v29 += 2;
    while ( v29 < v30 );
    memset_0(*v27, 0, 16 * ((unsigned __int64)(unsigned __int16)(v30 + 1) >> 1));
  }
  while ( v29 < v12 )
    *((_QWORD *)*v27 + v29++) = 0;
  *((_DWORD *)this + 20) = v12;
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 20); ++j )
  {
    if ( j )
    {
      v32 = 1;
      v33 = j + v11 - 1;
    }
    else
    {
      if ( v11 )
        v32 = v11;
      else
        v32 = *((_WORD *)this + 32);
      v33 = 0;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v41 + 32LL))(
            v41,
            2,
            v32,
            *((_QWORD *)this + 7) + 88LL * v33,
            0,
            (__int64)*v27 + 8 * j,
            0);
    if ( v34 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049570[0] )
        bidTraceW(off_1800491C0[0], 1788928, off_180049570[0], (unsigned int)v34, 1747);
      ThrowHR(v34);
    }
  }
  v35 = ((unsigned int)*((unsigned __int16 *)this + 102) + 7) >> 3;
  *((_WORD *)this + 108) = v35;
  v36 = MMMAlloc((unsigned __int16)v35, v28);
  *((_QWORD *)this + 26) = v36;
  OnNullThrowOOM(v36);
  v37 = ((unsigned int)*((unsigned __int16 *)this + 32) + 7) >> 3;
  *((_WORD *)this + 116) = v37;
  v39 = MMMAlloc(2 * (unsigned int)(unsigned __int16)v37, v38);
  *((_QWORD *)this + 28) = v39;
  OnNullThrowOOM(v39);
  v40 = *((unsigned __int16 *)this + 116);
  *((_WORD *)this + 124) = v40;
  *((_QWORD *)this + 30) = *((_QWORD *)this + 28) + v40;
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v41);
}

```

## disassembly

```asm
0x180006218  mov     rax, rsp
0x18000621b  push    rbx
0x18000621c  push    rbp
0x18000621d  push    rsi
0x18000621e  push    rdi
0x18000621f  push    r12
0x180006221  push    r13
0x180006223  push    r14
0x180006225  push    r15
0x180006227  sub     rsp, 48h
0x18000622b  mov     r13, rdx
0x18000622e  mov     rbx, rcx
0x180006231  xor     r12d, r12d
0x180006234  mov     [rax+8], r12
0x180006238  lea     r15, [rcx+80h]
0x18000623f  movzx   r8d, word ptr [r15]
0x180006243  lea     eax, [r12+58h]
0x180006248  mul     r8
0x18000624b  lea     rdi, [r12-1]
0x180006250  cmovb   rax, rdi
0x180006254  mov     ecx, eax; unsigned int
0x180006256  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000625b  mov     [rbx+38h], rax
0x18000625f  mov     rcx, rax; void *
0x180006262  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180006267  movzx   ecx, word ptr [r15]
0x18000626b  lea     esi, [rdi+3]
0x18000626e  mov     eax, esi
0x180006270  mul     rcx
0x180006273  cmovb   rax, rdi
0x180006277  mov     ecx, eax; unsigned int
0x180006279  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000627e  mov     [rbx+100h], rax
0x180006285  mov     rcx, rax; void *
0x180006288  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000628d  mov     [rbx+40h], r12w
0x180006292  mov     [rbx+0CCh], r12w
0x18000629a  mov     rcx, [rbx+18h]
0x18000629e  mov     rax, [rcx]
0x1800062a1  lea     r8, [rsp+88h+arg_0]
0x1800062a9  lea     rdx, IID_IAccessor
0x1800062b0  mov     rax, [rax]
0x1800062b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062b8  mov     edi, eax
0x1800062ba  test    eax, eax
0x1800062bc  jns     short loc_1800062FE
0x1800062be  test    byte ptr cs:_bidGblFlags, sil
0x1800062c5  jz      short loc_1800062F6
0x1800062c7  mov     rcx, cs:off_180049578; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x1800062ce  test    rcx, rcx
0x1800062d1  jz      short loc_1800062F6
0x1800062d3  mov     dword ptr [rsp+88h+var_68], 68Eh
0x1800062db  mov     r9d, eax
0x1800062de  mov     r8, cs:off_180049578; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x1800062e5  mov     edx, 1A3800h
0x1800062ea  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800062f1  call    _bidTraceW
0x1800062f6  mov     ecx, edi; int
0x1800062f8  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800062fe  mov     ebp, r12d
0x180006301  mov     r11d, 1
0x180006307  mov     esi, r11d
0x18000630a  mov     r14d, r12d
0x18000630d  mov     edi, r12d
0x180006310  cmp     r12w, [r15]
0x180006314  jnb     loc_180006414
0x18000631a  movzx   edx, di; unsigned __int16
0x18000631d  mov     rcx, r15; this
0x180006320  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180006325  mov     r10d, eax
0x180006328  mov     rcx, r15; this
0x18000632b  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180006330  movzx   r9d, ax
0x180006334  mov     rcx, r15; this
0x180006337  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x18000633c  mov     r12d, eax
0x18000633f  bt      r10d, 0Dh
0x180006344  jb      short loc_180006355
0x180006346  mov     eax, 88h
0x18000634b  cmp     r9w, ax
0x18000634f  jz      short loc_180006355
0x180006351  xor     ecx, ecx
0x180006353  jmp     short loc_180006358
0x180006355  mov     ecx, r11d
0x180006358  cmp     dword ptr [rbx+0C8h], 0
0x18000635f  jz      short loc_180006369
0x180006361  test    ecx, ecx
0x180006363  jnz     loc_180006403
0x180006369  test    r10b, 60h
0x18000636d  jnz     short loc_180006373
0x18000636f  test    ecx, ecx
0x180006371  jz      short loc_18000638E
0x180006373  movzx   ecx, word ptr [rbx+0CCh]; this
0x18000637a  mov     rax, [rbx+100h]
0x180006381  mov     [rax+rcx*2], r14w
0x180006386  add     [rbx+0CCh], r11w
0x18000638e  mov     r9, [rbx+0A0h]
0x180006395  movzx   edx, di
0x180006398  movzx   eax, r14w
0x18000639c  imul    r8, rax, 58h ; 'X'
0x1800063a0  add     r8, [rbx+38h]; struct tagDBBINDING *
0x1800063a4  test    r9, r9
0x1800063a7  jz      short loc_1800063BD
0x1800063a9  imul    rdx, 25B0h
0x1800063b0  add     rdx, r9; struct tagCOLRSDATA *
0x1800063b3  mov     r9, r13; unsigned __int64 *
0x1800063b6  call    ?SetupDBBinding@GenADTG@@AEAAXPEAUtagCOLRSDATA@@PEAUtagDBBINDING@@PEA_K@Z; GenADTG::SetupDBBinding(tagCOLRSDATA *,tagDBBINDING *,unsigned __int64 *)
0x1800063bb  jmp     short loc_1800063D3
0x1800063bd  imul    rdx, 0A8h
0x1800063c4  add     rdx, [rbx+88h]; struct tagDBCOLUMNINFO *
0x1800063cb  mov     r9, r13; unsigned __int64 *
0x1800063ce  call    ?SetupDBBinding@GenADTG@@AEAAXPEAUtagDBCOLUMNINFO@@PEAUtagDBBINDING@@PEA_K@Z; GenADTG::SetupDBBinding(tagDBCOLUMNINFO *,tagDBBINDING *,unsigned __int64 *)
0x1800063d3  cmp     r12d, 0FFh
0x1800063da  jbe     short loc_1800063E9
0x1800063dc  xor     r12d, r12d
0x1800063df  test    bp, bp
0x1800063e2  cmovz   bp, r14w
0x1800063e7  jmp     short loc_1800063EC
0x1800063e9  xor     r12d, r12d
0x1800063ec  mov     r11d, 1
0x1800063f2  add     r14w, r11w
0x1800063f6  lea     eax, [rsi+1]
0x1800063f9  test    bp, bp
0x1800063fc  cmovz   eax, esi
0x1800063ff  mov     esi, eax
0x180006401  jmp     short loc_180006406
0x180006403  xor     r12d, r12d
0x180006406  add     di, r11w
0x18000640a  cmp     di, [r15]
0x18000640e  jb      loc_18000631A
0x180006414  mov     [rbx+40h], r14w
0x180006419  mov     ecx, esi
0x18000641b  mov     eax, 8
0x180006420  mul     rcx
0x180006423  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000642a  cmovb   rax, rcx
0x18000642e  mov     ecx, eax; unsigned int
0x180006430  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180006435  lea     r14, [rbx+48h]
0x180006439  mov     [r14], rax
0x18000643c  mov     rcx, rax; void *
0x18000643f  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180006444  mov     edi, r12d
0x180006447  mov     r13d, 2
0x18000644d  lea     r15d, [r13-1]
0x180006451  cmp     esi, r13d
0x180006454  jb      short loc_1800064AE
0x180006456  mov     r9, [r14]
0x180006459  cmp     r9, r14
0x18000645c  ja      short loc_180006471
0x18000645e  movzx   eax, si
0x180006461  sub     ax, r15w
0x180006465  movzx   eax, ax
0x180006468  lea     rcx, [r9+rax*8]
0x18000646c  cmp     rcx, r14
0x18000646f  jnb     short loc_1800064AE
0x180006471  mov     edx, esi
0x180006473  and     edx, 0FFFFFFFEh
0x180006476  add     di, r13w
0x18000647a  movzx   eax, di
0x18000647d  cmp     eax, edx
0x18000647f  jb      short loc_180006476
0x180006481  add     dx, r15w
0x180006485  movzx   r8d, dx
0x180006489  shr     r8, 1
0x18000648c  shl     r8, 4
0x180006490  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180006494  xor     edx, edx; Val
0x180006496  mov     rcx, r9; void *
0x180006499  call    memset_0
0x18000649e  jmp     short loc_1800064AE
0x1800064a0  movzx   ecx, di
0x1800064a3  mov     rax, [r14]
0x1800064a6  mov     [rax+rcx*8], r12
0x1800064aa  add     di, r15w
0x1800064ae  movzx   eax, di
0x1800064b1  cmp     eax, esi
0x1800064b3  jb      short loc_1800064A0
0x1800064b5  mov     [rbx+50h], esi
0x1800064b8  mov     edi, r12d
0x1800064bb  movzx   eax, di
0x1800064be  cmp     eax, [rbx+50h]
0x1800064c1  jnb     loc_180006578
0x1800064c7  test    di, di
0x1800064ca  jnz     short loc_1800064E1
0x1800064cc  test    bp, bp
0x1800064cf  jnz     short loc_1800064D8
0x1800064d1  movzx   r8d, word ptr [rbx+40h]
0x1800064d6  jmp     short loc_1800064DC
0x1800064d8  movzx   r8d, bp
0x1800064dc  mov     r9d, r12d
0x1800064df  jmp     short loc_1800064EC
0x1800064e1  mov     r8d, r15d
0x1800064e4  lea     r9d, [rdi+rbp]
0x1800064e8  sub     r9w, r15w
0x1800064ec  mov     rcx, [rsp+88h+arg_0]
0x1800064f4  mov     r10, [rcx]
0x1800064f7  movzx   edx, di
0x1800064fa  mov     rax, [r14]
0x1800064fd  lea     r11, [rax+rdx*8]
0x180006501  movzx   eax, r9w
0x180006505  imul    r9, rax, 58h ; 'X'
0x180006509  add     r9, [rbx+38h]
0x18000650d  movzx   r8d, r8w
0x180006511  mov     [rsp+88h+var_58], r12
0x180006516  mov     [rsp+88h+var_60], r11
0x18000651b  mov     [rsp+88h+var_68], r12
0x180006520  mov     edx, r13d
0x180006523  mov     rax, [r10+20h]
0x180006527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652c  mov     esi, eax
0x18000652e  test    eax, eax
0x180006530  js      short loc_180006538
0x180006532  add     di, r15w
0x180006536  jmp     short loc_1800064BB
0x180006538  test    byte ptr cs:_bidGblFlags, r13b
0x18000653f  jz      short loc_180006570
0x180006541  mov     rax, cs:off_180049570; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x180006548  test    rax, rax
0x18000654b  jz      short loc_180006570
0x18000654d  mov     dword ptr [rsp+88h+var_68], 6D3h
0x180006555  mov     r9d, esi
0x180006558  mov     r8, cs:off_180049570; "<GenADTG::CreateAccessors|ADO|ERR>  HRE"...
0x18000655f  mov     edx, 1B4C00h
0x180006564  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000656b  call    _bidTraceW
0x180006570  mov     ecx, esi; int
0x180006572  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180006578  movzx   eax, word ptr [rbx+0CCh]
0x18000657f  add     eax, 7
0x180006582  shr     eax, 3
0x180006585  movzx   ecx, ax; unsigned int
0x180006588  mov     [rbx+0D8h], cx
0x18000658f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180006594  mov     [rbx+0D0h], rax
0x18000659b  mov     rcx, rax; void *
0x18000659e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800065a3  movzx   eax, word ptr [rbx+40h]
0x1800065a7  add     eax, 7
0x1800065aa  shr     eax, 3
0x1800065ad  movzx   ecx, ax
0x1800065b0  mov     [rbx+0E8h], cx
0x1800065b7  add     ecx, ecx; unsigned int
0x1800065b9  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800065be  mov     [rbx+0E0h], rax
0x1800065c5  mov     rcx, rax; void *
0x1800065c8  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800065cd  movzx   eax, word ptr [rbx+0E8h]
0x1800065d4  mov     [rbx+0F8h], ax
0x1800065db  add     rax, [rbx+0E0h]
0x1800065e2  mov     [rbx+0F0h], rax
0x1800065e9  lea     rcx, [rsp+88h+arg_0]
0x1800065f1  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x1800065f6  add     rsp, 48h
0x1800065fa  pop     r15
0x1800065fc  pop     r14
0x1800065fe  pop     r13
0x180006600  pop     r12
0x180006602  pop     rdi
0x180006603  pop     rsi
0x180006604  pop     rbp
0x180006605  pop     rbx
0x180006606  retn
```
