# CTxtBreaker::OnPostReplaceRange(long,long,long,long,long)

- ea: `0x18008d6a0`
- end: `0x18008dabb`
- name: `?OnPostReplaceRange@CTxtBreaker@@UEAAXJJJJJ@Z`
- size: `1051`
- prototype: `void(CTxtBreaker *__hidden this, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x180008f70`
- `0x180008fec`
- `0x18001ce50`
- `0x18001f230`
- `0x18002720c`
- `0x180032c44`
- `0x180032fc4`
- `0x18003a91c`
- `0x180083d24`
- `0x18008d160`
- `0x18008d458`
- `0x18008d6a0`
- `0x18008dd00`
- `0x18008ddb4`
- `0x180093c00`

## import_xrefs

- `USP10!ScriptBreak` at `0x18008d9a1`
- `USP10!ScriptBreak` at `0x18008d9a1`

## pseudocode

```c
void __fastcall CTxtBreaker::OnPostReplaceRange(CTxtBreaker *this, int a2, int a3, int a4)
{
  int v6; // edi
  int v8; // r15d
  CUniscribe *v9; // rax
  int v10; // r13d
  CBreakArray *v11; // r14
  CBreakArray **v12; // rax
  int v13; // r11d
  int v14; // r11d
  int v15; // edi
  int v16; // r14d
  CBreakArray *v17; // rcx
  CUniscribe *v18; // rcx
  int v19; // r8d
  int cInChars; // r14d
  SCRIPT_LOGATTR *v21; // r14
  CBreakArray *v22; // rcx
  CBreakArray **v23; // r13
  unsigned __int8 *v24; // rcx
  __int64 v25; // r12
  SCRIPT_LOGATTR **v26; // rax
  int v27; // eax
  __int64 v28; // rsi
  const SCRIPT_ANALYSIS *v29; // rdi
  const struct SCRIPT_PROPERTIES *v30; // rax
  unsigned int v31; // r8d
  int v32; // edi
  int v33; // eax
  __int64 v34; // rdi
  SCRIPT_LOGATTR *v35; // r15
  int v36; // r12d
  CBreakArray *v37; // rcx
  int v38; // r8d
  int v39; // eax
  CBreakArray *v40; // rcx
  _DWORD *v41; // rdi
  int v42; // [rsp+50h] [rbp-B0h] BYREF
  int v43; // [rsp+54h] [rbp-ACh] BYREF
  int v44; // [rsp+58h] [rbp-A8h]
  void *lpMem; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+68h] [rbp-98h]
  CBreakArray **v47; // [rsp+70h] [rbp-90h]
  SCRIPT_LOGATTR *psla; // [rsp+78h] [rbp-88h]
  CUniscribe *Uniscribe; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h]
  _BYTE v51[16]; // [rsp+90h] [rbp-70h] BYREF
  int v52; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v53[512]; // [rsp+B0h] [rbp-50h] BYREF

  v44 = a2;
  psla = (SCRIPT_LOGATTR *)this;
  v6 = a2;
  if ( !a3 && !a4 )
    return;
  CTxtPtr::CTxtPtr((CTxtPtr *)v51, *((struct CTxtEdit **)this + 2), a2);
  if ( v6 <= 0 )
  {
    v8 = 0;
    v46 = 0;
  }
  else
  {
    v8 = v6 - 1;
    v46 = v6 - 1;
  }
  LODWORD(lpMem) = 0;
  v43 = 0;
  CTxtPtr::FindWhiteSpaceBound((CTxtPtr *)v51, a4, (int *)&lpMem, &v43, 0);
  v9 = (CUniscribe *)*((_QWORD *)this + 3);
  Uniscribe = v9;
  if ( v9 )
  {
    v42 = 1;
    v47 = (CBreakArray **)((char *)this + 32);
    v10 = 3;
    v11 = v9;
  }
  else
  {
    v12 = (CBreakArray **)((char *)this + 32);
    v10 = 1;
    v11 = *v12;
    v47 = v12;
    if ( !v11 )
    {
      v47 = v12;
      v11 = 0;
      v42 = 1;
      goto LABEL_15;
    }
    v42 = 0;
  }
  while ( v8 > (int)lpMem && ((unsigned int)CBreakArray::GetBreak(v11, v8) != v42 || v13) )
    v46 = --v8;
LABEL_15:
  CTxtPtr::AdvanceCp((CTxtPtr *)v51, v8 - v52);
  v14 = a3 + v6;
  v43 += a3 - a4;
  if ( v11 )
  {
    v15 = v43;
    while ( v14 < v15 )
    {
      if ( (unsigned int)CBreakArray::GetBreak(v11, v14) == v42 )
      {
        if ( !v10 )
          break;
        --v10;
      }
      ++v14;
    }
    v6 = v44;
  }
  v16 = v14 + a4 - a3;
  if ( v8 == v16 )
  {
    if ( Uniscribe )
      CBreakArray::ReplaceBreak(Uniscribe, v6, a3, 0);
    v17 = *(CBreakArray **)&psla[32];
    if ( v17 )
      CBreakArray::ReplaceBreak(v17, v6, a3, 0);
    return;
  }
  lpMem = 0;
  v42 = 0;
  Uniscribe = GetUniscribe();
  if ( !Uniscribe )
    return;
  cInChars = v16 - v8;
  CUniscribe::CreateClientStruc(v18, v53, v19, (struct tagUSP_CLIENT **)&lpMem, cInChars, 7u);
  if ( !lpMem )
    return;
  CTxtPtr::GetText((CTxtPtr *)v51, cInChars, **(unsigned __int16 ***)lpMem);
  if ( (int)CUniscribe::ItemizeString(
              *(CUniscribe **)lpMem,
              (struct tagUSP_CLIENT *)lpMem,
              0,
              &v42,
              **(WCHAR ***)lpMem,
              cInChars,
              0,
              0,
              0) > 0 )
  {
    v21 = psla;
    v22 = *(CBreakArray **)&psla[24];
    if ( v22 )
      CBreakArray::ReplaceBreak(v22, v6, a3, a4);
    v23 = v47;
    if ( *v47 )
      CBreakArray::ReplaceBreak(*v47, v6, a3, a4);
    v24 = (unsigned __int8 *)lpMem;
    v25 = *(_QWORD *)(*(_QWORD *)lpMem + 16LL);
    v47 = **(CBreakArray ****)lpMem;
    v26 = (SCRIPT_LOGATTR **)*((_QWORD *)lpMem + 1);
    v50 = v25;
    psla = *v26;
    v27 = 0;
    v43 = 0;
    if ( v42 <= 0 )
      goto LABEL_54;
    do
    {
      v28 = v27;
      v29 = (const SCRIPT_ANALYSIS *)(v25 + 8LL * v27);
      v30 = CUniscribe::GeteProp(Uniscribe, *(_WORD *)&v29[1] & 0x3FF);
      if ( (*(_DWORD *)v30 & 0x20000) != 0 && (*(_DWORD *)v30 & 0xC0000) != 0 )
      {
        if ( ScriptBreak(
               (const WCHAR *)v47 + *(int *)(v25 + 8 * v28),
               *(_DWORD *)(v25 + 8 * v28 + 8) - *(_DWORD *)(v25 + 8 * v28),
               v29 + 1,
               psla) )
        {
          break;
        }
        v32 = *(_DWORD *)(v25 + 8 * v28);
        v33 = v32 + v8;
        v34 = (unsigned int)(*(_DWORD *)(v25 + 8 * v28 + 8) + ~v32);
        if ( (int)v34 >= 0 )
        {
          v35 = psla;
          v36 = v33;
          do
          {
            v37 = *(CBreakArray **)&v21[24];
            if ( v37 )
            {
              v38 = (*(_BYTE *)&v35[v34] >> 3) & 1;
              v44 = v36 + v34;
              CBreakArray::SetBreak(v37, v36 + v34, v38);
              v39 = v44;
            }
            else
            {
              v39 = v36 + v34;
            }
            if ( *v23 )
            {
              LOBYTE(v31) = ~*(_BYTE *)&v35[v34];
              CBreakArray::SetBreak(*v23, v39, (v31 >> 2) & 1);
            }
            v34 = (unsigned int)(v34 - 1);
          }
          while ( (int)v34 >= 0 );
          v8 = v46;
          v25 = v50;
        }
      }
      else
      {
        v40 = *(CBreakArray **)&v21[24];
        v41 = (_DWORD *)(v25 + 8 * v28);
        if ( v40 )
          CBreakArray::ClearBreak(v40, *v41 + v8, *(_DWORD *)(v25 + 8 * v28 + 8) - *v41);
        if ( *v23 )
          CBreakArray::ClearBreak(*v23, v8 + *v41, *(_DWORD *)(v25 + 8 * (v28 + 1)) - *v41);
      }
      v27 = v43 + 1;
      v43 = v27;
    }
    while ( v27 < v42 );
  }
  v24 = (unsigned __int8 *)lpMem;
LABEL_54:
  if ( v24 && v53 != v24 )
    CW32System::FreePv(v24);
}

```

