# DdmUpdateQoSPolicies

- ea: `0x180014c9c`
- end: `0x180014e3a`
- name: `DdmUpdateQoSPolicies`
- size: `414`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007400`

## callees

- `0x180007c0c`
- `0x180014c9c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180014d76`
- `KERNEL32!DeviceIoControl` at `0x180014d76`
- `KERNEL32!GetLastError` at `0x180014d8a`
- `KERNEL32!GetLastError` at `0x180014d8a`

## string_xrefs

- `0x180014cfc`: `DdmUpdateQoSPolicies`
- `0x180014daa`: `IOCTL_NDISWAN_UPDATE_QOS_POLICIES failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmUpdateQoSPolicies(LPVOID lpInBuffer)
{
  DWORD v2; // edi
  __int64 v3; // r8
  __int64 v4; // rbx
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
    while ( aDdmupdateqospo[v5] );
    v11 = L"DdmUpdateQoSPolicies";
    v12 = 2 * v5 + 2;
    v13 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v3,
      2u,
      &v10);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x1200BCu, lpInBuffer, 0x1Cu, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v14) = 0;
      FormatRRASErrorString(&v14, L"IOCTL_NDISWAN_UPDATE_QOS_POLICIES failed with error 0x%x", LastError);
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
  return v2;
}

```

## disassembly

```asm
0x180014c9c  mov     [rsp-8+arg_8], rbx
0x180014ca1  mov     [rsp-8+arg_10], rsi
0x180014ca6  push    rbp
0x180014ca7  push    rdi
0x180014ca8  push    r14
0x180014caa  lea     rbp, [rsp-780h]
0x180014cb2  sub     rsp, 880h
0x180014cb9  mov     rax, cs:__security_cookie
0x180014cc0  xor     rax, rsp
0x180014cc3  mov     [rbp+790h+var_20], rax
0x180014cca  xor     r14d, r14d
0x180014ccd  mov     rsi, rcx
0x180014cd0  lea     rcx, [rsp+890h+var_81C]; void *
0x180014cd5  mov     [rsp+890h+BytesReturned], r14d
0x180014cda  xor     edx, edx; Val
0x180014cdc  mov     [rsp+890h+var_820], r14d
0x180014ce1  mov     r8d, 7FCh; Size
0x180014ce7  mov     edi, r14d
0x180014cea  call    memset_0
0x180014cef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180014cf3  test    cs:byte_1800CF404, 10h
0x180014cfa  jz      short loc_180014D48
0x180014cfc  lea     rcx, aDdmupdateqospo; "DdmUpdateQoSPolicies"
0x180014d03  mov     rax, rbx
0x180014d06  inc     rax
0x180014d09  cmp     [rcx+rax*2], r14w
0x180014d0e  jnz     short loc_180014D06
0x180014d10  lea     eax, ds:2[rax*2]
0x180014d17  mov     [rsp+890h+var_838], rcx
0x180014d1c  mov     [rsp+890h+var_830], eax
0x180014d20  lea     rdx, RasDdmTraceInfo
0x180014d27  lea     rax, [rsp+890h+var_848]
0x180014d2c  mov     [rsp+890h+var_82C], r14d
0x180014d31  mov     r9d, 2
0x180014d37  mov     [rsp+890h+lpOutBuffer], rax
0x180014d3c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014d43  call    McGenEventWrite_EventWriteTransfer
0x180014d48  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180014d4f  lea     rax, [rsp+890h+BytesReturned]
0x180014d54  mov     [rsp+890h+lpOverlapped], r14; lpOverlapped
0x180014d59  mov     r9d, 1Ch; nInBufferSize
0x180014d5f  mov     [rsp+890h+lpBytesReturned], rax; lpBytesReturned
0x180014d64  mov     r8, rsi; lpInBuffer
0x180014d67  mov     [rsp+890h+nOutBufferSize], r14d; nOutBufferSize
0x180014d6c  mov     edx, 1200BCh; dwIoControlCode
0x180014d71  mov     [rsp+890h+lpOutBuffer], r14; lpOutBuffer
0x180014d76  call    cs:__imp_DeviceIoControl
0x180014d7d  nop     dword ptr [rax+rax+00h]
0x180014d82  test    eax, eax
0x180014d84  jnz     loc_180014E10
0x180014d8a  call    cs:__imp_GetLastError
0x180014d91  nop     dword ptr [rax+rax+00h]
0x180014d96  test    cs:byte_1800CF404, 8
0x180014d9d  mov     edi, eax
0x180014d9f  jz      short loc_180014E10
0x180014da1  mov     r8d, eax
0x180014da4  mov     word ptr [rsp+890h+var_820], r14w
0x180014daa  lea     rdx, aIoctlNdiswanUp; "IOCTL_NDISWAN_UPDATE_QOS_POLICIES faile"...
0x180014db1  lea     rcx, [rsp+890h+var_820]
0x180014db6  call    FormatRRASErrorString
0x180014dbb  test    cs:byte_1800CF404, 8
0x180014dc2  jz      short loc_180014E10
0x180014dc4  lea     rax, [rsp+890h+var_820]
0x180014dc9  inc     rbx
0x180014dcc  cmp     [rax+rbx*2], r14w
0x180014dd1  jnz     short loc_180014DC9
0x180014dd3  lea     eax, ds:2[rbx*2]
0x180014dda  mov     [rsp+890h+var_82C], r14d
0x180014ddf  lea     rdx, [rsp+890h+var_820]
0x180014de4  mov     [rsp+890h+var_830], eax
0x180014de8  lea     rax, [rsp+890h+var_848]
0x180014ded  mov     [rsp+890h+var_838], rdx
0x180014df2  mov     r9d, 2
0x180014df8  mov     [rsp+890h+lpOutBuffer], rax
0x180014dfd  lea     rdx, RasDdmTraceError
0x180014e04  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014e0b  call    McGenEventWrite_EventWriteTransfer
0x180014e10  mov     eax, edi
0x180014e12  mov     rcx, [rbp+790h+var_20]
0x180014e19  xor     rcx, rsp; StackCookie
0x180014e1c  call    __security_check_cookie
0x180014e21  lea     r11, [rsp+890h+var_10]
0x180014e29  mov     rbx, [r11+28h]
0x180014e2d  mov     rsi, [r11+30h]
0x180014e31  mov     rsp, r11
0x180014e34  pop     r14
0x180014e36  pop     rdi
0x180014e37  pop     rbp
0x180014e38  retn
```
