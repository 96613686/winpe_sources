# CFwProfileMgr::PostNlmNotification(CFwProfileMgr::NLM_NOTIFICATION_TYPE,_GUID const *,tagNP_NETWORK_PROPERTY_CHANGE)

- ea: `0x18001e10c`
- end: `0x18001e1f0`
- name: `?PostNlmNotification@CFwProfileMgr@@AEAAJW4NLM_NOTIFICATION_TYPE@1@PEBU_GUID@@W4tagNP_NETWORK_PROPERTY_CHANGE@@@Z`
- size: `228`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001dc40`
- `0x18001de20`
- `0x18001df00`
- `0x18001df20`

## callees

- `0x18000994c`
- `0x18001e10c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e195`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e195`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e162`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001e162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e19b`
- `KERNEL32!QueueUserWorkItem` at `0x18001e175`
- `KERNEL32!QueueUserWorkItem` at `0x18001e175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e12a`

## pseudocode

```c
__int64 __fastcall CFwProfileMgr::PostNlmNotification(__int64 a1, int a2, __int128 *a3, int a4)
{
  char *v8; // rax
  void *v9; // rsi
  unsigned int v10; // ebx
  __int128 v11; // xmm0
  signed int LastError; // eax

  v8 = (char *)CoTaskMemAlloc(0x20u);
  v9 = v8;
  if ( v8 )
  {
    *(_QWORD *)v8 = a1;
    v10 = 0;
    *((_DWORD *)v8 + 2) = a2;
    v11 = *a3;
    *((_DWORD *)v8 + 7) = a4;
    *(_OWORD *)(v8 + 12) = v11;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 216));
    ResetEvent(*(HANDLE *)(a1 + 208));
    if ( !QueueUserWorkItem(CFwProfileMgr::s_NlmNotificationWorker, v9, 0) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(a1 + 216));
      if ( !*(_DWORD *)(a1 + 216) )
        SetEvent(*(HANDLE *)(a1 + 208));
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v10 = -2147024882;
  }
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18001e10c  push    rbx
0x18001e10e  push    rbp
0x18001e10f  push    rsi
0x18001e110  push    rdi
0x18001e111  push    r14
0x18001e113  push    r15
0x18001e115  sub     rsp, 28h
0x18001e119  mov     rdi, rcx
0x18001e11c  mov     ebp, r9d
0x18001e11f  mov     ecx, 20h ; ' '; cb
0x18001e124  mov     r14, r8
0x18001e127  mov     r15d, edx
0x18001e12a  call    cs:__imp_CoTaskMemAlloc
0x18001e130  mov     rsi, rax
0x18001e133  test    rax, rax
0x18001e136  jnz     short loc_18001E13F
0x18001e138  mov     ebx, 8007000Eh
0x18001e13d  jmp     short loc_18001E1B0
0x18001e13f  mov     [rax], rdi
0x18001e142  xor     ebx, ebx
0x18001e144  mov     [rax+8], r15d
0x18001e148  movups  xmm0, xmmword ptr [r14]
0x18001e14c  mov     [rax+1Ch], ebp
0x18001e14f  movdqu  xmmword ptr [rax+0Ch], xmm0
0x18001e154  lock inc dword ptr [rdi+0D8h]
0x18001e15b  mov     rcx, [rdi+0D0h]; hEvent
0x18001e162  call    cs:__imp_ResetEvent
0x18001e168  xor     r8d, r8d; Flags
0x18001e16b  lea     rcx, ?s_NlmNotificationWorker@CFwProfileMgr@@CAKPEAX@Z; Function
0x18001e172  mov     rdx, rsi; Context
0x18001e175  call    cs:__imp_QueueUserWorkItem
0x18001e17b  test    eax, eax
0x18001e17d  jnz     short loc_18001E1B0
0x18001e17f  lock dec dword ptr [rdi+0D8h]
0x18001e186  cmp     [rdi+0D8h], ebx
0x18001e18c  jnz     short loc_18001E19B
0x18001e18e  mov     rcx, [rdi+0D0h]; hEvent
0x18001e195  call    cs:__imp_SetEvent
0x18001e19b  call    cs:__imp_GetLastError
0x18001e1a1  mov     ebx, eax
0x18001e1a3  test    eax, eax
0x18001e1a5  jle     short loc_18001E1B0
0x18001e1a7  movzx   ebx, ax
0x18001e1aa  or      ebx, 80070000h
0x18001e1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1b7  lea     rax, WPP_GLOBAL_Control
0x18001e1be  cmp     rcx, rax
0x18001e1c1  jz      short loc_18001E1E1
0x18001e1c3  test    byte ptr [rcx+1Ch], 8
0x18001e1c7  jz      short loc_18001E1E1
0x18001e1c9  mov     rcx, [rcx+10h]
0x18001e1cd  lea     r8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001e1d4  mov     edx, 48h ; 'H'
0x18001e1d9  mov     r9d, ebx
0x18001e1dc  call    WPP_SF_d
0x18001e1e1  mov     eax, ebx
0x18001e1e3  add     rsp, 28h
0x18001e1e7  pop     r15
0x18001e1e9  pop     r14
0x18001e1eb  pop     rdi
0x18001e1ec  pop     rsi
0x18001e1ed  pop     rbp
0x18001e1ee  pop     rbx
0x18001e1ef  retn
```
