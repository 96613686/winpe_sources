# Dns64TcpTransportRefillPostedAcceptRequests

- ea: `0x18006eb88`
- end: `0x18006ef10`
- name: `Dns64TcpTransportRefillPostedAcceptRequests`
- size: `904`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006df20`
- `0x18006e6a0`
- `0x18006ef18`
- `0x18006f450`
- `0x18006f6d8`

## callees

- `0x1800159d4`
- `0x180045d64`
- `0x1800616b4`
- `0x18006bbb4`
- `0x18006c7bc`
- `0x18006eb88`
- `0x18006f388`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ed4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006edde`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ed4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006edde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ebb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ebb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ed88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee1d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006ee31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ed9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ec55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ed9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006ee7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006eef2`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006ed2f`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18006ed2f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006ecbb`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18006ecbb`
- `WS2_32!__imp_WSAGetLastError` at `0x18006ed0c`
- `WS2_32!__imp_WSAGetLastError` at `0x18006ed0c`

## string_xrefs

- `0x18006ec19`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006edf3`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006ee93`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`
- `0x18006eecf`: `onecoreuap\net\netio\iphlpsvc\service\dns64tcp.c`

## pseudocode

```c
void __fastcall Dns64TcpTransportRefillPostedAcceptRequests(__int64 a1, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  _DWORD *v7; // rsi
  int v8; // edx
  int v9; // ecx
  __int64 v10; // rbx
  __int64 v11; // r15
  volatile signed __int32 *v12; // r14
  int v13; // ecx
  int v14; // ecx
  int Error; // eax
  int v16; // ecx
  int v17; // ecx
  int v18; // r12d
  __int64 *v19; // rdi
  __int64 v20; // rax
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // [rsp+A0h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 72);
  v23 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  v7 = (_DWORD *)(a1 + 112);
  if ( a2 )
    --*v7;
  if ( a3 )
    --*(_DWORD *)(a1 + 116);
  if ( !*(_DWORD *)a1 || *v7 || *(_DWORD *)(a1 + 116) >= 0x2710u )
    goto LABEL_41;
  Dns64RequestAllocateEx(a1 - 272, 1, &v23);
  v10 = v23;
  if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
    McTemplateU0psqp_EventWriteTransfer(
      v9,
      v8,
      v23,
      (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
      220,
      a1 - 16);
  if ( v10 )
  {
    ++*(_DWORD *)(a1 + 116);
    ++*v7;
    LeaveCriticalSection(v3);
    v11 = v10 - 232;
    if ( (unsigned int)Dns64TcpTransportRequestPrepareReceiveSocket(v10 - 232)
      || (v12 = (volatile signed __int32 *)(a1 + 24), !(unsigned __int8)RoReferenceEx(a1 + 24)) )
    {
LABEL_23:
      EnterCriticalSection(v3);
      --*(_DWORD *)(a1 + 116);
      --*v7;
      LeaveCriticalSection(v3);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v17,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
          92);
LABEL_40:
      Dns64RequestDereferenceEx(v10);
      return;
    }
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v13,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        252);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    StartThreadpoolIo(*(PTP_IO *)(a1 + 16));
    if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, int, int, __int64, __int64))(a1 + 120))(
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(v11 + 24),
            v11 + 72,
            0,
            44,
            44,
            v11 + 160,
            v11 + 192) )
    {
      Error = WSAGetLastError();
      if ( Error )
      {
        if ( Error != 997 )
        {
          CancelThreadpoolIo(*(PTP_IO *)(a1 + 16));
          if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFE) == 3 )
            SetEvent(*(HANDLE *)(a1 + 32));
          if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
            McTemplateU0psq_EventWriteTransfer(
              v16,
              (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
              v10,
              (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
              36);
          Dns64RequestDereferenceEx(v10);
          goto LABEL_23;
        }
      }
    }
    v18 = 0;
    if ( _InterlockedExchangeAdd(v12, 0xFFFFFFFE) == 3 )
      SetEvent(*(HANDLE *)(a1 + 32));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v14,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        54);
    _InterlockedAdd((volatile signed __int32 *)(v10 + 736), 1u);
    EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( !*(_DWORD *)v11 )
    {
      EnterCriticalSection(v3);
      if ( *(_DWORD *)a1 )
      {
        v19 = (__int64 *)(a1 + 40);
        v20 = *v19;
        if ( *(__int64 **)(*v19 + 8) != v19 )
          __fastfail(3u);
        *(_QWORD *)v10 = v20;
        v18 = 1;
        *(_QWORD *)(v10 + 8) = v19;
        *(_QWORD *)(v20 + 8) = v10;
        *v19 = v10;
        *(_DWORD *)(v10 + 16) = 1;
      }
      LeaveCriticalSection(v3);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v21,
        (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
        72);
    Dns64RequestDereferenceEx(v10);
    if ( !v18 )
    {
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x10000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v22,
          (unsigned int)EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE,
          v10,
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\dns64tcp.c",
          82);
      goto LABEL_40;
    }
  }
  else
  {
LABEL_41:
    LeaveCriticalSection(v3);
  }
}

