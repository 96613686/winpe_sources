# CFhService::StopServiceCallback(void *,uchar)

- ea: `0x1800017c0`
- end: `0x180001940`
- name: `?StopServiceCallback@CFhService@@CAXPEAXE@Z`
- size: `384`
- prototype: `void __fastcall(CFhService *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800017c0`
- `0x180001f20`
- `0x1800020c0`
- `0x180002220`
- `0x180002350`
- `0x18000ca14`
- `0x18000d840`

## import_xrefs

- `KERNEL32!UnregisterWaitEx` at `0x18000186d`
- `KERNEL32!UnregisterWaitEx` at `0x18000186d`
- `KERNEL32!SetEvent` at `0x1800018f2`
- `KERNEL32!SetEvent` at `0x1800018f2`
- `KERNEL32!CloseHandle` at `0x1800018fc`
- `KERNEL32!CloseHandle` at `0x1800018fc`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18000190f`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18000190f`

## pseudocode

```c
void __fastcall CFhService::StopServiceCallback(CFhService *this)
{
  void *v2; // rcx
  int v3; // eax
  CManagerThread *v4; // rcx
  int v5; // eax
  int v6; // r8d
  void *v7; // rcx
  void *v8; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids);
  _m_prefetchw((char *)this + 56);
  while ( (_InterlockedOr((volatile signed __int32 *)this + 14, 2u) & 1) != 0 )
  {
    _mm_pause();
    _m_prefetchw((char *)this + 56);
  }
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
0x1800017c0  mov     [rsp+arg_0], rbx
0x1800017c5  mov     [rsp+arg_8], rsi
0x1800017ca  push    rdi
0x1800017cb  sub     rsp, 30h
0x1800017cf  mov     rbx, rcx
0x1800017d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017d9  lea     rsi, WPP_GLOBAL_Control
0x1800017e0  cmp     rcx, rsi
0x1800017e3  jz      short loc_180001800
0x1800017e5  test    byte ptr [rcx+1Ch], 8
0x1800017e9  jz      short loc_180001800
0x1800017eb  mov     rcx, [rcx+10h]
0x1800017ef  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800017f6  mov     edx, 17h
0x1800017fb  call    WPP_SF_
0x180001800  prefetchw byte ptr [rbx+38h]
0x180001804  mov     eax, [rbx+38h]
0x180001807  mov     ecx, eax
0x180001809  or      ecx, 2
0x18000180c  lock cmpxchg [rbx+38h], ecx
0x180001811  jnz     short loc_180001807
0x180001813  test    al, 1
0x180001815  jz      short loc_180001839
0x180001817  nop     word ptr [rax+rax+00000000h]
0x180001820  pause
0x180001822  prefetchw byte ptr [rbx+38h]
0x180001826  mov     eax, [rbx+38h]
0x180001829  mov     ecx, eax
0x18000182b  or      ecx, 2
0x18000182e  lock cmpxchg [rbx+38h], ecx
0x180001833  jnz     short loc_180001829
0x180001835  test    al, 1
0x180001837  jnz     short loc_180001820
0x180001839  mov     rcx, cs:WPP_GLOBAL_Control
0x180001840  cmp     rcx, rsi
0x180001843  jz      short loc_180001860
0x180001845  test    byte ptr [rcx+1Ch], 8
0x180001849  jz      short loc_180001860
0x18000184b  mov     rcx, [rcx+10h]
0x18000184f  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180001856  mov     edx, 18h
0x18000185b  call    WPP_SF_
0x180001860  mov     rcx, [rbx+28h]; WaitHandle
0x180001864  xor     edi, edi
0x180001866  test    rcx, rcx
0x180001869  jz      short loc_180001877
0x18000186b  xor     edx, edx; CompletionEvent
0x18000186d  call    cs:__imp_UnregisterWaitEx
0x180001873  mov     [rbx+28h], rdi
0x180001877  call    ?RpcUnregisterServer@@YAJXZ; RpcUnregisterServer(void)
0x18000187c  test    eax, eax
0x18000187e  jns     short loc_1800018AA
0x180001880  mov     rcx, cs:WPP_GLOBAL_Control
0x180001887  cmp     rcx, rsi
0x18000188a  jz      short loc_1800018AA
0x18000188c  test    byte ptr [rcx+1Ch], 1
0x180001890  jz      short loc_1800018AA
0x180001892  mov     rcx, [rcx+10h]
0x180001896  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x18000189d  mov     edx, 19h
0x1800018a2  mov     r9d, eax
0x1800018a5  call    WPP_SF_d
0x1800018aa  call    ?Stop@CManagerThread@@QEAAJXZ; CManagerThread::Stop(void)
0x1800018af  test    eax, eax
0x1800018b1  jns     short loc_1800018DD
0x1800018b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018ba  cmp     rcx, rsi
0x1800018bd  jz      short loc_1800018DD
0x1800018bf  test    byte ptr [rcx+1Ch], 1
0x1800018c3  jz      short loc_1800018DD
0x1800018c5  mov     rcx, [rcx+10h]
0x1800018c9  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x1800018d0  mov     edx, 1Ah
0x1800018d5  mov     r9d, eax
0x1800018d8  call    WPP_SF_d
0x1800018dd  lea     rcx, ?g_ManagerThread@@3VCManagerThread@@A; this
0x1800018e4  call    ?ReleaseResources@CManagerThread@@QEAAXXZ; CManagerThread::ReleaseResources(void)
0x1800018e9  mov     rcx, [rbx+30h]; hEvent
0x1800018ed  test    rcx, rcx
0x1800018f0  jz      short loc_180001906
0x1800018f2  call    cs:__imp_SetEvent
0x1800018f8  mov     rcx, [rbx+30h]; hObject
0x1800018fc  call    cs:__imp_CloseHandle
0x180001902  mov     [rbx+30h], rdi
0x180001906  mov     rcx, [rbx+48h]; RegistrationHandle
0x18000190a  test    rcx, rcx
0x18000190d  jz      short loc_180001919
0x18000190f  call    cs:__imp_PowerSettingUnregisterNotification
0x180001915  mov     [rbx+48h], rdi
0x180001919  xor     r9d, r9d; unsigned int
0x18000191c  mov     [rsp+38h+var_18], edi; unsigned int
0x180001920  mov     edx, 1; unsigned int
0x180001925  mov     rcx, rbx; this
0x180001928  call    ?ReportStatus@CFhService@@AEAAJKKKK@Z; CFhService::ReportStatus(ulong,ulong,ulong,ulong)
0x18000192d  mov     rsi, [rsp+38h+arg_8]
0x180001932  mov     [rbx], rdi
0x180001935  mov     rbx, [rsp+38h+arg_0]
0x18000193a  add     rsp, 30h
0x18000193e  pop     rdi
0x18000193f  retn
```
