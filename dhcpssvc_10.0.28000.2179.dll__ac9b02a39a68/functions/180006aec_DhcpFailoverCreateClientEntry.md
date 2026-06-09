# DhcpFailoverCreateClientEntry

- ea: `0x180006aec`
- end: `0x180007166`
- name: `DhcpFailoverCreateClientEntry`
- size: `1658`
- prototype: `__int64 __fastcall(void *pvData)`
- caller_count: `3`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006808`
- `0x180058c00`
- `0x18005a9ec`

## callees

- `0x180003c90`
- `0x180006aec`
- `0x18000e1a0`
- `0x18000e1d0`
- `0x18000e64c`
- `0x18000e78c`
- `0x18000e7c0`
- `0x18000e814`
- `0x180020608`
- `0x1800250e8`
- `0x180030ed4`
- `0x180098a40`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800070ec`
- `ESENT!JetUpdate` at `0x1800070ec`
- `ESENT!JetSetColumn` at `0x180006cd2`
- `ESENT!JetSetColumn` at `0x180006cd2`
- `KERNEL32!EnterCriticalSection` at `0x180006b27`
- `KERNEL32!EnterCriticalSection` at `0x180006b27`
- `KERNEL32!LeaveCriticalSection` at `0x180006d0b`
- `KERNEL32!LeaveCriticalSection` at `0x180006d0b`

## string_xrefs

- `0x180007109`: `CreateClientEntryVQ:JetUpdate`

## pseudocode

