# DdmModernDevice::GetProtocolCompression(_RAS_PROTOCOLTYPE,_RAS_PROTOCOLCOMPRESSION *,_RAS_PROTOCOLCOMPRESSION *)

- ea: `0x180042b00`
- end: `0x180042d52`
- name: `?GetProtocolCompression@DdmModernDevice@@UEAAKW4_RAS_PROTOCOLTYPE@@PEAU_RAS_PROTOCOLCOMPRESSION@@1@Z`
- size: `594`
- prototype: `__int64 __fastcall(__int64, int, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180042b00`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180042cab`
- `KERNEL32!DeviceIoControl` at `0x180042cab`
- `KERNEL32!GetLastError` at `0x180042cbb`
- `KERNEL32!GetLastError` at `0x180042cbb`

## string_xrefs

- `0x180042bc1`: `GetProtocolCompression`
- `0x180042c1d`: `GetProtocolCompression failed. Type 0x%x not supported`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::GetProtocolCompression(__int64 a1, int a2, _DWORD *a3, _DWORD *a4)
{
  DWORD LastError; // edi
  char v9; // al
  unsigned int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 OutBuffer; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v17; // [rsp+58h] [rbp-A8h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  __int128 v19; // [rsp+6Ch] [rbp-94h]
  __int128 v20; // [rsp+7Ch] [rbp-84h]
  int v21; // [rsp+8Ch] [rbp-74h]
  int v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  BytesReturned = 0;
  v15 = 0;
  v22 = 0;
  LastError = 0;
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v21 = 0;
  v9 = byte_1800CF404;
  v10 = -1;
  v19 = 0;
  v20 = 0;
  v17 = 0;
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v18) = 0;
    v11 = a1 ? *(unsigned int *)(a1 + 96) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v18, v11);
    v9 = byte_1800CF404;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"GetProtocolCompression",
        (unsigned int)&v17,
        0,
        (__int64)&v18);
      v9 = byte_1800CF404;
    }
  }
  if ( a2 != 2048 )
  {
    LastError = 50;
    if ( (v9 & 8) == 0 )
      return LastError;
    LOWORD(v22) = 0;
    LOWORD(v18) = 0;
    if ( a1 )
      v10 = *(_DWORD *)(a1 + 96);
    ConvertPortNoToString(&v18, v10);
    FormatRRASErrorString(&v22, L"GetProtocolCompression failed. Type 0x%x not supported", 50);
    goto LABEL_12;
  }
  OutBuffer = *(_QWORD *)(a1 + 112);
  if ( DeviceIoControl(gblDdmDriverInfo, 0x120054u, &OutBuffer, 0x10u, &OutBuffer, 0x10u, &BytesReturned, 0) )
  {
    *a3 = v15;
    *a4 = HIDWORD(v15);
    return LastError;
  }
  LastError = GetLastError();
  if ( (byte_1800CF404 & 8) != 0 )
  {
    v12 = *(unsigned int *)(a1 + 96);
    LOWORD(v22) = 0;
    LOWORD(v18) = 0;
    ConvertPortNoToString(&v18, v12);
    FormatRRASErrorString(&v22, L"IOCTL_NDISWAN_GET_VJ_INFO failed with error 0x%x", LastError);
LABEL_12:
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v22,
        (unsigned int)&v17,
        0,
        (__int64)&v18);
  }
  return LastError;
}

```

## disassembly

