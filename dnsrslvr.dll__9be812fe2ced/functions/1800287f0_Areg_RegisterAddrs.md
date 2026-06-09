# Areg_RegisterAddrs

- ea: `0x1800287f0`
- end: `0x180028df2`
- name: `Areg_RegisterAddrs`
- size: `1538`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027ef0`

## callees

- `0x180026134`
- `0x180026270`
- `0x180026314`
- `0x1800287f0`
- `0x18002943c`
- `0x180033fc4`
- `0x180034528`
- `0x180036f4c`
- `0x1800370f8`
- `0x180046ec0`
- `0x18004ae00`
- `0x18007b76c`
- `0x18007bf5c`
- `0x18008614c`
- `0x180086700`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `DNSAPI!DnsGlobals` at `0x18002894d`
- `DNSAPI!DnsGlobals` at `0x180028b40`
- `DNSAPI!Reg_ReadUpdateInfo` at `0x1800289ce`
- `DNSAPI!Reg_ReadUpdateInfo` at `0x1800289ce`
- `DNSAPI!Reg_FreeUpdateInfo` at `0x180028d9b`
- `DNSAPI!Reg_FreeUpdateInfo` at `0x180028d9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028c8d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028c2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028c2c`

## pseudocode

```c
__int64 __fastcall Areg_RegisterAddrs(__int64 a1, __int64 a2, int a3)
{
  void **v4; // r14
  void *v6; // rsi
  WCHAR *v7; // r15
  _WORD *v8; // r13
  void *v9; // rcx
  int v10; // ebx
  __int64 *v11; // r12
  int v12; // ecx
  int v13; // r8d
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rdx
  const char *v17; // rax
  const WCHAR *v18; // rbx
  __int64 v19; // rdx
  const char *v20; // rdi
  unsigned int UpdateInfo; // eax
  void *v22; // r10
  int v23; // edx
  int v24; // eax
  void *v25; // r9
  int v26; // r11d
  WCHAR *v27; // rcx
  int Entry; // eax
  int v29; // [rsp+70h] [rbp-69h]
  const char *v30; // [rsp+90h] [rbp-49h]
  int v31; // [rsp+98h] [rbp-41h]
  int v32; // [rsp+9Ch] [rbp-3Dh]
  __int64 v33; // [rsp+A0h] [rbp-39h] BYREF
  void *v34; // [rsp+A8h] [rbp-31h]
  int v35; // [rsp+B0h] [rbp-29h]
  int v36; // [rsp+B4h] [rbp-25h]
  void *v37; // [rsp+B8h] [rbp-21h]
  __int64 v38[2]; // [rsp+C0h] [rbp-19h] BYREF
  PCNZWCH lpString1[2]; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v40; // [rsp+E0h] [rbp+7h]

  v38[0] = 0;
  v40 = 0;
  v4 = 0;
  *(_OWORD *)lpString1 = 0;
  if ( !a1 )
    return 87;
  v6 = *(void **)(a1 + 40);
  v7 = *(WCHAR **)(a1 + 16);
  v8 = *(_WORD **)(a1 + 24);
  v9 = *(void **)(a1 + 48);
  v10 = *(_DWORD *)(a1 + 60);
  v35 = *(_DWORD *)(a1 + 56);
  v33 = *(_QWORD *)(a1 + 8);
  v37 = v6;
  v34 = v9;
  v31 = v10;
  v32 = 0;
  v30 = 0;
  v11 = (__int64 *)(a1 + 32);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_qdSSSDDDqq(
      (_DWORD)v9,
      0,
      a3,
      a1,
      *(_DWORD *)(a1 + 72),
      (__int64)v7,
      (__int64)v8,
      *v11,
      v10,
      *(_DWORD *)(a1 + 64),
      *(_DWORD *)(a1 + 68),
      (__int64)v6,
      (__int64)v9);
    v9 = v34;
  }
  DnsPrint_DnsAddrArray("DNS servers:", "server", v9);
  DnsPrint_DnsAddrArray("Local registerable addrs:", 0, v6);
  LOBYTE(v14) = 8;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_SSS(v12, v14, v13, (_DWORD)v7, (__int64)v8, *v11);
  v15 = 0;
  if ( !g_fAregInitialized )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v16 = 38;
LABEL_95:
      WPP_SF_(1035, v16, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
      goto LABEL_96;
    }
    goto LABEL_96;
  }
  if ( g_fNoMoreUpdatess || g_fAregThreadStop )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v16 = 39;
      goto LABEL_95;
    }
