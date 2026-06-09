# CScrubDatabase::CreateParityTable(void)

- ea: `0x18002eb28`
- end: `0x18002ed9f`
- name: `?CreateParityTable@CScrubDatabase@@AEAAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002f6a8`
- `0x18002f874`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18002eb28`
- `0x1800308c4`

## import_xrefs

- `ESENT!JetCreateTableColumnIndex2W` at `0x18002ecdc`
- `ESENT!JetCreateTableColumnIndex2W` at `0x18002ecdc`

## string_xrefs

- `0x18002eb43`: `CScrubDatabase::CreateParityTable`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::CreateParityTable(CScrubDatabase *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // r8
  JET_DBID v4; // edx
  JET_SESID v5; // rcx
  unsigned int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // edi
  unsigned int v10; // ebx
  int v11; // eax
  JET_TABLEID tableid; // rdx
  const char *v14; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-B8h]
  JET_TABLECREATE2_W ptablecreate; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 near **v18; // [rsp+B8h] [rbp-48h]
  __int64 v19; // [rsp+C0h] [rbp-40h]
  int v20; // [rsp+C8h] [rbp-38h]
  __int64 v21; // [rsp+D0h] [rbp-30h]
  __int64 v22; // [rsp+D8h] [rbp-28h]
  __int64 v23; // [rsp+E0h] [rbp-20h]
  int v24; // [rsp+E8h] [rbp-18h]
  unsigned __int16 near **v25; // [rsp+F0h] [rbp-10h]
  __int64 v26; // [rsp+F8h] [rbp-8h]
  int v27; // [rsp+100h] [rbp+0h]
  __int64 v28; // [rsp+108h] [rbp+8h]
  __int64 v29; // [rsp+110h] [rbp+10h]
  __int64 v30; // [rsp+118h] [rbp+18h]
  int v31; // [rsp+120h] [rbp+20h] BYREF
  WCHAR *v32; // [rsp+128h] [rbp+28h]
  unsigned __int16 near **v33; // [rsp+130h] [rbp+30h]
  int v34; // [rsp+138h] [rbp+38h]
  int v35; // [rsp+13Ch] [rbp+3Ch]
  int v36; // [rsp+140h] [rbp+40h]
  __int64 v37; // [rsp+148h] [rbp+48h]
  __int64 v38; // [rsp+150h] [rbp+50h]
  __int64 v39; // [rsp+158h] [rbp+58h]
  __int64 v40; // [rsp+160h] [rbp+60h]
  int v41; // [rsp+168h] [rbp+68h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v14 = "CScrubDatabase::CreateParityTable";
  v3 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v3 + 16) = "CScrubDatabase::CreateParityTable";
  ++*(_WORD *)(v3 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::CreateParityTable");
  }
  v19 = 15;
  v20 = 5;
  v17 = 56;
  v18 = &ParityTable::OffsetColumnName;
  v24 = 56;
  v25 = &ParityTable::LengthColumnName;
  v4 = *((_DWORD *)this + 4);
  v32 = ParityTable::OffsetIndexName;
  v33 = &ParityTable::OffsetIndexKey;
  ptablecreate.szTableName = ParityTable::TableName;
  ptablecreate.rgcolumncreate = (JET_COLUMNCREATE_W *)&v17;
  v31 = 80;
  v36 = 80;
  v5 = *((_QWORD *)this + 1);
  ptablecreate.rgindexcreate = (JET_INDEXCREATE_W *)&v31;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v26 = 15;
  v27 = 5;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v34 = 18;
  v35 = 7;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  *(_QWORD *)&ptablecreate.cbStruct = 96;
  ptablecreate.szTemplateTableName = 0;
  *(_QWORD *)&ptablecreate.ulPages = 8;
  *(_QWORD *)&ptablecreate.cColumns = 2;
  *(_QWORD *)&ptablecreate.cIndexes = 1;
  ptablecreate.szCallback = 0;
  ptablecreate.cbtyp = 0;
  ptablecreate.grbit = 1;
  ptablecreate.tableid = -1;
  *(_QWORD *)&ptablecreate.cCreated = 0;
  v6 = JetCreateTableColumnIndex2W(v5, v4, &ptablecreate);
  v9 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v6);
    }
    if ( v9 == -1011 )
    {
      v10 = -2147024882;
    }
    else
    {
      v11 = -v9;
      if ( v9 > 0 )
        LOWORD(v11) = v9;
      v10 = v9 & 0x8E5E0000 | (unsigned __int16)v11 | 0xE5E0000;
    }
    v15 = v10;
  }
  else
  {
    tableid = ptablecreate.tableid;
    *((_DWORD *)this + 8) = v23;
    *((_DWORD *)this + 9) = v30;
    *((_QWORD *)this + 3) = tableid;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SP(*((_QWORD *)WPP_GLOBAL_Control + 2), tableid, v7, v8, tableid);
    }
    v15 = 0;
    v10 = 0;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v14);
  return v10;
}

```

## disassembly

