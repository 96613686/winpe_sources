# CMetaData::mdReadTableData(tagCOLRSDATA *,ushort *,ushort *)

- ea: `0x180004930`
- end: `0x180004cc1`
- name: `?mdReadTableData@CMetaData@@AEAAXPEAUtagCOLRSDATA@@PEAG1@Z`
- size: `913`
- prototype: `void(CMetaData *__hidden this, struct tagCOLRSDATA *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800043c8`

## callees

- `0x180001db8`
- `0x180001dd4`
- `0x1800028b8`
- `0x1800028e8`
- `0x1800029ac`
- `0x180004930`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f092`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CMetaData::mdReadTableData(
        CMetaData *this,
        struct tagCOLRSDATA *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  unsigned __int16 *v5; // rsi
  __int64 v8; // r15
  unsigned __int8 *v9; // r14
  __int16 v10; // si
  unsigned __int8 *v11; // rbx
  unsigned __int8 *v12; // rdi
  __int64 v13; // rax
  unsigned int v14; // esi
  unsigned __int128 v15; // rax
  unsigned __int64 v16; // kr00_8
  unsigned __int8 *v17; // r12
  int v18; // eax
  int v19; // esi
  __int64 v20; // rax
  unsigned int v21; // esi
  unsigned __int128 v22; // rax
  unsigned __int64 v23; // kr10_8
  int v24; // eax
  int v25; // esi
  __int64 v26; // rax
  unsigned int v27; // esi
  unsigned __int128 v28; // rax
  unsigned __int64 v29; // kr20_8
  int v30; // eax
  int v31; // esi
  unsigned int v32; // r9d
  unsigned __int128 v33; // rax
  unsigned __int8 *v34; // rbx

  v4 = a4;
  v5 = a3;
  if ( !*((_DWORD *)a2 + 1325) )
  {
    v8 = *((_QWORD *)this + 6);
    v9 = (unsigned __int8 *)v8;
    if ( v8 )
    {
      while ( !(unsigned int)fSameTable((struct tagTABLELIST *)v9, a2) )
      {
        v9 = (unsigned __int8 *)*((_QWORD *)v9 + 6);
        if ( !v9 )
          goto LABEL_5;
      }
    }
    else
    {
LABEL_5:
      v10 = 0;
      v11 = 0;
      v12 = 0;
      if ( v8 )
        v10 = *(_WORD *)(v8 + 40);
      v9 = MMMAlloc(0x38u, (unsigned int)a2);
      OnNullThrowOOM(v9);
      *((_WORD *)v9 + 20) = v10 + 1;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)a2 + v13 + 2136) );
      v14 = v13 + 1;
      v16 = (unsigned int)(v13 + 1);
      v15 = (unsigned int)(v13 + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v16, 2u) )
        LODWORD(v15) = -1;
      v17 = MMMAlloc(v15, DWORD2(v15));
      OnNullThrowOOM(v17);
      v18 = StringCchCopyW((unsigned __int16 *)v17, v14, (const unsigned __int16 *)a2 + 2136);
      v19 = v18;
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180049408[0] )
            bidTraceW(off_1800491B8[0], 875520, off_180049408[0], (unsigned int)v18, 855);
        }
        ThrowHR(v19);
      }
      if ( !*((_DWORD *)a2 + 804) )
      {
        v20 = -1;
        do
          ++v20;
        while ( *((_WORD *)a2 + v20 + 1094) );
        v21 = v20 + 1;
        v23 = (unsigned int)(v20 + 1);
        v22 = (unsigned int)(v20 + 1) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v23, 2u) )
          LODWORD(v22) = -1;
        v11 = MMMAlloc(v22, DWORD2(v22));
        OnNullThrowOOM(v11);
        v24 = StringCchCopyW((unsigned __int16 *)v11, v21, (const unsigned __int16 *)a2 + 1094);
        v25 = v24;
        if ( v24 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049400[0] )
            bidTraceW(off_1800491B8[0], 881664, off_180049400[0], (unsigned int)v24, 861);
          ThrowHR(v25);
        }
      }
      if ( !*((_DWORD *)a2 + 1065) )
      {
        v26 = -1;
        do
          ++v26;
        while ( *((_WORD *)a2 + v26 + 1616) );
        v27 = v26 + 1;
        v29 = (unsigned int)(v26 + 1);
        v28 = (unsigned int)(v26 + 1) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v29, 2u) )
          LODWORD(v28) = -1;
        v12 = MMMAlloc(v28, DWORD2(v28));
        OnNullThrowOOM(v12);
        v30 = StringCchCopyW((unsigned __int16 *)v12, v27, (const unsigned __int16 *)a2 + 1616);
        v31 = v30;
        if ( v30 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800493F8[0] )
            bidTraceW(off_1800491B8[0], 888832, off_1800493F8[0], (unsigned int)v30, 868);
          ThrowHR(v31);
        }
      }
      *((_DWORD *)v9 + 6) = 0;
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v9 + 6) = *((_QWORD *)this + 6);
      *(_QWORD *)v9 = v17;
      *((_QWORD *)v9 + 1) = v11;
      *((_QWORD *)v9 + 2) = v12;
      *((_QWORD *)this + 6) = v9;
      operator delete(0);
      operator delete(0);
      operator delete(0);
      operator delete(0);
      v4 = a4;
      v5 = a3;
    }
    if ( !*((_DWORD *)a2 + 2396) && *((_WORD *)a2 + 4790) == 0xFFFF )
    {
      v32 = *((unsigned __int16 *)v9 + 13);
      if ( v32 == 10 * (v32 / 0xA) )
      {
        v33 = (v32 + 10) * (unsigned __int128)2uLL;
        if ( !is_mul_ok(v32 + 10, 2u) )
          LODWORD(v33) = -1;
        v34 = MMMAlloc(v33, DWORD2(v33));
        OnNullThrowOOM(v34);
        memcpy_0(v34, *((const void **)v9 + 4), 2LL * *((unsigned __int16 *)v9 + 13));
        operator delete(*((unsigned __int8 **)v9 + 4));
        *((_QWORD *)v9 + 4) = v34;
      }
      *(_WORD *)(*((_QWORD *)v9 + 4) + 2LL * (unsigned __int16)(*((_WORD *)v9 + 13))++) = *((_WORD *)a2 + 520);
    }
    *v5 = *((_WORD *)v9 + 20);
    *v4 = ++*((_WORD *)v9 + 12);
  }
}

```