```c
__int64 __fastcall DhcpFailoverCreateClientEntry(char *pvData, int a2, int a3, int a4)
{
  char *v4; // rbx
  char v6; // r12
  unsigned int v7; // esi
  int v10; // edi
  __int64 v11; // r8
  JET_COLUMNID v12; // ecx
  int v13; // eax
  __int64 v14; // r15
  _WORD *v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // r8d
  const void *v18; // r9
  __int64 v19; // rax
  unsigned int cbData; // eax
  __int64 v21; // rbx
  int v22; // eax
  _WORD *String; // rax
  __int64 v25; // r8
  _WORD *v26; // rax
  __int64 v27; // r8
  _WORD *v28; // rdx
  unsigned int v29; // r8d
  unsigned int v30; // eax
  int v31; // eax
  __int64 v32; // r8
  _QWORD v33[2]; // [rsp+50h] [rbp-10h] BYREF
  int pvDataa; // [rsp+A0h] [rbp+40h] BYREF
  int v35; // [rsp+A8h] [rbp+48h] BYREF

  v35 = a2;
  v4 = pvData + 56;
  v6 = pvData[56];
  v7 = 0;
  pvDataa = 0;
  v33[0] = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v10 = DhcpJetBeginTransaction();
  if ( v10 )
    goto LABEL_24;
  DhcpDoDynDnsCreateEntryWork(
    pvData,
    *((_QWORD *)pvData + 4),
    v4,
    &v35,
    v6 == 2,
    *((_DWORD *)pvData + 4),
    *((_QWORD *)pvData + 1),
    a4,
    *((_DWORD *)pvData + 29) & 1);
  v10 = DhcpJetPrepareUpdate(*(_QWORD *)DhcpGlobalClientTable, pvData, v11, v35 == 0);
  if ( v10 )
    goto LABEL_24;
  if ( !v35 )
  {
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 8), pvData, 4u);
    if ( v10 )
      goto LABEL_24;
  }
  pvDataa = DhcpGetSubnetMaskForAddress(*(unsigned int *)pvData);
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 104), &pvDataa, 4u);
  if ( v10 )
    goto LABEL_24;
  DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), v4, 1u);
  v12 = *(_DWORD *)(DhcpGlobalClientTable + 24);
  if ( v6 != 2 )
  {
    v10 = DhcpJetSetValue(v12, *((void **)pvData + 1), *((_DWORD *)pvData + 4));
    if ( v10 )
      goto LABEL_24;
    v13 = v35;
    v14 = -1;
    if ( v35 )
    {
      if ( !*((_QWORD *)pvData + 4) )
        goto LABEL_16;
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
      v13 = v35;
LABEL_16:
      if ( v13 )
      {
        if ( !*((_QWORD *)pvData + 5) )
        {
LABEL_32:
          if ( *((_DWORD *)pvData + 5)
            && *((_DWORD *)pvData + 6)
            && (unsigned int)MemServerIsReservedAddress(DhcpGlobalThisServer, *(unsigned int *)pvData) )
          {
            v33[0] = 0x7FFFFFFFFFFFFFFFLL;
          }
          else
          {
            v33[0] = *(_QWORD *)(pvData + 20);
          }
          v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), v33, 8u);
          if ( v10 )
            goto LABEL_24;
          goto LABEL_47;
        }
        v18 = (const void *)*((_QWORD *)pvData + 5);
      }
      else
      {
        v18 = (const void *)*((_QWORD *)pvData + 5);
        if ( !v18 )
        {
          cbData = 0;
LABEL_22:
          v21 = (unsigned int)JetSetColumn(
                                DhcpGlobalJetServerSession,
                                DhcpGlobalClientTableHandle,
                                *(_DWORD *)(DhcpGlobalClientTable + 56),
                                v18,
                                cbData,
                                0,
                                0);
          v22 = DhcpMapJetError(v21, "JetSetValue:Setcolumn");
          v10 = v22;
          if ( (_DWORD)v21 == 1512 )
          {
            v10 = 20013;
            goto LABEL_24;
          }
          if ( v22 )
            goto LABEL_24;
          goto LABEL_32;
        }
      }
      v19 = -1;
      do
        ++v19;
      while ( *((_WORD *)v18 + v19) );
      cbData = 2 * v19 + 2;
      goto LABEL_22;
    }
LABEL_24:
    DhcpJetRollBack();
    goto LABEL_25;
  }
  v10 = DhcpJetSetValue(v12, pvData, 4u);
  if ( v10 )
    goto LABEL_24;
  String = (_WORD *)GetString(1080);
  v14 = -1;
  v25 = -1;
  do
    ++v25;
  while ( String[v25] );
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), String, 2 * (int)v25 + 2);
  if ( v10 )
    goto LABEL_24;
  v26 = (_WORD *)GetString(1081);
  v27 = -1;
  do
    ++v27;
  while ( v26[v27] );
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 56), v26, 2 * (int)v27 + 2);
  if ( v10 )
    goto LABEL_24;
  v33[0] = *(_QWORD *)(pvData + 20);
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 88), v33, 8u);
  if ( v10 )
    goto LABEL_24;
LABEL_47:
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 136), &DhcpGlobalServerName, DhcpGlobalServerNameLen);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 120), pvData + 52, 4u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 152), pvData + 48, 1u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 168), pvData + 57, 1u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 184), pvData + 60, 8u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 200), pvData + 68, 1u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 216), pvData + 72, 4u);
  if ( v10 )
    goto LABEL_24;
  if ( !a3 )
  {
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 232), pvData + 76, 4u);
    if ( v10 )
      goto LABEL_24;
    v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 248), pvData + 80, 4u);
    if ( v10 )
      goto LABEL_24;
  }
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 264), pvData + 84, 4u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 280), pvData + 88, 4u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 296), pvData + 92, 4u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 312), pvData + 112, 1u);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 328), pvData + 96, 4u);
  if ( v10 )
    goto LABEL_24;
  v28 = (_WORD *)*((_QWORD *)pvData + 13);
  if ( v28 )
  {
    do
      ++v14;
    while ( v28[v14] );
    v29 = 2 * v14 + 2;
  }
  else
  {
    v29 = 0;
  }
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 344), v28, v29);
  if ( v10 )
    goto LABEL_24;
  v10 = DhcpJetSetValue(*(_DWORD *)(DhcpGlobalClientTable + 360), pvData + 116, 4u);
  if ( v10 )
    goto LABEL_24;
  v30 = JetUpdate(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle, 0, 0, 0);
  if ( v30 == -1605 )
  {
    v10 = 20014;
    goto LABEL_24;
  }
  v10 = DhcpMapJetError(v30, "CreateClientEntryVQ:JetUpdate");
  if ( v10 )
    goto LABEL_24;
  DhcpJetCommitTransaction();
  if ( v6 == 2 )
  {
    GetString(1080);
    v31 = GetString(1074);
    DhcpUpdateAuditLog(v10 + 13, v31, *(_DWORD *)pvData, 0, 0, v32);
    goto LABEL_26;
  }
LABEL_25:
  v7 = v10;
LABEL_26:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return v7;
}

```

