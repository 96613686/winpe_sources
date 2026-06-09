# DhcpSetJetParameters

- ea: `0x18000f690`
- end: `0x1800101fa`
- name: `DhcpSetJetParameters`
- size: `2922`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000df98`
- `0x18000f4b8`
- `0x1800131d0`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18000c180`
- `0x18000f144`
- `0x18000f690`
- `0x18001130c`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetGetSystemParameter` at `0x18000f9b7`
- `ESENT!JetGetSystemParameter` at `0x18000f9b7`
- `ESENT!JetSetSystemParameter` at `0x18000f7b1`
- `ESENT!JetSetSystemParameter` at `0x18000f822`
- `ESENT!JetSetSystemParameter` at `0x18000f87d`
- `ESENT!JetSetSystemParameter` at `0x18000f955`
- `ESENT!JetSetSystemParameter` at `0x18000fa1e`
- `ESENT!JetSetSystemParameter` at `0x18000fab1`
- `ESENT!JetSetSystemParameter` at `0x18000fb4f`
- `ESENT!JetSetSystemParameter` at `0x18000fbaf`
- `ESENT!JetSetSystemParameter` at `0x18000fc0f`
- `ESENT!JetSetSystemParameter` at `0x18000fc6f`
- `ESENT!JetSetSystemParameter` at `0x18000fcfe`
- `ESENT!JetSetSystemParameter` at `0x18000fd5e`
- `ESENT!JetSetSystemParameter` at `0x18000fdee`
- `ESENT!JetSetSystemParameter` at `0x18000fe4a`
- `ESENT!JetSetSystemParameter` at `0x18000feba`
- `ESENT!JetSetSystemParameter` at `0x18000ff16`
- `ESENT!JetSetSystemParameter` at `0x18000ff72`
- `ESENT!JetSetSystemParameter` at `0x180010025`
- `ESENT!JetSetSystemParameter` at `0x180010063`
- `ESENT!JetSetSystemParameter` at `0x1800100bf`
- `ESENT!JetSetSystemParameter` at `0x18001011b`
- `ESENT!JetSetSystemParameter` at `0x180010165`
- `ESENT!JetSetSystemParameter` at `0x18000f7b1`
- `ESENT!JetSetSystemParameter` at `0x18000f822`
- `ESENT!JetSetSystemParameter` at `0x18000f87d`
- `ESENT!JetSetSystemParameter` at `0x18000f955`
- `ESENT!JetSetSystemParameter` at `0x18000fa1e`
- `ESENT!JetSetSystemParameter` at `0x18000fab1`
- `ESENT!JetSetSystemParameter` at `0x18000fb4f`
- `ESENT!JetSetSystemParameter` at `0x18000fbaf`
- `ESENT!JetSetSystemParameter` at `0x18000fc0f`
- `ESENT!JetSetSystemParameter` at `0x18000fc6f`
- `ESENT!JetSetSystemParameter` at `0x18000fcfe`
- `ESENT!JetSetSystemParameter` at `0x18000fd5e`
- `ESENT!JetSetSystemParameter` at `0x18000fdee`
- `ESENT!JetSetSystemParameter` at `0x18000fe4a`
- `ESENT!JetSetSystemParameter` at `0x18000feba`
- `ESENT!JetSetSystemParameter` at `0x18000ff16`
- `ESENT!JetSetSystemParameter` at `0x18000ff72`
- `ESENT!JetSetSystemParameter` at `0x180010025`
- `ESENT!JetSetSystemParameter` at `0x180010063`
- `ESENT!JetSetSystemParameter` at `0x1800100bf`
- `ESENT!JetSetSystemParameter` at `0x18001011b`
- `ESENT!JetSetSystemParameter` at `0x180010165`
- `USER32!OemToCharBuffA` at `0x18000f764`
- `USER32!OemToCharBuffA` at `0x18000f907`
- `USER32!OemToCharBuffA` at `0x18000fffc`
- `USER32!OemToCharBuffA` at `0x18000f764`
- `USER32!OemToCharBuffA` at `0x18000f907`
- `USER32!OemToCharBuffA` at `0x18000fffc`

## pseudocode

```c
__int64 DhcpSetJetParameters()
{
  __int64 v0; // rsi
  __int64 v1; // rax
  __int64 v2; // r8
  __int64 SystemParameter; // rdi
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // ecx
  unsigned __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned __int128 v12; // rax
  unsigned __int64 v13; // kr00_8
  unsigned __int64 v14; // rax
  __int64 v15; // r14
  unsigned __int64 v16; // rdi
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  CHAR pszDest[272]; // [rsp+40h] [rbp-C0h] BYREF

  v24 = 0;
  pszDest[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( DhcpGlobalOemDatabasePath[v1] );
  if ( (unsigned __int64)(v1 + 2) < 0x104 )
    StringCbPrintfA(pszDest, 0x104u, "%s%s", DhcpGlobalOemDatabasePath, "\\");
  v2 = -1;
  do
    ++v2;
  while ( pszDest[v2] );
  OemToCharBuffA(pszDest, pszDest, v2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, pszDest);
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 0, 0, pszDest);
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 19;
LABEL_17:
    v7 = (unsigned int)SystemParameter;
LABEL_18:
    WPP_SF_D(v5[2], v6, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v7);
LABEL_130:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_131;
  }
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 3, 0, "j50");
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 20;
    goto LABEL_17;
  }
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 11, 1024, 0);
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 21;
    goto LABEL_17;
  }
  StringCbPrintfA(pszDest, 0x104u, "%s%s", DhcpGlobalOemDatabasePath, "\\");
  v8 = -1;
  do
    ++v8;
  while ( pszDest[v8] );
  OemToCharBuffA(pszDest, pszDest, v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, pszDest);
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 1, 0, pszDest);
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 23;
    goto LABEL_17;
  }
  SystemParameter = (unsigned int)JetGetSystemParameter(JetInstance, 0, 64, &v24, 0, 0);
  v4 = DhcpMapJetError(SystemParameter, "GetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 24;
    goto LABEL_17;
  }
  LODWORD(SystemParameter) = JetSetSystemParameter(&JetInstance, 0, 60, 0x6400000 / v24, 0);
  v4 = DhcpMapJetError((unsigned int)SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 25;
    goto LABEL_17;
  }
  v9 = DhcpJetDatabaseMaxCacheSize;
  v10 = 0;
  if ( DhcpJetDatabaseMaxCacheSize == -1 )
    goto LABEL_58;
  v11 = 2;
  if ( (unsigned int)DhcpJetDatabaseMaxCacheSize >= 2 )
    v11 = (unsigned int)DhcpJetDatabaseMaxCacheSize;
  v13 = v11;
  v12 = (unsigned __int64)v11 * (unsigned __int128)0x100000uLL;
  if ( is_mul_ok(v13, 0x100000u) )
  {
    v14 = v12 / v24;
    v10 = v14;
    if ( v14 )
    {
      LODWORD(v15) = JetSetSystemParameter(&JetInstance, 0, 23, v14, 0);
      v4 = DhcpMapJetError((unsigned int)v15, "SetSysParam");
      if ( v4 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v4;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
          goto LABEL_131;
        v6 = 26;
LABEL_53:
        v7 = (unsigned int)v15;
        goto LABEL_18;
      }
      v9 = DhcpJetDatabaseMaxCacheSize;
    }
  }
  if ( v9 == -1 || !v10 )
  {
LABEL_58:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
  }
  v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 9, 1500, 0);
  v4 = DhcpMapJetError(v15, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 28;
    goto LABEL_53;
  }
  v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 6, 36, 0);
  v4 = DhcpMapJetError(v15, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 29;
    goto LABEL_53;
  }
  v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 8, 100, 0);
  v4 = DhcpMapJetError(v15, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 30;
    goto LABEL_53;
  }
  v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 10, 1, 0);
  v4 = DhcpMapJetError(v15, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 31;
    goto LABEL_53;
  }
  if ( DhcpJetDatabaseMaxCacheSize == -1 || !v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
  }
  else
  {
    v16 = v10 / 0x64;
    v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 31, v16, 0);
    v4 = DhcpMapJetError(v15, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_131;
      v6 = 32;
      goto LABEL_53;
    }
    SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 32, 2 * v16, 0);
    v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_131;
      v6 = 33;
      goto LABEL_17;
    }
  }
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 50, 1, 0);
  v4 = DhcpMapJetError(SystemParameter, "JET_paramNoInformationEvent");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 35;
    goto LABEL_17;
  }
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 5, 10, 0);
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
      goto LABEL_131;
    v6 = 36;
    goto LABEL_17;
  }
  if ( DhcpGlobalDatabaseLoggingFlag )
  {
    SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 34, 1, "on");
    v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_131;
      v6 = 37;
      goto LABEL_17;
    }
    SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 12, 30, 0);
    v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_131;
      v6 = 38;
      goto LABEL_17;
    }
    SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 13, 100, 0);
    v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) == 0 )
        goto LABEL_131;
      v6 = 39;
      goto LABEL_17;
    }
    StringCbPrintfA(pszDest, 0x104u, "%s%s", DhcpGlobalOemDatabasePath, "\\");
    do
      ++v0;
    while ( pszDest[v0] );
    OemToCharBuffA(pszDest, pszDest, v0);
    v17 = JetSetSystemParameter(&JetInstance, 0, 2, 0, pszDest);
    v4 = DhcpMapJetError(v17, "SetSysParam");
    if ( v4 )
      goto LABEL_130;
  }
  else
  {
    v20 = JetSetSystemParameter(&JetInstance, 0, 34, 0, "off");
    v4 = DhcpMapJetError(v20, "SetSysParam");
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v4;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_131;
      v19 = 40;
      goto LABEL_129;
    }
  }
  v18 = JetSetSystemParameter(&JetInstance, 0, 44, 1, 0);
  v4 = DhcpMapJetError(v18, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_131;
    v19 = 41;
    goto LABEL_129;
  }
  v21 = JetSetSystemParameter(&JetInstance, 0, 17, 1, 0);
  v4 = DhcpMapJetError(v21, "SetSysParam");
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v4;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_131;
    v19 = 42;
    goto LABEL_129;
  }
  v22 = JetSetSystemParameter(&JetInstance, 0, 52, 1, 0);
  v4 = DhcpMapJetError(v22, "SetSysParam");
  if ( !v4 )
    return v4;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v19 = 43;
