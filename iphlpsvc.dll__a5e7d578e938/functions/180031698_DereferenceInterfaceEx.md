# DereferenceInterfaceEx

- ea: `0x180031698`
- end: `0x180031860`
- name: `DereferenceInterfaceEx`
- size: `456`
- prototype: ``
- caller_count: `16`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800307b0`
- `0x1800311e0`
- `0x1800315b0`
- `0x180031e38`
- `0x180040e30`
- `0x180045014`
- `0x180045550`
- `0x1800455d4`
- `0x180061d74`
- `0x180061e30`
- `0x1800620a4`
- `0x180062cbc`
- `0x180062da8`
- `0x180062f70`
- `0x1800632a0`
- `0x180063680`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180031698`
- `0x18003adb0`
- `0x1800616b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031832`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031832`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031816`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031816`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031845`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031845`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003177c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003177c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031803`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031794`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031794`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031769`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031769`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800317e3`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800317e3`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317a9`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317c6`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317a9`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317c6`
- `webio!__imp_WebCloseHttpRequest` at `0x1800316bc`
- `webio!__imp_WebCloseHttpRequest` at `0x1800316bc`
- `webio!__imp_WebCloseSession` at `0x1800316d3`
- `webio!__imp_WebCloseSession` at `0x1800316d3`
- `webio!__imp_WebDeleteUri` at `0x1800316e8`
- `webio!__imp_WebDeleteUri` at `0x1800316e8`

## string_xrefs

- `0x18003170c`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180031734`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`

## pseudocode

