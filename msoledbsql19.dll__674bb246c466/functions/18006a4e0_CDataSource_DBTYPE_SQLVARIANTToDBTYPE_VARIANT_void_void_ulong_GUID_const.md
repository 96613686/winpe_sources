# CDataSource::DBTYPE_SQLVARIANTToDBTYPE_VARIANT(void *,void *,ulong *,_GUID const *)

- ea: `0x18006a4e0`
- end: `0x18006ac21`
- name: `?DBTYPE_SQLVARIANTToDBTYPE_VARIANT@CDataSource@@QEAAJPEAX0PEAKPEBU_GUID@@@Z`
- size: `1857`
- prototype: `__int64 __fastcall(CDataSource *this, char *, _WORD *Src, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18005aa30`

## callees

- `0x180003030`
- `0x180003d80`
- `0x1800465a0`
- `0x18006a4e0`
- `0x18006cce0`
- `0x180074be0`
- `0x180140260`
- `0x1801a65e1`
- `0x1801a65f0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18006a75c`
- `KERNEL32!MultiByteToWideChar` at `0x18006a7ec`
- `KERNEL32!MultiByteToWideChar` at `0x18006a75c`
- `KERNEL32!MultiByteToWideChar` at `0x18006a7ec`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18006a8b7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18006a8b7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18006a8c3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18006a8c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006a6b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006a797`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006a6b1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006a797`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18006a856`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18006a856`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006a8cd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18006a8cd`
- `OLEAUT32!__imp_VarDecFromStr` at `0x18006a977`
- `OLEAUT32!__imp_VarDecFromStr` at `0x18006a977`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18006a809`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18006a809`

## pseudocode

```c
__int64 __fastcall CDataSource::DBTYPE_SQLVARIANTToDBTYPE_VARIANT(
        CDataSource *this,
        char *a2,
        _WORD *Src,
        unsigned int *a4)
{
  int v4; // eax
  HRESULT v9; // ebx
  double v10; // xmm2_8
  double v11; // xmm1_8
  BSTR v12; // rax
  int v13; // eax
  UINT v14; // ecx
  UINT v15; // eax
  int cchWideChar; // ebp
  WCHAR *lpWideCharStr; // rax
  SAFEARRAY *Vector; // rax
  size_t v19; // r8
  const void *v20; // rdx
  HRESULT v21; // eax
  __int64 v22; // rax
  char *v23; // rcx
  unsigned __int16 v24; // dx
  unsigned __int8 v25; // al
  __int64 v26; // rax
  __int64 v27; // rax
  char v29; // [rsp+58h] [rbp-280h]
  unsigned int v30; // [rsp+78h] [rbp-260h]
  UINT CodePage[2]; // [rsp+80h] [rbp-258h] BYREF
  unsigned int v32; // [rsp+88h] [rbp-250h] BYREF
  OLECHAR strIn[264]; // [rsp+90h] [rbp-248h] BYREF

  v4 = *(unsigned __int16 *)a2;
  v32 = 0;
  v9 = 0;
  switch ( v4 )
  {
    case 0:
      *Src = 0;
      goto LABEL_60;
    case 1:
      *Src = 1;
      goto LABEL_60;
    case 2:
      *Src = 2;
      Src[4] = *((_WORD *)a2 + 8);
      goto LABEL_60;
    case 3:
      *Src = 3;
      *((_DWORD *)Src + 2) = *((_DWORD *)a2 + 4);
      goto LABEL_60;
    case 4:
      *Src = 4;
      *((_DWORD *)Src + 2) = *((_DWORD *)a2 + 4);
      goto LABEL_60;
    case 5:
      *Src = 5;
      *((_QWORD *)Src + 1) = *((_QWORD *)a2 + 2);
      goto LABEL_60;
    case 6:
    case 200:
      *Src = 6;
      *((_QWORD *)Src + 1) = *((_QWORD *)a2 + 2);
      goto LABEL_60;
    case 11:
      *Src = 11;
      Src[4] = *((_WORD *)a2 + 8);
      goto LABEL_60;
    case 17:
      *Src = 17;
      *((_BYTE *)Src + 8) = a2[16];
      goto LABEL_60;
    case 20:
      *Src = 20;
      *((_QWORD *)Src + 1) = *((_QWORD *)a2 + 2);
      goto LABEL_60;
    case 131:
    case 205:
      *Src = 14;
      *(_QWORD *)CodePage = 0;
      if ( (int)_VarStrFromNum((const struct tagDB_NUMERIC *)(a2 + 16), strIn, (unsigned __int64 *)CodePage, 0x105u) < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return (unsigned int)-2147467259;
        return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7197705, 2147500037LL);
      }
      v9 = VarDecFromStr(strIn, 0x409u, 0, (DECIMAL *)Src);
      if ( v9 >= 0 )
        goto LABEL_60;
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7203849, 2147500037LL);
      return (unsigned int)-2147467259;
    case 133:
      v21 = CDataSource::DataConvert(
              this,
              0x85u,
              0xCu,
              4u,
              0,
              a2 + 16,
              Src,
              0x18u,
              0,
              (unsigned __int8 *)&v32,
              0xAu,
              0,
              0,
              0,
              0,
              0);
      goto LABEL_59;
    case 135:
    case 206:
      *Src = 7;
      *(_QWORD *)CodePage = 0;
      if ( !DateTimeFromTimestamp((struct tagDBTIMESTAMP *)a2 + 1, 8u, CodePage, 0) )
      {
        v10 = (double)(int)CodePage[0] + 2.0;
        v11 = (double)(int)CodePage[1] / 25920000.0;
        if ( v10 < 0.0 )
          *((double *)Src + 1) = v10 - v11;
        else
          *((double *)Src + 1) = v11 + v10;
        goto LABEL_60;
      }
      if ( (bidGblFlags & 2) == 0 )
        return (unsigned int)-2147467259;
      return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7067657, 2147500037LL);
    case 145:
      v22 = (unsigned __int8)a2[28];
      v23 = a2 + 16;
      v30 = 0;
      v24 = 145;
      v29 = v22;
      v25 = byte_1801C3F98[v22];
      goto LABEL_58;
    case 146:
      v27 = (unsigned __int8)a2[36];
      v23 = a2 + 16;
      v30 = 0;
      v24 = 146;
      v29 = v27;
      v25 = *((_BYTE *)&qword_1801C44F0[3] + v27);
      goto LABEL_58;
    case 201:
    case 202:
      *Src = 8;
      v12 = SysAllocStringLen(*((const OLECHAR **)a2 + 3), (unsigned __int64)*((__int16 *)a2 + 8) >> 1);
      *((_QWORD *)Src + 1) = v12;
      if ( v12 )
        goto LABEL_60;
      if ( (bidGblFlags & 2) == 0 )
        return (unsigned int)-2147024882;
      return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7094281, 2147942414LL);
    case 203:
    case 204:
      CodePage[0] = 0;
      v13 = CodePageFromTDSCollation(a2 + 32, CodePage);
      v9 = v13;
      if ( v13 >= 0 )
      {
        v14 = CodePage[0];
        *Src = 8;
        v15 = MultiByteToWideChar(v14, 0, *((LPCCH *)a2 + 3), *((__int16 *)a2 + 8), 0, 0);
        cchWideChar = v15;
        if ( v15 )
        {
          lpWideCharStr = SysAllocStringLen(0, v15);
          *((_QWORD *)Src + 1) = lpWideCharStr;
          if ( lpWideCharStr )
          {
            MultiByteToWideChar(CodePage[0], 0, *((LPCCH *)a2 + 3), *((__int16 *)a2 + 8), lpWideCharStr, cchWideChar);
            goto LABEL_60;
          }
          if ( (bidGblFlags & 2) == 0 )
            return (unsigned int)-2147024882;
          return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7134217, 2147942414LL);
        }
        else
        {
          if ( (bidGblFlags & 2) == 0 )
            return (unsigned int)-2147467259;
          return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7126025, 2147500037LL);
        }
      }
      else if ( (bidGblFlags & 2) != 0 )
      {
        _mm_lfence();
        bidTraceHR(*(_QWORD *)&::CodePage, 7111689, (unsigned int)v13);
      }
      return (unsigned int)v9;
    case 207:
    case 208:
      *Src = 8209;
      Vector = SafeArrayCreateVector(0x11u, 0, *((__int16 *)a2 + 8));
      *((_QWORD *)Src + 1) = Vector;
      if ( Vector )
      {
        *(_QWORD *)CodePage = 0;
        if ( SafeArrayAccessData(Vector, (void **)CodePage) < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7170057, 2147500037LL);
          return (unsigned int)-2147467259;
        }
        v19 = *((__int16 *)a2 + 8);
        v20 = (const void *)*((_QWORD *)a2 + 3);
        if ( *((_WORD *)a2 + 8) )
        {
          if ( *(_QWORD *)CodePage )
          {
            if ( v20 )
            {
              memcpy_0(*(void **)CodePage, v20, v19);
              goto LABEL_45;
            }
            memset_0(*(void **)CodePage, 0, v19);
          }
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
LABEL_45:
        v9 = SafeArrayUnaccessData(*((SAFEARRAY **)Src + 1));
        if ( v9 >= 0 )
        {
LABEL_60:
          if ( a4 )
            *a4 = v32;
          return (unsigned int)v9;
        }
        if ( (bidGblFlags & 2) != 0 )
          return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7181321, 2147500037LL);
        return (unsigned int)-2147467259;
      }
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(*(_QWORD *)&::CodePage, 7161865, 2147942414LL);
      else
        return (unsigned int)-2147024882;
    case 212:
      v26 = (unsigned __int8)a2[32];
      v23 = a2 + 16;
      v30 = 1024;
      v24 = 135;
      v29 = v26;
      v25 = *((_BYTE *)&qword_1801C4058 + v26);
