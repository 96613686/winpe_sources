# DhcpPolicyWildCardLenListInit

- ea: `0x1800bae60`
- end: `0x1800bb096`
- name: `DhcpPolicyWildCardLenListInit`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180025144`

## callees

- `0x1800b8ba0`
- `0x1800bae60`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800bafe7`
- `ESENT!JetRetrieveColumns` at `0x1800bafe7`
- `ESENT!JetSetCurrentIndex2A` at `0x1800baf2e`
- `ESENT!JetSetCurrentIndex2A` at `0x1800baf2e`
- `ESENT!JetMakeKey` at `0x1800baf66`
- `ESENT!JetMakeKey` at `0x1800baf66`
- `ESENT!JetSeek` at `0x1800baf96`
- `ESENT!JetSeek` at `0x1800baf96`
- `ESENT!JetMove` at `0x1800bb03d`
- `ESENT!JetMove` at `0x1800bb03d`

## string_xrefs

- `0x1800bb04b`: `DhcpPolicyWildCardLenListInit:JetMove`

## pseudocode

```c
__int64 DhcpPolicyWildCardLenListInit()
{
  JET_SESID v0; // rsi
  unsigned int v1; // ebx
  LPVOID v2; // r14
  unsigned int v3; // eax
  __int64 result; // rax
  unsigned int Key; // eax
  unsigned int v6; // edi
  unsigned int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // r9
  char pvData[4]; // [rsp+38h] [rbp-69h] BYREF
  int v11; // [rsp+3Ch] [rbp-65h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-61h] BYREF
  unsigned int v13; // [rsp+44h] [rbp-5Dh] BYREF
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+48h] [rbp-59h] BYREF
  int v15; // [rsp+78h] [rbp-29h]
  unsigned int *v16; // [rsp+80h] [rbp-21h]
  __int64 v17; // [rsp+88h] [rbp-19h]
  __int64 v18; // [rsp+90h] [rbp-11h]
  __int64 v19; // [rsp+98h] [rbp-9h]
  int v20; // [rsp+A0h] [rbp-1h]
  JET_COLUMNID v21; // [rsp+A8h] [rbp+7h]
  int *v22; // [rsp+B0h] [rbp+Fh]
  __int64 v23; // [rsp+B8h] [rbp+17h]
  __int64 v24; // [rsp+C0h] [rbp+1Fh]
  __int64 v25; // [rsp+C8h] [rbp+27h]
  int v26; // [rsp+D0h] [rbp+2Fh]

  v0 = DhcpGlobalJetServerSession;
  v1 = 0;
  v2 = DhcpGlobalThisServer;
  pretrievecolumn.columnid = dword_1800F9580;
  pretrievecolumn.pvData = &v13;
  v15 = dword_1800F9640;
  v16 = &v12;
  v21 = dword_1800F95F8;
  v22 = &v11;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  pvData[0] = 1;
  *(_QWORD *)&pretrievecolumn.cbData = 4;
  *(_QWORD *)&pretrievecolumn.grbit = 1;
  *(_QWORD *)&pretrievecolumn.itagSequence = 1;
  pretrievecolumn.err = 0;
  v17 = 4;
  v18 = 1;
  v19 = 1;
  v20 = 0;
  v23 = 4;
  v24 = 1;
  v25 = 1;
  v26 = 0;
  v3 = JetSetCurrentIndex2A(DhcpGlobalJetServerSession, PolicyConditionTableId, "PolicyConditionTable_Index3", 0);
  result = PolicyMapJetError(v3, "DhcpPolicyWildCardLenListInit:JetSetCurrentIndex2");
  if ( !(_DWORD)result )
  {
    Key = JetMakeKey(v0, PolicyConditionTableId, pvData, 1u, 1u);
    result = PolicyMapJetError(Key, "DhcpPolicyWildCardLenListInit:5");
    if ( !(_DWORD)result )
    {
      v6 = JetSeek(v0, PolicyConditionTableId, 0x21u);
      result = PolicyMapJetError(v6, "DhcpPolicyWildCardLenListInit:7");
      if ( !(_DWORD)result )
      {
        do
        {
          v7 = JetRetrieveColumns(v0, PolicyConditionTableId, &pretrievecolumn, 3u);
          v8 = PolicyMapJetError(v7, "DhcpPolicyWildCardLenListInit:1");
          if ( v8 )
            break;
          if ( v11 == 4 || (v9 = 1, v11 == 5) )
            v9 = 0;
          result = AddWildCardLengthToSubnet(v2, v13, v12, v9);
          if ( (_DWORD)result )
            return result;
          v7 = JetMove(v0, PolicyConditionTableId, 1, 0);
          v8 = PolicyMapJetError(v7, "DhcpPolicyWildCardLenListInit:JetMove");
        }
        while ( !v8 );
        if ( v7 != -1603 )
          return v8;
        return v1;
      }
      if ( v6 == -1601 || v6 == 1039 )
        return v1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800bae60  mov     rax, rsp
0x1800bae63  mov     [rax+8], rbx
0x1800bae67  mov     [rax+10h], rsi
0x1800bae6b  mov     [rax+18h], rdi
0x1800bae6f  push    rbp
0x1800bae70  push    r14
0x1800bae72  push    r15
0x1800bae74  lea     rbp, [rax-5Fh]
0x1800bae78  sub     rsp, 0E0h
0x1800bae7f  mov     rax, cs:__security_cookie
0x1800bae86  xor     rax, rsp
0x1800bae89  mov     [rbp+57h+var_20], rax
0x1800bae8d  mov     eax, cs:dword_1800F9580
0x1800bae93  lea     r8, aPolicyconditio_4; "PolicyConditionTable_Index3"
0x1800bae9a  mov     rsi, cs:DhcpGlobalJetServerSession
0x1800baea1  xor     ebx, ebx
0x1800baea3  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800baeaa  xor     r9d, r9d; grbit
0x1800baead  mov     r14, cs:DhcpGlobalThisServer
0x1800baeb4  mov     rcx, rsi; sesid
0x1800baeb7  mov     [rbp+57h+pretrievecolumn.columnid], eax
0x1800baeba  lea     rax, [rbp+57h+var_B4]
0x1800baebe  lea     r15d, [rbx+1]
0x1800baec2  mov     [rbp+57h+pretrievecolumn.pvData], rax
0x1800baec6  mov     eax, cs:dword_1800F9640
0x1800baecc  mov     [rbp+57h+var_80], eax
0x1800baecf  lea     rax, [rbp+57h+var_B8]
0x1800baed3  mov     [rbp+57h+var_78], rax
0x1800baed7  mov     eax, cs:dword_1800F95F8
0x1800baedd  mov     [rbp+57h+var_50], eax
0x1800baee0  lea     rax, [rbp+57h+var_BC]
0x1800baee4  mov     [rbp+57h+var_48], rax
0x1800baee8  mov     [rbp+57h+var_B8], ebx
0x1800baeeb  mov     [rbp+57h+var_BC], ebx
0x1800baeee  mov     [rbp+57h+var_B4], ebx
0x1800baef1  mov     [rbp+57h+pvData], r15b
0x1800baef5  mov     qword ptr [rbp+57h+pretrievecolumn.cbData], 4
0x1800baefd  mov     qword ptr [rbp+57h+pretrievecolumn.grbit], r15
0x1800baf01  mov     qword ptr [rbp+57h+pretrievecolumn.itagSequence], r15
0x1800baf05  mov     [rbp+57h+pretrievecolumn.err], ebx
0x1800baf08  mov     [rbp+57h+var_70], 4
0x1800baf10  mov     [rbp+57h+var_68], r15
0x1800baf14  mov     [rbp+57h+var_60], r15
0x1800baf18  mov     [rbp+57h+var_58], ebx
0x1800baf1b  mov     [rbp+57h+var_40], 4
0x1800baf23  mov     [rbp+57h+var_38], r15
0x1800baf27  mov     [rbp+57h+var_30], r15
0x1800baf2b  mov     [rbp+57h+var_28], ebx
0x1800baf2e  call    cs:__imp_JetSetCurrentIndex2A
0x1800baf35  nop     dword ptr [rax+rax+00h]
0x1800baf3a  mov     ecx, eax
0x1800baf3c  lea     rdx, aDhcppolicywild; "DhcpPolicyWildCardLenListInit:JetSetCur"...
0x1800baf43  call    PolicyMapJetError
0x1800baf48  test    eax, eax
0x1800baf4a  jnz     loc_1800BB06C
0x1800baf50  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800baf57  lea     r8, [rbp+57h+pvData]; pvData
0x1800baf5b  mov     r9d, r15d; cbData
0x1800baf5e  mov     [rsp+0F0h+grbit], r15d; grbit
0x1800baf63  mov     rcx, rsi; sesid
0x1800baf66  call    cs:__imp_JetMakeKey
0x1800baf6d  nop     dword ptr [rax+rax+00h]
0x1800baf72  mov     ecx, eax
0x1800baf74  lea     rdx, aDhcppolicywild_0; "DhcpPolicyWildCardLenListInit:5"
0x1800baf7b  call    PolicyMapJetError
0x1800baf80  test    eax, eax
0x1800baf82  jnz     loc_1800BB06C
0x1800baf88  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800baf8f  lea     r8d, [rbx+21h]; grbit
0x1800baf93  mov     rcx, rsi; sesid
0x1800baf96  call    cs:__imp_JetSeek
0x1800baf9d  nop     dword ptr [rax+rax+00h]
0x1800bafa2  mov     ecx, eax
0x1800bafa4  lea     rdx, aDhcppolicywild_3; "DhcpPolicyWildCardLenListInit:7"
0x1800bafab  mov     edi, eax
0x1800bafad  call    PolicyMapJetError
0x1800bafb2  test    eax, eax
0x1800bafb4  jz      short loc_1800BAFD3
0x1800bafb6  cmp     edi, 0FFFFF9BFh
0x1800bafbc  jz      loc_1800BB06A
0x1800bafc2  cmp     edi, 40Fh
0x1800bafc8  jnz     loc_1800BB06C
0x1800bafce  jmp     loc_1800BB06A
0x1800bafd3  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bafda  lea     r8, [rbp+57h+pretrievecolumn]; pretrievecolumn
0x1800bafde  mov     r9d, 3; cretrievecolumn
0x1800bafe4  mov     rcx, rsi; sesid
0x1800bafe7  call    cs:__imp_JetRetrieveColumns
0x1800bafee  nop     dword ptr [rax+rax+00h]
0x1800baff3  mov     ecx, eax
0x1800baff5  lea     rdx, aDhcppolicywild_1; "DhcpPolicyWildCardLenListInit:1"
0x1800baffc  mov     edi, eax
0x1800baffe  call    PolicyMapJetError
0x1800bb003  test    eax, eax
0x1800bb005  jnz     short loc_1800BB061
0x1800bb007  mov     eax, [rbp+57h+var_BC]
0x1800bb00a  sub     eax, 4
0x1800bb00d  jz      short loc_1800BB017
0x1800bb00f  mov     r9d, r15d
0x1800bb012  cmp     eax, r15d
0x1800bb015  jnz     short loc_1800BB01A
0x1800bb017  mov     r9d, ebx
0x1800bb01a  mov     r8d, [rbp+57h+var_B8]
0x1800bb01e  mov     rcx, r14
0x1800bb021  mov     edx, [rbp+57h+var_B4]
0x1800bb024  call    AddWildCardLengthToSubnet
0x1800bb029  test    eax, eax
0x1800bb02b  jnz     short loc_1800BB06C
0x1800bb02d  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800bb034  xor     r9d, r9d; grbit
0x1800bb037  mov     r8d, r15d; cRow
0x1800bb03a  mov     rcx, rsi; sesid
0x1800bb03d  call    cs:__imp_JetMove
0x1800bb044  nop     dword ptr [rax+rax+00h]
0x1800bb049  mov     ecx, eax
0x1800bb04b  lea     rdx, aDhcppolicywild_2; "DhcpPolicyWildCardLenListInit:JetMove"
0x1800bb052  mov     edi, eax
0x1800bb054  call    PolicyMapJetError
0x1800bb059  test    eax, eax
0x1800bb05b  jz      loc_1800BAFD3
0x1800bb061  cmp     edi, 0FFFFF9BDh
0x1800bb067  cmovnz  ebx, eax
0x1800bb06a  mov     eax, ebx
0x1800bb06c  mov     rcx, [rbp+57h+var_20]
0x1800bb070  xor     rcx, rsp; StackCookie
0x1800bb073  call    __security_check_cookie
0x1800bb078  lea     r11, [rsp+0F0h+var_10]
0x1800bb080  mov     rbx, [r11+20h]
0x1800bb084  mov     rsi, [r11+28h]
0x1800bb088  mov     rdi, [r11+30h]
0x1800bb08c  mov     rsp, r11
0x1800bb08f  pop     r15
0x1800bb091  pop     r14
0x1800bb093  pop     rbp
0x1800bb094  retn
```
