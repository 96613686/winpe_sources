# CscService_DoWorkOnServiceMainThread(long (*)(void *),void *)

- ea: `0x180025e4c`
- end: `0x180025fa7`
- name: `?CscService_DoWorkOnServiceMainThread@@YAJP6AJPEAX@Z0@Z`
- size: `347`
- prototype: `__int64 __fastcall(int (*)(void *), void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180055b70`

## callees

- `0x180025e4c`
- `0x18002f10c`
- `0x18003e928`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025f79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025f8f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025f8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e8f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025f69`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025f69`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025e68`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025ec1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025ec1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e7b`
- `USER32!PostThreadMessageW` at `0x180025f02`
- `USER32!PostThreadMessageW` at `0x180025f02`

## pseudocode

```c
__int64 __fastcall CscService_DoWorkOnServiceMainThread(__int64 (__fastcall *a1)(LPARAM), LPARAM a2)
{
  int v4; // ebx
  signed int LastError; // ebx
  bool v7; // sf
  signed int v8; // eax
  LPARAM lParam[2]; // [rsp+30h] [rbp-28h] BYREF
  HANDLE hHandle[3]; // [rsp+40h] [rbp-18h]

  EnterCriticalSection(&g_csDone);
  v4 = g_bDone;
  LeaveCriticalSection(&g_csDone);
  if ( v4 )
    return (unsigned int)-2147023834;
  if ( GetCurrentThreadId() == g_idServiceMainThread )
    return (unsigned int)a1(a2);
  *(_OWORD *)lParam = 0;
  hHandle[0] = 0;
  hHandle[1] = CreateEventW(0, 0, 0, 0);
  if ( !hHandle[1] )
    return (unsigned int)ResultFromLastError();
  lParam[0] = (LPARAM)a1;
  lParam[1] = a2;
  LODWORD(hHandle[0]) = 0;
  if ( PostThreadMessageW(g_idServiceMainThread, 0xD26u, 0, (LPARAM)lParam) )
    goto LABEL_23;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
      (unsigned int)LastError,
      g_idServiceMainThread);
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError < 0;
  }
  if ( !v7 )
  {
LABEL_23:
    if ( WaitForSingleObject(hHandle[1], 0xFFFFFFFF) )
    {
      v8 = GetLastError();
      LastError = v8;
      if ( v8 > 0 )
        LastError = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      LastError = (signed int)hHandle[0];
    }
  }
  CloseHandle(hHandle[1]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180025e4c  mov     [rsp+arg_0], rbx
0x180025e51  mov     [rsp+arg_8], rsi
0x180025e56  push    rdi
0x180025e57  sub     rsp, 50h
0x180025e5b  mov     rsi, rcx
0x180025e5e  mov     rdi, rdx
0x180025e61  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180025e68  call    cs:__imp_EnterCriticalSection
0x180025e6e  mov     ebx, cs:?g_bDone@@3HA; int g_bDone
0x180025e74  lea     rcx, ?g_csDone@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180025e7b  call    cs:__imp_LeaveCriticalSection
0x180025e81  test    ebx, ebx
0x180025e83  jz      short loc_180025E8F
0x180025e85  mov     ebx, 80070426h
0x180025e8a  jmp     loc_180025F95
0x180025e8f  call    cs:__imp_GetCurrentThreadId
0x180025e95  cmp     eax, cs:?g_idServiceMainThread@@3KA; ulong g_idServiceMainThread
0x180025e9b  jnz     short loc_180025EAA
0x180025e9d  mov     rcx, rdi
0x180025ea0  mov     rax, rsi
0x180025ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ea8  jmp     short loc_180025ED6
0x180025eaa  xorps   xmm0, xmm0
0x180025ead  xor     r9d, r9d; lpName
0x180025eb0  xor     r8d, r8d; bInitialState
0x180025eb3  xor     edx, edx; bManualReset
0x180025eb5  xor     ecx, ecx; lpEventAttributes
0x180025eb7  movups  xmmword ptr [rsp+58h+lParam], xmm0
0x180025ebc  movups  xmmword ptr [rsp+58h+hHandle], xmm0
0x180025ec1  call    cs:__imp_CreateEventW
0x180025ec7  mov     [rsp+58h+hHandle+8], rax
0x180025ecc  test    rax, rax
0x180025ecf  jnz     short loc_180025EDD
0x180025ed1  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180025ed6  mov     ebx, eax
0x180025ed8  jmp     loc_180025F95
0x180025edd  mov     ecx, cs:?g_idServiceMainThread@@3KA; idThread
0x180025ee3  lea     r9, [rsp+58h+lParam]; lParam
0x180025ee8  xor     r8d, r8d; wParam
0x180025eeb  mov     [rsp+58h+lParam], rsi
0x180025ef0  mov     edx, 0D26h; Msg
0x180025ef5  mov     [rsp+58h+lParam+8], rdi
0x180025efa  mov     dword ptr [rsp+58h+hHandle], 0
0x180025f02  call    cs:__imp_PostThreadMessageW
0x180025f08  mov     edi, 80070000h
0x180025f0d  test    eax, eax
0x180025f0f  jnz     short loc_180025F61
0x180025f11  call    cs:__imp_GetLastError
0x180025f17  mov     ebx, eax
0x180025f19  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f20  lea     rax, WPP_GLOBAL_Control
0x180025f27  cmp     rcx, rax
0x180025f2a  jz      short loc_180025F54
0x180025f2c  test    byte ptr [rcx+1Ch], 2
0x180025f30  jz      short loc_180025F54
0x180025f32  mov     eax, cs:?g_idServiceMainThread@@3KA; ulong g_idServiceMainThread
0x180025f38  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x180025f3f  mov     rcx, [rcx+10h]
0x180025f43  mov     edx, 0Ch
0x180025f48  mov     r9d, ebx
0x180025f4b  mov     [rsp+58h+var_38], eax
0x180025f4f  call    WPP_SF_dd
0x180025f54  test    ebx, ebx
0x180025f56  jle     short loc_180025F5F
0x180025f58  movzx   ebx, bx
0x180025f5b  or      ebx, edi
0x180025f5d  test    ebx, ebx
0x180025f5f  js      short loc_180025F8A
0x180025f61  mov     rcx, [rsp+58h+hHandle+8]; hHandle
0x180025f66  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025f69  call    cs:__imp_WaitForSingleObject
0x180025f6f  test    eax, eax
0x180025f71  jnz     short loc_180025F79
0x180025f73  mov     ebx, dword ptr [rsp+58h+hHandle]
0x180025f77  jmp     short loc_180025F8A
0x180025f79  call    cs:__imp_GetLastError
0x180025f7f  mov     ebx, eax
0x180025f81  test    eax, eax
0x180025f83  jle     short loc_180025F8A
0x180025f85  movzx   ebx, ax
0x180025f88  or      ebx, edi
0x180025f8a  mov     rcx, [rsp+58h+hHandle+8]; hObject
0x180025f8f  call    cs:__imp_CloseHandle
0x180025f95  mov     rsi, [rsp+58h+arg_8]
0x180025f9a  mov     eax, ebx
0x180025f9c  mov     rbx, [rsp+58h+arg_0]
0x180025fa1  add     rsp, 50h
0x180025fa5  pop     rdi
0x180025fa6  retn
```
