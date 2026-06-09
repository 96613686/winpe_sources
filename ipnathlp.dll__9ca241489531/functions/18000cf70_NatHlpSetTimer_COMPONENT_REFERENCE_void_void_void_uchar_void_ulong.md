# NatHlpSetTimer(_COMPONENT_REFERENCE *,void * *,void (*)(void *,uchar),void *,ulong)

- ea: `0x18000cf70`
- end: `0x18000d1bc`
- name: `?NatHlpSetTimer@@YAJPEAU_COMPONENT_REFERENCE@@PEAPEAXP6AXPEAXE@Z2K@Z`
- size: `588`
- prototype: `__int64 __usercall@<rax>(struct _COMPONENT_REFERENCE *@<rcx>, void **@<rdx>, void (*)(void *, unsigned __int8)@<r8>, void *@<r9>, unsigned int)`
- caller_count: `12`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c140`
- `0x180012e18`
- `0x180047e80`
- `0x180058da8`
- `0x180058f80`
- `0x180061f74`
- `0x180062f90`
- `0x18006b4d4`
- `0x18006b8c0`
- `0x18006fa64`
- `0x180085160`
- `0x180085330`

## callees

- `0x18000b900`
- `0x18000bad0`
- `0x18000c110`
- `0x18000c750`
- `0x18000cf70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cfc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfd4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cfd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cff4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cff4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d047`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d1a0`
- `ntdll!RtlCreateTimer` at `0x18000d030`
- `ntdll!RtlCreateTimer` at `0x18000d030`

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
0x18000cf70  mov     [rsp+arg_8], rbp
0x18000cf75  mov     [rsp+arg_10], rsi
0x18000cf7a  push    rdi
0x18000cf7b  push    r14
0x18000cf7d  push    r15
0x18000cf7f  sub     rsp, 40h
0x18000cf83  mov     rsi, r9
0x18000cf86  mov     r14, r8
0x18000cf89  mov     rdi, rdx
0x18000cf8c  mov     rbp, rcx
0x18000cf8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf96  lea     r15, WPP_GLOBAL_Control
0x18000cf9d  cmp     rcx, r15
0x18000cfa0  jz      short loc_18000CFB2
0x18000cfa2  test    byte ptr [rcx+1Ch], 8
0x18000cfa6  jz      short loc_18000CFB2
0x18000cfa8  cmp     byte ptr [rcx+19h], 6
0x18000cfac  jnb     loc_18000D0DC
0x18000cfb2  mov     [rsp+58h+arg_0], rbx
0x18000cfb7  test    rbp, rbp
0x18000cfba  jnz     loc_18000D0AD
0x18000cfc0  call    cs:__imp_GetProcessHeap
0x18000cfc6  mov     edx, 8; dwFlags
0x18000cfcb  mov     r8d, 18h; dwBytes
0x18000cfd1  mov     rcx, rax; hHeap
0x18000cfd4  call    cs:__imp_HeapAlloc
0x18000cfda  mov     rbx, rax
0x18000cfdd  test    rax, rax
0x18000cfe0  jz      loc_18000D0C4
0x18000cfe6  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000cfed  mov     [rax], r14
0x18000cff0  mov     [rax+8], rsi
0x18000cff4  call    cs:__imp_EnterCriticalSection
0x18000cffa  mov     rcx, cs:?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18000d001  test    rcx, rcx
0x18000d004  jz      loc_18000D167
0x18000d00a  xor     eax, eax
0x18000d00c  lea     rsi, [rbx+10h]
0x18000d010  mov     [rsp+58h+Flags], eax; Flags
0x18000d014  lea     r8, ?NhpTimerCallbackRoutine@@YAXPEAXE@Z; Callback
0x18000d01b  mov     [rsp+58h+Period], eax; Period
0x18000d01f  mov     r9, rbx; Parameter
0x18000d022  mov     eax, [rsp+58h+arg_20]
0x18000d029  mov     rdx, rsi; phNewTimer
0x18000d02c  mov     [rsp+58h+DueTime], eax; DueTime
0x18000d030  call    cs:__imp_RtlCreateTimer
0x18000d036  mov     ebx, eax
0x18000d038  test    eax, eax
0x18000d03a  js      loc_18000D129
0x18000d040  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d047  call    cs:__imp_LeaveCriticalSection
0x18000d04d  test    ebx, ebx
0x18000d04f  js      loc_18000D1A6
0x18000d055  test    rdi, rdi
0x18000d058  jz      short loc_18000D060
0x18000d05a  mov     rax, [rsi]
0x18000d05d  mov     [rdi], rax
0x18000d060  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d067  cmp     rcx, r15
0x18000d06a  jnz     short loc_18000D087
0x18000d06c  mov     eax, ebx
0x18000d06e  mov     rbx, [rsp+58h+arg_0]
0x18000d073  mov     rbp, [rsp+58h+arg_8]
0x18000d078  mov     rsi, [rsp+58h+arg_10]
0x18000d07d  add     rsp, 40h
0x18000d081  pop     r15
0x18000d083  pop     r14
0x18000d085  pop     rdi
0x18000d086  retn
0x18000d087  test    byte ptr [rcx+1Ch], 8
0x18000d08b  jz      short loc_18000D06C
0x18000d08d  cmp     byte ptr [rcx+19h], 6
0x18000d091  jb      short loc_18000D06C
0x18000d093  mov     rcx, [rcx+10h]
0x18000d097  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000d09e  mov     edx, 16h
0x18000d0a3  mov     r9d, ebx
0x18000d0a6  call    WPP_SF_d
0x18000d0ab  jmp     short loc_18000D06C
0x18000d0ad  mov     rcx, rbp; lpCriticalSection
0x18000d0b0  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x18000d0b5  test    al, al
0x18000d0b7  jnz     loc_18000CFC0
0x18000d0bd  mov     eax, 0C0000001h
0x18000d0c2  jmp     short loc_18000D06E
0x18000d0c4  test    rbp, rbp
0x18000d0c7  jnz     short loc_18000D0F6
0x18000d0c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d0d0  cmp     rcx, r15
0x18000d0d3  jnz     short loc_18000D100
0x18000d0d5  mov     eax, 0C0000017h
0x18000d0da  jmp     short loc_18000D06E
0x18000d0dc  mov     rcx, [rcx+10h]
0x18000d0e0  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000d0e7  mov     edx, 12h
0x18000d0ec  call    WPP_SF_
0x18000d0f1  jmp     loc_18000CFB2
0x18000d0f6  mov     rcx, rbp; struct _COMPONENT_REFERENCE *
0x18000d0f9  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000d0fe  jmp     short loc_18000D0C9
0x18000d100  test    byte ptr [rcx+1Ch], 8
0x18000d104  jz      short loc_18000D0D5
0x18000d106  cmp     byte ptr [rcx+19h], 6
0x18000d10a  jb      short loc_18000D0D5
0x18000d10c  mov     rcx, [rcx+10h]
0x18000d110  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000d117  mov     edx, 13h
0x18000d11c  mov     r9d, 0C0000017h
0x18000d122  call    WPP_SF_d
0x18000d127  jmp     short loc_18000D0D5
0x18000d129  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d130  cmp     rcx, r15
0x18000d133  jz      loc_18000D040
0x18000d139  test    byte ptr [rcx+1Ch], 8
0x18000d13d  jz      loc_18000D040
0x18000d143  cmp     byte ptr [rcx+19h], 2
0x18000d147  jb      loc_18000D040
0x18000d14d  mov     rcx, [rcx+10h]
0x18000d151  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000d158  mov     edx, 14h
0x18000d15d  mov     r9d, ebx
0x18000d160  call    WPP_SF_d
0x18000d165  jmp     short loc_18000D199
0x18000d167  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d16e  cmp     rcx, r15
0x18000d171  jz      short loc_18000D194
0x18000d173  test    byte ptr [rcx+1Ch], 8
0x18000d177  jz      short loc_18000D194
0x18000d179  cmp     byte ptr [rcx+19h], 4
0x18000d17d  jb      short loc_18000D194
0x18000d17f  mov     rcx, [rcx+10h]
0x18000d183  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18000d18a  mov     edx, 15h
0x18000d18f  call    WPP_SF_
0x18000d194  mov     ebx, 0C0000001h
0x18000d199  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d1a0  call    cs:__imp_LeaveCriticalSection
0x18000d1a6  test    rbp, rbp
0x18000d1a9  jz      loc_18000D060
0x18000d1af  mov     rcx, rbp; struct _COMPONENT_REFERENCE *
0x18000d1b2  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x18000d1b7  jmp     loc_18000D060
```
