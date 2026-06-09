# NatHlpSetTimer(_COMPONENT_REFERENCE *,void * *,void (*)(void *,uchar),void *,ulong)

- ea: `0x18000d8f0`
- end: `0x18000db61`
- name: `?NatHlpSetTimer@@YAJPEAU_COMPONENT_REFERENCE@@PEAPEAXP6AXPEAXE@Z2K@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, void **, void (*)(void *, unsigned __int8), void *, ULONG DueTime)`
- caller_count: `12`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca50`
- `0x180013dbc`
- `0x18004ba34`
- `0x18005d3cc`
- `0x18005d5c0`
- `0x180066b74`
- `0x180067cb0`
- `0x180070a4c`
- `0x180070e80`
- `0x1800753a8`
- `0x18008bb24`
- `0x18008bd10`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x18000d8f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d940`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d95a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d95a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d980`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d980`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000db3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000db3f`
- `ntdll!RtlCreateTimer` at `0x18000d9c2`
- `ntdll!RtlCreateTimer` at `0x18000d9c2`

## pseudocode

```c
__int64 __fastcall NatHlpSetTimer(
        struct _RTL_CRITICAL_SECTION *a1,
        void **a2,
        void (*a3)(void *, unsigned __int8),
        void *a4,
        ULONG DueTime)
{
  HANDLE ProcessHeap; // rax
  void **v10; // rax
  void **v11; // rbx
  void **v12; // rsi
  NTSTATUS Timer; // eax
  int v14; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids);
  }
  if ( a1 && !AcquireComponentReference(a1) )
    return 3221225473LL;
  ProcessHeap = GetProcessHeap();
  v10 = (void **)HeapAlloc(ProcessHeap, 8u, 0x18u);
  v11 = v10;
  if ( v10 )
  {
    *v10 = a3;
    v10[1] = a4;
    EnterCriticalSection(&NhpTimerQueueLock);
    if ( NhpTimerQueueHandle )
    {
      v12 = v11 + 2;
      Timer = RtlCreateTimer(NhpTimerQueueHandle, v11 + 2, NhpTimerCallbackRoutine, v11, DueTime, 0, 0);
      v14 = Timer;
      if ( Timer >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        LeaveCriticalSection(&NhpTimerQueueLock);
        if ( v14 >= 0 )
        {
          if ( a2 )
            *a2 = *v12;
          goto LABEL_12;
        }
LABEL_36:
        if ( a1 )
          ReleaseComponentReference((struct _COMPONENT_REFERENCE *)a1);
LABEL_12:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids,
            (unsigned int)v14);
        }
        return (unsigned int)v14;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids,
        (unsigned int)Timer);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids);
      }
      v14 = -1073741823;
    }
    LeaveCriticalSection(&NhpTimerQueueLock);
    goto LABEL_36;
  }
  if ( a1 )
    ReleaseComponentReference((struct _COMPONENT_REFERENCE *)a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids, 3221225495LL);
  }
  return 3221225495LL;
}

