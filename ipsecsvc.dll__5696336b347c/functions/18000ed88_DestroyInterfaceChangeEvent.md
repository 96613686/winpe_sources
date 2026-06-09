# DestroyInterfaceChangeEvent

- ea: `0x18000ed88`
- end: `0x18000ee0b`
- name: `DestroyInterfaceChangeEvent`
- size: `131`
- prototype: `int()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000f7f4`

## callees

- `0x18000ed88`

## import_xrefs

- `WS2_32!WSACloseEvent` at `0x18000ed98`
- `WS2_32!WSACloseEvent` at `0x18000ed98`
- `WS2_32!__imp_closesocket` at `0x18000edba`
- `WS2_32!__imp_closesocket` at `0x18000eddc`
- `WS2_32!__imp_closesocket` at `0x18000edba`
- `WS2_32!__imp_closesocket` at `0x18000eddc`
- `WS2_32!__imp_WSACleanup` at `0x18000edf6`
- `WS2_32!__imp_WSACleanup` at `0x18000edf6`

## pseudocode

```c
int DestroyInterfaceChangeEvent()
{
  int result; // eax

  if ( ghIfChangeEvent )
  {
    WSACloseEvent(ghIfChangeEvent);
    ghIfChangeEvent = 0;
  }
  if ( gIfChangeEventSocket4 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    closesocket(gIfChangeEventSocket4);
    gIfChangeEventSocket4 = -1;
  }
  result = gIfChangeEventSocket6 - 1;
  if ( gIfChangeEventSocket6 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = closesocket(gIfChangeEventSocket6);
    gIfChangeEventSocket6 = -1;
  }
  if ( gbwsaStarted )
  {
    result = WSACleanup();
    gbwsaStarted = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ed88  sub     rsp, 28h
0x18000ed8c  mov     rcx, cs:ghIfChangeEvent; hEvent
0x18000ed93  test    rcx, rcx
0x18000ed96  jz      short loc_18000EDA9
0x18000ed98  call    cs:__imp_WSACloseEvent
0x18000ed9e  mov     cs:ghIfChangeEvent, 0
0x18000eda9  mov     rcx, cs:gIfChangeEventSocket4; s
0x18000edb0  lea     rax, [rcx-1]
0x18000edb4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000edb8  ja      short loc_18000EDCB
0x18000edba  call    cs:__imp_closesocket
0x18000edc0  mov     cs:gIfChangeEventSocket4, 0FFFFFFFFFFFFFFFFh
0x18000edcb  mov     rcx, cs:gIfChangeEventSocket6; s
0x18000edd2  lea     rax, [rcx-1]
0x18000edd6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000edda  ja      short loc_18000EDED
0x18000eddc  call    cs:__imp_closesocket
0x18000ede2  mov     cs:gIfChangeEventSocket6, 0FFFFFFFFFFFFFFFFh
0x18000eded  cmp     cs:gbwsaStarted, 0
0x18000edf4  jz      short loc_18000EE06
0x18000edf6  call    cs:__imp_WSACleanup
0x18000edfc  mov     cs:gbwsaStarted, 0
0x18000ee06  add     rsp, 28h
0x18000ee0a  retn
```
