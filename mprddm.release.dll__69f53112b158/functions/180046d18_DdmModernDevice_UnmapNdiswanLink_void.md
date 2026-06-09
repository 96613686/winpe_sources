# DdmModernDevice::UnmapNdiswanLink(void)

- ea: `0x180046d18`
- end: `0x180046f3a`
- name: `?UnmapNdiswanLink@DdmModernDevice@@QEAAXXZ`
- size: `546`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180041360`
- `0x1800414e0`

## callees

- `0x180007d00`
- `0x180046d18`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180046e86`
- `KERNEL32!DeviceIoControl` at `0x180046e86`
- `KERNEL32!GetLastError` at `0x180046e96`
- `KERNEL32!GetLastError` at `0x180046e96`

## string_xrefs

- `0x180046dd2`: `UnmapNdiswanLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DdmModernDevice::UnmapNdiswanLink(DdmModernDevice *this)
{
  bool v2; // zf
  __int64 v3; // rdx
  __int128 v4; // xmm1
  int v5; // eax
  __int128 v6; // xmm0
  __int128 v7; // xmm1
  DWORD LastError; // edi
  __int64 v9; // rdx
  DWORD BytesReturned[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-B8h] BYREF
  __int128 InBuffer_8; // [rsp+58h] [rbp-B0h] BYREF
  _DWORD v13[12]; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD v14[4]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v15; // [rsp+D8h] [rbp-30h]
  int v16; // [rsp+E0h] [rbp-28h]
  int v17; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v18[2044]; // [rsp+ECh] [rbp-1Ch] BYREF

  BytesReturned[1] = 0;
  memset_0(v14, 0, 0x4Cu);
  BytesReturned[0] = 76;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  memset(v13, 0, 40);
  v2 = *((_QWORD *)this + 14) == -1;
  InBuffer_8 = 0;
  if ( !v2 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v3 = *((unsigned int *)this + 24);
      LOWORD(v13[0]) = 0;
      ConvertPortNoToString(v13, v3);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"UnmapNdiswanLink",
          (unsigned int)&InBuffer_8,
          0,
          (__int64)v13);
    }
    (*(void (__fastcall **)(DdmModernDevice *, DWORD *, _OWORD *))(*(_QWORD *)this + 384LL))(this, BytesReturned, v14);
    v4 = v14[1];
    v5 = v16;
    *(_OWORD *)((char *)this + 11124) = v14[0];
    v6 = v14[2];
    *(_OWORD *)((char *)this + 11140) = v4;
    v7 = v14[3];
    *(_OWORD *)((char *)this + 11156) = v6;
    *(_QWORD *)&v6 = v15;
    *(_OWORD *)((char *)this + 11172) = v7;
    *(_QWORD *)((char *)this + 11188) = v6;
    *((_DWORD *)this + 2799) = v5;
    InBuffer = *((_QWORD *)this + 14);
    if ( DeviceIoControl(gblDdmDriverInfo, 0x1200B8u, &InBuffer, 8u, 0, 0, &BytesReturned[1], 0) )
    {
      *((_QWORD *)this + 14) = -1;
    }
    else
    {
      LastError = GetLastError();
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v9 = *((unsigned int *)this + 24);
        LOWORD(v17) = 0;
        LOWORD(v13[0]) = 0;
        ConvertPortNoToString(v13, v9);
        FormatRRASErrorString(&v17, L"IOCTL_NDISWAN_UNMAP_CONNECTION_ID failed with error 0x%x", LastError);
        if ( (byte_1800CF404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v17,
            (unsigned int)&InBuffer_8,
            0,
            (__int64)v13);
      }
    }
  }
}

```

## disassembly

