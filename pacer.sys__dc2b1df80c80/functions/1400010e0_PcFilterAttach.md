# PcFilterAttach

- ea: `0x1400010e0`
- end: `0x140001811`
- name: `PcFilterAttach`
- size: `1841`
- prototype: `__int64 __fastcall(NDIS_HANDLE NdisFilterHandle)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x1400010e0`
- `0x140001820`
- `0x140001884`
- `0x1400020f0`
- `0x14000287c`
- `0x140002c1c`
- `0x14000bc08`
- `0x14000eb54`
- `0x14000f48c`
- `0x140013110`
- `0x140013600`
- `0x14001fee0`

## import_xrefs

- `ntoskrnl!InitializeSListHead` at `0x1400011b7`
- `ntoskrnl!InitializeSListHead` at `0x1400011b7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400011cb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400011cb`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000179f`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000179f`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400017e2`
- `NDIS!NdisFreeMemoryWithTag` at `0x140001800`
- `NDIS!NdisFreeMemoryWithTag` at `0x1400017e2`
- `NDIS!NdisFreeMemoryWithTag` at `0x140001800`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14000114e`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14000157f`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14000114e`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14000157f`
- `NDIS!NdisFreeRWLock` at `0x1400017cd`
- `NDIS!NdisFreeRWLock` at `0x1400017cd`
- `NDIS!NdisInitializeEvent` at `0x1400011df`
- `NDIS!NdisInitializeEvent` at `0x1400011f6`
- `NDIS!NdisInitializeEvent` at `0x1400011df`
- `NDIS!NdisInitializeEvent` at `0x1400011f6`
- `NDIS!NdisResetEvent` at `0x14000120a`
- `NDIS!NdisResetEvent` at `0x14000120a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140001268`
- `NDIS!NdisAllocateNetBufferListPool` at `0x140001268`
- `NDIS!NdisAllocateRWLock` at `0x14000121e`
- `NDIS!NdisAllocateRWLock` at `0x14000121e`
- `NDIS!NdisFSetAttributes` at `0x1400013fd`
- `NDIS!NdisFSetAttributes` at `0x1400013fd`
- `NDIS!NdisReleaseRWLock` at `0x140001495`
- `NDIS!NdisReleaseRWLock` at `0x140001495`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000142c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000142c`
- `NETIO!NsiGetParameter` at `0x1400012e1`
- `NETIO!NsiGetParameter` at `0x1400012e1`
- `NETIO!GetUnicastIpAddressTable` at `0x1400012fb`
- `NETIO!GetUnicastIpAddressTable` at `0x1400012fb`
- `NETIO!FreeMibTable` at `0x14000177c`
- `NETIO!FreeMibTable` at `0x14000177c`

## pseudocode

