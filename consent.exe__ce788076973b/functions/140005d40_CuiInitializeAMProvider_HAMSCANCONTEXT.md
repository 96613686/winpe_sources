# CuiInitializeAMProvider(HAMSCANCONTEXT__ * *)

- ea: `0x140005d40`
- end: `0x140005f62`
- name: `?CuiInitializeAMProvider@@YAKPEAPEAUHAMSCANCONTEXT__@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(DWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a080`

## callees

- `0x140005d40`
- `0x14000fbec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005f34`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005f34`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005d9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005dbe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005d9e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005dbe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005f17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ead`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005ed5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005f55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005f55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005d57`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005d57`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005dec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005dec`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x140005e0b`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x140005e0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005f4c`

## pseudocode

```c
__int64 __fastcall CuiInitializeAMProvider(DWORD **a1)
{
  DWORD *v2; // rbx
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HANDLE Thread; // rax
  DWORD LastError; // edi
  __int64 v8; // rcx
  __int64 v9; // rdx
  void *v10; // rcx
  void *v11; // rcx

  v2 = (DWORD *)LocalAlloc(0x40u, 0x28u);
  if ( !v2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, 14);
    return 14;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v2 + 2) = EventW;
  if ( EventW )
  {
    v5 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v2 + 3) = v5;
    if ( v5 )
    {
      Thread = CreateThread(0, 0, CuipAMScanThreadProc, v2, 0, v2 + 2);
      *(_QWORD *)v2 = Thread;
      if ( Thread )
      {
        if ( QueueUserAPC(CuipAMInitializeAPCProc, Thread, (ULONG_PTR)v2) )
        {
          *a1 = v2;
          return 0;
        }
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_25;
        v9 = 17;
      }
      else
      {
        LastError = GetLastError();
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_25;
        v9 = 16;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_25;
      v9 = 15;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_25;
    v9 = 14;
  }
  WPP_SF_D(*(_QWORD *)(v8 + 16), v9, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, LastError);
LABEL_25:
  v10 = (void *)*((_QWORD *)v2 + 2);
  if ( v10 )
  {
    SetEvent(v10);
    CloseHandle(*((HANDLE *)v2 + 2));
  }
  if ( *(_QWORD *)v2 )
  {
    WaitForSingleObject(*(HANDLE *)v2, 0xFFFFFFFF);
    CloseHandle(*(HANDLE *)v2);
  }
  v11 = (void *)*((_QWORD *)v2 + 3);
  if ( v11 )
    CloseHandle(v11);
  LocalFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x140005d40  mov     [rsp+arg_8], rbx
0x140005d45  push    rdi
0x140005d46  sub     rsp, 30h
0x140005d4a  mov     rdi, rcx
0x140005d4d  mov     edx, 28h ; '('; uBytes
0x140005d52  mov     ecx, 40h ; '@'; uFlags
0x140005d57  call    cs:__imp_LocalAlloc
0x140005d5d  mov     rbx, rax
0x140005d60  test    rax, rax
0x140005d63  jnz     short loc_140005D8C
0x140005d65  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d6c  lea     rax, WPP_GLOBAL_Control
0x140005d73  cmp     rcx, rax
0x140005d76  jnz     loc_140005E5B
0x140005d7c  mov     eax, 0Eh
0x140005d81  mov     rbx, [rsp+38h+arg_8]
0x140005d86  add     rsp, 30h
0x140005d8a  pop     rdi
0x140005d8b  retn
0x140005d8c  xor     r9d, r9d; lpName
0x140005d8f  mov     [rsp+38h+arg_0], rsi
0x140005d94  xor     r8d, r8d; bInitialState
0x140005d97  mov     edx, 1; bManualReset
0x140005d9c  xor     ecx, ecx; lpEventAttributes
0x140005d9e  call    cs:__imp_CreateEventW
0x140005da4  mov     [rbx+10h], rax
0x140005da8  test    rax, rax
0x140005dab  jz      loc_140005E85
0x140005db1  xor     r9d, r9d; lpName
0x140005db4  xor     r8d, r8d; bInitialState
0x140005db7  mov     edx, 1; bManualReset
0x140005dbc  xor     ecx, ecx; lpEventAttributes
0x140005dbe  call    cs:__imp_CreateEventW
0x140005dc4  mov     [rbx+18h], rax
0x140005dc8  test    rax, rax
0x140005dcb  jz      short loc_140005E28
0x140005dcd  lea     rax, [rbx+8]
0x140005dd1  mov     r9, rbx; lpParameter
0x140005dd4  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140005dd9  lea     r8, ?CuipAMScanThreadProc@@YAKPEAX@Z; lpStartAddress
0x140005de0  xor     edx, edx; dwStackSize
0x140005de2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140005dea  xor     ecx, ecx; lpThreadAttributes
0x140005dec  call    cs:__imp_CreateThread
0x140005df2  mov     [rbx], rax
0x140005df5  test    rax, rax
0x140005df8  jz      loc_140005EAD
0x140005dfe  mov     r8, rbx; dwData
0x140005e01  lea     rcx, ?CuipAMInitializeAPCProc@@YAX_K@Z; pfnAPC
0x140005e08  mov     rdx, rax; hThread
0x140005e0b  call    cs:__imp_QueueUserAPC
0x140005e11  test    eax, eax
0x140005e13  jz      loc_140005ED5
0x140005e19  mov     [rdi], rbx
0x140005e1c  xor     eax, eax
0x140005e1e  mov     rsi, [rsp+38h+arg_0]
0x140005e23  jmp     loc_140005D81
0x140005e28  call    cs:__imp_GetLastError
0x140005e2e  mov     edi, eax
0x140005e30  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e37  lea     rax, WPP_GLOBAL_Control
0x140005e3e  cmp     rcx, rax
0x140005e41  jz      loc_140005F0E
0x140005e47  test    byte ptr [rcx+1Ch], 2
0x140005e4b  jz      loc_140005F0E
0x140005e51  mov     edx, 0Fh
0x140005e56  jmp     loc_140005EFB
0x140005e5b  test    byte ptr [rcx+1Ch], 2
0x140005e5f  jz      loc_140005D7C
0x140005e65  mov     rcx, [rcx+10h]
0x140005e69  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140005e70  mov     edx, 0Dh
0x140005e75  mov     r9d, 0Eh
0x140005e7b  call    WPP_SF_D
0x140005e80  jmp     loc_140005D7C
0x140005e85  call    cs:__imp_GetLastError
0x140005e8b  mov     edi, eax
0x140005e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e94  lea     rax, WPP_GLOBAL_Control
0x140005e9b  cmp     rcx, rax
0x140005e9e  jz      short loc_140005F0E
0x140005ea0  test    byte ptr [rcx+1Ch], 2
0x140005ea4  jz      short loc_140005F0E
0x140005ea6  mov     edx, 0Eh
0x140005eab  jmp     short loc_140005EFB
0x140005ead  call    cs:__imp_GetLastError
0x140005eb3  mov     edi, eax
0x140005eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ebc  lea     rax, WPP_GLOBAL_Control
0x140005ec3  cmp     rcx, rax
0x140005ec6  jz      short loc_140005F0E
0x140005ec8  test    byte ptr [rcx+1Ch], 2
0x140005ecc  jz      short loc_140005F0E
0x140005ece  mov     edx, 10h
0x140005ed3  jmp     short loc_140005EFB
0x140005ed5  call    cs:__imp_GetLastError
0x140005edb  mov     edi, eax
0x140005edd  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ee4  lea     rax, WPP_GLOBAL_Control
0x140005eeb  cmp     rcx, rax
0x140005eee  jz      short loc_140005F0E
0x140005ef0  test    byte ptr [rcx+1Ch], 2
0x140005ef4  jz      short loc_140005F0E
0x140005ef6  mov     edx, 11h
0x140005efb  mov     rcx, [rcx+10h]
0x140005eff  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140005f06  mov     r9d, edi
0x140005f09  call    WPP_SF_D
0x140005f0e  mov     rcx, [rbx+10h]; hEvent
0x140005f12  test    rcx, rcx
0x140005f15  jz      short loc_140005F27
0x140005f17  call    cs:__imp_SetEvent
0x140005f1d  mov     rcx, [rbx+10h]; hObject
0x140005f21  call    cs:__imp_CloseHandle
0x140005f27  mov     rcx, [rbx]; hHandle
0x140005f2a  test    rcx, rcx
0x140005f2d  jz      short loc_140005F43
0x140005f2f  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140005f34  call    cs:__imp_WaitForSingleObject
0x140005f3a  mov     rcx, [rbx]; hObject
0x140005f3d  call    cs:__imp_CloseHandle
0x140005f43  mov     rcx, [rbx+18h]; hObject
0x140005f47  test    rcx, rcx
0x140005f4a  jz      short loc_140005F52
0x140005f4c  call    cs:__imp_CloseHandle
0x140005f52  mov     rcx, rbx; hMem
0x140005f55  call    cs:__imp_LocalFree
0x140005f5b  mov     eax, edi
0x140005f5d  jmp     loc_140005E1E
```
