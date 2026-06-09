# StartHidDevice

- ea: `0x18000674c`
- end: `0x18000696f`
- name: `StartHidDevice`
- size: `547`
- prototype: `__int64 __fastcall(unsigned __int64 *lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006460`

## callees

- `0x1800025b8`
- `0x1800025e0`
- `0x18000674c`
- `0x180008450`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180006772`
- `KERNEL32!CreateEventW` at `0x1800067cb`
- `KERNEL32!CreateEventW` at `0x180006772`
- `KERNEL32!CreateEventW` at `0x1800067cb`
- `KERNEL32!CloseHandle` at `0x180006818`
- `KERNEL32!CloseHandle` at `0x1800068a0`
- `KERNEL32!CloseHandle` at `0x180006818`
- `KERNEL32!CloseHandle` at `0x1800068a0`
- `KERNEL32!CreateThread` at `0x180006853`
- `KERNEL32!CreateThread` at `0x180006853`
- `KERNEL32!GetLastError` at `0x180006925`
- `KERNEL32!GetLastError` at `0x180006925`
- `KERNEL32!SetEvent` at `0x180006949`
- `KERNEL32!SetEvent` at `0x180006949`
- `USER32!RegisterDeviceNotificationW` at `0x1800068f3`
- `USER32!RegisterDeviceNotificationW` at `0x1800068f3`

## pseudocode

```c
__int64 __fastcall StartHidDevice(unsigned __int64 *lpParameter)
{
  HANDLE EventW; // rax
  __int64 v3; // r9
  HANDLE v5; // rax
  __int64 v6; // r9
  void *v7; // rcx
  HANDLE Thread; // rax
  __int64 v9; // r9
  HDEVNOTIFY v10; // rax
  __int64 v11; // rbx
  DWORD LastError; // eax
  _OWORD NotificationFilter[3]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v14; // [rsp+60h] [rbp-18h]

  EventW = CreateEventW(0, 0, 0, 0);
  lpParameter[19] = (unsigned __int64)EventW;
  if ( !EventW )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v3);
    }
    return 0;
  }
  v5 = CreateEventW(0, 1, 1, 0);
  lpParameter[20] = (unsigned __int64)v5;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v6);
    }
    v7 = (void *)lpParameter[19];
LABEL_13:
    CloseHandle(v7);
    return 0;
  }
  lpParameter[18] = (unsigned __int64)v5;
  *((_DWORD *)lpParameter + 42) = 1;
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)HidThreadProc, lpParameter, 0, (LPDWORD)lpParameter + 43);
  lpParameter[22] = (unsigned __int64)Thread;
  if ( !Thread )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v9);
    }
    CloseHandle((HANDLE)lpParameter[19]);
    v7 = (void *)lpParameter[20];
    goto LABEL_13;
  }
  NotificationFilter[0] = 0;
  v14 = 0;
  NotificationFilter[1] = lpParameter[1];
  NotificationFilter[2] = 0;
  *(_QWORD *)&NotificationFilter[0] = 0x600000038LL;
  v10 = RegisterDeviceNotificationW(hWndHidServ, NotificationFilter, 0);
  lpParameter[14] = (unsigned __int64)v10;
  if ( !v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_D(v11, 44, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, LastError);
  }
  SetEvent((HANDLE)lpParameter[19]);
  return 1;
}

