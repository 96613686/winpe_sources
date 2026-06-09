# HotPlugDriverBlockedW(HWND__ *,HINSTANCE__ *,ushort const *,int)

- ea: `0x180004e60`
- end: `0x1800050a8`
- name: `?HotPlugDriverBlockedW@@YAKPEAUHWND__@@PEAUHINSTANCE__@@PEBGH@Z`
- size: `584`
- prototype: `__int64 __fastcall(HWND, HINSTANCE, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180002c74`
- `0x180002d70`
- `0x180003048`
- `0x180004e60`
- `0x180006338`
- `0x180006a68`
- `0x180008760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180004ef1`
- `KERNEL32!CloseHandle` at `0x180004f07`
- `KERNEL32!CloseHandle` at `0x18000505d`
- `KERNEL32!CloseHandle` at `0x18000506b`
- `KERNEL32!CloseHandle` at `0x180004ef1`
- `KERNEL32!CloseHandle` at `0x180004f07`
- `KERNEL32!CloseHandle` at `0x18000505d`
- `KERNEL32!CloseHandle` at `0x18000506b`
- `KERNEL32!SetEvent` at `0x180004efc`
- `KERNEL32!SetEvent` at `0x180005042`
- `KERNEL32!SetEvent` at `0x180005052`
- `KERNEL32!SetEvent` at `0x180004efc`
- `KERNEL32!SetEvent` at `0x180005042`
- `KERNEL32!SetEvent` at `0x180005052`
- `KERNEL32!CreateEventW` at `0x180004f7c`
- `KERNEL32!CreateEventW` at `0x180004fab`
- `KERNEL32!CreateEventW` at `0x180004f7c`
- `KERNEL32!CreateEventW` at `0x180004fab`
- `KERNEL32!WaitForSingleObject` at `0x180004f8f`
- `KERNEL32!WaitForSingleObject` at `0x180004f8f`
- `USER32!SetProcessDPIAware` at `0x180004eb6`
- `USER32!SetProcessDPIAware` at `0x180004eb6`
- `USER32!TranslateMessage` at `0x180004fe4`
- `USER32!TranslateMessage` at `0x180004fe4`
- `USER32!PeekMessageW` at `0x180005006`
- `USER32!PeekMessageW` at `0x180005006`
- `USER32!DispatchMessageW` at `0x180004fef`
- `USER32!DispatchMessageW` at `0x180004fef`
- `USER32!MsgWaitForMultipleObjects` at `0x180005026`
- `USER32!MsgWaitForMultipleObjects` at `0x180005026`

## pseudocode

```c
__int64 __fastcall HotPlugDriverBlockedW(HWND a1, HINSTANCE a2, const unsigned __int16 *a3)
{
  int v4; // ebx
  void *v5; // rdi
  const wchar_t *v6; // r9
  HANDLE EventW; // rax
  DWORD v8; // eax
  HANDLE pHandles; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hEvent; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+58h] [rbp-A8h]
  MSG Msg; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  hObject = 0;
  v13 = 0;
  hEvent = 0;
  v14 = 0;
  pHandles = 0;
  SetProcessDPIAware();
  if ( !OpenPipeAndEventHandles(a3, &hObject, &hEvent) )
    return 1;
  v4 = DeviceCollectionBuildFromPipe(hObject, 3, (__int64)&v13);
  CloseHandle(hObject);
  SetEvent(hEvent);
  CloseHandle(hEvent);
  if ( !v4 )
    return 1;
  v5 = 0;
  if ( (_DWORD)v14 == 1 )
  {
    v6 = 0;
    if ( (__int128 *)v13 != &v13 )
      v6 = (const wchar_t *)(v13 + 16);
  }
  else
  {
    v6 = L"ALL";
  }
  if ( (int)StringCchPrintfW(Name, 0x104u, L"Local\\DRIVERBLOCK-%s", v6) < 0
    || (EventW = CreateEventW(0, 0, 1, Name), (v5 = EventW) == 0)
    || !WaitForSingleObject(EventW, 0) )
  {
    pHandles = CreateEventW(0, 0, 1, L"Local\\HotPlug_DriverBlockedIcon_Event");
    if ( pHandles )
    {
      while ( 1 )
      {
        v8 = MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu);
        if ( !v8 )
          break;
        if ( v8 != 1 )
          goto LABEL_21;
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 16 )
            goto LABEL_21;
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
    }
    DisplayDriverBlockBalloon((struct DEVICE_COLLECTION **)&v13);
    if ( v5 )
      SetEvent(v5);
  }
LABEL_21:
  if ( pHandles )
  {
    SetEvent(pHandles);
    CloseHandle(pHandles);
  }
  if ( v5 )
    CloseHandle(v5);
  DeviceCollectionDestroy((struct DEVICE_COLLECTION *)&v13);
  return 1;
}

```

