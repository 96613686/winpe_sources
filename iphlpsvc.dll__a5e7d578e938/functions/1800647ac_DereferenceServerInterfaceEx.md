# DereferenceServerInterfaceEx

- ea: `0x1800647ac`
- end: `0x180064975`
- name: `DereferenceServerInterfaceEx`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180046434`
- `0x18004a1c4`
- `0x1800639ac`
- `0x1800646d8`
- `0x180064fe0`
- `0x1800678bc`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x18003adb0`
- `0x1800616b4`
- `0x1800647ac`
- `0x1800677cc`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x180064886`
- `ntdll!RtlRemoveEntryHashTable` at `0x180064886`
- `ntdll!RtlDeleteHashTable` at `0x1800648f0`
- `ntdll!RtlDeleteHashTable` at `0x180064903`
- `ntdll!RtlDeleteHashTable` at `0x180064916`
- `ntdll!RtlDeleteHashTable` at `0x1800648f0`
- `ntdll!RtlDeleteHashTable` at `0x180064903`
- `ntdll!RtlDeleteHashTable` at `0x180064916`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006483f`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18006483f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800648e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800648e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006494f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006494f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064929`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006493c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180064929`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006493c`

## string_xrefs

- `0x1800647e3`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180064813`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
0x1800647ac  push    rbx
0x1800647ae  push    rsi
0x1800647af  push    rdi
0x1800647b0  push    r14
0x1800647b2  sub     rsp, 38h
0x1800647b6  mov     rdi, rcx
0x1800647b9  or      eax, 0FFFFFFFFh
0x1800647bc  lock xadd [rcx+118h], eax
0x1800647c4  cmp     eax, 1
0x1800647c7  jnz     loc_180064963
0x1800647cd  call    ShutdownThreadPoolIo
0x1800647d2  mov     r8, [rdi+120h]
0x1800647d9  test    r8, r8
0x1800647dc  jz      short loc_180064838
0x1800647de  mov     ebx, 168h
0x1800647e3  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x1800647ea  add     r8, 38h ; '8'
0x1800647ee  mov     [rsp+58h+var_38], ebx
0x1800647f2  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x1800647f9  mov     ecx, 20000000h
0x1800647fe  call    EventWrite0
0x180064803  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18006480a  jz      short loc_18006482A
0x18006480c  mov     r8, [rdi+120h]
0x180064813  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18006481a  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180064821  mov     [rsp+58h+var_38], ebx
0x180064825  call    McTemplateU0psq_EventWriteTransfer
0x18006482a  mov     rcx, [rdi+120h]
0x180064831  mov     dl, 1
0x180064833  call    IpTlsDereferenceInterfaceEx
0x180064838  mov     rcx, [rdi+128h]; NotificationHandle
0x18006483f  call    cs:__imp_CancelMibChangeNotify2
0x180064846  nop     dword ptr [rax+rax+00h]
0x18006484b  lea     r14, [rdi+8]
0x18006484f  mov     rsi, [r14]
0x180064852  jmp     short loc_18006489A
0x180064854  mov     rax, [rsi]
0x180064857  cmp     [rax+8], rsi
0x18006485b  jnz     loc_18006496E
0x180064861  mov     rcx, [rsi+8]
0x180064865  cmp     [rcx], rsi
0x180064868  jnz     loc_18006496E
0x18006486e  mov     [rcx], rax
0x180064871  lea     rbx, [rsi-30h]
0x180064875  mov     [rax+8], rcx
0x180064879  mov     rdx, rbx
0x18006487c  lea     rcx, [rdi+68h]
0x180064880  xor     r8d, r8d
0x180064883  mov     rsi, rax
0x180064886  call    cs:__imp_RtlRemoveEntryHashTable
0x18006488d  nop     dword ptr [rax+rax+00h]
0x180064892  mov     rcx, rbx
0x180064895  call    FREE
0x18006489a  cmp     rsi, r14
0x18006489d  jnz     short loc_180064854
0x18006489f  lea     rsi, [rdi+20h]
0x1800648a3  mov     rbx, [rsi]
0x1800648a6  jmp     short loc_1800648D4
0x1800648a8  mov     rax, [rbx]
0x1800648ab  cmp     [rax+8], rbx
0x1800648af  jnz     loc_18006496E
0x1800648b5  mov     rdx, [rbx+8]
0x1800648b9  cmp     [rdx], rbx
0x1800648bc  jnz     loc_18006496E
0x1800648c2  mov     rcx, rbx
0x1800648c5  mov     [rdx], rax
0x1800648c8  mov     rbx, rax
0x1800648cb  mov     [rax+8], rdx
0x1800648cf  call    FREE
0x1800648d4  cmp     rbx, rsi
0x1800648d7  jnz     short loc_1800648A8
0x1800648d9  lea     rcx, [rdi+0F0h]; lpCriticalSection
0x1800648e0  call    cs:__imp_DeleteCriticalSection
0x1800648e7  nop     dword ptr [rax+rax+00h]
0x1800648ec  lea     rcx, [rdi+68h]
0x1800648f0  call    cs:__imp_RtlDeleteHashTable
0x1800648f7  nop     dword ptr [rax+rax+00h]
0x1800648fc  lea     rcx, [rdi+90h]
0x180064903  call    cs:__imp_RtlDeleteHashTable
0x18006490a  nop     dword ptr [rax+rax+00h]
0x18006490f  lea     rcx, [rdi+0B8h]
0x180064916  call    cs:__imp_RtlDeleteHashTable
0x18006491d  nop     dword ptr [rax+rax+00h]
0x180064922  mov     rcx, [rdi+130h]; pti
0x180064929  call    cs:__imp_CloseThreadpoolTimer
0x180064930  nop     dword ptr [rax+rax+00h]
0x180064935  mov     rcx, [rdi+160h]; pti
0x18006493c  call    cs:__imp_CloseThreadpoolTimer
0x180064943  nop     dword ptr [rax+rax+00h]
0x180064948  mov     rcx, [rdi+168h]; pwk
0x18006494f  call    cs:__imp_CloseThreadpoolWork
0x180064956  nop     dword ptr [rax+rax+00h]
0x18006495b  mov     rcx, rdi
0x18006495e  call    FREE
0x180064963  add     rsp, 38h
0x180064967  pop     r14
0x180064969  pop     rdi
0x18006496a  pop     rsi
0x18006496b  pop     rbx
0x18006496c  retn
0x18006496e  mov     ecx, 3
0x180064973  int     29h; Win8: RtlFailFast(ecx)
```
