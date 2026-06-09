# NhpTimerCallbackRoutine(void *,uchar)

- ea: `0x1800333c0`
- end: `0x18003354f`
- name: `?NhpTimerCallbackRoutine@@YAXPEAXE@Z`
- size: `399`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x18000ca20`
- `0x1800333c0`
- `0x180033558`
- `0x180034098`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033480`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033480`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033494`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003343e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003343e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033474`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033474`
- `ntdll!RtlDeleteTimer` at `0x180033461`
- `ntdll!RtlDeleteTimer` at `0x180033461`

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
0x1800333c0  mov     [rsp+arg_0], rbx
0x1800333c5  mov     [rsp+arg_8], rsi
0x1800333ca  push    rdi
0x1800333cb  sub     rsp, 30h
0x1800333cf  movzx   edi, dl
0x1800333d2  mov     rbx, rcx
0x1800333d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333dc  lea     rsi, WPP_GLOBAL_Control
0x1800333e3  cmp     rcx, rsi
0x1800333e6  jz      short loc_180033427
0x1800333e8  test    byte ptr [rcx+1Ch], 8
0x1800333ec  jz      short loc_1800333F8
0x1800333ee  cmp     byte ptr [rcx+19h], 6
0x1800333f2  jnb     loc_1800334E0
0x1800333f8  cmp     rcx, rsi
0x1800333fb  jz      short loc_180033427
0x1800333fd  test    byte ptr [rcx+1Ch], 8
0x180033401  jz      short loc_180033427
0x180033403  cmp     byte ptr [rcx+19h], 4
0x180033407  jb      short loc_180033427
0x180033409  mov     rax, [rbx+8]
0x18003340d  mov     edx, 0Fh
0x180033412  mov     r9, [rbx]
0x180033415  mov     rcx, [rcx+10h]
0x180033419  mov     [rsp+38h+var_10], edi
0x18003341d  mov     [rsp+38h+var_18], rax
0x180033422  call    WPP_SF_qqD
0x180033427  mov     rcx, [rbx+8]
0x18003342b  movzx   edx, dil
0x18003342f  mov     rax, [rbx]
0x180033432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033437  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18003343e  call    cs:__imp_EnterCriticalSection
0x180033445  nop     dword ptr [rax+rax+00h]
0x18003344a  mov     rcx, cs:?NhpTimerQueueHandle@@3PEAXEA; TimerQueue
0x180033451  test    rcx, rcx
0x180033454  jz      loc_180033508
0x18003345a  mov     rdx, [rbx+10h]; Timer
0x18003345e  xor     r8d, r8d; CompletionEvent
0x180033461  call    cs:__imp_RtlDeleteTimer
0x180033468  nop     dword ptr [rax+rax+00h]
0x18003346d  lea     rcx, ?NhpTimerQueueLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033474  call    cs:__imp_LeaveCriticalSection
0x18003347b  nop     dword ptr [rax+rax+00h]
0x180033480  call    cs:__imp_GetProcessHeap
0x180033487  nop     dword ptr [rax+rax+00h]
0x18003348c  mov     r8, rbx; lpMem
0x18003348f  xor     edx, edx; dwFlags
0x180033491  mov     rcx, rax; hHeap
0x180033494  call    cs:__imp_HeapFree
0x18003349b  nop     dword ptr [rax+rax+00h]
0x1800334a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800334a7  cmp     rcx, rsi
0x1800334aa  jnz     short loc_1800334BD
0x1800334ac  mov     rbx, [rsp+38h+arg_0]
0x1800334b1  mov     rsi, [rsp+38h+arg_8]
0x1800334b6  add     rsp, 30h
0x1800334ba  pop     rdi
0x1800334bb  retn
0x1800334bd  test    byte ptr [rcx+1Ch], 8
0x1800334c1  jz      short loc_1800334AC
0x1800334c3  cmp     byte ptr [rcx+19h], 6
0x1800334c7  jb      short loc_1800334AC
0x1800334c9  mov     rcx, [rcx+10h]
0x1800334cd  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x1800334d4  mov     edx, 11h
0x1800334d9  call    WPP_SF_
0x1800334de  jmp     short loc_1800334AC
0x1800334e0  mov     rcx, [rcx+10h]
0x1800334e4  lea     r8, WPP_e9dd5aa48a2f3015263a53cfeeae5727_Traceguids
0x1800334eb  mov     edx, 0Eh
0x1800334f0  mov     dword ptr [rsp+38h+var_18], edi
0x1800334f4  mov     r9, rbx
0x1800334f7  call    WPP_SF_qD
0x1800334fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180033503  jmp     loc_1800333F8
0x180033508  mov     rcx, cs:WPP_GLOBAL_Control
0x18003350f  cmp     rcx, rsi
0x180033512  jz      loc_18003346D
0x180033518  test    byte ptr [rcx+1Ch], 8
0x18003351c  jz      loc_18003346D
0x180033522  cmp     byte ptr [rcx+19h], 3
0x180033526  jb      loc_18003346D
0x18003352c  mov     rax, [rbx+8]
0x180033530  mov     edx, 10h
0x180033535  mov     r9, [rbx]
0x180033538  mov     rcx, [rcx+10h]
0x18003353c  mov     [rsp+38h+var_10], edi
0x180033540  mov     [rsp+38h+var_18], rax
0x180033545  call    WPP_SF_qqD
0x18003354a  jmp     loc_18003346D
```
