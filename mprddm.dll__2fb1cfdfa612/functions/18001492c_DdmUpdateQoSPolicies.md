# DdmUpdateQoSPolicies

- ea: `0x18001492c`
- end: `0x180014a8a`
- name: `DdmUpdateQoSPolicies`
- size: `350`
- prototype: `__int64 __fastcall(LPVOID lpInBuffer)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800073e0`

## callees

- `0x180007b7c`
- `0x18001492c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800149de`
- `KERNEL32!DeviceIoControl` at `0x1800149de`
- `KERNEL32!GetLastError` at `0x1800149ec`
- `KERNEL32!GetLastError` at `0x1800149ec`

## string_xrefs

- `0x18001497b`: `DdmUpdateQoSPolicies`
- `0x180014a05`: `IOCTL_NDISWAN_UPDATE_QOS_POLICIES failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmUpdateQoSPolicies(LPVOID lpInBuffer)
{
  DWORD v2; // ebx
  __int64 v3; // r8
  DWORD LastError; // eax
  __int64 v5; // r8
  __int64 v6; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v10; // [rsp+58h] [rbp-A8h]
  __int64 v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  BytesReturned = 0;
  v12 = 0;
  v2 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v11 = 42;
    v10 = L"DdmUpdateQoSPolicies";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v3,
      2u,
      &v9);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x1200BCu, lpInBuffer, 0x1Cu, 0, 0, &BytesReturned, 0) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"IOCTL_NDISWAN_UPDATE_QOS_POLICIES failed with error 0x%x", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v6 = -1;
        do
          ++v6;
        while ( *(_WORD *)&v13[2 * v6 - 4] );
        v11 = (unsigned int)(2 * v6 + 2);
        v10 = (const wchar_t *)&v12;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v5,
          2u,
          &v9);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001492c  push    rbp
0x18001492e  push    rbx
0x18001492f  push    rsi
0x180014930  push    rdi
0x180014931  lea     rbp, [rsp-788h]
0x180014939  sub     rsp, 888h
0x180014940  mov     rax, cs:__security_cookie
0x180014947  xor     rax, rsp
0x18001494a  mov     [rbp+7A0h+var_30], rax
0x180014951  xor     esi, esi
0x180014953  mov     rdi, rcx
0x180014956  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18001495b  mov     [rsp+8A0h+BytesReturned], esi
0x18001495f  xor     edx, edx; Val
0x180014961  mov     [rsp+8A0h+var_830], esi
0x180014965  mov     r8d, 7FCh; Size
0x18001496b  mov     ebx, esi
0x18001496d  call    memset_0
0x180014972  test    cs:byte_1800C8404, 10h
0x180014979  jz      short loc_1800149B1
0x18001497b  lea     rax, aDdmupdateqospo; "DdmUpdateQoSPolicies"
0x180014982  mov     [rsp+8A0h+var_840], 2Ah ; '*'
0x18001498b  mov     [rsp+8A0h+var_848], rax
0x180014990  lea     r9d, [rsi+2]
0x180014994  lea     rax, [rsp+8A0h+var_858]
0x180014999  lea     rdx, RasDdmTraceInfo
0x1800149a0  mov     [rsp+8A0h+lpOutBuffer], rax
0x1800149a5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800149ac  call    McGenEventWrite_EventWriteTransfer
0x1800149b1  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x1800149b8  lea     rax, [rsp+8A0h+BytesReturned]
0x1800149bd  mov     [rsp+8A0h+lpOverlapped], rsi; lpOverlapped
0x1800149c2  mov     r9d, 1Ch; nInBufferSize
0x1800149c8  mov     [rsp+8A0h+lpBytesReturned], rax; lpBytesReturned
0x1800149cd  mov     r8, rdi; lpInBuffer
0x1800149d0  mov     [rsp+8A0h+nOutBufferSize], esi; nOutBufferSize
0x1800149d4  mov     edx, 1200BCh; dwIoControlCode
0x1800149d9  mov     [rsp+8A0h+lpOutBuffer], rsi; lpOutBuffer
0x1800149de  call    cs:__imp_DeviceIoControl
0x1800149e4  test    eax, eax
0x1800149e6  jnz     loc_180014A6D
0x1800149ec  call    cs:__imp_GetLastError
0x1800149f2  test    cs:byte_1800C8404, 8
0x1800149f9  mov     ebx, eax
0x1800149fb  jz      short loc_180014A6D
0x1800149fd  mov     r8d, eax
0x180014a00  mov     word ptr [rsp+8A0h+var_830], si
0x180014a05  lea     rdx, aIoctlNdiswanUp; "IOCTL_NDISWAN_UPDATE_QOS_POLICIES faile"...
0x180014a0c  lea     rcx, [rsp+8A0h+var_830]
0x180014a11  call    FormatRRASErrorString
0x180014a16  test    cs:byte_1800C8404, 8
0x180014a1d  jz      short loc_180014A6D
0x180014a1f  lea     rdx, [rsp+8A0h+var_830]
0x180014a24  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014a28  inc     rax
0x180014a2b  cmp     [rdx+rax*2], si
0x180014a2f  jnz     short loc_180014A28
0x180014a31  lea     eax, ds:2[rax*2]
0x180014a38  mov     dword ptr [rsp+8A0h+var_840+4], esi
0x180014a3c  lea     rdx, [rsp+8A0h+var_830]
0x180014a41  mov     dword ptr [rsp+8A0h+var_840], eax
0x180014a45  lea     rax, [rsp+8A0h+var_858]
0x180014a4a  mov     [rsp+8A0h+var_848], rdx
0x180014a4f  mov     r9d, 2
0x180014a55  mov     [rsp+8A0h+lpOutBuffer], rax
0x180014a5a  lea     rdx, RasDdmTraceError
0x180014a61  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014a68  call    McGenEventWrite_EventWriteTransfer
0x180014a6d  mov     eax, ebx
0x180014a6f  mov     rcx, [rbp+7A0h+var_30]
0x180014a76  xor     rcx, rsp; StackCookie
0x180014a79  call    __security_check_cookie
0x180014a7e  add     rsp, 888h
0x180014a85  pop     rdi
0x180014a86  pop     rsi
0x180014a87  pop     rbx
0x180014a88  pop     rbp
0x180014a89  retn
```
