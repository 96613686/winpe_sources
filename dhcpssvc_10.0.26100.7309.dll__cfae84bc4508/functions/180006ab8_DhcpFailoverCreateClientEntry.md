# DhcpFailoverCreateClientEntry

- ea: `0x180006ab8`
- end: `0x180007145`
- name: `DhcpFailoverCreateClientEntry`
- size: `1677`
- prototype: `__int64 __fastcall(char *pvData, int, int, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800067dc`
- `0x180058f38`
- `0x18005ad38`

## callees

- `0x180003c9c`
- `0x180006ab8`
- `0x180008f80`
- `0x18000eaf4`
- `0x18000eb24`
- `0x18000ef84`
- `0x18000f0c4`
- `0x18000f0f8`
- `0x18000f144`
- `0x180021120`
- `0x180025b98`
- `0x180031918`
- `0x18009877c`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800070a6`
- `ESENT!JetUpdate` at `0x1800070a6`
- `ESENT!JetSetColumn` at `0x180006cc0`
- `ESENT!JetSetColumn` at `0x180006cc0`
- `KERNEL32!EnterCriticalSection` at `0x180006af3`
- `KERNEL32!EnterCriticalSection` at `0x180006af3`
- `KERNEL32!LeaveCriticalSection` at `0x1800070cc`
- `KERNEL32!LeaveCriticalSection` at `0x1800070cc`

## string_xrefs

- `0x1800070f3`: `CreateClientEntryVQ:JetUpdate`

## pseudocode

```c
__int64 __fastcall DhcpFailoverCreateClientEntry(char *pvData, int a2, int a3, int a4)
{
  char *v4; // rbx
  char v6; // r12
  unsigned int v7; // edi
  int v10; // esi
  __int64 v11; // r8
  JET_COLUMNID v12; // ecx
  int v13; // eax
  __int64 v14; // r15
  _WORD *v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // r8d
  int IsEnabledDeviceUsageNoInline; // eax
  _WORD *v19; // rdx
  unsigned int cbData; // ecx
  __int64 v21; // rax
  __int64 v22; // rbx
  unsigned int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  _WORD *String; // rax
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // r8
  _WORD *v31; // rax
  __int64 v32; // r8
  _WORD *v33; // rdx
  unsigned int v34; // r8d
  unsigned int v35; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rdx
  int v41; // eax
  __int64 v42; // r8
  _QWORD v43[2]; // [rsp+50h] [rbp-10h] BYREF
  int pvDataa; // [rsp+A0h] [rbp+40h] BYREF
  int v45; // [rsp+A8h] [rbp+48h] BYREF

  v45 = a2;
  v4 = pvData + 56;
  v6 = pvData[56];
  v7 = 0;
  pvDataa = 0;
  v43[0] = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v10 = DhcpJetBeginTransaction();
  if ( v10 )
    goto LABEL_73;
  DhcpDoDynDnsCreateEntryWork(
    (struct in_addr *)pvData,
    *((const wchar_t **)pvData + 4),
    v4,
    &v45,
    v6 == 2,
    *((_DWORD *)pvData + 4),
    *((_QWORD *)pvData + 1),
    a4,
    *((_DWORD *)pvData + 29) & 1);
  v10 = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, pvData, v11, v45 == 0);
  if ( v10 )
    goto LABEL_73;
  if ( !v45 )
  {
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), pvData, 4u);
    if ( v10 )
      goto LABEL_73;
  }
  pvDataa = DhcpGetSubnetMaskForAddress(*(unsigned int *)pvData);
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 104), &pvDataa, 4u);
  if ( v10 )
    goto LABEL_73;
  DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v4, 1u);
  v12 = *(_DWORD *)(DhcpGlobalClientTable + 24);
  if ( v6 != 2 )
  {
    v10 = DhcpJetSetValue(v12, *((void **)pvData + 1), *((_DWORD *)pvData + 4));
    if ( v10 )
      goto LABEL_73;
    v13 = v45;
    v14 = -1;
    if ( v45 )
    {
      if ( !*((_QWORD *)pvData + 4) )
      {
LABEL_16:
        if ( !v13 || *((_QWORD *)pvData + 5) )
        {
          IsEnabledDeviceUsageNoInline = Feature_Servicing_DhcpClientInfoGetJetWarning__private_IsEnabledDeviceUsageNoInline();
          v19 = (_WORD *)*((_QWORD *)pvData + 5);
          if ( IsEnabledDeviceUsageNoInline )
          {
            if ( v19 )
            {
              v21 = -1;
              do
                ++v21;
              while ( v19[v21] );
              cbData = 2 * v21 + 2;
            }
            else
            {
              cbData = 0;
            }
            v22 = (unsigned int)JetSetColumn(
                                  DhcpGlobalJetServerSession,
                                  DhcpGlobalClientTableHandle,
                                  *(_DWORD *)(DhcpGlobalClientTable + 56),
                                  *((const void **)pvData + 5),
                                  cbData,
                                  0,
                                  0);
            v10 = DhcpMapJetError(v22, "JetSetValue:Setcolumn");
            if ( (_DWORD)v22 == 1512 )
              v10 = 20013;
          }
          else
          {
            if ( v19 )
            {
              v24 = -1;
              do
                ++v24;
              while ( v19[v24] );
              v23 = 2 * v24 + 2;
            }
            else
            {
              v23 = 0;
            }
            v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 56), v19, v23);
          }
          if ( v10 )
            goto LABEL_73;
        }
        v43[0] = *((_DWORD *)pvData + 5)
              && *((_DWORD *)pvData + 6)
              && (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, *(unsigned int *)pvData)
               ? 0x7FFFFFFFFFFFFFFFLL
               : *(_QWORD *)(pvData + 20);
        v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), v43, 8u);
        if ( v10 )
          goto LABEL_73;
        goto LABEL_50;
      }
      v15 = (_WORD *)*((_QWORD *)pvData + 4);
    }
    else
    {
      v15 = (_WORD *)*((_QWORD *)pvData + 4);
      if ( !v15 )
      {
        v17 = 0;
        goto LABEL_14;
      }
    }
    v16 = -1;
    do
      ++v16;
    while ( v15[v16] );
    v17 = 2 * v16 + 2;
