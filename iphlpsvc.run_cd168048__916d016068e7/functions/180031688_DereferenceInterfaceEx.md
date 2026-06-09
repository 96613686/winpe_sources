# DereferenceInterfaceEx

- ea: `0x180031688`
- end: `0x180031850`
- name: `DereferenceInterfaceEx`
- size: `456`
- prototype: ``
- caller_count: `16`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800307a0`
- `0x1800311d0`
- `0x1800315a0`
- `0x180031e28`
- `0x180040e70`
- `0x180045054`
- `0x180045590`
- `0x180045614`
- `0x180061d54`
- `0x180061e10`
- `0x180062084`
- `0x180062c9c`
- `0x180062d88`
- `0x180062f50`
- `0x180063280`
- `0x180063660`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180031688`
- `0x18003ada0`
- `0x180061694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031822`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031822`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031806`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031806`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031835`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031835`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003176c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003176c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800317f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800317f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180031784`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031759`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180031759`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800317d3`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800317d3`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180031799`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317b6`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x180031799`
- `ext-ms-win-net-httpproxyext-l1-1-0!ProxyHelperClientFreeMemory` at `0x1800317b6`
- `webio!__imp_WebCloseHttpRequest` at `0x1800316ac`
- `webio!__imp_WebCloseHttpRequest` at `0x1800316ac`
- `webio!__imp_WebCloseSession` at `0x1800316c3`
- `webio!__imp_WebCloseSession` at `0x1800316c3`
- `webio!__imp_WebDeleteUri` at `0x1800316d8`
- `webio!__imp_WebDeleteUri` at `0x1800316d8`

## string_xrefs

- `0x1800316fc`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`
- `0x180031724`: `onecoreuap\net\netio\iphlpsvc\service\iptlsclient.c`

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
0x180031688  push    rbx
0x18003168a  sub     rsp, 30h
0x18003168e  mov     rbx, rcx
0x180031691  or      eax, 0FFFFFFFFh
0x180031694  lock xadd [rcx+7Ch], eax
0x180031699  cmp     eax, 1
0x18003169c  jnz     loc_180031849
0x1800316a2  mov     rcx, [rcx]
0x1800316a5  test    rcx, rcx
0x1800316a8  jz      short loc_1800316B8
0x1800316aa  xor     edx, edx
0x1800316ac  call    cs:__imp_WebCloseHttpRequest
0x1800316b3  nop     dword ptr [rax+rax+00h]
0x1800316b8  mov     rcx, [rbx+8]
0x1800316bc  test    rcx, rcx
0x1800316bf  jz      short loc_1800316CF
0x1800316c1  xor     edx, edx
0x1800316c3  call    cs:__imp_WebCloseSession
0x1800316ca  nop     dword ptr [rax+rax+00h]
0x1800316cf  mov     rcx, [rbx+10h]
0x1800316d3  test    rcx, rcx
0x1800316d6  jz      short loc_1800316E4
0x1800316d8  call    cs:__imp_WebDeleteUri
0x1800316df  nop     dword ptr [rax+rax+00h]
0x1800316e4  mov     r8, [rbx+80h]
0x1800316eb  test    r8, r8
0x1800316ee  jz      short loc_18003174D
0x1800316f0  add     r8, 38h ; '8'
0x1800316f4  mov     [rsp+38h+var_18], 7Bh ; '{'
0x1800316fc  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180031703  mov     ecx, 20000000h
0x180031708  lea     rdx, aSDereferenceIp_0; "(%s: Dereference IPTLS interface %S:%d"
0x18003170f  call    EventWrite0
0x180031714  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18003171b  jz      short loc_18003173F
0x18003171d  mov     r8, [rbx+80h]
0x180031724  lea     r9, aOnecoreuapNetN_45; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003172b  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_INTERFACE_DEREFERENCE
0x180031732  mov     [rsp+38h+var_18], 7Bh ; '{'
0x18003173a  call    McTemplateU0psq_EventWriteTransfer
0x18003173f  mov     rcx, [rbx+80h]
0x180031746  mov     dl, 1
0x180031748  call    IpTlsDereferenceInterfaceEx
0x18003174d  mov     rcx, [rbx+0A0h]; pti
0x180031754  test    rcx, rcx
0x180031757  jz      short loc_180031765
0x180031759  call    cs:__imp_CloseThreadpoolTimer
0x180031760  nop     dword ptr [rax+rax+00h]
0x180031765  lea     rcx, [rbx+0B0h]; lpCriticalSection
0x18003176c  call    cs:__imp_DeleteCriticalSection
0x180031773  nop     dword ptr [rax+rax+00h]
0x180031778  mov     rcx, [rbx+88h]; pwk
0x18003177f  test    rcx, rcx
0x180031782  jz      short loc_180031790
0x180031784  call    cs:__imp_CloseThreadpoolWork
0x18003178b  nop     dword ptr [rax+rax+00h]
0x180031790  mov     rcx, [rbx+28h]
0x180031794  test    rcx, rcx
0x180031797  jz      short loc_1800317AD
0x180031799  call    cs:__imp_ProxyHelperClientFreeMemory
0x1800317a0  nop     dword ptr [rax+rax+00h]
0x1800317a5  mov     qword ptr [rbx+28h], 0
0x1800317ad  mov     rcx, [rbx+30h]
0x1800317b1  test    rcx, rcx
0x1800317b4  jz      short loc_1800317CA
0x1800317b6  call    cs:__imp_ProxyHelperClientFreeMemory
0x1800317bd  nop     dword ptr [rax+rax+00h]
0x1800317c2  mov     qword ptr [rbx+30h], 0
0x1800317ca  mov     rcx, [rbx+48h]; AuthData
0x1800317ce  test    rcx, rcx
0x1800317d1  jz      short loc_1800317E7
0x1800317d3  call    cs:__imp_SspiFreeAuthIdentity
0x1800317da  nop     dword ptr [rax+rax+00h]
0x1800317df  mov     qword ptr [rbx+48h], 0
0x1800317e7  mov     rcx, [rbx+98h]; hObject
0x1800317ee  test    rcx, rcx
0x1800317f1  jz      short loc_1800317FF
0x1800317f3  call    cs:__imp_CloseHandle
0x1800317fa  nop     dword ptr [rax+rax+00h]
0x1800317ff  lea     rcx, stru_1800CC350; lpCriticalSection
0x180031806  call    cs:__imp_EnterCriticalSection
0x18003180d  nop     dword ptr [rax+rax+00h]
0x180031812  add     cs:dword_1800CC330, 0FFFFFFFFh
0x180031819  jnz     short loc_18003182E
0x18003181b  mov     rcx, cs:qword_1800CC338; hEvent
0x180031822  call    cs:__imp_SetEvent
0x180031829  nop     dword ptr [rax+rax+00h]
0x18003182e  lea     rcx, stru_1800CC350; lpCriticalSection
0x180031835  call    cs:__imp_LeaveCriticalSection
0x18003183c  nop     dword ptr [rax+rax+00h]
0x180031841  mov     rcx, rbx
0x180031844  call    FREE
0x180031849  add     rsp, 30h
0x18003184d  pop     rbx
0x18003184e  retn
```
