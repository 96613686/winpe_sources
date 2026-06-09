# CFwProfileMgr::RegisterForChangeNotifications(void)

- ea: `0x18001e310`
- end: `0x18001e4d8`
- name: `?RegisterForChangeNotifications@CFwProfileMgr@@AEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CFwProfileMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d570`

## callees

- `0x180009924`
- `0x18000994c`
- `0x18001e310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e35a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e35a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e428`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e369`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e428`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e479`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e479`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001e419`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x18001e419`
- `FirewallAPI!IcfChangeNotificationDestroy` at `0x18001e497`
- `FirewallAPI!IcfChangeNotificationDestroy` at `0x18001e497`
- `FirewallAPI!IcfChangeNotificationCreate` at `0x18001e3c3`
- `FirewallAPI!IcfChangeNotificationCreate` at `0x18001e3c3`

## pseudocode

```c
__int64 __fastcall CFwProfileMgr::RegisterForChangeNotifications(CFwProfileMgr *this)
{
  signed int v2; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  CFwCplLua *v5; // rcx
  _QWORD *v6; // rdi
  signed int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  signed int v10; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 7) = EventW;
  if ( EventW )
    goto LABEL_12;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_12:
    v6 = (_QWORD *)((char *)this + 64);
    if ( !(unsigned int)IcfChangeNotificationCreate(*((_QWORD *)this + 7), (char *)this + 64) )
      goto LABEL_19;
    v7 = GetLastError();
    v2 = v7;
    if ( v7 > 0 )
      v2 = (unsigned __int16)v7 | 0x80070000;
    if ( v2 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v8 = 46;
    }
    else
    {
LABEL_19:
      v9 = RegisterWaitForSingleObjectEx(*((_QWORD *)this + 7), CFwProfileMgr::WaitCallback, this, 0xFFFFFFFFLL, 0);
      *((_QWORD *)this + 9) = v9;
      if ( v9 )
        goto LABEL_31;
      v10 = GetLastError();
      v2 = v10;
      if ( v10 > 0 )
        v2 = (unsigned __int16)v10 | 0x80070000;
      if ( v2 >= 0 )
        goto LABEL_31;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_27;
      v8 = 47;
    }
    WPP_SF_d(*((_QWORD *)v5 + 2), v8, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, (unsigned int)v2);
    v5 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, (unsigned int)v2);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = (_QWORD *)((char *)this + 64);
LABEL_27:
  if ( *((_QWORD *)this + 7) )
  {
    CloseHandle(*((HANDLE *)this + 7));
    *((_QWORD *)this + 7) = 0;
    v5 = WPP_GLOBAL_Control;
  }
  if ( *v6 )
  {
    IcfChangeNotificationDestroy(v6);
    *v6 = 0;
LABEL_31:
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 48, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001e310  push    rbx
0x18001e312  push    rsi
0x18001e313  push    rdi
0x18001e314  push    r12
0x18001e316  push    r14
0x18001e318  sub     rsp, 30h
0x18001e31c  mov     rsi, rcx
0x18001e31f  xor     ebx, ebx
0x18001e321  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e328  lea     r14, WPP_GLOBAL_Control
0x18001e32f  lea     r12, WPP_0bd2a823c7ab36d0aa1f9362dc484429_Traceguids
0x18001e336  cmp     rcx, r14
0x18001e339  jz      short loc_18001E350
0x18001e33b  test    byte ptr [rcx+1Ch], 8
0x18001e33f  jz      short loc_18001E350
0x18001e341  mov     rcx, [rcx+10h]
0x18001e345  lea     edx, [rbx+2Ch]
0x18001e348  mov     r8, r12
0x18001e34b  call    WPP_SF_
0x18001e350  xor     r9d, r9d; lpName
0x18001e353  xor     r8d, r8d; bInitialState
0x18001e356  xor     edx, edx; bManualReset
0x18001e358  xor     ecx, ecx; lpEventAttributes
0x18001e35a  call    cs:__imp_CreateEventW
0x18001e360  mov     [rsi+38h], rax
0x18001e364  test    rax, rax
0x18001e367  jnz     short loc_18001E3B8
0x18001e369  call    cs:__imp_GetLastError
0x18001e36f  mov     ebx, eax
0x18001e371  test    eax, eax
0x18001e373  jle     short loc_18001E37E
0x18001e375  movzx   ebx, ax
0x18001e378  or      ebx, 80070000h
0x18001e37e  test    ebx, ebx
0x18001e380  jns     short loc_18001E3B8
0x18001e382  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e389  cmp     rcx, r14
0x18001e38c  jz      short loc_18001E3AF
0x18001e38e  test    byte ptr [rcx+1Ch], 1
0x18001e392  jz      short loc_18001E3AF
0x18001e394  mov     rcx, [rcx+10h]
0x18001e398  mov     edx, 2Dh ; '-'
0x18001e39d  mov     r9d, ebx
0x18001e3a0  mov     r8, r12
0x18001e3a3  call    WPP_SF_d
0x18001e3a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3af  lea     rdi, [rsi+40h]
0x18001e3b3  jmp     loc_18001E46E
0x18001e3b8  mov     rcx, [rsi+38h]
0x18001e3bc  lea     rdi, [rsi+40h]
0x18001e3c0  mov     rdx, rdi
0x18001e3c3  call    cs:__imp_IcfChangeNotificationCreate
0x18001e3c9  test    eax, eax
0x18001e3cb  jz      short loc_18001E3FF
0x18001e3cd  call    cs:__imp_GetLastError
0x18001e3d3  mov     ebx, eax
0x18001e3d5  test    eax, eax
0x18001e3d7  jle     short loc_18001E3E2
0x18001e3d9  movzx   ebx, ax
0x18001e3dc  or      ebx, 80070000h
0x18001e3e2  test    ebx, ebx
0x18001e3e4  jns     short loc_18001E3FF
0x18001e3e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3ed  cmp     rcx, r14
0x18001e3f0  jz      short loc_18001E46E
0x18001e3f2  test    byte ptr [rcx+1Ch], 1
0x18001e3f6  jz      short loc_18001E46E
0x18001e3f8  mov     edx, 2Eh ; '.'
0x18001e3fd  jmp     short loc_18001E458
0x18001e3ff  mov     rcx, [rsi+38h]
0x18001e403  lea     rdx, ?WaitCallback@CFwProfileMgr@@CAXPEAXE@Z; CFwProfileMgr::WaitCallback(void *,uchar)
0x18001e40a  or      r9d, 0FFFFFFFFh
0x18001e40e  mov     [rsp+58h+var_38], 0
0x18001e416  mov     r8, rsi
0x18001e419  call    cs:__imp_RegisterWaitForSingleObjectEx
0x18001e41f  mov     [rsi+48h], rax
0x18001e423  test    rax, rax
0x18001e426  jnz     short loc_18001E4A4
0x18001e428  call    cs:__imp_GetLastError
0x18001e42e  mov     ebx, eax
0x18001e430  test    eax, eax
0x18001e432  jle     short loc_18001E43D
0x18001e434  movzx   ebx, ax
0x18001e437  or      ebx, 80070000h
0x18001e43d  test    ebx, ebx
0x18001e43f  jns     short loc_18001E4A4
0x18001e441  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e448  cmp     rcx, r14
0x18001e44b  jz      short loc_18001E46E
0x18001e44d  test    byte ptr [rcx+1Ch], 1
0x18001e451  jz      short loc_18001E46E
0x18001e453  mov     edx, 2Fh ; '/'
0x18001e458  mov     rcx, [rcx+10h]
0x18001e45c  mov     r9d, ebx
0x18001e45f  mov     r8, r12
0x18001e462  call    WPP_SF_d
0x18001e467  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e46e  cmp     qword ptr [rsi+38h], 0
0x18001e473  jz      short loc_18001E48E
0x18001e475  mov     rcx, [rsi+38h]; hObject
0x18001e479  call    cs:__imp_CloseHandle
0x18001e47f  mov     qword ptr [rsi+38h], 0
0x18001e487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e48e  cmp     qword ptr [rdi], 0
0x18001e492  jz      short loc_18001E4AB
0x18001e494  mov     rcx, rdi
0x18001e497  call    cs:__imp_IcfChangeNotificationDestroy
0x18001e49d  mov     qword ptr [rdi], 0
0x18001e4a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e4ab  cmp     rcx, r14
0x18001e4ae  jz      short loc_18001E4CA
0x18001e4b0  test    byte ptr [rcx+1Ch], 8
0x18001e4b4  jz      short loc_18001E4CA
0x18001e4b6  mov     rcx, [rcx+10h]
0x18001e4ba  mov     edx, 30h ; '0'
0x18001e4bf  mov     r9d, ebx
0x18001e4c2  mov     r8, r12
0x18001e4c5  call    WPP_SF_d
0x18001e4ca  mov     eax, ebx
0x18001e4cc  add     rsp, 30h
0x18001e4d0  pop     r14
0x18001e4d2  pop     r12
0x18001e4d4  pop     rdi
0x18001e4d5  pop     rsi
0x18001e4d6  pop     rbx
0x18001e4d7  retn
```
