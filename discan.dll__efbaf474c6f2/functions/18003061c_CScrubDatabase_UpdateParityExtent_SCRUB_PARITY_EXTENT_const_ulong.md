# CScrubDatabase::UpdateParityExtent(_SCRUB_PARITY_EXTENT const *,ulong)

- ea: `0x18003061c`
- end: `0x180030839`
- name: `?UpdateParityExtent@CScrubDatabase@@QEAAJPEBU_SCRUB_PARITY_EXTENT@@K@Z`
- size: `541`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this, const struct _SCRUB_PARITY_EXTENT *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022450`

## callees

- `0x180002e20`
- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002e738`
- `0x18002fd34`
- `0x18003061c`

## import_xrefs

- `ESENT!JetBeginTransaction` at `0x1800306e0`
- `ESENT!JetBeginTransaction` at `0x1800306e0`
- `ESENT!JetCommitTransaction` at `0x18003078b`
- `ESENT!JetCommitTransaction` at `0x18003078b`

## string_xrefs

- `0x18003065e`: `CScrubDatabase::UpdateParityExtent`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::UpdateParityExtent(
        CScrubDatabase *this,
        const struct _SCRUB_PARITY_EXTENT *a2,
        unsigned int a3)
{
  USHORT Length; // cx
  __int64 v7; // r10
  USHORT v8; // dx
  USHORT v9; // ax
  unsigned int v10; // eax
  int v11; // edi
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  int v17; // eax
  const char *v19; // [rsp+30h] [rbp-20h] BYREF
  int updated; // [rsp+38h] [rbp-18h]
  USHORT v21; // [rsp+40h] [rbp-10h]
  USHORT v22; // [rsp+42h] [rbp-Eh]
  int v23; // [rsp+44h] [rbp-Ch]
  char *v24; // [rsp+48h] [rbp-8h]
  __int64 *v25; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+58h] BYREF

  Length = GlobalIndentString.Length;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v19 = "CScrubDatabase::UpdateParityExtent";
  v8 = ++*(_WORD *)(v7 + 8);
  *(_QWORD *)(v7 + 16) = "CScrubDatabase::UpdateParityExtent";
  v9 = Length;
  if ( v8 < Length )
  {
    v9 = v8;
    Length = v8;
  }
  v21 = v9;
  v23 = 0;
  v24 = off_180047060;
  v22 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::UpdateParityExtent");
  }
  v10 = JetBeginTransaction(*((_QWORD *)this + 1));
  v11 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v10);
    }
    if ( v11 == -1011 )
    {
      v12 = -2147024882;
    }
    else
    {
      v13 = -v11;
      if ( v11 > 0 )
        LOWORD(v13) = v11;
      v12 = v11 & 0x8E5E0000 | (unsigned __int16)v13 | 0xE5E0000;
    }
    updated = v12;
  }
  else
  {
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v26, (__int64)this);
    v14 = 0;
    v25 = &v26;
    while ( v14 < a3 )
    {
      updated = CScrubDatabase::UpdateParityExtent(this, (const struct _SCRUB_PARITY_EXTENT *)((char *)a2 + 16 * v14));
      v12 = updated;
      if ( updated < 0 )
        goto LABEL_33;
      ++v14;
    }
    v15 = JetCommitTransaction(*((_QWORD *)this + 1), 0);
    v16 = v15;
    if ( v15 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v15);
      }
      if ( v16 == -1011 )
      {
        v12 = -2147024882;
      }
      else
      {
        v17 = -v16;
        if ( v16 > 0 )
          LOWORD(v17) = v16;
        v12 = v16 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
      }
      updated = v12;
LABEL_33:
      CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___::_CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___(&v25);
      goto LABEL_35;
    }
    v25 = 0;
    updated = 0;
    CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___::_CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___(&v25);
    v12 = 0;
  }
LABEL_35:
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v12;
}