LABEL_58:
      v21 = CDataSource::DataConvert(
              this,
              v24,
              0xCu,
              4u,
              0,
              v23,
              Src,
              0x18u,
              0,
              (unsigned __int8 *)&v32,
              v25,
              v29,
              0,
              0,
              0,
              v30);
LABEL_59:
      v9 = v21;
      goto LABEL_60;
    default:
      goto LABEL_60;
  }
}

```

## disassembly

```asm
0x18006a4e0  push    rbx
0x18006a4e2  push    rbp
0x18006a4e3  push    rsi
0x18006a4e4  push    rdi
0x18006a4e5  push    r14
0x18006a4e7  sub     rsp, 2B0h
0x18006a4ee  mov     rax, cs:__security_cookie
0x18006a4f5  xor     rax, rsp
0x18006a4f8  mov     [rsp+2D8h+var_38], rax
0x18006a500  movzx   eax, word ptr [rdx]
0x18006a503  xor     ebp, ebp
0x18006a505  mov     [rsp+2D8h+var_250], ebp
0x18006a50c  mov     r14, r9
0x18006a50f  mov     rdi, r8
0x18006a512  mov     rsi, rdx
0x18006a515  mov     r10, rcx
0x18006a518  mov     ebx, ebp
0x18006a51a  cmp     eax, 0D4h; switch 213 cases
0x18006a51f  ja      def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a525  lea     r9, cs:180000000h
0x18006a52c  movzx   eax, ds:(byte_18006AB4C - 180000000h)[r9+rax]
0x18006a535  mov     ecx, ds:(jpt_18006A540 - 180000000h)[r9+rax*4]
0x18006a53d  add     rcx, r9
0x18006a540  jmp     rcx; switch jump
0x18006a542  mov     word ptr [r8], 1; jumptable 000000018006A540 case 1
0x18006a548  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a54d  mov     [r8], bp; jumptable 000000018006A540 case 0
0x18006a551  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a556  mov     word ptr [r8], 11h; jumptable 000000018006A540 case 17
0x18006a55c  movzx   eax, byte ptr [rdx+10h]
0x18006a560  mov     [r8+8], al
0x18006a564  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a569  mov     word ptr [r8], 2; jumptable 000000018006A540 case 2
0x18006a56f  movzx   eax, word ptr [rdx+10h]
0x18006a573  mov     [r8+8], ax
0x18006a578  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a57d  mov     word ptr [r8], 3; jumptable 000000018006A540 case 3
0x18006a583  mov     eax, [rdx+10h]
0x18006a586  mov     [r8+8], eax
0x18006a58a  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a58f  mov     word ptr [r8], 14h; jumptable 000000018006A540 case 20
0x18006a595  mov     rax, [rdx+10h]
0x18006a599  mov     [r8+8], rax
0x18006a59d  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a5a2  mov     word ptr [r8], 4; jumptable 000000018006A540 case 4
0x18006a5a8  mov     eax, [rdx+10h]
0x18006a5ab  mov     [r8+8], eax
0x18006a5af  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a5b4  mov     word ptr [r8], 5; jumptable 000000018006A540 case 5
0x18006a5ba  mov     rax, [rdx+10h]
0x18006a5be  mov     [r8+8], rax
0x18006a5c2  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a5c7  mov     word ptr [r8], 6; jumptable 000000018006A540 cases 6,200
0x18006a5cd  mov     rax, [rdx+10h]
0x18006a5d1  mov     [r8+8], rax
0x18006a5d5  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a5da  mov     word ptr [r8], 0Bh; jumptable 000000018006A540 case 11
0x18006a5e0  movzx   eax, word ptr [rdx+10h]
0x18006a5e4  mov     [r8+8], ax
0x18006a5e9  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a5ee  mov     word ptr [r8], 7; jumptable 000000018006A540 cases 135,206
0x18006a5f4  lea     rcx, [rdx+10h]; struct tagDBTIMESTAMP *
0x18006a5f8  lea     r8, [rsp+2D8h+CodePage]; void *
0x18006a600  mov     qword ptr [rsp+2D8h+CodePage], rbp
0x18006a608  mov     edx, 8; unsigned __int64
0x18006a60d  xor     r9d, r9d; bool
0x18006a610  call    ?DateTimeFromTimestamp@@YAGPEAUtagDBTIMESTAMP@@_KPEAX_N@Z; DateTimeFromTimestamp(tagDBTIMESTAMP *,unsigned __int64,void *,bool)
0x18006a615  test    ax, ax
0x18006a618  jz      short loc_18006A64B
0x18006a61a  test    byte ptr cs:_bidGblFlags, 2
0x18006a621  jz      short loc_18006A641
0x18006a623  mov     rcx, cs:CodePage
0x18006a62a  mov     edx, 6BD809h
0x18006a62f  mov     r8d, 80004005h
0x18006a635  call    _bidTraceHR
0x18006a63a  mov     ebx, eax
0x18006a63c  jmp     loc_18006AAD9
0x18006a641  mov     ebx, 80004005h
0x18006a646  jmp     loc_18006AAD9
0x18006a64b  movd    xmm2, [rsp+2D8h+CodePage]
0x18006a654  xorps   xmm1, xmm1
0x18006a657  mov     eax, [rsp+2D8h+CodePage+4]
0x18006a65e  xorps   xmm0, xmm0
0x18006a661  cvtdq2pd xmm2, xmm2
0x18006a665  cvtsi2sd xmm1, rax
0x18006a66a  addsd   xmm2, cs:__real@4000000000000000
0x18006a672  divsd   xmm1, cs:__real@4178b82000000000
0x18006a67a  comisd  xmm2, xmm0
0x18006a67e  jb      short loc_18006A68E
0x18006a680  addsd   xmm1, xmm2
0x18006a684  movsd   qword ptr [rdi+8], xmm1
0x18006a689  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a68e  subsd   xmm2, xmm1
0x18006a692  movsd   qword ptr [rdi+8], xmm2
0x18006a697  movaps  xmm1, xmm2
0x18006a69a  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a69f  mov     word ptr [r8], 8; jumptable 000000018006A540 cases 201,202
0x18006a6a5  movsx   rdx, word ptr [rdx+10h]
0x18006a6aa  mov     rcx, [rsi+18h]; strIn
0x18006a6ae  shr     rdx, 1; ui
0x18006a6b1  call    cs:__imp_SysAllocStringLen
0x18006a6b7  mov     [rdi+8], rax
0x18006a6bb  test    rax, rax
0x18006a6be  jnz     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a6c4  test    byte ptr cs:_bidGblFlags, 2
0x18006a6cb  jz      short loc_18006A6EB
0x18006a6cd  mov     rcx, cs:CodePage
0x18006a6d4  mov     edx, 6C4009h
0x18006a6d9  mov     r8d, 8007000Eh
0x18006a6df  call    _bidTraceHR
0x18006a6e4  mov     ebx, eax
0x18006a6e6  jmp     loc_18006AAD9
0x18006a6eb  mov     ebx, 8007000Eh
0x18006a6f0  jmp     loc_18006AAD9
0x18006a6f5  lea     rcx, [rdx+20h]; jumptable 000000018006A540 cases 203,204
0x18006a6f9  mov     [rsp+2D8h+CodePage], ebp
0x18006a700  lea     rdx, [rsp+2D8h+CodePage]
0x18006a708  call    CodePageFromTDSCollation
0x18006a70d  mov     ebx, eax
0x18006a70f  test    eax, eax
0x18006a711  jns     short loc_18006A73C
0x18006a713  test    byte ptr cs:_bidGblFlags, 2
0x18006a71a  jz      loc_18006AAD9
0x18006a720  lfence
0x18006a723  mov     rcx, cs:CodePage
0x18006a72a  mov     r8d, eax
0x18006a72d  mov     edx, 6C8409h
0x18006a732  call    _bidTraceHR
0x18006a737  jmp     loc_18006AAD9
0x18006a73c  mov     ecx, [rsp+2D8h+CodePage]; CodePage
0x18006a743  xor     edx, edx; dwFlags
0x18006a745  mov     word ptr [rdi], 8
0x18006a74a  movsx   r9d, word ptr [rsi+10h]; cbMultiByte
0x18006a74f  mov     r8, [rsi+18h]; lpMultiByteStr
0x18006a753  mov     [rsp+2D8h+cchWideChar], ebp; cchWideChar
0x18006a757  mov     [rsp+2D8h+lpWideCharStr], rbp; lpWideCharStr
0x18006a75c  call    cs:__imp_MultiByteToWideChar
0x18006a762  mov     ebp, eax
0x18006a764  test    eax, eax
0x18006a766  jnz     short loc_18006A793
0x18006a768  test    byte ptr cs:_bidGblFlags, 2
0x18006a76f  jz      loc_18006A641
0x18006a775  mov     rcx, cs:CodePage
0x18006a77c  mov     edx, 6CBC09h
0x18006a781  mov     r8d, 80004005h
0x18006a787  call    _bidTraceHR
0x18006a78c  mov     ebx, eax
0x18006a78e  jmp     loc_18006AAD9
0x18006a793  mov     edx, ebp; ui
0x18006a795  xor     ecx, ecx; strIn
0x18006a797  call    cs:__imp_SysAllocStringLen
0x18006a79d  mov     [rdi+8], rax
0x18006a7a1  test    rax, rax
0x18006a7a4  jnz     short loc_18006A7D1
0x18006a7a6  test    byte ptr cs:_bidGblFlags, 2
0x18006a7ad  jz      loc_18006A6EB
0x18006a7b3  mov     rcx, cs:CodePage
0x18006a7ba  mov     edx, 6CDC09h
0x18006a7bf  mov     r8d, 8007000Eh
0x18006a7c5  call    _bidTraceHR
0x18006a7ca  mov     ebx, eax
0x18006a7cc  jmp     loc_18006AAD9
0x18006a7d1  movsx   r9d, word ptr [rsi+10h]; cbMultiByte
0x18006a7d6  xor     edx, edx; dwFlags
0x18006a7d8  mov     r8, [rsi+18h]; lpMultiByteStr
0x18006a7dc  mov     ecx, [rsp+2D8h+CodePage]; CodePage
0x18006a7e3  mov     [rsp+2D8h+cchWideChar], ebp; cchWideChar
0x18006a7e7  mov     [rsp+2D8h+lpWideCharStr], rax; lpWideCharStr
0x18006a7ec  call    cs:__imp_MultiByteToWideChar
0x18006a7f2  jmp     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a7f7  mov     word ptr [r8], 2011h; jumptable 000000018006A540 cases 207,208
0x18006a7fd  mov     ecx, 11h; vt
0x18006a802  movsx   r8d, word ptr [rdx+10h]; cElements
0x18006a807  xor     edx, edx; lLbound
0x18006a809  call    cs:__imp_SafeArrayCreateVector
0x18006a80f  mov     [rdi+8], rax
0x18006a813  test    rax, rax
0x18006a816  jnz     short loc_18006A843
0x18006a818  test    byte ptr cs:_bidGblFlags, 2
0x18006a81f  jz      loc_18006A6EB
0x18006a825  mov     rcx, cs:CodePage
0x18006a82c  mov     edx, 6D4809h
0x18006a831  mov     r8d, 8007000Eh
0x18006a837  call    _bidTraceHR
0x18006a83c  mov     ebx, eax
0x18006a83e  jmp     loc_18006AAD9
0x18006a843  lea     rdx, [rsp+2D8h+CodePage]; ppvData
0x18006a84b  mov     qword ptr [rsp+2D8h+CodePage], rbp
0x18006a853  mov     rcx, rax; psa
0x18006a856  call    cs:__imp_SafeArrayAccessData
0x18006a85c  test    eax, eax
0x18006a85e  jns     short loc_18006A88B
0x18006a860  test    byte ptr cs:_bidGblFlags, 2
0x18006a867  jz      loc_18006A641
0x18006a86d  mov     rcx, cs:CodePage
0x18006a874  mov     edx, 6D6809h
0x18006a879  mov     r8d, 80004005h
0x18006a87f  call    _bidTraceHR
0x18006a884  mov     ebx, eax
0x18006a886  jmp     loc_18006AAD9
0x18006a88b  movsx   r8, word ptr [rsi+10h]; Size
0x18006a890  mov     rdx, [rsi+18h]; Src
0x18006a894  test    r8, r8
0x18006a897  jz      short loc_18006A8C9
0x18006a899  mov     rcx, qword ptr [rsp+2D8h+CodePage]; void *
0x18006a8a1  test    rcx, rcx
0x18006a8a4  jz      short loc_18006A8B7
0x18006a8a6  test    rdx, rdx
0x18006a8a9  jz      short loc_18006A8B2
0x18006a8ab  call    memcpy_0
0x18006a8b0  jmp     short loc_18006A8C9
0x18006a8b2  call    memset_0
0x18006a8b7  call    cs:__imp__errno
0x18006a8bd  mov     dword ptr [rax], 16h
0x18006a8c3  call    cs:__imp__invalid_parameter_noinfo
0x18006a8c9  mov     rcx, [rdi+8]; psa
0x18006a8cd  call    cs:__imp_SafeArrayUnaccessData
0x18006a8d3  mov     ebx, eax
0x18006a8d5  test    eax, eax
0x18006a8d7  jns     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a8dd  test    byte ptr cs:_bidGblFlags, 2
0x18006a8e4  jz      loc_18006A641
0x18006a8ea  mov     rcx, cs:CodePage
0x18006a8f1  mov     edx, 6D9409h
0x18006a8f6  mov     r8d, 80004005h
0x18006a8fc  call    _bidTraceHR
0x18006a901  mov     ebx, eax
0x18006a903  jmp     loc_18006AAD9
0x18006a908  mov     word ptr [r8], 0Eh; jumptable 000000018006A540 cases 131,205
0x18006a90e  lea     rcx, [rdx+10h]; struct tagDB_NUMERIC *
0x18006a912  lea     r8, [rsp+2D8h+CodePage]; unsigned __int64 *
0x18006a91a  mov     qword ptr [rsp+2D8h+CodePage], rbp
0x18006a922  lea     rdx, [rsp+2D8h+strIn]; wchar_t *
0x18006a92a  mov     r9d, 105h; unsigned __int64
0x18006a930  call    ?_VarStrFromNum@@YAJPEBUtagDB_NUMERIC@@PEA_WPEA_K_K@Z; _VarStrFromNum(tagDB_NUMERIC const *,wchar_t *,unsigned __int64 *,unsigned __int64)
0x18006a935  test    eax, eax
0x18006a937  jns     short loc_18006A964
0x18006a939  test    byte ptr cs:_bidGblFlags, 2
0x18006a940  jz      loc_18006A641
0x18006a946  mov     rcx, cs:CodePage
0x18006a94d  mov     edx, 6DD409h
0x18006a952  mov     r8d, 80004005h
0x18006a958  call    _bidTraceHR
0x18006a95d  mov     ebx, eax
0x18006a95f  jmp     loc_18006AAD9
0x18006a964  mov     r9, rdi; pdecOut
0x18006a967  lea     rcx, [rsp+2D8h+strIn]; strIn
0x18006a96f  xor     r8d, r8d; dwFlags
0x18006a972  mov     edx, 409h; lcid
0x18006a977  call    cs:__imp_VarDecFromStr
0x18006a97d  mov     ebx, eax
0x18006a97f  test    eax, eax
0x18006a981  jns     def_18006A540; jumptable 000000018006A540 default case, cases 7-10,12-16,18,19,21-130,132,134,136-144,147-199,209-211
0x18006a987  test    byte ptr cs:_bidGblFlags, 2
0x18006a98e  jz      loc_18006A641
0x18006a994  mov     rcx, cs:CodePage
0x18006a99b  mov     edx, 6DEC09h
0x18006a9a0  mov     r8d, 80004005h
0x18006a9a6  call    _bidTraceHR
0x18006a9ab  mov     ebx, eax
0x18006a9ad  jmp     loc_18006AAD9
0x18006a9b2  mov     [rsp+2D8h+var_260], ebp; jumptable 000000018006A540 case 133
0x18006a9b6  lea     rax, [rdx+10h]
0x18006a9ba  mov     [rsp+2D8h+var_268], ebp
0x18006a9be  lea     rcx, [rsp+2D8h+var_250]
0x18006a9c6  mov     [rsp+2D8h+var_270], ebp
0x18006a9ca  mov     edx, 85h
0x18006a9cf  mov     [rsp+2D8h+var_278], rbp
0x18006a9d4  mov     [rsp+2D8h+var_280], bl
0x18006a9d8  mov     [rsp+2D8h+var_288], 0Ah
0x18006a9dd  mov     [rsp+2D8h+var_290], rcx
0x18006a9e2  mov     [rsp+2D8h+var_298], ebp
0x18006a9e6  mov     [rsp+2D8h+var_2A0], 18h
0x18006a9ef  mov     [rsp+2D8h+Src], rdi
0x18006a9f4  mov     qword ptr [rsp+2D8h+cchWideChar], rax
0x18006a9f9  jmp     loc_18006AAAF
0x18006a9fe  movzx   eax, byte ptr [rdx+1Ch]; jumptable 000000018006A540 case 145
0x18006aa02  lea     rcx, [rdx+10h]
0x18006aa06  mov     [rsp+2D8h+var_260], ebp
0x18006aa0a  mov     edx, 91h
0x18006aa0f  mov     [rsp+2D8h+var_268], ebp
0x18006aa13  mov     [rsp+2D8h+var_270], ebp
0x18006aa17  mov     [rsp+2D8h+var_278], rbp
0x18006aa1c  mov     [rsp+2D8h+var_280], al
0x18006aa20  movzx   eax, byte ptr [rax+r9+1C3F98h]
0x18006aa29  jmp     short loc_18006AA87
0x18006aa2b  movzx   eax, byte ptr [rdx+20h]; jumptable 000000018006A540 case 212
0x18006aa2f  lea     rcx, [rdx+10h]
0x18006aa33  mov     [rsp+2D8h+var_260], 400h
0x18006aa3b  mov     edx, 87h
0x18006aa40  mov     [rsp+2D8h+var_268], ebp
0x18006aa44  mov     [rsp+2D8h+var_270], ebp
0x18006aa48  mov     [rsp+2D8h+var_278], rbp
0x18006aa4d  mov     [rsp+2D8h+var_280], al
0x18006aa51  movzx   eax, byte ptr [rax+r9+1C4058h]
0x18006aa5a  jmp     short loc_18006AA87
0x18006aa5c  movzx   eax, byte ptr [rdx+24h]; jumptable 000000018006A540 case 146
0x18006aa60  lea     rcx, [rdx+10h]
0x18006aa64  mov     [rsp+2D8h+var_260], ebp; unsigned int
0x18006aa68  mov     edx, 92h; unsigned __int16
  ... truncated ...
```
