# CDtcService::Stop(void)

- ea: `0x180083e40`
- end: `0x18008404f`
- name: `?Stop@CDtcService@@UEAAJXZ`
- size: `527`
- prototype: `__int64 __fastcall(CDtcService *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006220`
- `0x1800063b0`
- `0x180083e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084038`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084038`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083f18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083f55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083fb2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083f18`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083f55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180083fb2`
- `USER32!PostThreadMessageA` at `0x180083f06`
- `USER32!PostThreadMessageA` at `0x180083f06`

## string_xrefs

- `0x180083e5d`: `com\complus\dtc\dtc\msdtc\src\cservice.cpp`
- `0x180083e51`: `CDtcService::Stop IN`
- `0x180083e6c`: `CDtcService::Stop`
- `0x180083eb1`: `CDtcService::Stop OUT 1`
- `0x180083f1e`: `WaitForSingleObject(m_hWorkerThread, 2000)`
- `0x180083f60`: `WaitForSingleObject(m_hWorkerThread, 2000)`
- `0x180083fc3`: `CDtcService::Stopped`
- `0x180084008`: `CDtcService::Stop OUT 2`

## pseudocode

```c
__int64 __fastcall CDtcService::Stop(CDtcService *this)
{
  unsigned int v3; // edi

  TraceStringInline(
    3,
    6,
    L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
    285,
    L"CDtcService::Stop",
    0,
    L"CDtcService::Stop IN");
  if ( *((_QWORD *)this + 5) )
  {
    CDtcService::ReportStatus(this, 3u, 0, 1u, 0x124F80u, 0);
    PostThreadMessageA(*((_DWORD *)this + 12), 0x12u, 0, 0);
    WaitForSingleObject(z_hCleanUpDoneEvent, 0xDBBA0u);
    v3 = 2;
    TraceStringInline(
      3,
      4,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      312,
      L"CDtcService::Stop",
      0,
      L"WaitForSingleObject(m_hWorkerThread, 2000)");
    while ( WaitForSingleObject(*((HANDLE *)this + 5), 0x7D0u) == -1 )
    {
      CDtcService::ReportStatus(this, 3u, 0, v3++, 0x7D0u, 0);
      TraceStringInline(
        3,
        4,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
        312,
        L"CDtcService::Stop",
        0,
        L"WaitForSingleObject(m_hWorkerThread, 2000)");
    }
    TraceStringInline(
      3,
      4,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      317,
      L"CDtcService::Stop",
      0,
      L"CDtcService::Stopped");
    CDtcService::ReportStatus(this, 1u, 0, 0, 0, 0);
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      320,
      L"CDtcService::Stop",
      0,
      L"CDtcService::Stop OUT 2");
    SetEvent(z_hServiceStopDone);
    return 0;
  }
  else
  {
    CDtcService::ReportStatus(this, 1u, 0, 0, 0, 0);
    TraceStringInline(
      3,
      6,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\cservice.cpp",
      292,
      L"CDtcService::Stop",
      0,
      L"CDtcService::Stop OUT 1");
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180083e40  push    rbx
0x180083e42  push    rbp
0x180083e43  push    rsi
0x180083e44  push    rdi
0x180083e45  push    r12
0x180083e47  push    r14
0x180083e49  push    r15
0x180083e4b  sub     rsp, 40h
0x180083e4f  xor     esi, esi
0x180083e51  lea     rax, aCdtcserviceSto_2; "CDtcService::Stop IN"
0x180083e58  mov     [rsp+78h+var_48], rax
0x180083e5d  lea     r14, aComComplusDtcD_35; "com\\complus\\dtc\\dtc\\msdtc\\src\\cse"...
0x180083e64  mov     rbx, rcx
0x180083e67  mov     qword ptr [rsp+78h+var_50], rsi
0x180083e6c  lea     r15, aCdtcserviceSto_0; "CDtcService::Stop"
0x180083e73  mov     r9d, 11Dh
0x180083e79  lea     r12d, [rsi+6]
0x180083e7d  mov     qword ptr [rsp+78h+var_58], r15
0x180083e82  lea     ebp, [rsi+3]
0x180083e85  mov     edx, r12d
0x180083e88  mov     ecx, ebp
0x180083e8a  mov     r8, r14
0x180083e8d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083e92  xor     r8d, r8d; unsigned int
0x180083e95  mov     [rsp+78h+var_50], esi; int
0x180083e99  mov     rcx, rbx; this
0x180083e9c  cmp     [rbx+28h], rsi
0x180083ea0  jnz     short loc_180083EE4
0x180083ea2  xor     r9d, r9d; unsigned int
0x180083ea5  mov     [rsp+78h+var_58], esi; unsigned int
0x180083ea9  lea     edx, [rsi+1]; unsigned int
0x180083eac  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x180083eb1  lea     rax, aCdtcserviceSto; "CDtcService::Stop OUT 1"
0x180083eb8  mov     r9d, 124h
0x180083ebe  mov     [rsp+78h+var_48], rax
0x180083ec3  mov     r8, r14
0x180083ec6  mov     qword ptr [rsp+78h+var_50], rsi
0x180083ecb  mov     edx, r12d
0x180083ece  mov     ecx, ebp
0x180083ed0  mov     qword ptr [rsp+78h+var_58], r15
0x180083ed5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083eda  mov     eax, 80004005h
0x180083edf  jmp     loc_180084040
0x180083ee4  mov     r9d, 1; unsigned int
0x180083eea  mov     [rsp+78h+var_58], 124F80h; unsigned int
0x180083ef2  mov     edx, ebp; unsigned int
0x180083ef4  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x180083ef9  mov     ecx, [rbx+30h]; idThread
0x180083efc  xor     r9d, r9d; lParam
0x180083eff  xor     r8d, r8d; wParam
0x180083f02  lea     edx, [r9+12h]; Msg
0x180083f06  call    cs:__imp_PostThreadMessageA
0x180083f0c  mov     rcx, cs:?z_hCleanUpDoneEvent@@3PEAXEA; hHandle
0x180083f13  mov     edx, 0DBBA0h; dwMilliseconds
0x180083f18  call    cs:__imp_WaitForSingleObject
0x180083f1e  lea     rax, aWaitforsingleo_1; "WaitForSingleObject(m_hWorkerThread, 20"...
0x180083f25  mov     edi, 2
0x180083f2a  mov     [rsp+78h+var_48], rax
0x180083f2f  mov     r9d, 138h
0x180083f35  mov     qword ptr [rsp+78h+var_50], rsi
0x180083f3a  mov     r8, r14
0x180083f3d  mov     ecx, ebp
0x180083f3f  mov     qword ptr [rsp+78h+var_58], r15
0x180083f44  lea     edx, [rdi+2]
0x180083f47  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083f4c  mov     rcx, [rbx+28h]; hHandle
0x180083f50  mov     edx, 7D0h; dwMilliseconds
0x180083f55  call    cs:__imp_WaitForSingleObject
0x180083f5b  cmp     eax, 0FFFFFFFFh
0x180083f5e  jnz     short loc_180083FC3
0x180083f60  lea     r12, aWaitforsingleo_1; "WaitForSingleObject(m_hWorkerThread, 20"...
0x180083f67  mov     [rsp+78h+var_50], esi; int
0x180083f6b  mov     r9d, edi; unsigned int
0x180083f6e  xor     r8d, r8d; unsigned int
0x180083f71  mov     [rsp+78h+var_58], 7D0h; unsigned int
0x180083f79  mov     edx, ebp; unsigned int
0x180083f7b  mov     rcx, rbx; this
0x180083f7e  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x180083f83  mov     [rsp+78h+var_48], r12
0x180083f88  mov     r9d, 138h
0x180083f8e  mov     qword ptr [rsp+78h+var_50], rsi
0x180083f93  mov     r8, r14
0x180083f96  mov     edx, 4
0x180083f9b  mov     qword ptr [rsp+78h+var_58], r15
0x180083fa0  mov     ecx, ebp
0x180083fa2  inc     edi
0x180083fa4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083fa9  mov     rcx, [rbx+28h]; hHandle
0x180083fad  mov     edx, 7D0h; dwMilliseconds
0x180083fb2  call    cs:__imp_WaitForSingleObject
0x180083fb8  cmp     eax, 0FFFFFFFFh
0x180083fbb  jz      short loc_180083F67
0x180083fbd  mov     r12d, 6
0x180083fc3  lea     rax, aCdtcserviceSto_1; "CDtcService::Stopped"
0x180083fca  mov     r9d, 13Dh
0x180083fd0  mov     [rsp+78h+var_48], rax
0x180083fd5  mov     r8, r14
0x180083fd8  mov     qword ptr [rsp+78h+var_50], rsi
0x180083fdd  mov     edx, 4
0x180083fe2  mov     ecx, ebp
0x180083fe4  mov     qword ptr [rsp+78h+var_58], r15
0x180083fe9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180083fee  xor     r9d, r9d; unsigned int
0x180083ff1  mov     [rsp+78h+var_50], esi; int
0x180083ff5  xor     r8d, r8d; unsigned int
0x180083ff8  mov     [rsp+78h+var_58], esi; unsigned int
0x180083ffc  mov     rcx, rbx; this
0x180083fff  lea     edx, [r9+1]; unsigned int
0x180084003  call    ?ReportStatus@CDtcService@@QEAAJKKKKH@Z; CDtcService::ReportStatus(ulong,ulong,ulong,ulong,int)
0x180084008  lea     rax, aCdtcserviceSto_3; "CDtcService::Stop OUT 2"
0x18008400f  mov     r9d, 140h
0x180084015  mov     [rsp+78h+var_48], rax
0x18008401a  mov     r8, r14
0x18008401d  mov     qword ptr [rsp+78h+var_50], rsi
0x180084022  mov     edx, r12d
0x180084025  mov     ecx, ebp
0x180084027  mov     qword ptr [rsp+78h+var_58], r15
0x18008402c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180084031  mov     rcx, cs:?z_hServiceStopDone@@3PEAXEA; hEvent
0x180084038  call    cs:__imp_SetEvent
0x18008403e  xor     eax, eax
0x180084040  add     rsp, 40h
0x180084044  pop     r15
0x180084046  pop     r14
0x180084048  pop     r12
0x18008404a  pop     rdi
0x18008404b  pop     rsi
0x18008404c  pop     rbp
0x18008404d  pop     rbx
0x18008404e  retn
```
