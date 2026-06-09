# EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(void *)

- ea: `0x18001fd10`
- end: `0x18001fdd2`
- name: `?WaitForCOMcallCompletion@ThirdPartyEapMethodConfig@Peer@EapLm@@AEAAXPEAX@Z`
- size: `194`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *__hidden this, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f360`
- `0x18001f440`
- `0x18001f5a0`

## callees

- `0x180002404`
- `0x1800155dc`
- `0x18001fd10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fd63`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001fd63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd1e`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x18001fda0`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x18001fda0`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18001fd85`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x18001fd85`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18001fd7a`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18001fd7a`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18001fdc1`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x18001fdc1`

## string_xrefs

- `0x18001fd26`: `New thread could not be created`

## pseudocode

```c
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::WaitForCOMcallCompletion(
        EapLm::Peer::ThirdPartyEapMethodConfig *this,
        void *a2)
{
  DWORD LastError; // eax
  DWORD v3; // eax
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Handles; // [rsp+78h] [rbp+10h] BYREF

  Handles = a2;
  if ( !a2 )
  {
    LastError = GetLastError();
    EapHost::EapException::Throw(L"New thread could not be created", LastError);
  }
  do
  {
    do
    {
      memset(&Msg, 0, sizeof(Msg));
      if ( !(unsigned __int8)IsDispatchMessageWPresent(this) )
      {
        v3 = WaitForMultipleObjectsEx(1u, &Handles, 0, 0xFFFFFFFF, 0);
        break;
      }
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      v3 = MsgWaitForMultipleObjects(1u, &Handles, 0, 0xFFFFFFFF, 0x1CFFu);
    }
    while ( v3 == 1 );
  }
  while ( v3 == 258 );
}

```

## disassembly

```asm
0x18001fd10  mov     [rsp+Handles], rdx
0x18001fd15  sub     rsp, 68h
0x18001fd19  test    rdx, rdx
0x18001fd1c  jnz     short loc_18001FD33
0x18001fd1e  call    cs:__imp_GetLastError
0x18001fd24  mov     edx, eax; unsigned int
0x18001fd26  lea     rcx, aNewThreadCould; "New thread could not be created"
0x18001fd2d  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x18001fd33  xorps   xmm0, xmm0
0x18001fd36  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x18001fd3b  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x18001fd40  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x18001fd45  call    IsDispatchMessageWPresent
0x18001fd4a  xor     r8d, r8d; bWaitAll
0x18001fd4d  test    al, al
0x18001fd4f  jnz     short loc_18001FD8E
0x18001fd51  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001fd55  mov     [rsp+68h+bAlertable], r8d; bAlertable
0x18001fd5a  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18001fd5f  lea     ecx, [r8+1]; nCount
0x18001fd63  call    cs:__imp_WaitForMultipleObjectsEx
0x18001fd69  cmp     eax, 102h
0x18001fd6e  jz      short loc_18001FD33
0x18001fd70  add     rsp, 68h
0x18001fd74  retn
0x18001fd75  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001fd7a  call    cs:__imp_TranslateMessage
0x18001fd80  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001fd85  call    cs:__imp_DispatchMessageW
0x18001fd8b  xor     r8d, r8d; wMsgFilterMin
0x18001fd8e  xor     r9d, r9d; wMsgFilterMax
0x18001fd91  mov     [rsp+68h+bAlertable], 1; wRemoveMsg
0x18001fd99  xor     edx, edx; hWnd
0x18001fd9b  lea     rcx, [rsp+68h+Msg]; lpMsg
0x18001fda0  call    cs:__imp_PeekMessageW
0x18001fda6  test    eax, eax
0x18001fda8  jnz     short loc_18001FD75
0x18001fdaa  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001fdae  mov     [rsp+68h+bAlertable], 1CFFh; dwWakeMask
0x18001fdb6  xor     r8d, r8d; fWaitAll
0x18001fdb9  lea     rdx, [rsp+68h+Handles]; pHandles
0x18001fdbe  lea     ecx, [rax+1]; nCount
0x18001fdc1  call    cs:__imp_MsgWaitForMultipleObjects
0x18001fdc7  cmp     eax, 1
0x18001fdca  jz      loc_18001FD33
0x18001fdd0  jmp     short loc_18001FD69
```
