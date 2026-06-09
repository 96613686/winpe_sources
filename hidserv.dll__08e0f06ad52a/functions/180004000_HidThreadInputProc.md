# HidThreadInputProc

- ea: `0x180004000`
- end: `0x180004302`
- name: `HidThreadInputProc`
- size: `770`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800025e0`
- `0x180004000`
- `0x1800051b4`
- `0x180005280`
- `0x18000841e`
- `0x180008450`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800042c0`
- `KERNEL32!CloseHandle` at `0x1800042cd`
- `KERNEL32!CloseHandle` at `0x1800042da`
- `KERNEL32!CloseHandle` at `0x1800042c0`
- `KERNEL32!CloseHandle` at `0x1800042cd`
- `KERNEL32!CloseHandle` at `0x1800042da`
- `KERNEL32!WaitForMultipleObjects` at `0x18000406f`
- `KERNEL32!WaitForMultipleObjects` at `0x1800042a0`
- `KERNEL32!WaitForMultipleObjects` at `0x18000406f`
- `KERNEL32!WaitForMultipleObjects` at `0x1800042a0`
- `KERNEL32!GetLastError` at `0x180004267`
- `KERNEL32!GetLastError` at `0x180004267`
- `KERNEL32!SetEvent` at `0x18000428b`
- `KERNEL32!SetEvent` at `0x18000428b`
- `USER32!SendInput` at `0x1800041b8`
- `USER32!SendInput` at `0x1800041b8`
- `USER32!GetGUIThreadInfo` at `0x1800041d0`
- `USER32!GetGUIThreadInfo` at `0x1800041d0`
- `USER32!SendNotifyMessageW` at `0x180004243`
- `USER32!SendNotifyMessageW` at `0x180004243`

## pseudocode

```c
__int64 __fastcall HidThreadInputProc(PVOID Parameter)
{
  DWORD v1; // eax
  int v2; // r8d
  const char *v3; // rax
  const char *v4; // rax
  HWND hwndActive; // rbx
  __int64 v6; // rbx
  DWORD LastError; // eax
  tagINPUT pInputs; // [rsp+30h] [rbp-69h] BYREF
  HANDLE Handles[3]; // [rsp+58h] [rbp-41h] BYREF
  tagGUITHREADINFO pgui; // [rsp+70h] [rbp-29h] BYREF

  memset_0(&pgui, 0, sizeof(pgui));
  memset(&pInputs, 0, 36);
  _InterlockedIncrement(&cThreadRef);
  Handles[0] = hDesktopSwitch;
  Handles[1] = hInputEvent;
  v1 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
  if ( InputThreadEnabled )
  {
    while ( !v1 )
    {
LABEL_33:
      v1 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
      if ( !InputThreadEnabled )
        goto LABEL_34;
    }
    switch ( InputType )
    {
      case 0:
        pgui.cbSize = 72;
        if ( GetGUIThreadInfo(0, &pgui) )
        {
          hwndActive = pgui.hwndActive;
          if ( pgui.hwndFocus )
            hwndActive = pgui.hwndFocus;
          if ( hwndActive )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                16,
                WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids,
                (unsigned __int16)InputAppCommand);
            }
            SendNotifyMessageW(
              hwndActive,
              0x319u,
              (WPARAM)hwndActive,
              ((unsigned __int16)InputAppCommand | 0x1000LL) << 16);
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v6 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            LastError = GetLastError();
            WPP_SF_D(v6, 17, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, LastError);
          }
        }
        goto LABEL_32;
      case 1:
        memset(&pInputs, 0, sizeof(pInputs));
        pInputs.type = 1;
        pInputs.ki.wVk = (unsigned __int8)InputVKey;
        pInputs.mi.dy = (IsKeyDown == 0 ? 2 : 0) | 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v4 = "down";
          if ( !IsKeyDown )
            v4 = "up";
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned __int16)IsKeyDown,
            (unsigned __int8)InputVKey,
            (unsigned __int8)InputVKey,
            (__int64)v4);
        }
        break;
      case 2:
        memset(&pInputs, 0, sizeof(pInputs));
        pInputs.type = 1;
        pInputs.ki.wScan = (unsigned __int8)InputVKey;
        pInputs.mi.dy = (IsKeyDown == 0 ? 2 : 0) | 4;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v3 = "down";
          if ( !IsKeyDown )
            v3 = "up";
          WPP_SF_cs(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned __int16)IsKeyDown,
            v2,
            (unsigned int)"up",
            (__int64)v3);
        }
        break;
      default:
LABEL_32:
        SetEvent(hInputDoneEvent);
        goto LABEL_33;
    }
    SendInput(1u, &pInputs, 40);
    goto LABEL_32;
  }
LABEL_34:
  CloseHandle(hDesktopSwitch);
  CloseHandle(hInputEvent);
  CloseHandle(hInputDoneEvent);
  _InterlockedDecrement(&cThreadRef);
  return 0;
}

```