```

## disassembly

```asm
0x18000674c  mov     [rsp+arg_8], rbx
0x180006751  push    rdi
0x180006752  sub     rsp, 70h
0x180006756  mov     rax, cs:__security_cookie
0x18000675d  xor     rax, rsp
0x180006760  mov     [rsp+78h+var_10], rax
0x180006765  mov     rdi, rcx
0x180006768  xor     r9d, r9d; lpName
0x18000676b  xor     ecx, ecx; lpEventAttributes
0x18000676d  xor     r8d, r8d; bInitialState
0x180006770  xor     edx, edx; bManualReset
0x180006772  call    cs:__imp_CreateEventW
0x180006778  mov     [rdi+98h], rax
0x18000677f  test    rax, rax
0x180006782  jnz     short loc_1800067BF
0x180006784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000678b  lea     rax, WPP_GLOBAL_Control
0x180006792  cmp     rcx, rax
0x180006795  jz      short loc_1800067B8
0x180006797  test    byte ptr [rcx+1Ch], 2
0x18000679b  jz      short loc_1800067B8
0x18000679d  cmp     byte ptr [rcx+19h], 2
0x1800067a1  jb      short loc_1800067B8
0x1800067a3  mov     rcx, [rcx+10h]
0x1800067a7  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x1800067ae  mov     edx, 29h ; ')'
0x1800067b3  call    WPP_SF_
0x1800067b8  xor     eax, eax
0x1800067ba  jmp     loc_180006954
0x1800067bf  xor     r9d, r9d; lpName
0x1800067c2  xor     ecx, ecx; lpEventAttributes
0x1800067c4  lea     edx, [r9+1]; bManualReset
0x1800067c8  mov     r8d, edx; bInitialState
0x1800067cb  call    cs:__imp_CreateEventW
0x1800067d1  mov     [rdi+0A0h], rax
0x1800067d8  test    rax, rax
0x1800067db  jnz     short loc_180006820
0x1800067dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067e4  lea     rax, WPP_GLOBAL_Control
0x1800067eb  cmp     rcx, rax
0x1800067ee  jz      short loc_180006811
0x1800067f0  test    byte ptr [rcx+1Ch], 2
0x1800067f4  jz      short loc_180006811
0x1800067f6  cmp     byte ptr [rcx+19h], 2
0x1800067fa  jb      short loc_180006811
0x1800067fc  mov     rcx, [rcx+10h]
0x180006800  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x180006807  mov     edx, 2Ah ; '*'
0x18000680c  call    WPP_SF_
0x180006811  mov     rcx, [rdi+98h]; hObject
0x180006818  call    cs:__imp_CloseHandle
0x18000681e  jmp     short loc_1800067B8
0x180006820  mov     [rdi+90h], rax
0x180006827  lea     r8, HidThreadProc; lpStartAddress
0x18000682e  lea     rax, [rdi+0ACh]
0x180006835  mov     dword ptr [rdi+0A8h], 1
0x18000683f  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x180006844  mov     r9, rdi; lpParameter
0x180006847  xor     edx, edx; dwStackSize
0x180006849  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180006851  xor     ecx, ecx; lpThreadAttributes
0x180006853  call    cs:__imp_CreateThread
0x180006859  mov     [rdi+0B0h], rax
0x180006860  test    rax, rax
0x180006863  jnz     short loc_1800068B2
0x180006865  mov     rcx, cs:WPP_GLOBAL_Control
0x18000686c  lea     rax, WPP_GLOBAL_Control
0x180006873  cmp     rcx, rax
0x180006876  jz      short loc_180006899
0x180006878  test    byte ptr [rcx+1Ch], 2
0x18000687c  jz      short loc_180006899
0x18000687e  cmp     byte ptr [rcx+19h], 2
0x180006882  jb      short loc_180006899
0x180006884  mov     rcx, [rcx+10h]
0x180006888  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x18000688f  mov     edx, 2Bh ; '+'
0x180006894  call    WPP_SF_
0x180006899  mov     rcx, [rdi+98h]; hObject
0x1800068a0  call    cs:__imp_CloseHandle
0x1800068a6  mov     rcx, [rdi+0A0h]
0x1800068ad  jmp     loc_180006818
0x1800068b2  mov     rcx, cs:hWndHidServ; hRecipient
0x1800068b9  lea     rdx, [rsp+78h+NotificationFilter]; NotificationFilter
0x1800068be  xorps   xmm0, xmm0
0x1800068c1  xor     eax, eax
0x1800068c3  movups  [rsp+78h+NotificationFilter], xmm0
0x1800068c8  mov     [rsp+78h+var_18], rax
0x1800068cd  xor     r8d, r8d; Flags
0x1800068d0  mov     rax, [rdi+8]
0x1800068d4  movups  [rsp+78h+var_38], xmm0
0x1800068d9  mov     qword ptr [rsp+78h+var_38], rax
0x1800068de  movups  [rsp+78h+var_28], xmm0
0x1800068e3  mov     dword ptr [rsp+78h+NotificationFilter], 38h ; '8'
0x1800068eb  mov     dword ptr [rsp+78h+NotificationFilter+4], 6
0x1800068f3  call    cs:__imp_RegisterDeviceNotificationW
0x1800068f9  mov     [rdi+70h], rax
0x1800068fd  test    rax, rax
0x180006900  jnz     short loc_180006942
0x180006902  mov     rbx, cs:WPP_GLOBAL_Control
0x180006909  lea     rax, WPP_GLOBAL_Control
0x180006910  cmp     rbx, rax
0x180006913  jz      short loc_180006942
0x180006915  test    byte ptr [rbx+1Ch], 2
0x180006919  jz      short loc_180006942
0x18000691b  cmp     byte ptr [rbx+19h], 2
0x18000691f  jb      short loc_180006942
0x180006921  mov     rbx, [rbx+10h]
0x180006925  call    cs:__imp_GetLastError
0x18000692b  mov     edx, 2Ch ; ','
0x180006930  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x180006937  mov     r9d, eax
0x18000693a  mov     rcx, rbx
0x18000693d  call    WPP_SF_D
0x180006942  mov     rcx, [rdi+98h]; hEvent
0x180006949  call    cs:__imp_SetEvent
0x18000694f  mov     eax, 1
0x180006954  mov     rcx, [rsp+78h+var_10]
0x180006959  xor     rcx, rsp; StackCookie
0x18000695c  call    __security_check_cookie
0x180006961  mov     rbx, [rsp+78h+arg_8]
0x180006969  add     rsp, 70h
0x18000696d  pop     rdi
0x18000696e  retn
```