```c
__int64 __fastcall PcFilterAttach(NDIS_HANDLE NdisFilterHandle, __int64 a2, __int64 a3)
{
  unsigned int v3; // esi
  unsigned int v6; // ebx
  _QWORD *v7; // rbx
  _QWORD *v8; // rbx
  int Parameter; // eax
  __int64 v10; // r8
  UINT v11; // r14d
  int v12; // r12d
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v20; // rcx
  ULONG v21; // r8d
  PMIB_UNICASTIPADDRESS_TABLE v22; // r9
  _DWORD *i; // rdx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  _WORD *v26; // rax
  void *v27; // rcx
  void *v28; // rcx
  struct _NDIS_RW_LOCK_EX *v29; // rcx
  int v30; // [rsp+38h] [rbp-61h]
  __int64 v31; // [rsp+40h] [rbp-59h]
  PVOID VirtualAddress; // [rsp+60h] [rbp-39h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+68h] [rbp-31h] BYREF
  PVOID v34; // [rsp+70h] [rbp-29h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+78h] [rbp-21h] BYREF
  _NDIS_FILTER_ATTRIBUTES FilterAttributes; // [rsp+80h] [rbp-19h] BYREF
  __int64 v37; // [rsp+88h] [rbp-11h] BYREF
  UNICODE_STRING v38; // [rsp+90h] [rbp-9h] BYREF
  _BYTE Parameters[20]; // [rsp+A0h] [rbp+7h] BYREF

  v3 = 0;
  FilterAttributes = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v37 = 0;
  VirtualAddress = 0;
  Table = 0;
  memset(Parameters, 0, sizeof(Parameters));
  v34 = 0;
  v38 = 0;
  v6 = NdisAllocateMemoryWithTag(&VirtualAddress, 0x120u, 0x63666350u);
  if ( v6 )
    goto LABEL_20;
  memset(VirtualAddress, 0, 0x120u);
  *((_QWORD *)VirtualAddress + 5) = NdisFilterHandle;
  *((_DWORD *)VirtualAddress + 25) = 1;
  *((_DWORD *)VirtualAddress + 4) = *(_DWORD *)(a3 + 72);
  *((_DWORD *)VirtualAddress + 5) = *(_DWORD *)(a3 + 76);
  *((_DWORD *)VirtualAddress + 24) = *(_DWORD *)(a3 + 24);
  *((_BYTE *)VirtualAddress + 28) = 1;
  InitializeSListHead((PSLIST_HEADER)VirtualAddress + 4);
  KeInitializeSpinLock((PKSPIN_LOCK)VirtualAddress + 10);
  NdisInitializeEvent((PNDIS_EVENT)((char *)VirtualAddress + 104));
  NdisInitializeEvent((PNDIS_EVENT)((char *)VirtualAddress + 136));
  NdisResetEvent((PNDIS_EVENT)((char *)VirtualAddress + 104));
  v7 = VirtualAddress;
  v7[4] = NdisAllocateRWLock(*((NDIS_HANDLE *)VirtualAddress + 5));
  if ( !*((_QWORD *)VirtualAddress + 4) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0 )
    {
      goto LABEL_41;
    }
    v25 = 14;
    goto LABEL_40;
  }
  v8 = VirtualAddress;
  *(_WORD *)&Parameters[6] = WPP_MAIN_CB.SecurityDescriptor;
  Parameters[13] = 0;
  *(_WORD *)&Parameters[14] = 0;
  *(_DWORD *)&Parameters[16] = 0;
  *(_DWORD *)Parameters = 1311104;
  *(_WORD *)&Parameters[4] = 0;
  strcpy(&Parameters[8], "Pcsb");
  v8[6] = NdisAllocateNetBufferListPool(NdisFilterHandle, (PNET_BUFFER_LIST_POOL_PARAMETERS)Parameters);
  if ( !*((_QWORD *)VirtualAddress + 6) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) == 0 )
    {
      goto LABEL_41;
    }
    v25 = 15;
LABEL_40:
    WPP_SF_(v24->AttachedDevice, v25, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids);
LABEL_41:
    v6 = -1073741670;
    goto LABEL_20;
  }
  PcpReadSettings(NdisFilterHandle, (__int64)VirtualAddress + 168);
  PcpInitializeDSCPToUPMappings((char *)VirtualAddress + 214);
  Parameter = NsiGetParameter(1, &NPI_MS_NDIS_MODULEID, 2, (char *)VirtualAddress + 96, 4, 2, &v37, 8, 0);
  if ( Parameter < 0 )
    goto LABEL_28;
  Parameter = GetUnicastIpAddressTable(2u, &Table);
  if ( Parameter < 0 )
    goto LABEL_28;
  v10 = 0;
  v11 = 0;
  v12 = -1;
  if ( !Table->NumEntries )
    goto LABEL_7;
  do
  {
    if ( Table->Table[v10].InterfaceLuid.Value == v37 )
      ++v3;
    v10 = (unsigned int)(v10 + 1);
  }
  while ( (unsigned int)v10 < Table->NumEntries );
  if ( !v3 )
    goto LABEL_7;
  v20 = 20LL * v3;
  if ( v20 > 0xFFFFFFFF || (v11 = v20 + 6, (int)v20 + 6 < (unsigned int)v20) )
  {
    Parameter = -1073741675;
LABEL_28:
    v6 = Parameter;
    goto LABEL_20;
  }
  v6 = NdisAllocateMemoryWithTag(&v34, v11, 0x616E6350u);
  if ( v6 )
    goto LABEL_20;
  memset(v34, 0, v11);
  *(_DWORD *)v34 = v3;
  v21 = 0;
  *((_WORD *)v34 + 2) = 2;
  v22 = Table;
  for ( i = (char *)v34 + 6; v21 < v22->NumEntries; ++v21 )
  {
    if ( v22->Table[v21].InterfaceLuid.Value == v37 )
    {
      *i = 131088;
      i[2] = Table->Table[v21].Address.Ipv4.sin_addr.S_un.S_addr;
      i += 5;
      v22 = Table;
    }
  }
LABEL_7:
  v13 = *(_QWORD *)(a3 + 40);
  if ( *(_WORD *)v13 >= 0x10u
    && (v26 = *(_WORD **)(v13 + 8), *v26 == 92)
    && v26[1] == 68
    && v26[2] == 69
    && v26[3] == 86
    && v26[4] == 73
    && v26[5] == 67
    && v26[6] == 69
    && v26[7] == 92 )
  {
    v38.Buffer = v26 + 8;
    v38.Length = *(_WORD *)v13 - 16;
    v38.MaximumLength = *(_WORD *)(v13 + 2) - 16;
  }
  else
  {
    v38 = *(UNICODE_STRING *)v13;
  }
  v14 = *(_QWORD *)(a3 + 56);
  v15 = -1;
  if ( v14 != -1 )
    v14 = *(_QWORD *)(a3 + 56) >> 3;
  Parameter = PcpLineCreate(
                (_QWORD *)VirtualAddress + 20,
                (__int64)VirtualAddress,
                1,
                *(_WORD *)(*(_QWORD *)(a3 + 32) + 2LL),
                v38.MaximumLength,
                v37,
                v14,
                0,
                0);
  if ( Parameter < 0 )
    goto LABEL_28;
  if ( v34 )
  {
    v12 = v11;
    v15 = (__int64)v34;
  }
  PcpLineUpdate(
    *((_QWORD *)VirtualAddress + 20),
    *(const UNICODE_STRING **)(a3 + 32),
    &v38,
    0,
    0,
    0,
    0,
    v30,
    v31,
    v15,
    v12);
  v34 = 0;
  FilterAttributes = (_NDIS_FILTER_ATTRIBUTES)524685LL;
  v6 = NdisFSetAttributes(NdisFilterHandle, VirtualAddress, &FilterAttributes);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_263d9268693f357b83e9029a6246d0a9_Traceguids, v6);
    }
  }
  else
  {
    *((_DWORD *)VirtualAddress + 6) = 1;
    NdisAcquireRWLockWrite(PcgFilterDriverContext, &LockState, 0);
    v16 = VirtualAddress;
    if ( dword_140018838 || *(_DWORD *)(a3 + 72) == 3 || *((_BYTE *)VirtualAddress + 211) == 1 )
    {
      *((_BYTE *)VirtualAddress + 28) = 0;
      v16 = VirtualAddress;
    }
    v17 = (_QWORD *)qword_140018830;
    if ( *(__int64 **)qword_140018830 != &qword_140018828 )
      __fastfail(3u);
    v16[1] = qword_140018830;
    *v16 = &qword_140018828;
    *v17 = v16;
    qword_140018830 = (__int64)v16;
    NdisReleaseRWLock(PcgFilterDriverContext, &LockState);
    v18 = *((_QWORD *)VirtualAddress + 20);
    PcpTraceLineUpDownEvent(
      v18 + 296,
      *((_DWORD *)VirtualAddress + 4),
      *(_QWORD *)(v18 + 272),
      *(unsigned __int16 *)(v18 + 264),
      *(_QWORD *)(v18 + 288),
      *(unsigned __int16 *)(v18 + 280),
      0);
    PcpLineStart(*((_QWORD *)VirtualAddress + 20));
  }
LABEL_20:
  if ( Table )
    FreeMibTable(Table);
  if ( v6 )
  {
    if ( VirtualAddress )
    {
      v27 = (void *)*((_QWORD *)VirtualAddress + 6);
      if ( v27 )
        NdisFreeNetBufferListPool(v27);
      v28 = (void *)*((_QWORD *)VirtualAddress + 20);
      if ( v28 )
        PcpLineDestroy(v28);
      v29 = (struct _NDIS_RW_LOCK_EX *)*((_QWORD *)VirtualAddress + 4);
      if ( v29 )
        NdisFreeRWLock(v29);
      NdisFreeMemoryWithTag(VirtualAddress, 0x63666350u);
    }
    if ( v34 )
      NdisFreeMemoryWithTag(v34, 0x616E6350u);
  }
  return v6;
}

```

