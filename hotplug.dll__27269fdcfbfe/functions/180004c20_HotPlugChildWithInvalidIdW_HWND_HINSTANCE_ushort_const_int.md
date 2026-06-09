# HotPlugChildWithInvalidIdW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180004c20`
- end: `0x180004e59`
- name: `?HotPlugChildWithInvalidIdW@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `569`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002c74`
- `0x180002d70`
- `0x180003048`
- `0x180004c20`
- `0x180006338`
- `0x18000672c`
- `0x180008760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180004cb1`
- `KERNEL32!CloseHandle` at `0x180004cc7`
- `KERNEL32!CloseHandle` at `0x180004e0e`
- `KERNEL32!CloseHandle` at `0x180004e1c`
- `KERNEL32!CloseHandle` at `0x180004cb1`
- `KERNEL32!CloseHandle` at `0x180004cc7`
- `KERNEL32!CloseHandle` at `0x180004e0e`
- `KERNEL32!CloseHandle` at `0x180004e1c`
- `KERNEL32!SetEvent` at `0x180004cbc`
- `KERNEL32!SetEvent` at `0x180004df3`
- `KERNEL32!SetEvent` at `0x180004e03`
- `KERNEL32!SetEvent` at `0x180004cbc`
- `KERNEL32!SetEvent` at `0x180004df3`
- `KERNEL32!SetEvent` at `0x180004e03`
- `KERNEL32!CreateEventW` at `0x180004d2d`
- `KERNEL32!CreateEventW` at `0x180004d5c`
- `KERNEL32!CreateEventW` at `0x180004d2d`
- `KERNEL32!CreateEventW` at `0x180004d5c`
- `KERNEL32!WaitForSingleObject` at `0x180004d40`
- `KERNEL32!WaitForSingleObject` at `0x180004d40`
- `USER32!SetProcessDPIAware` at `0x180004c76`
- `USER32!SetProcessDPIAware` at `0x180004c76`
- `USER32!TranslateMessage` at `0x180004d95`
- `USER32!TranslateMessage` at `0x180004d95`
- `USER32!PeekMessageW` at `0x180004db7`
- `USER32!PeekMessageW` at `0x180004db7`
- `USER32!DispatchMessageW` at `0x180004da0`
- `USER32!DispatchMessageW` at `0x180004da0`
- `USER32!MsgWaitForMultipleObjects` at `0x180004dd7`
- `USER32!MsgWaitForMultipleObjects` at `0x180004dd7`

## pseudocode

```c
__int64 __fastcall HotPlugChildWithInvalidIdW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  void *v5; // rdi
  __int64 v6; // r9
  HANDLE EventW; // rax
  DWORD v8; // eax
  HANDLE pHandles; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hEvent; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v13[2]; // [rsp+48h] [rbp-B8h] BYREF
  MSG Msg; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  hObject = 0;
  memset(v13, 0, sizeof(v13));
  hEvent = 0;
  pHandles = 0;
  SetProcessDPIAware();
  if ( !OpenPipeAndEventHandles(a3, &hObject, &hEvent) )
    return 1;
  v4 = DeviceCollectionBuildFromPipe(hObject, 4, (__int64)v13);
  CloseHandle(hObject);
  SetEvent(hEvent);
  CloseHandle(hEvent);
  if ( !v4 )
    return 1;
  v5 = 0;
  v6 = 0;
  if ( *(_OWORD **)&v13[0] != v13 )
    v6 = *(_QWORD *)&v13[0] + 16LL;
  if ( (int)StringCchPrintfW(Name, 0x104u, L"Local\\CHILDWITHINVALIDID-%s", v6) < 0
    || (EventW = CreateEventW(0, 0, 1, Name), (v5 = EventW) == 0)
    || !WaitForSingleObject(EventW, 0) )
  {
    pHandles = CreateEventW(0, 0, 1, L"Local\\HotPlug_ChildWithInvalidId_Event");
    if ( pHandles )
    {
      while ( 1 )
      {
        v8 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
        if ( !v8 )
          break;
        if ( v8 != 1 )
          goto LABEL_18;
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 16 )
            goto LABEL_18;
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
    }
    DisplayChildWithInvalidIdBalloon((struct DEVICE_COLLECTION *)v13);
    if ( v5 )
      SetEvent(v5);
  }
LABEL_18:
  if ( pHandles )
  {
    SetEvent(pHandles);
    CloseHandle(pHandles);
  }
  if ( v5 )
    CloseHandle(v5);
  DeviceCollectionDestroy((struct DEVICE_COLLECTION *)v13);
  return 1;
}

```

