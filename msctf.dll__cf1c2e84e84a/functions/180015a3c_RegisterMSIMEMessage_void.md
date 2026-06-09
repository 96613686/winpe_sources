# RegisterMSIMEMessage(void)

- ea: `0x180015a3c`
- end: `0x180015b97`
- name: `?RegisterMSIMEMessage@@YAHXZ`
- size: `347`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x1800156c0`
- `0x1800158fc`

## callees

- `0x180015a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015a64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a4e`
- `USER32!RegisterWindowMessageW` at `0x180015a79`
- `USER32!RegisterWindowMessageW` at `0x180015a8c`
- `USER32!RegisterWindowMessageW` at `0x180015a9f`
- `USER32!RegisterWindowMessageW` at `0x180015ab2`
- `USER32!RegisterWindowMessageW` at `0x180015ac5`
- `USER32!RegisterWindowMessageW` at `0x180015ad8`
- `USER32!RegisterWindowMessageW` at `0x180015aeb`
- `USER32!RegisterWindowMessageW` at `0x180015afe`
- `USER32!RegisterWindowMessageW` at `0x180015b11`
- `USER32!RegisterWindowMessageW` at `0x180015b24`
- `USER32!RegisterWindowMessageW` at `0x180015a79`
- `USER32!RegisterWindowMessageW` at `0x180015a8c`
- `USER32!RegisterWindowMessageW` at `0x180015a9f`
- `USER32!RegisterWindowMessageW` at `0x180015ab2`
- `USER32!RegisterWindowMessageW` at `0x180015ac5`
- `USER32!RegisterWindowMessageW` at `0x180015ad8`
- `USER32!RegisterWindowMessageW` at `0x180015aeb`
- `USER32!RegisterWindowMessageW` at `0x180015afe`
- `USER32!RegisterWindowMessageW` at `0x180015b11`
- `USER32!RegisterWindowMessageW` at `0x180015b24`

## string_xrefs

- `0x180015a72`: `MSIMEService`
- `0x180015a7f`: `MSIMEUIReady`
- `0x180015a92`: `MSIMEReconvertRequest`
- `0x180015b04`: `MSIMEMouseOperation`
- `0x180015b17`: `MSIMEKeyMap`
- `0x180015ade`: `MSIMEModeBias`
- `0x180015ab8`: `MSIMEDocumentFeed`
- `0x180015acb`: `MSIMEQueryPosition`
- `0x180015af1`: `MSIMEShowImePad`
- `0x180015aa5`: `MSIMEReconvert`

## pseudocode

```c
__int64 RegisterMSIMEMessage(void)
{
  unsigned int v0; // ebx
  UINT v2; // eax

  v0 = 1;
  EnterCriticalSection(&g_cs);
  if ( !dword_180141308 )
  {
    WM_MSIME_SERVICE = RegisterWindowMessageW(L"MSIMEService");
    WM_MSIME_UIREADY = RegisterWindowMessageW(L"MSIMEUIReady");
    WM_MSIME_RECONVERTREQUEST = RegisterWindowMessageW(L"MSIMEReconvertRequest");
    WM_MSIME_RECONVERT = RegisterWindowMessageW(L"MSIMEReconvert");
    WM_MSIME_DOCUMENTFEED = RegisterWindowMessageW(L"MSIMEDocumentFeed");
    WM_MSIME_QUERYPOSITION = RegisterWindowMessageW(L"MSIMEQueryPosition");
    WM_MSIME_MODEBIAS = RegisterWindowMessageW(L"MSIMEModeBias");
    WM_MSIME_SHOWIMEPAD = RegisterWindowMessageW(L"MSIMEShowImePad");
    WM_MSIME_MOUSE = RegisterWindowMessageW(L"MSIMEMouseOperation");
    v2 = RegisterWindowMessageW(L"MSIMEKeyMap");
    WM_MSIME_KEYMAP = v2;
    if ( WM_MSIME_SERVICE
      && WM_MSIME_SHOWIMEPAD
      && WM_MSIME_UIREADY
      && WM_MSIME_RECONVERTREQUEST
      && WM_MSIME_RECONVERT
      && WM_MSIME_DOCUMENTFEED
      && WM_MSIME_QUERYPOSITION
      && WM_MSIME_MODEBIAS
      && WM_MSIME_MOUSE
      && v2 )
    {
      dword_180141308 = 1;
    }
    else
    {
      v0 = 0;
    }
  }
  LeaveCriticalSection(&g_cs);
  return v0;
}