```asm
0x180046d18  mov     rax, rsp
0x180046d1b  mov     [rax+10h], rbx
0x180046d1f  mov     [rax+18h], rsi
0x180046d23  mov     [rax+20h], rdi
0x180046d27  push    rbp
0x180046d28  lea     rbp, [rax-7F8h]
0x180046d2f  sub     rsp, 8F0h
0x180046d36  mov     rax, cs:__security_cookie
0x180046d3d  xor     rax, rsp
0x180046d40  mov     [rbp+7F0h+var_10], rax
0x180046d47  xor     esi, esi
0x180046d49  mov     rbx, rcx
0x180046d4c  xor     edx, edx; Val
0x180046d4e  mov     [rsp+8F0h+BytesReturned+4], esi
0x180046d52  lea     rcx, [rbp+7F0h+var_860]; void *
0x180046d56  lea     edi, [rsi+4Ch]
0x180046d59  mov     r8d, edi; Size
0x180046d5c  call    memset_0
0x180046d61  xor     edx, edx; Val
0x180046d63  mov     [rsp+8F0h+BytesReturned], edi
0x180046d67  mov     r8d, 7FCh; Size
0x180046d6d  mov     [rbp+7F0h+var_810], esi
0x180046d70  lea     rcx, [rbp+7F0h+var_80C]; void *
0x180046d74  call    memset_0
0x180046d79  xorps   xmm0, xmm0
0x180046d7c  mov     dword ptr [rsp+8F0h+var_894+4], esi
0x180046d80  xor     eax, eax
0x180046d82  cmp     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x180046d87  movups  [rsp+8F0h+var_894+8], xmm0
0x180046d8c  mov     [rbp+7F0h+var_86C], eax
0x180046d8f  movups  xmmword ptr [rsp+8F0h+var_884+8], xmm0
0x180046d94  movups  [rsp+8F0h+InBuffer+8], xmm0
0x180046d99  jz      loc_180046F11
0x180046d9f  test    cs:byte_1800CF404, 10h
0x180046da6  jz      short loc_180046DF1
0x180046da8  mov     edx, [rbx+60h]
0x180046dab  lea     rcx, [rsp+8F0h+var_894+4]
0x180046db0  mov     word ptr [rsp+8F0h+var_894+4], si
0x180046db5  call    ConvertPortNoToString
0x180046dba  test    cs:byte_1800CF404, 10h
0x180046dc1  jz      short loc_180046DF1
0x180046dc3  lea     rax, [rsp+8F0h+var_894+4]
0x180046dc8  mov     qword ptr [rsp+8F0h+nOutBufferSize], rax
0x180046dcd  lea     r9, [rsp+8F0h+InBuffer+8]
0x180046dd2  lea     r8, aUnmapndiswanli; "UnmapNdiswanLink"
0x180046dd9  mov     [rsp+8F0h+lpOutBuffer], rsi
0x180046dde  lea     rdx, RasDdmParamTraceInfo
0x180046de5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180046dec  call    McTemplateU0zjzz_EventWriteTransfer
0x180046df1  mov     rax, [rbx]
0x180046df4  lea     r8, [rbp+7F0h+var_860]
0x180046df8  lea     rdx, [rsp+8F0h+BytesReturned]
0x180046dfd  mov     rcx, rbx
0x180046e00  mov     rax, [rax+180h]
0x180046e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e0c  movaps  xmm0, [rbp+7F0h+var_860]
0x180046e10  lea     r8, [rsp+8F0h+InBuffer]; lpInBuffer
0x180046e15  movaps  xmm1, [rbp+7F0h+var_850]
0x180046e19  mov     r9d, 8; nInBufferSize
0x180046e1f  mov     eax, [rbp+7F0h+var_818]
0x180046e22  mov     edx, 1200B8h; dwIoControlCode
0x180046e27  movups  xmmword ptr [rbx+2B74h], xmm0
0x180046e2e  mov     [rsp+8F0h+lpOverlapped], rsi; lpOverlapped
0x180046e33  movaps  xmm0, [rbp+7F0h+var_840]
0x180046e37  movups  xmmword ptr [rbx+2B84h], xmm1
0x180046e3e  movaps  xmm1, [rbp+7F0h+var_830]
0x180046e42  movups  xmmword ptr [rbx+2B94h], xmm0
0x180046e49  movsd   xmm0, [rbp+7F0h+var_820]
0x180046e4e  movups  xmmword ptr [rbx+2BA4h], xmm1
0x180046e55  movsd   qword ptr [rbx+2BB4h], xmm0
0x180046e5d  mov     [rbx+2BBCh], eax
0x180046e63  mov     rax, [rbx+70h]
0x180046e67  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180046e6e  mov     qword ptr [rsp+8F0h+InBuffer], rax
0x180046e73  lea     rax, [rsp+8F0h+BytesReturned+4]
0x180046e78  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x180046e7d  mov     [rsp+8F0h+nOutBufferSize], esi; nOutBufferSize
0x180046e81  mov     [rsp+8F0h+lpOutBuffer], rsi; lpOutBuffer
0x180046e86  call    cs:__imp_DeviceIoControl
0x180046e8d  nop     dword ptr [rax+rax+00h]
0x180046e92  test    eax, eax
0x180046e94  jnz     short loc_180046F0C
0x180046e96  call    cs:__imp_GetLastError
0x180046e9d  nop     dword ptr [rax+rax+00h]
0x180046ea2  test    cs:byte_1800CF404, 8
0x180046ea9  mov     edi, eax
0x180046eab  jz      short loc_180046F11
0x180046ead  mov     edx, [rbx+60h]
0x180046eb0  lea     rcx, [rsp+8F0h+var_894+4]
0x180046eb5  mov     word ptr [rbp+7F0h+var_810], si
0x180046eb9  mov     word ptr [rsp+8F0h+var_894+4], si
0x180046ebe  call    ConvertPortNoToString
0x180046ec3  mov     r8d, edi
0x180046ec6  lea     rdx, aIoctlNdiswanUn; "IOCTL_NDISWAN_UNMAP_CONNECTION_ID faile"...
0x180046ecd  lea     rcx, [rbp+7F0h+var_810]
0x180046ed1  call    FormatRRASErrorString
0x180046ed6  test    cs:byte_1800CF404, 8
0x180046edd  jz      short loc_180046F11
0x180046edf  lea     rax, [rsp+8F0h+var_894+4]
0x180046ee4  mov     qword ptr [rsp+8F0h+nOutBufferSize], rax
0x180046ee9  lea     r9, [rsp+8F0h+InBuffer+8]
0x180046eee  lea     r8, [rbp+7F0h+var_810]
0x180046ef2  mov     [rsp+8F0h+lpOutBuffer], rsi
0x180046ef7  lea     rdx, RasDdmParamTraceError
0x180046efe  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180046f05  call    McTemplateU0zjzz_EventWriteTransfer
0x180046f0a  jmp     short loc_180046F11
0x180046f0c  or      qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x180046f11  mov     rcx, [rbp+7F0h+var_10]
0x180046f18  xor     rcx, rsp; StackCookie
0x180046f1b  call    __security_check_cookie
0x180046f20  lea     r11, [rsp+8F0h+var_s0]
0x180046f28  mov     rbx, [r11+18h]
0x180046f2c  mov     rsi, [r11+20h]
0x180046f30  mov     rdi, [r11+28h]
0x180046f34  mov     rsp, r11
0x180046f37  pop     rbp
0x180046f38  retn
```
