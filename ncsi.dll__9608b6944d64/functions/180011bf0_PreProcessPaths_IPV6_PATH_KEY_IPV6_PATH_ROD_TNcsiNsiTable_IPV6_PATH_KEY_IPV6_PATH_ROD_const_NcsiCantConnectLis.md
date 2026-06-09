# PreProcessPaths<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> const &,NcsiCantConnectList<_IPV6_PATH_KEY> &,LocalConnects &,LocalNets &)

- ea: `0x180011bf0`
- end: `0x180012258`
- name: `??$PreProcessPaths@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@YAXAEBV?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@AEAV?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@AEAVLocalConnects@@AEAVLocalNets@@@Z`
- size: `1640`
- prototype: `void()`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180011ab4`

## callees

- `0x180010200`
- `0x180011a58`
- `0x180011b60`
- `0x180011bf0`
- `0x180012260`
- `0x1800123a0`
- `0x1800124b0`
- `0x1800138cc`
- `0x180021b50`
- `0x1800228ec`
- `0x180022c2c`
- `0x180027f4c`
- `0x1800298c0`
- `0x180047240`
- `0x180047f54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012041`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011dd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011e35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011fd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012041`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f30`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011c2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011e19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011f30`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c17`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void PreProcessPaths<_IPV6_PATH_KEY,_IPV6_PATH_ROD>()
{
  DWORD TickCount; // ebx
  LocalConnects *v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // r10
  __int64 v5; // rsi
  __int64 v6; // rcx
  _QWORD *v7; // r15
  _QWORD *v8; // r14
  __int64 v9; // rax
  __int64 v10; // r12
  __int64 v11; // r13
  int v12; // eax
  unsigned int v13; // r8d
  int v14; // edx
  LocalNets *v15; // rcx
  LocalConnects *v16; // rcx
  LocalNets *v17; // rcx
  __int64 v18; // rbx
  __int64 i; // rdi
  __int64 v20; // rax
  __int64 *v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // rbx
  __int64 v24; // rcx
  int v25; // r8d
  int v26; // [rsp+40h] [rbp-69h]
  const char *v27; // [rsp+48h] [rbp-61h]
  DWORD v28; // [rsp+50h] [rbp-59h]
  __int64 v29; // [rsp+58h] [rbp-51h]
  __int64 v30; // [rsp+60h] [rbp-49h]
  _BYTE v31[20]; // [rsp+A0h] [rbp-9h] BYREF

  TickCount = GetTickCount();
  v28 = TickCount;
  EnterCriticalSection(&g_ncsiLock);
  NcsiCantConnectList<_IPV6_PATH_KEY>::ExpireConnections();
  LocalConnects::ExpireConnections(v1);
  v2 = qword_18009DD70;
  v29 = qword_18009DD70;
  v3 = qword_18009DD80;
  v30 = qword_18009DD80;
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      19,
      WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids,
      g_nsiPathTablev6);
    v4 = WPP_GLOBAL_Control;
    v2 = v29;
    v3 = v30;
  }
  v5 = 0;
  if ( g_nsiPathTablev6 )
  {
    while ( 1 )
    {
      v6 = 48 * v5;
      v7 = (_QWORD *)(48 * v5 + v2 + 16);
      v8 = (_QWORD *)(48 * v5 + v2 + 32);
      v9 = *v8 - *v7;
      if ( *v8 == *v7 )
        v9 = v8[1] - v7[1];
      if ( !v9 )
        goto LABEL_20;
      v10 = v6 + v2;
      v11 = v3 + 112LL * (unsigned int)v5;
      v12 = *(unsigned __int8 *)(v11 + 20);
      if ( (_BYTE)v12 )
        break;
      NcsiCantConnectList<_IPV6_PATH_KEY>::RemoveEntry(v6, v6 + v2);
      v4 = WPP_GLOBAL_Control;
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        VerboseMessage(v10, v11, 3);
LABEL_19:
        v4 = WPP_GLOBAL_Control;
      }
LABEL_20:
      v5 = (unsigned int)(v5 + 1);
      v2 = v29;
      v3 = v30;
      TickCount = v28;
      if ( (unsigned int)v5 >= g_nsiPathTablev6 )
        goto LABEL_21;
    }
    if ( !*(_BYTE *)(v11 + 21) )
    {
      v13 = *(_DWORD *)(v11 + 16);
      if ( v13 > 0xEA60 || TickCount < 0xEA60 )
      {
        if ( *(_BYTE *)(v4 + 25) < 5u || (_UNKNOWN *)v4 == &WPP_GLOBAL_Control || (*(_BYTE *)(v4 + 28) & 2) == 0 )
          goto LABEL_20;
        v14 = *(unsigned __int8 *)(v11 + 20);
        v27 = "PathStateCanConnectTooOld";
        v26 = *(_DWORD *)(v11 + 16);
        goto LABEL_18;
      }
      if ( v13 <= 0x3A98 )
      {
        if ( *(_BYTE *)(v4 + 25) < 5u || (_UNKNOWN *)v4 == &WPP_GLOBAL_Control || (*(_BYTE *)(v4 + 28) & 2) == 0 )
          goto LABEL_20;
        WPP_SF_i_IPV6__IPV6_ddds(
          *(_QWORD *)(v4 + 16),
          v12,
          v13,
          *(_QWORD *)(v10 + 8),
          (__int64)v8,
          (__int64)v7,
          v12,
          *(_BYTE *)(v11 + 21),
          v13,
          (__int64)"PathStateCanConnectTooNew");
        goto LABEL_19;
      }
      EnterCriticalSection(&g_ncsiCantConnectStoreIPv6);
      std::_Tree<std::_Tmap_traits<_IPV6_PATH_KEY,unsigned long,std::less<_IPV6_PATH_KEY>,std::allocator<std::pair<_IPV6_PATH_KEY const,unsigned long>>,0>>::erase(
        &qword_18009D6E8,
        v10);
      LeaveCriticalSection(&g_ncsiCantConnectStoreIPv6);
      v15 = (LocalNets *)*(unsigned __int8 *)(v10 + 16);
      if ( (*(_BYTE *)(v10 + 16) & 0xF0) == 0
        || (*(_BYTE *)(v10 + 16) & 0xF0) == 0xF0
        || (memset(v31, 0, sizeof(v31)),
            *(_WORD *)v31 = 23,
            v31[4] = (_BYTE)v15,
            *(_QWORD *)&v31[5] = *(_QWORD *)(v10 + 17),
            *(_DWORD *)&v31[13] = *(_DWORD *)(v10 + 25),
            *(_WORD *)&v31[17] = *(_WORD *)(v10 + 29),
            v31[19] = *(_BYTE *)(v10 + 31),
            LocalNets::AddressIsKnownLocal(v15, (const struct INX_ADDR *)v31)) )
      {
        v16 = (LocalConnects *)WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids);
        }
        *(_OWORD *)v31 = 0;
        *(_WORD *)v31 = 23;
        *(_OWORD *)&v31[4] = *(_OWORD *)(v10 + 16);
        LocalConnects::StoreSuccessfulPath(v16, (const union _NET_LUID_LH *)(v10 + 8), (const struct INX_ADDR *)v31);
        v4 = WPP_GLOBAL_Control;
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
          goto LABEL_20;
        VerboseMessage(v10, v11, 5);
        goto LABEL_19;
      }
      v4 = WPP_GLOBAL_Control;
      if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
        || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
        goto LABEL_20;
      }
      v27 = "PathStateCanConnect";
      v26 = *(_DWORD *)(v11 + 16);
LABEL_63:
      v14 = *(unsigned __int8 *)(v11 + 20);
LABEL_18:
      WPP_SF_i_IPV6__IPV6_ddds(
        *(_QWORD *)(v4 + 16),
        v14,
        v13,
        *(_QWORD *)(v10 + 8),
        (__int64)v8,
        (__int64)v7,
        v14,
        *(_BYTE *)(v11 + 21),
        v26,
        (__int64)v27);
      goto LABEL_19;
    }
    v17 = (LocalNets *)*(unsigned __int8 *)(v10 + 16);
    if ( (*(_BYTE *)(v10 + 16) & 0xF0) != 0 && (*(_BYTE *)(v10 + 16) & 0xF0) != 0xF0 )
    {
      memset(v31, 0, sizeof(v31));
      *(_WORD *)v31 = 23;
      v31[4] = (_BYTE)v17;
      *(_QWORD *)&v31[5] = *(_QWORD *)(v10 + 17);
      *(_DWORD *)&v31[13] = *(_DWORD *)(v10 + 25);
      *(_WORD *)&v31[17] = *(_WORD *)(v10 + 29);
      v31[19] = *(_BYTE *)(v10 + 31);
      if ( !LocalNets::AddressIsKnownLocal(v17, (const struct INX_ADDR *)v31) )
      {
LABEL_44:
        if ( (unsigned __int8)NcsiCantConnectList<_IPV6_PATH_KEY>::AddItem(v24, v10) )
        {
          *(_DWORD *)(v11 + 16) = 0;
          v4 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u )
              goto LABEL_20;
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 20, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids);
            v4 = WPP_GLOBAL_Control;
          }
          if ( *(_BYTE *)(v4 + 25) < 5u )
            goto LABEL_20;
          VerboseMessage(v10, v11, 1);
          goto LABEL_19;
        }
        *(_DWORD *)(v11 + 16) = -1;
        v4 = WPP_GLOBAL_Control;
        if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
          || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        {
          goto LABEL_20;
        }
        v27 = "PathStateCantConnectItemOld";
        LOBYTE(v26) = -1;
        goto LABEL_63;
      }
    }
    *(_OWORD *)v31 = 0;
    *(_WORD *)v31 = 23;
    *(_OWORD *)&v31[4] = *(_OWORD *)(v10 + 16);
    EnterCriticalSection(&g_ncsiLocalConnects);
    v18 = *(_QWORD *)(qword_18009D668 + 8);
    for ( i = qword_18009D668; !*(_BYTE *)(v18 + 25); v18 = *(_QWORD *)v18 )
    {
      if ( memcmp_0((const void *)(v18 + 32), (const void *)(v10 + 8), 8u) < 0 )
        v18 += 16;
      else
        i = v18;
    }
    if ( *(_BYTE *)(i + 25) || memcmp_0((const void *)(v10 + 8), (const void *)(i + 32), 8u) < 0 )
    {
      v20 = qword_18009D668;
      i = qword_18009D668;
    }
    else
    {
      v20 = qword_18009D668;
    }
    if ( i == v20 )
    {
      LeaveCriticalSection(&g_ncsiLocalConnects);
    }
    else
    {
      v21 = (__int64 *)(i + 40);
      v22 = std::_Tree<std::_Tmap_traits<INX_ADDR,unsigned long,std::less<INX_ADDR>,std::allocator<std::pair<INX_ADDR const,unsigned long>>,0>>::_Find<INX_ADDR>(
              i + 40,
              v31);
      v23 = *v21;
      LeaveCriticalSection(&g_ncsiLocalConnects);
      if ( v22 != v23 )
        goto LABEL_44;
    }
    *(_DWORD *)(v11 + 16) = -1;
    v4 = WPP_GLOBAL_Control;
    if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 5u
      || (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
    {
      goto LABEL_20;
    }
    WPP_SF_i_IPV6__IPV6_ddds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      *(unsigned __int8 *)(v11 + 20),
      v25,
      *(_QWORD *)(v10 + 8),
      (__int64)v8,
      (__int64)v7,
      *(_BYTE *)(v11 + 20),
      *(_BYTE *)(v11 + 21),
      -1,
      (__int64)"PathStateLocalNotConnected");
    goto LABEL_19;
  }
LABEL_21:
  LeaveCriticalSection(&g_ncsiLock);
}

```