```asm
0x18002eb28  push    rbp
0x18002eb2a  push    rbx
0x18002eb2b  push    rsi
0x18002eb2c  push    rdi
0x18002eb2d  push    r14
0x18002eb2f  push    r15
0x18002eb31  lea     rbp, [rsp-78h]
0x18002eb36  sub     rsp, 178h
0x18002eb3d  mov     edx, cs:_tls_index
0x18002eb43  lea     r9, aCscrubdatabase_2; "CScrubDatabase::CreateParityTable"
0x18002eb4a  mov     rax, gs:58h
0x18002eb53  mov     rbx, rcx
0x18002eb56  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002eb5d  mov     r14d, 1
0x18002eb63  mov     [rsp+1A0h+var_160], r9
0x18002eb68  mov     r8, [rax+rdx*8]
0x18002eb6c  mov     eax, 10h
0x18002eb71  mov     edx, 8
0x18002eb76  mov     [rax+r8], r9
0x18002eb7a  movzx   eax, cx
0x18002eb7d  add     [rdx+r8], r14w
0x18002eb82  movzx   edx, word ptr [rdx+r8]
0x18002eb87  cmp     dx, cx
0x18002eb8a  cmovb   ax, dx
0x18002eb8e  cmovb   cx, dx
0x18002eb92  mov     [rsp+1A0h+var_170], ax
0x18002eb97  xor     eax, eax
0x18002eb99  mov     [rsp+1A0h+var_16C], eax
0x18002eb9d  mov     rax, cs:off_180047060; "                                       "...
0x18002eba4  mov     [rsp+1A0h+var_168], rax
0x18002eba9  mov     [rsp+1A0h+var_16E], cx
0x18002ebae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebb5  lea     r15, WPP_GLOBAL_Control
0x18002ebbc  lea     edi, [r14+4]
0x18002ebc0  cmp     rcx, r15
0x18002ebc3  jz      short loc_18002EBE7
0x18002ebc5  test    [rcx+1Ch], r14b
0x18002ebc9  jz      short loc_18002EBE7
0x18002ebcb  cmp     [rcx+19h], dil
0x18002ebcf  jb      short loc_18002EBE7
0x18002ebd1  mov     rcx, [rcx+10h]; LoggerHandle
0x18002ebd5  lea     edx, [rdi+8]
0x18002ebd8  mov     [rsp+1A0h+var_180], r9; __int64
0x18002ebdd  lea     r9, [rsp+1A0h+var_170]
0x18002ebe2  call    WPP_SF_aZs
0x18002ebe7  xor     esi, esi
0x18002ebe9  mov     [rbp+0A0h+var_E0], 0Fh
0x18002ebf1  mov     edx, 38h ; '8'
0x18002ebf6  mov     [rbp+0A0h+var_D8], edi
0x18002ebf9  lea     rax, ?OffsetColumnName@ParityTable@@3PAGA; "Offset"
0x18002ec00  mov     [rbp+0A0h+var_F0], edx
0x18002ec03  mov     [rbp+0A0h+var_E8], rax
0x18002ec07  lea     r8, [rsp+1A0h+ptablecreate]; ptablecreate
0x18002ec0c  lea     rax, ?LengthColumnName@ParityTable@@3PAGA; "Length"
0x18002ec13  mov     [rbp+0A0h+var_B8], edx
0x18002ec16  mov     [rbp+0A0h+var_B0], rax
0x18002ec1a  lea     ecx, [rdx+18h]
0x18002ec1d  mov     edx, [rbx+10h]; dbid
0x18002ec20  lea     rax, ?OffsetIndexName@ParityTable@@3PAGA; "ParityOffsetIndex"
0x18002ec27  mov     [rbp+0A0h+var_78], rax
0x18002ec2b  lea     rax, ?OffsetIndexKey@ParityTable@@3PAGA; "+Offset"
0x18002ec32  mov     [rbp+0A0h+var_70], rax
0x18002ec36  lea     rax, ?TableName@ParityTable@@3PAGA; "ParityExtent"
0x18002ec3d  mov     [rsp+1A0h+ptablecreate.szTableName], rax
0x18002ec42  lea     rax, [rbp+0A0h+var_F0]
0x18002ec46  mov     [rsp+1A0h+ptablecreate.rgcolumncreate], rax
0x18002ec4b  lea     rax, [rbp+0A0h+var_80]
0x18002ec4f  mov     [rbp+0A0h+var_80], ecx
0x18002ec52  mov     [rbp+0A0h+var_60], ecx
0x18002ec55  mov     rcx, [rbx+8]; sesid
0x18002ec59  mov     [rbp+0A0h+ptablecreate.rgindexcreate], rax
0x18002ec5d  mov     [rbp+0A0h+var_D0], rsi
0x18002ec61  mov     [rbp+0A0h+var_C8], rsi
0x18002ec65  mov     [rbp+0A0h+var_C0], rsi
0x18002ec69  mov     [rbp+0A0h+var_A8], 0Fh
0x18002ec71  mov     [rbp+0A0h+var_A0], edi
0x18002ec74  mov     [rbp+0A0h+var_98], rsi
0x18002ec78  mov     [rbp+0A0h+var_90], rsi
0x18002ec7c  mov     [rbp+0A0h+var_88], rsi
0x18002ec80  mov     [rbp+0A0h+var_68], 12h
0x18002ec87  mov     [rbp+0A0h+var_64], 7
0x18002ec8e  mov     [rbp+0A0h+var_58], rsi
0x18002ec92  mov     [rbp+0A0h+var_50], rsi
0x18002ec96  mov     [rbp+0A0h+var_48], rsi
0x18002ec9a  mov     [rbp+0A0h+var_40], rsi
0x18002ec9e  mov     [rbp+0A0h+var_38], esi
0x18002eca1  mov     qword ptr [rsp+1A0h+ptablecreate.cbStruct], 60h ; '`'
0x18002ecaa  mov     [rsp+1A0h+ptablecreate.szTemplateTableName], rsi
0x18002ecaf  mov     qword ptr [rsp+1A0h+ptablecreate.ulPages], 8
0x18002ecb8  mov     qword ptr [rsp+1A0h+ptablecreate.cColumns], 2
0x18002ecc1  mov     qword ptr [rbp+0A0h+ptablecreate.cIndexes], r14
0x18002ecc5  mov     [rbp+0A0h+ptablecreate.szCallback], rsi
0x18002ecc9  mov     [rbp+0A0h+ptablecreate.cbtyp], esi
0x18002eccc  mov     [rbp+0A0h+ptablecreate.grbit], r14d
0x18002ecd0  mov     [rbp+0A0h+ptablecreate.tableid], 0FFFFFFFFFFFFFFFFh
0x18002ecd8  mov     qword ptr [rbp+0A0h+ptablecreate.cCreated], rsi
0x18002ecdc  call    cs:__imp_JetCreateTableColumnIndex2W
0x18002ece2  mov     edi, eax
0x18002ece4  test    eax, eax
0x18002ece6  jz      short loc_18002ED43
0x18002ece8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecef  cmp     rcx, r15
0x18002ecf2  jz      short loc_18002ED16
0x18002ecf4  test    [rcx+1Ch], r14b
0x18002ecf8  jz      short loc_18002ED16
0x18002ecfa  cmp     byte ptr [rcx+19h], 2
0x18002ecfe  jb      short loc_18002ED16
0x18002ed00  mov     rcx, [rcx+10h]
0x18002ed04  lea     edx, [rsi+1Bh]
0x18002ed07  mov     r9d, eax
0x18002ed0a  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002ed11  call    WPP_SF_d
0x18002ed16  cmp     edi, 0FFFFFC0Dh
0x18002ed1c  jnz     short loc_18002ED25
0x18002ed1e  mov     ebx, 8007000Eh
0x18002ed23  jmp     short loc_18002ED3D
0x18002ed25  mov     eax, edi
0x18002ed27  neg     eax
0x18002ed29  cmovs   eax, edi
0x18002ed2c  and     edi, 8E5E0000h
0x18002ed32  movzx   ebx, ax
0x18002ed35  or      ebx, edi
0x18002ed37  or      ebx, 0E5E0000h
0x18002ed3d  mov     [rsp+1A0h+var_158], ebx
0x18002ed41  jmp     short loc_18002ED83
0x18002ed43  mov     eax, dword ptr [rbp+0A0h+var_C0]
0x18002ed46  mov     rdx, [rbp+0A0h+ptablecreate.tableid]
0x18002ed4a  mov     [rbx+20h], eax
0x18002ed4d  mov     eax, dword ptr [rbp+0A0h+var_88]
0x18002ed50  mov     [rbx+24h], eax
0x18002ed53  mov     [rbx+18h], rdx
0x18002ed57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed5e  cmp     rcx, r15
0x18002ed61  jz      short loc_18002ED7D
0x18002ed63  test    [rcx+1Ch], r14b
0x18002ed67  jz      short loc_18002ED7D
0x18002ed69  cmp     byte ptr [rcx+19h], 4
0x18002ed6d  jb      short loc_18002ED7D
0x18002ed6f  mov     rcx, [rcx+10h]
0x18002ed73  mov     [rsp+1A0h+var_180], rdx
0x18002ed78  call    WPP_SF_SP
0x18002ed7d  mov     [rsp+1A0h+var_158], esi
0x18002ed81  mov     ebx, esi
0x18002ed83  lea     rcx, [rsp+1A0h+var_160]; this
0x18002ed88  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002ed8d  mov     eax, ebx
0x18002ed8f  add     rsp, 178h
0x18002ed96  pop     r15
0x18002ed98  pop     r14
0x18002ed9a  pop     rdi
0x18002ed9b  pop     rsi
0x18002ed9c  pop     rbx
0x18002ed9d  pop     rbp
0x18002ed9e  retn
```