## disassembly

```asm
0x180004c20  mov     [rsp-8+arg_0], rbx
0x180004c25  mov     [rsp-8+arg_8], rdi
0x180004c2a  push    rbp
0x180004c2b  lea     rbp, [rsp-1C0h]
0x180004c33  sub     rsp, 2C0h
0x180004c3a  mov     rax, cs:__security_cookie
0x180004c41  xor     rax, rsp
0x180004c44  mov     [rbp+1C0h+var_10], rax
0x180004c4b  xorps   xmm0, xmm0
0x180004c4e  mov     [rsp+2C0h+hObject], 0
0x180004c57  movups  [rsp+2C0h+var_278], xmm0
0x180004c5c  mov     rbx, r8
0x180004c5f  mov     [rsp+2C0h+hEvent], 0
0x180004c68  movups  [rsp+2C0h+var_268], xmm0
0x180004c6d  mov     [rsp+2C0h+pHandles], 0
0x180004c76  call    cs:__imp_SetProcessDPIAware
0x180004c7c  lea     r8, [rsp+2C0h+hEvent]; void **
0x180004c81  mov     rcx, rbx; lpFileName
0x180004c84  lea     rdx, [rsp+2C0h+hObject]; void **
0x180004c89  call    ?OpenPipeAndEventHandles@@YAHPEBGPEAPEAX1@Z; OpenPipeAndEventHandles(ushort const *,void * *,void * *)
0x180004c8e  test    eax, eax
0x180004c90  jz      loc_180004E30
0x180004c96  mov     rcx, [rsp+2C0h+hObject]
0x180004c9b  lea     r8, [rsp+2C0h+var_278]
0x180004ca0  mov     edx, 4
0x180004ca5  call    ?DeviceCollectionBuildFromPipe@@YAHPEAXW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z; DeviceCollectionBuildFromPipe(void *,_COLLECTION_TYPE,DEVICE_COLLECTION *)
0x180004caa  mov     rcx, [rsp+2C0h+hObject]; hObject
0x180004caf  mov     ebx, eax
0x180004cb1  call    cs:__imp_CloseHandle
0x180004cb7  mov     rcx, [rsp+2C0h+hEvent]; hEvent
0x180004cbc  call    cs:__imp_SetEvent
0x180004cc2  mov     rcx, [rsp+2C0h+hEvent]; hObject
0x180004cc7  call    cs:__imp_CloseHandle
0x180004ccd  test    ebx, ebx
0x180004ccf  jz      loc_180004E30
0x180004cd5  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x180004cda  xor     edi, edi
0x180004cdc  xor     eax, eax
0x180004cde  lea     ebx, [rdi+1]
0x180004ce1  jmp     short loc_180004CEC
0x180004ce3  test    eax, eax
0x180004ce5  jz      short loc_180004CF6
0x180004ce7  mov     rcx, [rcx]
0x180004cea  add     eax, ebx
0x180004cec  lea     rdx, [rsp+2C0h+var_278]
0x180004cf1  cmp     rcx, rdx
0x180004cf4  jnz     short loc_180004CE3
0x180004cf6  xor     r9d, r9d
0x180004cf9  lea     rax, [rcx+10h]
0x180004cfd  lea     rdx, [rsp+2C0h+var_278]
0x180004d02  cmp     rcx, rdx
0x180004d05  lea     r8, aLocalChildwith; "Local\\CHILDWITHINVALIDID-%s"
0x180004d0c  mov     edx, 104h; unsigned __int64
0x180004d11  lea     rcx, [rbp+1C0h+Name]; unsigned __int16 *
0x180004d15  cmovnz  r9, rax
0x180004d19  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d1e  test    eax, eax
0x180004d20  js      short loc_180004D4E
0x180004d22  lea     r9, [rbp+1C0h+Name]; lpName
0x180004d26  mov     r8d, ebx; bInitialState
0x180004d29  xor     edx, edx; bManualReset
0x180004d2b  xor     ecx, ecx; lpEventAttributes
0x180004d2d  call    cs:__imp_CreateEventW
0x180004d33  mov     rdi, rax
0x180004d36  test    rax, rax
0x180004d39  jz      short loc_180004D4E
0x180004d3b  xor     edx, edx; dwMilliseconds
0x180004d3d  mov     rcx, rax; hHandle
0x180004d40  call    cs:__imp_WaitForSingleObject
0x180004d46  test    eax, eax
0x180004d48  jnz     loc_180004DF9
0x180004d4e  lea     r9, Name; "Local\\HotPlug_ChildWithInvalidId_Event"
0x180004d55  mov     r8d, ebx; bInitialState
0x180004d58  xor     edx, edx; bManualReset
0x180004d5a  xor     ecx, ecx; lpEventAttributes
0x180004d5c  call    cs:__imp_CreateEventW
0x180004d62  mov     [rsp+2C0h+pHandles], rax
0x180004d67  test    rax, rax
0x180004d6a  jz      short loc_180004DE1
0x180004d6c  jmp     short loc_180004DC1
0x180004d6e  cmp     eax, ebx
0x180004d70  jnz     loc_180004DF9
0x180004d76  xorps   xmm0, xmm0
0x180004d79  movups  xmmword ptr [rsp+2C0h+Msg.hwnd], xmm0
0x180004d7e  movups  xmmword ptr [rsp+2C0h+Msg.wParam], xmm0
0x180004d83  movups  xmmword ptr [rbp+1C0h+Msg.time], xmm0
0x180004d87  jmp     short loc_180004DA6
0x180004d89  cmp     [rsp+2C0h+Msg.message], 10h
0x180004d8e  jz      short loc_180004DF9
0x180004d90  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180004d95  call    cs:__imp_TranslateMessage
0x180004d9b  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180004da0  call    cs:__imp_DispatchMessageW
0x180004da6  xor     r9d, r9d; wMsgFilterMax
0x180004da9  mov     [rsp+2C0h+wRemoveMsg], ebx; wRemoveMsg
0x180004dad  xor     r8d, r8d; wMsgFilterMin
0x180004db0  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180004db5  xor     edx, edx; hWnd
0x180004db7  call    cs:__imp_PeekMessageW
0x180004dbd  test    eax, eax
0x180004dbf  jnz     short loc_180004D89
0x180004dc1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180004dc5  mov     [rsp+2C0h+wRemoveMsg], 1CFFh; dwWakeMask
0x180004dcd  xor     r8d, r8d; fWaitAll
0x180004dd0  lea     rdx, [rsp+2C0h+pHandles]; pHandles
0x180004dd5  mov     ecx, ebx; nCount
0x180004dd7  call    cs:__imp_MsgWaitForMultipleObjects
0x180004ddd  test    eax, eax
0x180004ddf  jnz     short loc_180004D6E
0x180004de1  lea     rcx, [rsp+2C0h+var_278]; struct DEVICE_COLLECTION *
0x180004de6  call    ?DisplayChildWithInvalidIdBalloon@@YAXPEAUDEVICE_COLLECTION@@@Z; DisplayChildWithInvalidIdBalloon(DEVICE_COLLECTION *)
0x180004deb  test    rdi, rdi
0x180004dee  jz      short loc_180004DF9
0x180004df0  mov     rcx, rdi; hEvent
0x180004df3  call    cs:__imp_SetEvent
0x180004df9  mov     rcx, [rsp+2C0h+pHandles]; hEvent
0x180004dfe  test    rcx, rcx
0x180004e01  jz      short loc_180004E14
0x180004e03  call    cs:__imp_SetEvent
0x180004e09  mov     rcx, [rsp+2C0h+pHandles]; hObject
0x180004e0e  call    cs:__imp_CloseHandle
0x180004e14  test    rdi, rdi
0x180004e17  jz      short loc_180004E22
0x180004e19  mov     rcx, rdi; hObject
0x180004e1c  call    cs:__imp_CloseHandle
0x180004e22  lea     rcx, [rsp+2C0h+var_278]; struct DEVICE_COLLECTION *
0x180004e27  call    ?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionDestroy(DEVICE_COLLECTION *)
0x180004e2c  mov     eax, ebx
0x180004e2e  jmp     short loc_180004E35
0x180004e30  mov     eax, 1
0x180004e35  mov     rcx, [rbp+1C0h+var_10]
0x180004e3c  xor     rcx, rsp; StackCookie
0x180004e3f  call    __security_check_cookie
0x180004e44  lea     r11, [rsp+2C0h+var_s0]
0x180004e4c  mov     rbx, [r11+10h]
0x180004e50  mov     rdi, [r11+18h]
0x180004e54  mov     rsp, r11
0x180004e57  pop     rbp
0x180004e58  retn
```