LABEL_96:
    LODWORD(v18) = 1062;
    goto LABEL_97;
  }
  v36 = v10 & 0x10;
  if ( (v10 & 0x10) != 0 && !DnsGlobals[61] )
  {
    v17 = "because WAN adapter registrations are disabled";
LABEL_15:
    LODWORD(v18) = 0;
    goto LABEL_81;
  }
  if ( !v7 || !*v7 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_24;
    v19 = 40;
    goto LABEL_23;
  }
  if ( (!v8 || !*v8) && (v10 & 0x20) == 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    {
LABEL_24:
      LODWORD(v18) = 87;
LABEL_97:
      v20 = 0;
      goto LABEL_98;
    }
    v19 = 41;
LABEL_23:
    WPP_SF_(1035, v19, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
    goto LABEL_24;
  }
  if ( (v10 & 0x10000000) != 0 )
  {
    areg_MarkAdapterAsPending(v7);
    LODWORD(v18) = 0;
    v20 = 0;
    goto LABEL_98;
  }
  UpdateInfo = Reg_ReadUpdateInfo(v7, lpString1);
  LODWORD(v18) = UpdateInfo;
  if ( UpdateInfo )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 42, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, UpdateInfo);
    goto LABEL_97;
  }
  v22 = v34;
  v18 = 0;
  v32 = 1;
  if ( v34 && *((_DWORD *)v34 + 1) )
  {
    v23 = v31;
  }
  else
  {
    v23 = v31;
    if ( (v31 & 0x20) == 0 )
    {
      v20 = "no DNS servers";
LABEL_34:
      LODWORD(v18) = 87;
      goto LABEL_98;
    }
  }
  if ( !(_DWORD)v40 )
  {
    v20 = "because adapter is disabled";
    v24 = areg_FindAndCleanupStaleEntries(v7, (__int64)&v33);
    goto LABEL_38;
  }
  if ( (v23 & 0x60) != 0 )
    goto LABEL_87;
  if ( !v8 || !*v8 )
  {
    v20 = "invalid (or no) hostname";
    goto LABEL_34;
  }
  v25 = v37;
  if ( v37 && *((_DWORD *)v37 + 1) )
  {
    v15 = HIDWORD(v40);
    if ( (*(_DWORD *)(a1 + 60) & 0x2000) != 0 )
      v15 = 0;
    v38[1] = (__int64)lpString1[0];
    HIDWORD(v40) = v15;
    if ( v15 )
    {
      v18 = (const WCHAR *)*v11;
      if ( *v11 )
      {
        if ( *v18 )
        {
          if ( !lpString1[0] )
            goto LABEL_60;
          goto LABEL_55;
        }
        v18 = 0;
      }
    }
    if ( !lpString1[0] )
    {
      if ( !lpString1[1] )
      {
        v17 = "no domains to register";
        goto LABEL_15;
      }
LABEL_60:
      v26 = v35;
      if ( (unsigned int)(v35 - 1) > 0xFFFFFFFD )
        v26 = DnsGlobals[63];
      if ( (*(_DWORD *)(a1 + 60) & 0x2000) != 0 )
        v27 = 0;
      else
        v27 = (WCHAR *)lpString1[1];
      Entry = areg_AllocateEntry(
                v7,
                v8,
                v27,
                v25,
                v22,
                0,
                0,
                *(_DWORD *)(a1 + 72),
                v26,
                v23,
                *(_DWORD *)(a1 + 64),
                *(_DWORD *)(a1 + 68),
                v29,
                (__int64)&v33,
                (__int64)v38);
      v4 = (void **)v38[0];
      LODWORD(v18) = Entry;
      if ( Entry )
        goto LABEL_79;
      LODWORD(v18) = 0;
      if ( v36 )
        *(_DWORD *)(v38[0] + 296) = 1;
      if ( (*(_DWORD *)(a1 + 60) & 0x2000) == 0 )
        areg_FindAndCleanupStaleEntries(v4[3], 0);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_q(1035, 44, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, v4);
      EnterCriticalSection(&g_AregListCs);
      if ( g_fNoMoreUpdatess || g_fAregThreadStop || g_fAregPurge )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 45, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
        LeaveCriticalSection(&g_AregListCs);
        LODWORD(v18) = 1062;
        goto LABEL_79;
      }
      areg_EnqueueUpdate(v4);
      v4 = 0;
      LeaveCriticalSection(&g_AregListCs);
      areg_MarkAdapterAsPending(v7);
      v20 = 0;
      goto LABEL_39;
    }
