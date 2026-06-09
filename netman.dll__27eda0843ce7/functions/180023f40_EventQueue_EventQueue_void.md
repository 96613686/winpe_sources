# EventQueue::~EventQueue(void)

- ea: `0x180023f40`
- end: `0x18002409e`
- name: `??1EventQueue@@QEAA@XZ`
- size: `350`
- prototype: `void __fastcall(EventQueue *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800204d4`

## callees

- `0x1800043a8`
- `0x18000538c`
- `0x180019200`
- `0x18001f920`
- `0x180023f40`
- `0x1800240a4`
- `0x180032c3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180024055`
- `KERNEL32!CloseHandle` at `0x180024055`
- `KERNEL32!LeaveCriticalSection` at `0x180023fe4`
- `KERNEL32!LeaveCriticalSection` at `0x180023fe4`
- `KERNEL32!TryEnterCriticalSection` at `0x180023fd7`
- `KERNEL32!TryEnterCriticalSection` at `0x180023fd7`
- `KERNEL32!DeleteCriticalSection` at `0x180023ff4`
- `KERNEL32!DeleteCriticalSection` at `0x180023ff4`
- `ntdll!RtlDeregisterWaitEx` at `0x180023f88`
- `ntdll!RtlDeregisterWaitEx` at `0x180023f88`
- `ntdll!RtlNtStatusToDosError` at `0x180023f90`
- `ntdll!RtlNtStatusToDosError` at `0x180023f90`

## pseudocode

```c
void __fastcall EventQueue::~EventQueue(EventQueue *this)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  bool v4; // sf
  __int64 v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // r8
  __int64 *v8; // rcx
  struct CONMAN_EVENT *v9; // rbx
  __int64 v10; // rdx
  Event *v11; // rcx
  _QWORD **v12; // rcx
  _QWORD *v13; // rcx
  _QWORD *v14; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_7b395475d90435087767593a55cc59de_Traceguids);
  v2 = RtlDeregisterWaitEx(*((HANDLE *)this + 9), (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v3 = RtlNtStatusToDosError(v2);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x80070000;
    v4 = v3 < 0;
  }
  if ( v4 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      &WPP_7b395475d90435087767593a55cc59de_Traceguids,
      (unsigned int)v3);
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16)) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  else
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  while ( 1 )
  {
    v7 = *((_QWORD *)this + 1);
    if ( !v7 )
      break;
    v8 = **(__int64 ***)this;
    v9 = (struct CONMAN_EVENT *)v8[3];
    v10 = *v8;
    *((_QWORD *)this + 1) = v7 - 1;
    *(_QWORD *)v8[1] = v10;
    *(_QWORD *)(v10 + 8) = v8[1];
    std::_Deallocate<16>(v8, 0x20u);
    if ( *(_DWORD *)v9 == 1 )
      FreeConmanEvent(v9);
  }
  v11 = (Event *)*((_QWORD *)this + 7);
  if ( v11 )
    Event::`scalar deleting destructor'(v11, v6);
  CloseHandle(*((HANDLE *)this + 8));
  v12 = *(_QWORD ***)this;
  **(_QWORD **)(*(_QWORD *)this + 8LL) = 0;
  v13 = *v12;
  if ( v13 )
  {
    do
    {
      v14 = (_QWORD *)*v13;
      std::_Deallocate<16>(v13, 0x20u);
      v13 = v14;
    }
    while ( v14 );
  }
  std::_Deallocate<16>(*(_QWORD **)this, 0x20u);
}