LABEL_14:
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), v15, v17);
    if ( !v10 )
    {
      v13 = v45;
      goto LABEL_16;
    }
LABEL_73:
    DhcpJetRollBack();
    goto LABEL_74;
  }
  v10 = DhcpJetSetValue(v12, pvData, 4u);
  if ( v10 )
    goto LABEL_73;
  String = (_WORD *)GetString(1080, v25, v26);
  v14 = -1;
  v28 = -1;
  do
    ++v28;
  while ( String[v28] );
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), String, 2 * (int)v28 + 2);
  if ( v10 )
    goto LABEL_73;
  v31 = (_WORD *)GetString(1081, v29, v30);
  v32 = -1;
  do
    ++v32;
  while ( v31[v32] );
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 56), v31, 2 * (int)v32 + 2);
  if ( v10 )
    goto LABEL_73;
  v43[0] = *(_QWORD *)(pvData + 20);
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), v43, 8u);
  if ( v10 )
    goto LABEL_73;
LABEL_50:
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 136), &DhcpGlobalServerName, DhcpGlobalServerNameLen);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 120), pvData + 52, 4u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), pvData + 48, 1u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 168), pvData + 57, 1u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 184), pvData + 60, 8u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 200), pvData + 68, 1u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), pvData + 72, 4u);
  if ( v10 )
    goto LABEL_73;
  if ( !a3 )
  {
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 232), pvData + 76, 4u);
    if ( v10 )
      goto LABEL_73;
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 248), pvData + 80, 4u);
    if ( v10 )
      goto LABEL_73;
  }
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 264), pvData + 84, 4u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), pvData + 88, 4u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 296), pvData + 92, 4u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 312), pvData + 112, 1u);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 328), pvData + 96, 4u);
  if ( v10 )
    goto LABEL_73;
  v33 = (_WORD *)*((_QWORD *)pvData + 13);
  if ( v33 )
  {
    do
      ++v14;
    while ( v33[v14] );
    v34 = 2 * v14 + 2;
  }
  else
  {
    v34 = 0;
  }
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 344), v33, v34);
  if ( v10 )
    goto LABEL_73;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), pvData + 116, 4u);
  if ( v10 )
    goto LABEL_73;
  v35 = JetUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0, 0, 0);
  if ( v35 == -1605 )
  {
    v10 = 20014;
    goto LABEL_73;
  }
  v10 = DhcpMapJetError(v35, "CreateClientEntryVQ:JetUpdate");
  if ( v10 )
    goto LABEL_73;
  DhcpJetCommitTransaction();
  if ( v6 == 2 )
  {
    v39 = GetString(1080, v37, v38);
    v41 = GetString(1074, v40, v39);
    DhcpUpdateAuditLog(v10 + 13, v41, *(_DWORD *)pvData, 0, 0, v42);
    goto LABEL_75;
  }
