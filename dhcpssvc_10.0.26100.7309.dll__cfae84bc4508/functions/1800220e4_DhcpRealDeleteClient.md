# DhcpRealDeleteClient

- ea: `0x1800220e4`
- end: `0x1800225a3`
- name: `DhcpRealDeleteClient`
- size: `1215`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020160`
- `0x180020964`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800058cc`
- `0x18000d97c`
- `0x18000eaf4`
- `0x18000eb24`
- `0x18000ebd4`
- `0x18000ed88`
- `0x18000f0c4`
- `0x1800220e4`
- `0x180022b6c`
- `0x180022e88`
- `0x180092f64`
- `0x1800930bc`

## import_xrefs

- `ESENT!JetDelete` at `0x1800224df`
- `ESENT!JetDelete` at `0x1800224df`
- `WS2_32!__imp_inet_ntoa` at `0x18002213b`
- `WS2_32!__imp_inet_ntoa` at `0x180022230`
- `WS2_32!__imp_inet_ntoa` at `0x1800222ad`
- `WS2_32!__imp_inet_ntoa` at `0x180022366`
- `WS2_32!__imp_inet_ntoa` at `0x18002213b`
- `WS2_32!__imp_inet_ntoa` at `0x180022230`
- `WS2_32!__imp_inet_ntoa` at `0x1800222ad`
- `WS2_32!__imp_inet_ntoa` at `0x180022366`
- `KERNEL32!EnterCriticalSection` at `0x18002217b`
- `KERNEL32!EnterCriticalSection` at `0x18002217b`
- `KERNEL32!LeaveCriticalSection` at `0x180022199`
- `KERNEL32!LeaveCriticalSection` at `0x180022569`
- `KERNEL32!LeaveCriticalSection` at `0x180022199`
- `KERNEL32!LeaveCriticalSection` at `0x180022569`
- `KERNEL32!HeapFree` at `0x180022587`
- `KERNEL32!HeapFree` at `0x180022587`

## pseudocode

