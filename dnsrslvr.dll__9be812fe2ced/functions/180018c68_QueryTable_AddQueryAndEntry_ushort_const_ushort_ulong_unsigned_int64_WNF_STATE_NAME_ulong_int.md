# QueryTable::AddQueryAndEntry(ushort const *,ushort,ulong,unsigned __int64,_WNF_STATE_NAME,ulong,int)

- ea: `0x180018c68`
- end: `0x180018eeb`
- name: `?AddQueryAndEntry@QueryTable@@QEAAJPEBGGK_KU_WNF_STATE_NAME@@KH@Z`
- size: `643`
- prototype: `__int64 __fastcall(QueryTable *this, const unsigned __int16 *, unsigned __int16, unsigned int, unsigned __int64, struct _WNF_STATE_NAME, ULONG, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180017860`

## callees

- `0x180017e70`
- `0x180018074`
- `0x180018314`
- `0x180018420`
- `0x180018c68`
- `0x180018fb0`
- `0x180019334`
- `0x180046ec0`
- `0x180052504`
- `0x18007dbc0`
- `0x180085fb8`
- `0x180086b1c`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180018ee0`
- `ntdll!NtDeleteWnfStateName` at `0x180018ee0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018dd5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cc3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018cc3`

## pseudocode

```c
__int64 __fastcall QueryTable::AddQueryAndEntry(
        QueryTable *this,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        unsigned int a4,
        unsigned __int64 a5,
        struct _WNF_STATE_NAME a6,
        ULONG a7,
        int a8)
{
  QueryTable *v8; // r14
  QTableNode *v9; // rbx
  QTableNode *v12; // r12
  QTableNode *Query; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // edi
  int v17; // r13d
  unsigned int v18; // eax
  QueryTable **v19; // rcx
  QueryTable **v20; // rax
  __int64 v22; // rdx
  QTableEntry *v23; // rdi
  QTableNode *v24; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+48h] [rbp-38h]
  struct QTableEntry *v26; // [rsp+50h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+58h] [rbp-28h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-20h]
  _WNF_STATE_NAME v29; // [rsp+68h] [rbp-18h] BYREF

  v8 = g_QueryTable;
  v9 = 0;
  v29 = a6;
  v25 = a4;
  v27 = a2;
  v24 = 0;
  v26 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)g_QueryTable + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)g_QueryTable + 1);
  v12 = 0;
  Query = QueryTable::FindQuery(v8, a2, a3);
  if ( !Query )
  {
    v14 = QTableNode::CreateInstance(v8, a2, a3, &v24);
    v16 = v14;
    if ( v14 )
    {
      v17 = 1;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 49, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, v14);
      v9 = v24;
      goto LABEL_15;
    }
    v9 = v24;
    Query = v24;
    v12 = v24;
  }
  v17 = 0;
  v18 = QTableNode::AddEntry((QTableNode ***)Query, v25, (struct _WNF_STATE_NAME)a5, v29, a7, a8, &v26);
  v16 = v18;
  if ( v18 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_15;
    v22 = 50;
    goto LABEL_22;
  }
  *(_DWORD *)(*((_QWORD *)Query + 11) + 36LL) -= *((_DWORD *)Query + 8);
  DnsCachedRecordsList::RemoveExpiredRecords((QTableNode *)((char *)Query + 16));
  *(_DWORD *)(*((_QWORD *)Query + 11) + 36LL) += *((_DWORD *)Query + 8);
  if ( *((_QWORD *)Query + 2) )
  {
    v23 = v26;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_SdDD(
        *((unsigned __int16 *)Query + 4),
        51,
        (unsigned int)WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids,
        *(_QWORD *)Query,
        *((_WORD *)Query + 4),
        *((_DWORD *)v26 + 12),
        *((_DWORD *)v26 + 13));
    v18 = QTableEntry::AddRecordsList(v23, (QTableNode *)((char *)Query + 16));
    v16 = v18;
    if ( v18 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_15;
      v22 = 52;
LABEL_22:
      WPP_SF_d(1035, v22, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, v18);
      goto LABEL_15;
    }
  }
  if ( v12 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_S(1035, 53, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids, v27);
    v19 = (QueryTable **)*((_QWORD *)v8 + 1);
    if ( *v19 != v8 )
      __fastfail(3u);
    v20 = (QueryTable **)((char *)v9 + 40);
    v9 = 0;
    *v20 = v8;
    v20[1] = (QueryTable *)v19;
    *v19 = (QueryTable *)v20;
    *((_QWORD *)v8 + 1) = v20;
  }
  QueryTable::RemoveNodeFromCache(v8, Query);
LABEL_15:
  if ( v9 )
    QTableNode::`scalar deleting destructor'(v9, v15);
  if ( v17 )
    NtDeleteWnfStateName(&v29);
  LeaveCriticalSection(lpCriticalSection);
  return v16;
}

```