```

## disassembly

```asm
0x180023f40  mov     [rsp+arg_0], rbx
0x180023f45  mov     [rsp+arg_8], rsi
0x180023f4a  push    rdi
0x180023f4b  sub     rsp, 20h
0x180023f4f  mov     rdi, rcx
0x180023f52  lea     rbx, WPP_GLOBAL_Control
0x180023f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f60  cmp     rcx, rbx
0x180023f63  jz      short loc_180023F80
0x180023f65  test    byte ptr [rcx+1Ch], 8
0x180023f69  jz      short loc_180023F80
0x180023f6b  mov     edx, 0Eh
0x180023f70  lea     r8, WPP_7b395475d90435087767593a55cc59de_Traceguids
0x180023f77  mov     rcx, [rcx+10h]
0x180023f7b  call    WPP_SF_
0x180023f80  or      rdx, 0FFFFFFFFFFFFFFFFh; hCompletionEvent
0x180023f84  mov     rcx, [rdi+48h]; hWaitHandle
0x180023f88  call    cs:__imp_RtlDeregisterWaitEx
0x180023f8e  mov     ecx, eax; Status
0x180023f90  call    cs:__imp_RtlNtStatusToDosError
0x180023f96  test    eax, eax
0x180023f98  jle     short loc_180023FA4
0x180023f9a  movzx   eax, ax
0x180023f9d  or      eax, 80070000h
0x180023fa2  test    eax, eax
0x180023fa4  jns     short loc_180023FD0
0x180023fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fad  cmp     rcx, rbx
0x180023fb0  jz      short loc_180023FD0
0x180023fb2  test    byte ptr [rcx+1Ch], 1
0x180023fb6  jz      short loc_180023FD0
0x180023fb8  mov     edx, 0Fh
0x180023fbd  mov     r9d, eax
0x180023fc0  lea     r8, WPP_7b395475d90435087767593a55cc59de_Traceguids
0x180023fc7  mov     rcx, [rcx+10h]
0x180023fcb  call    WPP_SF_d
0x180023fd0  lea     rbx, [rdi+10h]
0x180023fd4  mov     rcx, rbx; lpCriticalSection
0x180023fd7  call    cs:__imp_TryEnterCriticalSection
0x180023fdd  test    eax, eax
0x180023fdf  jz      short loc_180023FEC
0x180023fe1  mov     rcx, rbx; lpCriticalSection
0x180023fe4  call    cs:__imp_LeaveCriticalSection
0x180023fea  jmp     short loc_180023FF1
0x180023fec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023ff1  mov     rcx, rbx; lpCriticalSection
0x180023ff4  call    cs:__imp_DeleteCriticalSection
0x180023ffa  mov     esi, 20h ; ' '
0x180023fff  mov     r8, [rdi+8]
0x180024003  test    r8, r8
0x180024006  jz      short loc_180024043
0x180024008  mov     rax, [rdi]
0x18002400b  mov     rcx, [rax]
0x18002400e  mov     rbx, [rcx+18h]
0x180024012  mov     rdx, [rcx]
0x180024015  lea     rax, [r8-1]
0x180024019  mov     [rdi+8], rax
0x18002401d  mov     rax, [rcx+8]
0x180024021  mov     [rax], rdx
0x180024024  mov     rax, [rcx+8]
0x180024028  mov     [rdx+8], rax
0x18002402c  mov     rdx, rsi
0x18002402f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180024034  cmp     dword ptr [rbx], 1
0x180024037  jnz     short loc_180023FFF
0x180024039  mov     rcx, rbx; lpMem
0x18002403c  call    ?FreeConmanEvent@@YAXPEAUCONMAN_EVENT@@@Z; FreeConmanEvent(CONMAN_EVENT *)
0x180024041  jmp     short loc_180023FFF
0x180024043  mov     rcx, [rdi+38h]; this
0x180024047  test    rcx, rcx
0x18002404a  jz      short loc_180024051
0x18002404c  call    ??_GEvent@@QEAAPEAXI@Z; Event::`scalar deleting destructor'(uint)
0x180024051  mov     rcx, [rdi+40h]; hObject
0x180024055  call    cs:__imp_CloseHandle
0x18002405b  mov     rcx, [rdi]
0x18002405e  mov     rax, [rcx+8]
0x180024062  mov     qword ptr [rax], 0
0x180024069  mov     rcx, [rcx]
0x18002406c  test    rcx, rcx
0x18002406f  jz      short loc_180024084
0x180024071  mov     rbx, [rcx]
0x180024074  mov     rdx, rsi
0x180024077  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002407c  mov     rcx, rbx
0x18002407f  test    rbx, rbx
0x180024082  jnz     short loc_180024071
0x180024084  mov     rdx, rsi
0x180024087  mov     rcx, [rdi]
0x18002408a  mov     rbx, [rsp+28h+arg_0]
0x18002408f  mov     rsi, [rsp+28h+arg_8]
0x180024094  add     rsp, 20h
0x180024098  pop     rdi
0x180024099  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
