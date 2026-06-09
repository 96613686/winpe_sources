# RemovePolicyRangeEntry

- ea: `0x1800bccbc`
- end: `0x1800bd06f`
- name: `RemovePolicyRangeEntry`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180089788`

## callees

- `0x1800bc990`
- `0x1800bccbc`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x1800bcd12`
- `ESENT!JetSetCurrentIndexA` at `0x1800bce6a`
- `ESENT!JetSetCurrentIndexA` at `0x1800bcd12`
- `ESENT!JetSetCurrentIndexA` at `0x1800bce6a`
- `ESENT!JetRetrieveColumns` at `0x1800bce0b`
- `ESENT!JetRetrieveColumns` at `0x1800bcf19`
- `ESENT!JetRetrieveColumns` at `0x1800bcf66`
- `ESENT!JetRetrieveColumns` at `0x1800bce0b`
- `ESENT!JetRetrieveColumns` at `0x1800bcf19`
- `ESENT!JetRetrieveColumns` at `0x1800bcf66`
- `ESENT!JetSetColumns` at `0x1800bd008`
- `ESENT!JetSetColumns` at `0x1800bd008`
- `ESENT!JetUpdate` at `0x1800bd03b`
- `ESENT!JetUpdate` at `0x1800bd03b`
- `ESENT!JetMakeKey` at `0x1800bcd51`
- `ESENT!JetMakeKey` at `0x1800bcd8c`
- `ESENT!JetMakeKey` at `0x1800bcea2`
- `ESENT!JetMakeKey` at `0x1800bcd51`
- `ESENT!JetMakeKey` at `0x1800bcd8c`
- `ESENT!JetMakeKey` at `0x1800bcea2`
- `ESENT!JetSeek` at `0x1800bcdb7`
- `ESENT!JetSeek` at `0x1800bcecd`
- `ESENT!JetSeek` at `0x1800bcdb7`
- `ESENT!JetSeek` at `0x1800bcecd`
- `ESENT!JetDelete` at `0x1800bce37`
- `ESENT!JetDelete` at `0x1800bce37`
- `ESENT!JetPrepareUpdate` at `0x1800bcfb9`
- `ESENT!JetPrepareUpdate` at `0x1800bcfb9`

## string_xrefs

- `0x1800bcd20`: `RemovePolicyRangeEntry:JetSetCurrentIndex`
- `0x1800bce78`: `RemovePolicyRangeEntry:JetSetCurrentIndex`
- `0x1800bce45`: `RemovePolicyRangeEntry:JetDelete`
- `0x1800bce19`: `RemovePolicyRangeEntry:JetRetrieveColumns1`
- `0x1800bcf27`: `RemovePolicyRangeEntry:JetRetrieveColumns1`
- `0x1800bcdc5`: `RemovePolicyRangeEntry:JetSeek`
- `0x1800bcedb`: `RemovePolicyRangeEntry:JetSeek`
- `0x1800bcd5d`: `RemovePolicyRangeEntry:JetMakeKey`
- `0x1800bd049`: `RemovePolicyRangeEntry:Jetupdate`
- `0x1800bd016`: `RemovePolicyRangeEntry:JetSetColumns`
- `0x1800bcfc7`: `RemovePolicyRangeEntry:JetPrepareUpdate`
- `0x1800bcf74`: `RemovePolicyRangeEntry:JetRetrieveColumns2`

## pseudocode

