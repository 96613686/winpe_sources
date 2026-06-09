# CFhService::ShutdownService(void)

- ea: `0x180001690`
- end: `0x1800017b0`
- name: `?ShutdownService@CFhService@@QEAAXXZ`
- size: `288`
- prototype: `void __fastcall(CFhService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180001950`

## callees

- `0x180001690`
- `0x180001f20`
- `0x1800020c0`
- `0x180002220`
- `0x180002350`
- `0x18000ca14`
- `0x18000d840`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x1800016dd`
- `KERNEL32!UnregisterWaitEx` at `0x1800016dd`
- `KERNEL32!SetEvent` at `0x180001762`
- `KERNEL32!SetEvent` at `0x180001762`
- `KERNEL32!CloseHandle` at `0x18000176c`
- `KERNEL32!CloseHandle` at `0x18000176c`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18000177f`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18000177f`

## pseudocode

```c
void __fastcall CFhService::ShutdownService(CFhService *this)
{
  void *v2; // rcx
  int v3; // eax
  CManagerThread *v4; // rcx
  int v5; // eax
  int v6; // r8d
  void *v7; // rcx
  void *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    UnregisterWaitEx(v2, 0);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = RpcUnregisterServer();
  if ( v3 < 0 )
  {
    v4 = (CManagerThread *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
        (unsigned int)v3);
  }
  v5 = CManagerThread::Stop(v4);
  if ( v5 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
      (unsigned int)v5);
  CManagerThread::ReleaseResources((CManagerThread *)&g_ManagerThread);
  v7 = (void *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    SetEvent(v7);
    CloseHandle(*((HANDLE *)this + 6));
    *((_QWORD *)this + 6) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 9);
  if ( v8 )
  {
    PowerSettingUnregisterNotification(v8);
    *((_QWORD *)this + 9) = 0;
  }
  CFhService::ReportStatus(this, 1, v6, 0, 0);
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x180001690  mov     [rsp+arg_0], rbx
0x180001695  mov     [rsp+arg_8], rsi
0x18000169a  push    rdi
0x18000169b  sub     rsp, 30h
0x18000169f  mov     rbx, rcx
0x1800016a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016a9  lea     rsi, WPP_GLOBAL_Control
0x1800016b0  cmp     rcx, rsi
0x1800016b3  jz      short loc_1800016D0
0x1800016b5  test    byte ptr [rcx+1Ch], 8
0x1800016b9  jz      short loc_1800016D0
0x1800016bb  mov     rcx, [rcx+10h]
0x1800016bf  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800016c6  mov     edx, 18h
0x1800016cb  call    WPP_SF_
0x1800016d0  mov     rcx, [rbx+28h]; WaitHandle
0x1800016d4  xor     edi, edi
0x1800016d6  test    rcx, rcx
0x1800016d9  jz      short loc_1800016E7
0x1800016db  xor     edx, edx; CompletionEvent
0x1800016dd  call    cs:__imp_UnregisterWaitEx
0x1800016e3  mov     [rbx+28h], rdi
0x1800016e7  call    ?RpcUnregisterServer@@YAJXZ; RpcUnregisterServer(void)
0x1800016ec  test    eax, eax
0x1800016ee  jns     short loc_18000171A
0x1800016f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800016f7  cmp     rcx, rsi
0x1800016fa  jz      short loc_18000171A
0x1800016fc  test    byte ptr [rcx+1Ch], 1
0x180001700  jz      short loc_18000171A
0x180001702  mov     rcx, [rcx+10h]
0x180001706  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x18000170d  mov     edx, 19h
0x180001712  mov     r9d, eax
0x180001715  call    WPP_SF_d
0x18000171a  call    ?Stop@CManagerThread@@QEAAJXZ; CManagerThread::Stop(void)
0x18000171f  test    eax, eax
0x180001721  jns     short loc_18000174D
0x180001723  mov     rcx, cs:WPP_GLOBAL_Control
0x18000172a  cmp     rcx, rsi
0x18000172d  jz      short loc_18000174D
0x18000172f  test    byte ptr [rcx+1Ch], 1
0x180001733  jz      short loc_18000174D
0x180001735  mov     rcx, [rcx+10h]
0x180001739  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180001740  mov     edx, 1Ah
0x180001745  mov     r9d, eax
0x180001748  call    WPP_SF_d
0x18000174d  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; this
0x180001754  call    ?ReleaseResources@CManagerThread@@QEAAXXZ; CManagerThread::ReleaseResources(void)
0x180001759  mov     rcx, [rbx+30h]; hEvent
0x18000175d  test    rcx, rcx
0x180001760  jz      short loc_180001776
0x180001762  call    cs:__imp_SetEvent
0x180001768  mov     rcx, [rbx+30h]; hObject
0x18000176c  call    cs:__imp_CloseHandle
0x180001772  mov     [rbx+30h], rdi
0x180001776  mov     rcx, [rbx+48h]; RegistrationHandle
0x18000177a  test    rcx, rcx
0x18000177d  jz      short loc_180001789
0x18000177f  call    cs:__imp_PowerSettingUnregisterNotification
0x180001785  mov     [rbx+48h], rdi
0x180001789  xor     r9d, r9d; unsigned int
0x18000178c  mov     [rsp+38h+var_18], edi; unsigned int
0x180001790  mov     edx, 1; unsigned int
0x180001795  mov     rcx, rbx; this
0x180001798  call    ?ReportStatus@CFhService@@AEAAJKKKK@Z; CFhService::ReportStatus(ulong,ulong,ulong,ulong)
0x18000179d  mov     rsi, [rsp+38h+arg_8]
0x1800017a2  mov     [rbx], rdi
0x1800017a5  mov     rbx, [rsp+38h+arg_0]
0x1800017aa  add     rsp, 30h
0x1800017ae  pop     rdi
0x1800017af  retn
```