```c
void __fastcall DhcpRealDeleteClient(struct in_addr a1, const wchar_t *a2, char a3)
{
  const wchar_t *v3; // rsi
  const wchar_t *v5; // r12
  const wchar_t *v6; // rbx
  unsigned int v7; // eax
  int v8; // r8d
  char v9; // r15
  unsigned int v10; // ebx
  unsigned int Value; // ebx
  _QWORD *v12; // rcx
  char *v13; // rax
  int v14; // r8d
  int v15; // edx
  _BYTE *v16; // r10
  _BYTE *v17; // rcx
  unsigned int v18; // eax
  const size_t *v19; // rdx
  signed __int64 v20; // rdx
  int v21; // r8d
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r9
  unsigned int v27; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-10h] BYREF
  __int64 v29; // [rsp+38h] [rbp-8h] BYREF
  struct in_addr in; // [rsp+80h] [rbp+40h] BYREF
  __int64 pvData; // [rsp+90h] [rbp+50h] BYREF
  unsigned int pcbActual; // [rsp+98h] [rbp+58h] BYREF

  in = a1;
  lpMem = 0;
  v3 = a2;
  v29 = 0;
  LOBYTE(pvData) = 0;
  v5 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    v6 = a2;
    if ( !a2 )
      v6 = L"NULL";
    v7 = (unsigned int)inet_ntoa(a1);
    WPP_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, v8, v7, (__int64)v6, a3);
  }
  v9 = a3 & 3;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v10 = DhcpJetBeginTransaction();
  if ( v10 )
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v10);
    return;
  }
  pcbActual = 4;
  Value = DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &in, 4);
  if ( Value )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = inet_ntoa(in);
        v15 = 50;
LABEL_14:
        if ( !v3 )
          v3 = L"NULL";
        WPP_SF_Ss(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v14, (_DWORD)v3, (__int64)v13);
        goto LABEL_63;
      }
      goto LABEL_64;
    }
    goto LABEL_67;
  }
  pcbActual = 1;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 40), &pvData, &pcbActual);
  if ( Value )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = inet_ntoa(in);
        v15 = 51;
        goto LABEL_14;
      }
LABEL_64:
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
        WPP_SF_D(v12[2], 60, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, Value);
    }
LABEL_67:
    DhcpJetRollBack();
    goto LABEL_73;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids,
      (unsigned __int8)pvData);
    v16 = WPP_GLOBAL_Control;
  }
  if ( (pvData & 0xC0) != 0xC0 || v9 != (pvData & 3) )
  {
    if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || (v16[28] & 0x10) == 0 )
      goto LABEL_72;
    v23 = *((_QWORD *)v16 + 2);
    v24 = 53;
LABEL_71:
    WPP_SF_(v23, v24, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
    goto LABEL_72;
  }
  pcbActual = 0;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, &pcbActual);
  if ( Value )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v13 = inet_ntoa(in);
        v15 = 54;
        goto LABEL_14;
      }
      goto LABEL_64;
    }
    goto LABEL_67;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    if ( lpMem )
      v5 = (const wchar_t *)lpMem;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v5);
    v17 = WPP_GLOBAL_Control;
  }
  if ( !v3 )
  {
    if ( lpMem )
      goto LABEL_72;
    goto LABEL_37;
  }
  v19 = &Annotation;
  if ( lpMem )
    v19 = (const size_t *)lpMem;
  v20 = (char *)v19 - (char *)v3;
  do
  {
    v21 = *(const wchar_t *)((char *)v3 + v20);
    v22 = *v3 - v21;
    if ( v22 )
      break;
    ++v3;
  }
  while ( v21 );
  if ( v22 )
  {
    if ( v17 == (_BYTE *)&WPP_GLOBAL_Control || (v17[28] & 0x10) == 0 )
      goto LABEL_72;
    v23 = *((_QWORD *)v17 + 2);
    v24 = 56;
    goto LABEL_71;
  }
LABEL_37:
  if ( (in.S_un.S_addr & 0xF0000000) == 0xE0000000 )
    v18 = ((__int64 (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int64, __int64))MemServerGetMAddressInfo)(
            (_DWORD)DhcpGlobalThisServer,
            in,
            (unsigned int)&v29,
            0,
            0,
            0);
  else
    v18 = ((__int64 (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int64, __int64))MemServerGetUAddressInfo)(
            (_DWORD)DhcpGlobalThisServer,
            in,
            (unsigned int)&v29,
            0,
            0,
            0);
  Value = v18;
  if ( v18 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_67;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_64;
    v25 = 57;
    v26 = v18;
    goto LABEL_53;
  }
  if ( *(_DWORD *)(v29 + 4292) == 1 )
  {
    v27 = DhcpHandleFailoverRequest(v29, in.S_un.S_addr, 1, 0);
    Value = v27;
    if ( v27 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_67;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_64;
      v25 = 58;
      v26 = v27;
LABEL_53:
      WPP_SF_D(v12[2], v25, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids, v26);
      goto LABEL_63;
    }
  }
  else
  {
    Value = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
    if ( Value )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_67;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_64;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_5e79908d56a839214a8dcc812d846f36_Traceguids);
LABEL_63:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_64;
    }
  }
LABEL_72:
  DhcpJetCommitTransaction();
LABEL_73:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( lpMem )
    HeapFree(gDhcpHeap, 0, lpMem);
}

```

## disassembly

