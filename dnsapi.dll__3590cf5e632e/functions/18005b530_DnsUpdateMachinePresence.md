# DnsUpdateMachinePresence

- ea: `0x18005b530`
- end: `0x18005b9b1`
- name: `DnsUpdateMachinePresence`
- size: `1153`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180070ba0`
- `0x180090be0`
- `0x18009e728`

## callees

- `0x18005b530`
- `0x18005b9b8`
- `0x18005ba70`
- `0x18005bb30`
- `0x18005bc74`
- `0x180083954`
- `0x180084c4c`
- `0x18008b5f0`
- `0x1800d3cac`
- `0x1800dc038`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b926`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005b926`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b973`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005b973`
- `NSI!NsiFreeTable` at `0x18005b733`
- `NSI!NsiFreeTable` at `0x18005b90b`
- `NSI!NsiFreeTable` at `0x18005b733`
- `NSI!NsiFreeTable` at `0x18005b90b`
- `NSI!NsiAllocateAndGetTable` at `0x18005b60c`
- `NSI!NsiAllocateAndGetTable` at `0x18005b795`
- `NSI!NsiAllocateAndGetTable` at `0x18005b60c`
- `NSI!NsiAllocateAndGetTable` at `0x18005b795`

## string_xrefs

- `0x18005b8d3`: `outside`
- `0x18005b8da`: `inside`

## pseudocode

```c
__int64 DnsUpdateMachinePresence()
{
  unsigned int v0; // esi
  __int64 v1; // rcx
  unsigned int v3; // r14d
  char v4; // bl
  char v5; // r13
  char v6; // di
  unsigned int Table; // eax
  unsigned int v8; // r12d
  char v9; // cl
  __int64 v10; // r15
  unsigned __int8 v11; // al
  unsigned int v12; // eax
  unsigned int v13; // r15d
  char v14; // cl
  __int64 v15; // r12
  unsigned __int8 v16; // al
  __int64 v17; // rcx
  const wchar_t *v18; // rax
  const wchar_t *v19; // r9
  int v20; // [rsp+60h] [rbp-29h]
  unsigned __int8 v21; // [rsp+70h] [rbp-19h]
  unsigned __int8 v22; // [rsp+70h] [rbp-19h]
  unsigned int v23; // [rsp+78h] [rbp-11h]
  __int64 v24; // [rsp+80h] [rbp-9h] BYREF
  __int64 v25; // [rsp+88h] [rbp-1h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+7h] BYREF
  LPCSTR retaddr; // [rsp+E8h] [rbp+5Fh]

  v0 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 36, WPP_85172e4714023e67c3665ec5069963d4_Traceguids);
  if ( g_fVelocitySuppressInternalExports && !g_DnsIsCache && !(unsigned int)Dns_IsCallerDns(retaddr) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v1);
    return 120;
  }
  v3 = 0;
  v4 = 1;
  v5 = 0;
  v6 = 1;
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v24, 8, &v25, 240, 0, 0, 0, 0, &v26, 0);
  v23 = Table;
  v8 = Table;
  if ( Table )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_d(1035, 37, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, Table);
  }
  else if ( v26 )
  {
    do
    {
      v9 = 0;
      v10 = 240LL * v0;
      if ( *(_DWORD *)(v10 + v25 + 168) != 1 )
        v9 = v4;
      v4 = v9;
      if ( *(_BYTE *)(v10 + v25 + 165) )
        v5 = 1;
      v21 = IsInterfaceConnected(v24 + 8LL * v0);
      v11 = IsInterfaceVirtual(v24 + 8LL * v0);
      if ( v21 && !v11 && *(_DWORD *)(v10 + v25 + 16) != 1 )
        v6 = 0;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_idddd(
          v21,
          38,
          *(unsigned __int8 *)(v10 + v25 + 165),
          *(_QWORD *)(v24 + 8LL * v0),
          *(_DWORD *)(v10 + v25 + 168),
          *(unsigned __int8 *)(v10 + v25 + 165),
          v21,
          v11);
      ++v0;
    }
    while ( v0 < v26 );
    v3 = 0;
    v0 = 0;
  }
  NsiFreeTable(v24, v25, 0, 0);
  LOBYTE(v20) = 0;
  v24 = 0;
  v25 = 0;
  v12 = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, &v24, 8, &v25, 240, 0, 0, 0, 0, &v26, v20);
  v13 = v12;
  if ( v12 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_45;
    WPP_SF_d(1035, 39, WPP_85172e4714023e67c3665ec5069963d4_Traceguids, v12);
  }
  else if ( v26 )
  {
    do
    {
      v14 = 0;
      v15 = 240LL * v0;
      if ( *(_DWORD *)(v15 + v25 + 168) != 1 )
        v14 = v4;
      v4 = v14;
      if ( *(_BYTE *)(v15 + v25 + 165) )
        v5 = 1;
      v22 = IsInterfaceConnected(v24 + 8LL * v0);
      v16 = IsInterfaceVirtual(v24 + 8LL * v0);
      if ( v22 )
      {
        if ( !v16 )
        {
          v17 = v25;
          if ( *(_DWORD *)(v15 + v25 + 16) != 1 )
            v6 = 0;
        }
      }
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_idddd(
          v17,
          40,
          *(unsigned __int8 *)(v15 + v25 + 165),
          *(_QWORD *)(v24 + 8LL * v0),
          *(_DWORD *)(v15 + v25 + 168),
          *(unsigned __int8 *)(v15 + v25 + 165),
          v22,
          v16);
      ++v0;
    }
    while ( v0 < v26 );
    v3 = 0;
    v8 = v23;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    v18 = L"in private network";
    if ( !v6 )
      v18 = L"not in private network";
    v19 = L"outside";
    if ( !v4 )
      v19 = L"inside";
    WPP_SF_SS(1035, 41, (unsigned int)WPP_85172e4714023e67c3665ec5069963d4_Traceguids, (_DWORD)v19, (__int64)v18);
  }
