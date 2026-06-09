# DeviceUpdateCallback(unsigned __int64,long)

- ea: `0x180002190`
- end: `0x180002211`
- name: `?DeviceUpdateCallback@@YAX_KJ@Z`
- size: `129`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002190`
- `0x180003000`
- `0x18000303c`
- `0x180003074`
- `0x1800030b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800021ed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800021ed`

## string_xrefs

- `0x1800021a9`: `DeviceUpdateCallback`
- `0x1800021ba`: `DeviceUpdateCallback`
- `0x1800021d8`: `DeviceUpdateCallback`
- `0x1800021f3`: `DeviceUpdateCallback`
- `0x1800021a2`: `%s: Device update operation result is 0x%08x.`
- `0x1800021df`: `%s: pContext->completeEvent is NULL`
- `0x1800021fa`: `%s: pContext->completeEvent is set`

## pseudocode

```c
void __fastcall DeviceUpdateCallback(__int64 a1, unsigned int a2)
{
  void *v4; // rcx

  Logger::TraceInformation(L"%s: Device update operation result is 0x%08x.", L"DeviceUpdateCallback", a2);
  if ( !a1 )
    Logger::TraceError(L"%s: pContext is NULL", L"DeviceUpdateCallback");
  v4 = *(void **)(a1 + 8);
  *(_DWORD *)a1 = a2;
  if ( v4 )
  {
    SetEvent(v4);
    Logger::TraceVerbose(L"%s: pContext->completeEvent is set", L"DeviceUpdateCallback");
  }
  else
  {
    Logger::TraceWarning(L"%s: pContext->completeEvent is NULL", L"DeviceUpdateCallback");
  }
}

```

## disassembly

```asm
0x180002190  mov     [rsp+arg_0], rbx
0x180002195  push    rdi
0x180002196  sub     rsp, 20h
0x18000219a  mov     edi, edx
0x18000219c  mov     rbx, rcx
0x18000219f  mov     r8d, edx
0x1800021a2  lea     rcx, aSDeviceUpdateO; "%s: Device update operation result is 0"...
0x1800021a9  lea     rdx, aDeviceupdateca; "DeviceUpdateCallback"
0x1800021b0  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800021b5  test    rbx, rbx
0x1800021b8  jnz     short loc_1800021CD
0x1800021ba  lea     rdx, aDeviceupdateca; "DeviceUpdateCallback"
0x1800021c1  lea     rcx, aSPcontextIsNul; "%s: pContext is NULL"
0x1800021c8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800021cd  mov     rcx, [rbx+8]; hEvent
0x1800021d1  mov     [rbx], edi
0x1800021d3  test    rcx, rcx
0x1800021d6  jnz     short loc_1800021ED
0x1800021d8  lea     rdx, aDeviceupdateca; "DeviceUpdateCallback"
0x1800021df  lea     rcx, aSPcontextCompl; "%s: pContext->completeEvent is NULL"
0x1800021e6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800021eb  jmp     short loc_180002206
0x1800021ed  call    cs:__imp_SetEvent
0x1800021f3  lea     rdx, aDeviceupdateca; "DeviceUpdateCallback"
0x1800021fa  lea     rcx, aSPcontextCompl_0; "%s: pContext->completeEvent is set"
0x180002201  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180002206  mov     rbx, [rsp+28h+arg_0]
0x18000220b  add     rsp, 20h
0x18000220f  pop     rdi
0x180002210  retn
```
