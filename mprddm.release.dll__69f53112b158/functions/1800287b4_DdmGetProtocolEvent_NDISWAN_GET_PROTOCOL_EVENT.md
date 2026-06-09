# DdmGetProtocolEvent(_NDISWAN_GET_PROTOCOL_EVENT *)

- ea: `0x1800287b4`
- end: `0x18002895f`
- name: `?DdmGetProtocolEvent@@YAKPEAU_NDISWAN_GET_PROTOCOL_EVENT@@@Z`
- size: `427`
- prototype: `unsigned int __fastcall(struct _NDISWAN_GET_PROTOCOL_EVENT *lpOutBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180029cb0`

## callees

- `0x180007c0c`
- `0x1800287b4`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18002889b`
- `KERNEL32!DeviceIoControl` at `0x18002889b`
- `KERNEL32!GetLastError` at `0x1800288af`
- `KERNEL32!GetLastError` at `0x1800288af`

## string_xrefs

- `0x180028814`: `DdmGetProtocolEvent`
- `0x1800288cf`: `IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmGetProtocolEvent(struct _NDISWAN_GET_PROTOCOL_EVENT *lpOutBuffer)
{
  DWORD v2; // ebx
  __int64 v3; // r8
  __int64 v4; // rdi
  __int64 v5; // rax
  DWORD LastError; // eax
  __int64 v7; // r8
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+64h] [rbp-9Ch]
  int v14; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  BytesReturned = 0;
  v14 = 0;
  v2 = 0;
  memset_0(v15, 0, sizeof(v15));
  v4 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( aDdmgetprotocol_1[v5] );
    v11 = L"DdmGetProtocolEvent";
    v12 = 2 * v5 + 2;
    v13 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v3,
      2u,
      &v10);
  }
  if ( lpOutBuffer )
  {
    if ( !DeviceIoControl(gblDdmDriverInfo, 0x1200A0u, 0, 0, lpOutBuffer, 0x104u, &BytesReturned, 0) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v14) = 0;
        FormatRRASErrorString(&v14, L"IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed with error 0x%x", LastError);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v4;
          while ( *(_WORD *)&v15[2 * v4 - 4] );
          v13 = 0;
          v12 = 2 * v4 + 2;
          v11 = (const wchar_t *)&v14;
          McGenEventWrite_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasDdmTraceError,
            v7,
            2u,
            &v10);
        }
      }
    }
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x1800287b4  mov     [rsp-8+arg_8], rbx
0x1800287b9  mov     [rsp-8+arg_10], rsi
0x1800287be  push    rbp
0x1800287bf  push    rdi
0x1800287c0  push    r14
0x1800287c2  lea     rbp, [rsp-780h]
0x1800287ca  sub     rsp, 880h
0x1800287d1  mov     rax, cs:__security_cookie
0x1800287d8  xor     rax, rsp
0x1800287db  mov     [rbp+790h+var_20], rax
0x1800287e2  xor     r14d, r14d
0x1800287e5  mov     rsi, rcx
0x1800287e8  lea     rcx, [rsp+890h+var_81C]; void *
0x1800287ed  mov     [rsp+890h+BytesReturned], r14d
0x1800287f2  xor     edx, edx; Val
0x1800287f4  mov     [rsp+890h+var_820], r14d
0x1800287f9  mov     r8d, 7FCh; Size
0x1800287ff  mov     ebx, r14d
0x180028802  call    memset_0
0x180028807  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002880b  test    cs:byte_1800CF404, 10h
0x180028812  jz      short loc_180028860
0x180028814  lea     rcx, aDdmgetprotocol_1; "DdmGetProtocolEvent"
0x18002881b  mov     rax, rdi
0x18002881e  inc     rax
0x180028821  cmp     [rcx+rax*2], r14w
0x180028826  jnz     short loc_18002881E
0x180028828  lea     eax, ds:2[rax*2]
0x18002882f  mov     [rsp+890h+var_838], rcx
0x180028834  mov     [rsp+890h+var_830], eax
0x180028838  lea     rdx, RasDdmTraceInfo
0x18002883f  lea     rax, [rsp+890h+var_848]
0x180028844  mov     [rsp+890h+var_82C], r14d
0x180028849  mov     r9d, 2
0x18002884f  mov     [rsp+890h+lpOutBuffer], rax
0x180028854  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002885b  call    McGenEventWrite_EventWriteTransfer
0x180028860  test    rsi, rsi
0x180028863  jnz     short loc_18002886D
0x180028865  lea     ebx, [rsi+57h]
0x180028868  jmp     loc_180028935
0x18002886d  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180028874  lea     rax, [rsp+890h+BytesReturned]
0x180028879  mov     [rsp+890h+lpOverlapped], r14; lpOverlapped
0x18002887e  xor     r9d, r9d; nInBufferSize
0x180028881  mov     [rsp+890h+lpBytesReturned], rax; lpBytesReturned
0x180028886  xor     r8d, r8d; lpInBuffer
0x180028889  mov     [rsp+890h+nOutBufferSize], 104h; nOutBufferSize
0x180028891  mov     edx, 1200A0h; dwIoControlCode
0x180028896  mov     [rsp+890h+lpOutBuffer], rsi; lpOutBuffer
0x18002889b  call    cs:__imp_DeviceIoControl
0x1800288a2  nop     dword ptr [rax+rax+00h]
0x1800288a7  test    eax, eax
0x1800288a9  jnz     loc_180028935
0x1800288af  call    cs:__imp_GetLastError
0x1800288b6  nop     dword ptr [rax+rax+00h]
0x1800288bb  test    cs:byte_1800CF404, 8
0x1800288c2  mov     ebx, eax
0x1800288c4  jz      short loc_180028935
0x1800288c6  mov     r8d, eax
0x1800288c9  mov     word ptr [rsp+890h+var_820], r14w
0x1800288cf  lea     rdx, aIoctlNdiswanGe_1; "IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed"...
0x1800288d6  lea     rcx, [rsp+890h+var_820]
0x1800288db  call    FormatRRASErrorString
0x1800288e0  test    cs:byte_1800CF404, 8
0x1800288e7  jz      short loc_180028935
0x1800288e9  lea     rax, [rsp+890h+var_820]
0x1800288ee  inc     rdi
0x1800288f1  cmp     [rax+rdi*2], r14w
0x1800288f6  jnz     short loc_1800288EE
0x1800288f8  lea     eax, ds:2[rdi*2]
0x1800288ff  mov     [rsp+890h+var_82C], r14d
0x180028904  lea     rdx, [rsp+890h+var_820]
0x180028909  mov     [rsp+890h+var_830], eax
0x18002890d  lea     rax, [rsp+890h+var_848]
0x180028912  mov     [rsp+890h+var_838], rdx
0x180028917  mov     r9d, 2
0x18002891d  mov     [rsp+890h+lpOutBuffer], rax
0x180028922  lea     rdx, RasDdmTraceError
0x180028929  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180028930  call    McGenEventWrite_EventWriteTransfer
0x180028935  mov     eax, ebx
0x180028937  mov     rcx, [rbp+790h+var_20]
0x18002893e  xor     rcx, rsp; StackCookie
0x180028941  call    __security_check_cookie
0x180028946  lea     r11, [rsp+890h+var_10]
0x18002894e  mov     rbx, [r11+28h]
0x180028952  mov     rsi, [r11+30h]
0x180028956  mov     rsp, r11
0x180028959  pop     r14
0x18002895b  pop     rdi
0x18002895c  pop     rbp
0x18002895d  retn
```
