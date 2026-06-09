# ShellHandwriting::DelegationManager::RunDelegateThread(void)

- ea: `0x18007dbc0`
- end: `0x18007dd21`
- name: `?RunDelegateThread@DelegationManager@ShellHandwriting@@AEAAXXZ`
- size: `353`
- prototype: `void __fastcall(ShellHandwriting::DelegationManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007bc7c`

## callees

- `0x18007dbc0`
- `0x180094944`
- `0x18009925c`
- `0x180099ed4`
- `0x1800ac4f0`
- `0x1800ff5bc`
- `0x1801008b4`
- `0x180106a60`

## import_xrefs

- `USER32!TranslateMessage` at `0x18007dce4`
- `USER32!TranslateMessage` at `0x18007dce4`
- `USER32!GetMessageW` at `0x18007dc2a`
- `USER32!GetMessageW` at `0x18007dc2a`
- `USER32!DispatchMessageW` at `0x18007dcee`
- `USER32!DispatchMessageW` at `0x18007dcee`
- `USER32!PostThreadMessageW` at `0x18007dc06`
- `USER32!PostThreadMessageW` at `0x18007dc06`

## pseudocode

```c
void __fastcall ShellHandwriting::DelegationManager::RunDelegateThread(ShellHandwriting::DelegationManager *this)
{
  __int64 v2; // rcx
  char v3; // di
  ShellHandwriting::StaticPerThreadStore *v4; // rcx
  unsigned int lParam; // r14d
  unsigned int wParam; // esi
  unsigned int v7; // ecx
  int v8; // eax
  struct tagMSG Msg; // [rsp+20h] [rbp-29h] BYREF
  _OWORD v10[3]; // [rsp+50h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( !ShellHandwriting::DelegationManager::IsThreadDispatcherCallbackMode(this) )
    PostThreadMessageW(*(_DWORD *)(v2 + 16), 0x34Au, 0x1001u, *(unsigned int *)(v2 + 20));
  v3 = 1;
  memset(&Msg, 0, sizeof(Msg));
  do
  {
    if ( !GetMessageW(&Msg, 0, 0, 0) )
      break;
    switch ( Msg.message )
    {
      case 0x12u:
        v3 = 0;
        break;
      case 0x113u:
        if ( Msg.hwnd == (HWND)*((_QWORD *)this + 3) && (Msg.wParam & 0xFFFFFFF0) == 0x2350 )
        {
          v8 = ShellHandwriting::DelegationManager::FSM_ProcessTimeout(this, Msg.wParam);
          if ( v8 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x26C,
              (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\delegation\\shellhandwritingdelegation.cpp",
              (const char *)(unsigned int)v8,
              (int)Msg.hwnd);
        }
        break;
      case 0x34Au:
        lParam = Msg.lParam;
        wParam = Msg.wParam;
        memset(v10, 0, sizeof(v10));
        if ( ShellHandwriting::StaticPerThreadStore::GetPayloadForCurrentThread(
               v4,
               Msg.lParam,
               (struct ShellHandwriting::MessagePayload *)v10) )
        {
          ShellHandwriting::DelegationManager::FSM_ProcessUIThreadMessage(
            this,
            wParam,
            (const struct ShellHandwriting::MessagePayload *)v10);
        }
        else
        {
          ShellHandwriting::InputTraceLogging::ShellHandwriting::Delegation::StaleMessageFromUiThread(
            v7,
            wParam,
            lParam);
        }
        break;
    }
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  while ( v3 );
}

```

## disassembly

