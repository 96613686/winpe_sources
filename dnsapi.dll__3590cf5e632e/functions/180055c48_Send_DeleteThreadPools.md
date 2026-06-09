# Send_DeleteThreadPools

- ea: `0x180055c48`
- end: `0x180055e2e`
- name: `Send_DeleteThreadPools`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180053d88`

## callees

- `0x18002b050`
- `0x18005049c`
- `0x180055c48`
- `0x180055e34`
- `0x180083954`
- `0x1800ddfa8`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055c75`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180055c75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055c8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055c8a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180055d0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180055d0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180055d5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180055d5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180055cfe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolIoCallbacks` at `0x180055cfe`

## pseudocode

```c
void __fastcall Send_DeleteThreadPools(__int64 a1)
{
  int v2; // ebp
  struct _TP_IO *v3; // rax
  PTP_IO *v4; // rbx
  __int64 v5; // r14
  int v6; // ebp
  struct _TP_IO *v7; // rcx
  struct _TP_IO *v8; // rbx
  void *v9; // rcx
  struct _TP_TIMER *v10; // rbx
  void *v11; // rcx
  void *v12; // rcx

  if ( a1 )
  {
    Send_SetRunState();
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 528));
    v2 = *(_DWORD *)(a1 + 520);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 528));
    v3 = *(struct _TP_IO **)(a1 + 496);
    v4 = (PTP_IO *)(a1 + 464);
    v5 = *(_QWORD *)(a1 + 456);
    v6 = v2 & 0x20;
    if ( v3 && (v3 == *v4 || v3 == *(struct _TP_IO **)(a1 + 480)) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v7 = *(struct _TP_IO **)(a1 + 496);
    if ( v7 )
    {
      ThreadPool_DeleteIo(v7);
      v11 = *(void **)(a1 + 504);
      *(_QWORD *)(a1 + 496) = 0;
      DnsApiFree(v11);
      *(_QWORD *)(a1 + 504) = 0;
    }
    if ( *v4 )
    {
      ThreadPool_DeleteIo(*v4);
      v12 = *(void **)(a1 + 472);
      *v4 = 0;
      DnsApiFree(v12);
      *(_QWORD *)(a1 + 472) = 0;
    }
    v8 = *(struct _TP_IO **)(a1 + 480);
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_qD(1035, 18, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, v8, v6 == 0);
      if ( !v6 )
        WaitForThreadpoolIoCallbacks(v8, 0);
      CloseThreadpoolIo(v8);
      v9 = *(void **)(a1 + 488);
      *(_QWORD *)(a1 + 480) = 0;
      DnsApiFree(v9);
      *(_QWORD *)(a1 + 488) = 0;
    }
    v10 = *(struct _TP_TIMER **)(a1 + 512);
    if ( v10 && !v5 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_q(1035, 22, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, *(_QWORD *)(a1 + 512));
      WaitForThreadpoolTimerCallbacks(v10, 1);
    }
  }
}

