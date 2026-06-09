# COMCallThreadProc(void *)

- ea: `0x10122a00`
- end: `0x10122b84`
- name: `?COMCallThreadProc@@YAXPAX@Z`
- size: `388`
- prototype: `void __cdecl(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10050190`
- `0x101229c5`
- `0x10122a00`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x10122b3a`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x10122b3a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122ac0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122b0d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122ac0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122b0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122a38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122a38`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122af0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122b19`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122af0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122b19`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameA` at `0x10122a51`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameA` at `0x10122a51`
- `USER32!DispatchMessageA` at `0x10122b64`
- `USER32!DispatchMessageA` at `0x10122b64`
- `USER32!PeekMessageA` at `0x10122b75`
- `USER32!PeekMessageA` at `0x10122b75`
- `USER32!TranslateMessage` at `0x10122b57`
- `USER32!TranslateMessage` at `0x10122b57`
- `USER32!MsgWaitForMultipleObjects` at `0x10122a99`
- `USER32!MsgWaitForMultipleObjects` at `0x10122a99`

## pseudocode

```c
void __cdecl COMCallThreadProc()
{
  HRESULT v0; // esi
  int v1; // ecx
  MSG Msg; // [esp+Ch] [ebp-40Ch] BYREF
  DWORD pcbBuffer; // [esp+28h] [ebp-3F0h] BYREF
  CHAR Buffer[1000]; // [esp+2Ch] [ebp-3ECh] BYREF

  pcbBuffer = 1000;
  v0 = CoInitializeEx(0, 0);
  dword_10131128 = GetCurrentThreadId();
  if ( GetUserNameA(Buffer, &pcbBuffer) )
  {
    v1 = 0;
    while ( Buffer[v1] == aSystem[v1] )
    {
      if ( ++v1 == 7 )
      {
        dword_1013119C = 1;
        break;
      }
    }
  }
  dword_10131188 = 1;
LABEL_12:
  SetEvent(hHandle);
  while ( dword_10130FF4 != 999 )
  {
    if ( MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu) != 1 )
    {
      if ( dword_10130FF4 == 999 )
        break;
      if ( TokenHandle )
        SetThreadToken(0, TokenHandle);
      dword_10130FD8 = COMCallProcess(dword_10131038);
      dword_10130FF4 = 1000;
      goto LABEL_12;
    }
    while ( PeekMessageA(&Msg, 0, 0, 0, 1u) )
    {
      TranslateMessage(&Msg);
      DispatchMessageA(&Msg);
    }
  }
  if ( TokenHandle )
    SetThreadToken(0, 0);
  SetEvent(hHandle);
  if ( !v0 )
    CoUninitialize();
  dword_10131188 = 0;
  __endthreadex(0);
}

```

## disassembly