```c
__int64 __fastcall RemovePolicyRangeEntry(__int64 a1, __int64 a2, int a3)
{
  JET_SESID v3; // rbx
  unsigned int v5; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int itagSequence; // esi
  unsigned int v17; // edi
  unsigned int v18; // eax
  int v19; // eax
  int v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  JET_SETCOLUMN psetcolumn; // [rsp+30h] [rbp-39h] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+58h] [rbp-11h] BYREF
  int v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+D4h] [rbp+6Bh]
  int pvData; // [rsp+E0h] [rbp+77h] BYREF
  int v29; // [rsp+E8h] [rbp+7Fh] BYREF

  pvData = a3;
  v27 = HIDWORD(a1);
  v3 = DhcpGlobalJetServerSession;
  v26 = 0;
  v29 = 0;
  memset(&psetcolumn, 0, 36);
  v5 = JetSetCurrentIndexA(DhcpGlobalJetServerSession, PolicyRangeTableId, "PolicyRangeTable_Index2");
  result = PolicyMapJetError(v5, "RemovePolicyRangeEntry:JetSetCurrentIndex");
  if ( (_DWORD)result )
    return result;
  Key = JetMakeKey(v3, PolicyRangeTableId, (const void *)a2, 4u, 1u);
  result = PolicyMapJetError(Key, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v8 = JetMakeKey(v3, PolicyRangeTableId, (const void *)(a2 + 4), 4u, 0);
  result = PolicyMapJetError(v8, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v9 = JetSeek(v3, PolicyRangeTableId, 1u);
  if ( (unsigned int)PolicyMapJetError(v9, "RemovePolicyRangeEntry:JetSeek") )
    return 20107;
  pretrievecolumn.columnid = dword_1800F9738;
  pretrievecolumn.err = 0;
  pretrievecolumn.pvData = &v26;
  *(_QWORD *)&pretrievecolumn.grbit = 1;
  *(_QWORD *)&pretrievecolumn.cbData = 4;
  *(_QWORD *)&pretrievecolumn.itagSequence = 1;
  v10 = JetRetrieveColumns(v3, PolicyRangeTableId, &pretrievecolumn, 1u);
  result = PolicyMapJetError(v10, "RemovePolicyRangeEntry:JetRetrieveColumns1");
  if ( (_DWORD)result )
    return result;
  v11 = JetDelete(v3, PolicyRangeTableId);
  result = PolicyMapJetError(v11, "RemovePolicyRangeEntry:JetDelete");
  if ( (_DWORD)result )
    return result;
  v12 = JetSetCurrentIndexA(v3, PolicyTableId, "PolicyTable_Index1");
  result = PolicyMapJetError(v12, "RemovePolicyRangeEntry:JetSetCurrentIndex");
  if ( (_DWORD)result )
    return result;
  v13 = JetMakeKey(v3, PolicyTableId, &pvData, 4u, 1u);
  result = PolicyMapJetError(v13, "RemovePolicyRangeEntry:JetMakeKey");
  if ( (_DWORD)result )
    return result;
  v14 = JetSeek(v3, PolicyTableId, 1u);
  result = PolicyMapJetError(v14, "RemovePolicyRangeEntry:JetSeek");
  if ( (_DWORD)result )
    return result;
  pretrievecolumn.columnid = dword_1800F9830;
  pretrievecolumn.grbit = 1;
  pretrievecolumn.itagSequence = 0;
  pretrievecolumn.pvData = 0;
  pretrievecolumn.cbData = 0;
  v15 = JetRetrieveColumns(v3, PolicyTableId, &pretrievecolumn, 1u);
  result = PolicyMapJetError(v15, "RemovePolicyRangeEntry:JetRetrieveColumns1");
  if ( (_DWORD)result )
    return result;
  itagSequence = pretrievecolumn.itagSequence;
  v17 = 1;
  if ( !pretrievecolumn.itagSequence )
  {
    v20 = v26;
    v19 = v29;
LABEL_17:
    if ( v19 == v20 )
    {
LABEL_18:
      v21 = JetPrepareUpdate(v3, PolicyTableId, 2u);
      result = PolicyMapJetError(v21, "RemovePolicyRangeEntry:JetPrepareUpdate");
      if ( !(_DWORD)result )
      {
        psetcolumn.columnid = dword_1800F9830;
        psetcolumn.err = 0;
        psetcolumn.itagSequence = v17;
        memset(&psetcolumn.pvData, 0, 20);
        v22 = JetSetColumns(v3, PolicyTableId, &psetcolumn, 1u);
        result = PolicyMapJetError(v22, "RemovePolicyRangeEntry:JetSetColumns");
        if ( !(_DWORD)result )
        {
          v23 = JetUpdate(v3, PolicyTableId, 0, 0, 0);
          return PolicyMapJetError(v23, "RemovePolicyRangeEntry:Jetupdate");
        }
      }
      return result;
    }
    return 20107;
  }
  while ( 1 )
  {
    pretrievecolumn.pvData = &v29;
    pretrievecolumn.itagSequence = v17;
    pretrievecolumn.cbData = 4;
    v18 = JetRetrieveColumns(v3, PolicyTableId, &pretrievecolumn, 1u);
    result = PolicyMapJetError(v18, "RemovePolicyRangeEntry:JetRetrieveColumns2");
    if ( (_DWORD)result )
      return result;
    v19 = v29;
    v20 = v26;
    if ( v29 == v26 )
      goto LABEL_18;
    if ( ++v17 > itagSequence )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x1800bccbc  mov     [rsp-8+pvData], r8d
0x1800bccc1  mov     [rsp-8+arg_0], rcx
0x1800bccc6  push    rbp
0x1800bccc7  push    rbx
0x1800bccc8  push    rsi
0x1800bccc9  push    rdi
0x1800bccca  push    r12
0x1800bcccc  push    r14
0x1800bccce  push    r15
0x1800bccd0  lea     rbp, [rsp-27h]
0x1800bccd5  sub     rsp, 90h
0x1800bccdc  mov     rbx, cs:DhcpGlobalJetServerSession
0x1800bcce3  lea     r8, aPolicyrangetab_1; "PolicyRangeTable_Index2"
0x1800bccea  xorps   xmm0, xmm0
0x1800bcced  mov     rdi, rdx
0x1800bccf0  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bccf7  xor     r14d, r14d
0x1800bccfa  xor     eax, eax
0x1800bccfc  mov     dword ptr [rbp+57h+arg_0], r14d
0x1800bcd00  mov     rcx, rbx; sesid
0x1800bcd03  mov     [rbp+57h+arg_18], r14d
0x1800bcd07  movups  xmmword ptr [rbp+57h+psetcolumn.columnid], xmm0
0x1800bcd0b  mov     [rbp+57h+psetcolumn.err], eax
0x1800bcd0e  movups  xmmword ptr [rbp+57h+psetcolumn.cbData], xmm0
0x1800bcd12  call    cs:__imp_JetSetCurrentIndexA
0x1800bcd19  nop     dword ptr [rax+rax+00h]
0x1800bcd1e  mov     ecx, eax
0x1800bcd20  lea     rdx, aRemovepolicyra_3; "RemovePolicyRangeEntry:JetSetCurrentInd"...
0x1800bcd27  call    PolicyMapJetError
0x1800bcd2c  test    eax, eax
0x1800bcd2e  jnz     loc_1800BD05C
0x1800bcd34  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bcd3b  lea     r12d, [r14+4]
0x1800bcd3f  lea     r15d, [r14+1]
0x1800bcd43  mov     r9d, r12d; cbData
0x1800bcd46  mov     r8, rdi; pvData
0x1800bcd49  mov     [rsp+0C0h+grbit], r15d; grbit
0x1800bcd4e  mov     rcx, rbx; sesid
0x1800bcd51  call    cs:__imp_JetMakeKey
0x1800bcd58  nop     dword ptr [rax+rax+00h]
0x1800bcd5d  lea     rsi, aRemovepolicyra; "RemovePolicyRangeEntry:JetMakeKey"
0x1800bcd64  mov     ecx, eax
0x1800bcd66  mov     rdx, rsi
0x1800bcd69  call    PolicyMapJetError
0x1800bcd6e  test    eax, eax
0x1800bcd70  jnz     loc_1800BD05C
0x1800bcd76  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bcd7d  lea     r8, [rdi+4]; pvData
0x1800bcd81  mov     r9d, r12d; cbData
0x1800bcd84  mov     [rsp+0C0h+grbit], r14d; grbit
0x1800bcd89  mov     rcx, rbx; sesid
0x1800bcd8c  call    cs:__imp_JetMakeKey
0x1800bcd93  nop     dword ptr [rax+rax+00h]
0x1800bcd98  mov     ecx, eax
0x1800bcd9a  mov     rdx, rsi
0x1800bcd9d  call    PolicyMapJetError
0x1800bcda2  test    eax, eax
0x1800bcda4  jnz     loc_1800BD05C
0x1800bcdaa  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bcdb1  mov     r8d, r15d; grbit
0x1800bcdb4  mov     rcx, rbx; sesid
0x1800bcdb7  call    cs:__imp_JetSeek
0x1800bcdbe  nop     dword ptr [rax+rax+00h]
0x1800bcdc3  mov     ecx, eax
0x1800bcdc5  lea     rdx, aRemovepolicyra_6; "RemovePolicyRangeEntry:JetSeek"
0x1800bcdcc  call    PolicyMapJetError
0x1800bcdd1  test    eax, eax
0x1800bcdd3  jnz     loc_1800BD057
0x1800bcdd9  mov     eax, cs:dword_1800F9738
0x1800bcddf  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bcde3  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bcdea  mov     r9d, r15d; cretrievecolumn
0x1800bcded  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800bcdf0  mov     rcx, rbx; sesid
0x1800bcdf3  lea     rax, [rbp+57h+arg_0]
0x1800bcdf7  mov     qword ptr [rbp+57h+pretrievecolumn.columnidNextTagged], r14
0x1800bcdfb  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800bcdff  mov     qword ptr [rbp+57h+pretrievecolumn.grbit], r15
0x1800bce03  mov     qword ptr [rbp+57h+pretrievecolumn.cbData], r12
0x1800bce07  mov     [rbp+57h+pretrievecolumn.itagSequence], r15d
0x1800bce0b  call    cs:__imp_JetRetrieveColumns
0x1800bce12  nop     dword ptr [rax+rax+00h]
0x1800bce17  mov     ecx, eax
0x1800bce19  lea     rdx, aRemovepolicyra_5; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bce20  call    PolicyMapJetError
0x1800bce25  test    eax, eax
0x1800bce27  jnz     loc_1800BD05C
0x1800bce2d  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800bce34  mov     rcx, rbx; sesid
0x1800bce37  call    cs:__imp_JetDelete
0x1800bce3e  nop     dword ptr [rax+rax+00h]
0x1800bce43  mov     ecx, eax
0x1800bce45  lea     rdx, aRemovepolicyra_1; "RemovePolicyRangeEntry:JetDelete"
0x1800bce4c  call    PolicyMapJetError
0x1800bce51  test    eax, eax
0x1800bce53  jnz     loc_1800BD05C
0x1800bce59  mov     rdx, cs:PolicyTableId; tableid
0x1800bce60  lea     r8, aPolicytableInd_1; "PolicyTable_Index1"
0x1800bce67  mov     rcx, rbx; sesid
0x1800bce6a  call    cs:__imp_JetSetCurrentIndexA
0x1800bce71  nop     dword ptr [rax+rax+00h]
0x1800bce76  mov     ecx, eax
0x1800bce78  lea     rdx, aRemovepolicyra_3; "RemovePolicyRangeEntry:JetSetCurrentInd"...
0x1800bce7f  call    PolicyMapJetError
0x1800bce84  test    eax, eax
0x1800bce86  jnz     loc_1800BD05C
0x1800bce8c  mov     rdx, cs:PolicyTableId; tableid
0x1800bce93  lea     r8, [rbp+57h+pvData]; pvData
0x1800bce97  mov     r9d, r12d; cbData
0x1800bce9a  mov     [rsp+0C0h+grbit], r15d; grbit
0x1800bce9f  mov     rcx, rbx; sesid
0x1800bcea2  call    cs:__imp_JetMakeKey
0x1800bcea9  nop     dword ptr [rax+rax+00h]
0x1800bceae  mov     ecx, eax
0x1800bceb0  mov     rdx, rsi
0x1800bceb3  call    PolicyMapJetError
0x1800bceb8  test    eax, eax
0x1800bceba  jnz     loc_1800BD05C
0x1800bcec0  mov     rdx, cs:PolicyTableId; tableid
0x1800bcec7  mov     r8d, r15d; grbit
0x1800bceca  mov     rcx, rbx; sesid
0x1800bcecd  call    cs:__imp_JetSeek
0x1800bced4  nop     dword ptr [rax+rax+00h]
0x1800bced9  mov     ecx, eax
0x1800bcedb  lea     rdx, aRemovepolicyra_6; "RemovePolicyRangeEntry:JetSeek"
0x1800bcee2  call    PolicyMapJetError
0x1800bcee7  test    eax, eax
0x1800bcee9  jnz     loc_1800BD05C
0x1800bceef  mov     eax, cs:dword_1800F9830
0x1800bcef5  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bcef9  mov     rdx, cs:PolicyTableId; tableid
0x1800bcf00  mov     r9d, r15d; cretrievecolumn
0x1800bcf03  mov     rcx, rbx; sesid
0x1800bcf06  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800bcf09  mov     [rbp+57h+pretrievecolumn.grbit], r15d
0x1800bcf0d  mov     [rbp+57h+pretrievecolumn.itagSequence], r14d
0x1800bcf11  mov     [rbp+57h+pretrievecolumn.pvData], r14
0x1800bcf15  mov     [rbp+57h+pretrievecolumn.cbData], r14d
0x1800bcf19  call    cs:__imp_JetRetrieveColumns
0x1800bcf20  nop     dword ptr [rax+rax+00h]
0x1800bcf25  mov     ecx, eax
0x1800bcf27  lea     rdx, aRemovepolicyra_5; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bcf2e  call    PolicyMapJetError
0x1800bcf33  test    eax, eax
0x1800bcf35  jnz     loc_1800BD05C
0x1800bcf3b  mov     esi, [rbp+57h+pretrievecolumn.itagSequence]
0x1800bcf3e  mov     edi, r15d
0x1800bcf41  cmp     esi, r15d
0x1800bcf44  jb      short loc_1800BCF9B
0x1800bcf46  mov     rdx, cs:PolicyTableId; tableid
0x1800bcf4d  lea     rax, [rbp+57h+arg_18]
0x1800bcf51  mov     r9d, r15d; cretrievecolumn
0x1800bcf54  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800bcf58  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bcf5c  mov     [rbp+57h+pretrievecolumn.itagSequence], edi
0x1800bcf5f  mov     rcx, rbx; sesid
0x1800bcf62  mov     [rbp+57h+pretrievecolumn.cbData], r12d
0x1800bcf66  call    cs:__imp_JetRetrieveColumns
0x1800bcf6d  nop     dword ptr [rax+rax+00h]
0x1800bcf72  mov     ecx, eax
0x1800bcf74  lea     rdx, aRemovepolicyra_7; "RemovePolicyRangeEntry:JetRetrieveColum"...
0x1800bcf7b  call    PolicyMapJetError
0x1800bcf80  test    eax, eax
0x1800bcf82  jnz     loc_1800BD05C
0x1800bcf88  mov     eax, [rbp+57h+arg_18]
0x1800bcf8b  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1800bcf8e  cmp     eax, ecx
0x1800bcf90  jz      short loc_1800BCFA9
0x1800bcf92  add     edi, r15d
0x1800bcf95  cmp     edi, esi
0x1800bcf97  jbe     short loc_1800BCF46
0x1800bcf99  jmp     short loc_1800BCFA1
0x1800bcf9b  mov     ecx, dword ptr [rbp+57h+arg_0]
0x1800bcf9e  mov     eax, [rbp+57h+arg_18]
0x1800bcfa1  cmp     eax, ecx
0x1800bcfa3  jnz     loc_1800BD057
0x1800bcfa9  mov     rdx, cs:PolicyTableId; tableid
0x1800bcfb0  mov     r8d, 2; prep
0x1800bcfb6  mov     rcx, rbx; sesid
0x1800bcfb9  call    cs:__imp_JetPrepareUpdate
0x1800bcfc0  nop     dword ptr [rax+rax+00h]
0x1800bcfc5  mov     ecx, eax
0x1800bcfc7  lea     rdx, aRemovepolicyra_0; "RemovePolicyRangeEntry:JetPrepareUpdate"
0x1800bcfce  call    PolicyMapJetError
0x1800bcfd3  test    eax, eax
0x1800bcfd5  jnz     loc_1800BD05C
0x1800bcfdb  mov     eax, cs:dword_1800F9830
0x1800bcfe1  lea     r8, [rbp+57h+psetcolumn]; psetcolumn
0x1800bcfe5  mov     rdx, cs:PolicyTableId; tableid
0x1800bcfec  mov     r9d, r15d; csetcolumn
0x1800bcfef  mov     rcx, rbx; sesid
0x1800bcff2  mov     [rbp+57h+psetcolumn.columnid], eax
0x1800bcff5  mov     [rbp+57h+psetcolumn.err], r14d
0x1800bcff9  mov     qword ptr [rbp+57h+psetcolumn.grbit], r14
0x1800bcffd  mov     [rbp+57h+psetcolumn.itagSequence], edi
0x1800bd000  mov     [rbp+57h+psetcolumn.pvData], r14
0x1800bd004  mov     [rbp+57h+psetcolumn.cbData], r14d
0x1800bd008  call    cs:__imp_JetSetColumns
0x1800bd00f  nop     dword ptr [rax+rax+00h]
0x1800bd014  mov     ecx, eax
0x1800bd016  lea     rdx, aRemovepolicyra_4; "RemovePolicyRangeEntry:JetSetColumns"
0x1800bd01d  call    PolicyMapJetError
0x1800bd022  test    eax, eax
0x1800bd024  jnz     short loc_1800BD05C
0x1800bd026  mov     rdx, cs:PolicyTableId; tableid
0x1800bd02d  xor     r9d, r9d; cbBookmark
0x1800bd030  xor     r8d, r8d; pvBookmark
0x1800bd033  mov     qword ptr [rsp+0C0h+grbit], r14; pcbActual
0x1800bd038  mov     rcx, rbx; sesid
0x1800bd03b  call    cs:__imp_JetUpdate
0x1800bd042  nop     dword ptr [rax+rax+00h]
0x1800bd047  mov     ecx, eax
0x1800bd049  lea     rdx, aRemovepolicyra_2; "RemovePolicyRangeEntry:Jetupdate"
0x1800bd050  call    PolicyMapJetError
0x1800bd055  jmp     short loc_1800BD05C
0x1800bd057  mov     eax, 4E8Bh
0x1800bd05c  add     rsp, 90h
0x1800bd063  pop     r15
0x1800bd065  pop     r14
0x1800bd067  pop     r12
0x1800bd069  pop     rdi
0x1800bd06a  pop     rsi
0x1800bd06b  pop     rbx
0x1800bd06c  pop     rbp
0x1800bd06d  retn
```
