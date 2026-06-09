# DrDevice::OnReadCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140023030`
- end: `0x1400234f8`
- name: `?OnReadCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `1224`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _DWORD *, RefCount **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140022ab0`

## callees

- `0x140001660`
- `0x1400016a0`
- `0x14000324c`
- `0x1400032c0`
- `0x140006560`
- `0x1400065c0`
- `0x1400117e0`
- `0x140023030`
- `0x140023cf0`
- `0x140024020`
- `0x140024180`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14002339c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002339c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140023408`
- `ntoskrnl!ExReleaseFastMutex` at `0x140023408`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140023273`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140023273`

## pseudocode

```c
__int64 __fastcall DrDevice::OnReadCompletion(__int64 a1, unsigned int *a2, unsigned int a3, _DWORD *a4, RefCount **a5)
{
  __int64 v7; // r10
  __int64 v8; // r13
  __int64 v9; // rbp
  unsigned int v10; // r14d
  int v11; // eax
  unsigned int v12; // edi
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  char *v18; // rax
  RefCount **v19; // rdx
  __int64 v20; // rcx
  struct _RX_CONTEXT *v21; // rbp
  __int64 v22; // rdi

  v7 = a1;
  v8 = *((_QWORD *)*a5 + 4);
  v9 = *(_QWORD *)(v8 + 48);
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
LABEL_16:
      v7 = a1;
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( (a2[3] & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      v7 = a1;
    }
    v19 = a5;
    v20 = v7;
    if ( v9 )
    {
      DrDevice::CompleteBusyExchange(v7, a5, a2[3], 0);
      goto LABEL_74;
    }
LABEL_73:
    DrDevice::DiscardBusyExchange(v20, v19);
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      v7 = a1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        79,
        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        a2[4],
        *(_DWORD *)(v8 + 40));
      v7 = a1;
    }
  }
  v10 = a3 - 20;
  v11 = *(_DWORD *)(v8 + 40);
  v12 = a2[4] - v11;
  if ( v10 > v12 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        80,
        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        v10,
        a2[4] - v11);
      goto LABEL_16;
    }
LABEL_17:
    if ( !v9 )
    {
      DrDevice::DiscardBusyExchange(v7, a5);
      goto LABEL_20;
    }
LABEL_18:
    DrDevice::CompleteBusyExchange(v7, a5, 3221225862LL, 0);
LABEL_20:
    *a4 = 0;
    SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
    return 3221225862LL;
  }
  v14 = 0;
  if ( !v9 )
  {
    *(_DWORD *)(v8 + 40) = v10 + v11;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v7 = a1;
  }
  v15 = (_DWORD *)(v9 + 568);
  if ( v12 > *(_DWORD *)(v9 + 568) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      v7 = a1;
    }
    goto LABEL_18;
  }
  v16 = a2[4];
  *(_QWORD *)(v9 + 184) = v16;
  if ( !v16 || !v10 )
  {
LABEL_43:
    if ( v10 != v12 )
    {
      v21 = 0;
      ExAcquireFastMutex(&DrMutex);
      v22 = *((_QWORD *)*a5 + 4);
      *(_DWORD *)(v22 + 24) = 0;
      if ( *(_DWORD *)(v22 + 28) && *(_QWORD *)(v22 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
        v21 = *(struct _RX_CONTEXT **)(v22 + 48);
        *(_QWORD *)(v22 + 48) = 0;
        v21->MRxContext[2] = 0;
      }
      if ( *(_DWORD *)(v22 + 32) )
        *((_QWORD *)*a5 + 4) = 0;
      ExReleaseFastMutex(&DrMutex);
      if ( v21 )
      {
        DrDevice::CompleteRxContext(v21, -1073741536, 0);
        if ( *(_DWORD *)(v22 + 32) )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 16LL))(v22, 1);
      }
      DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
      *a4 = 0;
      if ( *a5 )
        RefCount::Release(*a5);
      return 0;
    }
    if ( a2[3] )
    {
      v14 = a2[3];
    }
    else if ( !a2[4] && v9 && *v15 )
    {
      v14 = -1073741807;
      a2[3] = -1073741807;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v14, a2[4]);
      v7 = a1;
    }
    v19 = a5;
    v20 = v7;
    if ( v9 )
    {
      DrDevice::CompleteBusyExchange(v7, a5, a2[3], a2[4]);
LABEL_74:
      *a4 = 1;
      SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
      return 0;
    }
    goto LABEL_73;
  }
  v17 = *(_QWORD *)(v9 + 544);
  if ( (*(_BYTE *)(v17 + 10) & 5) != 0 )
  {
    v18 = *(char **)(v17 + 24);
  }
  else
  {
    v18 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v17, 0, MmCached, 0, 0, 0x40000010u);
    v7 = a1;
  }
  if ( v18 )
  {
    memmove(&v18[*(unsigned int *)(v8 + 40)], a2 + 5, v10);
    *(_DWORD *)(v8 + 40) += v10;
    v7 = a1;
LABEL_42:
    v15 = (_DWORD *)(v9 + 568);
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v7 = a1;
  }
  DrDevice::CompleteBusyExchange(v7, a5, 3221225626LL, 0);
  *a4 = 0;
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return 3221225626LL;
}

