# CHtmlScanner::ScanTagName(CToken &)

- ea: `0x1800074e0`
- end: `0x180007a91`
- name: `?ScanTagName@CHtmlScanner@@AEAAXAEAVCToken@@@Z`
- size: `1457`
- prototype: `void __fastcall(CHtmlScanner *__hidden this, struct CToken *)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180008690`
- `0x180009fa0`
- `0x18000a3c0`
- `0x18000ad20`
- `0x18000b110`

## callees

- `0x180007130`
- `0x180007400`
- `0x1800074e0`
- `0x180009700`
- `0x18000a374`
- `0x180014130`
- `0x180025010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007666`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000780c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007950`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800079db`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007666`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000780c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180007950`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800079db`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000756f`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800075d4`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000756f`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x1800075d4`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007962`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007962`

## pseudocode

```c
void __fastcall CHtmlScanner::ScanTagName(CHtmlScanner *this, struct CToken *a2)
{
  __int64 v4; // r8
  const wchar_t *v5; // r9
  __int64 v6; // rdx
  unsigned __int16 Char; // ax
  unsigned __int16 v8; // di
  unsigned int v9; // ebx
  __int64 v10; // r8
  const wchar_t *v11; // r9
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r15
  char *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // r9
  void **i; // r14
  _DWORD *v19; // rax
  int v20; // r12d
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  const wchar_t *v25; // r9
  int v26; // r14d
  unsigned __int16 v27; // ax
  CSerialStream *v28; // rcx
  __int64 v29; // rax
  __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // r8
  const wchar_t *v33; // r9
  unsigned int v34; // eax
  wchar_t *v35; // rax
  __int64 v36; // rax
  unsigned int v37; // r15d
  char *v38; // r14
  void **j; // rbx
  __int64 v40; // r9
  _DWORD *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int16 v45; // [rsp+2Eh] [rbp-42h]
  __int64 v46; // [rsp+30h] [rbp-40h] BYREF
  __int64 v47; // [rsp+38h] [rbp-38h]
  __int64 v48; // [rsp+40h] [rbp-30h]
  __int64 v49; // [rsp+48h] [rbp-28h]

  *((_DWORD *)this + 8) = 0;
  *(_DWORD *)a2 = 1;
  *((_QWORD *)a2 + 1) = 0;
  CHtmlScanner::EatBlanks(this);
  v6 = *((_QWORD *)this + 1);
  if ( *(__int16 *)(v6 + 40) <= 0
    && *(_QWORD *)(v6 + 88) >= v6 + 2 * ((unsigned __int64)*(unsigned int *)(v6 + 84) + 21)
    && !*(_DWORD *)(v6 + 116)
    && *(_DWORD *)(v6 + 100) >= *(_DWORD *)(v6 + 104)
    && *(_DWORD *)(v6 + 96) == *(_DWORD *)(v6 + 296)
    && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v6 + 288)) )
  {
    *(_DWORD *)a2 = 2;
    *((_DWORD *)this + 9) = 2;
    return;
  }
  Char = CSerialStream::GetChar(*((CSerialStream **)this + 1), v6, v4, v5);
  *((_DWORD *)a2 + 1) = 1;
  v8 = Char;
  if ( Char == 47 )
  {
    *((_DWORD *)a2 + 1) = 0;
    CHtmlScanner::EatBlanks(this);
    if ( (unsigned int)CSerialStream::Eof(*((CSerialStream **)this + 1)) )
    {
      *(_DWORD *)a2 = 2;
      *((_DWORD *)this + 9) = 2;
      return;
    }
    v8 = CSerialStream::GetChar(*((CSerialStream **)this + 1), v31, v32, v33);
  }
  v9 = 0;
  if ( !(unsigned int)_o_iswspace(v8) )
  {
    do
    {
      if ( v8 == 62 || v9 >= 0x100 )
        break;
      v12 = v9++;
      *((_WORD *)this + v12 + 68) = v8;
      if ( v9 == 1 )
      {
        if ( *((_WORD *)this + 68) == 37 )
          goto LABEL_13;
      }
      else if ( v9 == 3
             && *((_DWORD *)a2 + 1)
             && *((_WORD *)this + 68) == 33
             && *((_WORD *)this + 69) == 45
             && *((_WORD *)this + 70) == 45 )
      {
        goto LABEL_37;
      }
      v13 = *((_QWORD *)this + 1);
      if ( *(__int16 *)(v13 + 40) <= 0
        && *(_QWORD *)(v13 + 88) >= v13 + 2 * ((unsigned __int64)*(unsigned int *)(v13 + 84) + 21)
        && !*(_DWORD *)(v13 + 116)
        && *(_DWORD *)(v13 + 100) >= *(_DWORD *)(v13 + 104)
        && *(_DWORD *)(v13 + 96) == *(_DWORD *)(v13 + 296)
        && (unsigned int)CMmStreamConsecBuf::Eof((CMmStreamConsecBuf *)(v13 + 288)) )
      {
        break;
      }
      v8 = CSerialStream::GetChar(*((CSerialStream **)this + 1), v13, v10, v11);
    }
    while ( !(unsigned int)_o_iswspace(v8) );
    if ( v9 != 3 )
      goto LABEL_13;
LABEL_37:
    if ( *((_DWORD *)a2 + 1)
      && *((_WORD *)this + 68) == 33
      && *((_WORD *)this + 69) == 45
      && *((_WORD *)this + 70) == 45
      && !(unsigned int)CSerialStream::Eof(*((CSerialStream **)this + 1)) )
    {
      v46 = 0;
      v26 = 0;
      v47 = 0;
      v48 = 0;
      v49 = 0;
      do
      {
        if ( v26 >= 15 )
          break;
        v27 = CSerialStream::GetChar(*((CSerialStream **)this + 1), v23, v24, v25);
        v28 = (CSerialStream *)*((_QWORD *)this + 1);
        v8 = v27;
        v29 = v26++;
        *((_WORD *)&v46 + v29) = v8;
      }
      while ( !(unsigned int)CSerialStream::Eof(v28) );
      if ( (unsigned int)CSerialStream::Eof(*((CSerialStream **)this + 1))
        || (unsigned int)_o__wcsnicmp(L"[if gte mso 9]>", &v46, 15, v30) )
      {
        while ( v26 > 0 )
        {
          v42 = *((_QWORD *)this + 1);
          v43 = (unsigned int)v26--;
          v44 = *(__int16 *)(v42 + 40);
          if ( (int)v44 < 20 )
          {
            *(_WORD *)(v42 + 2 * v44) = *(&v45 + v43);
            ++*(_WORD *)(v42 + 40);
          }
        }
        v8 = 45;
        *((_WORD *)this + v9 + 68) = 0;
LABEL_14:
        if ( v9 != 256 )
          goto LABEL_15;
        goto LABEL_31;
      }
      v9 = 17;
      *(_QWORD *)((char *)this + 142) = v46;
      *(_QWORD *)((char *)this + 150) = v47;
      *(_QWORD *)((char *)this + 158) = v48;
      *(_DWORD *)((char *)this + 166) = v49;
    }
  }
