# UxpQuicInitializeMsQuic

- ea: `0x14010fd08`
- end: `0x14010fefd`
- name: `UxpQuicInitializeMsQuic`
- size: `501`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14010958c`
- `0x14010b180`

## callees

- `0x14010fd08`
- `0x140111744`
- `0x1401677e0`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14010fd1f`
- `ntoskrnl!ExAllocatePool2` at `0x14010fd1f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010fde0`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010fde0`
- `ntoskrnl!KeInitializeEvent` at `0x14010fd48`
- `ntoskrnl!KeInitializeEvent` at `0x14010fd48`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fe61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010fe61`
- `NETIO!NmrRegisterClient` at `0x14010fdaf`
- `NETIO!NmrRegisterClient` at `0x14010fdaf`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14010fe46`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14010fe46`
- `NETIO!NmrClientDetachProviderComplete` at `0x14010fe1c`
- `NETIO!NmrClientDetachProviderComplete` at `0x14010fe1c`
- `NETIO!NmrDeregisterClient` at `0x14010fe30`
- `NETIO!NmrDeregisterClient` at `0x14010fe30`

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
                 &off_140182550,
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
0x14010fd08  push    rbx
0x14010fd0a  push    rbp
0x14010fd0b  push    rsi
0x14010fd0c  push    rdi
0x14010fd0d  sub     rsp, 38h
0x14010fd11  mov     edx, 98h
0x14010fd16  mov     r8d, 634E514Dh
0x14010fd1c  lea     ecx, [rdx-58h]
0x14010fd1f  call    cs:__imp_ExAllocatePool2
0x14010fd26  nop     dword ptr [rax+rax+00h]
0x14010fd2b  mov     rbx, rax
0x14010fd2e  test    rax, rax
0x14010fd31  jnz     short loc_14010FD3D
0x14010fd33  mov     edi, 0C000009Ah
0x14010fd38  jmp     loc_14010FEBE
0x14010fd3d  xor     r8d, r8d; State
0x14010fd40  lea     rcx, [rax+70h]; Event
0x14010fd44  lea     edx, [r8+1]; Type
0x14010fd48  call    cs:__imp_KeInitializeEvent
0x14010fd4f  nop     dword ptr [rax+rax+00h]
0x14010fd54  mov     dword ptr [rbx+5Ch], 1
0x14010fd5b  lea     rcx, [rbx+58h]
0x14010fd5f  mov     word ptr [rcx], 18h
0x14010fd64  lea     rax, __MsQuicClientAttachProvider
0x14010fd6b  movups  xmm0, cs:HttpServiceTrace
0x14010fd72  mov     [rbx+8], rax
0x14010fd76  lea     rsi, [rbx+50h]
0x14010fd7a  lea     rax, __MsQuicClientDetachProvider
0x14010fd81  mov     word ptr [rbx+2], 48h ; 'H'
0x14010fd87  movdqu  xmmword ptr [rbx+60h], xmm0
0x14010fd8c  mov     [rbx+10h], rax
0x14010fd90  mov     r8, rsi; NmrClientHandle
0x14010fd93  lea     rax, MSQUIC_NPI_ID
0x14010fd9a  mov     [rbx+30h], rcx
0x14010fd9e  mov     rcx, rbx; ClientCharacteristics
0x14010fda1  mov     [rbx+28h], rax
0x14010fda5  mov     rdx, rbx; ClientContext
0x14010fda8  mov     dword ptr [rbx+20h], 280000h
0x14010fdaf  call    cs:__imp_NmrRegisterClient
0x14010fdb6  nop     dword ptr [rax+rax+00h]
0x14010fdbb  mov     edi, eax
0x14010fdbd  test    eax, eax
0x14010fdbf  js      short loc_14010FDF9
0x14010fdc1  lea     rax, [rsp+58h+arg_0]
0x14010fdc6  mov     qword ptr [rsp+58h+arg_0], 0
0x14010fdcf  xor     r9d, r9d; Alertable
0x14010fdd2  mov     [rsp+58h+Timeout], rax; Timeout
0x14010fdd7  xor     r8d, r8d; WaitMode
0x14010fdda  lea     rcx, [rbx+70h]; Object
0x14010fdde  xor     edx, edx; WaitReason
0x14010fde0  call    cs:__imp_KeWaitForSingleObject
0x14010fde7  nop     dword ptr [rax+rax+00h]
0x14010fdec  test    eax, eax
0x14010fdee  jz      loc_14010FEF1
0x14010fdf4  mov     edi, 0C0000001h
0x14010fdf9  prefetchw byte ptr [rbx+90h]
0x14010fe00  mov     al, [rbx+90h]
0x14010fe06  mov     cl, al
0x14010fe08  or      cl, 1
0x14010fe0b  lock cmpxchg [rbx+90h], cl
0x14010fe13  jnz     short loc_14010FE06
0x14010fe15  test    al, al
0x14010fe17  jz      short loc_14010FE28
0x14010fe19  mov     rcx, [rsi]; NmrBindingHandle
0x14010fe1c  call    cs:__imp_NmrClientDetachProviderComplete
0x14010fe23  nop     dword ptr [rax+rax+00h]
0x14010fe28  mov     rcx, [rsi]; NmrClientHandle
0x14010fe2b  test    rcx, rcx
0x14010fe2e  jz      short loc_14010FE59
0x14010fe30  call    cs:__imp_NmrDeregisterClient
0x14010fe37  nop     dword ptr [rax+rax+00h]
0x14010fe3c  cmp     eax, 103h
0x14010fe41  jnz     short loc_14010FE52
0x14010fe43  mov     rcx, [rsi]; NmrClientHandle
0x14010fe46  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14010fe4d  nop     dword ptr [rax+rax+00h]
0x14010fe52  mov     qword ptr [rsi], 0
0x14010fe59  mov     edx, 634E514Dh; Tag
0x14010fe5e  mov     rcx, rbx; P
0x14010fe61  call    cs:__imp_ExFreePoolWithTag
0x14010fe68  nop     dword ptr [rax+rax+00h]
0x14010fe6d  test    edi, edi
0x14010fe6f  js      short loc_14010FEBE
0x14010fe71  mov     rax, cs:UxQuicNmrHandle
0x14010fe78  lea     rdx, UxQuicFuncTable
0x14010fe7f  mov     rcx, [rax+88h]
0x14010fe86  mov     rax, [rcx+8]
0x14010fe8a  mov     ecx, 2
0x14010fe8f  call    _guard_dispatch_icall
0x14010fe94  mov     edi, eax
0x14010fe96  test    eax, eax
0x14010fe98  js      short loc_14010FEBE
0x14010fe9a  mov     rax, cs:UxQuicFuncTable
0x14010fea1  lea     rdx, UxQuicRegistration
0x14010fea8  lea     rcx, off_140182550; "HTTP"
0x14010feaf  mov     rax, [rax+28h]
0x14010feb3  call    _guard_dispatch_icall
0x14010feb8  mov     edi, eax
0x14010feba  test    eax, eax
0x14010febc  jns     short loc_14010FEE5
0x14010febe  test    byte ptr cs:xmmword_1401A2C90+3, 2
0x14010fec5  jz      short loc_14010FEE0
0x14010fec7  mov     edx, 0Ch
0x14010fecc  lea     r8, WPP_21aec585436c3b39be1e04ca4a51c673_Traceguids
0x14010fed3  mov     ecx, 219h
0x14010fed8  mov     r9d, edi
0x14010fedb  call    WPP_SF_d
0x14010fee0  call    UxpQuicTerminateMsQuic
0x14010fee5  mov     eax, edi
0x14010fee7  add     rsp, 38h
0x14010feeb  pop     rdi
0x14010feec  pop     rsi
0x14010feed  pop     rbp
0x14010feee  pop     rbx
0x14010feef  retn
0x14010fef1  mov     cs:UxQuicNmrHandle, rbx
0x14010fef8  jmp     loc_14010FE71
```