## disassembly

```asm
0x1400010e0  mov     [rsp-8+arg_8], rbx
0x1400010e5  push    rbp
0x1400010e6  push    rsi
0x1400010e7  push    rdi
0x1400010e8  push    r12
0x1400010ea  push    r13
0x1400010ec  push    r14
0x1400010ee  push    r15
0x1400010f0  lea     rbp, [rsp-27h]
0x1400010f5  sub     rsp, 0C0h
0x1400010fc  mov     rax, cs:__security_cookie
0x140001103  xor     rax, rsp
0x140001106  mov     [rbp+57h+var_38], rax
0x14000110a  xor     esi, esi
0x14000110c  xor     eax, eax
0x14000110e  xorps   xmm0, xmm0
0x140001111  mov     [rbp+57h+var_40], eax
0x140001114  mov     r15, r8
0x140001117  mov     qword ptr [rbp+57h+FilterAttributes.Header.Type], rsi
0x14000111b  mov     r13, rcx
0x14000111e  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x140001122  mov     edi, 120h
0x140001127  mov     [rbp+57h+LockState.Flags], al
0x14000112a  mov     edx, edi; Length
0x14000112c  mov     [rbp+57h+var_68], rsi
0x140001130  mov     r8d, 63666350h; Tag
0x140001136  mov     [rbp+57h+VirtualAddress], rsi
0x14000113a  lea     rcx, [rbp+57h+VirtualAddress]; VirtualAddress
0x14000113e  mov     [rbp+57h+Table], rsi
0x140001142  movups  xmmword ptr [rbp+57h+Parameters.Header.Type], xmm0
0x140001146  mov     [rbp+57h+var_80], rsi
0x14000114a  movups  [rbp+57h+var_60], xmm0
0x14000114e  call    cs:__imp_NdisAllocateMemoryWithTag
0x140001155  nop     dword ptr [rax+rax+00h]
0x14000115a  mov     ebx, eax
0x14000115c  test    eax, eax
0x14000115e  jnz     loc_1400014F6
0x140001164  mov     rcx, [rbp+57h+VirtualAddress]; void *
0x140001168  mov     r8d, edi; Size
0x14000116b  xor     edx, edx; Val
0x14000116d  call    memset
0x140001172  mov     rax, [rbp+57h+VirtualAddress]
0x140001176  lea     r14d, [rsi+1]
0x14000117a  mov     [rax+28h], r13
0x14000117e  mov     rax, [rbp+57h+VirtualAddress]
0x140001182  mov     [rax+64h], r14d
0x140001186  mov     ecx, [r15+48h]
0x14000118a  mov     rax, [rbp+57h+VirtualAddress]
0x14000118e  mov     [rax+10h], ecx
0x140001191  mov     ecx, [r15+4Ch]
0x140001195  mov     rax, [rbp+57h+VirtualAddress]
0x140001199  mov     [rax+14h], ecx
0x14000119c  mov     rax, [rbp+57h+VirtualAddress]
0x1400011a0  mov     ecx, [r15+18h]
0x1400011a4  mov     [rax+60h], ecx
0x1400011a7  mov     rax, [rbp+57h+VirtualAddress]
0x1400011ab  mov     [rax+1Ch], r14b
0x1400011af  mov     rcx, [rbp+57h+VirtualAddress]
0x1400011b3  add     rcx, 40h ; '@'; SListHead
0x1400011b7  call    cs:__imp_InitializeSListHead
0x1400011be  nop     dword ptr [rax+rax+00h]
0x1400011c3  mov     rcx, [rbp+57h+VirtualAddress]
0x1400011c7  add     rcx, 50h ; 'P'; SpinLock
0x1400011cb  call    cs:__imp_KeInitializeSpinLock
0x1400011d2  nop     dword ptr [rax+rax+00h]
0x1400011d7  mov     rcx, [rbp+57h+VirtualAddress]
0x1400011db  add     rcx, 68h ; 'h'; Event
0x1400011df  call    cs:__imp_NdisInitializeEvent
0x1400011e6  nop     dword ptr [rax+rax+00h]
0x1400011eb  mov     rcx, [rbp+57h+VirtualAddress]
0x1400011ef  add     rcx, 88h; Event
0x1400011f6  call    cs:__imp_NdisInitializeEvent
0x1400011fd  nop     dword ptr [rax+rax+00h]
0x140001202  mov     rcx, [rbp+57h+VirtualAddress]
0x140001206  add     rcx, 68h ; 'h'; Event
0x14000120a  call    cs:__imp_NdisResetEvent
0x140001211  nop     dword ptr [rax+rax+00h]
0x140001216  mov     rbx, [rbp+57h+VirtualAddress]
0x14000121a  mov     rcx, [rbx+28h]; NdisHandle
0x14000121e  call    cs:__imp_NdisAllocateRWLock
0x140001225  nop     dword ptr [rax+rax+00h]
0x14000122a  mov     [rbx+20h], rax
0x14000122e  mov     rax, [rbp+57h+VirtualAddress]
0x140001232  cmp     [rax+20h], rsi
0x140001236  jz      loc_140001606
0x14000123c  movzx   eax, word ptr cs:WPP_MAIN_CB.SecurityDescriptor
0x140001243  lea     rdx, [rbp+57h+Parameters]; Parameters
0x140001247  mov     rbx, [rbp+57h+VirtualAddress]
0x14000124b  mov     rcx, r13; NdisHandle
0x14000124e  mov     [rbp+57h+Parameters.ContextSize], ax
0x140001252  mov     qword ptr [rbp+57h+Parameters.DataSize], rsi
0x140001256  mov     dword ptr [rbp+57h+Parameters.Header.Type], 140180h
0x14000125d  mov     word ptr [rbp+57h+Parameters.ProtocolId], si
0x140001261  mov     [rbp+57h+Parameters.PoolTag], 62736350h
0x140001268  call    cs:__imp_NdisAllocateNetBufferListPool
0x14000126f  nop     dword ptr [rax+rax+00h]
0x140001274  mov     [rbx+30h], rax
0x140001278  mov     rax, [rbp+57h+VirtualAddress]
0x14000127c  cmp     [rax+30h], rsi
0x140001280  jz      loc_140001651
0x140001286  mov     rdx, rax
0x140001289  mov     rcx, r13
0x14000128c  add     rdx, 0A8h
0x140001293  call    PcpReadSettings
0x140001298  mov     rcx, [rbp+57h+VirtualAddress]
0x14000129c  add     rcx, 0D6h
0x1400012a3  call    PcpInitializeDSCPToUPMappings
0x1400012a8  mov     r9, [rbp+57h+VirtualAddress]
0x1400012ac  lea     rax, [rbp+57h+var_68]
0x1400012b0  mov     dword ptr [rsp+0F0h+var_B0], esi
0x1400012b4  lea     edi, [rsi+2]
0x1400012b7  mov     [rsp+0F0h+var_B8], 8
0x1400012bf  lea     rdx, NPI_MS_NDIS_MODULEID
0x1400012c6  mov     [rsp+0F0h+var_C0], rax
0x1400012cb  add     r9, 60h ; '`'
0x1400012cf  mov     dword ptr [rsp+0F0h+var_C8], edi
0x1400012d3  mov     r8d, edi
0x1400012d6  mov     ecx, r14d
0x1400012d9  mov     dword ptr [rsp+0F0h+var_D0], 4
0x1400012e1  call    cs:__imp_NsiGetParameter
0x1400012e8  nop     dword ptr [rax+rax+00h]
0x1400012ed  test    eax, eax
0x1400012ef  js      loc_140001560
0x1400012f5  mov     ecx, edi; Family
0x1400012f7  lea     rdx, [rbp+57h+Table]; Table
0x1400012fb  call    cs:__imp_GetUnicastIpAddressTable
0x140001302  nop     dword ptr [rax+rax+00h]
0x140001307  test    eax, eax
0x140001309  js      loc_140001560
0x14000130f  mov     rax, [rbp+57h+Table]
0x140001313  xor     r8d, r8d
0x140001316  mov     r14d, esi
0x140001319  mov     r12d, 0FFFFFFFFh
0x14000131f  mov     r9d, [rax]
0x140001322  test    r9d, r9d
0x140001325  jnz     loc_14000167A
0x14000132b  mov     rcx, [r15+28h]
0x14000132f  mov     r8d, 10h
0x140001335  cmp     [rcx], r8w
0x140001339  jnb     loc_1400016A6
0x14000133f  movups  xmm0, xmmword ptr [rcx]
0x140001342  movdqu  [rbp+57h+var_60], xmm0
0x140001347  mov     r8, [r15+38h]
0x14000134b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000134f  mov     r10, [rbp+57h+VirtualAddress]
0x140001353  mov     rax, r8
0x140001356  mov     rdx, qword ptr [rbp+57h+var_60]
0x14000135a  mov     r9, [r15+20h]
0x14000135e  shr     rax, 3
0x140001362  mov     dword ptr [rsp+0F0h+var_B0], esi
0x140001366  lea     rcx, [r10+0A0h]
0x14000136d  cmp     r8, rbx
0x140001370  mov     [rsp+0F0h+var_B8], esi
0x140001374  movzx   r9d, word ptr [r9+2]
0x140001379  cmovnz  r8, rax
0x14000137d  mov     rax, [rbp+57h+var_68]
0x140001381  mov     [rsp+0F0h+var_C0], r8
0x140001386  mov     r8b, 1
0x140001389  shr     rdx, 10h
0x14000138d  mov     [rsp+0F0h+var_C8], rax
0x140001392  mov     word ptr [rsp+0F0h+var_D0], dx
0x140001397  mov     rdx, r10
0x14000139a  call    PcpLineCreate
0x14000139f  test    eax, eax
0x1400013a1  js      loc_140001560
0x1400013a7  mov     rax, [rbp+57h+var_80]
0x1400013ab  test    rax, rax
0x1400013ae  jnz     loc_140001724
0x1400013b4  mov     rcx, [rbp+57h+VirtualAddress]
0x1400013b8  lea     r8, [rbp+57h+var_60]
0x1400013bc  mov     rdx, [r15+20h]
0x1400013c0  xor     r9d, r9d
0x1400013c3  mov     [rsp+0F0h+var_A0], r12d
0x1400013c8  mov     [rsp+0F0h+var_A8], rbx
0x1400013cd  mov     rcx, [rcx+0A0h]
0x1400013d4  mov     dword ptr [rsp+0F0h+var_C0], esi
0x1400013d8  mov     dword ptr [rsp+0F0h+var_C8], esi
0x1400013dc  mov     [rsp+0F0h+var_D0], rsi
0x1400013e1  call    PcpLineUpdate
0x1400013e6  mov     [rbp+57h+var_80], rsi
0x1400013ea  mov     qword ptr [rbp+57h+FilterAttributes.Header.Type], 8018Dh
0x1400013f2  mov     rdx, [rbp+57h+VirtualAddress]; FilterModuleContext
0x1400013f6  lea     r8, [rbp+57h+FilterAttributes]; FilterAttributes
0x1400013fa  mov     rcx, r13; NdisFilterHandle
0x1400013fd  call    cs:__imp_NdisFSetAttributes
0x140001404  nop     dword ptr [rax+rax+00h]
0x140001409  mov     ebx, eax
0x14000140b  test    eax, eax
0x14000140d  jnz     loc_14000172F
0x140001413  mov     rax, [rbp+57h+VirtualAddress]
0x140001417  lea     rdx, [rbp+57h+LockState]; LockState
0x14000141b  xor     r8d, r8d; Flags
0x14000141e  mov     dword ptr [rax+18h], 1
0x140001425  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000142c  call    cs:__imp_NdisAcquireRWLockWrite
0x140001433  nop     dword ptr [rax+rax+00h]
0x140001438  cmp     cs:dword_140018838, esi
0x14000143e  lea     ecx, [rbx+3]
0x140001441  mov     rax, [rbp+57h+VirtualAddress]
0x140001445  jnz     loc_140001535
0x14000144b  cmp     [r15+48h], ecx
0x14000144f  jz      loc_140001535
0x140001455  cmp     byte ptr [rax+0D3h], 1
0x14000145c  jz      loc_140001535
0x140001462  mov     rdx, cs:qword_140018830
0x140001469  lea     r8, qword_140018828
0x140001470  cmp     [rdx], r8
0x140001473  jnz     loc_14000177A
0x140001479  mov     [rax+8], rdx
0x14000147d  mov     [rax], r8
0x140001480  mov     [rdx], rax
0x140001483  lea     rdx, [rbp+57h+LockState]; LockState
0x140001487  mov     rcx, cs:PcgFilterDriverContext; Lock
0x14000148e  mov     cs:qword_140018830, rax
0x140001495  call    cs:__imp_NdisReleaseRWLock
0x14000149c  nop     dword ptr [rax+rax+00h]
0x1400014a1  mov     rdx, [rbp+57h+VirtualAddress]
0x1400014a5  mov     dword ptr [rsp+0F0h+var_C0], esi
0x1400014a9  mov     r8, [rdx+0A0h]
0x1400014b0  mov     edx, [rdx+10h]
0x1400014b3  movzx   eax, word ptr [r8+118h]
0x1400014bb  lea     rcx, [r8+128h]
0x1400014c2  movzx   r9d, word ptr [r8+108h]
0x1400014ca  mov     dword ptr [rsp+0F0h+var_C8], eax
0x1400014ce  mov     rax, [r8+120h]
0x1400014d5  mov     r8, [r8+110h]
0x1400014dc  mov     [rsp+0F0h+var_D0], rax
0x1400014e1  call    PcpTraceLineUpDownEvent
0x1400014e6  mov     rcx, [rbp+57h+VirtualAddress]
0x1400014ea  mov     rcx, [rcx+0A0h]
0x1400014f1  call    PcpLineStart
0x1400014f6  mov     rcx, [rbp+57h+Table]; Memory
0x1400014fa  test    rcx, rcx
0x1400014fd  jnz     loc_14000177C
0x140001503  test    ebx, ebx
0x140001505  jnz     loc_14000178D
0x14000150b  mov     eax, ebx
0x14000150d  mov     rcx, [rbp+57h+var_38]
0x140001511  xor     rcx, rsp; StackCookie
0x140001514  call    __security_check_cookie
0x140001519  mov     rbx, [rsp+0F0h+arg_8]
0x140001521  add     rsp, 0C0h
0x140001528  pop     r15
0x14000152a  pop     r14
0x14000152c  pop     r13
0x14000152e  pop     r12
0x140001530  pop     rdi
0x140001531  pop     rsi
0x140001532  pop     rbp
0x140001533  retn
0x140001535  mov     [rax+1Ch], sil
0x140001539  mov     rax, [rbp+57h+VirtualAddress]
0x14000153d  jmp     loc_140001462
0x140001542  test    esi, esi
0x140001544  jz      loc_14000169F
0x14000154a  mov     eax, esi
0x14000154c  lea     rcx, [rax+rax*4]
0x140001550  shl     rcx, 2
0x140001554  cmp     rcx, r12
0x140001557  jbe     short loc_140001569
0x140001559  mov     eax, 0C0000095h
0x14000155e  xor     esi, esi
0x140001560  test    eax, eax
0x140001562  mov     ebx, esi
0x140001564  cmovs   ebx, eax
0x140001567  jmp     short loc_1400014F6
0x140001569  lea     r14d, [rcx+6]
0x14000156d  cmp     r14d, ecx
0x140001570  jb      short loc_140001559
0x140001572  mov     r8d, 616E6350h; Tag
0x140001578  lea     rcx, [rbp+57h+var_80]; VirtualAddress
0x14000157c  mov     edx, r14d; Length
0x14000157f  call    cs:__imp_NdisAllocateMemoryWithTag
0x140001586  nop     dword ptr [rax+rax+00h]
0x14000158b  mov     ebx, eax
0x14000158d  test    eax, eax
0x14000158f  jnz     loc_1400014F6
0x140001595  mov     rcx, [rbp+57h+var_80]; void *
0x140001599  xor     edx, edx; Val
0x14000159b  mov     r8d, r14d; Size
0x14000159e  call    memset
0x1400015a3  mov     rax, [rbp+57h+var_80]
0x1400015a7  mov     [rax], esi
0x1400015a9  xor     esi, esi
0x1400015ab  mov     rax, [rbp+57h+var_80]
0x1400015af  mov     r8d, esi
0x1400015b2  mov     [rax+4], di
0x1400015b6  mov     r9, [rbp+57h+Table]
0x1400015ba  mov     rdx, [rbp+57h+var_80]
0x1400015be  add     rdx, 6
0x1400015c2  cmp     [r9], esi
0x1400015c5  jbe     loc_14000132B
0x1400015cb  mov     eax, r8d
0x1400015ce  lea     rcx, [rax+rax*4]
0x1400015d2  mov     rax, [rbp+57h+var_68]
0x1400015d6  add     rcx, rcx
0x1400015d9  cmp     [r9+rcx*8+28h], rax
0x1400015de  jnz     short loc_1400015F9
0x1400015e0  mov     dword ptr [rdx], 20010h
0x1400015e6  mov     rax, [rbp+57h+Table]
  ... truncated ...
```