```asm
0x10122a00  mov     edi, edi
0x10122a02  push    ebp
0x10122a03  mov     ebp, esp
0x10122a05  sub     esp, 40Ch
0x10122a0b  mov     eax, ___security_cookie
0x10122a10  xor     eax, ebp
0x10122a12  mov     [ebp+var_4], eax
0x10122a15  push    ebx
0x10122a16  push    esi
0x10122a17  mov     esi, CoInitializeEx
0x10122a1d  mov     ecx, esi
0x10122a1f  push    edi
0x10122a20  xor     edi, edi
0x10122a22  mov     [ebp+pcbBuffer], 3E8h
0x10122a2c  push    edi; unsigned int
0x10122a2d  push    edi; void *
0x10122a2e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10122a34  call    esi ; CoInitializeEx
0x10122a36  mov     esi, eax
0x10122a38  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10122a3e  mov     dword_10131128, eax
0x10122a43  lea     eax, [ebp+pcbBuffer]
0x10122a49  push    eax; pcbBuffer
0x10122a4a  lea     eax, [ebp+Buffer]
0x10122a50  push    eax; lpBuffer
0x10122a51  call    ds:__imp__GetUserNameA@8; GetUserNameA(x,x)
0x10122a57  xor     ebx, ebx
0x10122a59  inc     ebx
0x10122a5a  test    eax, eax
0x10122a5c  jz      short loc_10122A83
0x10122a5e  lea     edx, [ebp+Buffer]
0x10122a64  mov     ecx, edi
0x10122a66  movzx   eax, byte ptr [edx+ecx]
0x10122a6a  mov     edi, offset aSystem; "SYSTEM"
0x10122a6f  push    0
0x10122a71  cmp     al, [edi+ecx]
0x10122a74  pop     edi
0x10122a75  jnz     short loc_10122A83
0x10122a77  inc     ecx
0x10122a78  cmp     ecx, 7
0x10122a7b  jnz     short loc_10122A66
0x10122a7d  mov     dword_1013119C, ebx
0x10122a83  mov     dword_10131188, ebx
0x10122a89  jmp     short loc_10122AEA
0x10122a8b  push    1CFFh; dwWakeMask
0x10122a90  push    0FFFFFFFFh; dwMilliseconds
0x10122a92  push    edi; fWaitAll
0x10122a93  push    offset pHandles; pHandles
0x10122a98  push    ebx; nCount
0x10122a99  call    ds:__imp__MsgWaitForMultipleObjects@20; MsgWaitForMultipleObjects(x,x,x,x,x)
0x10122a9f  cmp     eax, ebx
0x10122aa1  jz      loc_10122B6A
0x10122aa7  mov     ecx, dword_10130FF4
0x10122aad  cmp     ecx, 3E7h
0x10122ab3  jz      short loc_10122B02
0x10122ab5  mov     eax, TokenHandle
0x10122aba  test    eax, eax
0x10122abc  jz      short loc_10122ACC
0x10122abe  push    eax; Token
0x10122abf  push    edi; Thread
0x10122ac0  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x10122ac6  mov     ecx, dword_10130FF4
0x10122acc  push    offset dword_10131038
0x10122ad1  mov     edx, offset dword_10130FF8
0x10122ad6  call    ?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z; COMCallProcess(etCOMCall,ulong * const,_GUID * const)
0x10122adb  mov     dword_10130FD8, eax
0x10122ae0  mov     dword_10130FF4, 3E8h
0x10122aea  push    hHandle; hEvent
0x10122af0  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10122af6  cmp     dword_10130FF4, 3E7h
0x10122b00  jnz     short loc_10122A8B
0x10122b02  cmp     TokenHandle, 0
0x10122b09  jz      short loc_10122B13
0x10122b0b  push    edi; Token
0x10122b0c  push    edi; Thread
0x10122b0d  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x10122b13  push    hHandle; hEvent
0x10122b19  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10122b1f  test    esi, esi
0x10122b21  jnz     short loc_10122B33
0x10122b23  mov     esi, CoUninitialize
0x10122b29  mov     ecx, esi
0x10122b2b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10122b31  call    esi ; CoUninitialize
0x10122b33  push    edi; ReturnCode
0x10122b34  mov     dword_10131188, edi
0x10122b3a  call    ds:__imp___endthreadex
0x10122b40  pop     ecx
0x10122b41  mov     ecx, [ebp+var_4]
0x10122b44  pop     edi
0x10122b45  pop     esi
0x10122b46  xor     ecx, ebp; StackCookie
0x10122b48  pop     ebx
0x10122b49  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10122b4e  leave
0x10122b4f  retn
0x10122b50  lea     eax, [ebp+Msg]
0x10122b56  push    eax; lpMsg
0x10122b57  call    ds:__imp__TranslateMessage@4; TranslateMessage(x)
0x10122b5d  lea     eax, [ebp+Msg]
0x10122b63  push    eax; lpMsg
0x10122b64  call    ds:__imp__DispatchMessageA@4; DispatchMessageA(x)
0x10122b6a  push    ebx; wRemoveMsg
0x10122b6b  push    edi; wMsgFilterMax
0x10122b6c  push    edi; wMsgFilterMin
0x10122b6d  push    edi; hWnd
0x10122b6e  lea     eax, [ebp+Msg]
0x10122b74  push    eax; lpMsg
0x10122b75  call    ds:__imp__PeekMessageA@20; PeekMessageA(x,x,x,x,x)
0x10122b7b  test    eax, eax
0x10122b7d  jnz     short loc_10122B50
0x10122b7f  jmp     loc_10122AF6
```
