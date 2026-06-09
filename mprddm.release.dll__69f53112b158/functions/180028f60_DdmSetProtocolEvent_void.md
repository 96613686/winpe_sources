# DdmSetProtocolEvent(void)

- ea: `0x180028f60`
- end: `0x1800290f9`
- name: `?DdmSetProtocolEvent@@YAKXZ`
- size: `409`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001bf40`
- `0x180029cb0`

## callees

- `0x180007c0c`
- `0x180028f60`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18002902c`
- `KERNEL32!DeviceIoControl` at `0x18002902c`
- `KERNEL32!GetLastError` at `0x180029040`
- `KERNEL32!GetLastError` at `0x180029040`

## string_xrefs

- `0x180028fb6`: `DdmSetProtocolEvent`
- `0x18002906a`: `IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed with error 0x%x`

## pseudocode

```c
__int64 DdmSetProtocolEvent(void)
{
  DWORD v0; // ebx
  __int64 v1; // r8
  __int64 v2; // rdi
  __int64 v3; // rax
  DWORD LastError; // eax
  __int64 v5; // r8
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+48h] [rbp-C0h] BYREF
  const wchar_t *v8; // [rsp+58h] [rbp-B0h]
  int v9; // [rsp+60h] [rbp-A8h]
  int v10; // [rsp+64h] [rbp-A4h]
  int v11; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v12[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  v11 = 0;
  v0 = 0;
  memset_0(v12, 0, sizeof(v12));
  v2 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( aDdmsetprotocol[v3] );
    v8 = L"DdmSetProtocolEvent";
    v9 = 2 * v3 + 2;
    v10 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v1,
      2u,
      &v7);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x12009Cu, 0, 0, 0, 0, 0, &stru_1800CF930) )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError == 997 )
    {
      return 0;
    }
    else if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(&v11, L"IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed with error 0x%x", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v2;
        while ( *(_WORD *)&v12[2 * v2 - 4] );
        v10 = 0;
        v9 = 2 * v2 + 2;
        v8 = (const wchar_t *)&v11;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v5,
          2u,
          &v7);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180028f60  mov     rax, rsp
0x180028f63  mov     [rax+8], rbx
0x180028f67  mov     [rax+10h], rsi
0x180028f6b  mov     [rax+18h], rdi
0x180028f6f  push    rbp
0x180028f70  lea     rbp, [rax-778h]
0x180028f77  sub     rsp, 870h
0x180028f7e  mov     rax, cs:__security_cookie
0x180028f85  xor     rax, rsp
0x180028f88  mov     [rbp+770h+var_10], rax
0x180028f8f  xor     esi, esi
0x180028f91  lea     rcx, [rsp+870h+var_80C]; void *
0x180028f96  xor     edx, edx; Val
0x180028f98  mov     [rsp+870h+var_810], esi
0x180028f9c  mov     r8d, 7FCh; Size
0x180028fa2  mov     ebx, esi
0x180028fa4  call    memset_0
0x180028fa9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028fad  test    cs:byte_1800CF404, 10h
0x180028fb4  jz      short loc_180029000
0x180028fb6  lea     rcx, aDdmsetprotocol; "DdmSetProtocolEvent"
0x180028fbd  mov     rax, rdi
0x180028fc0  inc     rax
0x180028fc3  cmp     [rcx+rax*2], si
0x180028fc7  jnz     short loc_180028FC0
0x180028fc9  lea     eax, ds:2[rax*2]
0x180028fd0  mov     [rsp+870h+var_820], rcx
0x180028fd5  mov     [rsp+870h+var_818], eax
0x180028fd9  lea     rdx, RasDdmTraceInfo
0x180028fe0  lea     rax, [rsp+870h+var_830]
0x180028fe5  mov     [rsp+870h+var_814], esi
0x180028fe9  mov     r9d, 2
0x180028fef  mov     [rsp+870h+lpOutBuffer], rax
0x180028ff4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180028ffb  call    McGenEventWrite_EventWriteTransfer
0x180029000  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180029007  lea     rax, stru_1800CF930
0x18002900e  mov     [rsp+870h+lpOverlapped], rax; lpOverlapped
0x180029013  xor     r9d, r9d; nInBufferSize
0x180029016  mov     [rsp+870h+lpBytesReturned], rsi; lpBytesReturned
0x18002901b  xor     r8d, r8d; lpInBuffer
0x18002901e  mov     [rsp+870h+nOutBufferSize], esi; nOutBufferSize
0x180029022  mov     edx, 12009Ch; dwIoControlCode
0x180029027  mov     [rsp+870h+lpOutBuffer], rsi; lpOutBuffer
0x18002902c  call    cs:__imp_DeviceIoControl
0x180029033  nop     dword ptr [rax+rax+00h]
0x180029038  test    eax, eax
0x18002903a  jnz     loc_1800290CE
0x180029040  call    cs:__imp_GetLastError
0x180029047  nop     dword ptr [rax+rax+00h]
0x18002904c  mov     ebx, eax
0x18002904e  cmp     eax, 3E5h
0x180029053  jnz     short loc_180029059
0x180029055  mov     ebx, esi
0x180029057  jmp     short loc_1800290CE
0x180029059  test    cs:byte_1800CF404, 8
0x180029060  jz      short loc_1800290CE
0x180029062  mov     r8d, eax
0x180029065  mov     word ptr [rsp+870h+var_810], si
0x18002906a  lea     rdx, aIoctlNdiswanSe_1; "IOCTL_NDISWAN_SET_PROTOCOL_EVENT failed"...
0x180029071  lea     rcx, [rsp+870h+var_810]
0x180029076  call    FormatRRASErrorString
0x18002907b  test    cs:byte_1800CF404, 8
0x180029082  jz      short loc_1800290CE
0x180029084  lea     rax, [rsp+870h+var_810]
0x180029089  inc     rdi
0x18002908c  cmp     [rax+rdi*2], si
0x180029090  jnz     short loc_180029089
0x180029092  lea     eax, ds:2[rdi*2]
0x180029099  mov     [rsp+870h+var_814], esi
0x18002909d  lea     rdx, [rsp+870h+var_810]
0x1800290a2  mov     [rsp+870h+var_818], eax
0x1800290a6  lea     rax, [rsp+870h+var_830]
0x1800290ab  mov     [rsp+870h+var_820], rdx
0x1800290b0  mov     r9d, 2
0x1800290b6  mov     [rsp+870h+lpOutBuffer], rax
0x1800290bb  lea     rdx, RasDdmTraceError
0x1800290c2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800290c9  call    McGenEventWrite_EventWriteTransfer
0x1800290ce  mov     eax, ebx
0x1800290d0  mov     rcx, [rbp+770h+var_10]
0x1800290d7  xor     rcx, rsp; StackCookie
0x1800290da  call    __security_check_cookie
0x1800290df  lea     r11, [rsp+870h+var_s0]
0x1800290e7  mov     rbx, [r11+10h]
0x1800290eb  mov     rsi, [r11+18h]
0x1800290ef  mov     rdi, [r11+20h]
0x1800290f3  mov     rsp, r11
0x1800290f6  pop     rbp
0x1800290f7  retn
```
