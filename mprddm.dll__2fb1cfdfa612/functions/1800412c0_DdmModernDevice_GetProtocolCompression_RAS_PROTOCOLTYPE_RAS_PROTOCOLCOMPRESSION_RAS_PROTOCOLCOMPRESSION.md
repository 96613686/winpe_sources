# DdmModernDevice::GetProtocolCompression(_RAS_PROTOCOLTYPE,_RAS_PROTOCOLCOMPRESSION *,_RAS_PROTOCOLCOMPRESSION *)

- ea: `0x1800412c0`
- end: `0x180041520`
- name: `?GetProtocolCompression@DdmModernDevice@@UEAAKW4_RAS_PROTOCOLTYPE@@PEAU_RAS_PROTOCOLCOMPRESSION@@1@Z`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x1800412c0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x18004135d`
- `msvcrt!_itow_s` at `0x1800413e5`
- `msvcrt!_itow_s` at `0x1800414be`
- `msvcrt!_itow_s` at `0x18004135d`
- `msvcrt!_itow_s` at `0x1800413e5`
- `msvcrt!_itow_s` at `0x1800414be`
- `KERNEL32!DeviceIoControl` at `0x180041481`
- `KERNEL32!DeviceIoControl` at `0x180041481`
- `KERNEL32!GetLastError` at `0x18004148b`
- `KERNEL32!GetLastError` at `0x18004148b`

## string_xrefs

- `0x18004137d`: `GetProtocolCompression`
- `0x1800413eb`: `GetProtocolCompression failed. Type 0x%x not supported`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::GetProtocolCompression(__int64 a1, int a2, _DWORD *a3, _DWORD *a4)
{
  char v8; // dl
  int v9; // ecx
  DWORD LastError; // ebx
  int v11; // ecx
  int v12; // ecx
  __int128 OutBuffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Buffer[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+6Ch] [rbp-94h]
  __int128 v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  BytesReturned = 0;
  v21 = 0;
  OutBuffer = 0;
  memset_0(v22, 0, sizeof(v22));
  v8 = byte_1800C8404;
  *(_DWORD *)Buffer = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v16 = 0;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    Buffer[0] = 0;
    if ( a1 )
    {
      v9 = *(_DWORD *)(a1 + 96);
      if ( v9 != -1 )
      {
        _itow_s(v9, Buffer, 0x14u, 10);
        v8 = byte_1800C8404;
      }
    }
    if ( (v8 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"GetProtocolCompression",
        (unsigned int)&v16,
        0,
        (__int64)Buffer);
      v8 = byte_1800C8404;
    }
  }
  if ( a2 != 2048 )
  {
    LastError = 50;
    if ( (v8 & 8) == 0 )
      return LastError;
    LOWORD(v21) = 0;
    Buffer[0] = 0;
    if ( a1 )
    {
      v11 = *(_DWORD *)(a1 + 96);
      if ( v11 != -1 )
        _itow_s(v11, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(&v21, L"GetProtocolCompression failed. Type 0x%x not supported", 50);
    goto LABEL_13;
  }
  *(_QWORD *)&OutBuffer = *(_QWORD *)(a1 + 112);
  if ( DeviceIoControl(gblDdmDriverInfo, 0x120054u, &OutBuffer, 0x10u, &OutBuffer, 0x10u, &BytesReturned, 0) )
  {
    LastError = 0;
    *a3 = DWORD2(OutBuffer);
    *a4 = HIDWORD(OutBuffer);
    return LastError;
  }
  LastError = GetLastError();
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v21) = 0;
    Buffer[0] = 0;
    v12 = *(_DWORD *)(a1 + 96);
    if ( v12 != -1 )
      _itow_s(v12, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v21, L"IOCTL_NDISWAN_GET_VJ_INFO failed with error 0x%x", LastError);
LABEL_13:
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v21,
        (unsigned int)&v16,
        0,
        (__int64)Buffer);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800412c0  push    rbp
0x1800412c2  push    rbx
0x1800412c3  push    rsi
0x1800412c4  push    rdi
0x1800412c5  push    r14
0x1800412c7  lea     rbp, [rsp-7A0h]
0x1800412cf  sub     rsp, 8A0h
0x1800412d6  mov     rax, cs:__security_cookie
0x1800412dd  xor     rax, rsp
0x1800412e0  mov     [rbp+7C0h+var_30], rax
0x1800412e7  mov     r14, r8
0x1800412ea  mov     [rsp+8C0h+BytesReturned], 0
0x1800412f2  mov     ebx, edx
0x1800412f4  mov     rdi, rcx
0x1800412f7  xorps   xmm0, xmm0
0x1800412fa  lea     rcx, [rbp+7C0h+var_82C]; void *
0x1800412fe  xor     eax, eax
0x180041300  xor     edx, edx; Val
0x180041302  mov     r8d, 7FCh; Size
0x180041308  mov     [rbp+7C0h+var_830], eax
0x18004130b  movups  [rsp+8C0h+OutBuffer], xmm0
0x180041310  mov     rsi, r9
0x180041313  call    memset_0
0x180041318  mov     dl, cs:byte_1800C8404
0x18004131e  xor     eax, eax
0x180041320  mov     dword ptr [rsp+8C0h+Buffer], eax
0x180041324  xorps   xmm0, xmm0
0x180041327  mov     [rbp+7C0h+var_834], eax
0x18004132a  movups  [rsp+8C0h+var_854], xmm0
0x18004132f  movups  [rsp+8C0h+var_844], xmm0
0x180041334  movups  [rsp+8C0h+var_868], xmm0
0x180041339  test    dl, 8
0x18004133c  jz      short loc_1800413A6
0x18004133e  mov     [rsp+8C0h+Buffer], ax
0x180041343  test    rdi, rdi
0x180041346  jz      short loc_180041369
0x180041348  mov     ecx, [rdi+60h]; Value
0x18004134b  cmp     ecx, 0FFFFFFFFh
0x18004134e  jz      short loc_180041369
0x180041350  lea     r9d, [rax+0Ah]; Radix
0x180041354  lea     r8d, [rax+14h]; BufferCount
0x180041358  lea     rdx, [rsp+8C0h+Buffer]; Buffer
0x18004135d  call    cs:__imp__itow_s
0x180041363  mov     dl, cs:byte_1800C8404
0x180041369  test    dl, 8
0x18004136c  jz      short loc_1800413A6
0x18004136e  lea     rax, [rsp+8C0h+Buffer]
0x180041373  mov     qword ptr [rsp+8C0h+nOutBufferSize], rax
0x180041378  lea     r9, [rsp+8C0h+var_868]
0x18004137d  lea     r8, aGetprotocolcom; "GetProtocolCompression"
0x180041384  mov     [rsp+8C0h+lpOutBuffer], 0
0x18004138d  lea     rdx, RasDdmParamTraceError
0x180041394  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004139b  call    McTemplateU0zjzz_EventWriteTransfer
0x1800413a0  mov     dl, cs:byte_1800C8404
0x1800413a6  cmp     ebx, 800h
0x1800413ac  jz      loc_18004143F
0x1800413b2  mov     ebx, 32h ; '2'
0x1800413b7  test    dl, 8
0x1800413ba  jz      loc_180041501
0x1800413c0  xor     eax, eax
0x1800413c2  mov     word ptr [rbp+7C0h+var_830], ax
0x1800413c6  mov     [rsp+8C0h+Buffer], ax
0x1800413cb  test    rdi, rdi
0x1800413ce  jz      short loc_1800413EB
0x1800413d0  mov     ecx, [rdi+60h]; Value
0x1800413d3  cmp     ecx, 0FFFFFFFFh
0x1800413d6  jz      short loc_1800413EB
0x1800413d8  lea     r9d, [rbx-28h]; Radix
0x1800413dc  lea     r8d, [rbx-1Eh]; BufferCount
0x1800413e0  lea     rdx, [rsp+8C0h+Buffer]; Buffer
0x1800413e5  call    cs:__imp__itow_s
0x1800413eb  lea     rdx, aGetprotocolcom_0; "GetProtocolCompression failed. Type 0x%"...
0x1800413f2  mov     r8d, ebx
0x1800413f5  lea     rcx, [rbp+7C0h+var_830]
0x1800413f9  call    FormatRRASErrorString
0x1800413fe  test    cs:byte_1800C8404, 8
0x180041405  jz      loc_180041501
0x18004140b  lea     rax, [rsp+8C0h+Buffer]
0x180041410  mov     qword ptr [rsp+8C0h+nOutBufferSize], rax
0x180041415  lea     r9, [rsp+8C0h+var_868]
0x18004141a  lea     r8, [rbp+7C0h+var_830]
0x18004141e  mov     [rsp+8C0h+lpOutBuffer], 0
0x180041427  lea     rdx, RasDdmParamTraceError
0x18004142e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041435  call    McTemplateU0zjzz_EventWriteTransfer
0x18004143a  jmp     loc_180041501
0x18004143f  mov     rax, [rdi+70h]
0x180041443  lea     r8, [rsp+8C0h+OutBuffer]; lpInBuffer
0x180041448  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x18004144f  mov     r9d, 10h; nInBufferSize
0x180041455  mov     qword ptr [rsp+8C0h+OutBuffer], rax
0x18004145a  mov     edx, 120054h; dwIoControlCode
0x18004145f  mov     [rsp+8C0h+lpOverlapped], 0; lpOverlapped
0x180041468  lea     rax, [rsp+8C0h+BytesReturned]
0x18004146d  mov     [rsp+8C0h+lpBytesReturned], rax; lpBytesReturned
0x180041472  lea     rax, [rsp+8C0h+OutBuffer]
0x180041477  mov     [rsp+8C0h+nOutBufferSize], r9d; nOutBufferSize
0x18004147c  mov     [rsp+8C0h+lpOutBuffer], rax; lpOutBuffer
0x180041481  call    cs:__imp_DeviceIoControl
0x180041487  test    eax, eax
0x180041489  jnz     short loc_1800414D0
0x18004148b  call    cs:__imp_GetLastError
0x180041491  test    cs:byte_1800C8404, 8
0x180041498  mov     ebx, eax
0x18004149a  jz      short loc_180041501
0x18004149c  xor     ecx, ecx
0x18004149e  mov     word ptr [rbp+7C0h+var_830], cx
0x1800414a2  mov     [rsp+8C0h+Buffer], cx
0x1800414a7  mov     ecx, [rdi+60h]; Value
0x1800414aa  cmp     ecx, 0FFFFFFFFh
0x1800414ad  jz      short loc_1800414C4
0x1800414af  mov     r9d, 0Ah; Radix
0x1800414b5  lea     rdx, [rsp+8C0h+Buffer]; Buffer
0x1800414ba  lea     r8d, [r9+0Ah]; BufferCount
0x1800414be  call    cs:__imp__itow_s
0x1800414c4  lea     rdx, aIoctlNdiswanGe_0; "IOCTL_NDISWAN_GET_VJ_INFO failed with e"...
0x1800414cb  jmp     loc_1800413F2
0x1800414d0  movzx   eax, word ptr [rsp+8C0h+OutBuffer+8]
0x1800414d5  xor     ebx, ebx
0x1800414d7  mov     [r14], ax
0x1800414db  mov     al, byte ptr [rsp+8C0h+OutBuffer+0Ah]
0x1800414df  mov     [r14+2], al
0x1800414e3  mov     al, byte ptr [rsp+8C0h+OutBuffer+0Bh]
0x1800414e7  mov     [r14+3], al
0x1800414eb  movzx   eax, word ptr [rsp+8C0h+OutBuffer+0Ch]
0x1800414f0  mov     [rsi], ax
0x1800414f3  mov     al, byte ptr [rsp+8C0h+OutBuffer+0Eh]
0x1800414f7  mov     [rsi+2], al
0x1800414fa  mov     al, byte ptr [rsp+8C0h+OutBuffer+0Fh]
0x1800414fe  mov     [rsi+3], al
0x180041501  mov     eax, ebx
0x180041503  mov     rcx, [rbp+7C0h+var_30]
0x18004150a  xor     rcx, rsp; StackCookie
0x18004150d  call    __security_check_cookie
0x180041512  add     rsp, 8A0h
0x180041519  pop     r14
0x18004151b  pop     rdi
0x18004151c  pop     rsi
0x18004151d  pop     rbx
0x18004151e  pop     rbp
0x18004151f  retn
```
