# COSKKeyboardManager::HandleNormalKeyAction(tagKEYSTATE,tagKEYPAYLOAD,ushort *,HWND__ *)

- ea: `0x140011178`
- end: `0x140011361`
- name: `?HandleNormalKeyAction@COSKKeyboardManager@@AEAAXW4tagKEYSTATE@@UtagKEYPAYLOAD@@PEAGPEAUHWND__@@@Z`
- size: `489`
- prototype: `void __high(enum tagKEYSTATE, struct tagKEYPAYLOAD, unsigned __int16 *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400121e0`

## callees

- `0x140002de3`
- `0x14000dd8c`
- `0x140011178`
- `0x140025d70`

## import_xrefs

- `USER32!GetGUIThreadInfo` at `0x140011298`
- `USER32!GetGUIThreadInfo` at `0x140011298`
- `USER32!SetTimer` at `0x14001133d`
- `USER32!SetTimer` at `0x14001133d`
- `USER32!PostMessageW` at `0x14001125d`
- `USER32!PostMessageW` at `0x14001125d`
- `USER32!MapVirtualKeyExW` at `0x140011218`
- `USER32!MapVirtualKeyExW` at `0x140011218`
- `USER32!GetCursorInfo` at `0x1400112fe`
- `USER32!GetCursorInfo` at `0x1400112fe`
- `USER32!LoadCursorW` at `0x14001130f`
- `USER32!LoadCursorW` at `0x14001130f`
- `OLEAUT32!__imp_SysStringLen` at `0x1400111dc`
- `OLEAUT32!__imp_SysStringLen` at `0x1400111dc`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140011326`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140011326`

## pseudocode

