# NhpTimerCallbackRoutine(void *,uchar)

- ea: `0x18002e9b0`
- end: `0x18002eb20`
- name: `?NhpTimerCallbackRoutine@@YAXPEAXE@Z`
- size: `368`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000c110`
- `0x18002e9b0`
- `0x18002eb28`
- `0x1800319e8`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ea5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ea5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ea6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ea6c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ea2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ea2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ea58`
- `ntdll!RtlDeleteTimer` at `0x18002ea4b`
- `ntdll!RtlDeleteTimer` at `0x18002ea4b`

## pseudocode

```c
void __fastcall NhpTimerCallbackRoutine(_QWORD *a1, unsigned __int8 a2, __int64 a3)
{
  int v3; // edi
  PVOID *v5; // rcx
  __int64 v6; // r8
  HANDLE ProcessHeap; // rax

  v3 = a2;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids, a1, a2);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_qqD(v5[2], 15, a3, *a1, a1[1], v3);
  }
  ((void (__fastcall *)(_QWORD, _QWORD))*a1)(a1[1], (unsigned __int8)v3);
  EnterCriticalSection(&NhpTimerQueueLock);
  if ( NhpTimerQueueHandle )
  {
    RtlDeleteTimer(NhpTimerQueueHandle, (HANDLE)a1[2], 0);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v6, *a1, a1[1], v3);
  }
  LeaveCriticalSection(&NhpTimerQueueLock);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids);
  }
}

```

## disassembly

```asm
0x18002e9b0  mov     [rsp+arg_0], rbx
0x18002e9b5  mov     [rsp+arg_8], rsi
0x18002e9ba  push    rdi
0x18002e9bb  sub     rsp, 30h
0x18002e9bf  movzx   edi, dl
0x18002e9c2  mov     rbx, rcx
0x18002e9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9cc  lea     rsi, WPP_GLOBAL_Control
0x18002e9d3  cmp     rcx, rsi
0x18002e9d6  jz      short loc_18002EA17
0x18002e9d8  test    byte ptr [rcx+1Ch], 8
0x18002e9dc  jz      short loc_18002E9E8
0x18002e9de  cmp     byte ptr [rcx+19h], 6
0x18002e9e2  jnb     loc_18002EAB1
0x18002e9e8  cmp     rcx, rsi
0x18002e9eb  jz      short loc_18002EA17
0x18002e9ed  test    byte ptr [rcx+1Ch], 8
0x18002e9f1  jz      short loc_18002EA17
0x18002e9f3  cmp     byte ptr [rcx+19h], 4
0x18002e9f7  jb      short loc_18002EA17
0x18002e9f9  mov     rax, [rbx+8]
0x18002e9fd  mov     edx, 0Fh
0x18002ea02  mov     r9, [rbx]
0x18002ea05  mov     rcx, [rcx+10h]
0x18002ea09  mov     [rsp+38h+var_10], edi
0x18002ea0d  mov     [rsp+38h+var_18], rax
0x18002ea12  call    WPP_SF_qqD
0x18002ea17  mov     rcx, [rbx+8]
0x18002ea1b  movzx   edx, dil
0x18002ea1f  mov     rax, [rbx]
0x18002ea22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea27  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ea2e  call    cs:__imp_EnterCriticalSection
0x18002ea34  mov     rcx, cs:?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x18002ea3b  test    rcx, rcx
0x18002ea3e  jz      loc_18002EAD9
0x18002ea44  mov     rdx, [rbx+10h]; Timer
0x18002ea48  xor     r8d, r8d; CompletionEvent
0x18002ea4b  call    cs:__imp_RtlDeleteTimer
0x18002ea51  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ea58  call    cs:__imp_LeaveCriticalSection
0x18002ea5e  call    cs:__imp_GetProcessHeap
0x18002ea64  mov     r8, rbx; lpMem
0x18002ea67  xor     edx, edx; dwFlags
0x18002ea69  mov     rcx, rax; hHeap
0x18002ea6c  call    cs:__imp_HeapFree
0x18002ea72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea79  cmp     rcx, rsi
0x18002ea7c  jnz     short loc_18002EA8E
0x18002ea7e  mov     rbx, [rsp+38h+arg_0]
0x18002ea83  mov     rsi, [rsp+38h+arg_8]
0x18002ea88  add     rsp, 30h
0x18002ea8c  pop     rdi
0x18002ea8d  retn
0x18002ea8e  test    byte ptr [rcx+1Ch], 8
0x18002ea92  jz      short loc_18002EA7E
0x18002ea94  cmp     byte ptr [rcx+19h], 6
0x18002ea98  jb      short loc_18002EA7E
0x18002ea9a  mov     rcx, [rcx+10h]
0x18002ea9e  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18002eaa5  mov     edx, 11h
0x18002eaaa  call    WPP_SF_
0x18002eaaf  jmp     short loc_18002EA7E
0x18002eab1  mov     rcx, [rcx+10h]
0x18002eab5  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x18002eabc  mov     edx, 0Eh
0x18002eac1  mov     dword ptr [rsp+38h+var_18], edi
0x18002eac5  mov     r9, rbx
0x18002eac8  call    WPP_SF_qD
0x18002eacd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ead4  jmp     loc_18002E9E8
0x18002ead9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eae0  cmp     rcx, rsi
0x18002eae3  jz      loc_18002EA51
0x18002eae9  test    byte ptr [rcx+1Ch], 8
0x18002eaed  jz      loc_18002EA51
0x18002eaf3  cmp     byte ptr [rcx+19h], 3
0x18002eaf7  jb      loc_18002EA51
0x18002eafd  mov     rax, [rbx+8]
0x18002eb01  mov     edx, 10h
0x18002eb06  mov     r9, [rbx]
0x18002eb09  mov     rcx, [rcx+10h]
0x18002eb0d  mov     [rsp+38h+var_10], edi
0x18002eb11  mov     [rsp+38h+var_18], rax
0x18002eb16  call    WPP_SF_qqD
0x18002eb1b  jmp     loc_18002EA51
```