## disassembly

```asm
0x18008d6a0  push    rbp
0x18008d6a2  push    rbx
0x18008d6a3  push    rsi
0x18008d6a4  push    rdi
0x18008d6a5  push    r12
0x18008d6a7  push    r13
0x18008d6a9  push    r14
0x18008d6ab  push    r15
0x18008d6ad  lea     rbp, [rsp-1C8h]
0x18008d6b5  sub     rsp, 2C8h
0x18008d6bc  mov     rax, cs:__security_cookie
0x18008d6c3  xor     rax, rsp
0x18008d6c6  mov     [rbp+200h+var_50], rax
0x18008d6cd  xor     ebx, ebx
0x18008d6cf  mov     [rsp+300h+var_2A8], edx
0x18008d6d3  mov     [rsp+300h+psla], rcx
0x18008d6d8  mov     r12d, r9d
0x18008d6db  mov     esi, r8d
0x18008d6de  mov     edi, edx
0x18008d6e0  mov     r13, rcx
0x18008d6e3  test    r8d, r8d
0x18008d6e6  jnz     short loc_18008D6F1
0x18008d6e8  test    r9d, r9d
0x18008d6eb  jz      loc_18008DA97
0x18008d6f1  mov     rdx, [rcx+10h]; struct CTxtEdit *
0x18008d6f5  mov     r8d, edi; int
0x18008d6f8  lea     rcx, [rbp+200h+var_270]; this
0x18008d6fc  call    ??0CTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CTxtPtr::CTxtPtr(CTxtEdit *,long)
0x18008d701  test    edi, edi
0x18008d703  jle     short loc_18008D710
0x18008d705  lea     r15d, [rdi-1]
0x18008d709  mov     [rsp+300h+var_298], r15d
0x18008d70e  jmp     short loc_18008D717
0x18008d710  mov     r15d, ebx
0x18008d713  mov     [rsp+300h+var_298], ebx
0x18008d717  lea     r9, [rsp+300h+var_2AC]; int *
0x18008d71c  mov     dword ptr [rsp+300h+lpMem], ebx
0x18008d720  lea     r8, [rsp+300h+lpMem]; int *
0x18008d725  mov     [rsp+300h+var_2AC], ebx
0x18008d729  mov     edx, r12d; int
0x18008d72c  mov     dword ptr [rsp+300h+pwcInChars], ebx; unsigned int
0x18008d730  lea     rcx, [rbp+200h+var_270]; this
0x18008d734  call    ?FindWhiteSpaceBound@CTxtPtr@@QEAAJJAEAJ0K@Z; CTxtPtr::FindWhiteSpaceBound(long,long &,long &,ulong)
0x18008d739  mov     rax, [r13+18h]
0x18008d73d  mov     ebx, 1
0x18008d742  mov     [rbp+200h+var_280], rax
0x18008d746  test    rax, rax
0x18008d749  jz      short loc_18008D764
0x18008d74b  add     r13, 20h ; ' '
0x18008d74f  mov     [rsp+300h+var_2B0], ebx
0x18008d753  lea     r11d, [rbx+2]
0x18008d757  mov     [rsp+300h+var_290], r13
0x18008d75c  mov     r13d, r11d
0x18008d75f  mov     r14, rax
0x18008d762  jmp     short loc_18008D783
0x18008d764  lea     rax, [r13+20h]
0x18008d768  mov     r13d, ebx
0x18008d76b  mov     r14, [rax]
0x18008d76e  mov     [rsp+300h+var_290], rax
0x18008d773  test    r14, r14
0x18008d776  jz      short loc_18008D7AD
0x18008d778  mov     r11d, ebx
0x18008d77b  mov     [rsp+300h+var_2B0], 0
0x18008d783  cmp     r15d, dword ptr [rsp+300h+lpMem]
0x18008d788  jle     short loc_18008D7B9
0x18008d78a  mov     edx, r15d; int
0x18008d78d  mov     rcx, r14; this
0x18008d790  call    ?GetBreak@CBreakArray@@QEAAHJ@Z; CBreakArray::GetBreak(long)
0x18008d795  cmp     eax, [rsp+300h+var_2B0]
0x18008d799  jnz     short loc_18008D7A3
0x18008d79b  test    r11d, r11d
0x18008d79e  jz      short loc_18008D7B9
0x18008d7a0  sub     r11d, ebx
0x18008d7a3  sub     r15d, ebx
0x18008d7a6  mov     [rsp+300h+var_298], r15d
0x18008d7ab  jmp     short loc_18008D783
0x18008d7ad  mov     [rsp+300h+var_290], rax
0x18008d7b2  xor     r14d, r14d
0x18008d7b5  mov     [rsp+300h+var_2B0], ebx
0x18008d7b9  mov     edx, r15d
0x18008d7bc  lea     rcx, [rbp+200h+var_270]; this
0x18008d7c0  sub     edx, [rbp+200h+var_260]; int
0x18008d7c3  call    ?AdvanceCp@CTxtPtr@@QEAAJJ@Z; CTxtPtr::AdvanceCp(long)
0x18008d7c8  mov     eax, esi
0x18008d7ca  lea     r11d, [rsi+rdi]
0x18008d7ce  sub     eax, r12d
0x18008d7d1  add     [rsp+300h+var_2AC], eax
0x18008d7d5  test    r14, r14
0x18008d7d8  jz      short loc_18008D805
0x18008d7da  mov     edi, [rsp+300h+var_2AC]
0x18008d7de  cmp     r11d, edi
0x18008d7e1  jge     short loc_18008D801
0x18008d7e3  mov     edx, r11d; int
0x18008d7e6  mov     rcx, r14; this
0x18008d7e9  call    ?GetBreak@CBreakArray@@QEAAHJ@Z; CBreakArray::GetBreak(long)
0x18008d7ee  cmp     eax, [rsp+300h+var_2B0]
0x18008d7f2  jnz     short loc_18008D7FC
0x18008d7f4  test    r13d, r13d
0x18008d7f7  jz      short loc_18008D801
0x18008d7f9  sub     r13d, ebx
0x18008d7fc  add     r11d, ebx
0x18008d7ff  jmp     short loc_18008D7DE
0x18008d801  mov     edi, [rsp+300h+var_2A8]
0x18008d805  mov     r14d, r12d
0x18008d808  sub     r14d, esi
0x18008d80b  add     r14d, r11d
0x18008d80e  cmp     r15d, r14d
0x18008d811  jnz     short loc_18008D84D
0x18008d813  mov     rcx, [rbp+200h+var_280]; this
0x18008d817  test    rcx, rcx
0x18008d81a  jz      short loc_18008D829
0x18008d81c  xor     r9d, r9d; int
0x18008d81f  mov     r8d, esi; int
0x18008d822  mov     edx, edi; int
0x18008d824  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008d829  mov     r14, [rsp+300h+psla]
0x18008d82e  mov     rcx, [r14+20h]; this
0x18008d832  test    rcx, rcx
0x18008d835  jz      loc_18008DA97
0x18008d83b  xor     r9d, r9d; int
0x18008d83e  mov     r8d, esi; int
0x18008d841  mov     edx, edi; int
0x18008d843  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008d848  jmp     loc_18008DA97
0x18008d84d  xor     r13d, r13d
0x18008d850  mov     [rsp+300h+lpMem], r13
0x18008d855  mov     [rsp+300h+var_2B0], r13d
0x18008d85a  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x18008d85f  mov     [rbp+200h+var_280], rax
0x18008d863  test    rax, rax
0x18008d866  jz      loc_18008DA97
0x18008d86c  sub     r14d, r15d
0x18008d86f  mov     [rsp+300h+cInChars], 7; unsigned int
0x18008d877  lea     r9, [rsp+300h+lpMem]; struct tagUSP_CLIENT **
0x18008d87c  mov     dword ptr [rsp+300h+pwcInChars], r14d; int
0x18008d881  lea     rdx, [rbp+200h+var_250]; unsigned __int8 *
0x18008d885  call    ?CreateClientStruc@CUniscribe@@QEAAHPEAEJPEAPEAUtagUSP_CLIENT@@JK@Z; CUniscribe::CreateClientStruc(uchar *,long,tagUSP_CLIENT * *,long,ulong)
0x18008d88a  mov     r8, [rsp+300h+lpMem]
0x18008d88f  test    r8, r8
0x18008d892  jz      loc_18008DA97
0x18008d898  mov     r8, [r8]
0x18008d89b  lea     rcx, [rbp+200h+var_270]; this
0x18008d89f  mov     edx, r14d; int
0x18008d8a2  mov     r8, [r8]; unsigned __int16 *
0x18008d8a5  call    ?GetText@CTxtPtr@@QEAAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x18008d8aa  mov     rdx, [rsp+300h+lpMem]; struct tagUSP_CLIENT *
0x18008d8af  lea     r9, [rsp+300h+var_2B0]; int *
0x18008d8b4  mov     [rsp+300h+var_2C0], r13d; int
0x18008d8b9  xor     r8d, r8d; unsigned __int16
0x18008d8bc  mov     [rsp+300h+var_2C8], r13w; unsigned __int16
0x18008d8c2  mov     [rsp+300h+var_2D0], r13d; int
0x18008d8c7  mov     rcx, [rdx]; this
0x18008d8ca  mov     [rsp+300h+cInChars], r14d; cInChars
0x18008d8cf  mov     rax, [rcx]
0x18008d8d2  mov     [rsp+300h+pwcInChars], rax; pwcInChars
0x18008d8d7  call    ?ItemizeString@CUniscribe@@QEAAHPEAUtagUSP_CLIENT@@GPEAHPEAGHHGH@Z; CUniscribe::ItemizeString(tagUSP_CLIENT *,ushort,int *,ushort *,int,int,ushort,int)
0x18008d8dc  test    eax, eax
0x18008d8de  jle     loc_18008DA7F
0x18008d8e4  mov     r14, [rsp+300h+psla]
0x18008d8e9  mov     rcx, [r14+18h]; this
0x18008d8ed  test    rcx, rcx
0x18008d8f0  jz      short loc_18008D8FF
0x18008d8f2  mov     r9d, r12d; int
0x18008d8f5  mov     r8d, esi; int
0x18008d8f8  mov     edx, edi; int
0x18008d8fa  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008d8ff  mov     r13, [rsp+300h+var_290]
0x18008d904  mov     rcx, [r13+0]; this
0x18008d908  test    rcx, rcx
0x18008d90b  jz      short loc_18008D91A
0x18008d90d  mov     r9d, r12d; int
0x18008d910  mov     r8d, esi; int
0x18008d913  mov     edx, edi; int
0x18008d915  call    ?ReplaceBreak@CBreakArray@@QEAAJJJJ@Z; CBreakArray::ReplaceBreak(long,long,long)
0x18008d91a  mov     rcx, [rsp+300h+lpMem]
0x18008d91f  mov     rax, [rcx]
0x18008d922  mov     r12, [rax+10h]
0x18008d926  mov     rax, [rax]
0x18008d929  mov     [rsp+300h+var_290], rax
0x18008d92e  mov     rax, [rcx+8]
0x18008d932  mov     [rbp+200h+var_278], r12
0x18008d936  mov     rax, [rax]
0x18008d939  mov     [rsp+300h+psla], rax
0x18008d93e  xor     eax, eax
0x18008d940  mov     [rsp+300h+var_2AC], eax
0x18008d944  cmp     [rsp+300h+var_2B0], eax
0x18008d948  jle     loc_18008DA84
0x18008d94e  mov     rcx, [rbp+200h+var_280]; this
0x18008d952  movsxd  rsi, eax
0x18008d955  mov     eax, 3FFh
0x18008d95a  lea     rdi, [r12+rsi*8]
0x18008d95e  movzx   edx, word ptr [rdi+4]
0x18008d962  and     dx, ax; unsigned __int16
0x18008d965  call    ?GeteProp@CUniscribe@@QEAAPEBUSCRIPT_PROPERTIES@@G@Z; CUniscribe::GeteProp(ushort)
0x18008d96a  test    dword ptr [rax], 20000h
0x18008d970  jz      loc_18008DA2B
0x18008d976  test    dword ptr [rax], 0C0000h
0x18008d97c  jz      loc_18008DA2B
0x18008d982  movsxd  rax, dword ptr [r12+rsi*8]
0x18008d986  lea     r8, [rdi+4]; psa
0x18008d98a  mov     edx, [r12+rsi*8+8]
0x18008d98f  mov     rcx, [rsp+300h+var_290]
0x18008d994  sub     edx, [r12+rsi*8]; cChars
0x18008d998  mov     r9, [rsp+300h+psla]; psla
0x18008d99d  lea     rcx, [rcx+rax*2]; pwcChars
0x18008d9a1  call    cs:__imp_ScriptBreak
0x18008d9a8  nop     dword ptr [rax+rax+00h]
0x18008d9ad  test    eax, eax
0x18008d9af  jnz     loc_18008DA7F
0x18008d9b5  mov     edi, [r12+rsi*8]
0x18008d9b9  lea     eax, [rdi+r15]
0x18008d9bd  not     edi
0x18008d9bf  add     edi, [r12+rsi*8+8]
0x18008d9c4  js      loc_18008DA6B
0x18008d9ca  mov     r15, [rsp+300h+psla]
0x18008d9cf  mov     r12d, eax
0x18008d9d2  mov     rcx, [r14+18h]; this
0x18008d9d6  test    rcx, rcx
0x18008d9d9  jz      short loc_18008D9FA
0x18008d9db  movzx   r8d, byte ptr [rdi+r15]
0x18008d9e0  lea     edx, [r12+rdi]; int
0x18008d9e4  shr     r8d, 3
0x18008d9e8  and     r8d, ebx; int
0x18008d9eb  mov     [rsp+300h+var_2A8], edx
0x18008d9ef  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x18008d9f4  mov     eax, [rsp+300h+var_2A8]
0x18008d9f8  jmp     short loc_18008D9FE
0x18008d9fa  lea     eax, [r12+rdi]
0x18008d9fe  mov     rcx, [r13+0]; this
0x18008da02  test    rcx, rcx
0x18008da05  jz      short loc_18008DA1C
0x18008da07  mov     r8b, [rdi+r15]
0x18008da0b  mov     edx, eax; int
0x18008da0d  not     r8b
0x18008da10  shr     r8d, 2
0x18008da14  and     r8d, ebx; int
0x18008da17  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x18008da1c  sub     edi, ebx
0x18008da1e  jns     short loc_18008D9D2
0x18008da20  mov     r15d, [rsp+300h+var_298]
0x18008da25  mov     r12, [rbp+200h+var_278]
0x18008da29  jmp     short loc_18008DA6B
0x18008da2b  mov     rcx, [r14+18h]; this
0x18008da2f  lea     rdi, [r12+rsi*8]
0x18008da33  test    rcx, rcx
0x18008da36  jz      short loc_18008DA4B
0x18008da38  mov     eax, [rdi]
0x18008da3a  mov     r8d, [r12+rsi*8+8]
0x18008da3f  sub     r8d, eax; int
0x18008da42  lea     edx, [rax+r15]; int
0x18008da46  call    ?ClearBreak@CBreakArray@@QEAAXJJ@Z; CBreakArray::ClearBreak(long,long)
0x18008da4b  mov     rcx, [r13+0]; this
0x18008da4f  mov     rax, rbx
0x18008da52  test    rcx, rcx
0x18008da55  jz      short loc_18008DA6B
0x18008da57  mov     edx, [rdi]
0x18008da59  add     rax, rsi
0x18008da5c  mov     r8d, [r12+rax*8]
0x18008da60  sub     r8d, edx; int
0x18008da63  add     edx, r15d; int
0x18008da66  call    ?ClearBreak@CBreakArray@@QEAAXJJ@Z; CBreakArray::ClearBreak(long,long)
0x18008da6b  mov     eax, [rsp+300h+var_2AC]
0x18008da6f  add     eax, ebx
0x18008da71  mov     [rsp+300h+var_2AC], eax
0x18008da75  cmp     eax, [rsp+300h+var_2B0]
0x18008da79  jl      loc_18008D94E
0x18008da7f  mov     rcx, [rsp+300h+lpMem]; lpMem
0x18008da84  test    rcx, rcx
0x18008da87  jz      short loc_18008DA97
0x18008da89  lea     rax, [rbp+200h+var_250]
0x18008da8d  cmp     rax, rcx
0x18008da90  jz      short loc_18008DA97
0x18008da92  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18008da97  mov     rcx, [rbp+200h+var_50]
0x18008da9e  xor     rcx, rsp; StackCookie
0x18008daa1  call    __security_check_cookie
0x18008daa6  add     rsp, 2C8h
0x18008daad  pop     r15
0x18008daaf  pop     r14
0x18008dab1  pop     r13
0x18008dab3  pop     r12
0x18008dab5  pop     rdi
0x18008dab6  pop     rsi
0x18008dab7  pop     rbx
0x18008dab8  pop     rbp
0x18008dab9  retn
```
