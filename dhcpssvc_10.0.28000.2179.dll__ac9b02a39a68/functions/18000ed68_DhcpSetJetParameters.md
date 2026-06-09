# DhcpSetJetParameters

- ea: `0x18000ed68`
- end: `0x18000f8d2`
- name: `DhcpSetJetParameters`
- size: `2922`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d644`
- `0x18000eb90`
- `0x180012910`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18000c164`
- `0x18000e814`
- `0x18000ed68`
- `0x180010a14`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetGetSystemParameter` at `0x18000f08f`
- `ESENT!JetGetSystemParameter` at `0x18000f08f`
- `ESENT!JetSetSystemParameter` at `0x18000ee89`
- `ESENT!JetSetSystemParameter` at `0x18000eefa`
- `ESENT!JetSetSystemParameter` at `0x18000ef55`
- `ESENT!JetSetSystemParameter` at `0x18000f02d`
- `ESENT!JetSetSystemParameter` at `0x18000f0f6`
- `ESENT!JetSetSystemParameter` at `0x18000f189`
- `ESENT!JetSetSystemParameter` at `0x18000f227`
- `ESENT!JetSetSystemParameter` at `0x18000f287`
- `ESENT!JetSetSystemParameter` at `0x18000f2e7`
- `ESENT!JetSetSystemParameter` at `0x18000f347`
- `ESENT!JetSetSystemParameter` at `0x18000f3d6`
- `ESENT!JetSetSystemParameter` at `0x18000f436`
- `ESENT!JetSetSystemParameter` at `0x18000f4c6`
- `ESENT!JetSetSystemParameter` at `0x18000f522`
- `ESENT!JetSetSystemParameter` at `0x18000f592`
- `ESENT!JetSetSystemParameter` at `0x18000f5ee`
- `ESENT!JetSetSystemParameter` at `0x18000f64a`
- `ESENT!JetSetSystemParameter` at `0x18000f6fd`
- `ESENT!JetSetSystemParameter` at `0x18000f73b`
- `ESENT!JetSetSystemParameter` at `0x18000f797`
- `ESENT!JetSetSystemParameter` at `0x18000f7f3`
- `ESENT!JetSetSystemParameter` at `0x18000f83d`
- `ESENT!JetSetSystemParameter` at `0x18000ee89`
- `ESENT!JetSetSystemParameter` at `0x18000eefa`
- `ESENT!JetSetSystemParameter` at `0x18000ef55`
- `ESENT!JetSetSystemParameter` at `0x18000f02d`
- `ESENT!JetSetSystemParameter` at `0x18000f0f6`
- `ESENT!JetSetSystemParameter` at `0x18000f189`
- `ESENT!JetSetSystemParameter` at `0x18000f227`
- `ESENT!JetSetSystemParameter` at `0x18000f287`
- `ESENT!JetSetSystemParameter` at `0x18000f2e7`
- `ESENT!JetSetSystemParameter` at `0x18000f347`
- `ESENT!JetSetSystemParameter` at `0x18000f3d6`
- `ESENT!JetSetSystemParameter` at `0x18000f436`
- `ESENT!JetSetSystemParameter` at `0x18000f4c6`
- `ESENT!JetSetSystemParameter` at `0x18000f522`
- `ESENT!JetSetSystemParameter` at `0x18000f592`
- `ESENT!JetSetSystemParameter` at `0x18000f5ee`
- `ESENT!JetSetSystemParameter` at `0x18000f64a`
- `ESENT!JetSetSystemParameter` at `0x18000f6fd`
- `ESENT!JetSetSystemParameter` at `0x18000f73b`
- `ESENT!JetSetSystemParameter` at `0x18000f797`
- `ESENT!JetSetSystemParameter` at `0x18000f7f3`
- `ESENT!JetSetSystemParameter` at `0x18000f83d`
- `USER32!OemToCharBuffA` at `0x18000ee3c`
- `USER32!OemToCharBuffA` at `0x18000efdf`
- `USER32!OemToCharBuffA` at `0x18000f6d4`
- `USER32!OemToCharBuffA` at `0x18000ee3c`
- `USER32!OemToCharBuffA` at `0x18000efdf`
- `USER32!OemToCharBuffA` at `0x18000f6d4`

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
  SystemParameter = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 60, 0x6400000 / v24, 0);
  v4 = DhcpMapJetError(SystemParameter, "SetSysParam");
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
      v15 = (unsigned int)JetSetSystemParameter(&JetInstance, 0, 23, v14, 0);
      v4 = DhcpMapJetError(v15, "SetSysParam");
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
0x18000ed68  mov     [rsp-8+arg_0], rbx
0x18000ed6d  mov     [rsp-8+arg_8], rsi
0x18000ed72  mov     [rsp-8+arg_10], rdi
0x18000ed77  push    rbp
0x18000ed78  push    r12
0x18000ed7a  push    r13
0x18000ed7c  push    r14
0x18000ed7e  push    r15
0x18000ed80  lea     rbp, [rsp-60h]
0x18000ed85  sub     rsp, 160h
0x18000ed8c  mov     rax, cs:__security_cookie
0x18000ed93  xor     rax, rsp
0x18000ed96  mov     [rbp+80h+var_30], rax
0x18000ed9a  xor     r15d, r15d
0x18000ed9d  mov     [rsp+180h+var_150], r15
0x18000eda2  mov     [rsp+180h+pszDest], r15b
0x18000eda7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edae  lea     r12, WPP_GLOBAL_Control
0x18000edb5  lea     r13, WPP_7081cca1e2663faba6bfa446ec4ef913_Traceguids
0x18000edbc  mov     r14d, 8000h
0x18000edc2  cmp     rcx, r12
0x18000edc5  jz      short loc_18000EDDD
0x18000edc7  test    [rcx+1Ch], r14d
0x18000edcb  jz      short loc_18000EDDD
0x18000edcd  mov     rcx, [rcx+10h]
0x18000edd1  lea     edx, [r15+11h]
0x18000edd5  mov     r8, r13
0x18000edd8  call    WPP_SF_
0x18000eddd  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000ede4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ede8  mov     rax, rsi
0x18000edeb  inc     rax
0x18000edee  cmp     [r9+rax], r15b
0x18000edf2  jnz     short loc_18000EDEB
0x18000edf4  add     rax, 2
0x18000edf8  lea     rdx, asc_1800DEB20; "\\"
0x18000edff  mov     ecx, 104h
0x18000ee04  cmp     rax, rcx
0x18000ee07  jnb     short loc_18000EE21
0x18000ee09  mov     [rsp+180h+var_160], rdx
0x18000ee0e  lea     r8, aSS_0; "%s%s"
0x18000ee15  mov     edx, ecx; cbDest
0x18000ee17  lea     rcx, [rsp+180h+pszDest]; pszDest
0x18000ee1c  call    StringCbPrintfA
0x18000ee21  lea     rax, [rsp+180h+pszDest]
0x18000ee26  mov     r8, rsi
0x18000ee29  inc     r8; cchDstLength
0x18000ee2c  cmp     [rax+r8], r15b
0x18000ee30  jnz     short loc_18000EE29
0x18000ee32  lea     rdx, [rsp+180h+pszDest]; lpszDst
0x18000ee37  lea     rcx, [rsp+180h+pszDest]; lpszSrc
0x18000ee3c  call    cs:__imp_OemToCharBuffA
0x18000ee43  nop     dword ptr [rax+rax+00h]
0x18000ee48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee4f  cmp     rcx, r12
0x18000ee52  jz      short loc_18000EE70
0x18000ee54  test    [rcx+1Ch], r14d
0x18000ee58  jz      short loc_18000EE70
0x18000ee5a  mov     rcx, [rcx+10h]
0x18000ee5e  lea     r9, [rsp+180h+pszDest]
0x18000ee63  mov     edx, 12h
0x18000ee68  mov     r8, r13
0x18000ee6b  call    WPP_SF_s
0x18000ee70  lea     rax, [rsp+180h+pszDest]
0x18000ee75  xor     r9d, r9d
0x18000ee78  xor     r8d, r8d
0x18000ee7b  mov     [rsp+180h+var_160], rax
0x18000ee80  xor     edx, edx
0x18000ee82  lea     rcx, JetInstance
0x18000ee89  call    cs:__imp_JetSetSystemParameter
0x18000ee90  nop     dword ptr [rax+rax+00h]
0x18000ee95  mov     ecx, eax
0x18000ee97  lea     rdx, aSetsysparam; "SetSysParam"
0x18000ee9e  mov     edi, eax
0x18000eea0  call    DhcpMapJetError
0x18000eea5  mov     ebx, eax
0x18000eea7  test    eax, eax
0x18000eea9  jz      short loc_18000EEDE
0x18000eeab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeb2  cmp     rcx, r12
0x18000eeb5  jz      loc_18000F8A2
0x18000eebb  test    [rcx+1Ch], r14d
0x18000eebf  jz      loc_18000F883
0x18000eec5  mov     edx, 13h
0x18000eeca  mov     r9d, edi
0x18000eecd  mov     rcx, [rcx+10h]
0x18000eed1  mov     r8, r13
0x18000eed4  call    WPP_SF_D
0x18000eed9  jmp     loc_18000F87C
0x18000eede  xor     r9d, r9d
0x18000eee1  lea     rax, aJ50; "j50"
0x18000eee8  xor     edx, edx
0x18000eeea  mov     [rsp+180h+var_160], rax
0x18000eeef  lea     rcx, JetInstance
0x18000eef6  lea     r8d, [r9+3]
0x18000eefa  call    cs:__imp_JetSetSystemParameter
0x18000ef01  nop     dword ptr [rax+rax+00h]
0x18000ef06  mov     ecx, eax
0x18000ef08  lea     rdx, aSetsysparam; "SetSysParam"
0x18000ef0f  mov     edi, eax
0x18000ef11  call    DhcpMapJetError
0x18000ef16  mov     ebx, eax
0x18000ef18  test    eax, eax
0x18000ef1a  jz      short loc_18000EF3D
0x18000ef1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef23  cmp     rcx, r12
0x18000ef26  jz      loc_18000F8A2
0x18000ef2c  test    [rcx+1Ch], r14d
0x18000ef30  jz      loc_18000F883
0x18000ef36  mov     edx, 14h
0x18000ef3b  jmp     short loc_18000EECA
0x18000ef3d  xor     edx, edx
0x18000ef3f  mov     [rsp+180h+var_160], r15
0x18000ef44  mov     r9d, 400h
0x18000ef4a  lea     rcx, JetInstance
0x18000ef51  lea     r8d, [rdx+0Bh]
0x18000ef55  call    cs:__imp_JetSetSystemParameter
0x18000ef5c  nop     dword ptr [rax+rax+00h]
0x18000ef61  mov     ecx, eax
0x18000ef63  lea     rdx, aSetsysparam; "SetSysParam"
0x18000ef6a  mov     edi, eax
0x18000ef6c  call    DhcpMapJetError
0x18000ef71  mov     ebx, eax
0x18000ef73  test    eax, eax
0x18000ef75  jz      short loc_18000EF9B
0x18000ef77  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef7e  cmp     rcx, r12
0x18000ef81  jz      loc_18000F8A2
0x18000ef87  test    [rcx+1Ch], r14d
0x18000ef8b  jz      loc_18000F883
0x18000ef91  mov     edx, 15h
0x18000ef96  jmp     loc_18000EECA
0x18000ef9b  mov     r9, cs:DhcpGlobalOemDatabasePath
0x18000efa2  lea     rax, asc_1800DEB20; "\\"
0x18000efa9  lea     r8, aSS_0; "%s%s"
0x18000efb0  mov     [rsp+180h+var_160], rax
0x18000efb5  mov     edx, 104h; cbDest
0x18000efba  lea     rcx, [rsp+180h+pszDest]; pszDest
0x18000efbf  call    StringCbPrintfA
0x18000efc4  lea     rax, [rsp+180h+pszDest]
0x18000efc9  mov     r8, rsi
0x18000efcc  inc     r8; cchDstLength
0x18000efcf  cmp     [rax+r8], r15b
0x18000efd3  jnz     short loc_18000EFCC
0x18000efd5  lea     rdx, [rsp+180h+pszDest]; lpszDst
0x18000efda  lea     rcx, [rsp+180h+pszDest]; lpszSrc
0x18000efdf  call    cs:__imp_OemToCharBuffA
0x18000efe6  nop     dword ptr [rax+rax+00h]
0x18000efeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eff2  cmp     rcx, r12
0x18000eff5  jz      short loc_18000F013
0x18000eff7  test    [rcx+1Ch], r14d
0x18000effb  jz      short loc_18000F013
0x18000effd  mov     rcx, [rcx+10h]
0x18000f001  lea     r9, [rsp+180h+pszDest]
0x18000f006  mov     edx, 16h
0x18000f00b  mov     r8, r13
0x18000f00e  call    WPP_SF_s
0x18000f013  xor     r9d, r9d
0x18000f016  lea     rax, [rsp+180h+pszDest]
0x18000f01b  xor     edx, edx
0x18000f01d  mov     [rsp+180h+var_160], rax
0x18000f022  lea     rcx, JetInstance
0x18000f029  lea     r8d, [r9+1]
0x18000f02d  call    cs:__imp_JetSetSystemParameter
0x18000f034  nop     dword ptr [rax+rax+00h]
0x18000f039  mov     ecx, eax
0x18000f03b  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f042  mov     edi, eax
0x18000f044  call    DhcpMapJetError
0x18000f049  mov     ebx, eax
0x18000f04b  test    eax, eax
0x18000f04d  jz      short loc_18000F073
0x18000f04f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f056  cmp     rcx, r12
0x18000f059  jz      loc_18000F8A2
0x18000f05f  test    [rcx+1Ch], r14d
0x18000f063  jz      loc_18000F883
0x18000f069  mov     edx, 17h
0x18000f06e  jmp     loc_18000EECA
0x18000f073  mov     rcx, cs:JetInstance
0x18000f07a  lea     r9, [rsp+180h+var_150]
0x18000f07f  xor     edx, edx
0x18000f081  mov     [rsp+180h+var_158], r15d
0x18000f086  mov     [rsp+180h+var_160], r15
0x18000f08b  lea     r8d, [rdx+40h]
0x18000f08f  call    cs:__imp_JetGetSystemParameter
0x18000f096  nop     dword ptr [rax+rax+00h]
0x18000f09b  mov     ecx, eax
0x18000f09d  lea     rdx, aGetsysparam; "GetSysParam"
0x18000f0a4  mov     edi, eax
0x18000f0a6  call    DhcpMapJetError
0x18000f0ab  mov     ebx, eax
0x18000f0ad  test    eax, eax
0x18000f0af  jz      short loc_18000F0D5
0x18000f0b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0b8  cmp     rcx, r12
0x18000f0bb  jz      loc_18000F8A2
0x18000f0c1  test    [rcx+1Ch], r14d
0x18000f0c5  jz      loc_18000F883
0x18000f0cb  mov     edx, 18h
0x18000f0d0  jmp     loc_18000EECA
0x18000f0d5  xor     edx, edx
0x18000f0d7  mov     [rsp+180h+var_160], r15
0x18000f0dc  mov     eax, 6400000h
0x18000f0e1  lea     rcx, JetInstance
0x18000f0e8  div     [rsp+180h+var_150]
0x18000f0ed  xor     edx, edx
0x18000f0ef  mov     r9, rax
0x18000f0f2  lea     r8d, [rdx+3Ch]
0x18000f0f6  call    cs:__imp_JetSetSystemParameter
0x18000f0fd  nop     dword ptr [rax+rax+00h]
0x18000f102  mov     ecx, eax
0x18000f104  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f10b  mov     edi, eax
0x18000f10d  call    DhcpMapJetError
0x18000f112  mov     ebx, eax
0x18000f114  test    eax, eax
0x18000f116  jz      short loc_18000F13C
0x18000f118  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f11f  cmp     rcx, r12
0x18000f122  jz      loc_18000F8A2
0x18000f128  test    [rcx+1Ch], r14d
0x18000f12c  jz      loc_18000F883
0x18000f132  mov     edx, 19h
0x18000f137  jmp     loc_18000EECA
0x18000f13c  mov     ecx, cs:DhcpJetDatabaseMaxCacheSize
0x18000f142  mov     rdi, r15
0x18000f145  cmp     ecx, 0FFFFFFFFh
0x18000f148  jz      loc_18000F1EC
0x18000f14e  mov     edx, 2
0x18000f153  cmp     ecx, 2
0x18000f156  jb      short loc_18000F15A
0x18000f158  mov     edx, ecx
0x18000f15a  mov     eax, 100000h
0x18000f15f  mul     rdx
0x18000f162  test    rdx, rdx
0x18000f165  jnz     short loc_18000F1E2
0x18000f167  div     [rsp+180h+var_150]
0x18000f16c  mov     rdi, rax
0x18000f16f  test    rax, rax
0x18000f172  jz      short loc_18000F1E2
0x18000f174  xor     edx, edx
0x18000f176  mov     [rsp+180h+var_160], r15
0x18000f17b  mov     r9, rax
0x18000f17e  lea     rcx, JetInstance
0x18000f185  lea     r8d, [rdx+17h]
0x18000f189  call    cs:__imp_JetSetSystemParameter
0x18000f190  nop     dword ptr [rax+rax+00h]
0x18000f195  mov     ecx, eax
0x18000f197  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f19e  mov     r14d, eax
0x18000f1a1  call    DhcpMapJetError
0x18000f1a6  mov     ebx, eax
0x18000f1a8  test    eax, eax
0x18000f1aa  jz      short loc_18000F1D6
0x18000f1ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1b3  cmp     rcx, r12
0x18000f1b6  jz      loc_18000F8A2
0x18000f1bc  test    dword ptr [rcx+1Ch], 8000h
0x18000f1c3  jz      loc_18000F883
0x18000f1c9  mov     edx, 1Ah
0x18000f1ce  mov     r9d, r14d
0x18000f1d1  jmp     loc_18000EECD
0x18000f1d6  mov     ecx, cs:DhcpJetDatabaseMaxCacheSize
0x18000f1dc  mov     r14d, 8000h
0x18000f1e2  cmp     ecx, 0FFFFFFFFh
0x18000f1e5  jz      short loc_18000F1EC
0x18000f1e7  test    rdi, rdi
0x18000f1ea  jnz     short loc_18000F20F
0x18000f1ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1f3  cmp     rcx, r12
0x18000f1f6  jz      short loc_18000F20F
0x18000f1f8  test    [rcx+1Ch], r14d
0x18000f1fc  jz      short loc_18000F20F
0x18000f1fe  mov     rcx, [rcx+10h]
0x18000f202  mov     edx, 1Bh
0x18000f207  mov     r8, r13
0x18000f20a  call    WPP_SF_
0x18000f20f  xor     edx, edx
0x18000f211  mov     [rsp+180h+var_160], r15
0x18000f216  mov     r9d, 5DCh
0x18000f21c  lea     rcx, JetInstance
0x18000f223  lea     r8d, [rdx+9]
0x18000f227  call    cs:__imp_JetSetSystemParameter
0x18000f22e  nop     dword ptr [rax+rax+00h]
0x18000f233  mov     ecx, eax
0x18000f235  lea     rdx, aSetsysparam; "SetSysParam"
0x18000f23c  mov     r14d, eax
0x18000f23f  call    DhcpMapJetError
0x18000f244  mov     ebx, eax
0x18000f246  test    eax, eax
0x18000f248  jz      short loc_18000F271
0x18000f24a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f251  cmp     rcx, r12
0x18000f254  jz      loc_18000F8A2
0x18000f25a  test    dword ptr [rcx+1Ch], 8000h
0x18000f261  jz      loc_18000F883
0x18000f267  mov     edx, 1Ch
0x18000f26c  jmp     loc_18000F1CE
  ... truncated ...
```
