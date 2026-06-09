# pSetupSetFileCompressionState

- ea: `0x180007ff0`
- end: `0x1800080b0`
- name: `pSetupSetFileCompressionState`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800054d4`

## callees

- `0x180007f70`
- `0x180007ff0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000809d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008080`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008095`
- `KERNEL32!DeviceIoControl` at `0x180008076`
- `KERNEL32!DeviceIoControl` at `0x180008076`

## pseudocode

```c
_BOOL8 __fastcall pSetupSetFileCompressionState(const WCHAR *a1, int a2, __int64 a3)
{
  DWORD LastError; // ebx
  HANDLE hDevice; // [rsp+40h] [rbp-18h] BYREF
  __int16 InBuffer; // [rsp+68h] [rbp+10h] BYREF
  __int16 InBuffer_2; // [rsp+6Ah] [rbp+12h]
  LONG v8; // [rsp+70h] [rbp+18h] BYREF
  DWORD BytesReturned; // [rsp+78h] [rbp+20h] BYREF

  InBuffer_2 = HIWORD(a2);
  hDevice = (HANDLE)-1LL;
  InBuffer = 0;
  v8 = 0;
  BytesReturned = 0;
  LastError = pSetupOpenFileForWrite(a1, 0, a3, 0, &hDevice, &v8);
  if ( !LastError )
  {
    InBuffer = 1;
    if ( !DeviceIoControl(hDevice, 0x9C040u, &InBuffer, 2u, 0, 0, &BytesReturned, 0) )
      LastError = GetLastError();
  }
  if ( hDevice != (HANDLE)-1LL )
    CloseHandle(hDevice);
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x180007ff0  mov     [rsp+InBuffer], edx
0x180007ff4  mov     r11, rsp
0x180007ff7  push    rbx
0x180007ff8  sub     rsp, 50h
0x180007ffc  xor     eax, eax
0x180007ffe  mov     qword ptr [r11-18h], 0FFFFFFFFFFFFFFFFh
0x180008006  mov     word ptr [rsp+58h+InBuffer], ax
0x18000800b  xor     r9d, r9d
0x18000800e  lea     rax, [r11+18h]
0x180008012  mov     [rsp+58h+arg_10], 0
0x18000801a  mov     [r11-30h], rax
0x18000801e  xor     edx, edx
0x180008020  lea     rax, [r11-18h]
0x180008024  mov     [rsp+58h+BytesReturned], 0
0x18000802c  mov     [r11-38h], rax
0x180008030  call    pSetupOpenFileForWrite
0x180008035  mov     ebx, eax
0x180008037  test    eax, eax
0x180008039  jnz     short loc_180008088
0x18000803b  mov     rcx, [rsp+58h+hDevice]; hDevice
0x180008040  lea     eax, [rbx+1]
0x180008043  mov     [rsp+58h+lpOverlapped], 0; lpOverlapped
0x18000804c  lea     r9d, [rbx+2]; nInBufferSize
0x180008050  mov     word ptr [rsp+58h+InBuffer], ax
0x180008055  lea     r8, [rsp+58h+InBuffer]; lpInBuffer
0x18000805a  lea     rax, [rsp+58h+BytesReturned]
0x18000805f  mov     edx, 9C040h; dwIoControlCode
0x180008064  mov     [rsp+58h+lpBytesReturned], rax; lpBytesReturned
0x180008069  mov     [rsp+58h+nOutBufferSize], ebx; nOutBufferSize
0x18000806d  mov     [rsp+58h+lpOutBuffer], 0; lpOutBuffer
0x180008076  call    cs:__imp_DeviceIoControl
0x18000807c  test    eax, eax
0x18000807e  jnz     short loc_180008088
0x180008080  call    cs:__imp_GetLastError
0x180008086  mov     ebx, eax
0x180008088  cmp     [rsp+58h+hDevice], 0FFFFFFFFFFFFFFFFh
0x18000808e  jz      short loc_18000809B
0x180008090  mov     rcx, [rsp+58h+hDevice]; hObject
0x180008095  call    cs:__imp_CloseHandle
0x18000809b  mov     ecx, ebx; dwErrCode
0x18000809d  call    cs:__imp_SetLastError
0x1800080a3  xor     eax, eax
0x1800080a5  test    ebx, ebx
0x1800080a7  setz    al
0x1800080aa  add     rsp, 50h
0x1800080ae  pop     rbx
0x1800080af  retn
```
