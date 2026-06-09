# DdmSetProtocolEvent(void)

- ea: `0x180026cc0`
- end: `0x180026e30`
- name: `?DdmSetProtocolEvent@@YAKXZ`
- size: `368`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b570`
- `0x180027960`

## callees

- `0x180007b7c`
- `0x180026cc0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180026d70`
- `KERNEL32!DeviceIoControl` at `0x180026d70`
- `KERNEL32!GetLastError` at `0x180026d7e`
- `KERNEL32!GetLastError` at `0x180026d7e`

## string_xrefs

- `0x180026d0e`: `DdmSetProtocolEvent`
- `0x180026da2`: `IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed with error 0x%x`

## pseudocode

```c
__int64 DdmSetProtocolEvent(void)
{
  DWORD v0; // ebx
  __int64 v1; // r8
  DWORD LastError; // eax
  __int64 v3; // r8
  __int64 v4; // rax
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v7; // [rsp+58h] [rbp-A8h]
  __int64 v8; // [rsp+60h] [rbp-A0h]
  int v9; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v10[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v9 = 0;
  v0 = 0;
  memset_0(v10, 0, sizeof(v10));
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v8 = 40;
    v7 = L"DdmSetProtocolEvent";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v1,
      2u,
      &v6);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x12009Cu, 0, 0, 0, 0, 0, &stru_1800C8930) )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError == 997 )
    {
      return 0;
    }
    else if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v9) = 0;
      FormatRRASErrorString(&v9, L"IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed with error 0x%x", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v4 = -1;
        do
          ++v4;
        while ( *(_WORD *)&v10[2 * v4 - 4] );
        v8 = (unsigned int)(2 * v4 + 2);
        v7 = (const wchar_t *)&v9;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v3,
          2u,
          &v6);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180026cc0  mov     [rsp-8+arg_0], rbx
0x180026cc5  mov     [rsp-8+arg_8], rdi
0x180026cca  push    rbp
0x180026ccb  lea     rbp, [rsp-780h]
0x180026cd3  sub     rsp, 880h
0x180026cda  mov     rax, cs:__security_cookie
0x180026ce1  xor     rax, rsp
0x180026ce4  mov     [rbp+780h+var_10], rax
0x180026ceb  xor     edi, edi
0x180026ced  lea     rcx, [rsp+880h+var_80C]; void *
0x180026cf2  xor     edx, edx; Val
0x180026cf4  mov     [rsp+880h+var_810], edi
0x180026cf8  mov     r8d, 7FCh; Size
0x180026cfe  mov     ebx, edi
0x180026d00  call    memset_0
0x180026d05  test    cs:byte_1800C8404, 10h
0x180026d0c  jz      short loc_180026D44
0x180026d0e  lea     rax, aDdmsetprotocol; "DdmSetProtocolEvent"
0x180026d15  mov     [rsp+880h+var_820], 28h ; '('
0x180026d1e  mov     [rsp+880h+var_828], rax
0x180026d23  lea     r9d, [rdi+2]
0x180026d27  lea     rax, [rsp+880h+var_838]
0x180026d2c  lea     rdx, RasDdmTraceInfo
0x180026d33  mov     [rsp+880h+lpOutBuffer], rax
0x180026d38  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026d3f  call    McGenEventWrite_EventWriteTransfer
0x180026d44  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180026d4b  lea     rax, stru_1800C8930
0x180026d52  mov     [rsp+880h+lpOverlapped], rax; lpOverlapped
0x180026d57  xor     r9d, r9d; nInBufferSize
0x180026d5a  mov     [rsp+880h+lpBytesReturned], rdi; lpBytesReturned
0x180026d5f  xor     r8d, r8d; lpInBuffer
0x180026d62  mov     [rsp+880h+nOutBufferSize], edi; nOutBufferSize
0x180026d66  mov     edx, 12009Ch; dwIoControlCode
0x180026d6b  mov     [rsp+880h+lpOutBuffer], rdi; lpOutBuffer
0x180026d70  call    cs:__imp_DeviceIoControl
0x180026d76  test    eax, eax
0x180026d78  jnz     loc_180026E0A
0x180026d7e  call    cs:__imp_GetLastError
0x180026d84  mov     ebx, eax
0x180026d86  cmp     eax, 3E5h
0x180026d8b  jnz     short loc_180026D91
0x180026d8d  mov     ebx, edi
0x180026d8f  jmp     short loc_180026E0A
0x180026d91  test    cs:byte_1800C8404, 8
0x180026d98  jz      short loc_180026E0A
0x180026d9a  mov     r8d, eax
0x180026d9d  mov     word ptr [rsp+880h+var_810], di
0x180026da2  lea     rdx, aIoctlNdiswanSe_1; "IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed"...
0x180026da9  lea     rcx, [rsp+880h+var_810]
0x180026dae  call    FormatRRASErrorString
0x180026db3  test    cs:byte_1800C8404, 8
0x180026dba  jz      short loc_180026E0A
0x180026dbc  lea     rdx, [rsp+880h+var_810]
0x180026dc1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026dc5  inc     rax
0x180026dc8  cmp     [rdx+rax*2], di
0x180026dcc  jnz     short loc_180026DC5
0x180026dce  lea     eax, ds:2[rax*2]
0x180026dd5  mov     dword ptr [rsp+880h+var_820+4], edi
0x180026dd9  lea     rdx, [rsp+880h+var_810]
0x180026dde  mov     dword ptr [rsp+880h+var_820], eax
0x180026de2  lea     rax, [rsp+880h+var_838]
0x180026de7  mov     [rsp+880h+var_828], rdx
0x180026dec  mov     r9d, 2
0x180026df2  mov     [rsp+880h+lpOutBuffer], rax
0x180026df7  lea     rdx, RasDdmTraceError
0x180026dfe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026e05  call    McGenEventWrite_EventWriteTransfer
0x180026e0a  mov     eax, ebx
0x180026e0c  mov     rcx, [rbp+780h+var_10]
0x180026e13  xor     rcx, rsp; StackCookie
0x180026e16  call    __security_check_cookie
0x180026e1b  lea     r11, [rsp+880h+var_s0]
0x180026e23  mov     rbx, [r11+10h]
0x180026e27  mov     rdi, [r11+18h]
0x180026e2b  mov     rsp, r11
0x180026e2e  pop     rbp
0x180026e2f  retn
```
