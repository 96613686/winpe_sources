# SmsWapMsgHandler::~SmsWapMsgHandler(void)

- ea: `0x180002e94`
- end: `0x180002ed2`
- name: `??1SmsWapMsgHandler@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(SmsWapMsgHandler *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004bec`

## callees

- `0x180003098`
- `0x180003d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002eae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180002eae`
- `EventAggregation!EaDeleteAggregation` at `0x180002ea4`
- `EventAggregation!EaDeleteAggregation` at `0x180002ea4`

## pseudocode

```c
void __fastcall SmsWapMsgHandler::~SmsWapMsgHandler(SmsWapMsgHandler *this)
{
  EaDeleteAggregation(*((_QWORD *)this + 19));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  SmsWapMsgHandler::CleanSmsWapMsgStruct(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease((char *)this + 8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(this);
}

```

## disassembly

```asm
0x180002e94  push    rbx
0x180002e96  sub     rsp, 20h
0x180002e9a  mov     rbx, rcx
0x180002e9d  mov     rcx, [rcx+98h]
0x180002ea4  call    cs:__imp_EaDeleteAggregation
0x180002eaa  lea     rcx, [rbx+70h]; lpCriticalSection
0x180002eae  call    cs:__imp_DeleteCriticalSection
0x180002eb4  mov     rcx, rbx; this
0x180002eb7  call    ?CleanSmsWapMsgStruct@SmsWapMsgHandler@@AEAAXXZ; SmsWapMsgHandler::CleanSmsWapMsgStruct(void)
0x180002ebc  lea     rcx, [rbx+8]
0x180002ec0  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x180002ec5  mov     rcx, rbx
0x180002ec8  add     rsp, 20h
0x180002ecc  pop     rbx
0x180002ecd  jmp     ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
```