```c
void __fastcall COSKKeyboardManager::HandleNormalKeyAction(__int64 a1, int a2, __int64 a3, OLECHAR *a4, HWND hWnd)
{
  unsigned __int16 v8; // ax
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned __int16 v11; // bx
  unsigned int v12; // eax
  int v13; // ecx
  HCURSOR CursorW; // rax
  HWND v15; // rax
  struct tagGUITHREADINFO pgui; // [rsp+30h] [rbp-98h] BYREF
  tagCURSORINFO pci; // [rsp+80h] [rbp-48h] BYREF

  if ( a2 == 1 )
  {
    v8 = 0;
    if ( *(_BYTE *)(a1 + 223) )
    {
      v8 = 0;
      if ( *(_BYTE *)(a1 + 224) )
      {
        if ( *(_DWORD *)a3 == 1 && *(_WORD *)(a3 + 6) )
        {
          if ( SysStringLen(a4) != 1 )
            goto LABEL_11;
          v10 = (unsigned int)*a4 - 61441;
          if ( *a4 == 61441 )
            v10 = a4[1];
          if ( (_DWORD)v10 )
            v11 = *a4;
          else
LABEL_11:
            v11 = MapVirtualKeyExW(*(unsigned __int16 *)(a3 + 6), 2u, *(HKL *)(a1 + 144));
          if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(
              v10,
              (const EVENT_DESCRIPTOR *)ShowPredictions_Start,
              v9,
              1u,
              (PEVENT_DATA_DESCRIPTOR)&pci);
          v8 = v11;
        }
      }
    }
    PostMessageW(hWnd, 0x111u, 0x113EFu, v8);
  }
  else if ( !a2 && *(_DWORD *)(a1 + 164) == 2 )
  {
    memset_0(&pgui, 0, sizeof(pgui));
    pgui.cbSize = 72;
    if ( GetGUIThreadInfo(0, &pgui) )
    {
      if ( pgui.hwndCapture )
      {
        if ( *(_DWORD *)a3 == 1 )
        {
          v12 = *(unsigned __int16 *)(a3 + 4);
          LOWORD(v12) = v12 - 200;
          if ( (unsigned __int16)v12 <= 8u )
          {
            v13 = 297;
            if ( _bittest(&v13, v12) )
            {
              memset(&pci, 0, sizeof(pci));
              pci.cbSize = 24;
              if ( GetCursorInfo(&pci) )
              {
                CursorW = LoadCursorW(0, (LPCWSTR)0x7F86);
                if ( pci.hCursor == CursorW )
                {
                  v15 = DirectUI::NativeHWNDHost::GetHWND(*(DirectUI::NativeHWNDHost **)(a1 + 128));
                  SetTimer(v15, 0x7D4u, 0x2710u, 0);
                }
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140011178  push    rbx
0x14001117a  push    rbp
0x14001117b  push    rsi
0x14001117c  push    rdi
0x14001117d  push    r14
0x14001117f  sub     rsp, 0A0h
0x140011186  mov     rax, cs:__security_cookie
0x14001118d  xor     rax, rsp
0x140011190  mov     [rsp+0C8h+var_30], rax
0x140011198  mov     rbp, [rsp+0C8h+hWnd]
0x1400111a0  xor     ebx, ebx
0x1400111a2  mov     r14, r9
0x1400111a5  mov     rdi, r8
0x1400111a8  mov     rsi, rcx
0x1400111ab  cmp     edx, 1
0x1400111ae  jnz     loc_140011268
0x1400111b4  movzx   eax, bx
0x1400111b7  cmp     [rcx+0DFh], bl
0x1400111bd  jz      loc_14001124B
0x1400111c3  mov     eax, ebx
0x1400111c5  cmp     [rcx+0E0h], bl
0x1400111cb  jz      short loc_14001124B
0x1400111cd  cmp     [r8], edx
0x1400111d0  jnz     short loc_14001124B
0x1400111d2  cmp     bx, [r8+6]
0x1400111d7  jz      short loc_14001124B
0x1400111d9  mov     rcx, r9; pbstr
0x1400111dc  call    cs:__imp_SysStringLen
0x1400111e2  cmp     eax, 1
0x1400111e5  jnz     short loc_140011208
0x1400111e7  movzx   ecx, word ptr [r14]
0x1400111eb  mov     eax, 0F001h
0x1400111f0  sub     ecx, eax
0x1400111f2  jnz     short loc_1400111FE
0x1400111f4  movzx   ecx, word ptr [r14+2]
0x1400111f9  movzx   eax, bx
0x1400111fc  sub     ecx, eax
0x1400111fe  test    ecx, ecx
0x140011200  jz      short loc_140011208
0x140011202  movzx   ebx, word ptr [r14]
0x140011206  jmp     short loc_140011220
0x140011208  movzx   ecx, word ptr [rdi+6]; uCode
0x14001120c  mov     edx, 2; uMapType
0x140011211  mov     r8, [rsi+90h]; dwhkl
0x140011218  call    cs:__imp_MapVirtualKeyExW
0x14001121e  mov     ebx, eax
0x140011220  test    cs:Microsoft_Windows_oskEnableBits, 1
0x140011227  jz      short loc_140011248
0x140011229  lea     rax, [rsp+0C8h+pci]
0x140011231  mov     r9d, 1
0x140011237  lea     rdx, ShowPredictions_Start
0x14001123e  mov     [rsp+0C8h+var_A8], rax
0x140011243  call    McGenEventWrite_EventWriteTransfer
0x140011248  movzx   eax, bx
0x14001124b  movzx   r9d, ax; lParam
0x14001124f  mov     edx, 111h; Msg
0x140011254  mov     r8d, 113EFh; wParam
0x14001125a  mov     rcx, rbp; hWnd
0x14001125d  call    cs:__imp_PostMessageW
0x140011263  jmp     loc_140011343
0x140011268  test    edx, edx
0x14001126a  jnz     loc_140011343
0x140011270  cmp     dword ptr [rcx+0A4h], 2
0x140011277  jnz     loc_140011343
0x14001127d  lea     ebp, [rdx+48h]
0x140011280  mov     r8d, ebp; Size
0x140011283  lea     rcx, [rsp+0C8h+pgui]; void *
0x140011288  call    memset_0
0x14001128d  lea     rdx, [rsp+0C8h+pgui]; pgui
0x140011292  mov     [rsp+0C8h+pgui.cbSize], ebp
0x140011296  xor     ecx, ecx; idThread
0x140011298  call    cs:__imp_GetGUIThreadInfo
0x14001129e  test    eax, eax
0x1400112a0  jz      loc_140011343
0x1400112a6  cmp     [rsp+0C8h+pgui.hwndCapture], rbx
0x1400112ab  jz      loc_140011343
0x1400112b1  cmp     dword ptr [rdi], 1
0x1400112b4  jnz     loc_140011343
0x1400112ba  movzx   eax, word ptr [rdi+4]
0x1400112be  mov     ecx, 0C8h
0x1400112c3  sub     ax, cx
0x1400112c6  cmp     ax, 8
0x1400112ca  ja      short loc_140011343
0x1400112cc  mov     ecx, 129h
0x1400112d1  bt      ecx, eax
0x1400112d4  jnb     short loc_140011343
0x1400112d6  xorps   xmm0, xmm0
0x1400112d9  lea     rcx, [rsp+0C8h+pci]; pci
0x1400112e1  xor     eax, eax
0x1400112e3  movups  xmmword ptr [rsp+0C8h+pci.cbSize], xmm0
0x1400112eb  mov     [rsp+0C8h+pci.cbSize], 18h
0x1400112f6  mov     qword ptr [rsp+0C8h+pci.ptScreenPos.x], rax
0x1400112fe  call    cs:__imp_GetCursorInfo
0x140011304  test    eax, eax
0x140011306  jz      short loc_140011343
0x140011308  mov     edx, 7F86h; lpCursorName
0x14001130d  xor     ecx, ecx; hInstance
0x14001130f  call    cs:__imp_LoadCursorW
0x140011315  cmp     [rsp+0C8h+pci.hCursor], rax
0x14001131d  jnz     short loc_140011343
0x14001131f  mov     rcx, [rsi+80h]
0x140011326  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x14001132c  xor     r9d, r9d; lpTimerFunc
0x14001132f  mov     edx, 7D4h; nIDEvent
0x140011334  mov     rcx, rax; hWnd
0x140011337  mov     r8d, 2710h; uElapse
0x14001133d  call    cs:__imp_SetTimer
0x140011343  mov     rcx, [rsp+0C8h+var_30]
0x14001134b  xor     rcx, rsp; StackCookie
0x14001134e  call    __security_check_cookie
0x140011353  add     rsp, 0A0h
0x14001135a  pop     r14
0x14001135c  pop     rdi
0x14001135d  pop     rsi
0x14001135e  pop     rbp
0x14001135f  pop     rbx
0x140011360  retn
```