```

## disassembly

```asm
0x180015a3c  push    rbx
0x180015a3e  sub     rsp, 20h
0x180015a42  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x180015a49  mov     ebx, 1
0x180015a4e  call    cs:__imp_EnterCriticalSection
0x180015a54  cmp     cs:dword_180141308, 0
0x180015a5b  jz      short loc_180015A72
0x180015a5d  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x180015a64  call    cs:__imp_LeaveCriticalSection
0x180015a6a  mov     eax, ebx
0x180015a6c  add     rsp, 20h
0x180015a70  pop     rbx
0x180015a71  retn
0x180015a72  lea     rcx, String; "MSIMEService"
0x180015a79  call    cs:__imp_RegisterWindowMessageW
0x180015a7f  lea     rcx, aMsimeuiready; "MSIMEUIReady"
0x180015a86  mov     cs:?WM_MSIME_SERVICE@@3IA, eax; uint WM_MSIME_SERVICE
0x180015a8c  call    cs:__imp_RegisterWindowMessageW
0x180015a92  lea     rcx, aMsimereconvert_0; "MSIMEReconvertRequest"
0x180015a99  mov     cs:?WM_MSIME_UIREADY@@3IA, eax; uint WM_MSIME_UIREADY
0x180015a9f  call    cs:__imp_RegisterWindowMessageW
0x180015aa5  lea     rcx, aMsimereconvert; "MSIMEReconvert"
0x180015aac  mov     cs:?WM_MSIME_RECONVERTREQUEST@@3IA, eax; uint WM_MSIME_RECONVERTREQUEST
0x180015ab2  call    cs:__imp_RegisterWindowMessageW
0x180015ab8  lea     rcx, aMsimedocumentf; "MSIMEDocumentFeed"
0x180015abf  mov     cs:?WM_MSIME_RECONVERT@@3IA, eax; uint WM_MSIME_RECONVERT
0x180015ac5  call    cs:__imp_RegisterWindowMessageW
0x180015acb  lea     rcx, aMsimequeryposi; "MSIMEQueryPosition"
0x180015ad2  mov     cs:?WM_MSIME_DOCUMENTFEED@@3IA, eax; uint WM_MSIME_DOCUMENTFEED
0x180015ad8  call    cs:__imp_RegisterWindowMessageW
0x180015ade  lea     rcx, aMsimemodebias; "MSIMEModeBias"
0x180015ae5  mov     cs:?WM_MSIME_QUERYPOSITION@@3IA, eax; uint WM_MSIME_QUERYPOSITION
0x180015aeb  call    cs:__imp_RegisterWindowMessageW
0x180015af1  lea     rcx, aMsimeshowimepa; "MSIMEShowImePad"
0x180015af8  mov     cs:?WM_MSIME_MODEBIAS@@3IA, eax; uint WM_MSIME_MODEBIAS
0x180015afe  call    cs:__imp_RegisterWindowMessageW
0x180015b04  lea     rcx, aMsimemouseoper; "MSIMEMouseOperation"
0x180015b0b  mov     cs:?WM_MSIME_SHOWIMEPAD@@3IA, eax; uint WM_MSIME_SHOWIMEPAD
0x180015b11  call    cs:__imp_RegisterWindowMessageW
0x180015b17  lea     rcx, aMsimekeymap; "MSIMEKeyMap"
0x180015b1e  mov     cs:?WM_MSIME_MOUSE@@3IA, eax; uint WM_MSIME_MOUSE
0x180015b24  call    cs:__imp_RegisterWindowMessageW
0x180015b2a  cmp     cs:?WM_MSIME_SERVICE@@3IA, 0; uint WM_MSIME_SERVICE
0x180015b31  mov     cs:?WM_MSIME_KEYMAP@@3IA, eax; uint WM_MSIME_KEYMAP
0x180015b37  jz      short loc_180015B90
0x180015b39  cmp     cs:?WM_MSIME_SHOWIMEPAD@@3IA, 0; uint WM_MSIME_SHOWIMEPAD
0x180015b40  jz      short loc_180015B90
0x180015b42  cmp     cs:?WM_MSIME_UIREADY@@3IA, 0; uint WM_MSIME_UIREADY
0x180015b49  jz      short loc_180015B90
0x180015b4b  cmp     cs:?WM_MSIME_RECONVERTREQUEST@@3IA, 0; uint WM_MSIME_RECONVERTREQUEST
0x180015b52  jz      short loc_180015B90
0x180015b54  cmp     cs:?WM_MSIME_RECONVERT@@3IA, 0; uint WM_MSIME_RECONVERT
0x180015b5b  jz      short loc_180015B90
0x180015b5d  cmp     cs:?WM_MSIME_DOCUMENTFEED@@3IA, 0; uint WM_MSIME_DOCUMENTFEED
0x180015b64  jz      short loc_180015B90
0x180015b66  cmp     cs:?WM_MSIME_QUERYPOSITION@@3IA, 0; uint WM_MSIME_QUERYPOSITION
0x180015b6d  jz      short loc_180015B90
0x180015b6f  cmp     cs:?WM_MSIME_MODEBIAS@@3IA, 0; uint WM_MSIME_MODEBIAS
0x180015b76  jz      short loc_180015B90
0x180015b78  cmp     cs:?WM_MSIME_MOUSE@@3IA, 0; uint WM_MSIME_MOUSE
0x180015b7f  jz      short loc_180015B90
0x180015b81  test    eax, eax
0x180015b83  jz      short loc_180015B90
0x180015b85  mov     cs:dword_180141308, ebx
0x180015b8b  jmp     loc_180015A5D
0x180015b90  xor     ebx, ebx
0x180015b92  jmp     loc_180015A5D
```