```

## disassembly

```asm
0x180055c48  test    rcx, rcx
0x180055c4b  jz      locret_180055D7B
0x180055c51  mov     [rsp+arg_8], rbx
0x180055c56  mov     [rsp+arg_10], rbp
0x180055c5b  push    rsi
0x180055c5c  push    rdi
0x180055c5d  push    r14
0x180055c5f  sub     rsp, 30h
0x180055c63  mov     rdi, rcx
0x180055c66  call    Send_SetRunState
0x180055c6b  lea     rbx, [rdi+210h]
0x180055c72  mov     rcx, rbx; lpCriticalSection
0x180055c75  call    cs:__imp_EnterCriticalSection
0x180055c7c  nop     dword ptr [rax+rax+00h]
0x180055c81  mov     ebp, [rdi+208h]
0x180055c87  mov     rcx, rbx; lpCriticalSection
0x180055c8a  call    cs:__imp_LeaveCriticalSection
0x180055c91  nop     dword ptr [rax+rax+00h]
0x180055c96  mov     rax, [rdi+1F0h]
0x180055c9d  lea     rbx, [rdi+1D0h]
0x180055ca4  mov     r14, [rdi+1C8h]
0x180055cab  and     ebp, 20h
0x180055cae  mov     esi, 0
0x180055cb3  setz    sil
0x180055cb7  test    rax, rax
0x180055cba  jnz     loc_180055DBA
0x180055cc0  mov     rcx, [rdi+1F0h]; pio
0x180055cc7  test    rcx, rcx
0x180055cca  jnz     loc_180055DD6
0x180055cd0  mov     rcx, [rbx]; pio
0x180055cd3  test    rcx, rcx
0x180055cd6  jnz     loc_180055E04
0x180055cdc  mov     rbx, [rdi+1E0h]
0x180055ce3  test    rbx, rbx
0x180055ce6  jz      short loc_180055D3B
0x180055ce8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180055cef  jnz     loc_180055D7D
0x180055cf5  test    ebp, ebp
0x180055cf7  jnz     short loc_180055D0A
0x180055cf9  xor     edx, edx; fCancelPendingCallbacks
0x180055cfb  mov     rcx, rbx; pio
0x180055cfe  call    cs:__imp_WaitForThreadpoolIoCallbacks
0x180055d05  nop     dword ptr [rax+rax+00h]
0x180055d0a  mov     rcx, rbx; pio
0x180055d0d  call    cs:__imp_CloseThreadpoolIo
0x180055d14  nop     dword ptr [rax+rax+00h]
0x180055d19  mov     rcx, [rdi+1E8h]; lpMem
0x180055d20  mov     qword ptr [rdi+1E0h], 0
0x180055d2b  call    DnsApiFree
0x180055d30  mov     qword ptr [rdi+1E8h], 0
0x180055d3b  mov     rbx, [rdi+200h]
0x180055d42  test    rbx, rbx
0x180055d45  jz      short loc_180055D69
0x180055d47  test    r14, r14
0x180055d4a  jnz     short loc_180055D69
0x180055d4c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180055d53  jnz     short loc_180055D9F
0x180055d55  mov     edx, 1; fCancelPendingCallbacks
0x180055d5a  mov     rcx, rbx; pti
0x180055d5d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180055d64  nop     dword ptr [rax+rax+00h]
0x180055d69  mov     rbx, [rsp+48h+arg_8]
0x180055d6e  mov     rbp, [rsp+48h+arg_10]
0x180055d73  add     rsp, 30h
0x180055d77  pop     r14
0x180055d79  pop     rdi
0x180055d7a  pop     rsi
0x180055d7b  retn
0x180055d7d  mov     edx, 12h
0x180055d82  mov     [rsp+48h+var_28], esi
0x180055d86  mov     ecx, 40Bh
0x180055d8b  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180055d92  mov     r9, rbx
0x180055d95  call    WPP_SF_qD
0x180055d9a  jmp     loc_180055CF5
0x180055d9f  mov     edx, 16h
0x180055da4  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180055dab  mov     ecx, 40Bh
0x180055db0  mov     r9, rbx
0x180055db3  call    WPP_SF_q
0x180055db8  jmp     short loc_180055D55
0x180055dba  cmp     rax, [rbx]
0x180055dbd  jz      short loc_180055DCC
0x180055dbf  cmp     rax, [rdi+1E0h]
0x180055dc6  jnz     loc_180055CC0
0x180055dcc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180055dd1  jmp     loc_180055CC0
0x180055dd6  mov     edx, esi
0x180055dd8  call    ThreadPool_DeleteIo
0x180055ddd  mov     rcx, [rdi+1F8h]; lpMem
0x180055de4  mov     qword ptr [rdi+1F0h], 0
0x180055def  call    DnsApiFree
0x180055df4  mov     qword ptr [rdi+1F8h], 0
0x180055dff  jmp     loc_180055CD0
0x180055e04  mov     edx, esi
0x180055e06  call    ThreadPool_DeleteIo
0x180055e0b  mov     rcx, [rdi+1D8h]; lpMem
0x180055e12  mov     qword ptr [rbx], 0
0x180055e19  call    DnsApiFree
0x180055e1e  mov     qword ptr [rdi+1D8h], 0
0x180055e29  jmp     loc_180055CDC
```
