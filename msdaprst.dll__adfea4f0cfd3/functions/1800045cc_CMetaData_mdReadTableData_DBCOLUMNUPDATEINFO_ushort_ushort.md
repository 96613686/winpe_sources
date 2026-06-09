# CMetaData::mdReadTableData(DBCOLUMNUPDATEINFO *,ushort *,ushort *)

- ea: `0x1800045cc`
- end: `0x180004928`
- name: `?mdReadTableData@CMetaData@@AEAAXPEAUDBCOLUMNUPDATEINFO@@PEAG1@Z`
- size: `860`
- prototype: `void __fastcall(CMetaData *__hidden this, struct DBCOLUMNUPDATEINFO *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18000378c`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x1800028e8`
- `0x18000295c`
- `0x1800045cc`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f092`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdReadTableData(
        CMetaData *this,
        unsigned __int16 **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int8 *v6; // r10
  __int64 v7; // rsi
  unsigned __int8 *v8; // r14
  unsigned __int16 **v9; // r12
  unsigned __int16 **v10; // r15
  int v11; // r11d
  __int16 v12; // si
  unsigned __int8 *v13; // rdi
  unsigned __int8 *v14; // rbx
  __int64 v15; // rax
  unsigned int v16; // esi
  unsigned __int128 v17; // rax
  unsigned __int64 v18; // kr00_8
  __int64 v19; // rax
  unsigned int v20; // esi
  unsigned __int128 v21; // rax
  unsigned __int64 v22; // kr10_8
  int v23; // eax
  int v24; // esi
  __int64 v25; // rax
  unsigned int v26; // esi
  unsigned __int128 v27; // rax
  unsigned __int64 v28; // kr20_8
  int v29; // eax
  int v30; // esi
  unsigned int v31; // r9d
  const void **v32; // rdi
  unsigned __int128 v33; // rax
  unsigned __int8 *v34; // rbx
  unsigned __int16 *v35; // [rsp+90h] [rbp+8h]

  v6 = 0;
  if ( a2[11] )
  {
    v7 = *((_QWORD *)this + 6);
    v8 = (unsigned __int8 *)v7;
    v9 = a2 + 12;
    v10 = a2 + 13;
    if ( v7 )
    {
      while ( !(unsigned int)fSameString(*(unsigned __int16 **)v8, a2[11])
           || !(unsigned int)fSameString(*((unsigned __int16 **)v8 + 1), *v9)
           || !(unsigned int)fSameString(*((unsigned __int16 **)v8 + 2), *v10) )
      {
        v8 = (unsigned __int8 *)*((_QWORD *)v8 + 6);
        if ( !v8 )
          goto LABEL_9;
      }
      if ( v8 )
        goto LABEL_36;
LABEL_9:
      v12 = *(_WORD *)(v7 + 40);
    }
    else
    {
      v12 = 0;
    }
    v13 = v6;
    v14 = v6;
    v8 = MMMAlloc(0x38u, (unsigned int)a2);
    OnNullThrowOOM(v8);
    *((_WORD *)v8 + 20) = v12 + 1;
    v15 = -1;
    do
      ++v15;
    while ( a2[11][v15] );
    v16 = v15 + 1;
    v18 = (unsigned int)(v15 + 1);
    v17 = (unsigned int)(v15 + 1) * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v18, 2u) )
      LODWORD(v17) = -1;
    v35 = (unsigned __int16 *)MMMAlloc(v17, DWORD2(v17));
    OnNullThrowOOM(v35);
    StringCchCopyW(v35, v16, a2[11]);
    if ( *v9 )
    {
      v19 = -1;
      do
        ++v19;
      while ( (*v9)[v19] );
      v20 = v19 + 1;
      v22 = (unsigned int)(v19 + 1);
      v21 = (unsigned int)(v19 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v22, 2u) )
        LODWORD(v21) = -1;
      v13 = MMMAlloc(v21, DWORD2(v21));
      OnNullThrowOOM(v13);
      v23 = StringCchCopyW((unsigned __int16 *)v13, v20, *v9);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800493F0[0] )
            bidTraceW(off_1800491B8[0], 985088, off_1800493F0[0], (unsigned int)v23, 962);
        }
        ThrowHR(v24);
      }
    }
    if ( *v10 )
    {
      v25 = -1;
      do
        ++v25;
      while ( (*v10)[v25] );
      v26 = v25 + 1;
      v28 = (unsigned int)(v25 + 1);
      v27 = (unsigned int)(v25 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v28, 2u) )
        LODWORD(v27) = -1;
      v14 = MMMAlloc(v27, DWORD2(v27));
      OnNullThrowOOM(v14);
      v29 = StringCchCopyW((unsigned __int16 *)v14, v26, *v10);
      v30 = v29;
      if ( v29 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800493E8[0] )
          bidTraceW(off_1800491B8[0], 992256, off_1800493E8[0], (unsigned int)v29, 969);
        ThrowHR(v30);
      }
    }
    *((_DWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 6) = *((_QWORD *)this + 6);
    *(_QWORD *)v8 = v35;
    *((_QWORD *)v8 + 1) = v13;
    *((_QWORD *)v8 + 2) = v14;
    *((_QWORD *)this + 6) = v8;
    operator delete(0);
    operator delete(0);
    operator delete(0);
    operator delete(0);
    LOWORD(v6) = 0;
    v11 = -1;
LABEL_36:
    if ( *((_WORD *)a2 + 56) != (_WORD)v6 )
    {
      v31 = *((unsigned __int16 *)v8 + 13);
      v32 = (const void **)(v8 + 32);
      if ( v31 == 10 * (v31 / 0xA) )
      {
        v33 = (v31 + 10) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v31 + 10, 2u) )
          LODWORD(v33) = v11;
        v34 = MMMAlloc(v33, DWORD2(v33));
        OnNullThrowOOM(v34);
        memcpy_0(v34, *v32, 2LL * *((unsigned __int16 *)v8 + 13));
        operator delete((unsigned __int8 *)*v32);
        *v32 = v34;
      }
      *((_WORD *)*v32 + (unsigned __int16)(*((_WORD *)v8 + 13))++) = *((_WORD *)a2 + 8);
    }
    *a3 = *((_WORD *)v8 + 20);
    *a4 = ++*((_WORD *)v8 + 12);
  }
}