## disassembly

```asm
0x180011bf0  push    rbp
0x180011bf2  push    rbx
0x180011bf3  push    rsi
0x180011bf4  push    rdi
0x180011bf5  push    r12
0x180011bf7  push    r13
0x180011bf9  push    r14
0x180011bfb  push    r15
0x180011bfd  lea     rbp, [rsp-1Fh]
0x180011c02  sub     rsp, 0C8h
0x180011c09  mov     rax, cs:__security_cookie
0x180011c10  xor     rax, rsp
0x180011c13  mov     [rbp+57h+var_48], rax
0x180011c17  call    cs:__imp_GetTickCount
0x180011c1d  mov     ebx, eax
0x180011c1f  mov     [rbp+57h+var_B0], eax
0x180011c22  lea     rdi, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180011c29  mov     rcx, rdi; lpCriticalSection
0x180011c2c  call    cs:__imp_EnterCriticalSection
0x180011c32  mov     [rbp+57h+var_88], rdi
0x180011c36  call    ?ExpireConnections@?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@QEAAXXZ; NcsiCantConnectList<_IPV6_PATH_KEY>::ExpireConnections(void)
0x180011c3b  call    ?ExpireConnections@LocalConnects@@QEAAXXZ; LocalConnects::ExpireConnections(void)
0x180011c40  mov     r8, cs:qword_18009DD70
0x180011c47  mov     [rbp+57h+var_A8], r8
0x180011c4b  mov     r9, cs:qword_18009DD80
0x180011c52  mov     [rbp+57h+var_A0], r9
0x180011c56  lea     r11, WPP_GLOBAL_Control
0x180011c5d  mov     r10, cs:WPP_GLOBAL_Control
0x180011c64  cmp     r10, r11
0x180011c67  jz      short loc_180011CA9
0x180011c69  test    byte ptr [r10+1Ch], 2
0x180011c6e  jz      short loc_180011CA9
0x180011c70  cmp     byte ptr [r10+19h], 5
0x180011c75  jb      short loc_180011CA9
0x180011c77  mov     edx, 13h
0x180011c7c  mov     r9d, cs:?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x180011c83  lea     r8, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids
0x180011c8a  mov     rcx, [r10+10h]
0x180011c8e  call    WPP_SF_d
0x180011c93  mov     r10, cs:WPP_GLOBAL_Control
0x180011c9a  mov     r8, [rbp+57h+var_A8]
0x180011c9e  mov     r9, [rbp+57h+var_A0]
0x180011ca2  lea     r11, WPP_GLOBAL_Control
0x180011ca9  xor     esi, esi
0x180011cab  cmp     cs:?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A, esi; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x180011cb1  jbe     loc_180011DD0
0x180011cb7  mov     edi, 17h
0x180011cbc  nop     dword ptr [rax+00h]
0x180011cc0  mov     edx, esi
0x180011cc2  lea     rcx, [rsi+rsi*2]
0x180011cc6  shl     rcx, 4
0x180011cca  lea     r15, [r8+10h]
0x180011cce  add     r15, rcx
0x180011cd1  lea     r14, [r8+20h]
0x180011cd5  add     r14, rcx
0x180011cd8  mov     rax, [r14]
0x180011cdb  sub     rax, [r15]
0x180011cde  jnz     short loc_180011CE8
0x180011ce0  mov     rax, [r14+8]
0x180011ce4  sub     rax, [r15+8]
0x180011ce8  test    rax, rax
0x180011ceb  jz      loc_180011DA4
0x180011cf1  lea     r12, [rcx+r8]
0x180011cf5  imul    r13, rdx, 70h ; 'p'
0x180011cf9  add     r13, r9
0x180011cfc  mov     [rbp+57h+var_98], r13
0x180011d00  movzx   eax, byte ptr [r13+14h]
0x180011d05  test    al, al
0x180011d07  jnz     short loc_180011D36
0x180011d09  mov     rdx, r12
0x180011d0c  call    ?RemoveEntry@?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@QEAAXAEBU_IPV6_PATH_KEY@@@Z; NcsiCantConnectList<_IPV6_PATH_KEY>::RemoveEntry(_IPV6_PATH_KEY const &)
0x180011d11  mov     r10, cs:WPP_GLOBAL_Control
0x180011d18  cmp     byte ptr [r10+19h], 5
0x180011d1d  jb      loc_180011DA4
0x180011d23  mov     r8d, 3
0x180011d29  mov     rdx, r13
0x180011d2c  mov     rcx, r12
0x180011d2f  call    ?VerboseMessage@@YAXAEBU_IPV6_PATH_KEY@@AEBU_IPV6_PATH_ROD@@W4PathState@@@Z; VerboseMessage(_IPV6_PATH_KEY const &,_IPV6_PATH_ROD const &,PathState)
0x180011d34  jmp     short loc_180011D9D
0x180011d36  cmp     byte ptr [r13+15h], 0
0x180011d3b  jnz     loc_180011EEE
0x180011d41  mov     r8d, [r13+10h]
0x180011d45  cmp     r8d, 0EA60h
0x180011d4c  jbe     loc_180011DF9
0x180011d52  cmp     byte ptr [r10+19h], 5
0x180011d57  jb      short loc_180011DA4
0x180011d59  cmp     r10, r11
0x180011d5c  jz      short loc_180011DA4
0x180011d5e  test    byte ptr [r10+1Ch], 2
0x180011d63  jz      short loc_180011DA4
0x180011d65  mov     edx, eax
0x180011d67  mov     rax, cs:off_18007D108; "PathStateCanConnectTooOld"
0x180011d6e  mov     [rsp+100h+var_B8], rax
0x180011d73  mov     [rsp+100h+var_C0], r8d
0x180011d78  movzx   ecx, byte ptr [r13+15h]
0x180011d7d  mov     [rsp+100h+var_C8], ecx
0x180011d81  mov     [rsp+100h+var_D0], edx
0x180011d85  mov     [rsp+100h+var_D8], r15
0x180011d8a  mov     [rsp+100h+var_E0], r14
0x180011d8f  mov     r9, [r12+8]
0x180011d94  mov     rcx, [r10+10h]
0x180011d98  call    WPP_SF_i_IPV6__IPV6_ddds
0x180011d9d  mov     r10, cs:WPP_GLOBAL_Control
0x180011da4  inc     esi
0x180011da6  cmp     esi, cs:?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x180011dac  mov     r8, [rbp+57h+var_A8]
0x180011db0  mov     r9, [rbp+57h+var_A0]
0x180011db4  mov     ebx, [rbp+57h+var_B0]
0x180011db7  lea     r11, WPP_GLOBAL_Control
0x180011dbe  mov     edi, 17h
0x180011dc3  jb      loc_180011CC0
0x180011dc9  lea     rdi, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180011dd0  mov     rcx, rdi; lpCriticalSection
0x180011dd3  call    cs:__imp_LeaveCriticalSection
0x180011dd9  mov     rcx, [rbp+57h+var_48]
0x180011ddd  xor     rcx, rsp; StackCookie
0x180011de0  call    __security_check_cookie
0x180011de5  add     rsp, 0C8h
0x180011dec  pop     r15
0x180011dee  pop     r14
0x180011df0  pop     r13
0x180011df2  pop     r12
0x180011df4  pop     rdi
0x180011df5  pop     rsi
0x180011df6  pop     rbx
0x180011df7  pop     rbp
0x180011df8  retn
0x180011df9  cmp     ebx, 0EA60h
0x180011dff  jb      loc_180011D52
0x180011e05  cmp     r8d, 3A98h
0x180011e0c  jbe     loc_180011EB7
0x180011e12  lea     rcx, ?g_ncsiCantConnectStoreIPv6@@3V?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@A; lpCriticalSection
0x180011e19  call    cs:__imp_EnterCriticalSection
0x180011e1f  mov     rdx, r12
0x180011e22  lea     rcx, qword_18009D6E8
0x180011e29  call    ?erase@?$_Tree@V?$_Tmap_traits@U_IPV6_PATH_KEY@@KU?$less@U_IPV6_PATH_KEY@@@std@@V?$allocator@U?$pair@$$CBU_IPV6_PATH_KEY@@K@std@@@3@$0A@@std@@@std@@QEAA_KAEBU_IPV6_PATH_KEY@@@Z; std::_Tree<std::_Tmap_traits<_IPV6_PATH_KEY,ulong,std::less<_IPV6_PATH_KEY>,std::allocator<std::pair<_IPV6_PATH_KEY const,ulong>>,0>>::erase(_IPV6_PATH_KEY const &)
0x180011e2e  lea     rcx, ?g_ncsiCantConnectStoreIPv6@@3V?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@A; lpCriticalSection
0x180011e35  call    cs:__imp_LeaveCriticalSection
0x180011e3b  movzx   ecx, byte ptr [r12+10h]; this
0x180011e41  mov     eax, ecx
0x180011e43  and     eax, 0F0h
0x180011e48  jz      short loc_180011E55
0x180011e4a  cmp     eax, 0F0h
0x180011e4f  jnz     loc_1800120FE
0x180011e55  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180011e5c  lea     rax, WPP_GLOBAL_Control
0x180011e63  cmp     rcx, rax
0x180011e66  jnz     loc_1800120D0
0x180011e6c  xorps   xmm0, xmm0
0x180011e6f  movups  [rbp+57h+var_60], xmm0
0x180011e73  mov     word ptr [rbp+57h+var_60], di
0x180011e77  movups  xmm0, xmmword ptr [r12+10h]
0x180011e7d  movups  [rbp+57h+var_60+4], xmm0
0x180011e81  lea     rdx, [r12+8]; union _NET_LUID_LH *
0x180011e86  lea     r8, [rbp+57h+var_60]; struct INX_ADDR *
0x180011e8a  call    ?StoreSuccessfulPath@LocalConnects@@AEAAXAEBT_NET_LUID_LH@@AEBUINX_ADDR@@@Z; LocalConnects::StoreSuccessfulPath(_NET_LUID_LH const &,INX_ADDR const &)
0x180011e8f  mov     r10, cs:WPP_GLOBAL_Control
0x180011e96  cmp     byte ptr [r10+19h], 5
0x180011e9b  jb      loc_180011DA4
0x180011ea1  mov     r8d, 5
0x180011ea7  mov     rdx, r13
0x180011eaa  mov     rcx, r12
0x180011ead  call    ?VerboseMessage@@YAXAEBU_IPV6_PATH_KEY@@AEBU_IPV6_PATH_ROD@@W4PathState@@@Z; VerboseMessage(_IPV6_PATH_KEY const &,_IPV6_PATH_ROD const &,PathState)
0x180011eb2  jmp     loc_180011D9D
0x180011eb7  cmp     byte ptr [r10+19h], 5
0x180011ebc  jb      loc_180011DA4
0x180011ec2  cmp     r10, r11
0x180011ec5  jz      loc_180011DA4
0x180011ecb  test    byte ptr [r10+1Ch], 2
0x180011ed0  jz      loc_180011DA4
0x180011ed6  mov     edx, eax
0x180011ed8  mov     rax, cs:off_18007D100; "PathStateCanConnectTooNew"
0x180011edf  mov     [rsp+100h+var_B8], rax
0x180011ee4  mov     [rsp+100h+var_C0], r8d
0x180011ee9  jmp     loc_180011D78
0x180011eee  movzx   ecx, byte ptr [r12+10h]; this
0x180011ef4  mov     eax, ecx
0x180011ef6  and     eax, 0F0h
0x180011efb  jz      short loc_180011F08
0x180011efd  cmp     eax, 0F0h
0x180011f02  jnz     loc_1800121FE
0x180011f08  lea     rax, [r12+8]
0x180011f0d  mov     [rbp+57h+var_90], rax
0x180011f11  xorps   xmm0, xmm0
0x180011f14  movups  [rbp+57h+var_60], xmm0
0x180011f18  mov     word ptr [rbp+57h+var_60], di
0x180011f1c  movups  xmm0, xmmword ptr [r12+10h]
0x180011f22  movups  [rbp+57h+var_60+4], xmm0
0x180011f26  lea     rbx, ?g_ncsiLocalConnects@@3VLocalConnects@@A; LocalConnects g_ncsiLocalConnects
0x180011f2d  mov     rcx, rbx; lpCriticalSection
0x180011f30  call    cs:__imp_EnterCriticalSection
0x180011f36  mov     [rbp+57h+var_80], rbx
0x180011f3a  mov     rax, cs:qword_18009D668
0x180011f41  mov     rbx, [rax+8]
0x180011f45  xor     ecx, ecx
0x180011f47  mov     [rbp+57h+var_6C], ecx
0x180011f4a  mov     rdi, rax
0x180011f4d  cmp     [rbx+19h], cl
0x180011f50  jnz     short loc_180011F7E
0x180011f52  lea     rcx, [rbx+20h]; Buf1
0x180011f56  mov     r8d, 8; Size
0x180011f5c  lea     rdx, [r12+8]; Buf2
0x180011f61  call    memcmp_0
0x180011f66  test    eax, eax
0x180011f68  js      loc_18001224E
0x180011f6e  mov     rdi, rbx
0x180011f71  mov     rbx, [rbx]
0x180011f74  cmp     byte ptr [rbx+19h], 0
0x180011f78  jz      short loc_180011F52
0x180011f7a  mov     r13, [rbp+57h+var_98]
0x180011f7e  cmp     byte ptr [rdi+19h], 0
0x180011f82  jnz     loc_1800120C1
0x180011f88  lea     rdx, [rdi+20h]; Buf2
0x180011f8c  mov     r8d, 8; Size
0x180011f92  lea     rcx, [r12+8]; Buf1
0x180011f97  call    memcmp_0
0x180011f9c  test    eax, eax
0x180011f9e  js      loc_1800120C1
0x180011fa4  mov     rax, cs:qword_18009D668
0x180011fab  cmp     rdi, rax
0x180011fae  jz      loc_18001203A
0x180011fb4  lea     rbx, [rdi+28h]
0x180011fb8  lea     rdx, [rbp+57h+var_60]
0x180011fbc  mov     rcx, rbx
0x180011fbf  call    ??$_Find@UINX_ADDR@@@?$_Tree@V?$_Tmap_traits@UINX_ADDR@@KU?$less@UINX_ADDR@@@std@@V?$allocator@U?$pair@$$CBUINX_ADDR@@K@std@@@3@$0A@@std@@@std@@AEBAPEAU?$_Tree_node@U?$pair@$$CBUINX_ADDR@@K@std@@PEAX@1@AEBUINX_ADDR@@@Z; std::_Tree<std::_Tmap_traits<INX_ADDR,ulong,std::less<INX_ADDR>,std::allocator<std::pair<INX_ADDR const,ulong>>,0>>::_Find<INX_ADDR>(INX_ADDR const &)
0x180011fc4  mov     rdi, rax
0x180011fc7  mov     rbx, [rbx]
0x180011fca  lea     rcx, ?g_ncsiLocalConnects@@3VLocalConnects@@A; lpCriticalSection
0x180011fd1  call    cs:__imp_LeaveCriticalSection
0x180011fd7  cmp     rdi, rbx
0x180011fda  jz      short loc_180012047
0x180011fdc  mov     rdx, r12
0x180011fdf  call    ?AddItem@?$NcsiCantConnectList@U_IPV6_PATH_KEY@@@@QEAA_NAEBU_IPV6_PATH_KEY@@@Z; NcsiCantConnectList<_IPV6_PATH_KEY>::AddItem(_IPV6_PATH_KEY const &)
0x180011fe4  test    al, al
0x180011fe6  jnz     loc_180012194
0x180011fec  mov     dword ptr [r13+10h], 0FFFFFFFFh
0x180011ff4  mov     r10, cs:WPP_GLOBAL_Control
0x180011ffb  cmp     byte ptr [r10+19h], 5
0x180012000  jb      loc_180011DA4
0x180012006  lea     rax, WPP_GLOBAL_Control
0x18001200d  cmp     r10, rax
0x180012010  jz      loc_180011DA4
0x180012016  test    byte ptr [r10+1Ch], 2
0x18001201b  jz      loc_180011DA4
0x180012021  mov     rax, cs:off_18007D0E0; "PathStateCantConnectItemOld"
0x180012028  mov     [rsp+100h+var_B8], rax
0x18001202d  mov     [rsp+100h+var_C0], 0FFFFFFFFh
0x180012035  jmp     loc_18001218A
0x18001203a  lea     rcx, ?g_ncsiLocalConnects@@3VLocalConnects@@A; lpCriticalSection
0x180012041  call    cs:__imp_LeaveCriticalSection
0x180012047  mov     dword ptr [r13+10h], 0FFFFFFFFh
0x18001204f  mov     r10, cs:WPP_GLOBAL_Control
0x180012056  cmp     byte ptr [r10+19h], 5
0x18001205b  jb      loc_180011DA4
0x180012061  lea     rax, WPP_GLOBAL_Control
0x180012068  cmp     r10, rax
0x18001206b  jz      loc_180011DA4
0x180012071  test    byte ptr [r10+1Ch], 2
0x180012076  jz      loc_180011DA4
0x18001207c  movzx   ecx, byte ptr [r13+15h]
0x180012081  movzx   edx, byte ptr [r13+14h]
0x180012086  mov     rax, cs:off_18007D0D0; "PathStateLocalNotConnected"
0x18001208d  mov     [rsp+100h+var_B8], rax
0x180012092  mov     [rsp+100h+var_C0], 0FFFFFFFFh
0x18001209a  mov     [rsp+100h+var_C8], ecx
0x18001209e  mov     [rsp+100h+var_D0], edx
0x1800120a2  mov     [rsp+100h+var_D8], r15
0x1800120a7  mov     [rsp+100h+var_E0], r14
0x1800120ac  mov     rax, [rbp+57h+var_90]
0x1800120b0  mov     r9, [rax]
0x1800120b3  mov     rcx, [r10+10h]
0x1800120b7  call    WPP_SF_i_IPV6__IPV6_ddds
0x1800120bc  jmp     loc_180011D9D
0x1800120c1  mov     rax, cs:qword_18009D668
0x1800120c8  mov     rdi, rax
0x1800120cb  jmp     loc_180011FAB
0x1800120d0  test    byte ptr [rcx+1Ch], 2
0x1800120d4  jz      loc_180011E6C
0x1800120da  cmp     byte ptr [rcx+19h], 5
0x1800120de  jb      loc_180011E6C
0x1800120e4  mov     edx, 15h
0x1800120e9  lea     r8, WPP_d2d73694d2e23c12fceb2d470f7bf333_Traceguids
0x1800120f0  mov     rcx, [rcx+10h]
0x1800120f4  call    WPP_SF_
0x1800120f9  jmp     loc_180011E6C
0x1800120fe  xorps   xmm0, xmm0
0x180012101  xor     eax, eax
0x180012103  movups  [rbp+57h+var_60], xmm0
0x180012107  mov     [rbp+57h+var_50], eax
0x18001210a  mov     word ptr [rbp+57h+var_60], di
0x18001210e  mov     byte ptr [rbp+57h+var_60+4], cl
0x180012111  movsd   xmm0, qword ptr [r12+11h]
0x180012118  movsd   qword ptr [rbp+57h+var_60+5], xmm0
0x18001211d  mov     eax, [r12+19h]
0x180012122  mov     dword ptr [rbp+57h+var_60+0Dh], eax
0x180012125  movzx   eax, word ptr [r12+1Dh]
0x18001212b  mov     word ptr [rbp+57h+var_50+1], ax
0x18001212f  movzx   eax, byte ptr [r12+1Fh]
0x180012135  mov     byte ptr [rbp+57h+var_50+3], al
0x180012138  lea     rdx, [rbp+57h+var_60]; struct INX_ADDR *
  ... truncated ...
```
