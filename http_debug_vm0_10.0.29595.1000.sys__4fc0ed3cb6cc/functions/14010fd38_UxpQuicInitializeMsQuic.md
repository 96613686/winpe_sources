# UxpQuicInitializeMsQuic

- ea: `0x14010fd38`
- end: `0x14010ff2d`
- name: `UxpQuicInitializeMsQuic`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1401095bc`
- `0x14010b1b0`

## callees

- `0x14010fd38`
- `0x140111774`
- `0x1401678f0`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14010fd4f`
- `ntoskrnl!ExAllocatePool2` at `0x14010fd4f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010fe10`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010fe10`
- `ntoskrnl!KeInitializeEvent` at `0x14010fd78`
- `ntoskrnl!KeInitializeEvent` at `0x14010fd78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fe91`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fe91`
- `NETIO!NmrRegisterClient` at `0x14010fddf`
- `NETIO!NmrRegisterClient` at `0x14010fddf`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14010fe76`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14010fe76`
- `NETIO!NmrClientDetachProviderComplete` at `0x14010fe4c`
- `NETIO!NmrClientDetachProviderComplete` at `0x14010fe4c`
- `NETIO!NmrDeregisterClient` at `0x14010fe60`
- `NETIO!NmrDeregisterClient` at `0x14010fe60`

## pseudocode

