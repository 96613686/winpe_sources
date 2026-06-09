# COMCallThreadProc(void *)

- ea: `0x10122850`
- end: `0x101229d4`
- name: `?COMCallThreadProc@@YAXPAX@Z`
- size: `388`
- prototype: `void __cdecl(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10050000`
- `0x10122815`
- `0x10122850`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x1012298a`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x1012298a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122910`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1012295d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x10122910`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1012295d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122888`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122940`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122969`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122940`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122969`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameA` at `0x101228a1`
- `api-ms-win-core-sysinfo-l2-1-0!GetUserNameA` at `0x101228a1`
- `USER32!DispatchMessageA` at `0x101229b4`
- `USER32!DispatchMessageA` at `0x101229b4`
- `USER32!PeekMessageA` at `0x101229c5`
- `USER32!PeekMessageA` at `0x101229c5`
- `USER32!TranslateMessage` at `0x101229a7`
- `USER32!TranslateMessage` at `0x101229a7`
- `USER32!MsgWaitForMultipleObjects` at `0x101228e9`
- `USER32!MsgWaitForMultipleObjects` at `0x101228e9`

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
  dword_10131078 = GetCurrentThreadId();
  if ( GetUserNameA(Buffer, &pcbBuffer) )
  {
    v1 = 0;
    while ( Buffer[v1] == aSystem[v1] )
    {
      if ( ++v1 == 7 )
      {
        dword_101310EC = 1;
        break;
      }
    }
  }
  dword_101310D8 = 1;
LABEL_12:
  SetEvent(hHandle);
  while ( dword_10130F48 != 999 )
  {
    if ( MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu) != 1 )
    {
      if ( dword_10130F48 == 999 )
        break;
      if ( TokenHandle )
        SetThreadToken(0, TokenHandle);
      dword_10130F2C = COMCallProcess(dword_10130F88);
      dword_10130F48 = 1000;
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
  dword_101310D8 = 0;
  __endthreadex(0);
}

```

## disassembly

```asm
0x10122850  mov     edi, edi
0x10122852  push    ebp
0x10122853  mov     ebp, esp
0x10122855  sub     esp, 40Ch
0x1012285b  mov     eax, ___security_cookie
0x10122860  xor     eax, ebp
0x10122862  mov     [ebp+var_4], eax
0x10122865  push    ebx
0x10122866  push    esi
0x10122867  mov     esi, CoInitializeEx
0x1012286d  mov     ecx, esi
0x1012286f  push    edi
0x10122870  xor     edi, edi
0x10122872  mov     [ebp+pcbBuffer], 3E8h
0x1012287c  push    edi; unsigned int
0x1012287d  push    edi; void *
0x1012287e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10122884  call    esi ; CoInitializeEx
0x10122886  mov     esi, eax
0x10122888  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1012288e  mov     dword_10131078, eax
0x10122893  lea     eax, [ebp+pcbBuffer]
0x10122899  push    eax; pcbBuffer
0x1012289a  lea     eax, [ebp+Buffer]
0x101228a0  push    eax; lpBuffer
0x101228a1  call    ds:__imp__GetUserNameA@8; GetUserNameA(x,x)
0x101228a7  xor     ebx, ebx
0x101228a9  inc     ebx
0x101228aa  test    eax, eax
0x101228ac  jz      short loc_101228D3
0x101228ae  lea     edx, [ebp+Buffer]
0x101228b4  mov     ecx, edi
0x101228b6  movzx   eax, byte ptr [edx+ecx]
0x101228ba  mov     edi, offset aSystem; "SYSTEM"
0x101228bf  push    0
0x101228c1  cmp     al, [edi+ecx]
0x101228c4  pop     edi
0x101228c5  jnz     short loc_101228D3
0x101228c7  inc     ecx
0x101228c8  cmp     ecx, 7
0x101228cb  jnz     short loc_101228B6
0x101228cd  mov     dword_101310EC, ebx
0x101228d3  mov     dword_101310D8, ebx
0x101228d9  jmp     short loc_1012293A
0x101228db  push    1CFFh; dwWakeMask
0x101228e0  push    0FFFFFFFFh; dwMilliseconds
0x101228e2  push    edi; fWaitAll
0x101228e3  push    offset pHandles; pHandles
0x101228e8  push    ebx; nCount
0x101228e9  call    ds:__imp__MsgWaitForMultipleObjects@20; MsgWaitForMultipleObjects(x,x,x,x,x)
0x101228ef  cmp     eax, ebx
0x101228f1  jz      loc_101229BA
0x101228f7  mov     ecx, dword_10130F48
0x101228fd  cmp     ecx, 3E7h
0x10122903  jz      short loc_10122952
0x10122905  mov     eax, TokenHandle
0x1012290a  test    eax, eax
0x1012290c  jz      short loc_1012291C
0x1012290e  push    eax; Token
0x1012290f  push    edi; Thread
0x10122910  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x10122916  mov     ecx, dword_10130F48
0x1012291c  push    offset dword_10130F88
0x10122921  mov     edx, offset dword_10130F4C
0x10122926  call    ?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z; COMCallProcess(etCOMCall,ulong * const,_GUID * const)
0x1012292b  mov     dword_10130F2C, eax
0x10122930  mov     dword_10130F48, 3E8h
0x1012293a  push    hHandle; hEvent
0x10122940  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10122946  cmp     dword_10130F48, 3E7h
0x10122950  jnz     short loc_101228DB
0x10122952  cmp     TokenHandle, 0
0x10122959  jz      short loc_10122963
0x1012295b  push    edi; Token
0x1012295c  push    edi; Thread
0x1012295d  call    ds:__imp__SetThreadToken@8; SetThreadToken(x,x)
0x10122963  push    hHandle; hEvent
0x10122969  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1012296f  test    esi, esi
0x10122971  jnz     short loc_10122983
0x10122973  mov     esi, CoUninitialize
0x10122979  mov     ecx, esi
0x1012297b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10122981  call    esi ; CoUninitialize
0x10122983  push    edi; ReturnCode
0x10122984  mov     dword_101310D8, edi
0x1012298a  call    ds:__imp___endthreadex
0x10122990  pop     ecx
0x10122991  mov     ecx, [ebp+var_4]
0x10122994  pop     edi
0x10122995  pop     esi
0x10122996  xor     ecx, ebp; StackCookie
0x10122998  pop     ebx
0x10122999  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1012299e  leave
0x1012299f  retn
0x101229a0  lea     eax, [ebp+Msg]
0x101229a6  push    eax; lpMsg
0x101229a7  call    ds:__imp__TranslateMessage@4; TranslateMessage(x)
0x101229ad  lea     eax, [ebp+Msg]
0x101229b3  push    eax; lpMsg
0x101229b4  call    ds:__imp__DispatchMessageA@4; DispatchMessageA(x)
0x101229ba  push    ebx; wRemoveMsg
0x101229bb  push    edi; wMsgFilterMax
0x101229bc  push    edi; wMsgFilterMin
0x101229bd  push    edi; hWnd
0x101229be  lea     eax, [ebp+Msg]
0x101229c4  push    eax; lpMsg
0x101229c5  call    ds:__imp__PeekMessageA@20; PeekMessageA(x,x,x,x,x)
0x101229cb  test    eax, eax
0x101229cd  jnz     short loc_101229A0
0x101229cf  jmp     loc_10122946
```
