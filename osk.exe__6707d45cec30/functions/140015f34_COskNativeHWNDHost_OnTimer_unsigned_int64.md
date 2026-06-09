# COskNativeHWNDHost::OnTimer(unsigned __int64)

- ea: `0x140015f34`
- end: `0x1400160b0`
- name: `?OnTimer@COskNativeHWNDHost@@AEAAX_K@Z`
- size: `380`
- prototype: `void __fastcall(COskNativeHWNDHost *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400156e0`

## callees

- `0x140002de3`
- `0x140010c54`
- `0x1400110d0`
- `0x140015f34`
- `0x140016abc`
- `0x140025d70`

## import_xrefs

- `USER32!GetGUIThreadInfo` at `0x140015fcb`
- `USER32!GetGUIThreadInfo` at `0x140015fcb`
- `USER32!SendInput` at `0x140016064`
- `USER32!SendInput` at `0x140016064`
- `USER32!KillTimer` at `0x140015fa9`
- `USER32!KillTimer` at `0x140015fa9`
- `USER32!GetCursorPos` at `0x140015ff2`
- `USER32!GetCursorPos` at `0x140015ff2`
- `USER32!GetMessageExtraInfo` at `0x140016031`
- `USER32!GetMessageExtraInfo` at `0x140016031`
- `WINMM!PlaySoundW` at `0x14001607c`
- `WINMM!PlaySoundW` at `0x14001607c`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140015f9b`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140015f9b`

## pseudocode

```c
void __fastcall COskNativeHWNDHost::OnTimer(COskNativeHWNDHost *this, unsigned __int64 a2)
{
  HWND HWND; // rax
  int v3; // esi
  __int64 v4; // r14
  unsigned __int64 v5; // rbx
  struct tagPOINT Point; // [rsp+20h] [rbp-89h] BYREF
  struct tagINPUT pInputs[2]; // [rsp+30h] [rbp-79h] BYREF
  struct tagGUITHREADINFO pgui; // [rsp+80h] [rbp-29h] BYREF

  switch ( a2 )
  {
    case 0x7D2uLL:
      COskNativeHWNDHost::ShowOSKToolTip(this, 0, 0);
      break;
    case 0x7D3uLL:
      COSKKeyboardManager::HandleFocusChange(0);
      break;
    case 0x7D4uLL:
      HWND = DirectUI::NativeHWNDHost::GetHWND(this);
      KillTimer(HWND, 0x7D4u);
      memset_0(&pgui, 0, sizeof(pgui));
      pgui.cbSize = 72;
      if ( GetGUIThreadInfo(0, &pgui) && pgui.hwndCapture )
      {
        Point = 0;
        GetCursorPos(&Point);
        pInputs[0].type = 0;
        memset_0(&pInputs[0].mi, 0, 0x48u);
        v3 = 0;
        v4 = 0;
        do
        {
          v5 = 5 * v4;
          pInputs[v5 / 5].type = 0;
          *((_DWORD *)&pInputs[0].hi + 2 * v5 + 3) = (v3 == 0 ? 2 : 4) | 0x8000;
          *((_QWORD *)&pInputs[0].hi + 5 * v4 + 3) = GetMessageExtraInfo();
          ++v3;
          ++v4;
          *(&pInputs[0].mi.dx + 2 * v5) = Point.x;
          *((_DWORD *)&pInputs[0].hi.wParamL + 2 * v5) = Point.y;
        }
        while ( v3 < 2 );
        SendInput(2u, pInputs, 40);
        PlaySoundW((LPCWSTR)0x834, g_hInstance, 0x40005u);
      }
      break;
    default:
      if ( a2 - 2005 <= 1 )
      {
        if ( COSKKeyboardManager::s_pCOSKKeyboardManager )
          COSKKeyboardManager::HandleMousePressAndHoldInternal(this, a2);
      }
      break;
  }
}

```

## disassembly

