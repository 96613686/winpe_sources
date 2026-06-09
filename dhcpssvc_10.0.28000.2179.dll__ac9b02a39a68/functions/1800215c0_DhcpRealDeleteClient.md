# DhcpRealDeleteClient

- ea: `0x1800215c0`
- end: `0x180021a92`
- name: `DhcpRealDeleteClient`
- size: `1234`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f720`
- `0x18001fe44`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800058bc`
- `0x18000d028`
- `0x18000e1a0`
- `0x18000e1d0`
- `0x18000e284`
- `0x18000e450`
- `0x18000e78c`
- `0x1800215c0`
- `0x180022018`
- `0x180022340`
- `0x180093144`
- `0x1800932a8`

## import_xrefs

- `ESENT!JetDelete` at `0x1800219c5`
- `ESENT!JetDelete` at `0x1800219c5`
- `WS2_32!__imp_inet_ntoa` at `0x180021622`
- `WS2_32!__imp_inet_ntoa` at `0x180021712`
- `WS2_32!__imp_inet_ntoa` at `0x18002178b`
- `WS2_32!__imp_inet_ntoa` at `0x18002184c`
- `WS2_32!__imp_inet_ntoa` at `0x180021622`
- `WS2_32!__imp_inet_ntoa` at `0x180021712`
- `WS2_32!__imp_inet_ntoa` at `0x18002178b`
- `WS2_32!__imp_inet_ntoa` at `0x18002184c`
- `KERNEL32!EnterCriticalSection` at `0x180021659`
- `KERNEL32!EnterCriticalSection` at `0x180021659`
- `KERNEL32!LeaveCriticalSection` at `0x180021677`
- `KERNEL32!LeaveCriticalSection` at `0x180021a4f`
- `KERNEL32!LeaveCriticalSection` at `0x180021677`
- `KERNEL32!LeaveCriticalSection` at `0x180021a4f`
- `KERNEL32!HeapFree` at `0x180021a6d`
- `KERNEL32!HeapFree` at `0x180021a6d`

## pseudocode

