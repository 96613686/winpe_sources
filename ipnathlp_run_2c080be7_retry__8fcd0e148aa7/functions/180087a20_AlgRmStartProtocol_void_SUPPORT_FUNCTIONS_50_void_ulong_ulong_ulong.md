# AlgRmStartProtocol(void *,_SUPPORT_FUNCTIONS_50 *,void *,ulong,ulong,ulong)

- ea: `0x180087a20`
- end: `0x180087c8d`
- name: `?AlgRmStartProtocol@@YAKPEAXPEAU_SUPPORT_FUNCTIONS_50@@0KKK@Z`
- size: `621`
- prototype: `unsigned int __fastcall(void *, struct _SUPPORT_FUNCTIONS_50 *, void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000c1e0`
- `0x18000c3c0`
- `0x18000ca20`
- `0x18000d090`
- `0x18003477c`
- `0x180052bf4`
- `0x180087a20`
- `0x180087f34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087ad0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180087ad0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087ae9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180087ae9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087ac4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180087ac4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180087c3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087bfb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180087be3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x180087be3`

## pseudocode

```c
__int64 __fastcall AlgRmStartProtocol(void *a1, struct _SUPPORT_FUNCTIONS_50 *a2, _QWORD *a3)
{
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
  if ( !AcquireComponentReference(&AlgComponentReference) )
    return 1003;
  if ( a3 )
  {
    EnterCriticalSection(&AlgGlobalInfoLock);
    ProcessHeap = GetProcessHeap();
    v7 = 8;
    AlgGlobalInfo = HeapAlloc(ProcessHeap, 8u, 8u);
    if ( !AlgGlobalInfo )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
      }
      goto LABEL_33;
    }
    *(_QWORD *)AlgGlobalInfo = *a3;
    AlgNotificationEvent = a1;
    if ( a2 )
      AlgSupportFunctions = *a2;
    else
      memset_0(&AlgSupportFunctions, 0, sizeof(AlgSupportFunctions));
    LastError = NatOpenDriver(&AlgTranslatorHandle);
    v7 = LastError;
    if ( LastError )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 34;
LABEL_26:
        WPP_SF_d(v10[2], v11, WPP_98163cc445f73b00785e759405df1b1d_Traceguids, LastError);
      }
    }
    else
    {
      AlgTimerQueueHandle = CreateTimerQueue();
      if ( AlgTimerQueueHandle )
      {
        Initialise_ALG();
        _InterlockedExchange((volatile __int32 *)&AlgProtocolStopped, 0);
        goto LABEL_33;
      }
      LastError = GetLastError();
      v7 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 35;
        goto LABEL_26;
      }
    }
LABEL_33:
    LeaveCriticalSection(&AlgGlobalInfoLock);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
    }
    goto LABEL_37;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_98163cc445f73b00785e759405df1b1d_Traceguids);
  }
  v7 = 87;
LABEL_37:
  ReleaseComponentReference((struct _COMPONENT_REFERENCE *)&AlgComponentReference);
  return v7;
}

```

## disassembly