```asm
0x140015f34  push    rbp
0x140015f36  push    rbx
0x140015f37  push    rsi
0x140015f38  push    r14
0x140015f3a  lea     rbp, [rsp-3Fh]
0x140015f3f  sub     rsp, 0E8h
0x140015f46  mov     rax, cs:__security_cookie
0x140015f4d  xor     rax, rsp
0x140015f50  mov     [rbp+57h+var_30], rax
0x140015f54  mov     rax, rdx
0x140015f57  sub     rax, 7D2h
0x140015f5d  jz      loc_14001608D
0x140015f63  sub     rax, 1
0x140015f67  jz      loc_140016084
0x140015f6d  sub     rax, 1
0x140015f71  jz      short loc_140015F9B
0x140015f73  sub     rax, 1
0x140015f77  jz      short loc_140015F83
0x140015f79  cmp     rax, 1
0x140015f7d  jnz     loc_140016097
0x140015f83  cmp     cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA, 0; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x140015f8b  jz      loc_140016097
0x140015f91  call    ?HandleMousePressAndHoldInternal@COSKKeyboardManager@@AEAAX_K@Z; COSKKeyboardManager::HandleMousePressAndHoldInternal(unsigned __int64)
0x140015f96  jmp     loc_140016097
0x140015f9b  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140015fa1  mov     rcx, rax; hWnd
0x140015fa4  mov     edx, 7D4h; uIDEvent
0x140015fa9  call    cs:__imp_KillTimer
0x140015faf  mov     ebx, 48h ; 'H'
0x140015fb4  lea     rcx, [rbp+57h+pgui]; void *
0x140015fb8  mov     r8d, ebx; Size
0x140015fbb  xor     edx, edx; Val
0x140015fbd  call    memset_0
0x140015fc2  lea     rdx, [rbp+57h+pgui]; pgui
0x140015fc6  mov     [rbp+57h+pgui.cbSize], ebx
0x140015fc9  xor     ecx, ecx; idThread
0x140015fcb  call    cs:__imp_GetGUIThreadInfo
0x140015fd1  test    eax, eax
0x140015fd3  jz      loc_140016097
0x140015fd9  cmp     [rbp+57h+pgui.hwndCapture], 0
0x140015fde  jz      loc_140016097
0x140015fe4  lea     rcx, [rsp+100h+Point]; lpPoint
0x140015fe9  mov     qword ptr [rsp+100h+Point.x], 0
0x140015ff2  call    cs:__imp_GetCursorPos
0x140015ff8  mov     r8d, ebx; Size
0x140015ffb  mov     [rbp+57h+pInputs.type], 0
0x140016002  xor     edx, edx; Val
0x140016004  lea     rcx, [rbp+57h+pInputs.8]; void *
0x140016008  call    memset_0
0x14001600d  xor     esi, esi
0x14001600f  xor     r14d, r14d
0x140016012  lea     rbx, [r14+r14*4]
0x140016016  cmp     esi, 1
0x140016019  mov     [rbp+rbx*8+57h+pInputs.type], 0
0x140016021  sbb     eax, eax
0x140016023  and     eax, 0FFFFFFFEh
0x140016026  add     eax, 4
0x140016029  bts     eax, 0Fh
0x14001602d  mov     dword ptr [rbp+rbx*8+57h+pInputs.8+0Ch], eax
0x140016031  call    cs:__imp_GetMessageExtraInfo
0x140016037  mov     qword ptr [rbp+rbx*8+57h+pInputs.8+18h], rax
0x14001603c  inc     esi
0x14001603e  mov     eax, [rsp+100h+Point.x]
0x140016042  inc     r14
0x140016045  mov     dword ptr [rbp+rbx*8+57h+pInputs.8], eax
0x140016049  mov     eax, [rsp+100h+Point.y]
0x14001604d  mov     dword ptr [rbp+rbx*8+57h+pInputs.8+4], eax
0x140016051  cmp     esi, 2
0x140016054  jl      short loc_140016012
0x140016056  mov     r8d, 28h ; '('; cbSize
0x14001605c  lea     rdx, [rbp+57h+pInputs]; pInputs
0x140016060  lea     ecx, [r8-26h]; cInputs
0x140016064  call    cs:__imp_SendInput
0x14001606a  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hmod
0x140016071  mov     r8d, 40005h; fdwSound
0x140016077  mov     ecx, 834h; pszSound
0x14001607c  call    cs:__imp_PlaySoundW
0x140016082  jmp     short loc_140016097
0x140016084  xor     ecx, ecx; HKL
0x140016086  call    ?HandleFocusChange@COSKKeyboardManager@@SAXPEAUHKL__@@@Z; COSKKeyboardManager::HandleFocusChange(HKL__ *)
0x14001608b  jmp     short loc_140016097
0x14001608d  xor     r8d, r8d; int
0x140016090  xor     edx, edx; bool
0x140016092  call    ?ShowOSKToolTip@COskNativeHWNDHost@@AEAAX_NH@Z; COskNativeHWNDHost::ShowOSKToolTip(bool,int)
0x140016097  mov     rcx, [rbp+57h+var_30]
0x14001609b  xor     rcx, rsp; StackCookie
0x14001609e  call    __security_check_cookie
0x1400160a3  add     rsp, 0E8h
0x1400160aa  pop     r14
0x1400160ac  pop     rsi
0x1400160ad  pop     rbx
0x1400160ae  pop     rbp
0x1400160af  retn
```