```c
__int64 UxpQuicInitializeMsQuic()
{
  __int64 Pool2; // rax
  __int64 v1; // rbx
  NTSTATUS v2; // edi
  HANDLE *v3; // rsi
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp+8h] BYREF

  Pool2 = ExAllocatePool2(64, 152, 1666077005);
  v1 = Pool2;
  if ( Pool2 )
  {
    KeInitializeEvent((PRKEVENT)(Pool2 + 112), SynchronizationEvent, 0);
    *(_DWORD *)(v1 + 92) = 1;
    *(_WORD *)(v1 + 88) = 24;
    *(_QWORD *)(v1 + 8) = _MsQuicClientAttachProvider;
    v3 = (HANDLE *)(v1 + 80);
    *(_WORD *)(v1 + 2) = 72;
    *(_OWORD *)(v1 + 96) = HttpServiceTrace;
    *(_QWORD *)(v1 + 16) = _MsQuicClientDetachProvider;
    *(_QWORD *)(v1 + 48) = v1 + 88;
    *(_QWORD *)(v1 + 40) = MSQUIC_NPI_ID;
    *(_DWORD *)(v1 + 32) = 2621440;
    v2 = NmrRegisterClient((PNPI_CLIENT_CHARACTERISTICS)v1, (PVOID)v1, (PHANDLE)(v1 + 80));
    if ( v2 >= 0 )
    {
      Timeout.QuadPart = 0;
      if ( !KeWaitForSingleObject((PVOID)(v1 + 112), Executive, 0, 0, &Timeout) )
      {
        UxQuicNmrHandle = (PVOID)v1;
        v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*((_QWORD *)UxQuicNmrHandle + 17) + 8LL))(
               2,
               &UxQuicFuncTable);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(char **, __int64 *))(UxQuicFuncTable + 40))(
                 &off_140182560,
                 &UxQuicRegistration);
          if ( v2 >= 0 )
            return (unsigned int)v2;
        }
        goto LABEL_15;
      }
      v2 = -1073741823;
    }
    _m_prefetchw((const void *)(v1 + 144));
    if ( _InterlockedOr8((volatile signed __int8 *)(v1 + 144), 1u) )
      NmrClientDetachProviderComplete(*v3);
    if ( *v3 )
    {
      if ( NmrDeregisterClient(*v3) == 259 )
        NmrWaitForClientDeregisterComplete(*v3);
      *v3 = 0;
    }
    ExFreePoolWithTag((PVOID)v1, 0x634E514Du);
  }
  else
  {
    v2 = -1073741670;
  }
LABEL_15:
  if ( (BYTE3(xmmword_1401A2C90) & 2) != 0 )
    WPP_SF_d(537, 12, WPP_21aec585436c3b39be1e04ca4a51c673_Traceguids, (unsigned int)v2);
  UxpQuicTerminateMsQuic();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14010fd38  push    rbx
0x14010fd3a  push    rbp
0x14010fd3b  push    rsi
0x14010fd3c  push    rdi
0x14010fd3d  sub     rsp, 38h
0x14010fd41  mov     edx, 98h
0x14010fd46  mov     r8d, 634E514Dh
0x14010fd4c  lea     ecx, [rdx-58h]
0x14010fd4f  call    cs:__imp_ExAllocatePool2
0x14010fd56  nop     dword ptr [rax+rax+00h]
0x14010fd5b  mov     rbx, rax
0x14010fd5e  test    rax, rax
0x14010fd61  jnz     short loc_14010FD6D
0x14010fd63  mov     edi, 0C000009Ah
0x14010fd68  jmp     loc_14010FEEE
0x14010fd6d  xor     r8d, r8d; State
0x14010fd70  lea     rcx, [rax+70h]; Event
0x14010fd74  lea     edx, [r8+1]; Type
0x14010fd78  call    cs:__imp_KeInitializeEvent
0x14010fd7f  nop     dword ptr [rax+rax+00h]
0x14010fd84  mov     dword ptr [rbx+5Ch], 1
0x14010fd8b  lea     rcx, [rbx+58h]
0x14010fd8f  mov     word ptr [rcx], 18h
0x14010fd94  lea     rax, __MsQuicClientAttachProvider
0x14010fd9b  movups  xmm0, cs:HttpServiceTrace
0x14010fda2  mov     [rbx+8], rax
0x14010fda6  lea     rsi, [rbx+50h]
0x14010fdaa  lea     rax, __MsQuicClientDetachProvider
0x14010fdb1  mov     word ptr [rbx+2], 48h ; 'H'
0x14010fdb7  movdqu  xmmword ptr [rbx+60h], xmm0
0x14010fdbc  mov     [rbx+10h], rax
0x14010fdc0  mov     r8, rsi; NmrClientHandle
0x14010fdc3  lea     rax, MSQUIC_NPI_ID
0x14010fdca  mov     [rbx+30h], rcx
0x14010fdce  mov     rcx, rbx; ClientCharacteristics
0x14010fdd1  mov     [rbx+28h], rax
0x14010fdd5  mov     rdx, rbx; ClientContext
0x14010fdd8  mov     dword ptr [rbx+20h], 280000h
0x14010fddf  call    cs:__imp_NmrRegisterClient
0x14010fde6  nop     dword ptr [rax+rax+00h]
0x14010fdeb  mov     edi, eax
0x14010fded  test    eax, eax
0x14010fdef  js      short loc_14010FE29
0x14010fdf1  lea     rax, [rsp+58h+arg_0]
0x14010fdf6  mov     qword ptr [rsp+58h+arg_0], 0
0x14010fdff  xor     r9d, r9d; Alertable
0x14010fe02  mov     [rsp+58h+Timeout], rax; Timeout
0x14010fe07  xor     r8d, r8d; WaitMode
0x14010fe0a  lea     rcx, [rbx+70h]; Object
0x14010fe0e  xor     edx, edx; WaitReason
0x14010fe10  call    cs:__imp_KeWaitForSingleObject
0x14010fe17  nop     dword ptr [rax+rax+00h]
0x14010fe1c  test    eax, eax
0x14010fe1e  jz      loc_14010FF21
0x14010fe24  mov     edi, 0C0000001h
0x14010fe29  prefetchw byte ptr [rbx+90h]
0x14010fe30  mov     al, [rbx+90h]
0x14010fe36  mov     cl, al
0x14010fe38  or      cl, 1
0x14010fe3b  lock cmpxchg [rbx+90h], cl
0x14010fe43  jnz     short loc_14010FE36
0x14010fe45  test    al, al
0x14010fe47  jz      short loc_14010FE58
0x14010fe49  mov     rcx, [rsi]; NmrBindingHandle
0x14010fe4c  call    cs:__imp_NmrClientDetachProviderComplete
0x14010fe53  nop     dword ptr [rax+rax+00h]
0x14010fe58  mov     rcx, [rsi]; NmrClientHandle
0x14010fe5b  test    rcx, rcx
0x14010fe5e  jz      short loc_14010FE89
0x14010fe60  call    cs:__imp_NmrDeregisterClient
0x14010fe67  nop     dword ptr [rax+rax+00h]
0x14010fe6c  cmp     eax, 103h
0x14010fe71  jnz     short loc_14010FE82
0x14010fe73  mov     rcx, [rsi]; NmrClientHandle
0x14010fe76  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14010fe7d  nop     dword ptr [rax+rax+00h]
0x14010fe82  mov     qword ptr [rsi], 0
0x14010fe89  mov     edx, 634E514Dh; Tag
0x14010fe8e  mov     rcx, rbx; P
0x14010fe91  call    cs:__imp_ExFreePoolWithTag
0x14010fe98  nop     dword ptr [rax+rax+00h]
0x14010fe9d  test    edi, edi
0x14010fe9f  js      short loc_14010FEEE
0x14010fea1  mov     rax, cs:UxQuicNmrHandle
0x14010fea8  lea     rdx, UxQuicFuncTable
0x14010feaf  mov     rcx, [rax+88h]
0x14010feb6  mov     rax, [rcx+8]
0x14010feba  mov     ecx, 2
0x14010febf  call    _guard_dispatch_icall
0x14010fec4  mov     edi, eax
0x14010fec6  test    eax, eax
0x14010fec8  js      short loc_14010FEEE
0x14010feca  mov     rax, cs:UxQuicFuncTable
0x14010fed1  lea     rdx, UxQuicRegistration
0x14010fed8  lea     rcx, off_140182560; "HTTP"
0x14010fedf  mov     rax, [rax+28h]
0x14010fee3  call    _guard_dispatch_icall
0x14010fee8  mov     edi, eax
0x14010feea  test    eax, eax
0x14010feec  jns     short loc_14010FF15
0x14010feee  test    byte ptr cs:xmmword_1401A2C90+3, 2
0x14010fef5  jz      short loc_14010FF10
0x14010fef7  mov     edx, 0Ch
0x14010fefc  lea     r8, WPP_21aec585436c3b39be1e04ca4a51c673_Traceguids
0x14010ff03  mov     ecx, 219h
0x14010ff08  mov     r9d, edi
0x14010ff0b  call    WPP_SF_d
0x14010ff10  call    UxpQuicTerminateMsQuic
0x14010ff15  mov     eax, edi
0x14010ff17  add     rsp, 38h
0x14010ff1b  pop     rdi
0x14010ff1c  pop     rsi
0x14010ff1d  pop     rbp
0x14010ff1e  pop     rbx
0x14010ff1f  retn
0x14010ff21  mov     cs:UxQuicNmrHandle, rbx
0x14010ff28  jmp     loc_14010FEA1
```
