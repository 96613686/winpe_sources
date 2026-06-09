# SmbQUICRunOnceInitialize

- ea: `0x140093250`
- end: `0x140093604`
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
- `0x140093250`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400932a5`
- `ntoskrnl!KeInitializeEvent` at `0x1400932a5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140093343`
- `ntoskrnl!KeWaitForSingleObject` at `0x140093343`
- `ntoskrnl!ExAllocatePool2` at `0x14009327c`
- `ntoskrnl!ExAllocatePool2` at `0x14009327c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400933c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400934f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400933c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400934f1`
- `NETIO!NmrRegisterClient` at `0x14009330c`
- `NETIO!NmrRegisterClient` at `0x14009330c`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400933a9`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400934d6`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400933a9`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400934d6`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009337f`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400934ac`
- `NETIO!NmrClientDetachProviderComplete` at `0x14009337f`
- `NETIO!NmrClientDetachProviderComplete` at `0x1400934ac`
- `NETIO!NmrDeregisterClient` at `0x140093393`
- `NETIO!NmrDeregisterClient` at `0x1400934c0`
- `NETIO!NmrDeregisterClient` at `0x140093393`
- `NETIO!NmrDeregisterClient` at `0x1400934c0`

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
0x140093250  push    rbx
0x140093252  push    rbp
0x140093253  push    rsi
0x140093254  push    rdi
0x140093255  sub     rsp, 48h
0x140093259  mov     edx, 98h
0x14009325e  mov     [rsp+68h+var_30], 0
0x140093267  lea     rax, aSmbClient; "SMB Client"
0x14009326e  mov     r8d, 634E514Dh
0x140093274  mov     [rsp+68h+var_38], rax
0x140093279  lea     ecx, [rdx-58h]
0x14009327c  call    cs:__imp_ExAllocatePool2
0x140093283  nop     dword ptr [rax+rax+00h]
0x140093288  mov     rbx, rax
0x14009328b  test    rax, rax
0x14009328e  jnz     short loc_14009329A
0x140093290  mov     edi, 0C000009Ah
0x140093295  jmp     loc_1400933D4
0x14009329a  xor     r8d, r8d; State
0x14009329d  lea     rcx, [rax+70h]; Event
0x1400932a1  lea     edx, [r8+1]; Type
0x1400932a5  call    cs:__imp_KeInitializeEvent
0x1400932ac  nop     dword ptr [rax+rax+00h]
0x1400932b1  mov     dword ptr [rbx+5Ch], 1
0x1400932b8  lea     rcx, [rbx+58h]
0x1400932bc  mov     word ptr [rcx], 18h
0x1400932c1  lea     rax, __MsQuicClientAttachProvider
0x1400932c8  movups  xmm0, xmmword ptr cs:REMOTEFS_SMB.Data1
0x1400932cf  mov     [rbx+8], rax
0x1400932d3  lea     rsi, [rbx+50h]
0x1400932d7  lea     rax, __MsQuicClientDetachProvider
0x1400932de  mov     word ptr [rbx+2], 48h ; 'H'
0x1400932e4  movdqu  xmmword ptr [rbx+60h], xmm0
0x1400932e9  mov     [rbx+10h], rax
0x1400932ed  mov     r8, rsi; NmrClientHandle
0x1400932f0  lea     rax, MSQUIC_NPI_ID
0x1400932f7  mov     [rbx+30h], rcx
0x1400932fb  mov     rcx, rbx; ClientCharacteristics
0x1400932fe  mov     [rbx+28h], rax
0x140093302  mov     rdx, rbx; ClientContext
0x140093305  mov     dword ptr [rbx+20h], 280000h
0x14009330c  call    cs:__imp_NmrRegisterClient
0x140093313  nop     dword ptr [rax+rax+00h]
0x140093318  mov     edi, eax
0x14009331a  test    eax, eax
0x14009331c  js      short loc_14009335C
0x14009331e  lea     rax, [rsp+68h+arg_18]
0x140093326  mov     qword ptr [rsp+68h+arg_18], 0
0x140093332  xor     r9d, r9d; Alertable
0x140093335  mov     [rsp+68h+Timeout], rax; Timeout
0x14009333a  xor     r8d, r8d; WaitMode
0x14009333d  lea     rcx, [rbx+70h]; Object
0x140093341  xor     edx, edx; WaitReason
0x140093343  call    cs:__imp_KeWaitForSingleObject
0x14009334a  nop     dword ptr [rax+rax+00h]
0x14009334f  test    eax, eax
0x140093351  jz      loc_140093413
0x140093357  mov     edi, 0C0000001h
0x14009335c  prefetchw byte ptr [rbx+90h]
0x140093363  mov     al, [rbx+90h]
0x140093369  mov     cl, al
0x14009336b  or      cl, 1
0x14009336e  lock cmpxchg [rbx+90h], cl
0x140093376  jnz     short loc_140093369
0x140093378  test    al, al
0x14009337a  jz      short loc_14009338B
0x14009337c  mov     rcx, [rsi]; NmrBindingHandle
0x14009337f  call    cs:__imp_NmrClientDetachProviderComplete
0x140093386  nop     dword ptr [rax+rax+00h]
0x14009338b  mov     rcx, [rsi]; NmrClientHandle
0x14009338e  test    rcx, rcx
0x140093391  jz      short loc_1400933BC
0x140093393  call    cs:__imp_NmrDeregisterClient
0x14009339a  nop     dword ptr [rax+rax+00h]
0x14009339f  cmp     eax, 103h
0x1400933a4  jnz     short loc_1400933B5
0x1400933a6  mov     rcx, [rsi]; NmrClientHandle
0x1400933a9  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400933b0  nop     dword ptr [rax+rax+00h]
0x1400933b5  mov     qword ptr [rsi], 0
0x1400933bc  mov     edx, 634E514Dh; Tag
0x1400933c1  mov     rcx, rbx; P
0x1400933c4  call    cs:__imp_ExFreePoolWithTag
0x1400933cb  nop     dword ptr [rax+rax+00h]
0x1400933d0  test    edi, edi
0x1400933d2  jns     short loc_14009341A
0x1400933d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400933db  lea     rax, WPP_GLOBAL_Control
0x1400933e2  cmp     rcx, rax
0x1400933e5  jz      short loc_14009340C
0x1400933e7  mov     eax, [rcx+2Ch]
0x1400933ea  test    al, 4
0x1400933ec  jz      short loc_14009340C
0x1400933ee  cmp     byte ptr [rcx+29h], 4
0x1400933f2  jb      short loc_14009340C
0x1400933f4  mov     rcx, [rcx+18h]
0x1400933f8  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x1400933ff  mov     edx, 57h ; 'W'
0x140093404  mov     r9d, edi
0x140093407  call    WPP_SF_d
0x14009340c  xor     eax, eax
0x14009340e  jmp     loc_1400935FA
0x140093413  mov     cs:QuicNmrHandle, rbx
0x14009341a  mov     rax, cs:QuicNmrHandle
0x140093421  lea     rdx, MsQuic
0x140093428  mov     rcx, [rax+88h]
0x14009342f  mov     rax, [rcx+8]
0x140093433  mov     ecx, 2
0x140093438  call    _guard_dispatch_icall
0x14009343d  mov     r9d, eax
0x140093440  test    eax, eax
0x140093442  jns     loc_14009350D
0x140093448  mov     rcx, cs:WPP_GLOBAL_Control
0x14009344f  lea     rax, WPP_GLOBAL_Control
0x140093456  cmp     rcx, rax
0x140093459  jz      short loc_14009347E
0x14009345b  mov     edx, [rcx+2Ch]
0x14009345e  test    dl, 4
0x140093461  jz      short loc_14009347E
0x140093463  cmp     byte ptr [rcx+29h], 4
0x140093467  jb      short loc_14009347E
0x140093469  mov     rcx, [rcx+18h]
0x14009346d  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x140093474  mov     edx, 58h ; 'X'
0x140093479  call    WPP_SF_d
0x14009347e  mov     rdi, cs:QuicNmrHandle
0x140093485  lea     rbx, [rdi+50h]
0x140093489  prefetchw byte ptr [rdi+90h]
0x140093490  mov     al, [rdi+90h]
0x140093496  mov     cl, al
0x140093498  or      cl, 1
0x14009349b  lock cmpxchg [rdi+90h], cl
0x1400934a3  jnz     short loc_140093496
0x1400934a5  test    al, al
0x1400934a7  jz      short loc_1400934B8
0x1400934a9  mov     rcx, [rbx]; NmrBindingHandle
0x1400934ac  call    cs:__imp_NmrClientDetachProviderComplete
0x1400934b3  nop     dword ptr [rax+rax+00h]
0x1400934b8  mov     rcx, [rbx]; NmrClientHandle
0x1400934bb  test    rcx, rcx
0x1400934be  jz      short loc_1400934E9
0x1400934c0  call    cs:__imp_NmrDeregisterClient
0x1400934c7  nop     dword ptr [rax+rax+00h]
0x1400934cc  cmp     eax, 103h
0x1400934d1  jnz     short loc_1400934E2
0x1400934d3  mov     rcx, [rbx]; NmrClientHandle
0x1400934d6  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400934dd  nop     dword ptr [rax+rax+00h]
0x1400934e2  mov     qword ptr [rbx], 0
0x1400934e9  mov     edx, 634E514Dh; Tag
0x1400934ee  mov     rcx, rdi; P
0x1400934f1  call    cs:__imp_ExFreePoolWithTag
0x1400934f8  nop     dword ptr [rax+rax+00h]
0x1400934fd  mov     cs:QuicNmrHandle, 0
0x140093508  jmp     loc_14009340C
0x14009350d  mov     rax, cs:MsQuic
0x140093514  lea     rdx, Registration
0x14009351b  lea     rcx, [rsp+68h+var_38]
0x140093520  mov     rax, [rax+28h]
0x140093524  call    _guard_dispatch_icall
0x140093529  mov     r9d, eax
0x14009352c  test    eax, eax
0x14009352e  jns     loc_1400935BF
0x140093534  mov     rcx, cs:WPP_GLOBAL_Control
0x14009353b  lea     rax, WPP_GLOBAL_Control
0x140093542  cmp     rcx, rax
0x140093545  jz      short loc_14009356A
0x140093547  mov     edx, [rcx+2Ch]
0x14009354a  test    dl, 4
0x14009354d  jz      short loc_14009356A
0x14009354f  cmp     byte ptr [rcx+29h], 4
0x140093553  jb      short loc_14009356A
0x140093555  mov     rcx, [rcx+18h]
0x140093559  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x140093560  mov     edx, 59h ; 'Y'
0x140093565  call    WPP_SF_d
0x14009356a  mov     rax, cs:QuicNmrHandle
0x140093571  mov     rcx, [rax+88h]
0x140093578  mov     rax, [rcx+10h]
0x14009357c  mov     rcx, cs:MsQuic
0x140093583  call    _guard_dispatch_icall
0x140093588  mov     rdi, cs:QuicNmrHandle
0x14009358f  mov     cs:MsQuic, 0
0x14009359a  lea     rbx, [rdi+50h]
0x14009359e  prefetchw byte ptr [rdi+90h]
0x1400935a5  mov     al, [rdi+90h]
0x1400935ab  mov     cl, al
0x1400935ad  or      cl, 1
0x1400935b0  lock cmpxchg [rdi+90h], cl
0x1400935b8  jnz     short loc_1400935AB
0x1400935ba  jmp     loc_1400934A5
0x1400935bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400935c6  lea     rax, WPP_GLOBAL_Control
0x1400935cd  cmp     rcx, rax
0x1400935d0  jz      short loc_1400935F5
0x1400935d2  mov     edx, [rcx+2Ch]
0x1400935d5  test    dl, 4
0x1400935d8  jz      short loc_1400935F5
0x1400935da  cmp     byte ptr [rcx+29h], 4
0x1400935de  jb      short loc_1400935F5
0x1400935e0  mov     rcx, [rcx+18h]
0x1400935e4  lea     r8, WPP_fda175b9f5083825c260891a41b6395b_Traceguids
0x1400935eb  mov     edx, 5Ah ; 'Z'
0x1400935f0  call    WPP_SF_
0x1400935f5  mov     eax, 1
0x1400935fa  add     rsp, 48h
0x1400935fe  pop     rdi
0x1400935ff  pop     rsi
0x140093600  pop     rbp
0x140093601  pop     rbx
0x140093602  retn
```
