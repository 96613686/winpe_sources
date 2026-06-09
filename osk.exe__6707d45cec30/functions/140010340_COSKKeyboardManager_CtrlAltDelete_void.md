# COSKKeyboardManager::CtrlAltDelete(void)

- ea: `0x140010340`
- end: `0x1400103db`
- name: `?CtrlAltDelete@COSKKeyboardManager@@UEAAJXZ`
- size: `155`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140010340`
- `0x14001b6f0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001035c`
- `KERNEL32!GetCurrentProcessId` at `0x14001035c`
- `KERNEL32!ProcessIdToSessionId` at `0x140010369`
- `KERNEL32!ProcessIdToSessionId` at `0x140010369`
- `USER32!PostMessageW` at `0x1400103c8`
- `USER32!PostMessageW` at `0x1400103c8`
- `WMsgAPI!WmsgSendMessage` at `0x140010388`
- `WMsgAPI!WmsgSendMessage` at `0x140010388`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400103b1`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x1400103b1`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::CtrlAltDelete(DirectUI::NativeHWNDHost **this)
{
  unsigned int v2; // ebx
  DWORD CurrentProcessId; // eax
  int v4; // eax
  HWND HWND; // rax
  DWORD pSessionId; // [rsp+38h] [rbp+10h] BYREF
  int v8; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  if ( COSKUtils::ShouldRunSecure() )
  {
    pSessionId = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      v8 = 0;
      v4 = WmsgSendMessage(pSessionId, 520, 0, &v8);
      if ( v4 )
      {
        if ( v4 != 5 )
        {
          if ( v4 > 0 )
            return (unsigned __int16)v4 | 0x80070000;
          else
            return (unsigned int)v4;
        }
      }
    }
  }
  else
  {
    HWND = DirectUI::NativeHWNDHost::GetHWND(this[16]);
    PostMessageW(HWND, 0x111u, 0x13F0u, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x140010340  mov     [rsp+arg_0], rbx
0x140010345  push    rdi
0x140010346  sub     rsp, 20h
0x14001034a  mov     rdi, rcx
0x14001034d  xor     ebx, ebx
0x14001034f  call    ?ShouldRunSecure@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecure(void)
0x140010354  test    al, al
0x140010356  jz      short loc_1400103AA
0x140010358  mov     [rsp+28h+pSessionId], ebx
0x14001035c  call    cs:__imp_GetCurrentProcessId
0x140010362  mov     ecx, eax; dwProcessId
0x140010364  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x140010369  call    cs:__imp_ProcessIdToSessionId
0x14001036f  test    eax, eax
0x140010371  jz      short loc_1400103CE
0x140010373  mov     ecx, [rsp+28h+pSessionId]
0x140010377  lea     r9, [rsp+28h+arg_10]
0x14001037c  xor     r8d, r8d
0x14001037f  mov     [rsp+28h+arg_10], ebx
0x140010383  mov     edx, 208h
0x140010388  call    cs:__imp_WmsgSendMessage
0x14001038e  test    eax, eax
0x140010390  jz      short loc_1400103CE
0x140010392  cmp     eax, 5
0x140010395  jz      short loc_1400103CE
0x140010397  test    eax, eax
0x140010399  jg      short loc_14001039F
0x14001039b  mov     ebx, eax
0x14001039d  jmp     short loc_1400103CE
0x14001039f  movzx   ebx, ax
0x1400103a2  or      ebx, 80070000h
0x1400103a8  jmp     short loc_1400103CE
0x1400103aa  mov     rcx, [rdi+80h]
0x1400103b1  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x1400103b7  xor     r9d, r9d; lParam
0x1400103ba  mov     edx, 111h; Msg
0x1400103bf  mov     rcx, rax; hWnd
0x1400103c2  mov     r8d, 13F0h; wParam
0x1400103c8  call    cs:__imp_PostMessageW
0x1400103ce  mov     eax, ebx
0x1400103d0  mov     rbx, [rsp+28h+arg_0]
0x1400103d5  add     rsp, 20h
0x1400103d9  pop     rdi
0x1400103da  retn
```
