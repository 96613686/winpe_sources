# THREAD_MANAGER::RequestThread(ulong (*)(void *),void *)

- ea: `0x18002144c`
- end: `0x1800215f2`
- name: `?RequestThread@THREAD_MANAGER@@QEAAXP6AKPEAX@Z0@Z`
- size: `422`
- prototype: `void __fastcall(PVOID Parameter, unsigned int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800220d0`

## callees

- `0x180001210`
- `0x180001250`
- `0x180020a64`
- `0x180020ba8`
- `0x18002144c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800214cf`
- `KERNEL32!GetTickCount` at `0x1800214cf`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800215b7`
- `KERNEL32!CreateTimerQueueTimer` at `0x1800215b7`
- `KERNEL32!LeaveCriticalSection` at `0x1800215e1`
- `KERNEL32!LeaveCriticalSection` at `0x1800215e1`
- `KERNEL32!EnterCriticalSection` at `0x180021478`
- `KERNEL32!EnterCriticalSection` at `0x180021478`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180021587`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180021587`
- `iisutil!PuDbgPrint` at `0x1800214c9`
- `iisutil!PuDbgPrint` at `0x1800214c9`

## string_xrefs

- `0x1800214a9`: `W3TP: Thread Request received\n`
- `0x1800214b0`: `THREAD_MANAGER::RequestThread`
- `0x1800214c2`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3tp\thread_manager.cxx`

## pseudocode

```c
void __fastcall THREAD_MANAGER::RequestThread(char *Parameter, unsigned int (*a2)(void *), void *a3)
{
  bool v5; // zf
  DWORD TickCount; // esi
  _QWORD *v7; // rax
  void *v8; // rdx
  _DWORD *v9; // rcx

  if ( !*((_QWORD *)Parameter + 6) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    if ( !*((_QWORD *)Parameter + 6) )
    {
      v5 = (g_dwDebugFlags & 3) == 0;
      *((_DWORD *)Parameter + 13) = 1;
      if ( !v5 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3tp\\thread_manager.cxx",
          955,
          "THREAD_MANAGER::RequestThread",
          "W3TP: Thread Request received\n");
      TickCount = GetTickCount();
      if ( !(unsigned int)GetContextSwitchCount((unsigned int *)Parameter + 18)
        || *(_DWORD *)(*((_QWORD *)Parameter + 14) + 68LL) != -1
        && (int)GetProcessorInformation(
                  (union _LARGE_INTEGER *)Parameter + 16,
                  (union _LARGE_INTEGER *)Parameter + 15,
                  g_dwNumProcs) < 0 )
      {
        goto LABEL_15;
      }
      v7 = operator new(0x30u);
      if ( v7 )
      {
        *(_DWORD *)v7 = 1380012116;
        v7[1] = 0;
        v7[2] = 0;
        v7[3] = 0;
        v7[4] = 0;
        *((_DWORD *)v7 + 10) = 0;
      }
      else
      {
        v7 = 0;
      }
      *((_QWORD *)Parameter + 8) = v7;
      if ( !v7 )
        goto LABEL_15;
      v7[1] = THREAD_POOL_DATA::ThreadPoolThread;
      *(_QWORD *)(*((_QWORD *)Parameter + 8) + 16LL) = a3;
      *(_QWORD *)(*((_QWORD *)Parameter + 8) + 24LL) = Parameter;
      *(_DWORD *)(*((_QWORD *)Parameter + 8) + 32LL) = TickCount;
      *(_DWORD *)(*((_QWORD *)Parameter + 8) + 36LL) = 1;
      v8 = (void *)*((_QWORD *)Parameter + 7);
      if ( v8 )
      {
        DeleteTimerQueueTimer(0, v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        *((_QWORD *)Parameter + 7) = 0;
      }
      if ( !CreateTimerQueueTimer(
              (PHANDLE)Parameter + 7,
              0,
              (WAITORTIMERCALLBACK)THREAD_MANAGER::ControlTimerCallback,
              Parameter,
              *(_DWORD *)(*((_QWORD *)Parameter + 14) + 80LL),
              0,
              8u) )
      {
LABEL_15:
        v9 = (_DWORD *)*((_QWORD *)Parameter + 8);
        if ( v9 )
        {
          *v9 = 2017546324;
          operator delete(v9);
        }
        *((_QWORD *)Parameter + 8) = 0;
        *((_DWORD *)Parameter + 13) = 0;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  }
}

```

## disassembly