## disassembly

```asm
0x180004000  push    rbp
0x180004002  push    rbx
0x180004003  push    rdi
0x180004004  push    r14
0x180004006  lea     rbp, [rsp-3Fh]
0x18000400b  sub     rsp, 0D8h
0x180004012  mov     rax, cs:__security_cookie
0x180004019  xor     rax, rsp
0x18000401c  mov     [rbp+57h+var_30], rax
0x180004020  xor     edx, edx; Val
0x180004022  lea     rcx, [rbp+57h+pgui]; void *
0x180004026  lea     r8d, [rdx+48h]; Size
0x18000402a  call    memset_0
0x18000402f  xorps   xmm0, xmm0
0x180004032  xor     eax, eax
0x180004034  movups  xmmword ptr [rbp+57h+pInputs.type], xmm0
0x180004038  mov     dword ptr [rbp+57h+pInputs.8+18h], eax
0x18000403b  movups  xmmword ptr [rbp+57h+pInputs.8+8], xmm0
0x18000403f  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x180004043  lock inc cs:cThreadRef
0x18000404a  mov     rax, cs:hDesktopSwitch
0x180004051  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180004055  xor     r8d, r8d; bWaitAll
0x180004058  mov     [rbp+57h+Handles], rax
0x18000405c  mov     rax, cs:hInputEvent
0x180004063  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180004067  mov     [rbp+57h+Handles+8], rax
0x18000406b  lea     ecx, [r8+2]; nCount
0x18000406f  call    cs:__imp_WaitForMultipleObjects
0x180004075  xor     edi, edi
0x180004077  cmp     cs:InputThreadEnabled, edi
0x18000407d  jz      loc_1800042B9
0x180004083  lea     r14, WPP_GLOBAL_Control
0x18000408a  lea     r9, aUp; "up"
0x180004091  test    eax, eax
0x180004093  jz      loc_180004291
0x180004099  mov     ecx, cs:InputType
0x18000409f  test    ecx, ecx
0x1800040a1  jz      loc_1800041C3
0x1800040a7  sub     ecx, 1
0x1800040aa  jz      loc_180004134
0x1800040b0  cmp     ecx, 1
0x1800040b3  jnz     loc_180004284
0x1800040b9  movzx   edx, cs:IsKeyDown
0x1800040c0  xor     eax, eax
0x1800040c2  mov     qword ptr [rbp+57h+pInputs.8+18h], rax
0x1800040c6  xorps   xmm0, xmm0
0x1800040c9  movups  xmmword ptr [rbp+57h+pInputs.type], xmm0
0x1800040cd  mov     [rbp+57h+pInputs.type], ecx
0x1800040d0  movzx   eax, dx
0x1800040d3  neg     ax
0x1800040d6  movzx   eax, cs:InputVKey
0x1800040dd  sbb     ecx, ecx
0x1800040df  mov     word ptr [rbp+57h+pInputs.8+2], ax
0x1800040e3  not     ecx
0x1800040e5  and     ecx, 2
0x1800040e8  or      ecx, 4
0x1800040eb  mov     dword ptr [rbp+57h+pInputs.8+4], ecx
0x1800040ee  movups  xmmword ptr [rbp+57h+pInputs.8+8], xmm0
0x1800040f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040f9  cmp     rcx, r14
0x1800040fc  jz      loc_1800041AA
0x180004102  test    byte ptr [rcx+1Ch], 10h
0x180004106  jz      loc_1800041AA
0x18000410c  cmp     byte ptr [rcx+19h], 5
0x180004110  jb      loc_1800041AA
0x180004116  mov     rcx, [rcx+10h]
0x18000411a  lea     rax, aDown; "down"
0x180004121  test    dx, dx
0x180004124  cmovz   rax, r9
0x180004128  mov     [rsp+0F0h+var_D0], rax
0x18000412d  call    WPP_SF_cs
0x180004132  jmp     short loc_1800041AA
0x180004134  movzx   edx, cs:IsKeyDown
0x18000413b  xor     eax, eax
0x18000413d  movzx   r8d, cs:InputVKey
0x180004145  xorps   xmm0, xmm0
0x180004148  movups  xmmword ptr [rbp+57h+pInputs.type], xmm0
0x18000414c  mov     qword ptr [rbp+57h+pInputs.8+18h], rax
0x180004150  movzx   eax, dx
0x180004153  neg     ax
0x180004156  mov     [rbp+57h+pInputs.type], 1
0x18000415d  movups  xmmword ptr [rbp+57h+pInputs.8+8], xmm0
0x180004161  sbb     ecx, ecx
0x180004163  mov     word ptr [rbp+57h+pInputs.8], r8w
0x180004168  not     ecx
0x18000416a  and     ecx, 2
0x18000416d  or      ecx, 1
0x180004170  mov     dword ptr [rbp+57h+pInputs.8+4], ecx
0x180004173  mov     rcx, cs:WPP_GLOBAL_Control
0x18000417a  cmp     rcx, r14
0x18000417d  jz      short loc_1800041AA
0x18000417f  test    byte ptr [rcx+1Ch], 10h
0x180004183  jz      short loc_1800041AA
0x180004185  cmp     byte ptr [rcx+19h], 5
0x180004189  jb      short loc_1800041AA
0x18000418b  mov     rcx, [rcx+10h]
0x18000418f  lea     rax, aDown; "down"
0x180004196  test    dx, dx
0x180004199  cmovz   rax, r9
0x18000419d  mov     r9d, r8d
0x1800041a0  mov     [rsp+0F0h+var_D0], rax
0x1800041a5  call    WPP_SF_Ds
0x1800041aa  mov     r8d, 28h ; '('; cbSize
0x1800041b0  lea     rdx, [rbp+57h+pInputs]; pInputs
0x1800041b4  lea     ecx, [r8-27h]; cInputs
0x1800041b8  call    cs:__imp_SendInput
0x1800041be  jmp     loc_180004284
0x1800041c3  lea     rdx, [rbp+57h+pgui]; pgui
0x1800041c7  mov     [rbp+57h+pgui.cbSize], 48h ; 'H'
0x1800041ce  xor     ecx, ecx; idThread
0x1800041d0  call    cs:__imp_GetGUIThreadInfo
0x1800041d6  test    eax, eax
0x1800041d8  jz      loc_180004284
0x1800041de  mov     rax, [rbp+57h+pgui.hwndFocus]
0x1800041e2  mov     rbx, [rbp+57h+pgui.hwndActive]
0x1800041e6  test    rax, rax
0x1800041e9  cmovnz  rbx, rax
0x1800041ed  test    rbx, rbx
0x1800041f0  jz      short loc_18000424B
0x1800041f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800041f9  cmp     rcx, r14
0x1800041fc  jz      short loc_180004227
0x1800041fe  test    byte ptr [rcx+1Ch], 10h
0x180004202  jz      short loc_180004227
0x180004204  cmp     byte ptr [rcx+19h], 5
0x180004208  jb      short loc_180004227
0x18000420a  movzx   r9d, cs:InputAppCommand
0x180004212  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x180004219  mov     rcx, [rcx+10h]
0x18000421d  mov     edx, 10h
0x180004222  call    WPP_SF_D
0x180004227  movzx   r9d, cs:InputAppCommand
0x18000422f  mov     r8, rbx; wParam
0x180004232  bts     r9, 0Ch
0x180004237  mov     edx, 319h; Msg
0x18000423c  shl     r9, 10h; lParam
0x180004240  mov     rcx, rbx; hWnd
0x180004243  call    cs:__imp_SendNotifyMessageW
0x180004249  jmp     short loc_180004284
0x18000424b  mov     rbx, cs:WPP_GLOBAL_Control
0x180004252  cmp     rbx, r14
0x180004255  jz      short loc_180004284
0x180004257  test    byte ptr [rbx+1Ch], 10h
0x18000425b  jz      short loc_180004284
0x18000425d  cmp     byte ptr [rbx+19h], 3
0x180004261  jb      short loc_180004284
0x180004263  mov     rbx, [rbx+10h]
0x180004267  call    cs:__imp_GetLastError
0x18000426d  mov     edx, 11h
0x180004272  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x180004279  mov     r9d, eax
0x18000427c  mov     rcx, rbx
0x18000427f  call    WPP_SF_D
0x180004284  mov     rcx, cs:hInputDoneEvent; hEvent
0x18000428b  call    cs:__imp_SetEvent
0x180004291  xor     r8d, r8d; bWaitAll
0x180004294  lea     rdx, [rbp+57h+Handles]; lpHandles
0x180004298  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000429c  lea     ecx, [r8+2]; nCount
0x1800042a0  call    cs:__imp_WaitForMultipleObjects
0x1800042a6  cmp     cs:InputThreadEnabled, edi
0x1800042ac  lea     r9, aUp; "up"
0x1800042b3  jnz     loc_180004091
0x1800042b9  mov     rcx, cs:hDesktopSwitch; hObject
0x1800042c0  call    cs:__imp_CloseHandle
0x1800042c6  mov     rcx, cs:hInputEvent; hObject
0x1800042cd  call    cs:__imp_CloseHandle
0x1800042d3  mov     rcx, cs:hInputDoneEvent; hObject
0x1800042da  call    cs:__imp_CloseHandle
0x1800042e0  lock dec cs:cThreadRef
0x1800042e7  xor     eax, eax
0x1800042e9  mov     rcx, [rbp+57h+var_30]
0x1800042ed  xor     rcx, rsp; StackCookie
0x1800042f0  call    __security_check_cookie
0x1800042f5  add     rsp, 0D8h
0x1800042fc  pop     r14
0x1800042fe  pop     rdi
0x1800042ff  pop     rbx
0x180004300  pop     rbp
0x180004301  retn
```
