# UpdateDevice(void)

- ea: `0x18000273c`
- end: `0x18000286b`
- name: `?UpdateDevice@@YAJXZ`
- size: `303`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x18000273c`
- `0x180002874`
- `0x180003000`
- `0x18000303c`
- `0x180003074`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000277b`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000277b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000278b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000278b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002858`
- `dsreg!DsrBeginDeviceUpdate` at `0x1800027e7`
- `dsreg!DsrBeginDeviceUpdate` at `0x1800027e7`

## string_xrefs

- `0x180002794`: `CallbackContext::CreateCompleteEvent`
- `0x1800027c3`: `CallbackContext::CreateCompleteEvent`
- `0x18000279b`: `%s: CreateEventEx failed with error code: 0x%08x`
- `0x180002823`: `DeviceUpdateCallback`
- `0x180002746`: `UpdateDevice`
- `0x1800027f6`: `DsrBeginDeviceUpdate`

## pseudocode

```c
__int64 UpdateDevice(void)
{
  __int64 LastError; // rbx
  const wchar_t *v1; // r8
  int v2; // eax
  __int64 v3; // r9
  int v4; // eax
  __int64 v6; // [rsp+20h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-10h]

  Logger::TraceVerbose(L"%s started", L"UpdateDevice");
  LODWORD(v6) = 0;
  hObject = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !hObject )
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CreateEventEx failed with error code: 0x%08x",
      L"CallbackContext::CreateCompleteEvent",
      LastError);
    if ( (_DWORD)LastError )
    {
      if ( (int)LastError <= 0 )
      {
LABEL_6:
        v1 = L"CallbackContext::CreateCompleteEvent";
LABEL_13:
        v3 = (unsigned int)LastError;
        goto LABEL_14;
      }
    }
    else
    {
      LOWORD(LastError) = 1359;
    }
    LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_6;
  }
  Logger::TraceInformation(L"%s: Begin updating device attributes.", L"UpdateDevice");
  v2 = DsrBeginDeviceUpdate(DeviceUpdateCallback, &v6);
  LODWORD(LastError) = v2;
  if ( v2 >= 0 )
  {
    v4 = WaitForCallback((const struct CallbackContext *)&v6);
    LODWORD(LastError) = v4;
    if ( v4 >= 0 )
    {
      LODWORD(LastError) = v6;
      if ( (int)v6 >= 0 )
        goto LABEL_15;
      v1 = L"DeviceUpdateCallback";
      goto LABEL_13;
    }
    v3 = (unsigned int)v4;
    v1 = L"WaitForCallback";
  }
  else
  {
    v3 = (unsigned int)v2;
    v1 = L"DsrBeginDeviceUpdate";
  }
LABEL_14:
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"UpdateDevice", v1, v3, v6);
LABEL_15:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"UpdateDevice", (unsigned int)LastError);
  if ( hObject )
    CloseHandle(hObject);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000273c  mov     [rsp+arg_0], rbx
0x180002741  push    rdi
0x180002742  sub     rsp, 30h
0x180002746  lea     rdi, aUpdatedevice; "UpdateDevice"
0x18000274d  mov     rdx, rdi
0x180002750  lea     rcx, aSStarted; "%s started"
0x180002757  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000275c  xor     edx, edx; lpName
0x18000275e  mov     dword ptr [rsp+38h+var_18], 0
0x180002766  xor     ecx, ecx; lpEventAttributes
0x180002768  mov     [rsp+38h+hObject], 0
0x180002771  mov     r9d, 1F0003h; dwDesiredAccess
0x180002777  lea     r8d, [rdx+1]; dwFlags
0x18000277b  call    cs:__imp_CreateEventExW
0x180002781  mov     [rsp+38h+hObject], rax
0x180002786  test    rax, rax
0x180002789  jnz     short loc_1800027CC
0x18000278b  call    cs:__imp_GetLastError
0x180002791  mov     r8d, eax
0x180002794  lea     rdx, aCallbackcontex; "CallbackContext::CreateCompleteEvent"
0x18000279b  lea     rcx, aSCreateeventex; "%s: CreateEventEx failed with error cod"...
0x1800027a2  mov     ebx, eax
0x1800027a4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800027a9  test    ebx, ebx
0x1800027ab  jnz     short loc_1800027B4
0x1800027ad  mov     ebx, 54Fh
0x1800027b2  jmp     short loc_1800027B6
0x1800027b4  jle     short loc_1800027BF
0x1800027b6  movzx   ebx, bx
0x1800027b9  or      ebx, 80070000h
0x1800027bf  test    ebx, ebx
0x1800027c1  jns     short loc_1800027CC
0x1800027c3  lea     r8, aCallbackcontex; "CallbackContext::CreateCompleteEvent"
0x1800027ca  jmp     short loc_18000282A
0x1800027cc  mov     rdx, rdi
0x1800027cf  lea     rcx, aSBeginUpdating; "%s: Begin updating device attributes."
0x1800027d6  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800027db  lea     rdx, [rsp+38h+var_18]
0x1800027e0  lea     rcx, ?DeviceUpdateCallback@@YAX_KJ@Z; DeviceUpdateCallback(unsigned __int64,long)
0x1800027e7  call    cs:__imp_DsrBeginDeviceUpdate
0x1800027ed  mov     ebx, eax
0x1800027ef  test    eax, eax
0x1800027f1  jns     short loc_1800027FF
0x1800027f3  mov     r9d, eax
0x1800027f6  lea     r8, aDsrbegindevice; "DsrBeginDeviceUpdate"
0x1800027fd  jmp     short loc_18000282D
0x1800027ff  lea     rcx, [rsp+38h+var_18]; struct CallbackContext *
0x180002804  call    ?WaitForCallback@@YAJAEBUCallbackContext@@@Z; WaitForCallback(CallbackContext const &)
0x180002809  mov     ebx, eax
0x18000280b  test    eax, eax
0x18000280d  jns     short loc_18000281B
0x18000280f  mov     r9d, eax
0x180002812  lea     r8, aWaitforcallbac; "WaitForCallback"
0x180002819  jmp     short loc_18000282D
0x18000281b  mov     ebx, dword ptr [rsp+38h+var_18]
0x18000281f  test    ebx, ebx
0x180002821  jns     short loc_18000283C
0x180002823  lea     r8, aDeviceupdateca; "DeviceUpdateCallback"
0x18000282a  mov     r9d, ebx
0x18000282d  mov     rdx, rdi
0x180002830  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x."
0x180002837  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000283c  mov     r8d, ebx
0x18000283f  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x180002846  mov     rdx, rdi
0x180002849  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000284e  mov     rcx, [rsp+38h+hObject]; hObject
0x180002853  test    rcx, rcx
0x180002856  jz      short loc_18000285E
0x180002858  call    cs:__imp_CloseHandle
0x18000285e  mov     eax, ebx
0x180002860  mov     rbx, [rsp+38h+arg_0]
0x180002865  add     rsp, 30h
0x180002869  pop     rdi
0x18000286a  retn
```
