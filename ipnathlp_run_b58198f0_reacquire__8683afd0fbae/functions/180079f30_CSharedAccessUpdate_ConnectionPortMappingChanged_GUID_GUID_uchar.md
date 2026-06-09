# CSharedAccessUpdate::ConnectionPortMappingChanged(_GUID *,_GUID *,uchar)

- ea: `0x180079f30`
- end: `0x18007a52b`
- name: `?ConnectionPortMappingChanged@CSharedAccessUpdate@@UEAAJPEAU_GUID@@0E@Z`
- size: `1531`
- prototype: `__int64 __fastcall(CSharedAccessUpdate *this, struct _GUID *, struct _GUID *, char)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x1800237f8`
- `0x1800437a0`
- `0x180044320`
- `0x180045c6c`
- `0x180052bf4`
- `0x1800561cc`
- `0x1800564cc`
- `0x180079f30`
- `0x18007a534`
- `0x18007a608`
- `0x18007bb0c`
- `0x18007bdb8`
- `0x18008213c`
- `0x180082234`
- `0x18008232c`
- `0x180082424`
- `0x18008757c`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a0d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a0d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a0ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a0ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079f95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a4be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180079f95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007a4be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007a4db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a122`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007a122`

## pseudocode

```c
__int64 __fastcall CSharedAccessUpdate::ConnectionPortMappingChanged(
        CSharedAccessUpdate *this,
        struct _GUID *a2,
        struct _GUID *a3,
        char a4)
{
  signed int TargetAddressForPortMappingEntry; // edi
  __int64 ConnectionEntry; // rax
  __int64 v9; // rsi
  unsigned __int16 v10; // bx
  unsigned __int16 v11; // r13
  unsigned __int8 v12; // r12
  _QWORD *PortMappingEntry; // rax
  int v14; // edx
  int v15; // r9d
  _QWORD *v16; // rbx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  int v19; // eax
  unsigned __int16 v20; // r14
  void *v21; // rcx
  unsigned __int8 v22; // r14
  HANDLE ProcessHeap; // rax
  _QWORD *v24; // rax
  struct _GUID *v25; // rax
  _BYTE *v26; // r14
  char v27; // r15
  __int64 v28; // rdx
  __int64 v29; // rcx
  _DWORD *v30; // r15
  int v31; // edx
  int v32; // r9d
  unsigned int v33; // eax
  _QWORD *v34; // rcx
  int TicketsForLocalhost; // eax
  _QWORD *v36; // rcx
  char v38; // [rsp+31h] [rbp-27h]
  _BYTE v39[2]; // [rsp+32h] [rbp-26h] BYREF
  int v40; // [rsp+34h] [rbp-24h]
  unsigned int v41; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v42; // [rsp+3Ch] [rbp-1Ch] BYREF
  struct IHNetCfgMgr *v43; // [rsp+40h] [rbp-18h] BYREF
  __int64 v44; // [rsp+48h] [rbp-10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7b027e7f9e2431f2e35b1562f1d7a5e3_Traceguids);
  }
  v39[0] = 0;
  v38 = 1;
  TargetAddressForPortMappingEntry = 0;
  EnterCriticalSection(&NatInterfaceLock);
  ConnectionEntry = NatFindConnectionEntry(a2);
  v9 = ConnectionEntry;
  if ( ConnectionEntry )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
    v40 = 0;
    if ( (*(_DWORD *)(ConnectionEntry + 76) & 0x40000000) == 0 )
    {
      v22 = 0;
      goto LABEL_68;
    }
    PortMappingEntry = (_QWORD *)NatFindPortMappingEntry(ConnectionEntry, a3);
    v16 = PortMappingEntry;
    if ( PortMappingEntry )
    {
      v17 = *PortMappingEntry;
      if ( *(_QWORD **)(*PortMappingEntry + 8LL) != PortMappingEntry )
        goto LABEL_56;
      v18 = (_QWORD *)PortMappingEntry[1];
      if ( (_QWORD *)*v18 != v16 )
        goto LABEL_56;
      *v18 = v17;
      *(_QWORD *)(v17 + 8) = v18;
      if ( *((_BYTE *)v16 + 28) )
      {
        if ( v16[4] )
        {
          (*(void (__fastcall **)(struct IUdpBroadcastMapper *))(*(_QWORD *)NhpUdpBroadcastMapper + 32LL))(NhpUdpBroadcastMapper);
          v16[4] = 0;
        }
        --*(_DWORD *)(v9 + 184);
      }
      else
      {
        v19 = *((_DWORD *)v16 + 5);
        if ( v19 == INADDR_LOOPBACK_NO )
        {
          NatDeleteTicketsForLocalhost(
            (const struct _NAT_CONNECTION_INFO *)v9,
            (const struct _NAT_PORT_MAPPING_ENTRY *)v16,
            0xFFFFFFFF);
        }
        else
        {
          LOBYTE(v14) = *((_BYTE *)v16 + 16);
          NatDeleteTicket(*(_DWORD *)(v9 + 88), v14, *((unsigned __int16 *)v16 + 9), v15, *((_WORD *)v16 + 12), v19);
        }
        --*(_DWORD *)(v9 + 180);
      }
      v12 = *((_BYTE *)v16 + 16);
      v20 = *((_WORD *)v16 + 9);
      TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v16[7] + 40LL))(
                                           v16[7],
                                           v39);
      if ( TargetAddressForPortMappingEntry < 0 || !v39[0] )
      {
        v11 = v20;
        v38 = *((_BYTE *)v16 + 27);
        goto LABEL_23;
      }
      v11 = v20;
      if ( !a4 )
      {
LABEL_38:
        v26 = (char *)v16 + 27;
        v27 = *((_BYTE *)v16 + 27);
        TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v16[7] + 56LL))(
                                             v16[7],
                                             (__int64)v16 + 27);
        if ( TargetAddressForPortMappingEntry >= 0 )
        {
          if ( !v27 )
            v38 = *v26 != 0;
          v30 = (_DWORD *)v16 + 5;
          LOBYTE(v28) = *v26;
          LOBYTE(v29) = *(_BYTE *)(v9 + 114);
          TargetAddressForPortMappingEntry = NatGetTargetAddressForPortMappingEntry(v29, v28, v16[7], (char *)v16 + 20);
          if ( TargetAddressForPortMappingEntry >= 0 )
          {
            TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v16[7] + 96LL))(
                                                 v16[7],
                                                 v16 + 3);
            v21 = v16;
            if ( TargetAddressForPortMappingEntry < 0 )
              goto LABEL_24;
            if ( (unsigned __int8)NatIsPortMappingAllowed(v16, 0) )
            {
              LOBYTE(v31) = *((_BYTE *)v16 + 16);
              if ( (_BYTE)v31 == 17 && *v30 == -1 )
              {
                v42 = 0;
                v41 = 0;
                if ( NhQueryScopeInformation(&v42, &v41) )
                {
                  v33 = v41;
                  *((_BYTE *)v16 + 28) = 1;
                  TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(struct IUdpBroadcastMapper *, _QWORD, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)NhpUdpBroadcastMapper + 24LL))(
                                                       NhpUdpBroadcastMapper,
                                                       *((unsigned __int16 *)v16 + 9),
                                                       *(unsigned int *)(v9 + 88),
                                                       ~v33 | v42 & v33,
                                                       v16 + 4);
                  if ( TargetAddressForPortMappingEntry >= 0 )
                  {
                    v34 = *(_QWORD **)(v9 + 168);
                    if ( *v34 == v9 + 160 )
                    {
                      *v16 = v9 + 160;
                      v16[1] = v34;
                      *v34 = v16;
                      *(_QWORD *)(v9 + 168) = v16;
                      ++*(_DWORD *)(v9 + 184);
LABEL_58:
                      v22 = *((_BYTE *)v16 + 16);
                      v10 = *((_WORD *)v16 + 9);
                      goto LABEL_68;
                    }
                    goto LABEL_56;
                  }
                }
                else
                {
                  TargetAddressForPortMappingEntry = -2147467259;
                }
              }
              else
              {
                if ( *v30 == INADDR_LOOPBACK_NO )
                  TicketsForLocalhost = NatCreateTicketsForLocalhost(
                                          (const struct _NAT_CONNECTION_INFO *)v9,
                                          (const struct _NAT_PORT_MAPPING_ENTRY *)v16);
                else
                  TicketsForLocalhost = NatCreateTicket(
                                          *(_DWORD *)(v9 + 88),
                                          v31,
                                          *((unsigned __int16 *)v16 + 9),
                                          v32,
                                          *((_WORD *)v16 + 12),
                                          *v30);
                if ( !TicketsForLocalhost )
                {
                  v36 = *(_QWORD **)(v9 + 168);
                  if ( *v36 == v9 + 160 )
                  {
                    *v16 = v9 + 160;
                    v16[1] = v36;
                    *v36 = v16;
                    *(_QWORD *)(v9 + 168) = v16;
                    ++*(_DWORD *)(v9 + 180);
                    goto LABEL_58;
                  }
LABEL_56:
                  __fastfail(3u);
                }
                if ( TicketsForLocalhost > 0 )
                  TargetAddressForPortMappingEntry = (unsigned __int16)TicketsForLocalhost | 0x80070000;
                else
                  TargetAddressForPortMappingEntry = TicketsForLocalhost;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    11,
                    WPP_7b027e7f9e2431f2e35b1562f1d7a5e3_Traceguids,
                    (unsigned int)TicketsForLocalhost);
                }
              }
            }
          }
        }
LABEL_23:
        v21 = v16;
LABEL_24:
        NatFreePortMappingEntry(v21);
        v10 = v40;
        v22 = 0;
LABEL_68:
        if ( (*(_DWORD *)(v9 + 76) & 0x40000000) != 0 && (unsigned int)NhIsAlgStarted() )
        {
          if ( v12 && v11 )
            AlgRmPortMappingChanged(*(_DWORD *)(v9 + 64), v12, v11);
          if ( v22 && v10 && (v12 != v22 || v11 != v10) )
            AlgRmPortMappingChanged(*(_DWORD *)(v9 + 64), v22, v10);
        }
        goto LABEL_78;
      }
LABEL_36:
      TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v16[6] + 40LL))(
                                           v16[6],
                                           v16 + 2);
      if ( TargetAddressForPortMappingEntry < 0 )
        goto LABEL_23;
      TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v16[6] + 56LL))(
                                           v16[6],
                                           (__int64)v16 + 18);
      if ( TargetAddressForPortMappingEntry < 0 )
        goto LABEL_23;
      goto LABEL_38;
    }
    ProcessHeap = GetProcessHeap();
    v24 = HeapAlloc(ProcessHeap, 8u, 0x40u);
    v16 = v24;
    if ( v24 && (memset_0(v24, 0, 0x40u), v25 = (struct _GUID *)CoTaskMemAlloc(0x10u), (v16[5] = v25) != 0) )
    {
      *v25 = *a3;
      v43 = 0;
      v44 = 0;
      TargetAddressForPortMappingEntry = NhGetHNetCfgMgr(&v43);
      if ( TargetAddressForPortMappingEntry >= 0 )
      {
        TargetAddressForPortMappingEntry = (**(__int64 (__fastcall ***)(struct IHNetCfgMgr *, GUID *, __int64 *))v43)(
                                             v43,
                                             &GUID_85d18b70_3032_11d4_9348_00c04f8eeb71,
                                             &v44);
        (*(void (__fastcall **)(struct IHNetCfgMgr *))(*(_QWORD *)v43 + 16LL))(v43);
        if ( TargetAddressForPortMappingEntry >= 0 )
        {
          TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(__int64, struct _GUID *, _QWORD *))(*(_QWORD *)v44 + 56LL))(
                                               v44,
                                               a3,
                                               v16 + 6);
          if ( TargetAddressForPortMappingEntry >= 0 )
            TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)(v9 + 96) + 112LL))(
                                                 *(_QWORD *)(v9 + 96),
                                                 v16[6],
                                                 v16 + 7);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          if ( TargetAddressForPortMappingEntry >= 0 )
          {
            TargetAddressForPortMappingEntry = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)v16[7] + 40LL))(
                                                 v16[7],
                                                 v39);
            if ( TargetAddressForPortMappingEntry >= 0 )
            {
              if ( v39[0] )
                goto LABEL_36;
            }
          }
        }
      }
      v38 = 0;
      NatFreePortMappingEntry(v16);
    }
    else
    {
      TargetAddressForPortMappingEntry = -2147024882;
    }
    v10 = v40;
    v22 = 0;
    goto LABEL_68;
  }
LABEL_78:
  LeaveCriticalSection(&NatInterfaceLock);
  if ( v38 )
  {
    EnterCriticalSection(&NhLock);
    NhFreeDhcpReservations();
    NhBuildDhcpReservations();
    LeaveCriticalSection(&NhLock);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_7b027e7f9e2431f2e35b1562f1d7a5e3_Traceguids);
  }
  return (unsigned int)TargetAddressForPortMappingEntry;
}

```