LABEL_74:
  v7 = v10;
LABEL_75:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return v7;
}

```

## disassembly

```asm
0x180006ab8  mov     [rsp-38h+arg_10], rbx
0x180006abd  mov     [rsp-38h+arg_8], edx
0x180006ac1  push    rbp
0x180006ac2  push    rsi
0x180006ac3  push    rdi
0x180006ac4  push    r12
0x180006ac6  push    r13
0x180006ac8  push    r14
0x180006aca  push    r15
0x180006acc  mov     rbp, rsp
0x180006acf  sub     rsp, 60h
0x180006ad3  lea     rbx, [rcx+38h]
0x180006ad7  mov     r14, rcx
0x180006ada  mov     r12b, [rbx]
0x180006add  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180006ae4  xor     edi, edi
0x180006ae6  mov     r15d, r9d
0x180006ae9  mov     [rbp+pvData], edi
0x180006aec  mov     r13d, r8d
0x180006aef  mov     [rbp+var_10], rdi
0x180006af3  call    cs:__imp_EnterCriticalSection
0x180006afa  nop     dword ptr [rax+rax+00h]
0x180006aff  call    DhcpJetBeginTransaction
0x180006b04  mov     esi, eax
0x180006b06  test    eax, eax
0x180006b08  jnz     loc_1800070BE
0x180006b0e  mov     eax, [r14+74h]
0x180006b12  lea     r9, [rbp+arg_8]
0x180006b16  mov     rdx, [r14+20h]
0x180006b1a  and     eax, 1
0x180006b1d  mov     [rsp+60h+var_20], eax
0x180006b21  mov     ecx, edi
0x180006b23  mov     rax, [r14+8]
0x180006b27  cmp     r12b, 2
0x180006b2b  mov     [rsp+60h+var_28], r15d
0x180006b30  mov     r8, rbx
0x180006b33  mov     [rsp+60h+psetinfo], rax
0x180006b38  setz    cl
0x180006b3b  mov     eax, [r14+10h]
0x180006b3f  mov     [rsp+60h+grbit], eax
0x180006b43  mov     [rsp+60h+cbData], ecx
0x180006b47  mov     rcx, r14
0x180006b4a  call    DhcpDoDynDnsCreateEntryWork
0x180006b4f  mov     rcx, cs:DhcpGlobalClientTable
0x180006b56  mov     r9d, edi
0x180006b59  cmp     [rbp+arg_8], edi
0x180006b5c  mov     rdx, r14
0x180006b5f  setz    r9b
0x180006b63  mov     rcx, [rcx]
0x180006b66  call    DhcpJetPrepareUpdate
0x180006b6b  mov     esi, eax
0x180006b6d  test    eax, eax
0x180006b6f  jnz     loc_1800070BE
0x180006b75  lea     r15d, [rdi+4]
0x180006b79  cmp     [rbp+arg_8], edi
0x180006b7c  jnz     short loc_180006B9D
0x180006b7e  mov     rcx, cs:DhcpGlobalClientTable
0x180006b85  mov     r8d, r15d; cbData
0x180006b88  mov     rdx, r14; pvData
0x180006b8b  mov     ecx, [rcx+8]; columnid
0x180006b8e  call    DhcpJetSetValue
0x180006b93  mov     esi, eax
0x180006b95  test    eax, eax
0x180006b97  jnz     loc_1800070BE
0x180006b9d  mov     ecx, [r14]
0x180006ba0  call    DhcpGetSubnetMaskForAddress
0x180006ba5  mov     rcx, cs:DhcpGlobalClientTable
0x180006bac  lea     rdx, [rbp+pvData]; pvData
0x180006bb0  mov     [rbp+pvData], eax
0x180006bb3  mov     r8d, r15d; cbData
0x180006bb6  mov     ecx, [rcx+68h]; columnid
0x180006bb9  call    DhcpJetSetValue
0x180006bbe  mov     esi, eax
0x180006bc0  test    eax, eax
0x180006bc2  jnz     loc_1800070BE
0x180006bc8  mov     rcx, cs:DhcpGlobalClientTable
0x180006bcf  lea     r8d, [rax+1]; cbData
0x180006bd3  mov     rdx, rbx; pvData
0x180006bd6  mov     ecx, [rcx+28h]; columnid
0x180006bd9  call    DhcpJetSetValue
0x180006bde  mov     rcx, cs:DhcpGlobalClientTable
0x180006be5  mov     ecx, [rcx+18h]; columnid
0x180006be8  cmp     r12b, 2
0x180006bec  jz      loc_180006D83
0x180006bf2  mov     r8d, [r14+10h]; cbData
0x180006bf6  mov     rdx, [r14+8]; pvData
0x180006bfa  call    DhcpJetSetValue
0x180006bff  mov     esi, eax
0x180006c01  test    eax, eax
0x180006c03  jnz     loc_1800070BE
0x180006c09  mov     eax, [rbp+arg_8]
0x180006c0c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006c10  test    eax, eax
0x180006c12  jz      short loc_180006C76
0x180006c14  cmp     [r14+20h], rdi
0x180006c18  jz      short loc_180006C4E
0x180006c1a  mov     rdx, [r14+20h]; pvData
0x180006c1e  mov     rax, r15
0x180006c21  inc     rax
0x180006c24  cmp     [rdx+rax*2], di
0x180006c28  jnz     short loc_180006C21
0x180006c2a  lea     r8d, ds:2[rax*2]; cbData
0x180006c32  mov     rcx, cs:DhcpGlobalClientTable
0x180006c39  mov     ecx, [rcx+48h]; columnid
0x180006c3c  call    DhcpJetSetValue
0x180006c41  mov     esi, eax
0x180006c43  test    eax, eax
0x180006c45  jnz     loc_1800070BE
0x180006c4b  mov     eax, [rbp+arg_8]
0x180006c4e  test    eax, eax
0x180006c50  jz      short loc_180006C5C
0x180006c52  cmp     [r14+28h], rdi
0x180006c56  jz      loc_180006D24
0x180006c5c  call    Feature_Servicing_DhcpClientInfoGetJetWarning__private_IsEnabledDeviceUsageNoInline
0x180006c61  mov     rdx, [r14+28h]; pvData
0x180006c65  test    eax, eax
0x180006c67  jz      loc_180006CED
0x180006c6d  test    rdx, rdx
0x180006c70  jnz     short loc_180006C84
0x180006c72  mov     ecx, edi
0x180006c74  jmp     short loc_180006C97
0x180006c76  mov     rdx, [r14+20h]
0x180006c7a  test    rdx, rdx
0x180006c7d  jnz     short loc_180006C1E
0x180006c7f  mov     r8d, edi
0x180006c82  jmp     short loc_180006C32
0x180006c84  mov     rax, r15
0x180006c87  inc     rax
0x180006c8a  cmp     [rdx+rax*2], di
0x180006c8e  jnz     short loc_180006C87
0x180006c90  lea     ecx, ds:2[rax*2]
0x180006c97  mov     rax, cs:DhcpGlobalClientTable
0x180006c9e  mov     r9, rdx; pvData
0x180006ca1  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180006ca8  mov     [rsp+60h+psetinfo], rdi; psetinfo
0x180006cad  mov     [rsp+60h+grbit], edi; grbit
0x180006cb1  mov     r8d, [rax+38h]; columnid
0x180006cb5  mov     [rsp+60h+cbData], ecx; cbData
0x180006cb9  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180006cc0  call    cs:__imp_JetSetColumn
0x180006cc7  nop     dword ptr [rax+rax+00h]
0x180006ccc  mov     ecx, eax
0x180006cce  lea     rdx, aJetsetvalueSet; "JetSetValue:Setcolumn"
0x180006cd5  mov     ebx, eax
0x180006cd7  call    DhcpMapJetError
0x180006cdc  mov     esi, eax
0x180006cde  cmp     ebx, 5E8h
0x180006ce4  jnz     short loc_180006D1C
0x180006ce6  mov     esi, 4E2Dh
0x180006ceb  jmp     short loc_180006D1C
0x180006ced  test    rdx, rdx
0x180006cf0  jnz     short loc_180006CF7
0x180006cf2  mov     r8d, edi
0x180006cf5  jmp     short loc_180006D0B
0x180006cf7  mov     rax, r15
0x180006cfa  inc     rax
0x180006cfd  cmp     [rdx+rax*2], di
0x180006d01  jnz     short loc_180006CFA
0x180006d03  lea     r8d, ds:2[rax*2]; cbData
0x180006d0b  mov     rcx, cs:DhcpGlobalClientTable
0x180006d12  mov     ecx, [rcx+38h]; columnid
0x180006d15  call    DhcpJetSetValue
0x180006d1a  mov     esi, eax
0x180006d1c  test    esi, esi
0x180006d1e  jnz     loc_1800070BE
0x180006d24  cmp     [r14+14h], edi
0x180006d28  jz      short loc_180006D50
0x180006d2a  cmp     [r14+18h], edi
0x180006d2e  jz      short loc_180006D50
0x180006d30  mov     edx, [r14]
0x180006d33  mov     rcx, cs:DhcpGlobalThisServer
0x180006d3a  call    MemServerIsReservedAddress
0x180006d3f  test    eax, eax
0x180006d41  jz      short loc_180006D50
0x180006d43  or      dword ptr [rbp+var_10], 0FFFFFFFFh
0x180006d47  mov     dword ptr [rbp+var_10+4], 7FFFFFFFh
0x180006d4e  jmp     short loc_180006D58
0x180006d50  mov     rax, [r14+14h]
0x180006d54  mov     [rbp+var_10], rax
0x180006d58  mov     rcx, cs:DhcpGlobalClientTable
0x180006d5f  lea     rdx, [rbp+var_10]; pvData
0x180006d63  mov     r8d, 8; cbData
0x180006d69  mov     ecx, [rcx+58h]; columnid
0x180006d6c  call    DhcpJetSetValue
0x180006d71  mov     esi, eax
0x180006d73  test    eax, eax
0x180006d75  jnz     loc_1800070BE
0x180006d7b  lea     ebx, [rax+4]
0x180006d7e  jmp     loc_180006E3E
0x180006d83  mov     ebx, r15d
0x180006d86  mov     rdx, r14; pvData
0x180006d89  mov     r8d, ebx; cbData
0x180006d8c  call    DhcpJetSetValue
0x180006d91  mov     esi, eax
0x180006d93  test    eax, eax
0x180006d95  jnz     loc_1800070BE
0x180006d9b  mov     ecx, 438h
0x180006da0  call    GetString
0x180006da5  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006da9  mov     r8, r15
0x180006dac  inc     r8
0x180006daf  cmp     [rax+r8*2], di
0x180006db4  jnz     short loc_180006DAC
0x180006db6  mov     rcx, cs:DhcpGlobalClientTable
0x180006dbd  lea     r8d, ds:2[r8*2]; cbData
0x180006dc5  mov     rdx, rax; pvData
0x180006dc8  mov     ecx, [rcx+48h]; columnid
0x180006dcb  call    DhcpJetSetValue
0x180006dd0  mov     esi, eax
0x180006dd2  test    eax, eax
0x180006dd4  jnz     loc_1800070BE
0x180006dda  mov     ecx, 439h
0x180006ddf  call    GetString
0x180006de4  mov     r8, r15
0x180006de7  inc     r8
0x180006dea  cmp     [rax+r8*2], di
0x180006def  jnz     short loc_180006DE7
0x180006df1  mov     rcx, cs:DhcpGlobalClientTable
0x180006df8  lea     r8d, ds:2[r8*2]; cbData
0x180006e00  mov     rdx, rax; pvData
0x180006e03  mov     ecx, [rcx+38h]; columnid
0x180006e06  call    DhcpJetSetValue
0x180006e0b  mov     esi, eax
0x180006e0d  test    eax, eax
0x180006e0f  jnz     loc_1800070BE
0x180006e15  mov     rcx, cs:DhcpGlobalClientTable
0x180006e1c  lea     r8d, [rsi+8]; cbData
0x180006e20  mov     rax, [r14+14h]
0x180006e24  lea     rdx, [rbp+var_10]; pvData
0x180006e28  mov     [rbp+var_10], rax
0x180006e2c  mov     ecx, [rcx+58h]; columnid
0x180006e2f  call    DhcpJetSetValue
0x180006e34  mov     esi, eax
0x180006e36  test    eax, eax
0x180006e38  jnz     loc_1800070BE
0x180006e3e  mov     rcx, cs:DhcpGlobalClientTable
0x180006e45  lea     rdx, DhcpGlobalServerName; pvData
0x180006e4c  mov     r8d, cs:DhcpGlobalServerNameLen; cbData
0x180006e53  mov     ecx, [rcx+88h]; columnid
0x180006e59  call    DhcpJetSetValue
0x180006e5e  mov     esi, eax
0x180006e60  test    eax, eax
0x180006e62  jnz     loc_1800070BE
0x180006e68  mov     rcx, cs:DhcpGlobalClientTable
0x180006e6f  lea     rdx, [r14+34h]; pvData
0x180006e73  mov     r8d, ebx; cbData
0x180006e76  mov     ecx, [rcx+78h]; columnid
0x180006e79  call    DhcpJetSetValue
0x180006e7e  mov     esi, eax
0x180006e80  test    eax, eax
0x180006e82  jnz     loc_1800070BE
0x180006e88  mov     rcx, cs:DhcpGlobalClientTable
0x180006e8f  lea     rdx, [r14+30h]; pvData
0x180006e93  lea     r8d, [rax+1]; cbData
0x180006e97  mov     ecx, [rcx+98h]; columnid
0x180006e9d  call    DhcpJetSetValue
0x180006ea2  mov     esi, eax
0x180006ea4  test    eax, eax
0x180006ea6  jnz     loc_1800070BE
0x180006eac  mov     rcx, cs:DhcpGlobalClientTable
0x180006eb3  lea     rdx, [r14+39h]; pvData
0x180006eb7  lea     r8d, [rax+1]; cbData
0x180006ebb  mov     ecx, [rcx+0A8h]; columnid
0x180006ec1  call    DhcpJetSetValue
0x180006ec6  mov     esi, eax
0x180006ec8  test    eax, eax
0x180006eca  jnz     loc_1800070BE
0x180006ed0  mov     rcx, cs:DhcpGlobalClientTable
0x180006ed7  lea     rdx, [r14+3Ch]; pvData
0x180006edb  lea     r8d, [rax+8]; cbData
0x180006edf  mov     ecx, [rcx+0B8h]; columnid
0x180006ee5  call    DhcpJetSetValue
0x180006eea  mov     esi, eax
0x180006eec  test    eax, eax
0x180006eee  jnz     loc_1800070BE
0x180006ef4  mov     rcx, cs:DhcpGlobalClientTable
0x180006efb  lea     rdx, [r14+44h]; pvData
0x180006eff  lea     r8d, [rax+1]; cbData
0x180006f03  mov     ecx, [rcx+0C8h]; columnid
0x180006f09  call    DhcpJetSetValue
0x180006f0e  mov     esi, eax
0x180006f10  test    eax, eax
0x180006f12  jnz     loc_1800070BE
0x180006f18  mov     rcx, cs:DhcpGlobalClientTable
0x180006f1f  lea     rdx, [r14+48h]; pvData
0x180006f23  mov     r8d, ebx; cbData
0x180006f26  mov     ecx, [rcx+0D8h]; columnid
0x180006f2c  call    DhcpJetSetValue
0x180006f31  mov     esi, eax
0x180006f33  test    eax, eax
0x180006f35  jnz     loc_1800070BE
0x180006f3b  test    r13d, r13d
0x180006f3e  jnz     short loc_180006F86
0x180006f40  mov     rcx, cs:DhcpGlobalClientTable
0x180006f47  lea     rdx, [r14+4Ch]; pvData
0x180006f4b  mov     r8d, ebx; cbData
0x180006f4e  mov     ecx, [rcx+0E8h]; columnid
0x180006f54  call    DhcpJetSetValue
0x180006f59  mov     esi, eax
0x180006f5b  test    eax, eax
  ... truncated ...
```