```asm
0x18007dbc0  mov     [rsp-8+arg_8], rbx
0x18007dbc5  mov     [rsp-8+arg_10], rsi
0x18007dbca  push    rbp
0x18007dbcb  push    rdi
0x18007dbcc  push    r14
0x18007dbce  lea     rbp, [rsp-47h]
0x18007dbd3  sub     rsp, 90h
0x18007dbda  mov     rax, cs:__security_cookie
0x18007dbe1  xor     rax, rsp
0x18007dbe4  mov     [rbp+57h+var_20], rax
0x18007dbe8  mov     rbx, rcx
0x18007dbeb  call    ?IsThreadDispatcherCallbackMode@DelegationManager@ShellHandwriting@@AEAA_NXZ; ShellHandwriting::DelegationManager::IsThreadDispatcherCallbackMode(void)
0x18007dbf0  test    al, al
0x18007dbf2  jnz     short loc_18007DC0C
0x18007dbf4  mov     r9d, [rcx+14h]; lParam
0x18007dbf8  mov     edx, 34Ah; Msg
0x18007dbfd  mov     ecx, [rcx+10h]; idThread
0x18007dc00  mov     r8d, 1001h; wParam
0x18007dc06  call    cs:__imp_PostThreadMessageW
0x18007dc0c  xorps   xmm0, xmm0
0x18007dc0f  mov     dil, 1
0x18007dc12  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x18007dc16  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x18007dc1a  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x18007dc1e  xor     r9d, r9d; wMsgFilterMax
0x18007dc21  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007dc25  xor     r8d, r8d; wMsgFilterMin
0x18007dc28  xor     edx, edx; hWnd
0x18007dc2a  call    cs:__imp_GetMessageW
0x18007dc30  test    eax, eax
0x18007dc32  jz      loc_18007DCFD
0x18007dc38  mov     eax, [rbp+57h+Msg.message]
0x18007dc3b  cmp     eax, 12h
0x18007dc3e  jz      loc_18007DCDD
0x18007dc44  cmp     eax, 113h
0x18007dc49  jz      short loc_18007DC96
0x18007dc4b  cmp     eax, 34Ah
0x18007dc50  jnz     loc_18007DCE0
0x18007dc56  mov     r14d, dword ptr [rbp+57h+Msg.lParam]
0x18007dc5a  lea     r8, [rbp+57h+var_50]; struct ShellHandwriting::MessagePayload *
0x18007dc5e  mov     esi, dword ptr [rbp+57h+Msg.wParam]
0x18007dc61  xorps   xmm0, xmm0
0x18007dc64  mov     edx, r14d; unsigned int
0x18007dc67  movups  [rbp+57h+var_50], xmm0
0x18007dc6b  movups  [rbp+57h+var_40], xmm0
0x18007dc6f  movups  [rbp+57h+var_30], xmm0
0x18007dc73  call    ?GetPayloadForCurrentThread@StaticPerThreadStore@ShellHandwriting@@QEAA_NIPEAUMessagePayload@2@@Z; ShellHandwriting::StaticPerThreadStore::GetPayloadForCurrentThread(uint,ShellHandwriting::MessagePayload *)
0x18007dc78  mov     edx, esi; unsigned int
0x18007dc7a  test    al, al
0x18007dc7c  jz      short loc_18007DC8C
0x18007dc7e  lea     r8, [rbp+57h+var_50]; struct ShellHandwriting::MessagePayload *
0x18007dc82  mov     rcx, rbx; this
0x18007dc85  call    ?FSM_ProcessUIThreadMessage@DelegationManager@ShellHandwriting@@AEAAJIPEBUMessagePayload@2@@Z; ShellHandwriting::DelegationManager::FSM_ProcessUIThreadMessage(uint,ShellHandwriting::MessagePayload const *)
0x18007dc8a  jmp     short loc_18007DCE0
0x18007dc8c  mov     r8d, r14d; unsigned int
0x18007dc8f  call    ?StaleMessageFromUiThread@Delegation@ShellHandwriting@InputTraceLogging@2@SAXIII@Z; ShellHandwriting::InputTraceLogging::ShellHandwriting::Delegation::StaleMessageFromUiThread(uint,uint,uint)
0x18007dc94  jmp     short loc_18007DCE0
0x18007dc96  mov     rax, [rbx+18h]
0x18007dc9a  cmp     [rbp+57h+Msg.hwnd], rax
0x18007dc9e  jnz     short loc_18007DCE0
0x18007dca0  mov     rdx, [rbp+57h+Msg.wParam]; unsigned int
0x18007dca4  mov     ecx, 0FFFFFFF0h
0x18007dca9  mov     rax, rdx
0x18007dcac  and     rax, rcx
0x18007dcaf  cmp     rax, 2350h
0x18007dcb5  jnz     short loc_18007DCE0
0x18007dcb7  mov     rcx, rbx; this
0x18007dcba  call    ?FSM_ProcessTimeout@DelegationManager@ShellHandwriting@@AEAAJI@Z; ShellHandwriting::DelegationManager::FSM_ProcessTimeout(uint)
0x18007dcbf  test    eax, eax
0x18007dcc1  jns     short loc_18007DCE0
0x18007dcc3  mov     rcx, [rbp+5Fh]; this
0x18007dcc7  lea     r8, aClientcoreWind_7; "clientcore\\windows\\advcore\\ctf\\shel"...
0x18007dcce  mov     r9d, eax; char *
0x18007dcd1  mov     edx, 26Ch; void *
0x18007dcd6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007dcdb  jmp     short loc_18007DCE0
0x18007dcdd  xor     dil, dil
0x18007dce0  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007dce4  call    cs:__imp_TranslateMessage
0x18007dcea  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007dcee  call    cs:__imp_DispatchMessageW
0x18007dcf4  test    dil, dil
0x18007dcf7  jnz     loc_18007DC1E
0x18007dcfd  mov     rcx, [rbp+57h+var_20]
0x18007dd01  xor     rcx, rsp; StackCookie
0x18007dd04  call    __security_check_cookie
0x18007dd09  lea     r11, [rsp+0A0h+var_10]
0x18007dd11  mov     rbx, [r11+28h]
0x18007dd15  mov     rsi, [r11+30h]
0x18007dd19  mov     rsp, r11
0x18007dd1c  pop     r14
0x18007dd1e  pop     rdi
0x18007dd1f  pop     rbp
0x18007dd20  retn
```