```

## disassembly

```asm
0x18003061c  mov     [rsp-38h+arg_8], rbx
0x180030621  push    rbp
0x180030622  push    rsi
0x180030623  push    rdi
0x180030624  push    r12
0x180030626  push    r13
0x180030628  push    r14
0x18003062a  push    r15
0x18003062c  mov     rbp, rsp
0x18003062f  sub     rsp, 50h
0x180030633  mov     rax, gs:58h
0x18003063c  mov     r15, rdx
0x18003063f  mov     r9d, cs:_tls_index
0x180030646  mov     rsi, rcx
0x180030649  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180030650  mov     r12d, 1
0x180030656  mov     edx, 8
0x18003065b  mov     r14d, r8d
0x18003065e  lea     r8, aCscrubdatabase_3; "CScrubDatabase::UpdateParityExtent"
0x180030665  mov     r10, [rax+r9*8]
0x180030669  mov     eax, 10h
0x18003066e  mov     [rbp+var_20], r8
0x180030672  add     [rdx+r10], r12w
0x180030677  movzx   edx, word ptr [rdx+r10]
0x18003067c  mov     [rax+r10], r8
0x180030680  cmp     dx, cx
0x180030683  movzx   eax, cx
0x180030686  cmovb   ax, dx
0x18003068a  cmovb   cx, dx
0x18003068e  mov     [rbp+var_10], ax
0x180030692  xor     eax, eax
0x180030694  mov     [rbp+var_C], eax
0x180030697  mov     rax, cs:off_180047060; "                                       "...
0x18003069e  mov     [rbp+var_8], rax
0x1800306a2  mov     [rbp+var_E], cx
0x1800306a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306ad  lea     r13, WPP_GLOBAL_Control
0x1800306b4  cmp     rcx, r13
0x1800306b7  jz      short loc_1800306DC
0x1800306b9  test    [rcx+1Ch], r12b
0x1800306bd  jz      short loc_1800306DC
0x1800306bf  cmp     byte ptr [rcx+19h], 5
0x1800306c3  jb      short loc_1800306DC
0x1800306c5  mov     rcx, [rcx+10h]; LoggerHandle
0x1800306c9  lea     edx, [r12+0Ch]
0x1800306ce  lea     r9, [rbp+var_10]
0x1800306d2  mov     [rsp+50h+var_30], r8; __int64
0x1800306d7  call    WPP_SF_aZs
0x1800306dc  mov     rcx, [rsi+8]; sesid
0x1800306e0  call    cs:__imp_JetBeginTransaction
0x1800306e6  mov     edi, eax
0x1800306e8  test    eax, eax
0x1800306ea  jz      short loc_18003074B
0x1800306ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800306f3  cmp     rcx, r13
0x1800306f6  jz      short loc_18003071C
0x1800306f8  test    [rcx+1Ch], r12b
0x1800306fc  jz      short loc_18003071C
0x1800306fe  cmp     byte ptr [rcx+19h], 2
0x180030702  jb      short loc_18003071C
0x180030704  mov     rcx, [rcx+10h]
0x180030708  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18003070f  mov     edx, 1Dh
0x180030714  mov     r9d, eax
0x180030717  call    WPP_SF_d
0x18003071c  cmp     edi, 0FFFFFC0Dh
0x180030722  jnz     short loc_18003072B
0x180030724  mov     ebx, 8007000Eh
0x180030729  jmp     short loc_180030743
0x18003072b  mov     eax, edi
0x18003072d  neg     eax
0x18003072f  cmovs   eax, edi
0x180030732  and     edi, 8E5E0000h
0x180030738  movzx   ebx, ax
0x18003073b  or      ebx, edi
0x18003073d  or      ebx, 0E5E0000h
0x180030743  mov     [rbp+var_18], ebx
0x180030746  jmp     loc_180030816
0x18003074b  mov     rdx, rsi
0x18003074e  lea     rcx, [rbp+arg_18]
0x180030752  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180030757  lea     rcx, [rbp+arg_18]
0x18003075b  xor     edi, edi
0x18003075d  mov     [rbp+arg_0], rcx
0x180030761  cmp     edi, r14d
0x180030764  jnb     short loc_180030785
0x180030766  mov     edx, edi
0x180030768  mov     rcx, rsi; this
0x18003076b  shl     rdx, 4
0x18003076f  add     rdx, r15; struct _SCRUB_PARITY_EXTENT *
0x180030772  call    ?UpdateParityExtent@CScrubDatabase@@QEAAJPEBU_SCRUB_PARITY_EXTENT@@@Z; CScrubDatabase::UpdateParityExtent(_SCRUB_PARITY_EXTENT const *)
0x180030777  mov     [rbp+var_18], eax
0x18003077a  mov     ebx, eax
0x18003077c  test    eax, eax
0x18003077e  js      short loc_1800307F1
0x180030780  add     edi, r12d
0x180030783  jmp     short loc_180030761
0x180030785  mov     rcx, [rsi+8]; sesid
0x180030789  xor     edx, edx; grbit
0x18003078b  call    cs:__imp_JetCommitTransaction
0x180030791  mov     edi, eax
0x180030793  test    eax, eax
0x180030795  jz      short loc_1800307FC
0x180030797  mov     rcx, cs:WPP_GLOBAL_Control
0x18003079e  cmp     rcx, r13
0x1800307a1  jz      short loc_1800307C7
0x1800307a3  test    [rcx+1Ch], r12b
0x1800307a7  jz      short loc_1800307C7
0x1800307a9  cmp     byte ptr [rcx+19h], 2
0x1800307ad  jb      short loc_1800307C7
0x1800307af  mov     rcx, [rcx+10h]
0x1800307b3  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x1800307ba  mov     edx, 1Eh
0x1800307bf  mov     r9d, eax
0x1800307c2  call    WPP_SF_d
0x1800307c7  cmp     edi, 0FFFFFC0Dh
0x1800307cd  jnz     short loc_1800307D6
0x1800307cf  mov     ebx, 8007000Eh
0x1800307d4  jmp     short loc_1800307EE
0x1800307d6  mov     eax, edi
0x1800307d8  neg     eax
0x1800307da  cmovs   eax, edi
0x1800307dd  and     edi, 8E5E0000h
0x1800307e3  movzx   ebx, ax
0x1800307e6  or      ebx, edi
0x1800307e8  or      ebx, 0E5E0000h
0x1800307ee  mov     [rbp+var_18], ebx
0x1800307f1  lea     rcx, [rbp+arg_0]
0x1800307f5  call    CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e______CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___
0x1800307fa  jmp     short loc_180030816
0x1800307fc  lea     rcx, [rbp+arg_0]
0x180030800  mov     [rbp+arg_0], 0
0x180030808  mov     [rbp+var_18], 0
0x18003080f  call    CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e______CAutoTearDown__lambda_12881d7b0bf22b7d502b34deae262e0e___
0x180030814  xor     ebx, ebx
0x180030816  lea     rcx, [rbp+var_20]; this
0x18003081a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18003081f  mov     eax, ebx
0x180030821  mov     rbx, [rsp+50h+arg_8]
0x180030829  add     rsp, 50h
0x18003082d  pop     r15
0x18003082f  pop     r14
0x180030831  pop     r13
0x180030833  pop     r12
0x180030835  pop     rdi
0x180030836  pop     rsi
0x180030837  pop     rbp
0x180030838  retn
```