```

## disassembly

```asm
0x18000d8f0  mov     [rsp+arg_8], rbp
0x18000d8f5  mov     [rsp+arg_10], rsi
0x18000d8fa  push    rdi
0x18000d8fb  push    r14
0x18000d8fd  push    r15
0x18000d8ff  sub     rsp, 40h
0x18000d903  mov     rsi, r9
0x18000d906  mov     r14, r8
0x18000d909  mov     rdi, rdx
0x18000d90c  mov     rbp, rcx
0x18000d90f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d916  lea     r15, WPP_GLOBAL_Control
0x18000d91d  cmp     rcx, r15
0x18000d920  jz      short loc_18000D932
0x18000d922  test    byte ptr [rcx+1Ch], 8
0x18000d926  jz      short loc_18000D932
0x18000d928  cmp     byte ptr [rcx+19h], 6
0x18000d92c  jnb     loc_18000DA7B
0x18000d932  mov     [rsp+58h+arg_0], rbx
0x18000d937  test    rbp, rbp
0x18000d93a  jnz     loc_18000DA4C
0x18000d940  call    cs:__imp_GetProcessHeap
0x18000d947  nop     dword ptr [rax+rax+00h]
0x18000d94c  mov     edx, 8; dwFlags
0x18000d951  mov     r8d, 18h; dwBytes
0x18000d957  mov     rcx, rax; hHeap
0x18000d95a  call    cs:__imp_HeapAlloc
0x18000d961  nop     dword ptr [rax+rax+00h]
0x18000d966  mov     rbx, rax
0x18000d969  test    rax, rax
0x18000d96c  jz      loc_18000DA63
0x18000d972  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d979  mov     [rax], r14
0x18000d97c  mov     [rax+8], rsi
0x18000d980  call    cs:__imp_EnterCriticalSection
0x18000d987  nop     dword ptr [rax+rax+00h]
0x18000d98c  mov     rcx, cs:?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18000d993  test    rcx, rcx
0x18000d996  jz      loc_18000DB06
0x18000d99c  xor     eax, eax
0x18000d99e  lea     rsi, [rbx+10h]
0x18000d9a2  mov     [rsp+58h+Flags], eax; Flags
0x18000d9a6  lea     r8, ?NhpTimerCallbackRoutine@@YAXPEAXE@Z; Callback
0x18000d9ad  mov     [rsp+58h+Period], eax; Period
0x18000d9b1  mov     r9, rbx; Parameter
0x18000d9b4  mov     eax, [rsp+58h+arg_20]
0x18000d9bb  mov     rdx, rsi; phNewTimer
0x18000d9be  mov     [rsp+58h+DueTime], eax; DueTime
0x18000d9c2  call    cs:__imp_RtlCreateTimer
0x18000d9c9  nop     dword ptr [rax+rax+00h]
0x18000d9ce  mov     ebx, eax
0x18000d9d0  test    eax, eax
0x18000d9d2  js      loc_18000DAC8
0x18000d9d8  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d9df  call    cs:__imp_LeaveCriticalSection
0x18000d9e6  nop     dword ptr [rax+rax+00h]
0x18000d9eb  test    ebx, ebx
0x18000d9ed  js      loc_18000DB4B
0x18000d9f3  test    rdi, rdi
0x18000d9f6  jz      short loc_18000D9FE
0x18000d9f8  mov     rax, [rsi]
0x18000d9fb  mov     [rdi], rax
0x18000d9fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da05  cmp     rcx, r15
0x18000da08  jnz     short loc_18000DA26
0x18000da0a  mov     eax, ebx
0x18000da0c  mov     rbx, [rsp+58h+arg_0]
0x18000da11  mov     rbp, [rsp+58h+arg_8]
0x18000da16  mov     rsi, [rsp+58h+arg_10]
0x18000da1b  add     rsp, 40h
0x18000da1f  pop     r15
0x18000da21  pop     r14
0x18000da23  pop     rdi
0x18000da24  retn
0x18000da26  test    byte ptr [rcx+1Ch], 8
0x18000da2a  jz      short loc_18000DA0A
0x18000da2c  cmp     byte ptr [rcx+19h], 6
0x18000da30  jb      short loc_18000DA0A
0x18000da32  mov     rcx, [rcx+10h]
0x18000da36  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000da3d  mov     edx, 16h
0x18000da42  mov     r9d, ebx
0x18000da45  call    WPP_SF_d
0x18000da4a  jmp     short loc_18000DA0A
0x18000da4c  mov     rcx, rbp; lpCriticalSection
0x18000da4f  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18000da54  test    al, al
0x18000da56  jnz     loc_18000D940
0x18000da5c  mov     eax, 0C0000001h
0x18000da61  jmp     short loc_18000DA0C
0x18000da63  test    rbp, rbp
0x18000da66  jnz     short loc_18000DA95
0x18000da68  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da6f  cmp     rcx, r15
0x18000da72  jnz     short loc_18000DA9F
0x18000da74  mov     eax, 0C0000017h
0x18000da79  jmp     short loc_18000DA0C
0x18000da7b  mov     rcx, [rcx+10h]
0x18000da7f  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000da86  mov     edx, 12h
0x18000da8b  call    WPP_SF_
0x18000da90  jmp     loc_18000D932
0x18000da95  mov     rcx, rbp; struct _COMPONENT_REFERENCE *
0x18000da98  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000da9d  jmp     short loc_18000DA68
0x18000da9f  test    byte ptr [rcx+1Ch], 8
0x18000daa3  jz      short loc_18000DA74
0x18000daa5  cmp     byte ptr [rcx+19h], 6
0x18000daa9  jb      short loc_18000DA74
0x18000daab  mov     rcx, [rcx+10h]
0x18000daaf  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000dab6  mov     edx, 13h
0x18000dabb  mov     r9d, 0C0000017h
0x18000dac1  call    WPP_SF_d
0x18000dac6  jmp     short loc_18000DA74
0x18000dac8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dacf  cmp     rcx, r15
0x18000dad2  jz      loc_18000D9D8
0x18000dad8  test    byte ptr [rcx+1Ch], 8
0x18000dadc  jz      loc_18000D9D8
0x18000dae2  cmp     byte ptr [rcx+19h], 2
0x18000dae6  jb      loc_18000D9D8
0x18000daec  mov     rcx, [rcx+10h]
0x18000daf0  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000daf7  mov     edx, 14h
0x18000dafc  mov     r9d, ebx
0x18000daff  call    WPP_SF_d
0x18000db04  jmp     short loc_18000DB38
0x18000db06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db0d  cmp     rcx, r15
0x18000db10  jz      short loc_18000DB33
0x18000db12  test    byte ptr [rcx+1Ch], 8
0x18000db16  jz      short loc_18000DB33
0x18000db18  cmp     byte ptr [rcx+19h], 4
0x18000db1c  jb      short loc_18000DB33
0x18000db1e  mov     rcx, [rcx+10h]
0x18000db22  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000db29  mov     edx, 15h
0x18000db2e  call    WPP_SF_
0x18000db33  mov     ebx, 0C0000001h
0x18000db38  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000db3f  call    cs:__imp_LeaveCriticalSection
0x18000db46  nop     dword ptr [rax+rax+00h]
0x18000db4b  test    rbp, rbp
0x18000db4e  jz      loc_18000D9FE
0x18000db54  mov     rcx, rbp; struct _COMPONENT_REFERENCE *
0x18000db57  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000db5c  jmp     loc_18000D9FE
```
