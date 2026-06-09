# CAAUDPClientChannel::InternalConnect(void)

- ea: `0x18053e484`
- end: `0x18053f9c2`
- name: `?InternalConnect@CAAUDPClientChannel@@AEAAJXZ`
- size: `5438`
- prototype: `__int64 __fastcall(CAAUDPClientChannel *__hidden this)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation`

## callers

- `0x18053c8a0`
- `0x18053ce2c`

## callees

- `0x18001cdc0`
- `0x18001f5d0`
- `0x1800204e8`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800f7748`
- `0x18012962c`
- `0x18012966c`
- `0x18022702c`
- `0x18053cc9c`
- `0x18053cd64`
- `0x18053e484`
- `0x18053fbc4`
- `0x180540f40`
- `0x18054271c`
- `0x180542854`
- `0x180545704`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18053edcc`
- `msvcrt!memcpy_s` at `0x18053f341`
- `msvcrt!memcpy_s` at `0x18053edcc`
- `msvcrt!memcpy_s` at `0x18053f341`
- `KERNEL32!GetLastError` at `0x18053f443`
- `KERNEL32!GetLastError` at `0x18053f443`
- `KERNEL32!LocalAlloc` at `0x18053e715`
- `KERNEL32!LocalAlloc` at `0x18053e87e`
- `KERNEL32!LocalAlloc` at `0x18053ed4e`
- `KERNEL32!LocalAlloc` at `0x18053f2b9`
- `KERNEL32!LocalAlloc` at `0x18053e715`
- `KERNEL32!LocalAlloc` at `0x18053e87e`
- `KERNEL32!LocalAlloc` at `0x18053ed4e`
- `KERNEL32!LocalAlloc` at `0x18053f2b9`
- `KERNEL32!LocalFree` at `0x18053e903`
- `KERNEL32!LocalFree` at `0x18053e915`
- `KERNEL32!LocalFree` at `0x18053f913`
- `KERNEL32!LocalFree` at `0x18053f996`
- `KERNEL32!LocalFree` at `0x18053e903`
- `KERNEL32!LocalFree` at `0x18053e915`
- `KERNEL32!LocalFree` at `0x18053f913`
- `KERNEL32!LocalFree` at `0x18053f996`
- `WS2_32!WSAAddressToStringW` at `0x18053f20e`
- `WS2_32!WSAAddressToStringW` at `0x18053f20e`
- `WS2_32!__imp_WSAGetLastError` at `0x18053f218`
- `WS2_32!__imp_WSAGetLastError` at `0x18053f218`

## string_xrefs

- `0x18053f89c`: `IssueRead failed`
- `0x18053f8ba`: `IssueRead failed`
- `0x18053f784`: `InternalConnect: SetSideTransportProperty for up mtu failed`
- `0x18053f7a2`: `InternalConnect: SetSideTransportProperty for up mtu failed`
- `0x18053f7f6`: `InternalConnect: SetSideTransportProperty for down mtu failed`
- `0x18053f814`: `InternalConnect: SetSideTransportProperty for down mtu failed`
- `0x18053e5b1`: `m_ChannelContext->GetSideTransportProperty`
- `0x18053e5fc`: `m_ChannelContext->GetSideTransportProperty`
- `0x18053e812`: `m_ChannelContext->GetSideTransportProperty`
- `0x18053e86a`: `m_ChannelContext->GetSideTransportProperty`

## pseudocode

```c

```