## disassembly

```asm
0x180006aec  mov     [rsp-38h+arg_10], rbx
0x180006af1  mov     [rsp-38h+arg_8], edx
0x180006af5  push    rbp
0x180006af6  push    rsi
0x180006af7  push    rdi
0x180006af8  push    r12
0x180006afa  push    r13
0x180006afc  push    r14
0x180006afe  push    r15
0x180006b00  mov     rbp, rsp
0x180006b03  sub     rsp, 60h
0x180006b07  lea     rbx, [rcx+38h]
0x180006b0b  mov     r14, rcx
0x180006b0e  mov     r12b, [rbx]
0x180006b11  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180006b18  xor     esi, esi
0x180006b1a  mov     r15d, r9d
0x180006b1d  mov     [rbp+pvData], esi
0x180006b20  mov     r13d, r8d
0x180006b23  mov     [rbp+var_10], rsi
0x180006b27  call    cs:__imp_EnterCriticalSection
0x180006b2e  nop     dword ptr [rax+rax+00h]
0x180006b33  call    DhcpJetBeginTransaction
0x180006b38  mov     edi, eax
0x180006b3a  test    eax, eax
0x180006b3c  jnz     loc_180006CFD
0x180006b42  mov     eax, [r14+74h]
0x180006b46  lea     r9, [rbp+arg_8]
0x180006b4a  mov     rdx, [r14+20h]
0x180006b4e  and     eax, 1
0x180006b51  mov     [rsp+60h+var_20], eax
0x180006b55  mov     ecx, esi
0x180006b57  mov     rax, [r14+8]
0x180006b5b  cmp     r12b, 2
0x180006b5f  mov     [rsp+60h+var_28], r15d
0x180006b64  mov     r8, rbx
0x180006b67  mov     [rsp+60h+psetinfo], rax
0x180006b6c  setz    cl
0x180006b6f  mov     eax, [r14+10h]
0x180006b73  mov     [rsp+60h+grbit], eax
0x180006b77  mov     [rsp+60h+cbData], ecx
0x180006b7b  mov     rcx, r14
0x180006b7e  call    DhcpDoDynDnsCreateEntryWork
0x180006b83  mov     rcx, cs:DhcpGlobalClientTable
0x180006b8a  mov     r9d, esi
0x180006b8d  cmp     [rbp+arg_8], esi
0x180006b90  mov     rdx, r14
0x180006b93  setz    r9b
0x180006b97  mov     rcx, [rcx]
0x180006b9a  call    DhcpJetPrepareUpdate
0x180006b9f  mov     edi, eax
0x180006ba1  test    eax, eax
0x180006ba3  jnz     loc_180006CFD
0x180006ba9  lea     r15d, [rsi+4]
0x180006bad  cmp     [rbp+arg_8], esi
0x180006bb0  jnz     short loc_180006BD1
0x180006bb2  mov     rcx, cs:DhcpGlobalClientTable
0x180006bb9  mov     r8d, r15d; cbData
0x180006bbc  mov     rdx, r14; pvData
0x180006bbf  mov     ecx, [rcx+8]; columnid
0x180006bc2  call    DhcpJetSetValue
0x180006bc7  mov     edi, eax
0x180006bc9  test    eax, eax
0x180006bcb  jnz     loc_180006CFD
0x180006bd1  mov     ecx, [r14]
0x180006bd4  call    DhcpGetSubnetMaskForAddress
0x180006bd9  mov     rcx, cs:DhcpGlobalClientTable
0x180006be0  lea     rdx, [rbp+pvData]; pvData
0x180006be4  mov     [rbp+pvData], eax
0x180006be7  mov     r8d, r15d; cbData
0x180006bea  mov     ecx, [rcx+68h]; columnid
0x180006bed  call    DhcpJetSetValue
0x180006bf2  mov     edi, eax
0x180006bf4  test    eax, eax
0x180006bf6  jnz     loc_180006CFD
0x180006bfc  mov     rcx, cs:DhcpGlobalClientTable
0x180006c03  lea     r8d, [rax+1]; cbData
0x180006c07  mov     rdx, rbx; pvData
0x180006c0a  mov     ecx, [rcx+28h]; columnid
0x180006c0d  call    DhcpJetSetValue
0x180006c12  mov     rcx, cs:DhcpGlobalClientTable
0x180006c19  mov     ecx, [rcx+18h]; columnid
0x180006c1c  cmp     r12b, 2
0x180006c20  jz      loc_180006DC1
0x180006c26  mov     r8d, [r14+10h]; cbData
0x180006c2a  mov     rdx, [r14+8]; pvData
0x180006c2e  call    DhcpJetSetValue
0x180006c33  mov     edi, eax
0x180006c35  test    eax, eax
0x180006c37  jnz     loc_180006CFD
0x180006c3d  mov     eax, [rbp+arg_8]
0x180006c40  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006c44  test    eax, eax
0x180006c46  jz      loc_180006D32
0x180006c4c  cmp     [r14+20h], rsi
0x180006c50  jz      short loc_180006C82
0x180006c52  mov     rdx, [r14+20h]; pvData
0x180006c56  mov     rax, r15
0x180006c59  inc     rax
0x180006c5c  cmp     [rdx+rax*2], si
0x180006c60  jnz     short loc_180006C59
0x180006c62  lea     r8d, ds:2[rax*2]; cbData
0x180006c6a  mov     rcx, cs:DhcpGlobalClientTable
0x180006c71  mov     ecx, [rcx+48h]; columnid
0x180006c74  call    DhcpJetSetValue
0x180006c79  mov     edi, eax
0x180006c7b  test    eax, eax
0x180006c7d  jnz     short loc_180006CFD
0x180006c7f  mov     eax, [rbp+arg_8]
0x180006c82  test    eax, eax
0x180006c84  jz      loc_180006D47
0x180006c8a  cmp     [r14+28h], rsi
0x180006c8e  jz      loc_180006D5F
0x180006c94  mov     r9, [r14+28h]; pvData
0x180006c98  mov     rax, r15
0x180006c9b  inc     rax
0x180006c9e  cmp     [r9+rax*2], si
0x180006ca3  jnz     short loc_180006C9B
0x180006ca5  lea     eax, ds:2[rax*2]
0x180006cac  mov     r8, cs:DhcpGlobalClientTable
0x180006cb3  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x180006cba  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x180006cc1  mov     [rsp+60h+psetinfo], rsi; psetinfo
0x180006cc6  mov     r8d, [r8+38h]; columnid
0x180006cca  mov     [rsp+60h+grbit], esi; grbit
0x180006cce  mov     [rsp+60h+cbData], eax; cbData
0x180006cd2  call    cs:__imp_JetSetColumn
0x180006cd9  nop     dword ptr [rax+rax+00h]
0x180006cde  mov     ecx, eax
0x180006ce0  lea     rdx, aJetsetvalueSet; "JetSetValue:Setcolumn"
0x180006ce7  mov     ebx, eax
0x180006ce9  call    DhcpMapJetError
0x180006cee  mov     edi, eax
0x180006cf0  cmp     ebx, 5E8h
0x180006cf6  jnz     short loc_180006D5B
0x180006cf8  mov     edi, 4E2Dh
0x180006cfd  call    DhcpJetRollBack
0x180006d02  mov     esi, edi
0x180006d04  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180006d0b  call    cs:__imp_LeaveCriticalSection
0x180006d12  nop     dword ptr [rax+rax+00h]
0x180006d17  mov     rbx, [rsp+60h+arg_10]
0x180006d1f  mov     eax, esi
0x180006d21  add     rsp, 60h
0x180006d25  pop     r15
0x180006d27  pop     r14
0x180006d29  pop     r13
0x180006d2b  pop     r12
0x180006d2d  pop     rdi
0x180006d2e  pop     rsi
0x180006d2f  pop     rbp
0x180006d30  retn
0x180006d32  mov     rdx, [r14+20h]
0x180006d36  test    rdx, rdx
0x180006d39  jnz     loc_180006C56
0x180006d3f  mov     r8d, esi
0x180006d42  jmp     loc_180006C6A
0x180006d47  mov     r9, [r14+28h]
0x180006d4b  test    r9, r9
0x180006d4e  jnz     loc_180006C98
0x180006d54  mov     eax, esi
0x180006d56  jmp     loc_180006CAC
0x180006d5b  test    eax, eax
0x180006d5d  jnz     short loc_180006CFD
0x180006d5f  cmp     [r14+14h], esi
0x180006d63  jz      short loc_180006D8E
0x180006d65  cmp     [r14+18h], esi
0x180006d69  jz      short loc_180006D8E
0x180006d6b  mov     edx, [r14]
0x180006d6e  mov     rcx, cs:DhcpGlobalThisServer
0x180006d75  call    MemServerIsReservedAddress
0x180006d7a  test    eax, eax
0x180006d7c  jz      short loc_180006D8E
0x180006d7e  mov     dword ptr [rbp+var_10], 0FFFFFFFFh
0x180006d85  mov     dword ptr [rbp+var_10+4], 7FFFFFFFh
0x180006d8c  jmp     short loc_180006D96
0x180006d8e  mov     rax, [r14+14h]
0x180006d92  mov     [rbp+var_10], rax
0x180006d96  mov     rcx, cs:DhcpGlobalClientTable
0x180006d9d  lea     rdx, [rbp+var_10]; pvData
0x180006da1  mov     r8d, 8; cbData
0x180006da7  mov     ecx, [rcx+58h]; columnid
0x180006daa  call    DhcpJetSetValue
0x180006daf  mov     edi, eax
0x180006db1  test    eax, eax
0x180006db3  jnz     loc_180006CFD
0x180006db9  lea     ebx, [rax+4]
0x180006dbc  jmp     loc_180006E7C
0x180006dc1  mov     ebx, r15d
0x180006dc4  mov     rdx, r14; pvData
0x180006dc7  mov     r8d, ebx; cbData
0x180006dca  call    DhcpJetSetValue
0x180006dcf  mov     edi, eax
0x180006dd1  test    eax, eax
0x180006dd3  jnz     loc_180006CFD
0x180006dd9  mov     ecx, 438h
0x180006dde  call    GetString
0x180006de3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006de7  mov     r8, r15
0x180006dea  inc     r8
0x180006ded  cmp     [rax+r8*2], si
0x180006df2  jnz     short loc_180006DEA
0x180006df4  mov     rcx, cs:DhcpGlobalClientTable
0x180006dfb  lea     r8d, ds:2[r8*2]; cbData
0x180006e03  mov     rdx, rax; pvData
0x180006e06  mov     ecx, [rcx+48h]; columnid
0x180006e09  call    DhcpJetSetValue
0x180006e0e  mov     edi, eax
0x180006e10  test    eax, eax
0x180006e12  jnz     loc_180006CFD
0x180006e18  mov     ecx, 439h
0x180006e1d  call    GetString
0x180006e22  mov     r8, r15
0x180006e25  inc     r8
0x180006e28  cmp     [rax+r8*2], si
0x180006e2d  jnz     short loc_180006E25
0x180006e2f  mov     rcx, cs:DhcpGlobalClientTable
0x180006e36  lea     r8d, ds:2[r8*2]; cbData
0x180006e3e  mov     rdx, rax; pvData
0x180006e41  mov     ecx, [rcx+38h]; columnid
0x180006e44  call    DhcpJetSetValue
0x180006e49  mov     edi, eax
0x180006e4b  test    eax, eax
0x180006e4d  jnz     loc_180006CFD
0x180006e53  mov     rcx, cs:DhcpGlobalClientTable
0x180006e5a  lea     r8d, [rdi+8]; cbData
0x180006e5e  mov     rax, [r14+14h]
0x180006e62  lea     rdx, [rbp+var_10]; pvData
0x180006e66  mov     [rbp+var_10], rax
0x180006e6a  mov     ecx, [rcx+58h]; columnid
0x180006e6d  call    DhcpJetSetValue
0x180006e72  mov     edi, eax
0x180006e74  test    eax, eax
0x180006e76  jnz     loc_180006CFD
0x180006e7c  mov     rcx, cs:DhcpGlobalClientTable
0x180006e83  lea     rdx, DhcpGlobalServerName; pvData
0x180006e8a  mov     r8d, cs:DhcpGlobalServerNameLen; cbData
0x180006e91  mov     ecx, [rcx+88h]; columnid
0x180006e97  call    DhcpJetSetValue
0x180006e9c  mov     edi, eax
0x180006e9e  test    eax, eax
0x180006ea0  jnz     loc_180006CFD
0x180006ea6  mov     rcx, cs:DhcpGlobalClientTable
0x180006ead  lea     rdx, [r14+34h]; pvData
0x180006eb1  mov     r8d, ebx; cbData
0x180006eb4  mov     ecx, [rcx+78h]; columnid
0x180006eb7  call    DhcpJetSetValue
0x180006ebc  mov     edi, eax
0x180006ebe  test    eax, eax
0x180006ec0  jnz     loc_180006CFD
0x180006ec6  mov     rcx, cs:DhcpGlobalClientTable
0x180006ecd  lea     rdx, [r14+30h]; pvData
0x180006ed1  lea     r8d, [rax+1]; cbData
0x180006ed5  mov     ecx, [rcx+98h]; columnid
0x180006edb  call    DhcpJetSetValue
0x180006ee0  mov     edi, eax
0x180006ee2  test    eax, eax
0x180006ee4  jnz     loc_180006CFD
0x180006eea  mov     rcx, cs:DhcpGlobalClientTable
0x180006ef1  lea     rdx, [r14+39h]; pvData
0x180006ef5  lea     r8d, [rax+1]; cbData
0x180006ef9  mov     ecx, [rcx+0A8h]; columnid
0x180006eff  call    DhcpJetSetValue
0x180006f04  mov     edi, eax
0x180006f06  test    eax, eax
0x180006f08  jnz     loc_180006CFD
0x180006f0e  mov     rcx, cs:DhcpGlobalClientTable
0x180006f15  lea     rdx, [r14+3Ch]; pvData
0x180006f19  lea     r8d, [rax+8]; cbData
0x180006f1d  mov     ecx, [rcx+0B8h]; columnid
0x180006f23  call    DhcpJetSetValue
0x180006f28  mov     edi, eax
0x180006f2a  test    eax, eax
0x180006f2c  jnz     loc_180006CFD
0x180006f32  mov     rcx, cs:DhcpGlobalClientTable
0x180006f39  lea     rdx, [r14+44h]; pvData
0x180006f3d  lea     r8d, [rax+1]; cbData
0x180006f41  mov     ecx, [rcx+0C8h]; columnid
0x180006f47  call    DhcpJetSetValue
0x180006f4c  mov     edi, eax
0x180006f4e  test    eax, eax
0x180006f50  jnz     loc_180006CFD
0x180006f56  mov     rcx, cs:DhcpGlobalClientTable
0x180006f5d  lea     rdx, [r14+48h]; pvData
0x180006f61  mov     r8d, ebx; cbData
0x180006f64  mov     ecx, [rcx+0D8h]; columnid
0x180006f6a  call    DhcpJetSetValue
0x180006f6f  mov     edi, eax
0x180006f71  test    eax, eax
0x180006f73  jnz     loc_180006CFD
0x180006f79  test    r13d, r13d
0x180006f7c  jnz     short loc_180006FC4
0x180006f7e  mov     rcx, cs:DhcpGlobalClientTable
0x180006f85  lea     rdx, [r14+4Ch]; pvData
0x180006f89  mov     r8d, ebx; cbData
0x180006f8c  mov     ecx, [rcx+0E8h]; columnid
0x180006f92  call    DhcpJetSetValue
0x180006f97  mov     edi, eax
0x180006f99  test    eax, eax
0x180006f9b  jnz     loc_180006CFD
  ... truncated ...
```