## disassembly

```asm
0x180004e60  mov     [rsp-8+arg_0], rbx
0x180004e65  mov     [rsp-8+arg_8], rdi
0x180004e6a  push    rbp
0x180004e6b  lea     rbp, [rsp-1C0h]
0x180004e73  sub     rsp, 2C0h
0x180004e7a  mov     rax, cs:__security_cookie
0x180004e81  xor     rax, rsp
0x180004e84  mov     [rbp+1C0h+var_10], rax
0x180004e8b  xorps   xmm0, xmm0
0x180004e8e  mov     [rsp+2C0h+hObject], 0
0x180004e97  movups  [rsp+2C0h+var_278], xmm0
0x180004e9c  mov     rbx, r8
0x180004e9f  mov     [rsp+2C0h+hEvent], 0
0x180004ea8  movups  [rsp+2C0h+var_268], xmm0
0x180004ead  mov     [rsp+2C0h+pHandles], 0
0x180004eb6  call    cs:__imp_SetProcessDPIAware
0x180004ebc  lea     r8, [rsp+2C0h+hEvent]; void **
0x180004ec1  mov     rcx, rbx; lpFileName
0x180004ec4  lea     rdx, [rsp+2C0h+hObject]; void **
0x180004ec9  call    ?OpenPipeAndEventHandles@@YAHPEBGPEAPEAX1@Z; OpenPipeAndEventHandles(ushort const *,void * *,void * *)
0x180004ece  test    eax, eax
0x180004ed0  jz      loc_18000507F
0x180004ed6  mov     rcx, [rsp+2C0h+hObject]
0x180004edb  lea     r8, [rsp+2C0h+var_278]
0x180004ee0  mov     edx, 3
0x180004ee5  call    ?DeviceCollectionBuildFromPipe@@YAHPEAXW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z; DeviceCollectionBuildFromPipe(void *,_COLLECTION_TYPE,DEVICE_COLLECTION *)
0x180004eea  mov     rcx, [rsp+2C0h+hObject]; hObject
0x180004eef  mov     ebx, eax
0x180004ef1  call    cs:__imp_CloseHandle
0x180004ef7  mov     rcx, [rsp+2C0h+hEvent]; hEvent
0x180004efc  call    cs:__imp_SetEvent
0x180004f02  mov     rcx, [rsp+2C0h+hEvent]; hObject
0x180004f07  call    cs:__imp_CloseHandle
0x180004f0d  test    ebx, ebx
0x180004f0f  jz      loc_18000507F
0x180004f15  xor     edi, edi
0x180004f17  lea     ebx, [rdi+1]
0x180004f1a  cmp     dword ptr [rsp+2C0h+var_268], ebx
0x180004f1e  jnz     short loc_180004F51
0x180004f20  mov     rcx, qword ptr [rsp+2C0h+var_278]
0x180004f25  xor     eax, eax
0x180004f27  jmp     short loc_180004F32
0x180004f29  test    eax, eax
0x180004f2b  jz      short loc_180004F3C
0x180004f2d  mov     rcx, [rcx]
0x180004f30  add     eax, ebx
0x180004f32  lea     rdx, [rsp+2C0h+var_278]
0x180004f37  cmp     rcx, rdx
0x180004f3a  jnz     short loc_180004F29
0x180004f3c  xor     r9d, r9d
0x180004f3f  lea     rdx, [rsp+2C0h+var_278]
0x180004f44  cmp     rcx, rdx
0x180004f47  lea     rax, [rcx+10h]
0x180004f4b  cmovnz  r9, rax
0x180004f4f  jmp     short loc_180004F58
0x180004f51  lea     r9, aAll; "ALL"
0x180004f58  lea     r8, aLocalDriverblo; "Local\\DRIVERBLOCK-%s"
0x180004f5f  mov     edx, 104h; unsigned __int64
0x180004f64  lea     rcx, [rbp+1C0h+Name]; unsigned __int16 *
0x180004f68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004f6d  test    eax, eax
0x180004f6f  js      short loc_180004F9D
0x180004f71  lea     r9, [rbp+1C0h+Name]; lpName
0x180004f75  mov     r8d, ebx; bInitialState
0x180004f78  xor     edx, edx; bManualReset
0x180004f7a  xor     ecx, ecx; lpEventAttributes
0x180004f7c  call    cs:__imp_CreateEventW
0x180004f82  mov     rdi, rax
0x180004f85  test    rax, rax
0x180004f88  jz      short loc_180004F9D
0x180004f8a  xor     edx, edx; dwMilliseconds
0x180004f8c  mov     rcx, rax; hHandle
0x180004f8f  call    cs:__imp_WaitForSingleObject
0x180004f95  test    eax, eax
0x180004f97  jnz     loc_180005048
0x180004f9d  lea     r9, aLocalHotplugDr; "Local\\HotPlug_DriverBlockedIcon_Event"
0x180004fa4  mov     r8d, ebx; bInitialState
0x180004fa7  xor     edx, edx; bManualReset
0x180004fa9  xor     ecx, ecx; lpEventAttributes
0x180004fab  call    cs:__imp_CreateEventW
0x180004fb1  mov     [rsp+2C0h+pHandles], rax
0x180004fb6  test    rax, rax
0x180004fb9  jz      short loc_180005030
0x180004fbb  jmp     short loc_180005010
0x180004fbd  cmp     eax, ebx
0x180004fbf  jnz     loc_180005048
0x180004fc5  xorps   xmm0, xmm0
0x180004fc8  movups  xmmword ptr [rsp+2C0h+Msg.hwnd], xmm0
0x180004fcd  movups  xmmword ptr [rsp+2C0h+Msg.wParam], xmm0
0x180004fd2  movups  xmmword ptr [rbp+1C0h+Msg.time], xmm0
0x180004fd6  jmp     short loc_180004FF5
0x180004fd8  cmp     [rsp+2C0h+Msg.message], 10h
0x180004fdd  jz      short loc_180005048
0x180004fdf  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180004fe4  call    cs:__imp_TranslateMessage
0x180004fea  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180004fef  call    cs:__imp_DispatchMessageW
0x180004ff5  xor     r9d, r9d; wMsgFilterMax
0x180004ff8  mov     [rsp+2C0h+wRemoveMsg], ebx; wRemoveMsg
0x180004ffc  xor     r8d, r8d; wMsgFilterMin
0x180004fff  lea     rcx, [rsp+2C0h+Msg]; lpMsg
0x180005004  xor     edx, edx; hWnd
0x180005006  call    cs:__imp_PeekMessageW
0x18000500c  test    eax, eax
0x18000500e  jnz     short loc_180004FD8
0x180005010  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180005014  mov     [rsp+2C0h+wRemoveMsg], 1CFFh; dwWakeMask
0x18000501c  xor     r8d, r8d; fWaitAll
0x18000501f  lea     rdx, [rsp+2C0h+pHandles]; pHandles
0x180005024  mov     ecx, ebx; nCount
0x180005026  call    cs:__imp_MsgWaitForMultipleObjects
0x18000502c  test    eax, eax
0x18000502e  jnz     short loc_180004FBD
0x180005030  lea     rcx, [rsp+2C0h+var_278]; struct DEVICE_COLLECTION *
0x180005035  call    ?DisplayDriverBlockBalloon@@YAXPEAUDEVICE_COLLECTION@@@Z; DisplayDriverBlockBalloon(DEVICE_COLLECTION *)
0x18000503a  test    rdi, rdi
0x18000503d  jz      short loc_180005048
0x18000503f  mov     rcx, rdi; hEvent
0x180005042  call    cs:__imp_SetEvent
0x180005048  mov     rcx, [rsp+2C0h+pHandles]; hEvent
0x18000504d  test    rcx, rcx
0x180005050  jz      short loc_180005063
0x180005052  call    cs:__imp_SetEvent
0x180005058  mov     rcx, [rsp+2C0h+pHandles]; hObject
0x18000505d  call    cs:__imp_CloseHandle
0x180005063  test    rdi, rdi
0x180005066  jz      short loc_180005071
0x180005068  mov     rcx, rdi; hObject
0x18000506b  call    cs:__imp_CloseHandle
0x180005071  lea     rcx, [rsp+2C0h+var_278]; struct DEVICE_COLLECTION *
0x180005076  call    ?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionDestroy(DEVICE_COLLECTION *)
0x18000507b  mov     eax, ebx
0x18000507d  jmp     short loc_180005084
0x18000507f  mov     eax, 1
0x180005084  mov     rcx, [rbp+1C0h+var_10]
0x18000508b  xor     rcx, rsp; StackCookie
0x18000508e  call    __security_check_cookie
0x180005093  lea     r11, [rsp+2C0h+var_s0]
0x18000509b  mov     rbx, [r11+10h]
0x18000509f  mov     rdi, [r11+18h]
0x1800050a3  mov     rsp, r11
0x1800050a6  pop     rbp
0x1800050a7  retn
```