```

## disassembly

```asm
0x140023030  mov     [rsp+arg_8], rbx
0x140023035  mov     [rsp+arg_18], r9
0x14002303a  mov     [rsp+arg_0], rcx
0x14002303f  push    rbp
0x140023040  push    rsi
0x140023041  push    rdi
0x140023042  push    r12
0x140023044  push    r13
0x140023046  push    r14
0x140023048  push    r15
0x14002304a  sub     rsp, 30h
0x14002304e  mov     r12, [rsp+68h+arg_20]
0x140023056  mov     r14d, r8d
0x140023059  mov     r15, rdx
0x14002305c  mov     r10, rcx
0x14002305f  mov     rax, [r12]
0x140023063  mov     r13, [rax+20h]
0x140023067  mov     rbp, [r13+30h]
0x14002306b  cmp     r8d, 14h
0x14002306f  jnb     short loc_1400230AC
0x140023071  mov     rcx, cs:WPP_GLOBAL_Control
0x140023078  lea     rbx, WPP_GLOBAL_Control
0x14002307f  cmp     rcx, rbx
0x140023082  jz      loc_140023167
0x140023088  cmp     byte ptr [rcx+29h], 2
0x14002308c  jb      loc_140023167
0x140023092  mov     rcx, [rcx+18h]
0x140023096  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002309d  mov     edx, 4Dh ; 'M'
0x1400230a2  call    WPP_SF_
0x1400230a7  jmp     loc_140023162
0x1400230ac  cmp     dword ptr [rdx+0Ch], 0
0x1400230b0  jl      loc_140023479
0x1400230b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230bd  lea     rbx, WPP_GLOBAL_Control
0x1400230c4  cmp     rcx, rbx
0x1400230c7  jz      short loc_140023121
0x1400230c9  cmp     byte ptr [rcx+29h], 5
0x1400230cd  jb      short loc_1400230E9
0x1400230cf  mov     rcx, [rcx+18h]
0x1400230d3  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400230da  mov     edx, 4Eh ; 'N'
0x1400230df  call    WPP_SF_
0x1400230e4  mov     r10, [rsp+68h+arg_0]
0x1400230e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230f0  cmp     rcx, rbx
0x1400230f3  jz      short loc_140023121
0x1400230f5  cmp     byte ptr [rcx+29h], 5
0x1400230f9  jb      short loc_140023121
0x1400230fb  mov     eax, [r13+28h]
0x1400230ff  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140023106  mov     r9d, [r15+10h]
0x14002310a  mov     edx, 4Fh ; 'O'
0x14002310f  mov     rcx, [rcx+18h]
0x140023113  mov     [rsp+68h+BugCheckOnFailure], eax
0x140023117  call    WPP_SF_dd
0x14002311c  mov     r10, [rsp+68h+arg_0]
0x140023121  mov     edi, [r15+10h]
0x140023125  add     r14d, 0FFFFFFECh
0x140023129  mov     eax, [r13+28h]
0x14002312d  sub     edi, eax
0x14002312f  cmp     r14d, edi
0x140023132  jbe     short loc_1400231A5
0x140023134  mov     rcx, cs:WPP_GLOBAL_Control
0x14002313b  cmp     rcx, rbx
0x14002313e  jz      short loc_140023167
0x140023140  cmp     byte ptr [rcx+29h], 2
0x140023144  jb      short loc_140023167
0x140023146  mov     rcx, [rcx+18h]
0x14002314a  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140023151  mov     edx, 50h ; 'P'
0x140023156  mov     [rsp+68h+BugCheckOnFailure], edi
0x14002315a  mov     r9d, r14d
0x14002315d  call    WPP_SF_dd
0x140023162  mov     r10, [rsp+68h+arg_0]
0x140023167  mov     rdx, r12
0x14002316a  mov     rcx, r10
0x14002316d  test    rbp, rbp
0x140023170  jz      short loc_140023182
0x140023172  xor     r9d, r9d
0x140023175  mov     r8d, 0C0000186h
0x14002317b  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140023180  jmp     short loc_140023187
0x140023182  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140023187  xor     esi, esi
0x140023189  mov     rcx, [rsp+68h+arg_18]
0x140023191  mov     [rcx], esi
0x140023193  mov     rcx, r12
0x140023196  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14002319b  mov     eax, 0C0000186h
0x1400231a0  jmp     loc_1400234E2
0x1400231a5  xor     esi, esi
0x1400231a7  test    rbp, rbp
0x1400231aa  jz      loc_140023303
0x1400231b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400231b7  cmp     rcx, rbx
0x1400231ba  jz      short loc_1400231DC
0x1400231bc  cmp     byte ptr [rcx+29h], 5
0x1400231c0  jb      short loc_1400231DC
0x1400231c2  mov     rcx, [rcx+18h]
0x1400231c6  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400231cd  mov     edx, 51h ; 'Q'
0x1400231d2  call    WPP_SF_
0x1400231d7  mov     r10, [rsp+68h+arg_0]
0x1400231dc  lea     rcx, [rbp+238h]
0x1400231e3  cmp     edi, [rcx]
0x1400231e5  jbe     short loc_14002322C
0x1400231e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400231ee  cmp     rcx, rbx
0x1400231f1  jz      short loc_140023213
0x1400231f3  cmp     byte ptr [rcx+29h], 2
0x1400231f7  jb      short loc_140023213
0x1400231f9  mov     rcx, [rcx+18h]
0x1400231fd  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140023204  mov     edx, 52h ; 'R'
0x140023209  call    WPP_SF_
0x14002320e  mov     r10, [rsp+68h+arg_0]
0x140023213  xor     r9d, r9d
0x140023216  mov     r8d, 0C0000186h
0x14002321c  mov     rdx, r12
0x14002321f  mov     rcx, r10
0x140023222  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140023227  jmp     loc_140023189
0x14002322c  mov     eax, [r15+10h]
0x140023230  mov     [rbp+0B8h], rax
0x140023237  test    rax, rax
0x14002323a  jz      loc_140023311
0x140023240  test    r14d, r14d
0x140023243  jz      loc_140023311
0x140023249  mov     rcx, [rbp+220h]; MemoryDescriptorList
0x140023250  test    byte ptr [rcx+0Ah], 5
0x140023254  jz      short loc_14002325C
0x140023256  mov     rax, [rcx+18h]
0x14002325a  jmp     short loc_140023284
0x14002325c  mov     [rsp+68h+Priority], 40000010h; Priority
0x140023264  xor     r9d, r9d; RequestedAddress
0x140023267  xor     edx, edx; AccessMode
0x140023269  mov     [rsp+68h+BugCheckOnFailure], esi; BugCheckOnFailure
0x14002326d  mov     r8d, 1; CacheType
0x140023273  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002327a  nop     dword ptr [rax+rax+00h]
0x14002327f  mov     r10, [rsp+68h+arg_0]
0x140023284  test    rax, rax
0x140023287  jz      short loc_1400232A7
0x140023289  mov     ecx, [r13+28h]
0x14002328d  lea     rdx, [r15+14h]; Src
0x140023291  add     rcx, rax; void *
0x140023294  mov     r8d, r14d; Size
0x140023297  call    memmove
0x14002329c  add     [r13+28h], r14d
0x1400232a0  mov     r10, [rsp+68h+arg_0]
0x1400232a5  jmp     short loc_14002330A
0x1400232a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232ae  cmp     rcx, rbx
0x1400232b1  jz      short loc_1400232D3
0x1400232b3  cmp     byte ptr [rcx+29h], 2
0x1400232b7  jb      short loc_1400232D3
0x1400232b9  mov     rcx, [rcx+18h]
0x1400232bd  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400232c4  mov     edx, 53h ; 'S'
0x1400232c9  call    WPP_SF_
0x1400232ce  mov     r10, [rsp+68h+arg_0]
0x1400232d3  xor     r9d, r9d
0x1400232d6  mov     r8d, 0C000009Ah
0x1400232dc  mov     rdx, r12
0x1400232df  mov     rcx, r10
0x1400232e2  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400232e7  mov     rcx, [rsp+68h+arg_18]
0x1400232ef  mov     [rcx], esi
0x1400232f1  mov     rcx, r12
0x1400232f4  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400232f9  mov     eax, 0C000009Ah
0x1400232fe  jmp     loc_1400234E2
0x140023303  add     eax, r14d
0x140023306  mov     [r13+28h], eax
0x14002330a  lea     rcx, [rbp+238h]
0x140023311  cmp     r14d, edi
0x140023314  jnz     short loc_140023392
0x140023316  mov     eax, [r15+0Ch]
0x14002331a  test    eax, eax
0x14002331c  jnz     short loc_140023338
0x14002331e  cmp     [r15+10h], esi
0x140023322  jnz     short loc_14002333A
0x140023324  test    rbp, rbp
0x140023327  jz      short loc_14002333A
0x140023329  cmp     [rcx], esi
0x14002332b  jbe     short loc_14002333A
0x14002332d  mov     esi, 0C0000011h
0x140023332  mov     [r15+0Ch], esi
0x140023336  jmp     short loc_14002333A
0x140023338  mov     esi, eax
0x14002333a  mov     rcx, cs:WPP_GLOBAL_Control
0x140023341  cmp     rcx, rbx
0x140023344  jz      short loc_140023371
0x140023346  cmp     byte ptr [rcx+29h], 5
0x14002334a  jb      short loc_140023371
0x14002334c  mov     eax, [r15+10h]
0x140023350  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140023357  mov     rcx, [rcx+18h]
0x14002335b  mov     edx, 54h ; 'T'
0x140023360  mov     r9d, esi
0x140023363  mov     [rsp+68h+BugCheckOnFailure], eax
0x140023367  call    WPP_SF_dd
0x14002336c  mov     r10, [rsp+68h+arg_0]
0x140023371  mov     rdx, r12
0x140023374  mov     rcx, r10
0x140023377  test    rbp, rbp
0x14002337a  jz      loc_1400234C5
0x140023380  mov     r9d, [r15+10h]
0x140023384  mov     r8d, [r15+0Ch]
0x140023388  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x14002338d  jmp     loc_1400234CA
0x140023392  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140023399  mov     rbp, rsi
0x14002339c  call    cs:__imp_ExAcquireFastMutex
0x1400233a3  nop     dword ptr [rax+rax+00h]
0x1400233a8  mov     rax, [r12]
0x1400233ac  mov     rdi, [rax+20h]
0x1400233b0  mov     [rdi+18h], esi
0x1400233b3  cmp     [rdi+1Ch], esi
0x1400233b6  jz      short loc_1400233F4
0x1400233b8  cmp     [rdi+30h], rsi
0x1400233bc  jz      short loc_1400233F4
0x1400233be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233c5  cmp     rcx, rbx
0x1400233c8  jz      short loc_1400233E5
0x1400233ca  cmp     byte ptr [rcx+29h], 5
0x1400233ce  jb      short loc_1400233E5
0x1400233d0  mov     rcx, [rcx+18h]
0x1400233d4  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400233db  mov     edx, 41h ; 'A'
0x1400233e0  call    WPP_SF_
0x1400233e5  mov     rbp, [rdi+30h]
0x1400233e9  mov     [rdi+30h], rsi
0x1400233ed  mov     [rbp+0D0h], rsi
0x1400233f4  cmp     [rdi+20h], esi
0x1400233f7  jz      short loc_140023401
0x1400233f9  mov     rax, [r12]
0x1400233fd  mov     [rax+20h], rsi
0x140023401  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140023408  call    cs:__imp_ExReleaseFastMutex
0x14002340f  nop     dword ptr [rax+rax+00h]
0x140023414  test    rbp, rbp
0x140023417  jz      short loc_140023442
0x140023419  xor     r8d, r8d; unsigned int
0x14002341c  mov     edx, 0C0000120h; int
0x140023421  mov     rcx, rbp; RxContext
0x140023424  call    ?CompleteRxContext@DrDevice@@KAXPEAU_RX_CONTEXT@@JK@Z; DrDevice::CompleteRxContext(_RX_CONTEXT *,long,ulong)
0x140023429  cmp     [rdi+20h], esi
0x14002342c  jz      short loc_140023442
0x14002342e  mov     rax, [rdi]
0x140023431  mov     edx, 1
0x140023436  mov     rcx, rdi
0x140023439  mov     rax, [rax+10h]
0x14002343d  call    _guard_dispatch_icall
0x140023442  mov     rcx, [rsp+68h+arg_0]
0x140023447  xor     r8d, r8d; unsigned int
0x14002344a  mov     edx, 14h; unsigned int
0x14002344f  mov     rcx, [rcx+20h]
0x140023453  mov     rcx, [rcx+2E0h]; this
0x14002345a  call    ?ReadMore@DrSession@@QEAAHKK@Z; DrSession::ReadMore(ulong,ulong)
0x14002345f  mov     rcx, [rsp+68h+arg_18]
0x140023467  mov     [rcx], esi
0x140023469  mov     rcx, [r12]; this
0x14002346d  test    rcx, rcx
0x140023470  jz      short loc_1400234E0
0x140023472  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140023477  jmp     short loc_1400234E0
0x140023479  mov     rcx, cs:WPP_GLOBAL_Control
0x140023480  lea     rbx, WPP_GLOBAL_Control
0x140023487  cmp     rcx, rbx
0x14002348a  jz      short loc_1400234AC
0x14002348c  cmp     byte ptr [rcx+29h], 5
0x140023490  jb      short loc_1400234AC
0x140023492  mov     rcx, [rcx+18h]
0x140023496  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002349d  mov     edx, 55h ; 'U'
0x1400234a2  call    WPP_SF_
0x1400234a7  mov     r10, [rsp+68h+arg_0]
0x1400234ac  mov     rdx, r12
0x1400234af  mov     rcx, r10
0x1400234b2  test    rbp, rbp
0x1400234b5  jz      short loc_1400234C5
0x1400234b7  mov     r8d, [r15+0Ch]
0x1400234bb  xor     r9d, r9d
0x1400234be  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400234c3  jmp     short loc_1400234CA
0x1400234c5  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x1400234ca  mov     rcx, [rsp+68h+arg_18]
0x1400234d2  mov     dword ptr [rcx], 1
0x1400234d8  mov     rcx, r12
0x1400234db  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400234e0  xor     eax, eax
0x1400234e2  mov     rbx, [rsp+68h+arg_8]
0x1400234e7  add     rsp, 30h
0x1400234eb  pop     r15
0x1400234ed  pop     r14
0x1400234ef  pop     r13
0x1400234f1  pop     r12
0x1400234f3  pop     rdi
  ... truncated ...
```