```

## disassembly

```asm
0x18006eb88  mov     rax, rsp
0x18006eb8b  push    rbx
0x18006eb8c  push    rbp
0x18006eb8d  push    rsi
0x18006eb8e  push    rdi
0x18006eb8f  push    r12
0x18006eb91  push    r13
0x18006eb93  push    r14
0x18006eb95  push    r15
0x18006eb97  sub     rsp, 58h
0x18006eb9b  lea     rbp, [rcx+48h]
0x18006eb9f  mov     qword ptr [rax+8], 0
0x18006eba7  mov     rdi, rcx
0x18006ebaa  mov     r14d, r8d
0x18006ebad  mov     rcx, rbp; lpCriticalSection
0x18006ebb0  mov     ebx, edx
0x18006ebb2  call    cs:__imp_EnterCriticalSection
0x18006ebb9  nop     dword ptr [rax+rax+00h]
0x18006ebbe  or      eax, 0FFFFFFFFh
0x18006ebc1  lea     rsi, [rdi+70h]
0x18006ebc5  test    ebx, ebx
0x18006ebc7  jz      short loc_18006EBCB
0x18006ebc9  add     [rsi], eax
0x18006ebcb  test    r14d, r14d
0x18006ebce  jz      short loc_18006EBD3
0x18006ebd0  add     [rdi+74h], eax
0x18006ebd3  cmp     dword ptr [rdi], 0
0x18006ebd6  jz      loc_18006EEEF
0x18006ebdc  mov     r13d, 1
0x18006ebe2  cmp     [rsi], r13d
0x18006ebe5  jnb     loc_18006EEEF
0x18006ebeb  cmp     dword ptr [rdi+74h], 2710h
0x18006ebf2  jnb     loc_18006EEEF
0x18006ebf8  lea     r14, [rdi-110h]
0x18006ebff  mov     edx, r13d
0x18006ec02  mov     rcx, r14
0x18006ec05  lea     r8, [rsp+98h+arg_0]
0x18006ec0d  call    Dns64RequestAllocateEx
0x18006ec12  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ec19  lea     r12, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ec20  mov     rbx, [rsp+98h+arg_0]
0x18006ec28  jz      short loc_18006EC42
0x18006ec2a  mov     [rsp+98h+var_70], r14
0x18006ec2f  mov     r9, r12
0x18006ec32  mov     r8, rbx
0x18006ec35  mov     [rsp+98h+var_78], 1DCh
0x18006ec3d  call    McTemplateU0psqp_EventWriteTransfer
0x18006ec42  test    rbx, rbx
0x18006ec45  jz      loc_18006EEEF
0x18006ec4b  add     [rdi+74h], r13d
0x18006ec4f  mov     rcx, rbp; lpCriticalSection
0x18006ec52  add     [rsi], r13d
0x18006ec55  call    cs:__imp_LeaveCriticalSection
0x18006ec5c  nop     dword ptr [rax+rax+00h]
0x18006ec61  lea     r15, [rbx-0E8h]
0x18006ec68  mov     rcx, r15
0x18006ec6b  call    Dns64TcpTransportRequestPrepareReceiveSocket
0x18006ec70  test    eax, eax
0x18006ec72  jnz     loc_18006ED85
0x18006ec78  lea     r14, [rdi+18h]
0x18006ec7c  mov     rcx, r14
0x18006ec7f  call    RoReferenceEx
0x18006ec84  test    al, al
0x18006ec86  jz      loc_18006ED85
0x18006ec8c  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ec93  jz      short loc_18006ECAF
0x18006ec95  mov     r9, r12
0x18006ec98  mov     [rsp+98h+var_78], 1FCh
0x18006eca0  mov     r8, rbx
0x18006eca3  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006ecaa  call    McTemplateU0psq_EventWriteTransfer
0x18006ecaf  lock add [rbx+2E0h], r13d
0x18006ecb7  mov     rcx, [rdi+10h]; pio
0x18006ecbb  call    cs:__imp_StartThreadpoolIo
0x18006ecc2  nop     dword ptr [rax+rax+00h]
0x18006ecc7  mov     eax, 2Ch ; ','
0x18006eccc  lea     rcx, [r15+0C0h]
0x18006ecd3  mov     [rsp+98h+var_60], rcx
0x18006ecd8  lea     rdx, [r15+0A0h]
0x18006ecdf  mov     rcx, [rdi+8]
0x18006ece3  lea     r8, [r15+48h]
0x18006ece7  mov     [rsp+98h+var_68], rdx
0x18006ecec  xor     r9d, r9d
0x18006ecef  mov     rdx, [r15+18h]
0x18006ecf3  mov     dword ptr [rsp+98h+var_70], eax
0x18006ecf7  mov     [rsp+98h+var_78], eax
0x18006ecfb  mov     rax, [rdi+78h]
0x18006ecff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed04  test    eax, eax
0x18006ed06  jnz     loc_18006EDC8
0x18006ed0c  call    cs:__imp_WSAGetLastError
0x18006ed13  nop     dword ptr [rax+rax+00h]
0x18006ed18  test    eax, eax
0x18006ed1a  jz      loc_18006EDC8
0x18006ed20  cmp     eax, 3E5h
0x18006ed25  jz      loc_18006EDC8
0x18006ed2b  mov     rcx, [rdi+10h]; pio
0x18006ed2f  call    cs:__imp_CancelThreadpoolIo
0x18006ed36  nop     dword ptr [rax+rax+00h]
0x18006ed3b  mov     eax, 0FFFFFFFEh
0x18006ed40  lock xadd [r14], eax
0x18006ed45  cmp     eax, 3
0x18006ed48  jnz     short loc_18006ED5A
0x18006ed4a  mov     rcx, [rdi+20h]; hEvent
0x18006ed4e  call    cs:__imp_SetEvent
0x18006ed55  nop     dword ptr [rax+rax+00h]
0x18006ed5a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ed61  jz      short loc_18006ED7D
0x18006ed63  mov     r9, r12
0x18006ed66  mov     [rsp+98h+var_78], 224h
0x18006ed6e  mov     r8, rbx
0x18006ed71  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006ed78  call    McTemplateU0psq_EventWriteTransfer
0x18006ed7d  mov     rcx, rbx
0x18006ed80  call    Dns64RequestDereferenceEx
0x18006ed85  mov     rcx, rbp; lpCriticalSection
0x18006ed88  call    cs:__imp_EnterCriticalSection
0x18006ed8f  nop     dword ptr [rax+rax+00h]
0x18006ed94  or      eax, 0FFFFFFFFh
0x18006ed97  mov     rcx, rbp; lpCriticalSection
0x18006ed9a  add     [rdi+74h], eax
0x18006ed9d  add     [rsi], eax
0x18006ed9f  call    cs:__imp_LeaveCriticalSection
0x18006eda6  nop     dword ptr [rax+rax+00h]
0x18006edab  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006edb2  jz      loc_18006EEE5
0x18006edb8  mov     [rsp+98h+var_78], 25Ch
0x18006edc0  mov     r9, r12
0x18006edc3  jmp     loc_18006EED6
0x18006edc8  xor     r12d, r12d
0x18006edcb  lea     eax, [r12-2]
0x18006edd0  lock xadd [r14], eax
0x18006edd5  cmp     eax, 3
0x18006edd8  jnz     short loc_18006EDEA
0x18006edda  mov     rcx, [rdi+20h]; hEvent
0x18006edde  call    cs:__imp_SetEvent
0x18006ede5  nop     dword ptr [rax+rax+00h]
0x18006edea  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006edf1  jz      short loc_18006EE11
0x18006edf3  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006edfa  mov     [rsp+98h+var_78], 236h
0x18006ee02  mov     r8, rbx
0x18006ee05  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_REFERENCE
0x18006ee0c  call    McTemplateU0psq_EventWriteTransfer
0x18006ee11  lock add [rbx+2E0h], r13d
0x18006ee19  lea     rcx, [rbx+18h]; lpCriticalSection
0x18006ee1d  call    cs:__imp_EnterCriticalSection
0x18006ee24  nop     dword ptr [rax+rax+00h]
0x18006ee29  cmp     [r15], r12d
0x18006ee2c  jnz     short loc_18006EE7A
0x18006ee2e  mov     rcx, rbp; lpCriticalSection
0x18006ee31  call    cs:__imp_EnterCriticalSection
0x18006ee38  nop     dword ptr [rax+rax+00h]
0x18006ee3d  cmp     [rdi], r12d
0x18006ee40  jz      short loc_18006EE6B
0x18006ee42  add     rdi, 28h ; '('
0x18006ee46  mov     rax, [rdi]
0x18006ee49  cmp     [rax+8], rdi
0x18006ee4d  jz      short loc_18006EE56
0x18006ee4f  mov     ecx, 3
0x18006ee54  int     29h; Win8: RtlFailFast(ecx)
0x18006ee56  mov     [rbx], rax
0x18006ee59  mov     r12d, r13d
0x18006ee5c  mov     [rbx+8], rdi
0x18006ee60  mov     [rax+8], rbx
0x18006ee64  mov     [rdi], rbx
0x18006ee67  mov     [rbx+10h], r13d
0x18006ee6b  mov     rcx, rbp; lpCriticalSection
0x18006ee6e  call    cs:__imp_LeaveCriticalSection
0x18006ee75  nop     dword ptr [rax+rax+00h]
0x18006ee7a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18006ee7e  call    cs:__imp_LeaveCriticalSection
0x18006ee85  nop     dword ptr [rax+rax+00h]
0x18006ee8a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006ee91  jz      short loc_18006EEB1
0x18006ee93  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006ee9a  mov     [rsp+98h+var_78], 248h
0x18006eea2  mov     r8, rbx
0x18006eea5  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006eeac  call    McTemplateU0psq_EventWriteTransfer
0x18006eeb1  mov     rcx, rbx
0x18006eeb4  call    Dns64RequestDereferenceEx
0x18006eeb9  test    r12d, r12d
0x18006eebc  jnz     short loc_18006EEFE
0x18006eebe  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r13b
0x18006eec5  jz      short loc_18006EEE5
0x18006eec7  mov     [rsp+98h+var_78], 252h
0x18006eecf  lea     r9, aOnecoreuapNetN_36; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006eed6  mov     r8, rbx
0x18006eed9  lea     rdx, EVENT_IPHLPSVC_ETW_DNS64_REQUEST_DEREFERENCE
0x18006eee0  call    McTemplateU0psq_EventWriteTransfer
0x18006eee5  mov     rcx, rbx
0x18006eee8  call    Dns64RequestDereferenceEx
0x18006eeed  jmp     short loc_18006EEFE
0x18006eeef  mov     rcx, rbp; lpCriticalSection
0x18006eef2  call    cs:__imp_LeaveCriticalSection
0x18006eef9  nop     dword ptr [rax+rax+00h]
0x18006eefe  add     rsp, 58h
0x18006ef02  pop     r15
0x18006ef04  pop     r14
0x18006ef06  pop     r13
0x18006ef08  pop     r12
0x18006ef0a  pop     rdi
0x18006ef0b  pop     rsi
0x18006ef0c  pop     rbp
0x18006ef0d  pop     rbx
0x18006ef0e  retn
```
