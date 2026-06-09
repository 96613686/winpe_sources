# CScrubDatabase::OpenJetDatabase(unsigned __int64,ushort const *)

- ea: `0x18002f040`
- end: `0x18002f3b2`
- name: `?OpenJetDatabase@CScrubDatabase@@QEAAJ_KPEBG@Z`
- size: `882`
- prototype: `__int64 __fastcall(CScrubDatabase *this, __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18001e49c`
- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006584`
- `0x180006688`
- `0x18002e724`
- `0x18002e788`
- `0x18002f040`
- `0x18002f6a8`

## import_xrefs

- `ESENT!JetAttachDatabase2W` at `0x18002f144`
- `ESENT!JetAttachDatabase2W` at `0x18002f144`
- `ESENT!JetCreateDatabase2W` at `0x18002f169`
- `ESENT!JetCreateDatabase2W` at `0x18002f169`
- `ESENT!JetOpenDatabaseW` at `0x18002f23d`
- `ESENT!JetOpenDatabaseW` at `0x18002f23d`
- `ESENT!JetSetCurrentIndexW` at `0x18002f312`
- `ESENT!JetSetCurrentIndexW` at `0x18002f312`

## string_xrefs

- `0x18002f078`: `CScrubDatabase::OpenJetDatabase`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::OpenJetDatabase(CScrubDatabase *this, __int64 a2, const unsigned __int16 *a3)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v8; // r10
  USHORT v9; // dx
  USHORT v10; // ax
  JET_SESID v11; // rcx
  JET_ERR v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  bool v15; // di
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // eax
  unsigned int v19; // eax
  int v20; // edi
  int v21; // eax
  const char *v23; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-28h]
  USHORT v25; // [rsp+40h] [rbp-20h]
  USHORT v26; // [rsp+42h] [rbp-1Eh]
  int v27; // [rsp+44h] [rbp-1Ch]
  char *v28; // [rsp+48h] [rbp-18h]
  _BYTE v29[16]; // [rsp+50h] [rbp-10h] BYREF
  JET_DBID pdbid; // [rsp+90h] [rbp+30h] BYREF
  _BYTE *v31; // [rsp+98h] [rbp+38h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v23 = "CScrubDatabase::OpenJetDatabase";
  v8 = ThreadLocalStoragePointer[tls_index];
  v9 = ++*(_WORD *)(v8 + 8);
  *(_QWORD *)(v8 + 16) = "CScrubDatabase::OpenJetDatabase";
  v10 = Length;
  if ( v9 < Length )
  {
    v10 = v9;
    Length = v9;
  }
  v25 = v10;
  v27 = 0;
  v28 = off_180047060;
  v26 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::OpenJetDatabase");
  }
  *((_QWORD *)this + 1) = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, a3);
  }
  v11 = *((_QWORD *)this + 1);
  pdbid = 0;
  v12 = JetAttachDatabase2W(v11, a3, 0, 0x10u);
  if ( v12 == -1811 )
  {
    v12 = JetCreateDatabase2W(*((_QWORD *)this + 1), a3, 0, &pdbid, 0);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v14 = 11;
LABEL_27:
      WPP_SF_d(v13[2], v14, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, (unsigned int)v12);
LABEL_28:
      if ( v12 == -1011 )
      {
        v16 = -2147024882;
      }
      else
      {
        v17 = -v12;
        if ( v12 > 0 )
          LOWORD(v17) = v12;
        v16 = v12 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      v24 = v16;
      goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, a3);
    }
    v15 = 1;
  }
  else
  {
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v14 = 13;
      goto LABEL_27;
    }
    v12 = JetOpenDatabaseW(*((_QWORD *)this + 1), a3, 0, &pdbid, 0);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_28;
      }
      v14 = 14;
      goto LABEL_27;
    }
    v15 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, a3);
    }
  }
  lambda_ae0aec0d42d22013f87e184304d449f2_::_lambda_ae0aec0d42d22013f87e184304d449f2_(v29, this, &pdbid);
  v31 = v29;
  *((_DWORD *)this + 4) = pdbid;
  v18 = CScrubDatabase::PrepareParityTable(this, v15);
  v24 = v18;
  v16 = v18;
  if ( v18 >= 0 )
  {
    v19 = JetSetCurrentIndexW(*((_QWORD *)this + 1), *((_QWORD *)this + 3), ParityTable::OffsetIndexName);
    v20 = v19;
    if ( !v19 )
    {
      v31 = 0;
      v24 = 0;
      CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___::_CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___(&v31);
      v16 = 0;
      goto LABEL_61;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v19);
    }
    if ( v20 == -1011 )
    {
      v16 = -2147024882;
    }
    else
    {
      v21 = -v20;
      if ( v20 > 0 )
        LOWORD(v21) = v20;
      v16 = v20 & 0x8E5E0000 | (unsigned __int16)v21 | 0xE5E0000;
    }
    v24 = v16;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids,
      (unsigned int)v18);
  }
  CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___::_CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___(&v31);
LABEL_61:
  CHResultImp::~CHResultImp((CHResultImp *)&v23);
  return v16;
}

```

