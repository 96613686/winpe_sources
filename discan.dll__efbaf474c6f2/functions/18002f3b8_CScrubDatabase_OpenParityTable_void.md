# CScrubDatabase::OpenParityTable(void)

- ea: `0x18002f3b8`
- end: `0x18002f6a1`
- name: `?OpenParityTable@CScrubDatabase@@AEAAJXZ`
- size: `745`
- prototype: `__int64 __fastcall(CScrubDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18002f6a8`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x180012f60`
- `0x18002e760`
- `0x18002f3b8`
- `0x180030840`
- `0x180030934`
- `0x180037620`

## import_xrefs

- `ESENT!JetOpenTableW` at `0x18002f4b8`
- `ESENT!JetOpenTableW` at `0x18002f4b8`
- `ESENT!JetGetTableColumnInfoW` at `0x18002f59f`
- `ESENT!JetGetTableColumnInfoW` at `0x18002f59f`

## string_xrefs

- `0x18002f3e8`: `CScrubDatabase::OpenParityTable`

## pseudocode

```c
__int64 __fastcall CScrubDatabase::OpenParityTable(CScrubDatabase *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // rdx
  USHORT v5; // dx
  USHORT v6; // ax
  JET_DBID v7; // edx
  JET_SESID v8; // rcx
  unsigned int v9; // eax
  int v10; // edi
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  unsigned int v15; // esi
  JET_TABLEID v16; // rdx
  JET_SESID v17; // rcx
  const WCHAR *v18; // r15
  __int64 v19; // rdx
  JET_ERR TableColumnInfoW; // edi
  _DWORD *v21; // rcx
  int v22; // eax
  JET_TABLEID tableid; // [rsp+40h] [rbp-69h] BYREF
  _QWORD v25[2]; // [rsp+48h] [rbp-61h] BYREF
  const char *v26; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-49h]
  JET_PCWSTR szColumnName; // [rsp+68h] [rbp-41h]
  _QWORD v29[3]; // [rsp+70h] [rbp-39h]
  _BYTE v30[16]; // [rsp+88h] [rbp-21h] BYREF
  _DWORD pvResult[8]; // [rsp+98h] [rbp-11h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v26 = "CScrubDatabase::OpenParityTable";
  v27 = 0;
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "CScrubDatabase::OpenParityTable";
  v5 = ++*(_WORD *)(v4 + 8);
  v6 = Length;
  if ( v5 < Length )
  {
    v6 = v5;
    Length = v5;
  }
  LOWORD(v25[0]) = v6;
  HIDWORD(v25[0]) = 0;
  v25[1] = off_180047060;
  WORD1(v25[0]) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubDatabase::OpenParityTable");
  }
  v7 = *((_DWORD *)this + 4);
  v8 = *((_QWORD *)this + 1);
  tableid = 0;
  v9 = JetOpenTableW(v8, v7, ParityTable::TableName, 0, 0, 0x48u, &tableid);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6045f1246e8731b6b48955e2c326822f_Traceguids, v9);
    }
    if ( v10 == -1011 )
    {
      v11 = -2147024882;
    }
    else
    {
      v12 = -v10;
      if ( v10 > 0 )
        LOWORD(v12) = v10;
      v11 = v10 & 0x8E5E0000 | (unsigned __int16)v12 | 0xE5E0000;
    }
    v27 = v11;
  }
  else
  {
    lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_::_lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_(v30, this, &tableid);
    v15 = 0;
    szColumnName = (JET_PCWSTR)&ParityTable::OffsetColumnName;
    v25[0] = v30;
    v29[1] = &ParityTable::LengthColumnName;
    v29[0] = (char *)this + 32;
    v29[2] = (char *)this + 36;
    while ( 1 )
    {
      v16 = tableid;
      if ( v15 >= 2 )
        break;
      v17 = *((_QWORD *)this + 1);
      memset(pvResult, 0, 28);
      v18 = (const WCHAR *)v29[2 * v15 - 1];
      TableColumnInfoW = JetGetTableColumnInfoW(v17, tableid, v18, pvResult, 0x1Cu, 0);
      if ( TableColumnInfoW )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_SL(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v13, (_DWORD)v18, TableColumnInfoW);
        }
        if ( TableColumnInfoW == -1011 )
        {
          v11 = -2147024882;
        }
        else
        {
          v22 = -TableColumnInfoW;
          if ( TableColumnInfoW > 0 )
            LOWORD(v22) = TableColumnInfoW;
          v11 = TableColumnInfoW & 0x8E5E0000 | (unsigned __int16)v22 | 0xE5E0000;
        }
        v27 = v11;
        CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___::_CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___(
          v25,
          v19);
        goto LABEL_37;
      }
      v21 = (_DWORD *)v29[2 * v15++];
      *v21 = pvResult[1];
    }
    v25[0] = 0;
    *((_QWORD *)this + 3) = tableid;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SPDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, v13, v14, v16, *((_DWORD *)this + 8), *((_DWORD *)this + 9));
    }
    CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___::_CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___(
      v25,
      v16);
    v11 = 0;
  }