```c
__int64 __fastcall DereferenceInterfaceEx(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  int v7; // ecx
  struct _TP_TIMER *v8; // rcx
  struct _TP_WORK *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)a1 + 31, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    v3 = *a1;
    if ( v3 )
      WebCloseHttpRequest(v3, 0);
    v4 = a1[1];
    if ( v4 )
      WebCloseSession(v4, 0);
    if ( a1[2] )
      WebDeleteUri();
    v5 = a1[16];
    if ( v5 )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Dereference IPTLS interface %S:%d",
        v5 + 56,
        "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
        123);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v7,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE,
          a1[16],
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsclient.c",
          123);
      LOBYTE(v6) = 1;
      IpTlsDereferenceInterfaceEx(a1[16], v6);
    }
    v8 = (struct _TP_TIMER *)a1[20];
    if ( v8 )
      CloseThreadpoolTimer(v8);
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 22));
    v9 = (struct _TP_WORK *)a1[17];
    if ( v9 )
      CloseThreadpoolWork(v9);
    if ( a1[5] )
    {
      ProxyHelperClientFreeMemory();
      a1[5] = 0;
    }
    if ( a1[6] )
    {
      ProxyHelperClientFreeMemory();
      a1[6] = 0;
    }
    v10 = (void *)a1[9];
    if ( v10 )
    {
      SspiFreeAuthIdentity(v10);
      a1[9] = 0;
    }
    v11 = (void *)a1[19];
    if ( v11 )
      CloseHandle(v11);
    EnterCriticalSection(&stru_1800CC350);
    if ( !--dword_1800CC330 )
      SetEvent(qword_1800CC338);
    LeaveCriticalSection(&stru_1800CC350);
    return FREE(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180031698  push    rbx
0x18003169a  sub     rsp, 30h
0x18003169e  mov     rbx, rcx
0x1800316a1  or      eax, 0FFFFFFFFh
0x1800316a4  lock xadd [rcx+7Ch], eax
0x1800316a9  cmp     eax, 1
0x1800316ac  jnz     loc_180031859
0x1800316b2  mov     rcx, [rcx]
0x1800316b5  test    rcx, rcx
0x1800316b8  jz      short loc_1800316C8
0x1800316ba  xor     edx, edx
0x1800316bc  call    cs:__imp_WebCloseHttpRequest
0x1800316c3  nop     dword ptr [rax+rax+00h]
0x1800316c8  mov     rcx, [rbx+8]
0x1800316cc  test    rcx, rcx
0x1800316cf  jz      short loc_1800316DF
0x1800316d1  xor     edx, edx
0x1800316d3  call    cs:__imp_WebCloseSession
0x1800316da  nop     dword ptr [rax+rax+00h]
0x1800316df  mov     rcx, [rbx+10h]
0x1800316e3  test    rcx, rcx
0x1800316e6  jz      short loc_1800316F4
0x1800316e8  call    cs:__imp_WebDeleteUri
0x1800316ef  nop     dword ptr [rax+rax+00h]
0x1800316f4  mov     r8, [rbx+80h]
0x1800316fb  test    r8, r8
0x1800316fe  jz      short loc_18003175D
0x180031700  add     r8, 38h ; '8'
0x180031704  mov     [rsp+38h+var_18], 7Bh ; '{'
0x18003170c  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180031713  mov     ecx, 20000000h
0x180031718  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x18003171f  call    EventWrite0
0x180031724  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18003172b  jz      short loc_18003174F
0x18003172d  mov     r8, [rbx+80h]
0x180031734  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003173b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180031742  mov     [rsp+38h+var_18], 7Bh ; '{'
0x18003174a  call    McTemplateU0psq_EventWriteTransfer
0x18003174f  mov     rcx, [rbx+80h]
0x180031756  mov     dl, 1
0x180031758  call    IpTlsDereferenceInterfaceEx
0x18003175d  mov     rcx, [rbx+0A0h]; pti
0x180031764  test    rcx, rcx
0x180031767  jz      short loc_180031775
0x180031769  call    cs:__imp_CloseThreadpoolTimer
0x180031770  nop     dword ptr [rax+rax+00h]
0x180031775  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x18003177c  call    cs:__imp_DeleteCriticalSection
0x180031783  nop     dword ptr [rax+rax+00h]
0x180031788  mov     rcx, [rbx+88h]; pwk
0x18003178f  test    rcx, rcx
0x180031792  jz      short loc_1800317A0
0x180031794  call    cs:__imp_CloseThreadpoolWork
0x18003179b  nop     dword ptr [rax+rax+00h]
0x1800317a0  mov     rcx, [rbx+28h]
0x1800317a4  test    rcx, rcx
0x1800317a7  jz      short loc_1800317BD
0x1800317a9  call    cs:__imp_ProxyHelperClientFreeMemory
0x1800317b0  nop     dword ptr [rax+rax+00h]
0x1800317b5  mov     qword ptr [rbx+28h], 0
0x1800317bd  mov     rcx, [rbx+30h]
0x1800317c1  test    rcx, rcx
0x1800317c4  jz      short loc_1800317DA
0x1800317c6  call    cs:__imp_ProxyHelperClientFreeMemory
0x1800317cd  nop     dword ptr [rax+rax+00h]
0x1800317d2  mov     qword ptr [rbx+30h], 0
0x1800317da  mov     rcx, [rbx+48h]; AuthData
0x1800317de  test    rcx, rcx
0x1800317e1  jz      short loc_1800317F7
0x1800317e3  call    cs:__imp_SspiFreeAuthIdentity
0x1800317ea  nop     dword ptr [rax+rax+00h]
0x1800317ef  mov     qword ptr [rbx+48h], 0
0x1800317f7  mov     rcx, [rbx+98h]; hObject
0x1800317fe  test    rcx, rcx
0x180031801  jz      short loc_18003180F
0x180031803  call    cs:__imp_CloseHandle
0x18003180a  nop     dword ptr [rax+rax+00h]
0x18003180f  lea     rcx, stru_1800CC350; lpCriticalSection
0x180031816  call    cs:__imp_EnterCriticalSection
0x18003181d  nop     dword ptr [rax+rax+00h]
0x180031822  add     cs:dword_1800CC330, 0FFFFFFFFh
0x180031829  jnz     short loc_18003183E
0x18003182b  mov     rcx, cs:qword_1800CC338; hEvent
0x180031832  call    cs:__imp_SetEvent
0x180031839  nop     dword ptr [rax+rax+00h]
0x18003183e  lea     rcx, stru_1800CC350; lpCriticalSection
0x180031845  call    cs:__imp_LeaveCriticalSection
0x18003184c  nop     dword ptr [rax+rax+00h]
0x180031851  mov     rcx, rbx
0x180031854  call    FREE
0x180031859  add     rsp, 30h
0x18003185d  pop     rbx
0x18003185e  retn
```
