# CMediaElement::CMediaEngineExtension::CreateMFByteStreamFromDataURL(ushort *,IMFByteStream * *)

- ea: `0x180f0ff30`
- end: `0x180f103b5`
- name: `?CreateMFByteStreamFromDataURL@CMediaEngineExtension@CMediaElement@@IEAAJPEAGPEAPEAUIMFByteStream@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(CMediaElement::CMediaEngineExtension *__hidden this, unsigned __int16 *, struct IMFByteStream **)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180f0eb50`

## callees

- `0x180013efc`
- `0x1800151f0`
- `0x18005d080`
- `0x18005e684`
- `0x1800c5000`
- `0x1800c576c`
- `0x1805ae768`
- `0x18073082c`
- `0x180847538`
- `0x180f04408`
- `0x180f0ff30`
- `0x180f75d64`
- `0x180f75df0`
- `0x180f75f00`
- `0x18108ce68`
- `0x181104010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180f10359`
- `KERNEL32!GlobalFree` at `0x180f10359`
- `KERNEL32!GlobalLock` at `0x180f10082`
- `KERNEL32!GlobalLock` at `0x180f10082`
- `KERNEL32!GlobalUnlock` at `0x180f100dc`
- `KERNEL32!GlobalUnlock` at `0x180f10345`
- `KERNEL32!GlobalUnlock` at `0x180f100dc`
- `KERNEL32!GlobalUnlock` at `0x180f10345`
- `KERNEL32!GlobalAlloc` at `0x180f1004e`
- `KERNEL32!GlobalAlloc` at `0x180f1004e`
- `KERNEL32!GetProcAddress` at `0x180f1019f`
- `KERNEL32!GetProcAddress` at `0x180f1019f`
- `KERNEL32!GetLastError` at `0x180f101b7`
- `KERNEL32!GetLastError` at `0x180f101b7`
- `KERNEL32!LeaveCriticalSection` at `0x180f0ffa9`
- `KERNEL32!LeaveCriticalSection` at `0x180f0ffc6`
- `KERNEL32!LeaveCriticalSection` at `0x180f102d2`
- `KERNEL32!LeaveCriticalSection` at `0x180f102e0`
- `KERNEL32!LeaveCriticalSection` at `0x180f0ffa9`
- `KERNEL32!LeaveCriticalSection` at `0x180f0ffc6`
- `KERNEL32!LeaveCriticalSection` at `0x180f102d2`
- `KERNEL32!LeaveCriticalSection` at `0x180f102e0`
- `KERNEL32!EnterCriticalSection` at `0x180f0ff68`
- `KERNEL32!EnterCriticalSection` at `0x180f102ae`
- `KERNEL32!EnterCriticalSection` at `0x180f0ff68`
- `KERNEL32!EnterCriticalSection` at `0x180f102ae`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180f10100`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x180f10100`

## string_xrefs

- `0x180f0ff93`: `MF_E_SHUTDOWN in create byte stream from data URL.`
- `0x180f1037e`: `new data protocol failed in create byte stream from data URL.`
- `0x180f10024`: `SetUrl failed in create byte stream from data URL.`
- `0x180f10076`: `GlobalAlloc failed in create byte stream from data URL.`
- `0x180f100aa`: `GlobalLock failed in create byte stream from data URL.`
- `0x180f10126`: `CreateStreamOnHGlobal failed in create byte stream from data URL.`
- `0x180f10203`: `MFCreateMFByteStreamOnStream failed in create byte stream from data URL.`
- `0x180f10198`: `MFCreateMFByteStreamOnStream`

## pseudocode

```c

```