```

## disassembly

```asm
0x1800045cc  mov     [rsp+arg_18], r9
0x1800045d1  mov     [rsp+arg_10], r8
0x1800045d6  push    rbx
0x1800045d7  push    rbp
0x1800045d8  push    rsi
0x1800045d9  push    rdi
0x1800045da  push    r12
0x1800045dc  push    r13
0x1800045de  push    r14
0x1800045e0  push    r15
0x1800045e2  sub     rsp, 48h
0x1800045e6  mov     rbp, rdx
0x1800045e9  mov     r13, rcx
0x1800045ec  xor     r10d, r10d
0x1800045ef  cmp     [rdx+58h], r10
0x1800045f3  jz      loc_180004916
0x1800045f9  mov     rsi, [rcx+30h]
0x1800045fd  mov     r14, rsi
0x180004600  lea     r12, [rdx+60h]
0x180004604  lea     r15, [rdx+68h]
0x180004608  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000460c  test    rsi, rsi
0x18000460f  jz      short loc_18000465C
0x180004611  mov     rdx, [rbp+58h]; unsigned __int16 *
0x180004615  mov     rcx, [r14]; unsigned __int16 *
0x180004618  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x18000461d  test    eax, eax
0x18000461f  jz      short loc_180004642
0x180004621  mov     rdx, [r12]; unsigned __int16 *
0x180004625  mov     rcx, [r14+8]; unsigned __int16 *
0x180004629  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x18000462e  test    eax, eax
0x180004630  jz      short loc_180004642
0x180004632  mov     rdx, [r15]; unsigned __int16 *
0x180004635  mov     rcx, [r14+10h]; unsigned __int16 *
0x180004639  call    ?fSameString@@YAHPEAG0@Z; fSameString(ushort *,ushort *)
0x18000463e  test    eax, eax
0x180004640  jnz     short loc_18000464D
0x180004642  mov     r14, [r14+30h]
0x180004646  test    r14, r14
0x180004649  jnz     short loc_180004611
0x18000464b  jmp     short loc_180004656
0x18000464d  test    r14, r14
0x180004650  jnz     loc_180004875
0x180004656  movzx   esi, word ptr [rsi+28h]
0x18000465a  jmp     short loc_18000465F
0x18000465c  mov     esi, r10d
0x18000465f  mov     [rsp+88h+arg_0], r10
0x180004667  mov     rdi, r10
0x18000466a  mov     [rsp+88h+arg_8], r10
0x180004672  mov     rbx, r10
0x180004675  mov     [rsp+88h+var_58], rbx
0x18000467a  mov     ecx, 38h ; '8'; unsigned int
0x18000467f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004684  mov     r14, rax
0x180004687  mov     [rsp+88h+var_50], rax
0x18000468c  mov     rcx, rax; void *
0x18000468f  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004694  inc     si
0x180004697  mov     [r14+28h], si
0x18000469c  mov     rcx, [rbp+58h]
0x1800046a0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800046a4  mov     rax, r8
0x1800046a7  xor     edx, edx; unsigned int
0x1800046a9  inc     rax
0x1800046ac  cmp     [rcx+rax*2], dx
0x1800046b0  jnz     short loc_1800046A9
0x1800046b2  lea     esi, [rax+1]
0x1800046b5  mov     eax, 2
0x1800046ba  mul     rsi
0x1800046bd  cmovb   rax, r8
0x1800046c1  mov     ecx, eax; unsigned int
0x1800046c3  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800046c8  mov     [rsp+88h+arg_0], rax
0x1800046d0  mov     rcx, rax; void *
0x1800046d3  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800046d8  mov     r8, [rbp+58h]; unsigned __int16 *
0x1800046dc  mov     edx, esi; unsigned __int64
0x1800046de  mov     rcx, [rsp+88h+arg_0]; unsigned __int16 *
0x1800046e6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800046eb  mov     r11, [r12]
0x1800046ef  xor     ecx, ecx
0x1800046f1  test    r11, r11
0x1800046f4  jz      loc_18000478B
0x1800046fa  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800046fe  mov     rax, r8
0x180004701  inc     rax
0x180004704  cmp     [r11+rax*2], cx
0x180004709  jnz     short loc_180004701
0x18000470b  lea     esi, [rax+1]
0x18000470e  mov     eax, 2
0x180004713  mul     rsi
0x180004716  cmovb   rax, r8
0x18000471a  mov     ecx, eax; unsigned int
0x18000471c  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004721  mov     rdi, rax
0x180004724  mov     [rsp+88h+arg_8], rax
0x18000472c  mov     rcx, rax; void *
0x18000472f  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004734  mov     r8, [r12]; unsigned __int16 *
0x180004738  mov     edx, esi; unsigned __int64
0x18000473a  mov     rcx, rdi; unsigned __int16 *
0x18000473d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004742  mov     esi, eax
0x180004744  xor     r12d, r12d
0x180004747  test    eax, eax
0x180004749  jns     short loc_18000478E
0x18000474b  test    byte ptr cs:_bidGblFlags, 2
0x180004752  jz      short loc_180004783
0x180004754  mov     rcx, cs:off_1800493F0; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x18000475b  test    rcx, rcx
0x18000475e  jz      short loc_180004783
0x180004760  mov     [rsp+88h+var_68], 3C2h
0x180004768  mov     r9d, eax
0x18000476b  mov     r8, cs:off_1800493F0; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004772  mov     edx, 0F0800h
0x180004777  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000477e  call    _bidTraceW
0x180004783  mov     ecx, esi; int
0x180004785  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000478b  xor     r12d, r12d
0x18000478e  mov     rcx, [r15]
0x180004791  test    rcx, rcx
0x180004794  jz      loc_180004824
0x18000479a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000479e  mov     rax, r8
0x1800047a1  inc     rax
0x1800047a4  cmp     [rcx+rax*2], r12w
0x1800047a9  jnz     short loc_1800047A1
0x1800047ab  lea     esi, [rax+1]
0x1800047ae  mov     eax, 2
0x1800047b3  mul     rsi
0x1800047b6  cmovb   rax, r8
0x1800047ba  mov     ecx, eax; unsigned int
0x1800047bc  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800047c1  mov     rbx, rax
0x1800047c4  mov     [rsp+88h+var_58], rax
0x1800047c9  mov     rcx, rax; void *
0x1800047cc  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800047d1  mov     r8, [r15]; unsigned __int16 *
0x1800047d4  mov     edx, esi; unsigned __int64
0x1800047d6  mov     rcx, rbx; unsigned __int16 *
0x1800047d9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800047de  mov     esi, eax
0x1800047e0  test    eax, eax
0x1800047e2  jns     short loc_180004824
0x1800047e4  test    byte ptr cs:_bidGblFlags, 2
0x1800047eb  jz      short loc_18000481C
0x1800047ed  mov     rcx, cs:off_1800493E8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x1800047f4  test    rcx, rcx
0x1800047f7  jz      short loc_18000481C
0x1800047f9  mov     [rsp+88h+var_68], 3C9h
0x180004801  mov     r9d, eax
0x180004804  mov     r8, cs:off_1800493E8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x18000480b  mov     edx, 0F2400h
0x180004810  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004817  call    _bidTraceW
0x18000481c  mov     ecx, esi; int
0x18000481e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004824  mov     dword ptr [r14+18h], 0
0x18000482c  mov     [r14+20h], r12
0x180004830  mov     rax, [r13+30h]
0x180004834  mov     [r14+30h], rax
0x180004838  mov     rax, [rsp+88h+arg_0]
0x180004840  mov     [r14], rax
0x180004843  mov     [r14+8], rdi
0x180004847  mov     [r14+10h], rbx
0x18000484b  mov     [r13+30h], r14
0x18000484f  xor     ecx, ecx; void *
0x180004851  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004856  nop
0x180004857  xor     ecx, ecx; void *
0x180004859  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000485e  nop
0x18000485f  xor     ecx, ecx; void *
0x180004861  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004866  nop
0x180004867  xor     ecx, ecx; void *
0x180004869  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000486e  xor     r10d, r10d
0x180004871  or      r11, 0FFFFFFFFFFFFFFFFh
0x180004875  cmp     [rbp+70h], r10w
0x18000487a  jz      short loc_1800048F1
0x18000487c  movzx   r9d, word ptr [r14+1Ah]
0x180004881  lea     rdi, [r14+20h]
0x180004885  mov     eax, 0CCCCCCCDh
0x18000488a  mul     r9d
0x18000488d  shr     edx, 3
0x180004890  lea     r8d, [rdx+rdx*4]
0x180004894  add     r8d, r8d
0x180004897  cmp     r9d, r8d
0x18000489a  jnz     short loc_1800048DC
0x18000489c  lea     edx, [r9+0Ah]; unsigned int
0x1800048a0  mov     eax, 2
0x1800048a5  mul     rdx
0x1800048a8  cmovb   rax, r11
0x1800048ac  mov     ecx, eax; unsigned int
0x1800048ae  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800048b3  mov     rbx, rax
0x1800048b6  mov     rcx, rax; void *
0x1800048b9  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800048be  movzx   r8d, word ptr [r14+1Ah]
0x1800048c3  add     r8, r8; Size
0x1800048c6  mov     rdx, [rdi]; Src
0x1800048c9  mov     rcx, rbx; void *
0x1800048cc  call    memcpy_0
0x1800048d1  mov     rcx, [rdi]; void *
0x1800048d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800048d9  mov     [rdi], rbx
0x1800048dc  movzx   edx, word ptr [r14+1Ah]
0x1800048e1  mov     rcx, [rdi]
0x1800048e4  movzx   eax, word ptr [rbp+10h]
0x1800048e8  mov     [rcx+rdx*2], ax
0x1800048ec  inc     word ptr [r14+1Ah]
0x1800048f1  movzx   eax, word ptr [r14+28h]
0x1800048f6  mov     rcx, [rsp+88h+arg_10]
0x1800048fe  mov     [rcx], ax
0x180004901  inc     word ptr [r14+18h]
0x180004906  movzx   eax, word ptr [r14+18h]
0x18000490b  mov     rcx, [rsp+88h+arg_18]
0x180004913  mov     [rcx], ax
0x180004916  add     rsp, 48h
0x18000491a  pop     r15
0x18000491c  pop     r14
0x18000491e  pop     r13
0x180004920  pop     r12
0x180004922  pop     rdi
0x180004923  pop     rsi
0x180004924  pop     rbp
0x180004925  pop     rbx
0x180004926  retn
```