LABEL_37:
  CHResultImp::~CHResultImp((CHResultImp *)&v26);
  return v11;
}

```

## disassembly

```asm
0x18002f3b8  push    rbp
0x18002f3ba  push    rbx
0x18002f3bb  push    rsi
0x18002f3bc  push    rdi
0x18002f3bd  push    r12
0x18002f3bf  push    r13
0x18002f3c1  push    r14
0x18002f3c3  push    r15
0x18002f3c5  lea     rbp, [rsp-1Fh]
0x18002f3ca  sub     rsp, 0C8h
0x18002f3d1  mov     rax, cs:__security_cookie
0x18002f3d8  xor     rax, rsp
0x18002f3db  mov     [rbp+57h+var_48], rax
0x18002f3df  mov     rax, gs:58h
0x18002f3e8  lea     r8, aCscrubdatabase_5; "CScrubDatabase::OpenParityTable"
0x18002f3ef  mov     edx, cs:_tls_index
0x18002f3f5  mov     rbx, rcx
0x18002f3f8  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002f3ff  mov     r14d, 1
0x18002f405  mov     [rbp+57h+var_A8], r8
0x18002f409  mov     [rbp+57h+var_A0], 0
0x18002f410  mov     rdx, [rax+rdx*8]
0x18002f414  mov     eax, 10h
0x18002f419  mov     [rax+rdx], r8
0x18002f41d  mov     eax, 8
0x18002f422  add     [rax+rdx], r14w
0x18002f427  movzx   edx, word ptr [rax+rdx]
0x18002f42b  movzx   eax, cx
0x18002f42e  cmp     dx, cx
0x18002f431  cmovb   ax, dx
0x18002f435  cmovb   cx, dx
0x18002f439  mov     word ptr [rbp+57h+var_B8], ax
0x18002f43d  xor     eax, eax
0x18002f43f  mov     dword ptr [rbp+57h+var_B8+4], eax
0x18002f442  mov     rax, cs:off_180047060; "                                       "...
0x18002f449  mov     [rbp+57h+var_B0], rax
0x18002f44d  mov     word ptr [rbp+57h+var_B8+2], cx
0x18002f451  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f458  lea     r15, WPP_GLOBAL_Control
0x18002f45f  cmp     rcx, r15
0x18002f462  jz      short loc_18002F486
0x18002f464  test    [rcx+1Ch], r14b
0x18002f468  jz      short loc_18002F486
0x18002f46a  cmp     byte ptr [rcx+19h], 5
0x18002f46e  jb      short loc_18002F486
0x18002f470  mov     rcx, [rcx+10h]; LoggerHandle
0x18002f474  lea     edx, [r14+0Ch]
0x18002f478  lea     r9, [rbp+57h+var_B8]
0x18002f47c  mov     qword ptr [rsp+100h+cbParameters], r8; __int64
0x18002f481  call    WPP_SF_aZs
0x18002f486  mov     edx, [rbx+10h]; dbid
0x18002f489  lea     rax, [rbp+57h+tableid]
0x18002f48d  mov     rcx, [rbx+8]; sesid
0x18002f491  lea     r8, ?TableName@ParityTable@@3PAGA; "ParityExtent"
0x18002f498  mov     [rsp+100h+ptableid], rax; ptableid
0x18002f49d  xor     r9d, r9d; pvParameters
0x18002f4a0  mov     [rsp+100h+grbit], 48h ; 'H'; grbit
0x18002f4a8  mov     [rsp+100h+cbParameters], 0; cbParameters
0x18002f4b0  mov     [rbp+57h+tableid], 0
0x18002f4b8  call    cs:__imp_JetOpenTableW
0x18002f4be  mov     edi, eax
0x18002f4c0  test    eax, eax
0x18002f4c2  jz      short loc_18002F523
0x18002f4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4cb  cmp     rcx, r15
0x18002f4ce  jz      short loc_18002F4F4
0x18002f4d0  test    [rcx+1Ch], r14b
0x18002f4d4  jz      short loc_18002F4F4
0x18002f4d6  cmp     byte ptr [rcx+19h], 2
0x18002f4da  jb      short loc_18002F4F4
0x18002f4dc  mov     rcx, [rcx+10h]
0x18002f4e0  lea     r8, WPP_6045f1246e8731b6b48955e2c326822f_Traceguids
0x18002f4e7  mov     edx, 18h
0x18002f4ec  mov     r9d, eax
0x18002f4ef  call    WPP_SF_d
0x18002f4f4  cmp     edi, 0FFFFFC0Dh
0x18002f4fa  jnz     short loc_18002F503
0x18002f4fc  mov     ebx, 8007000Eh
0x18002f501  jmp     short loc_18002F51B
0x18002f503  mov     eax, edi
0x18002f505  neg     eax
0x18002f507  cmovs   eax, edi
0x18002f50a  and     edi, 8E5E0000h
0x18002f510  movzx   ebx, ax
0x18002f513  or      ebx, edi
0x18002f515  or      ebx, 0E5E0000h
0x18002f51b  mov     [rbp+57h+var_A0], ebx
0x18002f51e  jmp     loc_18002F676
0x18002f523  lea     r8, [rbp+57h+tableid]
0x18002f527  mov     rdx, rbx
0x18002f52a  lea     rcx, [rbp+57h+var_78]
0x18002f52e  call    _lambda_a1b1af645970ce3b4f2d5a29ed6a25f9____lambda_a1b1af645970ce3b4f2d5a29ed6a25f9_
0x18002f533  lea     rax, ?OffsetColumnName@ParityTable@@3PAGA; "Offset"
0x18002f53a  xor     esi, esi
0x18002f53c  mov     [rbp+57h+szColumnName], rax
0x18002f540  lea     rcx, [rbp+57h+var_78]
0x18002f544  lea     rax, ?LengthColumnName@ParityTable@@3PAGA; "Length"
0x18002f54b  mov     [rbp+57h+var_B8], rcx
0x18002f54f  lea     r12, [rbx+20h]
0x18002f553  mov     [rbp+57h+var_88], rax
0x18002f557  lea     r13, [rbx+24h]
0x18002f55b  mov     [rbp+57h+var_90], r12
0x18002f55f  mov     [rbp+57h+var_80], r13
0x18002f563  mov     rdx, [rbp+57h+tableid]; tableid
0x18002f567  cmp     esi, 2
0x18002f56a  jnb     loc_18002F622
0x18002f570  mov     rcx, [rbx+8]; sesid
0x18002f574  lea     r9, [rbp+57h+pvResult]; pvResult
0x18002f578  xorps   xmm0, xmm0
0x18002f57b  mov     r14d, esi
0x18002f57e  xor     eax, eax
0x18002f580  add     r14, r14
0x18002f583  movups  xmmword ptr [rbp+57h+pvResult], xmm0
0x18002f587  mov     [rsp+100h+grbit], eax; InfoLevel
0x18002f58b  movups  xmmword ptr [rbp+57h+pvResult+0Ch], xmm0
0x18002f58f  mov     r15, [rbp+r14*8+57h+szColumnName]
0x18002f594  mov     r8, r15; szColumnName
0x18002f597  mov     [rsp+100h+cbParameters], 1Ch; cbMax
0x18002f59f  call    cs:__imp_JetGetTableColumnInfoW
0x18002f5a5  mov     edi, eax
0x18002f5a7  test    eax, eax
0x18002f5a9  jnz     short loc_18002F5BE
0x18002f5ab  mov     rcx, [rbp+r14*8+57h+var_90]
0x18002f5b0  lea     r14d, [rdi+1]
0x18002f5b4  mov     eax, [rbp+57h+pvResult+4]
0x18002f5b7  add     esi, r14d
0x18002f5ba  mov     [rcx], eax
0x18002f5bc  jmp     short loc_18002F563
0x18002f5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5c5  lea     rax, WPP_GLOBAL_Control
0x18002f5cc  cmp     rcx, rax
0x18002f5cf  jz      short loc_18002F5ED
0x18002f5d1  test    byte ptr [rcx+1Ch], 1
0x18002f5d5  jz      short loc_18002F5ED
0x18002f5d7  cmp     byte ptr [rcx+19h], 2
0x18002f5db  jb      short loc_18002F5ED
0x18002f5dd  mov     rcx, [rcx+10h]
0x18002f5e1  mov     r9, r15
0x18002f5e4  mov     [rsp+100h+cbParameters], edi
0x18002f5e8  call    WPP_SF_SL
0x18002f5ed  cmp     edi, 0FFFFFC0Dh
0x18002f5f3  jnz     short loc_18002F5FC
0x18002f5f5  mov     ebx, 8007000Eh
0x18002f5fa  jmp     short loc_18002F614
0x18002f5fc  mov     eax, edi
0x18002f5fe  neg     eax
0x18002f600  cmovs   eax, edi
0x18002f603  and     edi, 8E5E0000h
0x18002f609  movzx   ebx, ax
0x18002f60c  or      ebx, edi
0x18002f60e  or      ebx, 0E5E0000h
0x18002f614  lea     rcx, [rbp+57h+var_B8]
0x18002f618  mov     [rbp+57h+var_A0], ebx
0x18002f61b  call    CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9______CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___
0x18002f620  jmp     short loc_18002F676
0x18002f622  mov     [rbp+57h+var_B8], 0
0x18002f62a  mov     [rbx+18h], rdx
0x18002f62e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f635  lea     rax, WPP_GLOBAL_Control
0x18002f63c  cmp     rcx, rax
0x18002f63f  jz      short loc_18002F66B
0x18002f641  test    [rcx+1Ch], r14b
0x18002f645  jz      short loc_18002F66B
0x18002f647  cmp     byte ptr [rcx+19h], 4
0x18002f64b  jb      short loc_18002F66B
0x18002f64d  mov     eax, [r13+0]
0x18002f651  mov     rcx, [rcx+10h]
0x18002f655  mov     dword ptr [rsp+100h+ptableid], eax
0x18002f659  mov     eax, [r12]
0x18002f65d  mov     [rsp+100h+grbit], eax
0x18002f661  mov     qword ptr [rsp+100h+cbParameters], rdx
0x18002f666  call    WPP_SF_SPDD
0x18002f66b  lea     rcx, [rbp+57h+var_B8]
0x18002f66f  call    CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9______CAutoTearDown__lambda_a1b1af645970ce3b4f2d5a29ed6a25f9___
0x18002f674  xor     ebx, ebx
0x18002f676  lea     rcx, [rbp+57h+var_A8]; this
0x18002f67a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002f67f  mov     eax, ebx
0x18002f681  mov     rcx, [rbp+57h+var_48]
0x18002f685  xor     rcx, rsp; StackCookie
0x18002f688  call    __security_check_cookie
0x18002f68d  add     rsp, 0C8h
0x18002f694  pop     r15
0x18002f696  pop     r14
0x18002f698  pop     r13
0x18002f69a  pop     r12
0x18002f69c  pop     rdi
0x18002f69d  pop     rsi
0x18002f69e  pop     rbx
0x18002f69f  pop     rbp
0x18002f6a0  retn
```