LABEL_13:
  *((_WORD *)this + v9 + 68) = 0;
  if ( v8 != 62 )
    goto LABEL_14;
LABEL_31:
  v21 = *((_QWORD *)this + 1);
  v22 = *(__int16 *)(v21 + 40);
  if ( (int)v22 < 20 )
  {
    *(_WORD *)(v21 + 2 * v22) = v8;
    ++*(_WORD *)(v21 + 40);
  }
LABEL_15:
  v14 = -1;
  v15 = (char *)this + 136;
  v16 = -1;
  do
    ++v16;
  while ( *(_WORD *)&v15[2 * v16] );
  for ( i = (&TagHashTable)[((unsigned int (__fastcall *)(void ***, char *, _QWORD))TagHashTable[2])(
                              &TagHashTable,
                              (char *)this + 136,
                              (unsigned int)v16)
                          + 1]; i; i = (void **)i[2] )
  {
    if ( !(unsigned int)_o__wcsnicmp((char *)this + 136, *i, (unsigned int)v16, v17)
      && !*((_WORD *)*i + (unsigned int)v16) )
    {
      v19 = i[1];
      v20 = v19[2];
      *((_QWORD *)a2 + 1) = v19;
LABEL_22:
      *(_DWORD *)a2 = v20;
      goto LABEL_23;
    }
  }
  v34 = *((_DWORD *)this + 15);
  if ( !v34 || (unsigned int)_o__wcsnicmp((char *)this + 136, *((_QWORD *)this + 6), v34, v17) )
  {
    v35 = wcschr((const wchar_t *)this + 68, 0x3Au);
    *((_QWORD *)a2 + 1) = 0;
    v20 = 62;
    if ( !v35 )
      v20 = 1;
    goto LABEL_22;
  }
  v36 = *((unsigned int *)this + 15);
  do
    ++v14;
  while ( *(_WORD *)&v15[2 * v14] );
  v37 = v14 - v36;
  v38 = &v15[2 * v36];
  for ( j = (&TagHashTable)[((unsigned int (__fastcall *)(void ***, char *, _QWORD))TagHashTable[2])(
                              &TagHashTable,
                              v38,
                              v37)
                          + 1]; j; j = (void **)j[2] )
  {
    if ( !(unsigned int)_o__wcsnicmp(v38, *j, v37, v40) && !*((_WORD *)*j + v37) )
    {
      v41 = j[1];
      v20 = v41[2];
      *((_QWORD *)a2 + 1) = v41;
      goto LABEL_22;
    }
  }
  *(_DWORD *)a2 = 61;
  *((_QWORD *)a2 + 1) = 0;
  (*(void (__fastcall **)(char *, char *, _QWORD, __int64))(*((_QWORD *)a2 + 2) + 32LL))(
    (char *)a2 + 16,
    v38 + 2,
    0,
    0xFFFFFFFFLL);
  v20 = *(_DWORD *)a2;