## disassembly

```asm
0x180018c68  mov     [rsp-38h+arg_0], rbx
0x180018c6d  push    rbp
0x180018c6e  push    rsi
0x180018c6f  push    rdi
0x180018c70  push    r12
0x180018c72  push    r13
0x180018c74  push    r14
0x180018c76  push    r15
0x180018c78  mov     rbp, rsp
0x180018c7b  sub     rsp, 80h
0x180018c82  mov     rax, cs:__security_cookie
0x180018c89  xor     rax, rsp
0x180018c8c  mov     [rbp+var_10], rax
0x180018c90  mov     r14, cs:?g_QueryTable@@3PEAVQueryTable@@EA; QueryTable * g_QueryTable
0x180018c97  xor     ebx, ebx
0x180018c99  mov     rax, qword ptr [rbp+arg_28.Data]
0x180018c9d  movzx   edi, r8w
0x180018ca1  mov     qword ptr [rbp+var_18.Data], rax
0x180018ca5  mov     r15, rdx
0x180018ca8  mov     [rbp+var_38], r9d
0x180018cac  lea     rax, [r14+28h]
0x180018cb0  mov     [rbp+var_28], rdx
0x180018cb4  mov     rcx, rax; lpCriticalSection
0x180018cb7  mov     [rbp+var_40], rbx
0x180018cbb  mov     [rbp+var_30], rbx
0x180018cbf  mov     [rbp+lpCriticalSection], rax
0x180018cc3  call    cs:__imp_EnterCriticalSection
0x180018cc9  movzx   r8d, di; unsigned __int16
0x180018ccd  mov     rdx, r15; unsigned __int16 *
0x180018cd0  mov     rcx, r14; this
0x180018cd3  call    ?FindQuery@QueryTable@@QEAAPEAVQTableNode@@PEBGG@Z; QueryTable::FindQuery(ushort const *,ushort)
0x180018cd8  xor     r12d, r12d
0x180018cdb  mov     rsi, rax
0x180018cde  test    rax, rax
0x180018ce1  jnz     short loc_180018D20
0x180018ce3  lea     r9, [rbp+var_40]; struct QTableNode **
0x180018ce7  movzx   r8d, di; unsigned __int16
0x180018ceb  mov     rdx, r15; unsigned __int16 *
0x180018cee  mov     rcx, r14; struct QueryTable *
0x180018cf1  call    ?CreateInstance@QTableNode@@SAJPEAVQueryTable@@PEBGGPEAPEAV1@@Z; QTableNode::CreateInstance(QueryTable *,ushort const *,ushort,QTableNode * *)
0x180018cf6  mov     edi, eax
0x180018cf8  test    eax, eax
0x180018cfa  jz      short loc_180018D16
0x180018cfc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180018d03  lea     r13d, [rbx+1]
0x180018d07  jnz     loc_180018E28
0x180018d0d  mov     rbx, [rbp+var_40]
0x180018d11  jmp     loc_180018DBF
0x180018d16  mov     rbx, [rbp+var_40]
0x180018d1a  mov     rsi, rbx
0x180018d1d  mov     r12, rbx
0x180018d20  mov     r9, qword ptr [rbp+var_18.Data]; struct _WNF_STATE_NAME
0x180018d24  lea     rax, [rbp+var_30]
0x180018d28  mov     r8, [rbp+arg_20]; unsigned __int64
0x180018d2c  mov     rcx, rsi; this
0x180018d2f  mov     edx, [rbp+var_38]; unsigned int
0x180018d32  xor     r13d, r13d
0x180018d35  mov     [rsp+80h+var_50], rax; struct QTableEntry **
0x180018d3a  mov     eax, [rbp+arg_38]
0x180018d3d  mov     [rsp+80h+var_58], eax; int
0x180018d41  mov     eax, [rbp+arg_30]
0x180018d44  mov     [rsp+80h+var_60], eax; unsigned int
0x180018d48  call    ?AddEntry@QTableNode@@QEAAJK_KU_WNF_STATE_NAME@@KHPEAPEAVQTableEntry@@@Z; QTableNode::AddEntry(ulong,unsigned __int64,_WNF_STATE_NAME,ulong,int,QTableEntry * *)
0x180018d4d  mov     edi, eax
0x180018d4f  test    eax, eax
0x180018d51  jnz     loc_180018E04
0x180018d57  mov     rcx, [rsi+58h]
0x180018d5b  lea     r15, [rsi+10h]
0x180018d5f  mov     eax, [r15+10h]
0x180018d63  sub     [rcx+24h], eax
0x180018d66  mov     rcx, r15; this
0x180018d69  call    ?RemoveExpiredRecords@DnsCachedRecordsList@@QEAAXXZ; DnsCachedRecordsList::RemoveExpiredRecords(void)
0x180018d6e  mov     rcx, [rsi+58h]
0x180018d72  mov     eax, [rsi+20h]
0x180018d75  add     [rcx+24h], eax
0x180018d78  cmp     [r15], r13
0x180018d7b  jnz     loc_180018E46
0x180018d81  test    r12, r12
0x180018d84  jz      short loc_180018DB4
0x180018d86  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180018d8d  jnz     loc_180018EA9
0x180018d93  mov     rcx, [r14+8]
0x180018d97  cmp     [rcx], r14
0x180018d9a  jnz     loc_180018EC8
0x180018da0  lea     rax, [rbx+28h]
0x180018da4  xor     ebx, ebx
0x180018da6  mov     [rax], r14
0x180018da9  mov     [rax+8], rcx
0x180018dad  mov     [rcx], rax
0x180018db0  mov     [r14+8], rax
0x180018db4  mov     rdx, rsi; struct QTableNode *
0x180018db7  mov     rcx, r14; this
0x180018dba  call    ?RemoveNodeFromCache@QueryTable@@QEAAXPEAVQTableNode@@@Z; QueryTable::RemoveNodeFromCache(QTableNode *)
0x180018dbf  test    rbx, rbx
0x180018dc2  jnz     loc_180018ECF
0x180018dc8  test    r13d, r13d
0x180018dcb  jnz     loc_180018EDC
0x180018dd1  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180018dd5  call    cs:__imp_LeaveCriticalSection
0x180018ddb  mov     eax, edi
0x180018ddd  mov     rcx, [rbp+var_10]
0x180018de1  xor     rcx, rsp; StackCookie
0x180018de4  call    __security_check_cookie
0x180018de9  mov     rbx, [rsp+80h+arg_0]
0x180018df1  add     rsp, 80h
0x180018df8  pop     r15
0x180018dfa  pop     r14
0x180018dfc  pop     r13
0x180018dfe  pop     r12
0x180018e00  pop     rdi
0x180018e01  pop     rsi
0x180018e02  pop     rbp
0x180018e03  retn
0x180018e04  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180018e0b  jz      short loc_180018DBF
0x180018e0d  mov     edx, 32h ; '2'
0x180018e12  mov     r9d, eax
0x180018e15  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180018e1c  mov     ecx, 40Bh
0x180018e21  call    WPP_SF_d
0x180018e26  jmp     short loc_180018DBF
0x180018e28  mov     edx, 31h ; '1'
0x180018e2d  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180018e34  mov     ecx, 40Bh
0x180018e39  mov     r9d, eax
0x180018e3c  call    WPP_SF_d
0x180018e41  jmp     loc_180018D0D
0x180018e46  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180018e4d  mov     rdi, [rbp+var_30]
0x180018e51  jz      short loc_180018E7D
0x180018e53  mov     eax, [rdi+34h]
0x180018e56  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180018e5d  movzx   ecx, word ptr [rsi+8]
0x180018e61  mov     edx, 33h ; '3'
0x180018e66  mov     r9, [rsi]
0x180018e69  mov     dword ptr [rsp+80h+var_50], eax
0x180018e6d  mov     eax, [rdi+30h]
0x180018e70  mov     [rsp+80h+var_58], eax
0x180018e74  mov     [rsp+80h+var_60], ecx
0x180018e78  call    WPP_SF_SdDD
0x180018e7d  mov     rdx, r15; struct DnsCachedRecordsList *
0x180018e80  mov     rcx, rdi; this
0x180018e83  call    ?AddRecordsList@QTableEntry@@QEAAJPEAVDnsCachedRecordsList@@@Z; QTableEntry::AddRecordsList(DnsCachedRecordsList *)
0x180018e88  mov     edi, eax
0x180018e8a  test    eax, eax
0x180018e8c  jz      loc_180018D81
0x180018e92  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180018e99  jz      loc_180018DBF
0x180018e9f  mov     edx, 34h ; '4'
0x180018ea4  jmp     loc_180018E12
0x180018ea9  mov     r9, [rbp+var_28]
0x180018ead  lea     r8, WPP_b99c85ad30f53c31ccd08e8a981e02ae_Traceguids
0x180018eb4  mov     edx, 35h ; '5'
0x180018eb9  mov     ecx, 40Bh
0x180018ebe  call    WPP_SF_S
0x180018ec3  jmp     loc_180018D93
0x180018ec8  mov     ecx, 3
0x180018ecd  int     29h; Win8: RtlFailFast(ecx)
0x180018ecf  mov     rcx, rbx; this
0x180018ed2  call    ??_GQTableNode@@QEAAPEAXI@Z; QTableNode::`scalar deleting destructor'(uint)
0x180018ed7  jmp     loc_180018DC8
0x180018edc  lea     rcx, [rbp+var_18]
0x180018ee0  call    cs:__imp_NtDeleteWnfStateName
0x180018ee6  jmp     loc_180018DD1
```
