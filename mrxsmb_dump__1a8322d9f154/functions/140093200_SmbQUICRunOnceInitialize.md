# SmbQUICRunOnceInitialize

- ea: `0x140093200`
- end: `0x1400935b4`
- name: `SmbQUICRunOnceInitialize`
- size: `948`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14003838c`
- `0x140039fa8`
- `0x140059ea0`
- `0x140093200`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140093255`
- `ntoskrnl!KeInitializeEvent` at `0x140093255`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400932f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400932f3`
- `ntoskrnl!ExAllocatePool2` at `0x14009322c`
- `ntoskrnl!ExAllocatePool2` at `0x14009322c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400934a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140093374`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400934a1`
- `NETIO!NmrRegisterClient` at `0x1400932bc`
- `NETIO!NmrRegisterClient` at `0x1400932bc`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140093359`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140093486`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140093359`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140093486`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009332f`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009345c`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009332f`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009345c`
- `NETIO!NmrDeregisterClient` at `0x140093343`
- `NETIO!NmrDeregisterClient` at `0x140093470`
- `NETIO!NmrDeregisterClient` at `0x140093343`
- `NETIO!NmrDeregisterClient` at `0x140093470`

## pseudocode

```c
__int64 __fastcall SmbQUICRunOnceInitialize(PRTL_RUN_ONCE a1, PVOID a2, PVOID *a3)
{
  __int64 Pool2; // rax
  __int64 v4; // rbx
  NTSTATUS v5; // edi
  HANDLE *v6; // rsi
  int v8; // eax
  __int64 v9; // r8
  PVOID v10; // rdi
  HANDLE *v11; // rbx
  signed __int8 v12; // al
  int v13; // eax
  __int64 Timer_high; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  _QWORD v17[7]; // [rsp+30h] [rbp-38h] BYREF
  LARGE_INTEGER Timeout; // [rsp+88h] [rbp+20h] BYREF

  v17[1] = 0;
  v17[0] = "SMB Client";
  Pool2 = ExAllocatePool2(64, 152, 1666077005);
  v4 = Pool2;
  if ( !Pool2 )
  {
    v5 = -1073741670;
LABEL_13:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        87,
        WPP_fda175b9f5083825c260891a41b6395b_Traceguids,
        (unsigned int)v5);
    }
    return 0;
  }
  KeInitializeEvent((PRKEVENT)(Pool2 + 112), SynchronizationEvent, 0);
  *(_DWORD *)(v4 + 92) = 1;
  *(_WORD *)(v4 + 88) = 24;
  *(_QWORD *)(v4 + 8) = _MsQuicClientAttachProvider;
  v6 = (HANDLE *)(v4 + 80);
  *(_WORD *)(v4 + 2) = 72;
  *(GUID *)(v4 + 96) = REMOTEFS_SMB;
  *(_QWORD *)(v4 + 16) = _MsQuicClientDetachProvider;
  *(_QWORD *)(v4 + 48) = v4 + 88;
  *(_QWORD *)(v4 + 40) = MSQUIC_NPI_ID;
  *(_DWORD *)(v4 + 32) = 2621440;
  v5 = NmrRegisterClient((PNPI_CLIENT_CHARACTERISTICS)v4, (PVOID)v4, (PHANDLE)(v4 + 80));
  if ( v5 < 0 )
  {
LABEL_6:
    _m_prefetchw((const void *)(v4 + 144));
    if ( _InterlockedOr8((volatile signed __int8 *)(v4 + 144), 1u) )
      NmrClientDetachProviderComplete(*v6);
    if ( *v6 )
    {
      if ( NmrDeregisterClient(*v6) == 259 )
        NmrWaitForClientDeregisterComplete(*v6);
      *v6 = 0;
    }
    ExFreePoolWithTag((PVOID)v4, 0x634E514Du);
    goto LABEL_13;
  }
  Timeout.QuadPart = 0;
  if ( KeWaitForSingleObject((PVOID)(v4 + 112), Executive, 0, 0, &Timeout) )
  {
    v5 = -1073741823;
    goto LABEL_6;
  }
  QuicNmrHandle = (PVOID)v4;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*((_QWORD *)QuicNmrHandle + 17) + 8LL))(2, &MsQuic);
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        88,
        WPP_fda175b9f5083825c260891a41b6395b_Traceguids,
        (unsigned int)v8);
    }
    v10 = QuicNmrHandle;
    v11 = (HANDLE *)((char *)QuicNmrHandle + 80);
    _m_prefetchw((char *)QuicNmrHandle + 144);
    v12 = _InterlockedOr8((volatile signed __int8 *)QuicNmrHandle + 144, 1u);
LABEL_25:
    if ( v12 )
      NmrClientDetachProviderComplete(*v11);
    if ( *v11 )
    {
      if ( NmrDeregisterClient(*v11) == 259 )
        NmrWaitForClientDeregisterComplete(*v11);
      *v11 = 0;
    }
    ExFreePoolWithTag(v10, 0x634E514Du);
    QuicNmrHandle = 0;
    return 0;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *, __int64, _QWORD))(MsQuic + 40))(
          v17,
          &Registration,
          v9,
          (unsigned int)v8);
  v16 = (unsigned int)v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (Timer_high & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          89,
          WPP_fda175b9f5083825c260891a41b6395b_Traceguids,
          (unsigned int)v13);
    }
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*((_QWORD *)QuicNmrHandle + 17) + 16LL))(
      MsQuic,
      Timer_high,
      v15,
      v16);
    v10 = QuicNmrHandle;
    MsQuic = 0;
    v11 = (HANDLE *)((char *)QuicNmrHandle + 80);
    _m_prefetchw((char *)QuicNmrHandle + 144);
    v12 = _InterlockedOr8((volatile signed __int8 *)QuicNmrHandle + 144, 1u);
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_fda175b9f5083825c260891a41b6395b_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x140093200  push    rbx
0x140093202  push    rbp
0x140093203  push    rsi
0x140093204  push    rdi
0x140093205  sub     rsp, 48h
0x140093209  mov     edx, 98h
0x14009320e  mov     [rsp+68h+var_30], 0
0x140093217  lea     rax, aSmbClient; "SMB Client"
0x14009321e  mov     r8d, 634E514Dh
0x140093224  mov     [rsp+68h+var_38], rax
0x140093229  lea     ecx, [rdx-58h]
0x14009322c  call    cs:__imp_ExAllocatePool2
0x140093233  nop     dword ptr [rax+rax+00h]
0x140093238  mov     rbx, rax
0x14009323b  test    rax, rax
0x14009323e  jnz     short loc_14009324A
0x140093240  mov     edi, 0C000009Ah
0x140093245  jmp     loc_140093384
0x14009324a  xor     r8d, r8d; State
0x14009324d  lea     rcx, [rax+70h]; Event
0x140093251  lea     edx, [r8+1]; Type
0x140093255  call    cs:__imp_KeInitializeEvent
0x14009325c  nop     dword ptr [rax+rax+00h]
0x140093261  mov     dword ptr [rbx+5Ch], 1
0x140093268  lea     rcx, [rbx+58h]
0x14009326c  mov     word ptr [rcx], 18h
0x140093271  lea     rax, __MsQuicClientAttachProvider
0x140093278  movups  xmm0, xmmword ptr cs:REMOTEFS_SMB.Data1
0x14009327f  mov     [rbx+8], rax
0x140093283  lea     rsi, [rbx+50h]
0x140093287  lea     rax, __MsQuicClientDetachProvider
0x14009328e  mov     word ptr [rbx+2], 48h ; 'H'
0x140093294  movdqu  xmmword ptr [rbx+60h], xmm0
0x140093299  mov     [rbx+10h], rax
0x14009329d  mov     r8, rsi; NmrClientHandle
0x1400932a0  lea     rax, MSQUIC_NPI_ID
0x1400932a7  mov     [rbx+30h], rcx
0x1400932ab  mov     rcx, rbx; ClientCharacteristics
0x1400932ae  mov     [rbx+28h], rax
0x1400932b2  mov     rdx, rbx; ClientContext
0x1400932b5  mov     dword ptr [rbx+20h], 280000h
0x1400932bc  call    cs:__imp_NmrRegisterClient
0x1400932c3  nop     dword ptr [rax+rax+00h]
0x1400932c8  mov     edi, eax
0x1400932ca  test    eax, eax
0x1400932cc  js      short loc_14009330C
0x1400932ce  lea     rax, [rsp+68h+arg_18]
0x1400932d6  mov     qword ptr [rsp+68h+arg_18], 0
0x1400932e2  xor     r9d, r9d; Alertable
0x1400932e5  mov     [rsp+68h+Timeout], rax; Timeout
0x1400932ea  xor     r8d, r8d; WaitMode
0x1400932ed  lea     rcx, [rbx+70h]; Object
0x1400932f1  xor     edx, edx; WaitReason
0x1400932f3  call    cs:__imp_KeWaitForSingleObject
0x1400932fa  nop     dword ptr [rax+rax+00h]
0x1400932ff  test    eax, eax
0x140093301  jz      loc_1400933C3
0x140093307  mov     edi, 0C0000001h
0x14009330c  prefetchw byte ptr [rbx+90h]
0x140093313  mov     al, [rbx+90h]
0x140093319  mov     cl, al
0x14009331b  or      cl, 1
0x14009331e  lock cmpxchg [rbx+90h], cl
0x140093326  jnz     short loc_140093319
0x140093328  test    al, al
0x14009332a  jz      short loc_14009333B
0x14009332c  mov     rcx, [rsi]; NmrBindingHandle
0x14009332f  call    cs:__imp_NmrClientDetachProviderComplete
0x140093336  nop     dword ptr [rax+rax+00h]
0x14009333b  mov     rcx, [rsi]; NmrClientHandle
0x14009333e  test    rcx, rcx
0x140093341  jz      short loc_14009336C
0x140093343  call    cs:__imp_NmrDeregisterClient
0x14009334a  nop     dword ptr [rax+rax+00h]
0x14009334f  cmp     eax, 103h
0x140093354  jnz     short loc_140093365
0x140093356  mov     rcx, [rsi]; NmrClientHandle
0x140093359  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140093360  nop     dword ptr [rax+rax+00h]
0x140093365  mov     qword ptr [rsi], 0
0x14009336c  mov     edx, 634E514Dh; Tag
0x140093371  mov     rcx, rbx; P
0x140093374  call    cs:__imp_ExFreePoolWithTag
0x14009337b  nop     dword ptr [rax+rax+00h]
0x140093380  test    edi, edi
0x140093382  jns     short loc_1400933CA
0x140093384  mov     rcx, cs:WPP_GLOBAL_Control
0x14009338b  lea     rax, WPP_GLOBAL_Control
0x140093392  cmp     rcx, rax
0x140093395  jz      short loc_1400933BC
0x140093397  mov     eax, [rcx+2Ch]
0x14009339a  test    al, 4
0x14009339c  jz      short loc_1400933BC
0x14009339e  cmp     byte ptr [rcx+29h], 4
0x1400933a2  jb      short loc_1400933BC
0x1400933a4  mov     rcx, [rcx+18h]
0x1400933a8  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x1400933af  mov     edx, 57h ; 'W'
0x1400933b4  mov     r9d, edi
0x1400933b7  call    WPP_SF_d
0x1400933bc  xor     eax, eax
0x1400933be  jmp     loc_1400935AA
0x1400933c3  mov     cs:QuicNmrHandle, rbx
0x1400933ca  mov     rax, cs:QuicNmrHandle
0x1400933d1  lea     rdx, MsQuic
0x1400933d8  mov     rcx, [rax+88h]
0x1400933df  mov     rax, [rcx+8]
0x1400933e3  mov     ecx, 2
0x1400933e8  call    _guard_dispatch_icall
0x1400933ed  mov     r9d, eax
0x1400933f0  test    eax, eax
0x1400933f2  jns     loc_1400934BD
0x1400933f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400933ff  lea     rax, WPP_GLOBAL_Control
0x140093406  cmp     rcx, rax
0x140093409  jz      short loc_14009342E
0x14009340b  mov     edx, [rcx+2Ch]
0x14009340e  test    dl, 4
0x140093411  jz      short loc_14009342E
0x140093413  cmp     byte ptr [rcx+29h], 4
0x140093417  jb      short loc_14009342E
0x140093419  mov     rcx, [rcx+18h]
0x14009341d  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x140093424  mov     edx, 58h ; 'X'
0x140093429  call    WPP_SF_d
0x14009342e  mov     rdi, cs:QuicNmrHandle
0x140093435  lea     rbx, [rdi+50h]
0x140093439  prefetchw byte ptr [rdi+90h]
0x140093440  mov     al, [rdi+90h]
0x140093446  mov     cl, al
0x140093448  or      cl, 1
0x14009344b  lock cmpxchg [rdi+90h], cl
0x140093453  jnz     short loc_140093446
0x140093455  test    al, al
0x140093457  jz      short loc_140093468
0x140093459  mov     rcx, [rbx]; NmrBindingHandle
0x14009345c  call    cs:__imp_NmrClientDetachProviderComplete
0x140093463  nop     dword ptr [rax+rax+00h]
0x140093468  mov     rcx, [rbx]; NmrClientHandle
0x14009346b  test    rcx, rcx
0x14009346e  jz      short loc_140093499
0x140093470  call    cs:__imp_NmrDeregisterClient
0x140093477  nop     dword ptr [rax+rax+00h]
0x14009347c  cmp     eax, 103h
0x140093481  jnz     short loc_140093492
0x140093483  mov     rcx, [rbx]; NmrClientHandle
0x140093486  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14009348d  nop     dword ptr [rax+rax+00h]
0x140093492  mov     qword ptr [rbx], 0
0x140093499  mov     edx, 634E514Dh; Tag
0x14009349e  mov     rcx, rdi; P
0x1400934a1  call    cs:__imp_ExFreePoolWithTag
0x1400934a8  nop     dword ptr [rax+rax+00h]
0x1400934ad  mov     cs:QuicNmrHandle, 0
0x1400934b8  jmp     loc_1400933BC
0x1400934bd  mov     rax, cs:MsQuic
0x1400934c4  lea     rdx, Registration
0x1400934cb  lea     rcx, [rsp+68h+var_38]
0x1400934d0  mov     rax, [rax+28h]
0x1400934d4  call    _guard_dispatch_icall
0x1400934d9  mov     r9d, eax
0x1400934dc  test    eax, eax
0x1400934de  jns     loc_14009356F
0x1400934e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400934eb  lea     rax, WPP_GLOBAL_Control
0x1400934f2  cmp     rcx, rax
0x1400934f5  jz      short loc_14009351A
0x1400934f7  mov     edx, [rcx+2Ch]
0x1400934fa  test    dl, 4
0x1400934fd  jz      short loc_14009351A
0x1400934ff  cmp     byte ptr [rcx+29h], 4
0x140093503  jb      short loc_14009351A
0x140093505  mov     rcx, [rcx+18h]
0x140093509  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x140093510  mov     edx, 59h ; 'Y'
0x140093515  call    WPP_SF_d
0x14009351a  mov     rax, cs:QuicNmrHandle
0x140093521  mov     rcx, [rax+88h]
0x140093528  mov     rax, [rcx+10h]
0x14009352c  mov     rcx, cs:MsQuic
0x140093533  call    _guard_dispatch_icall
0x140093538  mov     rdi, cs:QuicNmrHandle
0x14009353f  mov     cs:MsQuic, 0
0x14009354a  lea     rbx, [rdi+50h]
0x14009354e  prefetchw byte ptr [rdi+90h]
0x140093555  mov     al, [rdi+90h]
0x14009355b  mov     cl, al
0x14009355d  or      cl, 1
0x140093560  lock cmpxchg [rdi+90h], cl
0x140093568  jnz     short loc_14009355B
0x14009356a  jmp     loc_140093455
0x14009356f  mov     rcx, cs:WPP_GLOBAL_Control
0x140093576  lea     rax, WPP_GLOBAL_Control
0x14009357d  cmp     rcx, rax
0x140093580  jz      short loc_1400935A5
0x140093582  mov     edx, [rcx+2Ch]
0x140093585  test    dl, 4
0x140093588  jz      short loc_1400935A5
0x14009358a  cmp     byte ptr [rcx+29h], 4
0x14009358e  jb      short loc_1400935A5
0x140093590  mov     rcx, [rcx+18h]
0x140093594  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x14009359b  mov     edx, 5Ah ; 'Z'
0x1400935a0  call    WPP_SF_
0x1400935a5  mov     eax, 1
0x1400935aa  add     rsp, 48h
0x1400935ae  pop     rdi
0x1400935af  pop     rsi
0x1400935b0  pop     rbp
0x1400935b1  pop     rbx
0x1400935b2  retn
```