LABEL_23:
  *((_DWORD *)this + 9) = v20;
}

```

## disassembly

```asm
0x1800074e0  push    rbp
0x1800074e2  push    rsi
0x1800074e3  push    r12
0x1800074e5  push    r13
0x1800074e7  push    r15
0x1800074e9  mov     rbp, rsp
0x1800074ec  sub     rsp, 70h
0x1800074f0  mov     rax, cs:__security_cookie
0x1800074f7  xor     rax, rsp
0x1800074fa  mov     [rbp+var_20], rax
0x1800074fe  xor     r15d, r15d
0x180007501  mov     r12d, 1
0x180007507  mov     [rcx+20h], r15d
0x18000750b  mov     r13, rdx
0x18000750e  mov     [rdx], r12d
0x180007511  mov     rsi, rcx
0x180007514  mov     [rdx+8], r15
0x180007518  call    ?EatBlanks@CHtmlScanner@@AEAAXXZ; CHtmlScanner::EatBlanks(void)
0x18000751d  mov     rdx, [rsi+8]
0x180007521  cmp     [rdx+28h], r15w
0x180007526  jg      short loc_18000753D
0x180007528  mov     ecx, [rdx+54h]
0x18000752b  add     rcx, 15h
0x18000752f  lea     rcx, [rdx+rcx*2]
0x180007533  cmp     [rdx+58h], rcx
0x180007537  jnb     loc_1800078BE
0x18000753d  mov     rcx, [rsi+8]; this
0x180007541  mov     [rsp+70h+var_8], rdi
0x180007546  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x18000754b  mov     [r13+4], r12d
0x18000754f  movzx   edi, ax
0x180007552  cmp     ax, 2Fh ; '/'
0x180007556  jz      loc_180007911
0x18000755c  mov     [rsp+70h+arg_10], rbx
0x180007564  movzx   ecx, di
0x180007567  mov     [rsp+70h+var_10], r14
0x18000756c  mov     ebx, r15d
0x18000756f  call    cs:__imp__o_iswspace
0x180007575  test    eax, eax
0x180007577  jnz     short loc_1800075E7
0x180007579  cmp     di, 3Eh ; '>'
0x18000757d  jz      short loc_1800075DE
0x18000757f  cmp     ebx, 100h
0x180007585  jnb     short loc_1800075DE
0x180007587  mov     eax, ebx
0x180007589  inc     ebx
0x18000758b  mov     [rsi+rax*2+88h], di
0x180007593  cmp     ebx, r12d
0x180007596  jz      loc_1800076FD
0x18000759c  cmp     ebx, 3
0x18000759f  jz      loc_18000772F
0x1800075a5  mov     rdx, [rsi+8]
0x1800075a9  cmp     [rdx+28h], r15w
0x1800075ae  jg      short loc_1800075C5
0x1800075b0  mov     ecx, [rdx+54h]
0x1800075b3  add     rcx, 15h
0x1800075b7  lea     rcx, [rdx+rcx*2]
0x1800075bb  cmp     [rdx+58h], rcx
0x1800075bf  jnb     loc_1800076C2
0x1800075c5  mov     rcx, [rsi+8]; this
0x1800075c9  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x1800075ce  movzx   ecx, ax
0x1800075d1  movzx   edi, ax
0x1800075d4  call    cs:__imp__o_iswspace
0x1800075da  test    eax, eax
0x1800075dc  jz      short loc_180007579
0x1800075de  cmp     ebx, 3
0x1800075e1  jz      loc_180007763
0x1800075e7  mov     ecx, ebx
0x1800075e9  mov     [rsi+rcx*2+88h], r15w
0x1800075f2  cmp     di, 3Eh ; '>'
0x1800075f6  jz      loc_180007710
0x1800075fc  cmp     ebx, 100h
0x180007602  jz      loc_180007710
0x180007608  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000760f  lea     rdi, [rsi+88h]
0x180007616  mov     rbx, r15
0x180007619  nop     dword ptr [rax+00000000h]
0x180007620  inc     rbx
0x180007623  cmp     word ptr [rdi+rbx*2], 0
0x180007628  jnz     short loc_180007620
0x18000762a  mov     rax, cs:?TagHashTable@@3VCTagHashTable@@A; CTagHashTable TagHashTable
0x180007631  lea     r12, ?TagHashTable@@3VCTagHashTable@@A; CTagHashTable TagHashTable
0x180007638  mov     r8d, ebx
0x18000763b  mov     rdx, rdi
0x18000763e  mov     rcx, r12
0x180007641  mov     rax, [rax+10h]
0x180007645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000764a  mov     ecx, eax
0x18000764c  mov     r14, [r12+rcx*8+8]
0x180007651  test    r14, r14
0x180007654  jz      loc_18000793F
0x18000765a  mov     rdx, [r14]
0x18000765d  mov     rcx, rdi
0x180007660  mov     r8d, ebx
0x180007663  mov     r12d, ebx
0x180007666  call    cs:__imp__o__wcsnicmp
0x18000766c  test    eax, eax
0x18000766e  jnz     loc_180007908
0x180007674  mov     rax, [r14]
0x180007677  cmp     word ptr [rax+r12*2], 0
0x18000767d  jnz     loc_180007908
0x180007683  mov     rax, [r14+8]
0x180007687  mov     r12d, [rax+8]
0x18000768b  mov     [r13+8], rax
0x18000768f  mov     [r13+0], r12d
0x180007693  mov     [rsi+24h], r12d
0x180007697  mov     r14, [rsp+70h+var_10]
0x18000769c  mov     rbx, [rsp+70h+arg_10]
0x1800076a4  mov     rdi, [rsp+70h+var_8]
0x1800076a9  mov     rcx, [rbp+var_20]
0x1800076ad  xor     rcx, rsp; StackCookie
0x1800076b0  call    __security_check_cookie
0x1800076b5  add     rsp, 70h
0x1800076b9  pop     r15
0x1800076bb  pop     r13
0x1800076bd  pop     r12
0x1800076bf  pop     rsi
0x1800076c0  pop     rbp
0x1800076c1  retn
0x1800076c2  cmp     [rdx+74h], r15d
0x1800076c6  jnz     loc_1800075C5
0x1800076cc  mov     eax, [rdx+68h]
0x1800076cf  cmp     [rdx+64h], eax
0x1800076d2  jb      loc_1800075C5
0x1800076d8  lea     rcx, [rdx+120h]; this
0x1800076df  mov     eax, [rcx+8]
0x1800076e2  cmp     [rdx+60h], eax
0x1800076e5  jnz     loc_1800075C5
0x1800076eb  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x1800076f0  test    eax, eax
0x1800076f2  jnz     loc_1800075DE
0x1800076f8  jmp     loc_1800075C5
0x1800076fd  cmp     word ptr [rsi+88h], 25h ; '%'
0x180007705  jnz     loc_1800075A5
0x18000770b  jmp     loc_1800075E7
0x180007710  mov     rcx, [rsi+8]
0x180007714  movsx   rax, word ptr [rcx+28h]
0x180007719  cmp     eax, 14h
0x18000771c  jge     loc_180007608
0x180007722  mov     [rcx+rax*2], di
0x180007726  inc     word ptr [rcx+28h]
0x18000772a  jmp     loc_180007608
0x18000772f  cmp     [r13+4], r15d
0x180007733  jz      loc_1800075A5
0x180007739  cmp     word ptr [rsi+88h], 21h ; '!'
0x180007741  jnz     loc_1800075A5
0x180007747  cmp     word ptr [rsi+8Ah], 2Dh ; '-'
0x18000774f  jnz     loc_1800075A5
0x180007755  cmp     word ptr [rsi+8Ch], 2Dh ; '-'
0x18000775d  jnz     loc_1800075A5
0x180007763  cmp     [r13+4], r15d
0x180007767  jz      loc_1800075E7
0x18000776d  cmp     word ptr [rsi+88h], 21h ; '!'
0x180007775  jnz     loc_1800075E7
0x18000777b  cmp     word ptr [rsi+8Ah], 2Dh ; '-'
0x180007783  jnz     loc_1800075E7
0x180007789  cmp     word ptr [rsi+8Ch], 2Dh ; '-'
0x180007791  jnz     loc_1800075E7
0x180007797  mov     rcx, [rsi+8]; this
0x18000779b  call    ?Eof@CSerialStream@@QEAAHXZ; CSerialStream::Eof(void)
0x1800077a0  test    eax, eax
0x1800077a2  jnz     loc_1800075E7
0x1800077a8  mov     [rbp+var_40], r15
0x1800077ac  mov     r14d, r15d
0x1800077af  mov     [rbp+var_38], r15
0x1800077b3  mov     [rbp+var_30], r15
0x1800077b7  mov     [rbp+var_28], r15
0x1800077bb  nop     dword ptr [rax+rax+00h]
0x1800077c0  cmp     r14d, 0Fh
0x1800077c4  jge     short loc_1800077EA
0x1800077c6  mov     rcx, [rsi+8]; this
0x1800077ca  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x1800077cf  mov     rcx, [rsi+8]; this
0x1800077d3  movzx   edi, ax
0x1800077d6  movsxd  rax, r14d
0x1800077d9  inc     r14d
0x1800077dc  mov     word ptr [rbp+rax*2+var_40], di
0x1800077e1  call    ?Eof@CSerialStream@@QEAAHXZ; CSerialStream::Eof(void)
0x1800077e6  test    eax, eax
0x1800077e8  jz      short loc_1800077C0
0x1800077ea  mov     rcx, [rsi+8]; this
0x1800077ee  call    ?Eof@CSerialStream@@QEAAHXZ; CSerialStream::Eof(void)
0x1800077f3  test    eax, eax
0x1800077f5  jnz     loc_180007A1B
0x1800077fb  mov     r8d, 0Fh
0x180007801  lea     rdx, [rbp+var_40]
0x180007805  lea     rcx, aIfGteMso9_0; "[if gte mso 9]>"
0x18000780c  call    cs:__imp__o__wcsnicmp
0x180007812  test    eax, eax
0x180007814  jnz     loc_180007A1B
0x18000781a  movzx   eax, word ptr [rbp+var_40]
0x18000781e  mov     ebx, 11h
0x180007823  mov     [rsi+8Eh], ax
0x18000782a  movzx   eax, word ptr [rbp+var_40+2]
0x18000782e  mov     [rsi+90h], ax
0x180007835  movzx   eax, word ptr [rbp+var_40+4]
0x180007839  mov     [rsi+92h], ax
0x180007840  movzx   eax, word ptr [rbp+var_40+6]
0x180007844  mov     [rsi+94h], ax
0x18000784b  movzx   eax, word ptr [rbp+var_38]
0x18000784f  mov     [rsi+96h], ax
0x180007856  movzx   eax, word ptr [rbp+var_38+2]
0x18000785a  mov     [rsi+98h], ax
0x180007861  movzx   eax, word ptr [rbp+var_38+4]
0x180007865  mov     [rsi+9Ah], ax
0x18000786c  movzx   eax, word ptr [rbp+var_38+6]
0x180007870  mov     [rsi+9Ch], ax
0x180007877  movzx   eax, word ptr [rbp+var_30]
0x18000787b  mov     [rsi+9Eh], ax
0x180007882  movzx   eax, word ptr [rbp+var_30+2]
0x180007886  mov     [rsi+0A0h], ax
0x18000788d  movzx   eax, word ptr [rbp+var_30+4]
0x180007891  mov     [rsi+0A2h], ax
0x180007898  movzx   eax, word ptr [rbp+var_30+6]
0x18000789c  mov     [rsi+0A4h], ax
0x1800078a3  movzx   eax, word ptr [rbp+var_28]
0x1800078a7  mov     [rsi+0A6h], ax
0x1800078ae  movzx   eax, word ptr [rbp+var_28+2]
0x1800078b2  mov     [rsi+0A8h], ax
0x1800078b9  jmp     loc_1800075E7
0x1800078be  cmp     [rdx+74h], r15d
0x1800078c2  jnz     loc_18000753D
0x1800078c8  mov     eax, [rdx+68h]
0x1800078cb  cmp     [rdx+64h], eax
0x1800078ce  jb      loc_18000753D
0x1800078d4  lea     rcx, [rdx+120h]; this
0x1800078db  mov     eax, [rcx+8]
0x1800078de  cmp     [rdx+60h], eax
0x1800078e1  jnz     loc_18000753D
0x1800078e7  call    ?Eof@CMmStreamConsecBuf@@QEAAHXZ; CMmStreamConsecBuf::Eof(void)
0x1800078ec  test    eax, eax
0x1800078ee  jz      loc_18000753D
0x1800078f4  mov     dword ptr [r13+0], 2
0x1800078fc  mov     dword ptr [rsi+24h], 2
0x180007903  jmp     loc_1800076A9
0x180007908  mov     r14, [r14+10h]
0x18000790c  jmp     loc_180007651
0x180007911  mov     rcx, rsi; this
0x180007914  mov     [r13+4], r15d
0x180007918  call    ?EatBlanks@CHtmlScanner@@AEAAXXZ; CHtmlScanner::EatBlanks(void)
0x18000791d  mov     rcx, [rsi+8]; this
0x180007921  call    ?Eof@CSerialStream@@QEAAHXZ; CSerialStream::Eof(void)
0x180007926  test    eax, eax
0x180007928  jnz     loc_180007A07
0x18000792e  mov     rcx, [rsi+8]; this
0x180007932  call    ?GetChar@CSerialStream@@QEAA_WXZ; CSerialStream::GetChar(void)
0x180007937  movzx   edi, ax
0x18000793a  jmp     loc_18000755C
0x18000793f  mov     eax, [rsi+3Ch]
0x180007942  test    eax, eax
0x180007944  jz      short loc_18000795A
0x180007946  mov     rdx, [rsi+30h]
0x18000794a  mov     r8d, eax
0x18000794d  mov     rcx, rdi
0x180007950  call    cs:__imp__o__wcsnicmp
0x180007956  test    eax, eax
0x180007958  jz      short loc_18000798A
0x18000795a  mov     edx, 3Ah ; ':'; Ch
0x18000795f  mov     rcx, rdi; Str
0x180007962  call    cs:__imp_wcschr
0x180007968  mov     qword ptr [r13+8], 0
0x180007970  mov     r12d, 3Eh ; '>'
0x180007976  test    rax, rax
0x180007979  jnz     loc_18000768F
0x18000797f  mov     r12d, 1
0x180007985  jmp     loc_18000768F
0x18000798a  mov     eax, [rsi+3Ch]
0x18000798d  nop     dword ptr [rax]
0x180007990  inc     r15
0x180007993  cmp     word ptr [rdi+r15*2], 0
0x180007999  jnz     short loc_180007990
0x18000799b  sub     r15d, eax
0x18000799e  lea     r14, [rdi+rax*2]
0x1800079a2  mov     rax, cs:?TagHashTable@@3VCTagHashTable@@A; CTagHashTable TagHashTable
0x1800079a9  lea     rbx, ?TagHashTable@@3VCTagHashTable@@A; CTagHashTable TagHashTable
0x1800079b0  mov     r8d, r15d
0x1800079b3  mov     rdx, r14
0x1800079b6  mov     rcx, rbx
0x1800079b9  mov     rax, [rax+10h]
0x1800079bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079c2  mov     ecx, eax
0x1800079c4  mov     rbx, [rbx+rcx*8+8]
0x1800079c9  test    rbx, rbx
0x1800079cc  jz      loc_180007A5B
0x1800079d2  mov     rdx, [rbx]
0x1800079d5  mov     rcx, r14
0x1800079d8  mov     r8d, r15d
0x1800079db  call    cs:__imp__o__wcsnicmp
0x1800079e1  test    eax, eax
0x1800079e3  jnz     short loc_180007A01
0x1800079e5  mov     rax, [rbx]
0x1800079e8  cmp     word ptr [rax+r15*2], 0
0x1800079ee  jnz     short loc_180007A01
0x1800079f0  mov     rax, [rbx+8]
0x1800079f4  mov     r12d, [rax+8]
0x1800079f8  mov     [r13+8], rax
0x1800079fc  jmp     loc_18000768F
0x180007a01  mov     rbx, [rbx+10h]
0x180007a05  jmp     short loc_1800079C9
  ... truncated ...
```
