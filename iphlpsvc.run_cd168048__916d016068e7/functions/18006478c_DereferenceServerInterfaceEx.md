# DereferenceServerInterfaceEx

- ea: `0x18006478c`
- end: `0x180064955`
- name: `DereferenceServerInterfaceEx`
- size: `457`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180046474`
- `0x18004a204`
- `0x18006398c`
- `0x1800646b8`
- `0x180064fc0`
- `0x18006789c`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x18003ada0`
- `0x180061694`
- `0x18006478c`
- `0x1800677ac`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180064866`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064866`
- `ntdll!RtlDeleteHashTable` at `0x1800648d0`
- `ntdll!RtlDeleteHashTable` at `0x1800648e3`
- `ntdll!RtlDeleteHashTable` at `0x1800648f6`
- `ntdll!RtlDeleteHashTable` at `0x1800648d0`
- `ntdll!RtlDeleteHashTable` at `0x1800648e3`
- `ntdll!RtlDeleteHashTable` at `0x1800648f6`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006481f`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006481f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800648c0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800648c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006492f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006492f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064909`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006491c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064909`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006491c`

## string_xrefs

- `0x1800647c3`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x1800647f3`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
__int64 __fastcall DereferenceServerInterfaceEx(__int64 a1)
{
  __int64 result; // rax
  __int64 v3; // r8
  __int64 v4; // rdx
  int v5; // ecx
  _QWORD *v6; // rsi
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  _QWORD *v10; // rdx
  _QWORD *v11; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  _QWORD *v14; // rcx
  int v15; // [rsp+20h] [rbp-38h]

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    ShutdownThreadPoolIo(a1);
    v3 = *(_QWORD *)(a1 + 288);
    if ( v3 )
    {
      v15 = 360;
      EventWrite0(
        0x20000000,
        L"(%s: Dereference IPTLS interface %S:%d",
        v3 + 56,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        v15);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v5,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE,
          *(_QWORD *)(a1 + 288),
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          104);
      LOBYTE(v4) = 1;
      IpTlsDereferenceInterfaceEx(*(_QWORD *)(a1 + 288), v4);
    }
    CancelMibChangeNotify2(*(HANDLE *)(a1 + 296));
    v6 = *(_QWORD **)(a1 + 8);
    while ( v6 != (_QWORD *)(a1 + 8) )
    {
      v7 = (_QWORD *)*v6;
      if ( *(_QWORD **)(*v6 + 8LL) != v6 || (v8 = (_QWORD *)v6[1], (_QWORD *)*v8 != v6) )
LABEL_18:
        __fastfail(3u);
      *v8 = v7;
      v9 = v6 - 6;
      v7[1] = v8;
      v10 = v6 - 6;
      v6 = v7;
      RtlRemoveEntryHashTable(a1 + 104, v10, 0);
      FREE(v9);
    }
    v11 = *(_QWORD **)(a1 + 32);
    while ( v11 != (_QWORD *)(a1 + 32) )
    {
      v12 = (_QWORD *)*v11;
      if ( *(_QWORD **)(*v11 + 8LL) != v11 )
        goto LABEL_18;
      v13 = (_QWORD *)v11[1];
      if ( (_QWORD *)*v13 != v11 )
        goto LABEL_18;
      v14 = v11;
      *v13 = v12;
      v11 = v12;
      v12[1] = v13;
      FREE(v14);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
    RtlDeleteHashTable(a1 + 104);
    RtlDeleteHashTable(a1 + 144);
    RtlDeleteHashTable(a1 + 184);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 304));
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 352));
    CloseThreadpoolWork(*(PTP_WORK *)(a1 + 360));
    return FREE(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18006478c  push    rbx
0x18006478e  push    rsi
0x18006478f  push    rdi
0x180064790  push    r14
0x180064792  sub     rsp, 38h
0x180064796  mov     rdi, rcx
0x180064799  or      eax, 0FFFFFFFFh
0x18006479c  lock xadd [rcx+118h], eax
0x1800647a4  cmp     eax, 1
0x1800647a7  jnz     loc_180064943
0x1800647ad  call    ShutdownThreadPoolIo
0x1800647b2  mov     r8, [rdi+120h]
0x1800647b9  test    r8, r8
0x1800647bc  jz      short loc_180064818
0x1800647be  mov     ebx, 168h
0x1800647c3  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800647ca  add     r8, 38h ; '8'
0x1800647ce  mov     [rsp+58h+var_38], ebx
0x1800647d2  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x1800647d9  mov     ecx, 20000000h
0x1800647de  call    EventWrite0
0x1800647e3  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x1800647ea  jz      short loc_18006480A
0x1800647ec  mov     r8, [rdi+120h]
0x1800647f3  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800647fa  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180064801  mov     [rsp+58h+var_38], ebx
0x180064805  call    McTemplateU0psq_EventWriteTransfer
0x18006480a  mov     rcx, [rdi+120h]
0x180064811  mov     dl, 1
0x180064813  call    IpTlsDereferenceInterfaceEx
0x180064818  mov     rcx, [rdi+128h]; NotificationHandle
0x18006481f  call    cs:__imp_CancelMibChangeNotify2
0x180064826  nop     dword ptr [rax+rax+00h]
0x18006482b  lea     r14, [rdi+8]
0x18006482f  mov     rsi, [r14]
0x180064832  jmp     short loc_18006487A
0x180064834  mov     rax, [rsi]
0x180064837  cmp     [rax+8], rsi
0x18006483b  jnz     loc_18006494E
0x180064841  mov     rcx, [rsi+8]
0x180064845  cmp     [rcx], rsi
0x180064848  jnz     loc_18006494E
0x18006484e  mov     [rcx], rax
0x180064851  lea     rbx, [rsi-30h]
0x180064855  mov     [rax+8], rcx
0x180064859  mov     rdx, rbx
0x18006485c  lea     rcx, [rdi+68h]
0x180064860  xor     r8d, r8d
0x180064863  mov     rsi, rax
0x180064866  call    cs:__imp_RtlRemoveEntryHashTable
0x18006486d  nop     dword ptr [rax+rax+00h]
0x180064872  mov     rcx, rbx
0x180064875  call    FREE
0x18006487a  cmp     rsi, r14
0x18006487d  jnz     short loc_180064834
0x18006487f  lea     rsi, [rdi+20h]
0x180064883  mov     rbx, [rsi]
0x180064886  jmp     short loc_1800648B4
0x180064888  mov     rax, [rbx]
0x18006488b  cmp     [rax+8], rbx
0x18006488f  jnz     loc_18006494E
0x180064895  mov     rdx, [rbx+8]
0x180064899  cmp     [rdx], rbx
0x18006489c  jnz     loc_18006494E
0x1800648a2  mov     rcx, rbx
0x1800648a5  mov     [rdx], rax
0x1800648a8  mov     rbx, rax
0x1800648ab  mov     [rax+8], rdx
0x1800648af  call    FREE
0x1800648b4  cmp     rbx, rsi
0x1800648b7  jnz     short loc_180064888
0x1800648b9  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x1800648c0  call    cs:__imp_DeleteCriticalSection
0x1800648c7  nop     dword ptr [rax+rax+00h]
0x1800648cc  lea     rcx, [rdi+68h]
0x1800648d0  call    cs:__imp_RtlDeleteHashTable
0x1800648d7  nop     dword ptr [rax+rax+00h]
0x1800648dc  lea     rcx, [rdi+90h]
0x1800648e3  call    cs:__imp_RtlDeleteHashTable
0x1800648ea  nop     dword ptr [rax+rax+00h]
0x1800648ef  lea     rcx, [rdi+0B8h]
0x1800648f6  call    cs:__imp_RtlDeleteHashTable
0x1800648fd  nop     dword ptr [rax+rax+00h]
0x180064902  mov     rcx, [rdi+130h]; pti
0x180064909  call    cs:__imp_CloseThreadpoolTimer
0x180064910  nop     dword ptr [rax+rax+00h]
0x180064915  mov     rcx, [rdi+160h]; pti
0x18006491c  call    cs:__imp_CloseThreadpoolTimer
0x180064923  nop     dword ptr [rax+rax+00h]
0x180064928  mov     rcx, [rdi+168h]; pwk
0x18006492f  call    cs:__imp_CloseThreadpoolWork
0x180064936  nop     dword ptr [rax+rax+00h]
0x18006493b  mov     rcx, rdi
0x18006493e  call    FREE
0x180064943  add     rsp, 38h
0x180064947  pop     r14
0x180064949  pop     rdi
0x18006494a  pop     rsi
0x18006494b  pop     rbx
0x18006494c  retn
0x18006494e  mov     ecx, 3
0x180064953  int     29h; Win8: RtlFailFast(ecx)
```