## disassembly

```asm
0x18002f040  mov     [rsp-28h+arg_10], rbx
0x18002f045  push    rbp
0x18002f046  push    rsi
0x18002f047  push    rdi
0x18002f048  push    r12
0x18002f04a  push    r13
0x18002f04c  mov     rbp, rsp
0x18002f04f  sub     rsp, 60h
0x18002f053  mov     rax, gs:58h
0x18002f05c  mov     rdi, rdx
0x18002f05f  mov     r9d, cs:_tls_index
0x18002f066  mov     rsi, rcx
0x18002f069  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002f070  mov     rbx, r8
0x18002f073  mov     edx, 8
0x18002f078  lea     r8, aCscrubdatabase_8; "CScrubDatabase::OpenJetDatabase"
0x18002f07f  mov     [rbp+var_30], r8
0x18002f083  mov     r10, [rax+r9*8]
0x18002f087  mov     eax, 10h
0x18002f08c  inc     word ptr [rdx+r10]
0x18002f091  movzx   edx, word ptr [rdx+r10]
0x18002f096  mov     [rax+r10], r8
0x18002f09a  cmp     dx, cx
0x18002f09d  movzx   eax, cx
0x18002f0a0  cmovb   ax, dx
0x18002f0a4  cmovb   cx, dx
0x18002f0a8  mov     [rbp+var_20], ax
0x18002f0ac  xor     eax, eax
0x18002f0ae  mov     [rbp+var_1C], eax
0x18002f0b1  mov     rax, cs:off_180047060; "                                       "...
0x18002f0b8  mov     [rbp+var_18], rax
0x18002f0bc  mov     [rbp+var_1E], cx
0x18002f0c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0c7  lea     r12, WPP_GLOBAL_Control
0x18002f0ce  cmp     rcx, r12
0x18002f0d1  jz      short loc_18002F0F6
0x18002f0d3  test    byte ptr [rcx+1Ch], 1
0x18002f0d7  jz      short loc_18002F0F6
0x18002f0d9  cmp     byte ptr [rcx+19h], 5
0x18002f0dd  jb      short loc_18002F0F6
0x18002f0df  mov     rcx, [rcx+10h]; LoggerHandle
0x18002f0e3  lea     r9, [rbp+var_20]
0x18002f0e7  mov     edx, 0Dh
0x18002f0ec  mov     qword ptr [rsp+60h+grbit], r8; __int64
0x18002f0f1  call    WPP_SF_aZs
0x18002f0f6  mov     [rsi+8], rdi
0x18002f0fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f101  lea     r13, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002f108  cmp     rcx, r12
0x18002f10b  jz      short loc_18002F12D
0x18002f10d  test    byte ptr [rcx+1Ch], 1
0x18002f111  jz      short loc_18002F12D
0x18002f113  cmp     byte ptr [rcx+19h], 4
0x18002f117  jb      short loc_18002F12D
0x18002f119  mov     rcx, [rcx+10h]
0x18002f11d  mov     edx, 0Ah
0x18002f122  mov     r9, rbx
0x18002f125  mov     r8, r13
0x18002f128  call    WPP_SF_S
0x18002f12d  mov     rcx, [rsi+8]; sesid
0x18002f131  mov     r9d, 10h; grbit
0x18002f137  xor     r8d, r8d; cpgDatabaseSizeMax
0x18002f13a  mov     [rbp+pdbid], 0
0x18002f141  mov     rdx, rbx; szFilename
0x18002f144  call    cs:__imp_JetAttachDatabase2W
0x18002f14a  mov     edi, eax
0x18002f14c  cmp     eax, 0FFFFF8EDh
0x18002f151  jnz     short loc_18002F1C8
0x18002f153  mov     rcx, [rsi+8]; sesid
0x18002f157  lea     r9, [rbp+pdbid]; pdbid
0x18002f15b  xor     r8d, r8d; cpgDatabaseSizeMax
0x18002f15e  mov     [rsp+60h+grbit], 0; grbit
0x18002f166  mov     rdx, rbx; szFilename
0x18002f169  call    cs:__imp_JetCreateDatabase2W
0x18002f16f  mov     edi, eax
0x18002f171  test    eax, eax
0x18002f173  jz      short loc_18002F194
0x18002f175  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f17c  cmp     rcx, r12
0x18002f17f  jz      short loc_18002F1F8
0x18002f181  test    byte ptr [rcx+1Ch], 1
0x18002f185  jz      short loc_18002F1F8
0x18002f187  cmp     byte ptr [rcx+19h], 2
0x18002f18b  jb      short loc_18002F1F8
0x18002f18d  mov     edx, 0Bh
0x18002f192  jmp     short loc_18002F1E9
0x18002f194  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f19b  cmp     rcx, r12
0x18002f19e  jz      short loc_18002F1C0
0x18002f1a0  test    byte ptr [rcx+1Ch], 1
0x18002f1a4  jz      short loc_18002F1C0
0x18002f1a6  cmp     byte ptr [rcx+19h], 4
0x18002f1aa  jb      short loc_18002F1C0
0x18002f1ac  mov     rcx, [rcx+10h]
0x18002f1b0  mov     edx, 0Ch
0x18002f1b5  mov     r9, rbx
0x18002f1b8  mov     r8, r13
0x18002f1bb  call    WPP_SF_S
0x18002f1c0  mov     dil, 1
0x18002f1c3  jmp     loc_18002F297
0x18002f1c8  test    edi, edi
0x18002f1ca  jz      short loc_18002F227
0x18002f1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1d3  cmp     rcx, r12
0x18002f1d6  jz      short loc_18002F1F8
0x18002f1d8  test    byte ptr [rcx+1Ch], 1
0x18002f1dc  jz      short loc_18002F1F8
0x18002f1de  cmp     byte ptr [rcx+19h], 2
0x18002f1e2  jb      short loc_18002F1F8
0x18002f1e4  mov     edx, 0Dh
0x18002f1e9  mov     rcx, [rcx+10h]
0x18002f1ed  mov     r9d, edi
0x18002f1f0  mov     r8, r13
0x18002f1f3  call    WPP_SF_d
0x18002f1f8  cmp     edi, 0FFFFFC0Dh
0x18002f1fe  jnz     short loc_18002F207
0x18002f200  mov     ebx, 8007000Eh
0x18002f205  jmp     short loc_18002F21F
0x18002f207  mov     eax, edi
0x18002f209  neg     eax
0x18002f20b  cmovs   eax, edi
0x18002f20e  and     edi, 8E5E0000h
0x18002f214  movzx   ebx, ax
0x18002f217  or      ebx, edi
0x18002f219  or      ebx, 0E5E0000h
0x18002f21f  mov     [rbp+var_28], ebx
0x18002f222  jmp     loc_18002F393
0x18002f227  mov     rcx, [rsi+8]; sesid
0x18002f22b  lea     r9, [rbp+pdbid]; pdbid
0x18002f22f  xor     r8d, r8d; szConnect
0x18002f232  mov     [rsp+60h+grbit], 0; grbit
0x18002f23a  mov     rdx, rbx; szFilename
0x18002f23d  call    cs:__imp_JetOpenDatabaseW
0x18002f243  mov     edi, eax
0x18002f245  test    eax, eax
0x18002f247  jz      short loc_18002F268
0x18002f249  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f250  cmp     rcx, r12
0x18002f253  jz      short loc_18002F1F8
0x18002f255  test    byte ptr [rcx+1Ch], 1
0x18002f259  jz      short loc_18002F1F8
0x18002f25b  cmp     byte ptr [rcx+19h], 2
0x18002f25f  jb      short loc_18002F1F8
0x18002f261  mov     edx, 0Eh
0x18002f266  jmp     short loc_18002F1E9
0x18002f268  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f26f  xor     dil, dil
0x18002f272  cmp     rcx, r12
0x18002f275  jz      short loc_18002F297
0x18002f277  test    byte ptr [rcx+1Ch], 1
0x18002f27b  jz      short loc_18002F297
0x18002f27d  cmp     byte ptr [rcx+19h], 4
0x18002f281  jb      short loc_18002F297
0x18002f283  mov     rcx, [rcx+10h]
0x18002f287  mov     edx, 0Fh
0x18002f28c  mov     r9, rbx
0x18002f28f  mov     r8, r13
0x18002f292  call    WPP_SF_S
0x18002f297  lea     r8, [rbp+pdbid]
0x18002f29b  mov     rdx, rsi
0x18002f29e  lea     rcx, [rbp+var_10]
0x18002f2a2  call    _lambda_ae0aec0d42d22013f87e184304d449f2____lambda_ae0aec0d42d22013f87e184304d449f2_
0x18002f2a7  mov     eax, [rbp+pdbid]
0x18002f2aa  lea     rcx, [rbp+var_10]
0x18002f2ae  mov     [rbp+arg_8], rcx
0x18002f2b2  mov     dl, dil; bool
0x18002f2b5  mov     rcx, rsi; this
0x18002f2b8  mov     [rsi+10h], eax
0x18002f2bb  call    ?PrepareParityTable@CScrubDatabase@@AEAAJ_N@Z; CScrubDatabase::PrepareParityTable(bool)
0x18002f2c0  mov     [rbp+var_28], eax
0x18002f2c3  mov     ebx, eax
0x18002f2c5  test    eax, eax
0x18002f2c7  jns     short loc_18002F303
0x18002f2c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f2d0  cmp     rcx, r12
0x18002f2d3  jz      short loc_18002F2F5
0x18002f2d5  test    byte ptr [rcx+1Ch], 1
0x18002f2d9  jz      short loc_18002F2F5
0x18002f2db  cmp     byte ptr [rcx+19h], 2
0x18002f2df  jb      short loc_18002F2F5
0x18002f2e1  mov     rcx, [rcx+10h]
0x18002f2e5  mov     edx, 11h
0x18002f2ea  mov     r9d, eax
0x18002f2ed  mov     r8, r13
0x18002f2f0  call    WPP_SF_d
0x18002f2f5  lea     rcx, [rbp+arg_8]
0x18002f2f9  call    CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2______CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___
0x18002f2fe  jmp     loc_18002F393
0x18002f303  mov     rdx, [rsi+18h]; tableid
0x18002f307  lea     r8, ?OffsetIndexName@ParityTable@@3PAGA; "ParityOffsetIndex"
0x18002f30e  mov     rcx, [rsi+8]; sesid
0x18002f312  call    cs:__imp_JetSetCurrentIndexW
0x18002f318  mov     edi, eax
0x18002f31a  test    eax, eax
0x18002f31c  jz      short loc_18002F379
0x18002f31e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f325  cmp     rcx, r12
0x18002f328  jz      short loc_18002F34A
0x18002f32a  test    byte ptr [rcx+1Ch], 1
0x18002f32e  jz      short loc_18002F34A
0x18002f330  cmp     byte ptr [rcx+19h], 2
0x18002f334  jb      short loc_18002F34A
0x18002f336  mov     rcx, [rcx+10h]
0x18002f33a  mov     edx, 12h
0x18002f33f  mov     r9d, eax
0x18002f342  mov     r8, r13
0x18002f345  call    WPP_SF_d
0x18002f34a  cmp     edi, 0FFFFFC0Dh
0x18002f350  jnz     short loc_18002F359
0x18002f352  mov     ebx, 8007000Eh
0x18002f357  jmp     short loc_18002F371
0x18002f359  mov     eax, edi
0x18002f35b  neg     eax
0x18002f35d  cmovs   eax, edi
0x18002f360  and     edi, 8E5E0000h
0x18002f366  movzx   ebx, ax
0x18002f369  or      ebx, edi
0x18002f36b  or      ebx, 0E5E0000h
0x18002f371  mov     [rbp+var_28], ebx
0x18002f374  jmp     loc_18002F2F5
0x18002f379  lea     rcx, [rbp+arg_8]
0x18002f37d  mov     [rbp+arg_8], 0
0x18002f385  mov     [rbp+var_28], 0
0x18002f38c  call    CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2______CAutoTearDown__lambda_ae0aec0d42d22013f87e184304d449f2___
0x18002f391  xor     ebx, ebx
0x18002f393  lea     rcx, [rbp+var_30]; this
0x18002f397  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002f39c  mov     eax, ebx
0x18002f39e  mov     rbx, [rsp+60h+arg_10]
0x18002f3a6  add     rsp, 60h
0x18002f3aa  pop     r13
0x18002f3ac  pop     r12
0x18002f3ae  pop     rdi
0x18002f3af  pop     rsi
0x18002f3b0  pop     rbp
0x18002f3b1  retn
```