LABEL_129:
    WPP_SF_(v5[2], v19, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids);
    goto LABEL_130;
  }
LABEL_131:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
    WPP_SF_D(v5[2], 44, &WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000f690  mov     [rsp-8+arg_0], rbx
0x18000f695  mov     [rsp-8+arg_8], rsi
0x18000f69a  mov     [rsp-8+arg_10], rdi
0x18000f69f  push    rbp
0x18000f6a0  push    r12
0x18000f6a2  push    r13
0x18000f6a4  push    r14
0x18000f6a6  push    r15
0x18000f6a8  lea     rbp, [rsp-60h]
0x18000f6ad  sub     rsp, 160h
0x18000f6b4  mov     rax, cs:__security_cookie
0x18000f6bb  xor     rax, rsp
0x18000f6be  mov     [rbp+80h+var_30], rax
0x18000f6c2  xor     r15d, r15d
0x18000f6c5  mov     [rsp+180h+var_150], r15
0x18000f6ca  mov     [rsp+180h+pszDest], r15b
0x18000f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6d6  lea     r12, WPP_GLOBAL_Control
0x18000f6dd  lea     r13, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000f6e4  mov     r14d, 8000h
0x18000f6ea  cmp     rcx, r12
0x18000f6ed  jz      short loc_18000F705
0x18000f6ef  test    [rcx+1Ch], r14d
0x18000f6f3  jz      short loc_18000F705
0x18000f6f5  mov     rcx, [rcx+10h]
0x18000f6f9  lea     edx, [r15+11h]
0x18000f6fd  mov     r8, r13
0x18000f700  call    WPP_SF_
0x18000f705  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000f70c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f710  mov     rax, rsi
0x18000f713  inc     rax
0x18000f716  cmp     [r9+rax], r15b
0x18000f71a  jnz     short loc_18000F713
0x18000f71c  add     rax, 2
0x18000f720  lea     rdx, asc_1800DCB80; "\\"
0x18000f727  mov     ecx, 104h
0x18000f72c  cmp     rax, rcx
0x18000f72f  jnb     short loc_18000F749
0x18000f731  mov     [rsp+180h+var_160], rdx
0x18000f736  lea     r8, aSS_0; "%s%s"
0x18000f73d  mov     edx, ecx; cbDest
0x18000f73f  lea     rcx, [rsp+180h+pszDest]; pszDest
0x18000f744  call    StringCbPrintfA
0x18000f749  lea     rax, [rsp+180h+pszDest]
0x18000f74e  mov     r8, rsi
0x18000f751  inc     r8; cchDstLength
0x18000f754  cmp     [rax+r8], r15b
0x18000f758  jnz     short loc_18000F751
0x18000f75a  lea     rdx, [rsp+180h+pszDest]; lpszDst
0x18000f75f  lea     rcx, [rsp+180h+pszDest]; lpszSrc
0x18000f764  call    cs:__imp_OemToCharBuffA
0x18000f76b  nop     dword ptr [rax+rax+00h]
0x18000f770  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f777  cmp     rcx, r12
0x18000f77a  jz      short loc_18000F798
0x18000f77c  test    [rcx+1Ch], r14d
0x18000f780  jz      short loc_18000F798
0x18000f782  mov     rcx, [rcx+10h]
0x18000f786  lea     r9, [rsp+180h+pszDest]
0x18000f78b  mov     edx, 12h
0x18000f790  mov     r8, r13
0x18000f793  call    WPP_SF_s
0x18000f798  lea     rax, [rsp+180h+pszDest]
0x18000f79d  xor     r9d, r9d
0x18000f7a0  xor     r8d, r8d
0x18000f7a3  mov     [rsp+180h+var_160], rax
0x18000f7a8  xor     edx, edx
0x18000f7aa  lea     rcx, JetInstance
0x18000f7b1  call    cs:__imp_JetSetSystemParameter
0x18000f7b8  nop     dword ptr [rax+rax+00h]
0x18000f7bd  mov     ecx, eax
0x18000f7bf  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f7c6  mov     edi, eax
0x18000f7c8  call    DhcpMapJetError
0x18000f7cd  mov     ebx, eax
0x18000f7cf  test    eax, eax
0x18000f7d1  jz      short loc_18000F806
0x18000f7d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7da  cmp     rcx, r12
0x18000f7dd  jz      loc_1800101CA
0x18000f7e3  test    [rcx+1Ch], r14d
0x18000f7e7  jz      loc_1800101AB
0x18000f7ed  mov     edx, 13h
0x18000f7f2  mov     r9d, edi
0x18000f7f5  mov     rcx, [rcx+10h]
0x18000f7f9  mov     r8, r13
0x18000f7fc  call    WPP_SF_D
0x18000f801  jmp     loc_1800101A4
0x18000f806  xor     r9d, r9d
0x18000f809  lea     rax, aJ50; "j50"
0x18000f810  xor     edx, edx
0x18000f812  mov     [rsp+180h+var_160], rax
0x18000f817  lea     rcx, JetInstance
0x18000f81e  lea     r8d, [r9+3]
0x18000f822  call    cs:__imp_JetSetSystemParameter
0x18000f829  nop     dword ptr [rax+rax+00h]
0x18000f82e  mov     ecx, eax
0x18000f830  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f837  mov     edi, eax
0x18000f839  call    DhcpMapJetError
0x18000f83e  mov     ebx, eax
0x18000f840  test    eax, eax
0x18000f842  jz      short loc_18000F865
0x18000f844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f84b  cmp     rcx, r12
0x18000f84e  jz      loc_1800101CA
0x18000f854  test    [rcx+1Ch], r14d
0x18000f858  jz      loc_1800101AB
0x18000f85e  mov     edx, 14h
0x18000f863  jmp     short loc_18000F7F2
0x18000f865  xor     edx, edx
0x18000f867  mov     [rsp+180h+var_160], r15
0x18000f86c  mov     r9d, 400h
0x18000f872  lea     rcx, JetInstance
0x18000f879  lea     r8d, [rdx+0Bh]
0x18000f87d  call    cs:__imp_JetSetSystemParameter
0x18000f884  nop     dword ptr [rax+rax+00h]
0x18000f889  mov     ecx, eax
0x18000f88b  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f892  mov     edi, eax
0x18000f894  call    DhcpMapJetError
0x18000f899  mov     ebx, eax
0x18000f89b  test    eax, eax
0x18000f89d  jz      short loc_18000F8C3
0x18000f89f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f8a6  cmp     rcx, r12
0x18000f8a9  jz      loc_1800101CA
0x18000f8af  test    [rcx+1Ch], r14d
0x18000f8b3  jz      loc_1800101AB
0x18000f8b9  mov     edx, 15h
0x18000f8be  jmp     loc_18000F7F2
0x18000f8c3  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000f8ca  lea     rax, asc_1800DCB80; "\\"
0x18000f8d1  lea     r8, aSS_0; "%s%s"
0x18000f8d8  mov     [rsp+180h+var_160], rax
0x18000f8dd  mov     edx, 104h; cbDest
0x18000f8e2  lea     rcx, [rsp+180h+pszDest]; pszDest
0x18000f8e7  call    StringCbPrintfA
0x18000f8ec  lea     rax, [rsp+180h+pszDest]
0x18000f8f1  mov     r8, rsi
0x18000f8f4  inc     r8; cchDstLength
0x18000f8f7  cmp     [rax+r8], r15b
0x18000f8fb  jnz     short loc_18000F8F4
0x18000f8fd  lea     rdx, [rsp+180h+pszDest]; lpszDst
0x18000f902  lea     rcx, [rsp+180h+pszDest]; lpszSrc
0x18000f907  call    cs:__imp_OemToCharBuffA
0x18000f90e  nop     dword ptr [rax+rax+00h]
0x18000f913  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f91a  cmp     rcx, r12
0x18000f91d  jz      short loc_18000F93B
0x18000f91f  test    [rcx+1Ch], r14d
0x18000f923  jz      short loc_18000F93B
0x18000f925  mov     rcx, [rcx+10h]
0x18000f929  lea     r9, [rsp+180h+pszDest]
0x18000f92e  mov     edx, 16h
0x18000f933  mov     r8, r13
0x18000f936  call    WPP_SF_s
0x18000f93b  xor     r9d, r9d
0x18000f93e  lea     rax, [rsp+180h+pszDest]
0x18000f943  xor     edx, edx
0x18000f945  mov     [rsp+180h+var_160], rax
0x18000f94a  lea     rcx, JetInstance
0x18000f951  lea     r8d, [r9+1]
0x18000f955  call    cs:__imp_JetSetSystemParameter
0x18000f95c  nop     dword ptr [rax+rax+00h]
0x18000f961  mov     ecx, eax
0x18000f963  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f96a  mov     edi, eax
0x18000f96c  call    DhcpMapJetError
0x18000f971  mov     ebx, eax
0x18000f973  test    eax, eax
0x18000f975  jz      short loc_18000F99B
0x18000f977  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f97e  cmp     rcx, r12
0x18000f981  jz      loc_1800101CA
0x18000f987  test    [rcx+1Ch], r14d
0x18000f98b  jz      loc_1800101AB
0x18000f991  mov     edx, 17h
0x18000f996  jmp     loc_18000F7F2
0x18000f99b  mov     rcx, cs:JetInstance
0x18000f9a2  lea     r9, [rsp+180h+var_150]
0x18000f9a7  xor     edx, edx
0x18000f9a9  mov     [rsp+180h+var_158], r15d
0x18000f9ae  mov     [rsp+180h+var_160], r15
0x18000f9b3  lea     r8d, [rdx+40h]
0x18000f9b7  call    cs:__imp_JetGetSystemParameter
0x18000f9be  nop     dword ptr [rax+rax+00h]
0x18000f9c3  mov     ecx, eax
0x18000f9c5  lea     rdx, aGetsysparam; "GetSysParam"
0x18000f9cc  mov     edi, eax
0x18000f9ce  call    DhcpMapJetError
0x18000f9d3  mov     ebx, eax
0x18000f9d5  test    eax, eax
0x18000f9d7  jz      short loc_18000F9FD
0x18000f9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9e0  cmp     rcx, r12
0x18000f9e3  jz      loc_1800101CA
0x18000f9e9  test    [rcx+1Ch], r14d
0x18000f9ed  jz      loc_1800101AB
0x18000f9f3  mov     edx, 18h
0x18000f9f8  jmp     loc_18000F7F2
0x18000f9fd  xor     edx, edx
0x18000f9ff  mov     [rsp+180h+var_160], r15
0x18000fa04  mov     eax, 6400000h
0x18000fa09  lea     rcx, JetInstance
0x18000fa10  div     [rsp+180h+var_150]
0x18000fa15  xor     edx, edx
0x18000fa17  mov     r9, rax
0x18000fa1a  lea     r8d, [rdx+3Ch]
0x18000fa1e  call    cs:__imp_JetSetSystemParameter
0x18000fa25  nop     dword ptr [rax+rax+00h]
0x18000fa2a  mov     ecx, eax
0x18000fa2c  lea     rdx, aSetsysparam; "SetSysParam"
0x18000fa33  mov     edi, eax
0x18000fa35  call    DhcpMapJetError
0x18000fa3a  mov     ebx, eax
0x18000fa3c  test    eax, eax
0x18000fa3e  jz      short loc_18000FA64
0x18000fa40  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa47  cmp     rcx, r12
0x18000fa4a  jz      loc_1800101CA
0x18000fa50  test    [rcx+1Ch], r14d
0x18000fa54  jz      loc_1800101AB
0x18000fa5a  mov     edx, 19h
0x18000fa5f  jmp     loc_18000F7F2
0x18000fa64  mov     ecx, cs:DhcpJetDatabaseMaxCacheSize
0x18000fa6a  mov     rdi, r15
0x18000fa6d  cmp     ecx, 0FFFFFFFFh
0x18000fa70  jz      loc_18000FB14
0x18000fa76  mov     edx, 2
0x18000fa7b  cmp     ecx, 2
0x18000fa7e  jb      short loc_18000FA82
0x18000fa80  mov     edx, ecx
0x18000fa82  mov     eax, 100000h
0x18000fa87  mul     rdx
0x18000fa8a  test    rdx, rdx
0x18000fa8d  jnz     short loc_18000FB0A
0x18000fa8f  div     [rsp+180h+var_150]
0x18000fa94  mov     rdi, rax
0x18000fa97  test    rax, rax
0x18000fa9a  jz      short loc_18000FB0A
0x18000fa9c  xor     edx, edx
0x18000fa9e  mov     [rsp+180h+var_160], r15
0x18000faa3  mov     r9, rax
0x18000faa6  lea     rcx, JetInstance
0x18000faad  lea     r8d, [rdx+17h]
0x18000fab1  call    cs:__imp_JetSetSystemParameter
0x18000fab8  nop     dword ptr [rax+rax+00h]
0x18000fabd  mov     ecx, eax
0x18000fabf  lea     rdx, aSetsysparam; "SetSysParam"
0x18000fac6  mov     r14d, eax
0x18000fac9  call    DhcpMapJetError
0x18000face  mov     ebx, eax
0x18000fad0  test    eax, eax
0x18000fad2  jz      short loc_18000FAFE
0x18000fad4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fadb  cmp     rcx, r12
0x18000fade  jz      loc_1800101CA
0x18000fae4  test    dword ptr [rcx+1Ch], 8000h
0x18000faeb  jz      loc_1800101AB
0x18000faf1  mov     edx, 1Ah
0x18000faf6  mov     r9d, r14d
0x18000faf9  jmp     loc_18000F7F5
0x18000fafe  mov     ecx, cs:DhcpJetDatabaseMaxCacheSize
0x18000fb04  mov     r14d, 8000h
0x18000fb0a  cmp     ecx, 0FFFFFFFFh
0x18000fb0d  jz      short loc_18000FB14
0x18000fb0f  test    rdi, rdi
0x18000fb12  jnz     short loc_18000FB37
0x18000fb14  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb1b  cmp     rcx, r12
0x18000fb1e  jz      short loc_18000FB37
0x18000fb20  test    [rcx+1Ch], r14d
0x18000fb24  jz      short loc_18000FB37
0x18000fb26  mov     rcx, [rcx+10h]
0x18000fb2a  mov     edx, 1Bh
0x18000fb2f  mov     r8, r13
0x18000fb32  call    WPP_SF_
0x18000fb37  xor     edx, edx
0x18000fb39  mov     [rsp+180h+var_160], r15
0x18000fb3e  mov     r9d, 5DCh
0x18000fb44  lea     rcx, JetInstance
0x18000fb4b  lea     r8d, [rdx+9]
0x18000fb4f  call    cs:__imp_JetSetSystemParameter
0x18000fb56  nop     dword ptr [rax+rax+00h]
0x18000fb5b  mov     ecx, eax
0x18000fb5d  lea     rdx, aSetsysparam; "SetSysParam"
0x18000fb64  mov     r14d, eax
0x18000fb67  call    DhcpMapJetError
0x18000fb6c  mov     ebx, eax
0x18000fb6e  test    eax, eax
0x18000fb70  jz      short loc_18000FB99
0x18000fb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb79  cmp     rcx, r12
0x18000fb7c  jz      loc_1800101CA
0x18000fb82  test    dword ptr [rcx+1Ch], 8000h
0x18000fb89  jz      loc_1800101AB
0x18000fb8f  mov     edx, 1Ch
0x18000fb94  jmp     loc_18000FAF6
  ... truncated ...
```
