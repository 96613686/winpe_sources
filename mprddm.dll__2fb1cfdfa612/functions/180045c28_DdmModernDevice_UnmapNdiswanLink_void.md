# DdmModernDevice::UnmapNdiswanLink(void)

- ea: `0x180045c28`
- end: `0x180045e78`
- name: `?UnmapNdiswanLink@DdmModernDevice@@QEAAXXZ`
- size: `592`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003fad0`
- `0x18003fc60`

## callees

- `0x180007c50`
- `0x180045c28`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180045cdf`
- `msvcrt!_itow_s` at `0x180045df9`
- `msvcrt!_itow_s` at `0x180045cdf`
- `msvcrt!_itow_s` at `0x180045df9`
- `KERNEL32!DeviceIoControl` at `0x180045db8`
- `KERNEL32!DeviceIoControl` at `0x180045db8`
- `KERNEL32!GetLastError` at `0x180045dc6`
- `KERNEL32!GetLastError` at `0x180045dc6`

## string_xrefs

- `0x180045cff`: `UnmapNdiswanLink`

## pseudocode

```c
void __fastcall DdmModernDevice::UnmapNdiswanLink(DdmModernDevice *this)
{
  bool v2; // zf
  char v3; // dl
  int v4; // ecx
  __int128 v5; // xmm1
  __int64 v6; // rax
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  DWORD LastError; // edi
  int v11; // ecx
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-BCh] BYREF
  __int64 InBuffer; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Buffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+64h] [rbp-9Ch]
  __int128 v18; // [rsp+74h] [rbp-8Ch]
  int v19; // [rsp+84h] [rbp-7Ch]
  _OWORD v20[3]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v21[2]; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v23[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  BytesReturned = 0;
  InBuffer = 0;
  memset_0(v20, 0, 0x4Cu);
  v12 = 76;
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v2 = *((_QWORD *)this + 14) == -1;
  *(_DWORD *)Buffer = 0;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  v15 = 0;
  if ( !v2 )
  {
    v3 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v4 = *((_DWORD *)this + 24);
      Buffer[0] = 0;
      if ( v4 != -1 )
      {
        _itow_s(v4, Buffer, 0x14u, 10);
        v3 = byte_1800C8404;
      }
      if ( (v3 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"UnmapNdiswanLink",
          (unsigned int)&v15,
          0,
          (__int64)Buffer);
    }
    (*(void (__fastcall **)(DdmModernDevice *, int *, _OWORD *))(*(_QWORD *)this + 384LL))(this, &v12, v20);
    v5 = v20[1];
    v6 = *((_QWORD *)this + 14);
    *(_OWORD *)((char *)this + 11124) = v20[0];
    v7 = v20[2];
    *(_OWORD *)((char *)this + 11140) = v5;
    InBuffer = v6;
    v8 = v21[0];
    *(_OWORD *)((char *)this + 11156) = v7;
    v9 = *(_OWORD *)((char *)v21 + 12);
    *(_OWORD *)((char *)this + 11172) = v8;
    *((_OWORD *)this + 699) = v9;
    if ( DeviceIoControl(gblDdmDriverInfo, 0x1200B8u, &InBuffer, 8u, 0, 0, &BytesReturned, 0) )
    {
      *((_QWORD *)this + 14) = -1;
    }
    else
    {
      LastError = GetLastError();
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v22) = 0;
        Buffer[0] = 0;
        v11 = *((_DWORD *)this + 24);
        if ( v11 != -1 )
          _itow_s(v11, Buffer, 0x14u, 10);
        FormatRRASErrorString(&v22, L"IOCTL_NDISWAN_UNMAP_CONNECTION_ID failed with error 0x%x", LastError);
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v22,
            (unsigned int)&v15,
            0,
            (__int64)Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x180045c28  mov     [rsp-8+arg_8], rbx
0x180045c2d  mov     [rsp-8+arg_10], rdi
0x180045c32  push    rbp
0x180045c33  lea     rbp, [rsp-7F0h]
0x180045c3b  sub     rsp, 8F0h
0x180045c42  mov     rax, cs:__security_cookie
0x180045c49  xor     rax, rsp
0x180045c4c  mov     [rbp+7F0h+var_10], rax
0x180045c53  mov     rbx, rcx
0x180045c56  mov     [rsp+8F0h+BytesReturned], 0
0x180045c5e  mov     edi, 4Ch ; 'L'
0x180045c63  mov     [rsp+8F0h+InBuffer], 0
0x180045c6c  mov     r8d, edi; Size
0x180045c6f  lea     rcx, [rbp+7F0h+var_860]; void *
0x180045c73  xor     edx, edx; Val
0x180045c75  call    memset_0
0x180045c7a  xor     eax, eax
0x180045c7c  mov     [rsp+8F0h+var_8B0], edi
0x180045c80  xor     edx, edx; Val
0x180045c82  mov     [rbp+7F0h+var_810], eax
0x180045c85  mov     r8d, 7FCh; Size
0x180045c8b  lea     rcx, [rbp+7F0h+var_80C]; void *
0x180045c8f  call    memset_0
0x180045c94  xor     eax, eax
0x180045c96  xorps   xmm0, xmm0
0x180045c99  cmp     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x180045c9e  mov     dword ptr [rsp+8F0h+Buffer], eax
0x180045ca2  movups  [rsp+8F0h+var_88C], xmm0
0x180045ca7  mov     [rbp+7F0h+var_86C], eax
0x180045caa  movups  [rsp+8F0h+var_87C], xmm0
0x180045caf  movups  [rsp+8F0h+var_8A0], xmm0
0x180045cb4  jz      loc_180045E54
0x180045cba  mov     dl, cs:byte_1800C8404
0x180045cc0  test    dl, 10h
0x180045cc3  jz      short loc_180045D22
0x180045cc5  mov     ecx, [rbx+60h]; Value
0x180045cc8  mov     [rsp+8F0h+Buffer], ax
0x180045ccd  cmp     ecx, 0FFFFFFFFh
0x180045cd0  jz      short loc_180045CEB
0x180045cd2  lea     r9d, [rdi-42h]; Radix
0x180045cd6  lea     r8d, [rdi-38h]; BufferCount
0x180045cda  lea     rdx, [rsp+8F0h+Buffer]; Buffer
0x180045cdf  call    cs:__imp__itow_s
0x180045ce5  mov     dl, cs:byte_1800C8404
0x180045ceb  test    dl, 10h
0x180045cee  jz      short loc_180045D22
0x180045cf0  lea     rax, [rsp+8F0h+Buffer]
0x180045cf5  mov     qword ptr [rsp+8F0h+nOutBufferSize], rax
0x180045cfa  lea     r9, [rsp+8F0h+var_8A0]
0x180045cff  lea     r8, aUnmapndiswanli; "UnmapNdiswanLink"
0x180045d06  mov     [rsp+8F0h+lpOutBuffer], 0
0x180045d0f  lea     rdx, RasDdmParamTraceInfo
0x180045d16  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180045d1d  call    McTemplateU0zjzz_EventWriteTransfer
0x180045d22  mov     rax, [rbx]
0x180045d25  lea     r8, [rbp+7F0h+var_860]
0x180045d29  lea     rdx, [rsp+8F0h+var_8B0]
0x180045d2e  mov     rcx, rbx
0x180045d31  mov     rax, [rax+180h]
0x180045d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d3d  movaps  xmm0, [rbp+7F0h+var_860]
0x180045d41  lea     r8, [rsp+8F0h+InBuffer]; lpInBuffer
0x180045d46  movaps  xmm1, [rbp+7F0h+var_850]
0x180045d4a  mov     r9d, 8; nInBufferSize
0x180045d50  mov     rax, [rbx+70h]
0x180045d54  mov     edx, 1200B8h; dwIoControlCode
0x180045d59  movups  xmmword ptr [rbx+2B74h], xmm0
0x180045d60  mov     [rsp+8F0h+lpOverlapped], 0; lpOverlapped
0x180045d69  movaps  xmm0, [rbp+7F0h+var_840]
0x180045d6d  movups  xmmword ptr [rbx+2B84h], xmm1
0x180045d74  mov     [rsp+8F0h+InBuffer], rax
0x180045d79  lea     rax, [rsp+8F0h+BytesReturned]
0x180045d7e  movaps  xmm1, xmmword ptr [rbp+7F0h+var_830]
0x180045d82  movups  xmmword ptr [rbx+2B94h], xmm0
0x180045d89  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x180045d8e  movups  xmm0, xmmword ptr [rbp+7F0h+var_830+0Ch]
0x180045d92  mov     [rsp+8F0h+nOutBufferSize], 0; nOutBufferSize
0x180045d9a  movups  xmmword ptr [rbx+2BA4h], xmm1
0x180045da1  mov     [rsp+8F0h+lpOutBuffer], 0; lpOutBuffer
0x180045daa  movups  xmmword ptr [rbx+2BB0h], xmm0
0x180045db1  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180045db8  call    cs:__imp_DeviceIoControl
0x180045dbe  test    eax, eax
0x180045dc0  jnz     loc_180045E4C
0x180045dc6  call    cs:__imp_GetLastError
0x180045dcc  test    cs:byte_1800C8404, 8
0x180045dd3  mov     edi, eax
0x180045dd5  jz      short loc_180045E54
0x180045dd7  xor     ecx, ecx
0x180045dd9  mov     word ptr [rbp+7F0h+var_810], cx
0x180045ddd  mov     [rsp+8F0h+Buffer], cx
0x180045de2  mov     ecx, [rbx+60h]; Value
0x180045de5  cmp     ecx, 0FFFFFFFFh
0x180045de8  jz      short loc_180045DFF
0x180045dea  mov     r9d, 0Ah; Radix
0x180045df0  lea     rdx, [rsp+8F0h+Buffer]; Buffer
0x180045df5  lea     r8d, [r9+0Ah]; BufferCount
0x180045df9  call    cs:__imp__itow_s
0x180045dff  mov     r8d, edi
0x180045e02  lea     rdx, aIoctlNdiswanUn; "IOCTL_NDISWAN_UNMAP_CONNECTION_ID faile"...
0x180045e09  lea     rcx, [rbp+7F0h+var_810]
0x180045e0d  call    FormatRRASErrorString
0x180045e12  test    cs:byte_1800C8404, 8
0x180045e19  jz      short loc_180045E54
0x180045e1b  lea     rax, [rsp+8F0h+Buffer]
0x180045e20  mov     qword ptr [rsp+8F0h+nOutBufferSize], rax
0x180045e25  lea     r9, [rsp+8F0h+var_8A0]
0x180045e2a  lea     r8, [rbp+7F0h+var_810]
0x180045e2e  mov     [rsp+8F0h+lpOutBuffer], 0
0x180045e37  lea     rdx, RasDdmParamTraceError
0x180045e3e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180045e45  call    McTemplateU0zjzz_EventWriteTransfer
0x180045e4a  jmp     short loc_180045E54
0x180045e4c  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x180045e54  mov     rcx, [rbp+7F0h+var_10]
0x180045e5b  xor     rcx, rsp; StackCookie
0x180045e5e  call    __security_check_cookie
0x180045e63  lea     r11, [rsp+8F0h+var_s0]
0x180045e6b  mov     rbx, [r11+18h]
0x180045e6f  mov     rdi, [r11+20h]
0x180045e73  mov     rsp, r11
0x180045e76  pop     rbp
0x180045e77  retn
```