```asm
0x180042b00  mov     [rsp-8+arg_8], rbx
0x180042b05  push    rbp
0x180042b06  push    rsi
0x180042b07  push    rdi
0x180042b08  push    r12
0x180042b0a  push    r13
0x180042b0c  push    r14
0x180042b0e  push    r15
0x180042b10  lea     rbp, [rsp-7A0h]
0x180042b18  sub     rsp, 8A0h
0x180042b1f  mov     rax, cs:__security_cookie
0x180042b26  xor     rax, rsp
0x180042b29  mov     [rbp+7D0h+var_40], rax
0x180042b30  xor     r13d, r13d
0x180042b33  mov     rsi, r8
0x180042b36  mov     r12d, edx
0x180042b39  mov     [rsp+8D0h+BytesReturned], r13d
0x180042b3e  mov     rbx, rcx
0x180042b41  mov     [rsp+8D0h+var_888], r13
0x180042b46  xor     edx, edx; Val
0x180042b48  mov     [rbp+7D0h+var_840], r13d
0x180042b4c  mov     r8d, 7FCh; Size
0x180042b52  lea     rcx, [rbp+7D0h+var_83C]; void *
0x180042b56  mov     edi, r13d
0x180042b59  mov     r14, r9
0x180042b5c  call    memset_0
0x180042b61  xor     eax, eax
0x180042b63  mov     [rsp+8D0h+var_868], r13d
0x180042b68  xorps   xmm0, xmm0
0x180042b6b  mov     [rbp+7D0h+var_844], eax
0x180042b6e  mov     al, cs:byte_1800CF404
0x180042b74  or      r15d, 0FFFFFFFFh
0x180042b78  movups  [rsp+8D0h+var_864], xmm0
0x180042b7d  movups  [rsp+8D0h+var_854], xmm0
0x180042b82  movups  [rsp+8D0h+var_878], xmm0
0x180042b87  test    al, 8
0x180042b89  jz      short loc_180042BE6
0x180042b8b  mov     word ptr [rsp+8D0h+var_868], r13w
0x180042b91  test    rbx, rbx
0x180042b94  jz      short loc_180042B9B
0x180042b96  mov     edx, [rbx+60h]
0x180042b99  jmp     short loc_180042B9E
0x180042b9b  mov     edx, r15d
0x180042b9e  lea     rcx, [rsp+8D0h+var_868]
0x180042ba3  call    ConvertPortNoToString
0x180042ba8  mov     al, cs:byte_1800CF404
0x180042bae  test    al, 8
0x180042bb0  jz      short loc_180042BE6
0x180042bb2  lea     rax, [rsp+8D0h+var_868]
0x180042bb7  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x180042bbc  lea     r9, [rsp+8D0h+var_878]
0x180042bc1  lea     r8, aGetprotocolcom; "GetProtocolCompression"
0x180042bc8  mov     [rsp+8D0h+lpOutBuffer], r13
0x180042bcd  lea     rdx, RasDdmParamTraceError
0x180042bd4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042bdb  call    McTemplateU0zjzz_EventWriteTransfer
0x180042be0  mov     al, cs:byte_1800CF404
0x180042be6  cmp     r12d, 800h
0x180042bed  jz      short loc_180042C6D
0x180042bef  mov     edi, 32h ; '2'
0x180042bf4  test    al, 8
0x180042bf6  jz      loc_180042D25
0x180042bfc  mov     word ptr [rbp+7D0h+var_840], r13w
0x180042c01  mov     word ptr [rsp+8D0h+var_868], r13w
0x180042c07  test    rbx, rbx
0x180042c0a  jz      short loc_180042C10
0x180042c0c  mov     r15d, [rbx+60h]
0x180042c10  mov     edx, r15d
0x180042c13  lea     rcx, [rsp+8D0h+var_868]
0x180042c18  call    ConvertPortNoToString
0x180042c1d  lea     rdx, aGetprotocolcom_0; "GetProtocolCompression failed. Type 0x%"...
0x180042c24  mov     r8d, edi
0x180042c27  lea     rcx, [rbp+7D0h+var_840]
0x180042c2b  call    FormatRRASErrorString
0x180042c30  test    cs:byte_1800CF404, 8
0x180042c37  jz      loc_180042D25
0x180042c3d  lea     rax, [rsp+8D0h+var_868]
0x180042c42  mov     qword ptr [rsp+8D0h+nOutBufferSize], rax
0x180042c47  lea     r9, [rsp+8D0h+var_878]
0x180042c4c  lea     r8, [rbp+7D0h+var_840]
0x180042c50  mov     [rsp+8D0h+lpOutBuffer], r13
0x180042c55  lea     rdx, RasDdmParamTraceError
0x180042c5c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042c63  call    McTemplateU0zjzz_EventWriteTransfer
0x180042c68  jmp     loc_180042D25
0x180042c6d  mov     rax, [rbx+70h]
0x180042c71  lea     r8, [rsp+8D0h+OutBuffer]; lpInBuffer
0x180042c76  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180042c7d  mov     r9d, 10h; nInBufferSize
0x180042c83  mov     [rsp+8D0h+OutBuffer], rax
0x180042c88  mov     edx, 120054h; dwIoControlCode
0x180042c8d  mov     [rsp+8D0h+lpOverlapped], r13; lpOverlapped
0x180042c92  lea     rax, [rsp+8D0h+BytesReturned]
0x180042c97  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x180042c9c  lea     rax, [rsp+8D0h+OutBuffer]
0x180042ca1  mov     [rsp+8D0h+nOutBufferSize], r9d; nOutBufferSize
0x180042ca6  mov     [rsp+8D0h+lpOutBuffer], rax; lpOutBuffer
0x180042cab  call    cs:__imp_DeviceIoControl
0x180042cb2  nop     dword ptr [rax+rax+00h]
0x180042cb7  test    eax, eax
0x180042cb9  jnz     short loc_180042CF6
0x180042cbb  call    cs:__imp_GetLastError
0x180042cc2  nop     dword ptr [rax+rax+00h]
0x180042cc7  test    cs:byte_1800CF404, 8
0x180042cce  mov     edi, eax
0x180042cd0  jz      short loc_180042D25
0x180042cd2  mov     edx, [rbx+60h]
0x180042cd5  lea     rcx, [rsp+8D0h+var_868]
0x180042cda  mov     word ptr [rbp+7D0h+var_840], r13w
0x180042cdf  mov     word ptr [rsp+8D0h+var_868], r13w
0x180042ce5  call    ConvertPortNoToString
0x180042cea  lea     rdx, aIoctlNdiswanGe_0; "IOCTL_NDISWAN_GET_VJ_INFO failed with e"...
0x180042cf1  jmp     loc_180042C24
0x180042cf6  movzx   eax, word ptr [rsp+8D0h+var_888]
0x180042cfb  mov     [rsi], ax
0x180042cfe  mov     al, byte ptr [rsp+8D0h+var_888+2]
0x180042d02  mov     [rsi+2], al
0x180042d05  mov     al, byte ptr [rsp+8D0h+var_888+3]
0x180042d09  mov     [rsi+3], al
0x180042d0c  movzx   eax, word ptr [rsp+8D0h+var_888+4]
0x180042d11  mov     [r14], ax
0x180042d15  mov     al, byte ptr [rsp+8D0h+var_888+6]
0x180042d19  mov     [r14+2], al
0x180042d1d  mov     al, byte ptr [rsp+8D0h+var_888+7]
0x180042d21  mov     [r14+3], al
0x180042d25  mov     eax, edi
0x180042d27  mov     rcx, [rbp+7D0h+var_40]
0x180042d2e  xor     rcx, rsp; StackCookie
0x180042d31  call    __security_check_cookie
0x180042d36  mov     rbx, [rsp+8D0h+arg_8]
0x180042d3e  add     rsp, 8A0h
0x180042d45  pop     r15
0x180042d47  pop     r14
0x180042d49  pop     r13
0x180042d4b  pop     r12
0x180042d4d  pop     rdi
0x180042d4e  pop     rsi
0x180042d4f  pop     rbp
0x180042d50  retn
```