LABEL_55:
    if ( v18 )
    {
      if ( (unsigned int)Dns_NameCompare_W(lpString1[0], v18) && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 43, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
      v22 = v34;
      v25 = v37;
      v23 = v31;
    }
    goto LABEL_60;
  }
  v17 = "done -- there are no addresses to register in DNS";
LABEL_81:
  v30 = v17;
  if ( (*(_BYTE *)(a1 + 64) & 0x60) == 0 && (*(_BYTE *)(a1 + 68) & 0x60) == 0 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 48, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
LABEL_79:
    v20 = v30;
    goto LABEL_98;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    goto LABEL_89;
  WPP_SF_(1035, 46, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
LABEL_87:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 47, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids);
LABEL_89:
  v24 = areg_FindAndCleanupStaleEntries(v7, (__int64)&v33);
  v20 = v30;
LABEL_38:
  if ( v24 )
LABEL_39:
    areg_AlertOrStartRegThread(0);
LABEL_98:
  if ( v33 )
    areg_SignalUpdateStatus(&v33, (unsigned int)v18);
  if ( v32 )
    Reg_FreeUpdateInfo(lpString1, 0);
  if ( v4 )
    areg_FreeEntry(v4);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_Ds(v15, 49, (unsigned int)WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids, (_DWORD)v18, (__int64)v20);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800287f0  push    rbp
0x1800287f2  push    rbx
0x1800287f3  push    rsi
0x1800287f4  push    rdi
0x1800287f5  push    r12
0x1800287f7  push    r13
0x1800287f9  push    r14
0x1800287fb  push    r15
0x1800287fd  lea     rbp, [rsp-1Fh]
0x180028802  sub     rsp, 0F8h
0x180028809  mov     rax, cs:__security_cookie
0x180028810  xor     rax, rsp
0x180028813  mov     [rbp+57h+var_48], rax
0x180028817  xor     edx, edx
0x180028819  xor     eax, eax
0x18002881b  mov     [rbp+57h+var_70], rdx
0x18002881f  xorps   xmm0, xmm0
0x180028822  mov     [rbp+57h+var_50], rax
0x180028826  mov     rdi, rcx
0x180028829  mov     r14d, edx
0x18002882c  movups  xmmword ptr [rbp+57h+lpString1], xmm0
0x180028830  test    rcx, rcx
0x180028833  jnz     short loc_18002883D
0x180028835  lea     eax, [rcx+57h]
0x180028838  jmp     loc_180028DD2
0x18002883d  mov     eax, [rdi+38h]
0x180028840  mov     rsi, [rcx+28h]
0x180028844  mov     r15, [rcx+10h]
0x180028848  mov     r13, [rcx+18h]
0x18002884c  mov     rcx, [rcx+30h]
0x180028850  mov     ebx, [rdi+3Ch]
0x180028853  mov     [rbp+57h+var_80], eax
0x180028856  mov     rax, [rdi+8]
0x18002885a  mov     [rbp+57h+var_90], rax
0x18002885e  mov     [rbp+57h+var_78], rsi
0x180028862  mov     [rbp+57h+var_88], rcx
0x180028866  mov     [rbp+57h+var_98], ebx
0x180028869  mov     [rbp+57h+var_94], edx
0x18002886c  mov     [rbp+57h+var_A0], rdx
0x180028870  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028877  lea     r12, [rdi+20h]
0x18002887b  jz      short loc_1800288BF
0x18002887d  mov     eax, [rdi+44h]
0x180028880  mov     r9, rdi
0x180028883  mov     qword ptr [rsp+130h+var_D0], rcx
0x180028888  mov     qword ptr [rsp+130h+var_D8], rsi
0x18002888d  mov     [rsp+130h+var_E0], eax
0x180028891  mov     eax, [rdi+40h]
0x180028894  mov     [rsp+130h+var_E8], eax
0x180028898  mov     rax, [r12]
0x18002889c  mov     dword ptr [rsp+130h+var_F0], ebx
0x1800288a0  mov     [rsp+130h+var_F8], rax
0x1800288a5  mov     eax, [rdi+48h]
0x1800288a8  mov     [rsp+130h+var_100], r13
0x1800288ad  mov     [rsp+130h+var_108], r15
0x1800288b2  mov     dword ptr [rsp+130h+var_110], eax
0x1800288b6  call    WPP_SF_qdSSSDDDqq
0x1800288bb  mov     rcx, [rbp+57h+var_88]
0x1800288bf  mov     r8, rcx
0x1800288c2  lea     rdx, aServer; "server"
0x1800288c9  lea     rcx, aDnsServers; "DNS servers:"
0x1800288d0  call    DnsPrint_DnsAddrArray
0x1800288d5  mov     r8, rsi
0x1800288d8  lea     rcx, aLocalRegistera; "Local registerable addrs:"
0x1800288df  xor     edx, edx
0x1800288e1  call    DnsPrint_DnsAddrArray
0x1800288e6  mov     dl, 8
0x1800288e8  test    byte ptr cs:xmmword_1800AB5A0+1, dl
0x1800288ee  jz      short loc_180028908
0x1800288f0  mov     rax, [r12]
0x1800288f4  mov     r9, r15
0x1800288f7  mov     [rsp+130h+var_108], rax
0x1800288fc  mov     [rsp+130h+var_110], r13
0x180028901  call    WPP_SF_SSS
0x180028906  mov     dl, 8
0x180028908  xor     ecx, ecx
0x18002890a  cmp     cs:g_fAregInitialized, ecx
0x180028910  jnz     short loc_180028926
0x180028912  test    byte ptr cs:xmmword_1800AB5A0+1, dl
0x180028918  jz      loc_180028D75
0x18002891e  lea     edx, [rcx+26h]
0x180028921  jmp     loc_180028D64
0x180028926  cmp     cs:g_fNoMoreUpdatess, ecx
0x18002892c  jnz     loc_180028D57
0x180028932  cmp     cs:g_fAregThreadStop, ecx
0x180028938  jnz     loc_180028D57
0x18002893e  mov     eax, ebx
0x180028940  mov     esi, 40Bh
0x180028945  and     eax, 10h
0x180028948  mov     [rbp+57h+var_7C], eax
0x18002894b  jz      short loc_18002896A
0x18002894d  mov     rax, cs:__imp_DnsGlobals
0x180028954  cmp     [rax+0F4h], ecx
0x18002895a  jnz     short loc_18002896A
0x18002895c  lea     rax, aBecauseWanAdap; "because WAN adapter registrations are d"...
0x180028963  xor     ebx, ebx
0x180028965  jmp     loc_180028CA8
0x18002896a  test    r15, r15
0x18002896d  jz      loc_180028D41
0x180028973  cmp     [r15], cx
0x180028977  jz      loc_180028D41
0x18002897d  test    r13, r13
0x180028980  jz      short loc_180028989
0x180028982  cmp     [r13+0], cx
0x180028987  jnz     short loc_1800289B3
0x180028989  test    bl, 20h
0x18002898c  jnz     short loc_1800289B3
0x18002898e  test    byte ptr cs:xmmword_1800AB5A0+1, dl
0x180028994  jz      short loc_1800289A9
0x180028996  mov     edx, 29h ; ')'
0x18002899b  mov     ecx, esi
0x18002899d  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800289a4  call    WPP_SF_
0x1800289a9  mov     ebx, 57h ; 'W'
0x1800289ae  jmp     loc_180028D7A
0x1800289b3  mov     rcx, r15; lpSubKey
0x1800289b6  bt      ebx, 1Ch
0x1800289ba  jnb     short loc_1800289CA
0x1800289bc  call    areg_MarkAdapterAsPending
0x1800289c1  xor     ebx, ebx
0x1800289c3  mov     edi, ebx
0x1800289c5  jmp     loc_180028D7D
0x1800289ca  lea     rdx, [rbp+57h+lpString1]
0x1800289ce  call    cs:__imp_Reg_ReadUpdateInfo
0x1800289d4  mov     ebx, eax
0x1800289d6  test    eax, eax
0x1800289d8  jz      short loc_180028A02
0x1800289da  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800289e1  jz      loc_180028D7A
0x1800289e7  mov     edx, 2Ah ; '*'
0x1800289ec  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x1800289f3  mov     ecx, esi
0x1800289f5  mov     r9d, eax
0x1800289f8  call    WPP_SF_d
0x1800289fd  jmp     loc_180028D7A
0x180028a02  mov     r10, [rbp+57h+var_88]
0x180028a06  xor     ebx, ebx
0x180028a08  mov     r8d, 1
0x180028a0e  mov     [rbp+57h+var_94], r8d
0x180028a12  test    r10, r10
0x180028a15  jz      short loc_180028A1D
0x180028a17  cmp     [r10+4], ebx
0x180028a1b  jnz     short loc_180028A36
0x180028a1d  mov     edx, [rbp+57h+var_98]
0x180028a20  test    dl, 20h
0x180028a23  jnz     short loc_180028A39
0x180028a25  lea     rdi, aNoDnsServers; "no DNS servers"
0x180028a2c  mov     ebx, 57h ; 'W'
0x180028a31  jmp     loc_180028D7D
0x180028a36  mov     edx, [rbp+57h+var_98]
0x180028a39  cmp     dword ptr [rbp+57h+var_50], ebx
0x180028a3c  jnz     short loc_180028A6F
0x180028a3e  lea     rax, [rbp+57h+var_90]
0x180028a42  mov     r9d, r8d
0x180028a45  xor     edx, edx
0x180028a47  mov     [rsp+130h+var_110], rax; __int64
0x180028a4c  mov     rcx, r15; Src
0x180028a4f  lea     rdi, aBecauseAdapter; "because adapter is disabled"
0x180028a56  call    areg_FindAndCleanupStaleEntries
0x180028a5b  test    eax, eax
0x180028a5d  jz      loc_180028D7D
0x180028a63  xor     ecx, ecx
0x180028a65  call    areg_AlertOrStartRegThread
0x180028a6a  jmp     loc_180028D7D
0x180028a6f  test    dl, 60h
0x180028a72  jnz     loc_180028CF2
0x180028a78  test    r13, r13
0x180028a7b  jz      loc_180028D35
0x180028a81  cmp     [r13+0], bx
0x180028a86  jz      loc_180028D35
0x180028a8c  mov     r9, [rbp+57h+var_78]
0x180028a90  test    r9, r9
0x180028a93  jz      loc_180028CA1
0x180028a99  cmp     [r9+4], ebx
0x180028a9d  jz      loc_180028CA1
0x180028aa3  test    dword ptr [rdi+3Ch], 2000h
0x180028aaa  mov     r11, rbx
0x180028aad  mov     ecx, dword ptr [rbp+57h+var_50+4]
0x180028ab0  mov     r8, [rbp+57h+lpString1]
0x180028ab4  cmovnz  ecx, r11d
0x180028ab8  mov     [rbp+57h+var_68], r8
0x180028abc  mov     dword ptr [rbp+57h+var_50+4], ecx
0x180028abf  test    ecx, ecx
0x180028ac1  jz      short loc_180028AD5
0x180028ac3  mov     rbx, [r12]
0x180028ac7  test    rbx, rbx
0x180028aca  jz      short loc_180028AD5
0x180028acc  cmp     [rbx], r11w
0x180028ad0  jnz     short loc_180028AEC
0x180028ad2  mov     rbx, r11
0x180028ad5  test    r8, r8
0x180028ad8  jnz     short loc_180028AF1
0x180028ada  cmp     [rbp+57h+lpString1+8], r11
0x180028ade  jnz     short loc_180028B33
0x180028ae0  lea     rax, aNoDomainsToReg; "no domains to register"
0x180028ae7  jmp     loc_180028963
0x180028aec  test    r8, r8
0x180028aef  jz      short loc_180028B33
0x180028af1  test    rbx, rbx
0x180028af4  jz      short loc_180028B33
0x180028af6  mov     rdx, rbx; lpString2
0x180028af9  mov     rcx, r8; lpString1
0x180028afc  call    Dns_NameCompare_W
0x180028b01  test    eax, eax
0x180028b03  jz      short loc_180028B24
0x180028b05  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028b0c  jz      short loc_180028B21
0x180028b0e  mov     edx, 2Bh ; '+'
0x180028b13  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180028b1a  mov     ecx, esi
0x180028b1c  call    WPP_SF_
0x180028b21  mov     rbx, r14
0x180028b24  mov     r10, [rbp+57h+var_88]
0x180028b28  mov     r9, [rbp+57h+var_78]
0x180028b2c  mov     r8, [rbp+57h+var_68]
0x180028b30  mov     edx, [rbp+57h+var_98]
0x180028b33  mov     r11d, [rbp+57h+var_80]
0x180028b37  lea     eax, [r11-1]
0x180028b3b  cmp     eax, 0FFFFFFFDh
0x180028b3e  jbe     short loc_180028B4E
0x180028b40  mov     rax, cs:__imp_DnsGlobals
0x180028b47  mov     r11d, [rax+0FCh]
0x180028b4e  mov     r12d, 2000h
0x180028b54  test    [rdi+3Ch], r12d
0x180028b58  jnz     short loc_180028B60
0x180028b5a  mov     rcx, [rbp+57h+lpString1+8]
0x180028b5e  jmp     short loc_180028B66
0x180028b60  mov     rbx, r14
0x180028b63  mov     rcx, r14
0x180028b66  lea     rax, [rbp+57h+var_70]
0x180028b6a  mov     [rsp+130h+var_B0], rax; __int64
0x180028b72  lea     rax, [rbp+57h+var_90]
0x180028b76  mov     [rsp+130h+var_B8], rax; __int64
0x180028b7b  mov     eax, [rdi+44h]
0x180028b7e  mov     [rsp+130h+var_C8], eax; int
0x180028b82  mov     eax, [rdi+40h]
0x180028b85  mov     [rsp+130h+var_D0], eax; int
0x180028b89  mov     eax, [rdi+48h]
0x180028b8c  mov     [rsp+130h+var_D8], edx; int
0x180028b90  mov     rdx, r13; void *
0x180028b93  mov     [rsp+130h+var_E0], r11d; int
0x180028b98  mov     [rsp+130h+var_E8], eax; int
0x180028b9c  mov     [rsp+130h+var_F0], r14; __int64
0x180028ba1  mov     [rsp+130h+var_F8], r14; __int64
0x180028ba6  mov     [rsp+130h+var_100], r10; void *
0x180028bab  mov     [rsp+130h+var_108], r9; void *
0x180028bb0  mov     r9, r8
0x180028bb3  mov     [rsp+130h+var_110], rcx; void *
0x180028bb8  mov     r8, rbx
0x180028bbb  mov     rcx, r15; Src
0x180028bbe  call    areg_AllocateEntry
0x180028bc3  mov     r14, [rbp+57h+var_70]
0x180028bc7  mov     ebx, eax
0x180028bc9  test    eax, eax
0x180028bcb  jnz     loc_180028C98
0x180028bd1  xor     ebx, ebx
0x180028bd3  cmp     [rbp+57h+var_7C], ebx
0x180028bd6  jz      short loc_180028BE3
0x180028bd8  mov     dword ptr [r14+128h], 1
0x180028be3  test    [rdi+3Ch], r12d
0x180028be7  jnz     short loc_180028C03
0x180028be9  mov     rcx, [r14+18h]; Src
0x180028bed  mov     r9d, 1
0x180028bf3  xor     r8d, r8d
0x180028bf6  mov     [rsp+130h+var_110], rbx; __int64
0x180028bfb  mov     rdx, r14
0x180028bfe  call    areg_FindAndCleanupStaleEntries
0x180028c03  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028c0a  jz      short loc_180028C22
0x180028c0c  mov     edx, 2Ch ; ','
0x180028c11  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180028c18  mov     ecx, esi
0x180028c1a  mov     r9, r14
0x180028c1d  call    WPP_SF_q
0x180028c22  lea     rdi, g_AregListCs
0x180028c29  mov     rcx, rdi; lpCriticalSection
0x180028c2c  call    cs:__imp_EnterCriticalSection
0x180028c32  cmp     cs:g_fNoMoreUpdatess, ebx
0x180028c38  jnz     short loc_180028C6E
0x180028c3a  cmp     cs:g_fAregThreadStop, ebx
0x180028c40  jnz     short loc_180028C6E
0x180028c42  cmp     cs:g_fAregPurge, ebx
0x180028c48  jnz     short loc_180028C6E
0x180028c4a  mov     rcx, r14
0x180028c4d  call    areg_EnqueueUpdate
0x180028c52  mov     rcx, rdi; lpCriticalSection
0x180028c55  mov     r14, rbx
0x180028c58  call    cs:__imp_LeaveCriticalSection
0x180028c5e  mov     rcx, r15; lpSubKey
0x180028c61  call    areg_MarkAdapterAsPending
0x180028c66  mov     rdi, rbx
0x180028c69  jmp     loc_180028A63
0x180028c6e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180028c75  jz      short loc_180028C8A
0x180028c77  mov     edx, 2Dh ; '-'
0x180028c7c  lea     r8, WPP_7d480ea9e959396e1e8188612fd17a9a_Traceguids
0x180028c83  mov     ecx, esi
0x180028c85  call    WPP_SF_
0x180028c8a  mov     rcx, rdi; lpCriticalSection
0x180028c8d  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