```asm
0x1800220e4  mov     dword ptr [rsp-38h+in.S_un], ecx
0x1800220e8  push    rbp
0x1800220e9  push    rbx
0x1800220ea  push    rsi
0x1800220eb  push    rdi
0x1800220ec  push    r12
0x1800220ee  push    r14
0x1800220f0  push    r15
0x1800220f2  mov     rbp, rsp
0x1800220f5  sub     rsp, 40h
0x1800220f9  and     [rbp+lpMem], 0
0x1800220fe  mov     rsi, rdx
0x180022101  and     [rbp+var_8], 0
0x180022106  movzx   r15d, r8b
0x18002210a  mov     byte ptr [rbp+pvData], 0
0x18002210e  mov     rax, cs:WPP_GLOBAL_Control
0x180022115  lea     rdi, WPP_GLOBAL_Control
0x18002211c  lea     r12, aNull_0; "NULL"
0x180022123  cmp     rax, rdi
0x180022126  jz      short loc_180022170
0x180022128  test    dword ptr [rax+1Ch], 40000h
0x18002212f  jz      short loc_180022170
0x180022131  test    rdx, rdx
0x180022134  mov     rbx, rdx
0x180022137  cmovz   rbx, r12
0x18002213b  call    cs:__imp_inet_ntoa
0x180022142  nop     dword ptr [rax+rax+00h]
0x180022147  mov     rcx, cs:WPP_GLOBAL_Control
0x18002214e  mov     edx, 30h ; '0'
0x180022153  mov     r9, rax
0x180022156  mov     dword ptr [rsp+40h+var_18], r15d
0x18002215b  mov     [rsp+40h+var_20], rbx
0x180022160  mov     rcx, [rcx+10h]
0x180022164  call    WPP_SF_sSD
0x180022169  lea     rdi, WPP_GLOBAL_Control
0x180022170  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180022177  and     r15b, 3
0x18002217b  call    cs:__imp_EnterCriticalSection
0x180022182  nop     dword ptr [rax+rax+00h]
0x180022187  call    DhcpJetBeginTransaction
0x18002218c  mov     ebx, eax
0x18002218e  test    eax, eax
0x180022190  jz      short loc_1800221DF
0x180022192  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180022199  call    cs:__imp_LeaveCriticalSection
0x1800221a0  nop     dword ptr [rax+rax+00h]
0x1800221a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221ac  cmp     rcx, rdi
0x1800221af  jz      loc_180022593
0x1800221b5  mov     dil, 10h
0x1800221b8  test    [rcx+1Ch], dil
0x1800221bc  jz      loc_180022593
0x1800221c2  mov     rcx, [rcx+10h]
0x1800221c6  lea     r8, WPP_5e79908d56a839214a8dcc812d846f36_Traceguids
0x1800221cd  mov     edx, 31h ; '1'
0x1800221d2  mov     r9d, ebx
0x1800221d5  call    WPP_SF_D
0x1800221da  jmp     loc_180022593
0x1800221df  mov     rcx, cs:DhcpGlobalClientTable
0x1800221e6  lea     rdx, [rbp+in]
0x1800221ea  mov     r8d, 4
0x1800221f0  mov     [rbp+pcbActual], r8d
0x1800221f4  mov     rcx, [rcx]
0x1800221f7  call    DhcpJetOpenKey
0x1800221fc  lea     r14, WPP_5e79908d56a839214a8dcc812d846f36_Traceguids
0x180022203  mov     ebx, eax
0x180022205  mov     dil, 10h
0x180022208  test    eax, eax
0x18002220a  jz      short loc_180022265
0x18002220c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022213  lea     r15, WPP_GLOBAL_Control
0x18002221a  cmp     rcx, r15
0x18002221d  jz      loc_18002253A
0x180022223  test    [rcx+1Ch], dil
0x180022227  jz      loc_18002251B
0x18002222d  mov     ecx, dword ptr [rbp+in.S_un]; in
0x180022230  call    cs:__imp_inet_ntoa
0x180022237  nop     dword ptr [rax+rax+00h]
0x18002223c  mov     edx, 32h ; '2'
0x180022241  mov     rcx, cs:WPP_GLOBAL_Control
0x180022248  test    rsi, rsi
0x18002224b  mov     [rsp+40h+var_20], rax
0x180022250  cmovz   rsi, r12
0x180022254  mov     r9, rsi
0x180022257  mov     rcx, [rcx+10h]
0x18002225b  call    WPP_SF_Ss
0x180022260  jmp     loc_180022514
0x180022265  mov     rcx, cs:DhcpGlobalClientTable
0x18002226c  lea     r8, [rbp+pcbActual]; pcbActual
0x180022270  mov     [rbp+pcbActual], 1
0x180022277  lea     rdx, [rbp+pvData]; pvData
0x18002227b  mov     ecx, [rcx+28h]; columnid
0x18002227e  call    DhcpJetGetValue
0x180022283  mov     ebx, eax
0x180022285  test    eax, eax
0x180022287  jz      short loc_1800222C0
0x180022289  mov     rcx, cs:WPP_GLOBAL_Control
0x180022290  lea     r15, WPP_GLOBAL_Control
0x180022297  cmp     rcx, r15
0x18002229a  jz      loc_18002253A
0x1800222a0  test    [rcx+1Ch], dil
0x1800222a4  jz      loc_18002251B
0x1800222aa  mov     ecx, dword ptr [rbp+in.S_un]; in
0x1800222ad  call    cs:__imp_inet_ntoa
0x1800222b4  nop     dword ptr [rax+rax+00h]
0x1800222b9  mov     edx, 33h ; '3'
0x1800222be  jmp     short loc_180022241
0x1800222c0  mov     r10, cs:WPP_GLOBAL_Control
0x1800222c7  lea     rdx, WPP_GLOBAL_Control
0x1800222ce  cmp     r10, rdx
0x1800222d1  jz      short loc_180022301
0x1800222d3  test    dword ptr [r10+1Ch], 10000000h
0x1800222db  jz      short loc_180022301
0x1800222dd  movzx   r9d, byte ptr [rbp+pvData]
0x1800222e2  mov     edx, 34h ; '4'
0x1800222e7  mov     rcx, [r10+10h]
0x1800222eb  mov     r8, r14
0x1800222ee  call    WPP_SF_D
0x1800222f3  mov     r10, cs:WPP_GLOBAL_Control
0x1800222fa  lea     rdx, WPP_GLOBAL_Control
0x180022301  mov     al, byte ptr [rbp+pvData]
0x180022304  and     al, 0C0h
0x180022306  cmp     al, 0C0h
0x180022308  jnz     loc_180022541
0x18002230e  movzx   ecx, byte ptr [rbp+pvData]
0x180022312  and     ecx, 0FFFFFF03h
0x180022318  cmp     r15b, cl
0x18002231b  jnz     loc_180022541
0x180022321  mov     rcx, cs:DhcpGlobalClientTable
0x180022328  lea     r8, [rbp+pcbActual]; pcbActual
0x18002232c  and     [rbp+pcbActual], 0
0x180022330  lea     rdx, [rbp+lpMem]; pvData
0x180022334  mov     ecx, [rcx+48h]; columnid
0x180022337  call    DhcpJetGetValue
0x18002233c  mov     ebx, eax
0x18002233e  test    eax, eax
0x180022340  jz      short loc_18002237C
0x180022342  mov     rcx, cs:WPP_GLOBAL_Control
0x180022349  lea     r15, WPP_GLOBAL_Control
0x180022350  cmp     rcx, r15
0x180022353  jz      loc_18002253A
0x180022359  test    [rcx+1Ch], dil
0x18002235d  jz      loc_18002251B
0x180022363  mov     ecx, dword ptr [rbp+in.S_un]; in
0x180022366  call    cs:__imp_inet_ntoa
0x18002236d  nop     dword ptr [rax+rax+00h]
0x180022372  mov     edx, 36h ; '6'
0x180022377  jmp     loc_180022241
0x18002237c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022383  lea     r15, WPP_GLOBAL_Control
0x18002238a  cmp     rcx, r15
0x18002238d  jz      short loc_1800223BE
0x18002238f  test    dword ptr [rcx+1Ch], 10000000h
0x180022396  jz      short loc_1800223BE
0x180022398  mov     rax, [rbp+lpMem]
0x18002239c  mov     edx, 37h ; '7'
0x1800223a1  mov     rcx, [rcx+10h]
0x1800223a5  test    rax, rax
0x1800223a8  mov     r8, r14
0x1800223ab  cmovnz  r12, rax
0x1800223af  mov     r9, r12
0x1800223b2  call    WPP_SF_S
0x1800223b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223be  test    rsi, rsi
0x1800223c1  jnz     short loc_1800223FE
0x1800223c3  cmp     [rbp+lpMem], rsi
0x1800223c7  jnz     loc_18002255D
0x1800223cd  and     [rsp+40h+var_18], 0
0x1800223d3  lea     r8, [rbp+var_8]
0x1800223d7  mov     edx, dword ptr [rbp+in.S_un]
0x1800223da  xor     r9d, r9d
0x1800223dd  and     [rsp+40h+var_20], r9
0x1800223e2  mov     eax, edx
0x1800223e4  mov     rcx, cs:DhcpGlobalThisServer
0x1800223eb  and     eax, 0F0000000h
0x1800223f0  cmp     eax, 0E0000000h
0x1800223f5  jnz     short loc_18002244E
0x1800223f7  call    MemServerGetMAddressInfo
0x1800223fc  jmp     short loc_180022453
0x1800223fe  mov     rax, [rbp+lpMem]
0x180022402  lea     rdx, Annotation
0x180022409  test    rax, rax
0x18002240c  cmovnz  rdx, rax
0x180022410  sub     rdx, rsi
0x180022413  movzx   eax, word ptr [rsi]
0x180022416  movzx   r8d, word ptr [rsi+rdx]
0x18002241b  sub     eax, r8d
0x18002241e  jnz     short loc_180022429
0x180022420  add     rsi, 2
0x180022424  test    r8d, r8d
0x180022427  jnz     short loc_180022413
0x180022429  test    eax, eax
0x18002242b  jz      short loc_1800223CD
0x18002242d  cmp     rcx, r15
0x180022430  jz      loc_18002255D
0x180022436  test    [rcx+1Ch], dil
0x18002243a  jz      loc_18002255D
0x180022440  mov     rcx, [rcx+10h]
0x180022444  mov     edx, 38h ; '8'
0x180022449  jmp     loc_180022555
0x18002244e  call    MemServerGetUAddressInfo
0x180022453  mov     ebx, eax
0x180022455  test    eax, eax
0x180022457  jz      short loc_18002248F
0x180022459  mov     rcx, cs:WPP_GLOBAL_Control
0x180022460  cmp     rcx, r15
0x180022463  jz      loc_18002253A
0x180022469  test    dword ptr [rcx+1Ch], 800000h
0x180022470  jz      loc_18002251B
0x180022476  mov     edx, 39h ; '9'
0x18002247b  mov     r9d, eax
0x18002247e  mov     rcx, [rcx+10h]
0x180022482  mov     r8, r14
0x180022485  call    WPP_SF_D
0x18002248a  jmp     loc_180022514
0x18002248f  mov     rcx, [rbp+var_8]
0x180022493  cmp     dword ptr [rcx+10C4h], 1
0x18002249a  jnz     short loc_1800224D1
0x18002249c  mov     edx, dword ptr [rbp+in.S_un]
0x18002249f  xor     r9d, r9d
0x1800224a2  lea     r8d, [r9+1]
0x1800224a6  call    DhcpHandleFailoverRequest
0x1800224ab  mov     ebx, eax
0x1800224ad  test    eax, eax
0x1800224af  jz      loc_18002255D
0x1800224b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224bc  cmp     rcx, r15
0x1800224bf  jz      short loc_18002253A
0x1800224c1  test    [rcx+1Ch], dil
0x1800224c5  jz      short loc_18002251B
0x1800224c7  mov     edx, 3Ah ; ':'
0x1800224cc  mov     r9d, eax
0x1800224cf  jmp     short loc_18002247E
0x1800224d1  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800224d8  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800224df  call    cs:__imp_JetDelete
0x1800224e6  nop     dword ptr [rax+rax+00h]
0x1800224eb  mov     ebx, eax
0x1800224ed  test    eax, eax
0x1800224ef  jz      short loc_18002255D
0x1800224f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800224f8  cmp     rcx, r15
0x1800224fb  jz      short loc_18002253A
0x1800224fd  test    [rcx+1Ch], dil
0x180022501  jz      short loc_18002251B
0x180022503  mov     rcx, [rcx+10h]
0x180022507  mov     edx, 3Bh ; ';'
0x18002250c  mov     r8, r14
0x18002250f  call    WPP_SF_
0x180022514  mov     rcx, cs:WPP_GLOBAL_Control
0x18002251b  cmp     rcx, r15
0x18002251e  jz      short loc_18002253A
0x180022520  test    [rcx+1Ch], dil
0x180022524  jz      short loc_18002253A
0x180022526  mov     rcx, [rcx+10h]
0x18002252a  mov     edx, 3Ch ; '<'
0x18002252f  mov     r9d, ebx
0x180022532  mov     r8, r14
0x180022535  call    WPP_SF_D
0x18002253a  call    DhcpJetRollBack
0x18002253f  jmp     short loc_180022562
0x180022541  cmp     r10, rdx
0x180022544  jz      short loc_18002255D
0x180022546  test    [r10+1Ch], dil
0x18002254a  jz      short loc_18002255D
0x18002254c  mov     rcx, [r10+10h]
0x180022550  mov     edx, 35h ; '5'
0x180022555  mov     r8, r14
0x180022558  call    WPP_SF_
0x18002255d  call    DhcpJetCommitTransaction
0x180022562  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180022569  call    cs:__imp_LeaveCriticalSection
0x180022570  nop     dword ptr [rax+rax+00h]
0x180022575  mov     r8, [rbp+lpMem]; lpMem
0x180022579  test    r8, r8
0x18002257c  jz      short loc_180022593
0x18002257e  mov     rcx, cs:gDhcpHeap; hHeap
0x180022585  xor     edx, edx; dwFlags
0x180022587  call    cs:__imp_HeapFree
0x18002258e  nop     dword ptr [rax+rax+00h]
0x180022593  add     rsp, 40h
0x180022597  pop     r15
0x180022599  pop     r14
0x18002259b  pop     r12
0x18002259d  pop     rdi
0x18002259e  pop     rsi
0x18002259f  pop     rbx
0x1800225a0  pop     rbp
0x1800225a1  retn
```