## disassembly

```asm
0x180079f30  push    rbp
0x180079f32  push    rbx
0x180079f33  push    rsi
0x180079f34  push    rdi
0x180079f35  push    r12
0x180079f37  push    r13
0x180079f39  push    r14
0x180079f3b  push    r15
0x180079f3d  mov     rbp, rsp
0x180079f40  sub     rsp, 58h
0x180079f44  mov     r15b, r9b
0x180079f47  mov     r14, r8
0x180079f4a  mov     rbx, rdx
0x180079f4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079f54  lea     r12, WPP_GLOBAL_Control
0x180079f5b  cmp     rcx, r12
0x180079f5e  jz      short loc_180079F84
0x180079f60  test    dword ptr [rcx+1Ch], 200h
0x180079f67  jz      short loc_180079F84
0x180079f69  cmp     byte ptr [rcx+19h], 6
0x180079f6d  jb      short loc_180079F84
0x180079f6f  mov     rcx, [rcx+10h]
0x180079f73  lea     r8, WPP_7b027e7f9e2431f2e35b1562f1d7a5e3_Traceguids
0x180079f7a  mov     edx, 0Ah
0x180079f7f  call    WPP_SF_
0x180079f84  lea     rcx, NatInterfaceLock; lpCriticalSection
0x180079f8b  mov     [rbp+var_26], 0
0x180079f8f  mov     [rbp+var_27], 1
0x180079f93  xor     edi, edi
0x180079f95  call    cs:__imp_EnterCriticalSection
0x180079f9c  nop     dword ptr [rax+rax+00h]
0x180079fa1  mov     rcx, rbx
0x180079fa4  call    NatFindConnectionEntry
0x180079fa9  mov     rsi, rax
0x180079fac  test    rax, rax
0x180079faf  jz      loc_18007A49E
0x180079fb5  xor     ebx, ebx
0x180079fb7  xor     r13d, r13d
0x180079fba  xor     r12b, r12b
0x180079fbd  mov     [rbp+var_24], ebx
0x180079fc0  test    dword ptr [rax+4Ch], 40000000h
0x180079fc7  mov     [rbp+var_28], bl
0x180079fca  jz      loc_18007A440
0x180079fd0  mov     rdx, r14
0x180079fd3  mov     rcx, rax
0x180079fd6  call    NatFindPortMappingEntry
0x180079fdb  or      edi, 0FFFFFFFFh
0x180079fde  mov     rbx, rax
0x180079fe1  test    rax, rax
0x180079fe4  jz      loc_18007A0D2
0x180079fea  mov     rcx, [rax]
0x180079fed  cmp     [rcx+8], rax
0x180079ff1  jnz     loc_18007A3B0
0x180079ff7  mov     rax, [rax+8]
0x180079ffb  cmp     [rax], rbx
0x180079ffe  jnz     loc_18007A3B0
0x18007a004  mov     [rax], rcx
0x18007a007  mov     [rcx+8], rax
0x18007a00b  cmp     [rbx+1Ch], r13b
0x18007a00f  jz      short loc_18007A039
0x18007a011  mov     rdx, [rbx+20h]
0x18007a015  test    rdx, rdx
0x18007a018  jz      short loc_18007A031
0x18007a01a  mov     rcx, cs:?NhpUdpBroadcastMapper@@3PEAUIUdpBroadcastMapper@@EA; IUdpBroadcastMapper * NhpUdpBroadcastMapper
0x18007a021  mov     rax, [rcx]
0x18007a024  mov     rax, [rax+20h]
0x18007a028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a02d  mov     [rbx+20h], r13
0x18007a031  add     [rsi+0B8h], edi
0x18007a037  jmp     short loc_18007A077
0x18007a039  mov     eax, [rbx+14h]
0x18007a03c  cmp     eax, cs:?INADDR_LOOPBACK_NO@@3KA; ulong INADDR_LOOPBACK_NO
0x18007a042  jnz     short loc_18007A054
0x18007a044  mov     r8d, edi; unsigned int
0x18007a047  mov     rdx, rbx; struct _NAT_PORT_MAPPING_ENTRY *
0x18007a04a  mov     rcx, rsi; struct _NAT_CONNECTION_INFO *
0x18007a04d  call    ?NatDeleteTicketsForLocalhost@@YAXPEBU_NAT_CONNECTION_INFO@@PEBU_NAT_PORT_MAPPING_ENTRY@@K@Z; NatDeleteTicketsForLocalhost(_NAT_CONNECTION_INFO const *,_NAT_PORT_MAPPING_ENTRY const *,ulong)
0x18007a052  jmp     short loc_18007A071
0x18007a054  movzx   r8d, word ptr [rbx+12h]
0x18007a059  mov     dl, [rbx+10h]
0x18007a05c  mov     ecx, [rsi+58h]
0x18007a05f  mov     [rsp+58h+var_30], eax
0x18007a063  movzx   eax, word ptr [rbx+18h]
0x18007a067  mov     word ptr [rsp+58h+var_38], ax
0x18007a06c  call    NatDeleteTicket
0x18007a071  add     [rsi+0B4h], edi
0x18007a077  mov     rcx, [rbx+38h]
0x18007a07b  lea     rdx, [rbp+var_26]
0x18007a07f  mov     r12b, [rbx+10h]
0x18007a083  movzx   r14d, word ptr [rbx+12h]
0x18007a088  mov     rax, [rcx]
0x18007a08b  mov     rax, [rax+28h]
0x18007a08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a094  mov     edi, eax
0x18007a096  test    eax, eax
0x18007a098  js      short loc_18007A0B2
0x18007a09a  cmp     [rbp+var_26], r13b
0x18007a09e  jz      short loc_18007A0B2
0x18007a0a0  movzx   r13d, r14w
0x18007a0a4  test    r15b, r15b
0x18007a0a7  jz      loc_18007A241
0x18007a0ad  jmp     loc_18007A205
0x18007a0b2  mov     r15b, [rbx+1Bh]
0x18007a0b6  movzx   r13d, r14w
0x18007a0ba  mov     [rbp+var_27], r15b
0x18007a0be  mov     rcx, rbx; lpMem
0x18007a0c1  call    NatFreePortMappingEntry
0x18007a0c6  mov     ebx, [rbp+var_24]
0x18007a0c9  mov     r14b, [rbp+var_28]
0x18007a0cd  jmp     loc_18007A443
0x18007a0d2  call    cs:__imp_GetProcessHeap
0x18007a0d9  nop     dword ptr [rax+rax+00h]
0x18007a0de  mov     edi, 40h ; '@'
0x18007a0e3  mov     rcx, rax; hHeap
0x18007a0e6  mov     r8d, edi; dwBytes
0x18007a0e9  lea     edx, [rdi-38h]; dwFlags
0x18007a0ec  call    cs:__imp_HeapAlloc
0x18007a0f3  nop     dword ptr [rax+rax+00h]
0x18007a0f8  mov     rbx, rax
0x18007a0fb  test    rax, rax
0x18007a0fe  jnz     short loc_18007A110
0x18007a100  mov     edi, 8007000Eh
0x18007a105  mov     ebx, [rbp+var_24]
0x18007a108  mov     r14b, r12b
0x18007a10b  jmp     loc_18007A443
0x18007a110  mov     r8, rdi; Size
0x18007a113  xor     edx, edx; Val
0x18007a115  mov     rcx, rbx; void *
0x18007a118  call    memset_0
0x18007a11d  mov     ecx, 10h; cb
0x18007a122  call    cs:__imp_CoTaskMemAlloc
0x18007a129  nop     dword ptr [rax+rax+00h]
0x18007a12e  mov     [rbx+28h], rax
0x18007a132  test    rax, rax
0x18007a135  jz      short loc_18007A100
0x18007a137  movups  xmm0, xmmword ptr [r14]
0x18007a13b  lea     rcx, [rbp+var_18]; struct IHNetCfgMgr **
0x18007a13f  movdqu  xmmword ptr [rax], xmm0
0x18007a143  mov     [rbp+var_18], r13
0x18007a147  mov     [rbp+var_10], r13
0x18007a14b  call    ?NhGetHNetCfgMgr@@YAJPEAPEAUIHNetCfgMgr@@@Z; NhGetHNetCfgMgr(IHNetCfgMgr * *)
0x18007a150  mov     edi, eax
0x18007a152  test    eax, eax
0x18007a154  js      loc_18007A42F
0x18007a15a  mov     rcx, [rbp+var_18]
0x18007a15e  lea     r8, [rbp+var_10]
0x18007a162  lea     rdx, _GUID_85d18b70_3032_11d4_9348_00c04f8eeb71
0x18007a169  mov     rax, [rcx]
0x18007a16c  mov     rax, [rax]
0x18007a16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a174  mov     rcx, [rbp+var_18]
0x18007a178  mov     edi, eax
0x18007a17a  mov     rax, [rcx]
0x18007a17d  mov     rax, [rax+10h]
0x18007a181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a186  test    edi, edi
0x18007a188  js      loc_18007A42F
0x18007a18e  mov     rcx, [rbp+var_10]
0x18007a192  lea     r8, [rbx+30h]
0x18007a196  mov     rdx, r14
0x18007a199  mov     rax, [rcx]
0x18007a19c  mov     rax, [rax+38h]
0x18007a1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1a5  mov     edi, eax
0x18007a1a7  test    eax, eax
0x18007a1a9  js      short loc_18007A1C5
0x18007a1ab  mov     rcx, [rsi+60h]
0x18007a1af  lea     r8, [rbx+38h]
0x18007a1b3  mov     rdx, [rbx+30h]
0x18007a1b7  mov     rax, [rcx]
0x18007a1ba  mov     rax, [rax+70h]
0x18007a1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1c3  mov     edi, eax
0x18007a1c5  mov     rcx, [rbp+var_10]
0x18007a1c9  mov     rax, [rcx]
0x18007a1cc  mov     rax, [rax+10h]
0x18007a1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1d5  test    edi, edi
0x18007a1d7  js      loc_18007A42F
0x18007a1dd  mov     rcx, [rbx+38h]
0x18007a1e1  lea     rdx, [rbp+var_26]
0x18007a1e5  mov     rax, [rcx]
0x18007a1e8  mov     rax, [rax+28h]
0x18007a1ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a1f1  mov     edi, eax
0x18007a1f3  test    eax, eax
0x18007a1f5  js      loc_18007A42F
0x18007a1fb  cmp     [rbp+var_26], r12b
0x18007a1ff  jz      loc_18007A42F
0x18007a205  mov     rcx, [rbx+30h]
0x18007a209  lea     rdx, [rbx+10h]
0x18007a20d  mov     rax, [rcx]
0x18007a210  mov     rax, [rax+28h]
0x18007a214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a219  mov     edi, eax
0x18007a21b  test    eax, eax
0x18007a21d  js      loc_18007A0BE
0x18007a223  mov     rcx, [rbx+30h]
0x18007a227  lea     rdx, [rbx+12h]
0x18007a22b  mov     rax, [rcx]
0x18007a22e  mov     rax, [rax+38h]
0x18007a232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a237  mov     edi, eax
0x18007a239  test    eax, eax
0x18007a23b  js      loc_18007A0BE
0x18007a241  mov     rcx, [rbx+38h]
0x18007a245  lea     r14, [rbx+1Bh]
0x18007a249  mov     r15b, [r14]
0x18007a24c  mov     rdx, r14
0x18007a24f  mov     rax, [rcx]
0x18007a252  mov     rax, [rax+38h]
0x18007a256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a25b  mov     edi, eax
0x18007a25d  test    eax, eax
0x18007a25f  js      loc_18007A0BE
0x18007a265  test    r15b, r15b
0x18007a268  jnz     short loc_18007A274
0x18007a26a  mov     al, [r14]
0x18007a26d  neg     al
0x18007a26f  sbb     cl, cl
0x18007a271  and     [rbp+var_27], cl
0x18007a274  mov     r8, [rbx+38h]
0x18007a278  lea     r15, [rbx+14h]
0x18007a27c  mov     dl, [r14]
0x18007a27f  mov     r9, r15
0x18007a282  mov     cl, [rsi+72h]
0x18007a285  call    NatGetTargetAddressForPortMappingEntry
0x18007a28a  mov     edi, eax
0x18007a28c  test    eax, eax
0x18007a28e  js      loc_18007A0BE
0x18007a294  mov     rcx, [rbx+38h]
0x18007a298  lea     rdx, [rbx+18h]
0x18007a29c  mov     rax, [rcx]
0x18007a29f  mov     rax, [rax+60h]
0x18007a2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a2a8  mov     edi, eax
0x18007a2aa  mov     rcx, rbx
0x18007a2ad  test    eax, eax
0x18007a2af  js      loc_18007A0C1
0x18007a2b5  xor     edx, edx
0x18007a2b7  call    NatIsPortMappingAllowed
0x18007a2bc  test    al, al
0x18007a2be  jz      loc_18007A0BE
0x18007a2c4  mov     dl, [rbx+10h]
0x18007a2c7  cmp     dl, 11h
0x18007a2ca  jnz     loc_18007A36A
0x18007a2d0  cmp     dword ptr [r15], 0FFFFFFFFh
0x18007a2d4  jnz     loc_18007A36A
0x18007a2da  lea     rdx, [rbp+var_20]; unsigned int *
0x18007a2de  mov     [rbp+var_1C], 0
0x18007a2e5  lea     rcx, [rbp+var_1C]; unsigned int *
0x18007a2e9  mov     [rbp+var_20], 0
0x18007a2f0  call    ?NhQueryScopeInformation@@YAEPEAK0@Z; NhQueryScopeInformation(ulong *,ulong *)
0x18007a2f5  test    al, al
0x18007a2f7  jz      short loc_18007A360
0x18007a2f9  mov     eax, [rbp+var_20]
0x18007a2fc  lea     rdx, [rbx+20h]
0x18007a300  mov     byte ptr [rbx+1Ch], 1
0x18007a304  mov     r9d, eax
0x18007a307  mov     rcx, cs:?NhpUdpBroadcastMapper@@3PEAUIUdpBroadcastMapper@@EA; IUdpBroadcastMapper * NhpUdpBroadcastMapper
0x18007a30e  not     eax
0x18007a310  and     r9d, [rbp+var_1C]
0x18007a314  mov     r8d, [rsi+58h]
0x18007a318  or      r9d, eax
0x18007a31b  mov     [rsp+58h+var_38], rdx
0x18007a320  mov     r10, [rcx]
0x18007a323  movzx   edx, word ptr [rbx+12h]
0x18007a327  mov     rax, [r10+18h]
0x18007a32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a330  mov     edi, eax
0x18007a332  test    eax, eax
0x18007a334  js      loc_18007A0BE
0x18007a33a  lea     rax, [rsi+0A0h]
0x18007a341  mov     rcx, [rax+8]
0x18007a345  cmp     [rcx], rax
0x18007a348  jnz     short loc_18007A3B0
0x18007a34a  mov     [rbx], rax
0x18007a34d  mov     [rbx+8], rcx
0x18007a351  mov     [rcx], rbx
0x18007a354  mov     [rax+8], rbx
0x18007a358  inc     dword ptr [rsi+0B8h]
0x18007a35e  jmp     short loc_18007A3CB
0x18007a360  mov     edi, 80004005h
0x18007a365  jmp     loc_18007A0BE
0x18007a36a  mov     eax, [r15]
0x18007a36d  cmp     eax, cs:?INADDR_LOOPBACK_NO@@3KA; ulong INADDR_LOOPBACK_NO
0x18007a373  jnz     short loc_18007A382
0x18007a375  mov     rdx, rbx; struct _NAT_PORT_MAPPING_ENTRY *
0x18007a378  mov     rcx, rsi; struct _NAT_CONNECTION_INFO *
0x18007a37b  call    ?NatCreateTicketsForLocalhost@@YAKPEBU_NAT_CONNECTION_INFO@@PEBU_NAT_PORT_MAPPING_ENTRY@@@Z; NatCreateTicketsForLocalhost(_NAT_CONNECTION_INFO const *,_NAT_PORT_MAPPING_ENTRY const *)
0x18007a380  jmp     short loc_18007A39C
0x18007a382  movzx   r8d, word ptr [rbx+12h]
0x18007a387  mov     ecx, [rsi+58h]
0x18007a38a  mov     [rsp+58h+var_30], eax
0x18007a38e  movzx   eax, word ptr [rbx+18h]
0x18007a392  mov     word ptr [rsp+58h+var_38], ax
0x18007a397  call    NatCreateTicket
0x18007a39c  test    eax, eax
0x18007a39e  jnz     short loc_18007A3D5
0x18007a3a0  lea     rax, [rsi+0A0h]
  ... truncated ...
```