```asm
0x18002144c  push    rbx
0x18002144e  push    rbp
0x18002144f  push    rsi
0x180021450  push    rdi
0x180021451  push    r14
0x180021453  sub     rsp, 40h
0x180021457  xor     r14d, r14d
0x18002145a  mov     rbp, r8
0x18002145d  mov     rbx, rcx
0x180021460  cmp     [rcx+30h], r14d
0x180021464  jnz     loc_1800215E7
0x18002146a  cmp     [rcx+34h], r14d
0x18002146e  jnz     loc_1800215E7
0x180021474  add     rcx, 8; lpCriticalSection
0x180021478  call    cs:__imp_EnterCriticalSection
0x18002147e  cmp     [rbx+30h], r14d
0x180021482  jnz     loc_1800215DD
0x180021488  cmp     [rbx+34h], r14d
0x18002148c  jnz     loc_1800215DD
0x180021492  test    byte ptr cs:g_dwDebugFlags, 3
0x180021499  mov     dword ptr [rbx+34h], 1
0x1800214a0  jz      short loc_1800214CF
0x1800214a2  mov     rcx, cs:g_pDebug
0x1800214a9  lea     rax, aW3tpThreadRequ; "W3TP: Thread Request received\n"
0x1800214b0  lea     r9, aThreadManagerR_0; "THREAD_MANAGER::RequestThread"
0x1800214b7  mov     qword ptr [rsp+68h+DueTime], rax
0x1800214bc  mov     r8d, 3BBh
0x1800214c2  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800214c9  call    cs:__imp_PuDbgPrint
0x1800214cf  call    cs:__imp_GetTickCount
0x1800214d5  lea     rcx, [rbx+48h]; unsigned int *
0x1800214d9  mov     esi, eax
0x1800214db  call    ?GetContextSwitchCount@@YAHPEAK@Z; GetContextSwitchCount(ulong *)
0x1800214e0  test    eax, eax
0x1800214e2  jz      loc_1800215C1
0x1800214e8  mov     rcx, [rbx+70h]
0x1800214ec  cmp     dword ptr [rcx+44h], 0FFFFFFFFh
0x1800214f0  jz      short loc_180021511
0x1800214f2  mov     r8d, cs:?g_dwNumProcs@@3KA; unsigned int
0x1800214f9  lea     rdx, [rbx+78h]; union _LARGE_INTEGER *
0x1800214fd  lea     rcx, [rbx+80h]; union _LARGE_INTEGER *
0x180021504  call    ?GetProcessorInformation@@YAJPEAT_LARGE_INTEGER@@0K@Z; GetProcessorInformation(_LARGE_INTEGER *,_LARGE_INTEGER *,ulong)
0x180021509  test    eax, eax
0x18002150b  js      loc_1800215C1
0x180021511  mov     ecx, 30h ; '0'; Size
0x180021516  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002151b  test    rax, rax
0x18002151e  jz      short loc_18002153C
0x180021520  mov     dword ptr [rax], 52415054h
0x180021526  mov     [rax+8], r14
0x18002152a  mov     [rax+10h], r14
0x18002152e  mov     [rax+18h], r14
0x180021532  mov     [rax+20h], r14
0x180021536  mov     [rax+28h], r14d
0x18002153a  jmp     short loc_18002153F
0x18002153c  mov     rax, r14
0x18002153f  mov     [rbx+40h], rax
0x180021543  test    rax, rax
0x180021546  jz      short loc_1800215C1
0x180021548  lea     rcx, ?ThreadPoolThread@THREAD_POOL_DATA@@SAKPEAX@Z; THREAD_POOL_DATA::ThreadPoolThread(void *)
0x18002154f  mov     [rax+8], rcx
0x180021553  mov     rax, [rbx+40h]
0x180021557  mov     [rax+10h], rbp
0x18002155b  mov     rax, [rbx+40h]
0x18002155f  mov     [rax+18h], rbx
0x180021563  mov     rax, [rbx+40h]
0x180021567  mov     [rax+20h], esi
0x18002156a  lea     rsi, [rbx+38h]
0x18002156e  mov     rax, [rbx+40h]
0x180021572  mov     dword ptr [rax+24h], 1
0x180021579  mov     rdx, [rsi]; Timer
0x18002157c  test    rdx, rdx
0x18002157f  jz      short loc_180021590
0x180021581  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180021585  xor     ecx, ecx; TimerQueue
0x180021587  call    cs:__imp_DeleteTimerQueueTimer
0x18002158d  mov     [rsi], r14
0x180021590  mov     rax, [rbx+70h]
0x180021594  lea     r8, ?ControlTimerCallback@THREAD_MANAGER@@CAXPEAXE@Z; Callback
0x18002159b  mov     [rsp+68h+Flags], 8; Flags
0x1800215a3  mov     r9, rbx; Parameter
0x1800215a6  mov     [rsp+68h+Period], r14d; Period
0x1800215ab  xor     edx, edx; TimerQueue
0x1800215ad  mov     rcx, rsi; phNewTimer
0x1800215b0  mov     eax, [rax+50h]
0x1800215b3  mov     [rsp+68h+DueTime], eax; DueTime
0x1800215b7  call    cs:__imp_CreateTimerQueueTimer
0x1800215bd  test    eax, eax
0x1800215bf  jnz     short loc_1800215DD
0x1800215c1  mov     rcx, [rbx+40h]; Block
0x1800215c5  test    rcx, rcx
0x1800215c8  jz      short loc_1800215D5
0x1800215ca  mov     dword ptr [rcx], 78415054h
0x1800215d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800215d5  mov     [rbx+40h], r14
0x1800215d9  mov     [rbx+34h], r14d
0x1800215dd  lea     rcx, [rbx+8]; lpCriticalSection
0x1800215e1  call    cs:__imp_LeaveCriticalSection
0x1800215e7  add     rsp, 40h
0x1800215eb  pop     r14
0x1800215ed  pop     rdi
0x1800215ee  pop     rsi
0x1800215ef  pop     rbp
0x1800215f0  pop     rbx
0x1800215f1  retn
```
