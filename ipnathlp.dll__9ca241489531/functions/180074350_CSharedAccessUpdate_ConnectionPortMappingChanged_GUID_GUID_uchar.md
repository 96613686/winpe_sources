# CSharedAccessUpdate::ConnectionPortMappingChanged(_GUID *,_GUID *,uchar)

- ea: `0x180074350`
- end: `0x180074920`
- name: `?ConnectionPortMappingChanged@CSharedAccessUpdate@@UEAAJPEAU_GUID@@0E@Z`
- size: `1488`
- prototype: `__int64 __fastcall(CSharedAccessUpdate *this, struct _GUID *, struct _GUID *, char)`
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x1800307ec`
- `0x180040198`
- `0x180040bcc`
- `0x1800429b0`
- `0x18004ed64`
- `0x1800521c0`
- `0x1800524a0`
- `0x180074350`
- `0x180074928`
- `0x1800749f8`
- `0x180075d24`
- `0x180075fa0`
- `0x18007be70`
- `0x18007bf68`
- `0x18007c05c`
- `0x18007c140`
- `0x180080f88`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800744ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800744ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074500`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180074500`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800743b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800748c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800743b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800748c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800748ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800748d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800748ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800748d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074530`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180074530`

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
0x180074350  push    rbp
0x180074352  push    rbx
0x180074353  push    rsi
0x180074354  push    rdi
0x180074355  push    r12
0x180074357  push    r13
0x180074359  push    r14
0x18007435b  push    r15
0x18007435d  mov     rbp, rsp
0x180074360  sub     rsp, 58h
0x180074364  mov     r15b, r9b
0x180074367  mov     r14, r8
0x18007436a  mov     rbx, rdx
0x18007436d  mov     rcx, cs:WPP_GLOBAL_Control
0x180074374  lea     r12, WPP_GLOBAL_Control
0x18007437b  cmp     rcx, r12
0x18007437e  jz      short loc_1800743A4
0x180074380  test    dword ptr [rcx+1Ch], 200h
0x180074387  jz      short loc_1800743A4
0x180074389  cmp     byte ptr [rcx+19h], 6
0x18007438d  jb      short loc_1800743A4
0x18007438f  mov     rcx, [rcx+10h]
0x180074393  lea     r8, WPP_7b027e7f9e2431f2e35b1562f1d7a5e3_Traceguids
0x18007439a  mov     edx, 0Ah
0x18007439f  call    WPP_SF_
0x1800743a4  lea     rcx, NatInterfaceLock; lpCriticalSection
0x1800743ab  mov     [rbp+var_26], 0
0x1800743af  mov     [rbp+var_27], 1
0x1800743b3  xor     edi, edi
0x1800743b5  call    cs:__imp_EnterCriticalSection
0x1800743bb  mov     rcx, rbx
0x1800743be  call    NatFindConnectionEntry
0x1800743c3  mov     rsi, rax
0x1800743c6  test    rax, rax
0x1800743c9  jz      loc_1800748A6
0x1800743cf  xor     ebx, ebx
0x1800743d1  xor     r13d, r13d
0x1800743d4  xor     r12b, r12b
0x1800743d7  mov     [rbp+var_24], ebx
0x1800743da  test    dword ptr [rax+4Ch], 40000000h
0x1800743e1  mov     [rbp+var_28], bl
0x1800743e4  jz      loc_180074848
0x1800743ea  mov     rdx, r14
0x1800743ed  mov     rcx, rax
0x1800743f0  call    NatFindPortMappingEntry
0x1800743f5  or      edi, 0FFFFFFFFh
0x1800743f8  mov     rbx, rax
0x1800743fb  test    rax, rax
0x1800743fe  jz      loc_1800744EC
0x180074404  mov     rcx, [rax]
0x180074407  cmp     [rcx+8], rax
0x18007440b  jnz     loc_1800747B8
0x180074411  mov     rax, [rax+8]
0x180074415  cmp     [rax], rbx
0x180074418  jnz     loc_1800747B8
0x18007441e  mov     [rax], rcx
0x180074421  mov     [rcx+8], rax
0x180074425  cmp     [rbx+1Ch], r13b
0x180074429  jz      short loc_180074453
0x18007442b  mov     rdx, [rbx+20h]
0x18007442f  test    rdx, rdx
0x180074432  jz      short loc_18007444B
0x180074434  mov     rcx, cs:?NhpUdpBroadcastMapper@@3PEAUIUdpBroadcastMapper@@EA; IUdpBroadcastMapper * NhpUdpBroadcastMapper
0x18007443b  mov     rax, [rcx]
0x18007443e  mov     rax, [rax+20h]
0x180074442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074447  mov     [rbx+20h], r13
0x18007444b  add     [rsi+0B8h], edi
0x180074451  jmp     short loc_180074491
0x180074453  mov     eax, [rbx+14h]
0x180074456  cmp     eax, cs:?INADDR_LOOPBACK_NO@@3KA; ulong INADDR_LOOPBACK_NO
0x18007445c  jnz     short loc_18007446E
0x18007445e  mov     r8d, edi; unsigned int
0x180074461  mov     rdx, rbx; struct _NAT_PORT_MAPPING_ENTRY *
0x180074464  mov     rcx, rsi; struct _NAT_CONNECTION_INFO *
0x180074467  call    ?NatDeleteTicketsForLocalhost@@YAXPEBU_NAT_CONNECTION_INFO@@PEBU_NAT_PORT_MAPPING_ENTRY@@K@Z; NatDeleteTicketsForLocalhost(_NAT_CONNECTION_INFO const *,_NAT_PORT_MAPPING_ENTRY const *,ulong)
0x18007446c  jmp     short loc_18007448B
0x18007446e  movzx   r8d, word ptr [rbx+12h]
0x180074473  mov     dl, [rbx+10h]
0x180074476  mov     ecx, [rsi+58h]
0x180074479  mov     [rsp+58h+var_30], eax
0x18007447d  movzx   eax, word ptr [rbx+18h]
0x180074481  mov     word ptr [rsp+58h+var_38], ax
0x180074486  call    NatDeleteTicket
0x18007448b  add     [rsi+0B4h], edi
0x180074491  mov     rcx, [rbx+38h]
0x180074495  lea     rdx, [rbp+var_26]
0x180074499  mov     r12b, [rbx+10h]
0x18007449d  movzx   r14d, word ptr [rbx+12h]
0x1800744a2  mov     rax, [rcx]
0x1800744a5  mov     rax, [rax+28h]
0x1800744a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800744ae  mov     edi, eax
0x1800744b0  test    eax, eax
0x1800744b2  js      short loc_1800744CC
0x1800744b4  cmp     [rbp+var_26], r13b
0x1800744b8  jz      short loc_1800744CC
0x1800744ba  movzx   r13d, r14w
0x1800744be  test    r15b, r15b
0x1800744c1  jz      loc_180074649
0x1800744c7  jmp     loc_18007460D
0x1800744cc  mov     r15b, [rbx+1Bh]
0x1800744d0  movzx   r13d, r14w
0x1800744d4  mov     [rbp+var_27], r15b
0x1800744d8  mov     rcx, rbx; lpMem
0x1800744db  call    NatFreePortMappingEntry
0x1800744e0  mov     ebx, [rbp+var_24]
0x1800744e3  mov     r14b, [rbp+var_28]
0x1800744e7  jmp     loc_18007484B
0x1800744ec  call    cs:__imp_GetProcessHeap
0x1800744f2  mov     edi, 40h ; '@'
0x1800744f7  mov     rcx, rax; hHeap
0x1800744fa  mov     r8d, edi; dwBytes
0x1800744fd  lea     edx, [rdi-38h]; dwFlags
0x180074500  call    cs:__imp_HeapAlloc
0x180074506  mov     rbx, rax
0x180074509  test    rax, rax
0x18007450c  jnz     short loc_18007451E
0x18007450e  mov     edi, 8007000Eh
0x180074513  mov     ebx, [rbp+var_24]
0x180074516  mov     r14b, r12b
0x180074519  jmp     loc_18007484B
0x18007451e  mov     r8, rdi; Size
0x180074521  xor     edx, edx; Val
0x180074523  mov     rcx, rbx; void *
0x180074526  call    memset_0
0x18007452b  mov     ecx, 10h; cb
0x180074530  call    cs:__imp_CoTaskMemAlloc
0x180074536  mov     [rbx+28h], rax
0x18007453a  test    rax, rax
0x18007453d  jz      short loc_18007450E
0x18007453f  movups  xmm0, xmmword ptr [r14]
0x180074543  lea     rcx, [rbp+var_18]; struct IHNetCfgMgr **
0x180074547  movdqu  xmmword ptr [rax], xmm0
0x18007454b  mov     [rbp+var_18], r13
0x18007454f  mov     [rbp+var_10], r13
0x180074553  call    ?NhGetHNetCfgMgr@@YAJPEAPEAUIHNetCfgMgr@@@Z; NhGetHNetCfgMgr(IHNetCfgMgr * *)
0x180074558  mov     edi, eax
0x18007455a  test    eax, eax
0x18007455c  js      loc_180074837
0x180074562  mov     rcx, [rbp+var_18]
0x180074566  lea     r8, [rbp+var_10]
0x18007456a  lea     rdx, _GUID_85d18b70_3032_11d4_9348_00c04f8eeb71
0x180074571  mov     rax, [rcx]
0x180074574  mov     rax, [rax]
0x180074577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007457c  mov     rcx, [rbp+var_18]
0x180074580  mov     edi, eax
0x180074582  mov     rax, [rcx]
0x180074585  mov     rax, [rax+10h]
0x180074589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007458e  test    edi, edi
0x180074590  js      loc_180074837
0x180074596  mov     rcx, [rbp+var_10]
0x18007459a  lea     r8, [rbx+30h]
0x18007459e  mov     rdx, r14
0x1800745a1  mov     rax, [rcx]
0x1800745a4  mov     rax, [rax+38h]
0x1800745a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745ad  mov     edi, eax
0x1800745af  test    eax, eax
0x1800745b1  js      short loc_1800745CD
0x1800745b3  mov     rcx, [rsi+60h]
0x1800745b7  lea     r8, [rbx+38h]
0x1800745bb  mov     rdx, [rbx+30h]
0x1800745bf  mov     rax, [rcx]
0x1800745c2  mov     rax, [rax+70h]
0x1800745c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745cb  mov     edi, eax
0x1800745cd  mov     rcx, [rbp+var_10]
0x1800745d1  mov     rax, [rcx]
0x1800745d4  mov     rax, [rax+10h]
0x1800745d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745dd  test    edi, edi
0x1800745df  js      loc_180074837
0x1800745e5  mov     rcx, [rbx+38h]
0x1800745e9  lea     rdx, [rbp+var_26]
0x1800745ed  mov     rax, [rcx]
0x1800745f0  mov     rax, [rax+28h]
0x1800745f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800745f9  mov     edi, eax
0x1800745fb  test    eax, eax
0x1800745fd  js      loc_180074837
0x180074603  cmp     [rbp+var_26], r12b
0x180074607  jz      loc_180074837
0x18007460d  mov     rcx, [rbx+30h]
0x180074611  lea     rdx, [rbx+10h]
0x180074615  mov     rax, [rcx]
0x180074618  mov     rax, [rax+28h]
0x18007461c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074621  mov     edi, eax
0x180074623  test    eax, eax
0x180074625  js      loc_1800744D8
0x18007462b  mov     rcx, [rbx+30h]
0x18007462f  lea     rdx, [rbx+12h]
0x180074633  mov     rax, [rcx]
0x180074636  mov     rax, [rax+38h]
0x18007463a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007463f  mov     edi, eax
0x180074641  test    eax, eax
0x180074643  js      loc_1800744D8
0x180074649  mov     rcx, [rbx+38h]
0x18007464d  lea     r14, [rbx+1Bh]
0x180074651  mov     r15b, [r14]
0x180074654  mov     rdx, r14
0x180074657  mov     rax, [rcx]
0x18007465a  mov     rax, [rax+38h]
0x18007465e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074663  mov     edi, eax
0x180074665  test    eax, eax
0x180074667  js      loc_1800744D8
0x18007466d  test    r15b, r15b
0x180074670  jnz     short loc_18007467C
0x180074672  mov     al, [r14]
0x180074675  neg     al
0x180074677  sbb     cl, cl
0x180074679  and     [rbp+var_27], cl
0x18007467c  mov     r8, [rbx+38h]
0x180074680  lea     r15, [rbx+14h]
0x180074684  mov     dl, [r14]
0x180074687  mov     r9, r15
0x18007468a  mov     cl, [rsi+72h]
0x18007468d  call    NatGetTargetAddressForPortMappingEntry
0x180074692  mov     edi, eax
0x180074694  test    eax, eax
0x180074696  js      loc_1800744D8
0x18007469c  mov     rcx, [rbx+38h]
0x1800746a0  lea     rdx, [rbx+18h]
0x1800746a4  mov     rax, [rcx]
0x1800746a7  mov     rax, [rax+60h]
0x1800746ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800746b0  mov     edi, eax
0x1800746b2  mov     rcx, rbx
0x1800746b5  test    eax, eax
0x1800746b7  js      loc_1800744DB
0x1800746bd  xor     edx, edx
0x1800746bf  call    NatIsPortMappingAllowed
0x1800746c4  test    al, al
0x1800746c6  jz      loc_1800744D8
0x1800746cc  mov     dl, [rbx+10h]
0x1800746cf  cmp     dl, 11h
0x1800746d2  jnz     loc_180074772
0x1800746d8  cmp     dword ptr [r15], 0FFFFFFFFh
0x1800746dc  jnz     loc_180074772
0x1800746e2  lea     rdx, [rbp+var_20]; unsigned int *
0x1800746e6  mov     [rbp+var_1C], 0
0x1800746ed  lea     rcx, [rbp+var_1C]; unsigned int *
0x1800746f1  mov     [rbp+var_20], 0
0x1800746f8  call    ?NhQueryScopeInformation@@YAEPEAK0@Z; NhQueryScopeInformation(ulong *,ulong *)
0x1800746fd  test    al, al
0x1800746ff  jz      short loc_180074768
0x180074701  mov     eax, [rbp+var_20]
0x180074704  lea     rdx, [rbx+20h]
0x180074708  mov     byte ptr [rbx+1Ch], 1
0x18007470c  mov     r9d, eax
0x18007470f  mov     rcx, cs:?NhpUdpBroadcastMapper@@3PEAUIUdpBroadcastMapper@@EA; IUdpBroadcastMapper * NhpUdpBroadcastMapper
0x180074716  not     eax
0x180074718  and     r9d, [rbp+var_1C]
0x18007471c  mov     r8d, [rsi+58h]
0x180074720  or      r9d, eax
0x180074723  mov     [rsp+58h+var_38], rdx
0x180074728  mov     r10, [rcx]
0x18007472b  movzx   edx, word ptr [rbx+12h]
0x18007472f  mov     rax, [r10+18h]
0x180074733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074738  mov     edi, eax
0x18007473a  test    eax, eax
0x18007473c  js      loc_1800744D8
0x180074742  lea     rax, [rsi+0A0h]
0x180074749  mov     rcx, [rax+8]
0x18007474d  cmp     [rcx], rax
0x180074750  jnz     short loc_1800747B8
0x180074752  mov     [rbx], rax
0x180074755  mov     [rbx+8], rcx
0x180074759  mov     [rcx], rbx
0x18007475c  mov     [rax+8], rbx
0x180074760  inc     dword ptr [rsi+0B8h]
0x180074766  jmp     short loc_1800747D3
0x180074768  mov     edi, 80004005h
0x18007476d  jmp     loc_1800744D8
0x180074772  mov     eax, [r15]
0x180074775  cmp     eax, cs:?INADDR_LOOPBACK_NO@@3KA; ulong INADDR_LOOPBACK_NO
0x18007477b  jnz     short loc_18007478A
0x18007477d  mov     rdx, rbx; struct _NAT_PORT_MAPPING_ENTRY *
0x180074780  mov     rcx, rsi; struct _NAT_CONNECTION_INFO *
0x180074783  call    ?NatCreateTicketsForLocalhost@@YAKPEBU_NAT_CONNECTION_INFO@@PEBU_NAT_PORT_MAPPING_ENTRY@@@Z; NatCreateTicketsForLocalhost(_NAT_CONNECTION_INFO const *,_NAT_PORT_MAPPING_ENTRY const *)
0x180074788  jmp     short loc_1800747A4
0x18007478a  movzx   r8d, word ptr [rbx+12h]
0x18007478f  mov     ecx, [rsi+58h]
0x180074792  mov     [rsp+58h+var_30], eax
0x180074796  movzx   eax, word ptr [rbx+18h]
0x18007479a  mov     word ptr [rsp+58h+var_38], ax
0x18007479f  call    NatCreateTicket
0x1800747a4  test    eax, eax
0x1800747a6  jnz     short loc_1800747DD
0x1800747a8  lea     rax, [rsi+0A0h]
0x1800747af  mov     rcx, [rax+8]
0x1800747b3  cmp     [rcx], rax
0x1800747b6  jz      short loc_1800747BF
0x1800747b8  mov     ecx, 3
  ... truncated ...
```