```asm
0x180087a20  push    rbx
0x180087a22  push    rbp
0x180087a23  push    rsi
0x180087a24  push    rdi
0x180087a25  push    r12
0x180087a27  push    r15
0x180087a29  sub     rsp, 28h
0x180087a2d  mov     rsi, r8
0x180087a30  mov     rdi, rdx
0x180087a33  mov     rbp, rcx
0x180087a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a3d  lea     r15, WPP_GLOBAL_Control
0x180087a44  lea     r12, WPP_98163cc445f73b00785e759405df1b1d_Traceguids
0x180087a4b  cmp     rcx, r15
0x180087a4e  jz      short loc_180087A6D
0x180087a50  test    byte ptr [rcx+1Ch], 1
0x180087a54  jz      short loc_180087A6D
0x180087a56  cmp     byte ptr [rcx+19h], 6
0x180087a5a  jb      short loc_180087A6D
0x180087a5c  mov     rcx, [rcx+10h]
0x180087a60  mov     edx, 1Fh
0x180087a65  mov     r8, r12
0x180087a68  call    WPP_SF_
0x180087a6d  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; lpCriticalSection
0x180087a74  call    ?AcquireComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; AcquireComponentReference(_COMPONENT_REFERENCE *)
0x180087a79  test    al, al
0x180087a7b  jnz     short loc_180087A87
0x180087a7d  mov     eax, 3EBh
0x180087a82  jmp     loc_180087C7F
0x180087a87  test    rsi, rsi
0x180087a8a  jnz     short loc_180087ABD
0x180087a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a93  cmp     rcx, r15
0x180087a96  jz      short loc_180087AB3
0x180087a98  test    byte ptr [rcx+1Ch], 1
0x180087a9c  jz      short loc_180087AB3
0x180087a9e  cmp     byte ptr [rcx+19h], 6
0x180087aa2  jb      short loc_180087AB3
0x180087aa4  mov     rcx, [rcx+10h]
0x180087aa8  lea     edx, [rsi+20h]
0x180087aab  mov     r8, r12
0x180087aae  call    WPP_SF_
0x180087ab3  mov     ebx, 57h ; 'W'
0x180087ab8  jmp     loc_180087C71
0x180087abd  lea     rcx, ?AlgGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180087ac4  call    cs:__imp_EnterCriticalSection
0x180087acb  nop     dword ptr [rax+rax+00h]
0x180087ad0  call    cs:__imp_GetProcessHeap
0x180087ad7  nop     dword ptr [rax+rax+00h]
0x180087adc  mov     ebx, 8
0x180087ae1  mov     rcx, rax; hHeap
0x180087ae4  mov     r8d, ebx; dwBytes
0x180087ae7  mov     edx, ebx; dwFlags
0x180087ae9  call    cs:__imp_HeapAlloc
0x180087af0  nop     dword ptr [rax+rax+00h]
0x180087af5  mov     cs:?AlgGlobalInfo@@3PEAUIP_ALG_GLOBAL_INFO@@EA, rax; IP_ALG_GLOBAL_INFO * AlgGlobalInfo
0x180087afc  mov     rcx, rax
0x180087aff  test    rax, rax
0x180087b02  jnz     short loc_180087B3C
0x180087b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b0b  cmp     rcx, r15
0x180087b0e  jz      loc_180087C35
0x180087b14  test    byte ptr [rcx+1Ch], 1
0x180087b18  jz      loc_180087C35
0x180087b1e  cmp     byte ptr [rcx+19h], 2
0x180087b22  jb      loc_180087C35
0x180087b28  mov     rcx, [rcx+10h]
0x180087b2c  lea     edx, [rbx+19h]
0x180087b2f  mov     r8, r12
0x180087b32  call    WPP_SF_
0x180087b37  jmp     loc_180087C35
0x180087b3c  mov     rax, [rsi]
0x180087b3f  mov     [rcx], rax
0x180087b42  mov     cs:?AlgNotificationEvent@@3PEAXEA, rbp; void * AlgNotificationEvent
0x180087b49  test    rdi, rdi
0x180087b4c  jnz     short loc_180087B62
0x180087b4e  xor     edx, edx; Val
0x180087b50  lea     r8d, [rdi+60h]; Size
0x180087b54  lea     rcx, ?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A; void *
0x180087b5b  call    memset_0
0x180087b60  jmp     short loc_180087BA3
0x180087b62  movups  xmm0, xmmword ptr [rdi]
0x180087b65  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087b6c  movups  xmm1, xmmword ptr [rdi+10h]
0x180087b70  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+10h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087b77  movups  xmm0, xmmword ptr [rdi+20h]
0x180087b7b  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+20h, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087b82  movups  xmm1, xmmword ptr [rdi+30h]
0x180087b86  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+30h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087b8d  movups  xmm0, xmmword ptr [rdi+40h]
0x180087b91  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+40h, xmm0; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087b98  movups  xmm1, xmmword ptr [rdi+50h]
0x180087b9c  movaps  xmmword ptr cs:?AlgSupportFunctions@@3U_SUPPORT_FUNCTIONS_50@@A+50h, xmm1; _SUPPORT_FUNCTIONS_50 AlgSupportFunctions
0x180087ba3  lea     rcx, ?AlgTranslatorHandle@@3PEAXEA; FileHandle
0x180087baa  call    NatOpenDriver
0x180087baf  mov     ebx, eax
0x180087bb1  test    eax, eax
0x180087bb3  jz      short loc_180087BE3
0x180087bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180087bbc  cmp     rcx, r15
0x180087bbf  jz      short loc_180087C35
0x180087bc1  test    byte ptr [rcx+1Ch], 1
0x180087bc5  jz      short loc_180087C35
0x180087bc7  cmp     byte ptr [rcx+19h], 2
0x180087bcb  jb      short loc_180087C35
0x180087bcd  mov     edx, 22h ; '"'
0x180087bd2  mov     rcx, [rcx+10h]
0x180087bd6  mov     r9d, eax
0x180087bd9  mov     r8, r12
0x180087bdc  call    WPP_SF_d
0x180087be1  jmp     short loc_180087C35
0x180087be3  call    cs:__imp_CreateTimerQueue
0x180087bea  nop     dword ptr [rax+rax+00h]
0x180087bef  mov     cs:?AlgTimerQueueHandle@@3PEAXEA, rax; void * AlgTimerQueueHandle
0x180087bf6  test    rax, rax
0x180087bf9  jnz     short loc_180087C28
0x180087bfb  call    cs:__imp_GetLastError
0x180087c02  nop     dword ptr [rax+rax+00h]
0x180087c07  mov     ebx, eax
0x180087c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180087c10  cmp     rcx, r15
0x180087c13  jz      short loc_180087C35
0x180087c15  test    byte ptr [rcx+1Ch], 1
0x180087c19  jz      short loc_180087C35
0x180087c1b  cmp     byte ptr [rcx+19h], 2
0x180087c1f  jb      short loc_180087C35
0x180087c21  mov     edx, 23h ; '#'
0x180087c26  jmp     short loc_180087BD2
0x180087c28  call    ?Initialise_ALG@@YAJXZ; Initialise_ALG(void)
0x180087c2d  xor     eax, eax
0x180087c2f  xchg    eax, cs:?AlgProtocolStopped@@3KA; ulong AlgProtocolStopped
0x180087c35  lea     rcx, ?AlgGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180087c3c  call    cs:__imp_LeaveCriticalSection
0x180087c43  nop     dword ptr [rax+rax+00h]
0x180087c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180087c4f  cmp     rcx, r15
0x180087c52  jz      short loc_180087C71
0x180087c54  test    byte ptr [rcx+1Ch], 1
0x180087c58  jz      short loc_180087C71
0x180087c5a  cmp     byte ptr [rcx+19h], 6
0x180087c5e  jb      short loc_180087C71
0x180087c60  mov     rcx, [rcx+10h]
0x180087c64  mov     edx, 24h ; '$'
0x180087c69  mov     r8, r12
0x180087c6c  call    WPP_SF_
0x180087c71  lea     rcx, ?AlgComponentReference@@3U_COMPONENT_REFERENCE@@A; struct _COMPONENT_REFERENCE *
0x180087c78  call    ?ReleaseComponentReference@@YAEPEAU_COMPONENT_REFERENCE@@@Z; ReleaseComponentReference(_COMPONENT_REFERENCE *)
0x180087c7d  mov     eax, ebx
0x180087c7f  add     rsp, 28h
0x180087c83  pop     r15
0x180087c85  pop     r12
0x180087c87  pop     rdi
0x180087c88  pop     rsi
0x180087c89  pop     rbp
0x180087c8a  pop     rbx
0x180087c8b  retn
```