```c
void __fastcall DhcpRealDeleteClient(struct in_addr a1, const wchar_t *a2, char a3)
{
  const wchar_t *v4; // r14
  const wchar_t *v5; // r13
  __int64 v6; // rsi
  const wchar_t *v7; // rbx
  unsigned int v8; // eax
  int v9; // r8d
  char v10; // r12
  unsigned int v11; // ebx
  unsigned int Value; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rbx
  char *v15; // rax
  int v16; // r8d
  int v17; // edx
  _BYTE *v18; // r10
  _BYTE *v19; // rcx
  unsigned int v20; // eax
  const size_t *v21; // rdx
  signed __int64 v22; // rdx
  int v23; // r8d
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r9
  unsigned int v29; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-10h] BYREF
  __int64 v31; // [rsp+38h] [rbp-8h] BYREF
  struct in_addr in; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int8 pvData; // [rsp+90h] [rbp+50h] BYREF
  unsigned int pcbActual; // [rsp+98h] [rbp+58h] BYREF

  in = a1;
  lpMem = 0;
  v4 = a2;
  pvData = 0;
  v31 = 0;
  v5 = L"NULL";
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 )
  {
    v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v7 = a2;
    if ( !a2 )
      v7 = L"NULL";
    v8 = (unsigned int)inet_ntoa(a1);
    WPP_SF_sSD(v6, 48, v9, v8, (__int64)v7, a3);
  }
  v10 = a3 & 3;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v11 = DhcpJetBeginTransaction();
  if ( v11 )
  {
    LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v11);
    return;
  }
  pcbActual = 4;
  Value = DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &in, 4);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = inet_ntoa(in);
        v17 = 50;
LABEL_14:
        if ( !v4 )
          v4 = L"NULL";
        WPP_SF_Ss(v14, v17, v16, (_DWORD)v4, (__int64)v15);
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
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = inet_ntoa(in);
        v17 = 51;
        goto LABEL_14;
      }
LABEL_64:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
        WPP_SF_D(v13[2], 60, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, Value);
    }
LABEL_67:
    DhcpJetRollBack();
    goto LABEL_73;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, pvData);
    v18 = WPP_GLOBAL_Control;
  }
  if ( (pvData & 0xC0) != 0xC0 || v10 != (pvData & 3) )
  {
    if ( v18 == (_BYTE *)&WPP_GLOBAL_Control || (v18[28] & 0x10) == 0 )
      goto LABEL_72;
    v25 = *((_QWORD *)v18 + 2);
    v26 = 53;
LABEL_71:
    WPP_SF_(v25, v26, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
    goto LABEL_72;
  }
  pcbActual = 0;
  Value = DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 72), &lpMem, &pcbActual);
  if ( Value )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v14 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v15 = inet_ntoa(in);
        v17 = 54;
        goto LABEL_14;
      }
      goto LABEL_64;
    }
    goto LABEL_67;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    if ( lpMem )
      v5 = (const wchar_t *)lpMem;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v5);
    v19 = WPP_GLOBAL_Control;
  }
  if ( !v4 )
  {
    if ( lpMem )
      goto LABEL_72;
    goto LABEL_37;
  }
  v21 = &Annotation;
  if ( lpMem )
    v21 = (const size_t *)lpMem;
  v22 = (char *)v21 - (char *)v4;
  do
  {
    v23 = *(const wchar_t *)((char *)v4 + v22);
    v24 = *v4 - v23;
    if ( v24 )
      break;
    ++v4;
  }
  while ( v23 );
  if ( v24 )
  {
    if ( v19 == (_BYTE *)&WPP_GLOBAL_Control || (v19[28] & 0x10) == 0 )
      goto LABEL_72;
    v25 = *((_QWORD *)v19 + 2);
    v26 = 56;
    goto LABEL_71;
  }
LABEL_37:
  if ( (in.S_un.S_addr & 0xF0000000) == 0xE0000000 )
    v20 = ((__int64 (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int64, __int64))MemServerGetMAddressInfo)(
            (_DWORD)DhcpGlobalThisServer,
            in,
            (unsigned int)&v31,
            0,
            0,
            0);
  else
    v20 = ((__int64 (__fastcall *)(_DWORD, _DWORD, _DWORD, _DWORD, __int64, __int64))MemServerGetUAddressInfo)(
            (_DWORD)DhcpGlobalThisServer,
            in,
            (unsigned int)&v31,
            0,
            0,
            0);
  Value = v20;
  if ( v20 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_67;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      goto LABEL_64;
    v27 = 57;
    v28 = v20;
    goto LABEL_53;
  }
  if ( *(_DWORD *)(v31 + 4292) == 1 )
  {
    v29 = DhcpHandleFailoverRequest(v31, in.S_un.S_addr, 1, 0);
    Value = v29;
    if ( v29 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_67;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_64;
      v27 = 58;
      v28 = v29;
LABEL_53:
      WPP_SF_D(v13[2], v27, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids, v28);
      goto LABEL_63;
    }
  }
  else
  {
    Value = JetDelete(DhcpGlobalJetServerSession, DhcpGlobalClientTableHandle);
    if ( Value )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_67;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_64;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids);
LABEL_63:
      v13 = WPP_GLOBAL_Control;
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
0x1800215c0  mov     [rsp-38h+arg_8], rbx
0x1800215c5  mov     dword ptr [rsp-38h+in.S_un], ecx
0x1800215c9  push    rbp
0x1800215ca  push    rsi
0x1800215cb  push    rdi
0x1800215cc  push    r12
0x1800215ce  push    r13
0x1800215d0  push    r14
0x1800215d2  push    r15
0x1800215d4  mov     rbp, rsp
0x1800215d7  sub     rsp, 40h
0x1800215db  xor     r15d, r15d
0x1800215de  movzx   r12d, r8b
0x1800215e2  mov     [rbp+lpMem], r15
0x1800215e6  mov     r14, rdx
0x1800215e9  mov     [rbp+pvData], r15b
0x1800215ed  mov     [rbp+var_8], r15
0x1800215f1  mov     rsi, cs:WPP_GLOBAL_Control
0x1800215f8  lea     rdi, WPP_GLOBAL_Control
0x1800215ff  lea     r13, aNull_0; "NULL"
0x180021606  cmp     rsi, rdi
0x180021609  jz      short loc_18002164E
0x18002160b  test    dword ptr [rsi+1Ch], 40000h
0x180021612  jz      short loc_18002164E
0x180021614  mov     rsi, [rsi+10h]
0x180021618  test    rdx, rdx
0x18002161b  mov     rbx, rdx
0x18002161e  cmovz   rbx, r13
0x180021622  call    cs:__imp_inet_ntoa
0x180021629  nop     dword ptr [rax+rax+00h]
0x18002162e  lea     edx, [r15+30h]
0x180021632  mov     dword ptr [rsp+40h+var_18], r12d
0x180021637  mov     r9, rax
0x18002163a  mov     [rsp+40h+var_20], rbx
0x18002163f  mov     rcx, rsi
0x180021642  call    WPP_SF_sSD
0x180021647  lea     rdi, WPP_GLOBAL_Control
0x18002164e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180021655  and     r12b, 3
0x180021659  call    cs:__imp_EnterCriticalSection
0x180021660  nop     dword ptr [rax+rax+00h]
0x180021665  call    DhcpJetBeginTransaction
0x18002166a  mov     ebx, eax
0x18002166c  test    eax, eax
0x18002166e  jz      short loc_1800216BD
0x180021670  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180021677  call    cs:__imp_LeaveCriticalSection
0x18002167e  nop     dword ptr [rax+rax+00h]
0x180021683  mov     rcx, cs:WPP_GLOBAL_Control
0x18002168a  cmp     rcx, rdi
0x18002168d  jz      loc_180021A79
0x180021693  mov     sil, 10h
0x180021696  test    [rcx+1Ch], sil
0x18002169a  jz      loc_180021A79
0x1800216a0  mov     rcx, [rcx+10h]
0x1800216a4  lea     r8, WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids
0x1800216ab  mov     edx, 31h ; '1'
0x1800216b0  mov     r9d, ebx
0x1800216b3  call    WPP_SF_D
0x1800216b8  jmp     loc_180021A79
0x1800216bd  mov     rcx, cs:DhcpGlobalClientTable
0x1800216c4  lea     rdx, [rbp+in]
0x1800216c8  mov     r8d, 4
0x1800216ce  mov     [rbp+pcbActual], r8d
0x1800216d2  mov     rcx, [rcx]
0x1800216d5  call    DhcpJetOpenKey
0x1800216da  lea     r15, WPP_a10e7971d1c43cc0bc7e2a11ac7f8ae0_Traceguids
0x1800216e1  mov     edi, eax
0x1800216e3  mov     sil, 10h
0x1800216e6  test    eax, eax
0x1800216e8  jz      short loc_18002173F
0x1800216ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216f1  lea     r12, WPP_GLOBAL_Control
0x1800216f8  cmp     rcx, r12
0x1800216fb  jz      loc_180021A20
0x180021701  test    [rcx+1Ch], sil
0x180021705  jz      loc_180021A01
0x18002170b  mov     rbx, [rcx+10h]
0x18002170f  mov     ecx, dword ptr [rbp+in.S_un]; in
0x180021712  call    cs:__imp_inet_ntoa
0x180021719  nop     dword ptr [rax+rax+00h]
0x18002171e  mov     edx, 32h ; '2'
0x180021723  test    r14, r14
0x180021726  mov     [rsp+40h+var_20], rax
0x18002172b  mov     rcx, rbx
0x18002172e  cmovz   r14, r13
0x180021732  mov     r9, r14
0x180021735  call    WPP_SF_Ss
0x18002173a  jmp     loc_1800219FA
0x18002173f  mov     rcx, cs:DhcpGlobalClientTable
0x180021746  lea     r8, [rbp+pcbActual]; pcbActual
0x18002174a  mov     [rbp+pcbActual], 1
0x180021751  lea     rdx, [rbp+pvData]; pvData
0x180021755  mov     ecx, [rcx+28h]; columnid
0x180021758  call    DhcpJetGetValue
0x18002175d  mov     edi, eax
0x18002175f  test    eax, eax
0x180021761  jz      short loc_18002179E
0x180021763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002176a  lea     r12, WPP_GLOBAL_Control
0x180021771  cmp     rcx, r12
0x180021774  jz      loc_180021A20
0x18002177a  test    [rcx+1Ch], sil
0x18002177e  jz      loc_180021A01
0x180021784  mov     rbx, [rcx+10h]
0x180021788  mov     ecx, dword ptr [rbp+in.S_un]; in
0x18002178b  call    cs:__imp_inet_ntoa
0x180021792  nop     dword ptr [rax+rax+00h]
0x180021797  mov     edx, 33h ; '3'
0x18002179c  jmp     short loc_180021723
0x18002179e  mov     r10, cs:WPP_GLOBAL_Control
0x1800217a5  lea     rdx, WPP_GLOBAL_Control
0x1800217ac  mov     ebx, 10000000h
0x1800217b1  cmp     r10, rdx
0x1800217b4  jz      short loc_1800217E0
0x1800217b6  test    [r10+1Ch], ebx
0x1800217ba  jz      short loc_1800217E0
0x1800217bc  movzx   r9d, [rbp+pvData]
0x1800217c1  mov     edx, 34h ; '4'
0x1800217c6  mov     rcx, [r10+10h]
0x1800217ca  mov     r8, r15
0x1800217cd  call    WPP_SF_D
0x1800217d2  mov     r10, cs:WPP_GLOBAL_Control
0x1800217d9  lea     rdx, WPP_GLOBAL_Control
0x1800217e0  mov     al, [rbp+pvData]
0x1800217e3  and     al, 0C0h
0x1800217e5  cmp     al, 0C0h
0x1800217e7  jnz     loc_180021A27
0x1800217ed  movzx   ecx, [rbp+pvData]
0x1800217f1  and     ecx, 0FFFFFF03h
0x1800217f7  cmp     r12b, cl
0x1800217fa  jnz     loc_180021A27
0x180021800  mov     rcx, cs:DhcpGlobalClientTable
0x180021807  lea     r8, [rbp+pcbActual]; pcbActual
0x18002180b  mov     [rbp+pcbActual], 0
0x180021812  lea     rdx, [rbp+lpMem]; pvData
0x180021816  mov     ecx, [rcx+48h]; columnid
0x180021819  call    DhcpJetGetValue
0x18002181e  mov     edi, eax
0x180021820  test    eax, eax
0x180021822  jz      short loc_180021862
0x180021824  mov     rcx, cs:WPP_GLOBAL_Control
0x18002182b  lea     r12, WPP_GLOBAL_Control
0x180021832  cmp     rcx, r12
0x180021835  jz      loc_180021A20
0x18002183b  test    [rcx+1Ch], sil
0x18002183f  jz      loc_180021A01
0x180021845  mov     rbx, [rcx+10h]
0x180021849  mov     ecx, dword ptr [rbp+in.S_un]; in
0x18002184c  call    cs:__imp_inet_ntoa
0x180021853  nop     dword ptr [rax+rax+00h]
0x180021858  mov     edx, 36h ; '6'
0x18002185d  jmp     loc_180021723
0x180021862  mov     rcx, cs:WPP_GLOBAL_Control
0x180021869  lea     r12, WPP_GLOBAL_Control
0x180021870  cmp     rcx, r12
0x180021873  jz      short loc_1800218A0
0x180021875  test    [rcx+1Ch], ebx
0x180021878  jz      short loc_1800218A0
0x18002187a  mov     rax, [rbp+lpMem]
0x18002187e  mov     edx, 37h ; '7'
0x180021883  mov     rcx, [rcx+10h]
0x180021887  test    rax, rax
0x18002188a  mov     r8, r15
0x18002188d  cmovnz  r13, rax
0x180021891  mov     r9, r13
0x180021894  call    WPP_SF_S
0x180021899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218a0  test    r14, r14
0x1800218a3  jnz     short loc_1800218E3
0x1800218a5  cmp     [rbp+lpMem], r14
0x1800218a9  jnz     loc_180021A43
0x1800218af  mov     edx, dword ptr [rbp+in.S_un]
0x1800218b2  lea     r8, [rbp+var_8]
0x1800218b6  mov     rcx, cs:DhcpGlobalThisServer
0x1800218bd  xor     r9d, r9d
0x1800218c0  mov     eax, edx
0x1800218c2  mov     [rsp+40h+var_18], 0
0x1800218cb  and     eax, 0F0000000h
0x1800218d0  mov     [rsp+40h+var_20], r9
0x1800218d5  cmp     eax, 0E0000000h
0x1800218da  jnz     short loc_180021934
0x1800218dc  call    MemServerGetMAddressInfo
0x1800218e1  jmp     short loc_180021939
0x1800218e3  mov     rax, [rbp+lpMem]
0x1800218e7  lea     rdx, Annotation
0x1800218ee  test    rax, rax
0x1800218f1  cmovnz  rdx, rax
0x1800218f5  sub     rdx, r14
0x1800218f8  movzx   eax, word ptr [r14]
0x1800218fc  movzx   r8d, word ptr [r14+rdx]
0x180021901  sub     eax, r8d
0x180021904  jnz     short loc_18002190F
0x180021906  add     r14, 2
0x18002190a  test    r8d, r8d
0x18002190d  jnz     short loc_1800218F8
0x18002190f  test    eax, eax
0x180021911  jz      short loc_1800218AF
0x180021913  cmp     rcx, r12
0x180021916  jz      loc_180021A43
0x18002191c  test    [rcx+1Ch], sil
0x180021920  jz      loc_180021A43
0x180021926  mov     rcx, [rcx+10h]
0x18002192a  mov     edx, 38h ; '8'
0x18002192f  jmp     loc_180021A3B
0x180021934  call    MemServerGetUAddressInfo
0x180021939  mov     edi, eax
0x18002193b  test    eax, eax
0x18002193d  jz      short loc_180021975
0x18002193f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021946  cmp     rcx, r12
0x180021949  jz      loc_180021A20
0x18002194f  test    dword ptr [rcx+1Ch], 800000h
0x180021956  jz      loc_180021A01
0x18002195c  mov     edx, 39h ; '9'
0x180021961  mov     r9d, eax
0x180021964  mov     rcx, [rcx+10h]
0x180021968  mov     r8, r15
0x18002196b  call    WPP_SF_D
0x180021970  jmp     loc_1800219FA
0x180021975  mov     rcx, [rbp+var_8]
0x180021979  cmp     dword ptr [rcx+10C4h], 1
0x180021980  jnz     short loc_1800219B7
0x180021982  mov     edx, dword ptr [rbp+in.S_un]
0x180021985  xor     r9d, r9d
0x180021988  lea     r8d, [r9+1]
0x18002198c  call    DhcpHandleFailoverRequest
0x180021991  mov     edi, eax
0x180021993  test    eax, eax
0x180021995  jz      loc_180021A43
0x18002199b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219a2  cmp     rcx, r12
0x1800219a5  jz      short loc_180021A20
0x1800219a7  test    [rcx+1Ch], sil
0x1800219ab  jz      short loc_180021A01
0x1800219ad  mov     edx, 3Ah ; ':'
0x1800219b2  mov     r9d, eax
0x1800219b5  jmp     short loc_180021964
0x1800219b7  mov     rdx, cs:DhcpGlobalClientTableHandle; tableid
0x1800219be  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800219c5  call    cs:__imp_JetDelete
0x1800219cc  nop     dword ptr [rax+rax+00h]
0x1800219d1  mov     edi, eax
0x1800219d3  test    eax, eax
0x1800219d5  jz      short loc_180021A43
0x1800219d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219de  cmp     rcx, r12
0x1800219e1  jz      short loc_180021A20
0x1800219e3  test    [rcx+1Ch], sil
0x1800219e7  jz      short loc_180021A01
0x1800219e9  mov     rcx, [rcx+10h]
0x1800219ed  mov     edx, 3Bh ; ';'
0x1800219f2  mov     r8, r15
0x1800219f5  call    WPP_SF_
0x1800219fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a01  cmp     rcx, r12
0x180021a04  jz      short loc_180021A20
0x180021a06  test    [rcx+1Ch], sil
0x180021a0a  jz      short loc_180021A20
0x180021a0c  mov     rcx, [rcx+10h]
0x180021a10  mov     edx, 3Ch ; '<'
0x180021a15  mov     r9d, edi
0x180021a18  mov     r8, r15
0x180021a1b  call    WPP_SF_D
0x180021a20  call    DhcpJetRollBack
0x180021a25  jmp     short loc_180021A48
0x180021a27  cmp     r10, rdx
0x180021a2a  jz      short loc_180021A43
0x180021a2c  test    [r10+1Ch], sil
0x180021a30  jz      short loc_180021A43
0x180021a32  mov     rcx, [r10+10h]
0x180021a36  mov     edx, 35h ; '5'
0x180021a3b  mov     r8, r15
0x180021a3e  call    WPP_SF_
0x180021a43  call    DhcpJetCommitTransaction
0x180021a48  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180021a4f  call    cs:__imp_LeaveCriticalSection
0x180021a56  nop     dword ptr [rax+rax+00h]
0x180021a5b  mov     r8, [rbp+lpMem]; lpMem
0x180021a5f  test    r8, r8
0x180021a62  jz      short loc_180021A79
0x180021a64  mov     rcx, cs:gDhcpHeap; hHeap
0x180021a6b  xor     edx, edx; dwFlags
0x180021a6d  call    cs:__imp_HeapFree
0x180021a74  nop     dword ptr [rax+rax+00h]
0x180021a79  mov     rbx, [rsp+40h+arg_8]
0x180021a81  add     rsp, 40h
0x180021a85  pop     r15
0x180021a87  pop     r14
0x180021a89  pop     r13
0x180021a8b  pop     r12
0x180021a8d  pop     rdi
0x180021a8e  pop     rsi
0x180021a8f  pop     rbp
0x180021a90  retn
```