LABEL_45:
  NsiFreeTable(v24, v25, 0, 0);
  v24 = 0;
  v25 = 0;
  AcquireSRWLockExclusive(&g_DnsPolicyTableLock);
  if ( byte_180111F7A != v4 || byte_180111F7B != v5 )
  {
    byte_180111F7A = v4;
    byte_180111F7B = v5;
    FlushDnsPolicyUnreachableStatusUnlocked();
    goto LABEL_50;
  }
  if ( byte_180111F7C != v6 )
  {
    byte_180111F7C = v6;
LABEL_50:
    RefreshDirectAccessStatePrivate();
  }
  ReleaseSRWLockExclusive(&g_DnsPolicyTableLock);
  if ( v8 )
    v3 = v8;
  if ( v13 )
    return v13;
  return v3;
}

```

## disassembly

```asm
0x18005b530  push    rbp
0x18005b532  push    rbx
0x18005b533  push    rsi
0x18005b534  push    rdi
0x18005b535  push    r12
0x18005b537  push    r13
0x18005b539  push    r14
0x18005b53b  push    r15
0x18005b53d  lea     rbp, [rsp-1Fh]
0x18005b542  sub     rsp, 0A8h
0x18005b549  mov     rax, cs:__security_cookie
0x18005b550  xor     rax, rsp
0x18005b553  mov     [rbp+57h+var_48], rax
0x18005b557  xor     esi, esi
0x18005b559  mov     [rbp+57h+var_60], rsi
0x18005b55d  mov     [rbp+57h+var_58], rsi
0x18005b561  mov     [rbp+57h+var_50], esi
0x18005b564  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b56b  mov     r15d, 40Bh
0x18005b571  jz      short loc_18005B585
0x18005b573  lea     edx, [rsi+24h]
0x18005b576  mov     ecx, r15d
0x18005b579  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18005b580  call    WPP_SF_
0x18005b585  cmp     cs:g_fVelocitySuppressInternalExports, esi
0x18005b58b  jz      short loc_18005B5B1
0x18005b58d  cmp     cs:g_DnsIsCache, esi
0x18005b593  jnz     short loc_18005B5B1
0x18005b595  mov     rcx, [rbp+5Fh]; lpModuleName
0x18005b599  call    Dns_IsCallerDns
0x18005b59e  test    eax, eax
0x18005b5a0  jnz     short loc_18005B5B1
0x18005b5a2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005b5a7  mov     eax, 78h ; 'x'
0x18005b5ac  jmp     loc_18005B990
0x18005b5b1  mov     byte ptr [rsp+0E0h+var_80], sil
0x18005b5b6  lea     rax, [rbp+57h+var_50]
0x18005b5ba  mov     [rsp+0E0h+var_88], rax
0x18005b5bf  lea     r9, [rbp+57h+var_60]
0x18005b5c3  mov     [rsp+0E0h+var_90], esi
0x18005b5c7  lea     rax, [rbp+57h+var_58]
0x18005b5cb  mov     [rsp+0E0h+var_98], rsi
0x18005b5d0  lea     rdx, NPI_MS_IPV6_MODULEID
0x18005b5d7  mov     ecx, 1
0x18005b5dc  mov     [rsp+0E0h+var_A0], esi
0x18005b5e0  mov     [rsp+0E0h+var_A8], rsi
0x18005b5e5  mov     r14d, esi
0x18005b5e8  mov     [rsp+0E0h+var_B0], 0F0h
0x18005b5f0  mov     bl, cl
0x18005b5f2  mov     [rsp+0E0h+var_B8], rax
0x18005b5f7  mov     r13b, sil
0x18005b5fa  lea     r8d, [rcx+6]
0x18005b5fe  mov     dword ptr [rsp+0E0h+var_C0], 8
0x18005b606  mov     [rbp+57h+var_6C], esi
0x18005b609  mov     dil, cl
0x18005b60c  call    cs:__imp_NsiAllocateAndGetTable
0x18005b613  nop     dword ptr [rax+rax+00h]
0x18005b618  mov     [rbp+57h+var_68], eax
0x18005b61b  mov     r12d, eax
0x18005b61e  test    eax, eax
0x18005b620  jz      short loc_18005B64B
0x18005b622  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b629  jz      loc_18005B725
0x18005b62f  mov     edx, 25h ; '%'
0x18005b634  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18005b63b  mov     ecx, r15d
0x18005b63e  mov     r9d, eax
0x18005b641  call    WPP_SF_d
0x18005b646  jmp     loc_18005B725
0x18005b64b  cmp     [rbp+57h+var_50], esi
0x18005b64e  jbe     loc_18005B725
0x18005b654  mov     r14d, 1
0x18005b65a  mov     rdx, [rbp+57h+var_58]
0x18005b65e  xor     ecx, ecx
0x18005b660  mov     r8d, esi
0x18005b663  imul    r15, r8, 0F0h
0x18005b66a  movzx   eax, bl
0x18005b66d  movzx   r13d, r13b
0x18005b671  cmp     [r15+rdx+0A8h], r14d
0x18005b679  cmovnz  ecx, eax
0x18005b67c  mov     rax, [rbp+57h+var_60]
0x18005b680  cmp     byte ptr [r15+rdx+0A5h], 0
0x18005b689  mov     bl, cl
0x18005b68b  cmovnz  r13d, r14d
0x18005b68f  lea     rcx, [rax+r8*8]
0x18005b693  call    IsInterfaceConnected
0x18005b698  mov     rcx, [rbp+57h+var_60]
0x18005b69c  mov     edx, esi
0x18005b69e  mov     [rbp+57h+var_70], al
0x18005b6a1  lea     rcx, [rcx+rdx*8]
0x18005b6a5  call    IsInterfaceVirtual
0x18005b6aa  movzx   r8d, [rbp+57h+var_70]
0x18005b6af  test    r8b, r8b
0x18005b6b2  jz      short loc_18005B6CA
0x18005b6b4  test    al, al
0x18005b6b6  jnz     short loc_18005B6CA
0x18005b6b8  mov     rcx, [rbp+57h+var_58]
0x18005b6bc  xor     edx, edx
0x18005b6be  movzx   edi, dil
0x18005b6c2  cmp     [r15+rcx+10h], r14d
0x18005b6c7  cmovnz  edi, edx
0x18005b6ca  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b6d1  jz      short loc_18005B713
0x18005b6d3  mov     r9, [rbp+57h+var_58]
0x18005b6d7  mov     ecx, r8d
0x18005b6da  movzx   eax, al
0x18005b6dd  mov     edx, 26h ; '&'
0x18005b6e2  mov     dword ptr [rsp+0E0h+var_A8], eax
0x18005b6e6  mov     [rsp+0E0h+var_B0], ecx
0x18005b6ea  mov     eax, [r15+r9+0A8h]
0x18005b6f2  movzx   r8d, byte ptr [r15+r9+0A5h]
0x18005b6fb  mov     r9, [rbp+57h+var_60]
0x18005b6ff  mov     dword ptr [rsp+0E0h+var_B8], r8d
0x18005b704  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18005b708  mov     eax, esi
0x18005b70a  mov     r9, [r9+rax*8]
0x18005b70e  call    WPP_SF_idddd
0x18005b713  add     esi, r14d
0x18005b716  cmp     esi, [rbp+57h+var_50]
0x18005b719  jb      loc_18005B65A
0x18005b71f  mov     r14d, [rbp+57h+var_6C]
0x18005b723  xor     esi, esi
0x18005b725  mov     rdx, [rbp+57h+var_58]
0x18005b729  xor     r9d, r9d
0x18005b72c  mov     rcx, [rbp+57h+var_60]
0x18005b730  xor     r8d, r8d
0x18005b733  call    cs:__imp_NsiFreeTable
0x18005b73a  nop     dword ptr [rax+rax+00h]
0x18005b73f  mov     byte ptr [rsp+0E0h+var_80], sil
0x18005b744  lea     rax, [rbp+57h+var_50]
0x18005b748  mov     [rsp+0E0h+var_88], rax
0x18005b74d  lea     r9, [rbp+57h+var_60]
0x18005b751  mov     [rsp+0E0h+var_90], esi
0x18005b755  lea     rax, [rbp+57h+var_58]
0x18005b759  mov     [rsp+0E0h+var_98], rsi
0x18005b75e  lea     rdx, NPI_MS_IPV4_MODULEID
0x18005b765  mov     [rsp+0E0h+var_A0], esi
0x18005b769  mov     r8d, 7
0x18005b76f  mov     [rsp+0E0h+var_A8], rsi
0x18005b774  mov     [rsp+0E0h+var_B0], 0F0h
0x18005b77c  mov     [rsp+0E0h+var_B8], rax
0x18005b781  lea     ecx, [r8-6]
0x18005b785  mov     dword ptr [rsp+0E0h+var_C0], 8
0x18005b78d  mov     [rbp+57h+var_60], rsi
0x18005b791  mov     [rbp+57h+var_58], rsi
0x18005b795  call    cs:__imp_NsiAllocateAndGetTable
0x18005b79c  nop     dword ptr [rax+rax+00h]
0x18005b7a1  mov     r15d, eax
0x18005b7a4  test    eax, eax
0x18005b7a6  jz      short loc_18005B7D3
0x18005b7a8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b7af  jz      loc_18005B8FD
0x18005b7b5  mov     edx, 27h ; '''
0x18005b7ba  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18005b7c1  mov     ecx, 40Bh
0x18005b7c6  mov     r9d, eax
0x18005b7c9  call    WPP_SF_d
0x18005b7ce  jmp     loc_18005B8B0
0x18005b7d3  cmp     [rbp+57h+var_50], 0
0x18005b7d7  jbe     loc_18005B8AE
0x18005b7dd  mov     r14d, 1
0x18005b7e3  mov     rdx, [rbp+57h+var_58]
0x18005b7e7  xor     ecx, ecx
0x18005b7e9  mov     r8d, esi
0x18005b7ec  imul    r12, r8, 0F0h
0x18005b7f3  movzx   eax, bl
0x18005b7f6  movzx   r13d, r13b
0x18005b7fa  cmp     [r12+rdx+0A8h], r14d
0x18005b802  cmovnz  ecx, eax
0x18005b805  mov     rax, [rbp+57h+var_60]
0x18005b809  cmp     byte ptr [r12+rdx+0A5h], 0
0x18005b812  mov     bl, cl
0x18005b814  cmovnz  r13d, r14d
0x18005b818  lea     rcx, [rax+r8*8]
0x18005b81c  call    IsInterfaceConnected
0x18005b821  mov     rcx, [rbp+57h+var_60]
0x18005b825  mov     edx, esi
0x18005b827  mov     [rbp+57h+var_70], al
0x18005b82a  lea     rcx, [rcx+rdx*8]
0x18005b82e  call    IsInterfaceVirtual
0x18005b833  movzx   r10d, [rbp+57h+var_70]
0x18005b838  test    r10b, r10b
0x18005b83b  jz      short loc_18005B853
0x18005b83d  test    al, al
0x18005b83f  jnz     short loc_18005B853
0x18005b841  mov     rcx, [rbp+57h+var_58]
0x18005b845  xor     edx, edx
0x18005b847  movzx   edi, dil
0x18005b84b  cmp     [r12+rcx+10h], r14d
0x18005b850  cmovnz  edi, edx
0x18005b853  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b85a  jz      short loc_18005B89A
0x18005b85c  mov     r9, [rbp+57h+var_58]
0x18005b860  mov     edx, 28h ; '('
0x18005b865  movzx   eax, al
0x18005b868  mov     dword ptr [rsp+0E0h+var_A8], eax
0x18005b86c  mov     [rsp+0E0h+var_B0], r10d
0x18005b871  mov     eax, [r12+r9+0A8h]
0x18005b879  movzx   r8d, byte ptr [r12+r9+0A5h]
0x18005b882  mov     r9, [rbp+57h+var_60]
0x18005b886  mov     dword ptr [rsp+0E0h+var_B8], r8d
0x18005b88b  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18005b88f  mov     eax, esi
0x18005b891  mov     r9, [r9+rax*8]
0x18005b895  call    WPP_SF_idddd
0x18005b89a  add     esi, r14d
0x18005b89d  cmp     esi, [rbp+57h+var_50]
0x18005b8a0  jb      loc_18005B7E3
0x18005b8a6  mov     r14d, [rbp+57h+var_6C]
0x18005b8aa  mov     r12d, [rbp+57h+var_68]
0x18005b8ae  xor     esi, esi
0x18005b8b0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18005b8b7  jz      short loc_18005B8FD
0x18005b8b9  test    dil, dil
0x18005b8bc  lea     rdx, aNotInPrivateNe; "not in private network"
0x18005b8c3  lea     rax, aInPrivateNetwo; "in private network"
0x18005b8ca  mov     ecx, 40Bh
0x18005b8cf  cmovz   rax, rdx
0x18005b8d3  lea     r9, aOutside; "outside"
0x18005b8da  lea     rdx, aInside; "inside"
0x18005b8e1  mov     [rsp+0E0h+var_C0], rax
0x18005b8e6  test    bl, bl
0x18005b8e8  lea     r8, WPP_85172e4714023e67c3665ec5069963d4_Traceguids
0x18005b8ef  cmovz   r9, rdx
0x18005b8f3  mov     edx, 29h ; ')'
0x18005b8f8  call    WPP_SF_SS
0x18005b8fd  mov     rdx, [rbp+57h+var_58]
0x18005b901  xor     r9d, r9d
0x18005b904  mov     rcx, [rbp+57h+var_60]
0x18005b908  xor     r8d, r8d
0x18005b90b  call    cs:__imp_NsiFreeTable
0x18005b912  nop     dword ptr [rax+rax+00h]
0x18005b917  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18005b91e  mov     [rbp+57h+var_60], rsi
0x18005b922  mov     [rbp+57h+var_58], rsi
0x18005b926  call    cs:__imp_AcquireSRWLockExclusive
0x18005b92d  nop     dword ptr [rax+rax+00h]
0x18005b932  cmp     cs:byte_180111F7A, bl
0x18005b938  jnz     short loc_18005B955
0x18005b93a  cmp     cs:byte_180111F7B, r13b
0x18005b941  jnz     short loc_18005B955
0x18005b943  cmp     cs:byte_180111F7C, dil
0x18005b94a  jz      short loc_18005B96C
0x18005b94c  mov     cs:byte_180111F7C, dil
0x18005b953  jmp     short loc_18005B967
0x18005b955  mov     cs:byte_180111F7A, bl
0x18005b95b  mov     cs:byte_180111F7B, r13b
0x18005b962  call    FlushDnsPolicyUnreachableStatusUnlocked
0x18005b967  call    RefreshDirectAccessStatePrivate
0x18005b96c  lea     rcx, g_DnsPolicyTableLock; SRWLock
0x18005b973  call    cs:__imp_ReleaseSRWLockExclusive
0x18005b97a  nop     dword ptr [rax+rax+00h]
0x18005b97f  test    r12d, r12d
0x18005b982  cmovnz  r14d, r12d
0x18005b986  test    r15d, r15d
0x18005b989  cmovnz  r14d, r15d
0x18005b98d  mov     eax, r14d
0x18005b990  mov     rcx, [rbp+57h+var_48]
0x18005b994  xor     rcx, rsp; StackCookie
0x18005b997  call    __security_check_cookie
0x18005b99c  add     rsp, 0A8h
0x18005b9a3  pop     r15
0x18005b9a5  pop     r14
0x18005b9a7  pop     r13
0x18005b9a9  pop     r12
0x18005b9ab  pop     rdi
0x18005b9ac  pop     rsi
0x18005b9ad  pop     rbx
0x18005b9ae  pop     rbp
0x18005b9af  retn
```