## disassembly

```asm
0x180004930  mov     [rsp+arg_18], r9
0x180004935  mov     [rsp+arg_10], r8
0x18000493a  push    rbx
0x18000493b  push    rbp
0x18000493c  push    rsi
0x18000493d  push    rdi
0x18000493e  push    r12
0x180004940  push    r13
0x180004942  push    r14
0x180004944  push    r15
0x180004946  sub     rsp, 48h
0x18000494a  mov     rdi, r9
0x18000494d  mov     rsi, r8
0x180004950  mov     rbp, rdx
0x180004953  mov     r13, rcx
0x180004956  xor     r12d, r12d
0x180004959  cmp     [rdx+14B4h], r12d
0x180004960  jnz     loc_180004CAF
0x180004966  mov     r15, [rcx+30h]
0x18000496a  mov     r14, r15
0x18000496d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004971  test    r15, r15
0x180004974  jz      short loc_180004992
0x180004976  mov     rdx, rbp; struct tagCOLRSDATA *
0x180004979  mov     rcx, r14; struct tagTABLELIST *
0x18000497c  call    ?fSameTable@@YAHPEAUtagTABLELIST@@PEAUtagCOLRSDATA@@@Z; fSameTable(tagTABLELIST *,tagCOLRSDATA *)
0x180004981  test    eax, eax
0x180004983  jnz     loc_180004C0C
0x180004989  mov     r14, [r14+30h]
0x18000498d  test    r14, r14
0x180004990  jnz     short loc_180004976
0x180004992  mov     esi, r12d
0x180004995  mov     [rsp+88h+arg_0], r12
0x18000499d  mov     rbx, r12
0x1800049a0  mov     [rsp+88h+arg_8], rbx
0x1800049a8  mov     rdi, r12
0x1800049ab  mov     [rsp+88h+var_58], r12
0x1800049b0  test    r15, r15
0x1800049b3  jz      short loc_1800049BA
0x1800049b5  movzx   esi, word ptr [r15+28h]
0x1800049ba  mov     ecx, 38h ; '8'; unsigned int
0x1800049bf  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800049c4  mov     r14, rax
0x1800049c7  mov     [rsp+88h+var_50], rax
0x1800049cc  mov     rcx, rax; void *
0x1800049cf  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800049d4  inc     si
0x1800049d7  mov     [r14+28h], si
0x1800049dc  lea     r15, [rbp+10B0h]
0x1800049e3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800049e7  mov     rax, rcx
0x1800049ea  inc     rax
0x1800049ed  cmp     [r15+rax*2], r12w
0x1800049f2  jnz     short loc_1800049EA
0x1800049f4  lea     esi, [rax+1]
0x1800049f7  mov     eax, 2
0x1800049fc  mul     rsi
0x1800049ff  cmovb   rax, rcx
0x180004a03  mov     ecx, eax; unsigned int
0x180004a05  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004a0a  mov     r12, rax
0x180004a0d  mov     [rsp+88h+arg_0], rax
0x180004a15  mov     rcx, rax; void *
0x180004a18  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004a1d  mov     r8, r15; unsigned __int16 *
0x180004a20  mov     edx, esi; unsigned __int64
0x180004a22  mov     rcx, r12; unsigned __int16 *
0x180004a25  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004a2a  mov     esi, eax
0x180004a2c  xor     edx, edx; unsigned int
0x180004a2e  test    eax, eax
0x180004a30  jns     short loc_180004A72
0x180004a32  test    byte ptr cs:_bidGblFlags, 2
0x180004a39  jz      short loc_180004A6A
0x180004a3b  mov     rcx, cs:off_180049408; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004a42  test    rcx, rcx
0x180004a45  jz      short loc_180004A6A
0x180004a47  mov     [rsp+88h+var_68], 357h
0x180004a4f  mov     r9d, eax
0x180004a52  mov     r8, cs:off_180049408; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004a59  mov     edx, 0D5C00h
0x180004a5e  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004a65  call    _bidTraceW
0x180004a6a  mov     ecx, esi; int
0x180004a6c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004a72  cmp     [rbp+0C90h], edx
0x180004a78  jnz     loc_180004B14
0x180004a7e  lea     r15, [rbp+88Ch]
0x180004a85  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004a89  mov     rax, rcx
0x180004a8c  inc     rax
0x180004a8f  cmp     [r15+rax*2], dx
0x180004a94  jnz     short loc_180004A8C
0x180004a96  lea     esi, [rax+1]
0x180004a99  mov     eax, 2
0x180004a9e  mul     rsi
0x180004aa1  cmovb   rax, rcx
0x180004aa5  mov     ecx, eax; unsigned int
0x180004aa7  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004aac  mov     rbx, rax
0x180004aaf  mov     [rsp+88h+arg_8], rax
0x180004ab7  mov     rcx, rax; void *
0x180004aba  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004abf  mov     r8, r15; unsigned __int16 *
0x180004ac2  mov     edx, esi; unsigned __int64
0x180004ac4  mov     rcx, rbx; unsigned __int16 *
0x180004ac7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004acc  mov     esi, eax
0x180004ace  xor     edx, edx
0x180004ad0  test    eax, eax
0x180004ad2  jns     short loc_180004B14
0x180004ad4  test    byte ptr cs:_bidGblFlags, 2
0x180004adb  jz      short loc_180004B0C
0x180004add  mov     rcx, cs:off_180049400; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004ae4  test    rcx, rcx
0x180004ae7  jz      short loc_180004B0C
0x180004ae9  mov     [rsp+88h+var_68], 35Dh
0x180004af1  mov     r9d, eax
0x180004af4  mov     r8, cs:off_180049400; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004afb  mov     edx, 0D7400h
0x180004b00  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004b07  call    _bidTraceW
0x180004b0c  mov     ecx, esi; int
0x180004b0e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004b14  cmp     [rbp+10A4h], edx
0x180004b1a  jnz     loc_180004BB3
0x180004b20  lea     r15, [rbp+0CA0h]
0x180004b27  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004b2b  mov     rax, rcx
0x180004b2e  inc     rax
0x180004b31  cmp     [r15+rax*2], dx
0x180004b36  jnz     short loc_180004B2E
0x180004b38  lea     esi, [rax+1]
0x180004b3b  mov     eax, 2
0x180004b40  mul     rsi
0x180004b43  cmovb   rax, rcx
0x180004b47  mov     ecx, eax; unsigned int
0x180004b49  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004b4e  mov     rdi, rax
0x180004b51  mov     [rsp+88h+var_58], rax
0x180004b56  mov     rcx, rax; void *
0x180004b59  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004b5e  mov     r8, r15; unsigned __int16 *
0x180004b61  mov     edx, esi; unsigned __int64
0x180004b63  mov     rcx, rdi; unsigned __int16 *
0x180004b66  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004b6b  mov     esi, eax
0x180004b6d  xor     edx, edx
0x180004b6f  test    eax, eax
0x180004b71  jns     short loc_180004BB3
0x180004b73  test    byte ptr cs:_bidGblFlags, 2
0x180004b7a  jz      short loc_180004BAB
0x180004b7c  mov     rcx, cs:off_1800493F8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004b83  test    rcx, rcx
0x180004b86  jz      short loc_180004BAB
0x180004b88  mov     [rsp+88h+var_68], 364h
0x180004b90  mov     r9d, eax
0x180004b93  mov     r8, cs:off_1800493F8; "<CMetaData::mdReadTableData|ADO|ERR>  H"...
0x180004b9a  mov     edx, 0D9000h
0x180004b9f  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180004ba6  call    _bidTraceW
0x180004bab  mov     ecx, esi; int
0x180004bad  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180004bb3  mov     dword ptr [r14+18h], 0
0x180004bbb  mov     [r14+20h], rdx
0x180004bbf  mov     rax, [r13+30h]
0x180004bc3  mov     [r14+30h], rax
0x180004bc7  mov     [r14], r12
0x180004bca  mov     [r14+8], rbx
0x180004bce  mov     [r14+10h], rdi
0x180004bd2  mov     [r13+30h], r14
0x180004bd6  xor     ecx, ecx; void *
0x180004bd8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004bdd  nop
0x180004bde  xor     ecx, ecx; void *
0x180004be0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004be5  nop
0x180004be6  xor     ecx, ecx; void *
0x180004be8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004bed  nop
0x180004bee  xor     ecx, ecx; void *
0x180004bf0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004bf5  mov     rdi, [rsp+88h+arg_18]
0x180004bfd  mov     rsi, [rsp+88h+arg_10]
0x180004c05  xor     r12d, r12d
0x180004c08  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180004c0c  cmp     [rbp+2570h], r12d
0x180004c13  jnz     loc_180004C9A
0x180004c19  cmp     [rbp+256Ch], bx
0x180004c20  jnz     short loc_180004C9A
0x180004c22  movzx   r9d, word ptr [r14+1Ah]
0x180004c27  mov     eax, 0CCCCCCCDh
0x180004c2c  mul     r9d
0x180004c2f  shr     edx, 3
0x180004c32  lea     r8d, [rdx+rdx*4]
0x180004c36  add     r8d, r8d
0x180004c39  cmp     r9d, r8d
0x180004c3c  jnz     short loc_180004C81
0x180004c3e  lea     edx, [r9+0Ah]; unsigned int
0x180004c42  mov     eax, 2
0x180004c47  mul     rdx
0x180004c4a  cmovb   rax, rbx
0x180004c4e  mov     ecx, eax; unsigned int
0x180004c50  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180004c55  mov     rbx, rax
0x180004c58  mov     rcx, rax; void *
0x180004c5b  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180004c60  movzx   r8d, word ptr [r14+1Ah]
0x180004c65  add     r8, r8; Size
0x180004c68  mov     rdx, [r14+20h]; Src
0x180004c6c  mov     rcx, rbx; void *
0x180004c6f  call    memcpy_0
0x180004c74  mov     rcx, [r14+20h]; void *
0x180004c78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c7d  mov     [r14+20h], rbx
0x180004c81  movzx   edx, word ptr [r14+1Ah]
0x180004c86  mov     rcx, [r14+20h]
0x180004c8a  movzx   eax, word ptr [rbp+410h]
0x180004c91  mov     [rcx+rdx*2], ax
0x180004c95  inc     word ptr [r14+1Ah]
0x180004c9a  movzx   eax, word ptr [r14+28h]
0x180004c9f  mov     [rsi], ax
0x180004ca2  inc     word ptr [r14+18h]
0x180004ca7  movzx   eax, word ptr [r14+18h]
0x180004cac  mov     [rdi], ax
0x180004caf  add     rsp, 48h
0x180004cb3  pop     r15
0x180004cb5  pop     r14
0x180004cb7  pop     r13
0x180004cb9  pop     r12
0x180004cbb  pop     rdi
0x180004cbc  pop     rsi
0x180004cbd  pop     rbp
0x180004cbe  pop     rbx
0x180004cbf  retn
```
