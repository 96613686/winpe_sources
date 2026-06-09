# DdmGetProtocolInfo

- ea: `0x180012070`
- end: `0x180012263`
- name: `DdmGetProtocolInfo`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017794`

## callees

- `0x180007b7c`
- `0x180012070`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180012140`
- `KERNEL32!DeviceIoControl` at `0x180012140`
- `KERNEL32!GetLastError` at `0x18001214e`
- `KERNEL32!GetLastError` at `0x18001214e`

## string_xrefs

- `0x1800120d5`: `DdmGetProtocolInfo`
- `0x18001216d`: `IOCTL_NDISWAN_GET_PROTOCOL_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmGetProtocolInfo(__int64 a1, _OWORD *a2)
{
  __int64 v3; // r8
  DWORD LastError; // eax
  DWORD v5; // edi
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE OutBuffer[528]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+260h] [rbp+160h] BYREF
  const wchar_t *v21; // [rsp+270h] [rbp+170h]
  __int64 v22; // [rsp+278h] [rbp+178h]
  int v23; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v24[2044]; // [rsp+284h] [rbp+184h] BYREF

  BytesReturned[0] = 0;
  memset_0(OutBuffer, 0, 0x204u);
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v22 = 38;
    v21 = L"DdmGetProtocolInfo";
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v3,
      2u,
      &v20);
  }
  if ( DeviceIoControl(gblDdmDriverInfo, 0x1200A8u, 0, 0, OutBuffer, 0x204u, BytesReturned, 0) )
  {
    v8 = 4;
    v9 = OutBuffer;
    v5 = 0;
    do
    {
      v10 = v9[1];
      *a2 = *v9;
      v11 = v9[2];
      a2[1] = v10;
      v12 = v9[3];
      a2[2] = v11;
      v13 = v9[4];
      a2[3] = v12;
      v14 = v9[5];
      a2[4] = v13;
      v15 = v9[6];
      a2[5] = v14;
      v16 = v9[7];
      v9 += 8;
      a2[6] = v15;
      a2[7] = v16;
      a2 += 8;
      --v8;
    }
    while ( v8 );
    *(_DWORD *)a2 = *(_DWORD *)v9;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"IOCTL_NDISWAN_GET_PROTOCOL_INFO failed with error 0x%x", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_WORD *)&v24[2 * v7 - 4] );
        v22 = (unsigned int)(2 * v7 + 2);
        v21 = (const wchar_t *)&v23;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v6,
          2u,
          &v20);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180012070  push    rbp
0x180012072  push    rbx
0x180012073  push    rsi
0x180012074  push    rdi
0x180012075  lea     rbp, [rsp-998h]
0x18001207d  sub     rsp, 0A98h
0x180012084  mov     rax, cs:__security_cookie
0x18001208b  xor     rax, rsp
0x18001208e  mov     [rbp+9B0h+var_30], rax
0x180012095  mov     rbx, rdx
0x180012098  lea     rcx, [rsp+0AB0h+OutBuffer]; void *
0x18001209d  mov     edi, 204h
0x1800120a2  xor     esi, esi
0x1800120a4  mov     r8d, edi; Size
0x1800120a7  mov     [rsp+0AB0h+BytesReturned], esi
0x1800120ab  xor     edx, edx; Val
0x1800120ad  call    memset_0
0x1800120b2  xor     edx, edx; Val
0x1800120b4  mov     [rbp+9B0h+var_830], esi
0x1800120ba  mov     r8d, 7FCh; Size
0x1800120c0  lea     rcx, [rbp+9B0h+var_82C]; void *
0x1800120c7  call    memset_0
0x1800120cc  test    cs:byte_1800C8404, 10h
0x1800120d3  jz      short loc_180012111
0x1800120d5  lea     rax, aDdmgetprotocol; "DdmGetProtocolInfo"
0x1800120dc  mov     [rbp+9B0h+var_838], 26h ; '&'
0x1800120e7  mov     [rbp+9B0h+var_840], rax
0x1800120ee  lea     r9d, [rsi+2]
0x1800120f2  lea     rax, [rbp+9B0h+var_850]
0x1800120f9  lea     rdx, RasDdmTraceInfo
0x180012100  mov     [rsp+0AB0h+lpOutBuffer], rax
0x180012105  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001210c  call    McGenEventWrite_EventWriteTransfer
0x180012111  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180012118  lea     rax, [rsp+0AB0h+BytesReturned]
0x18001211d  mov     [rsp+0AB0h+lpOverlapped], rsi; lpOverlapped
0x180012122  xor     r9d, r9d; nInBufferSize
0x180012125  mov     [rsp+0AB0h+lpBytesReturned], rax; lpBytesReturned
0x18001212a  xor     r8d, r8d; lpInBuffer
0x18001212d  lea     rax, [rsp+0AB0h+OutBuffer]
0x180012132  mov     [rsp+0AB0h+nOutBufferSize], edi; nOutBufferSize
0x180012136  mov     edx, 1200A8h; dwIoControlCode
0x18001213b  mov     [rsp+0AB0h+lpOutBuffer], rax; lpOutBuffer
0x180012140  call    cs:__imp_DeviceIoControl
0x180012146  test    eax, eax
0x180012148  jnz     loc_1800121E9
0x18001214e  call    cs:__imp_GetLastError
0x180012154  test    cs:byte_1800C8404, 8
0x18001215b  mov     edi, eax
0x18001215d  jz      loc_180012246
0x180012163  mov     r8d, eax
0x180012166  mov     word ptr [rbp+9B0h+var_830], si
0x18001216d  lea     rdx, aIoctlNdiswanGe; "IOCTL_NDISWAN_GET_PROTOCOL_INFO failed "...
0x180012174  lea     rcx, [rbp+9B0h+var_830]
0x18001217b  call    FormatRRASErrorString
0x180012180  test    cs:byte_1800C8404, 8
0x180012187  jz      loc_180012246
0x18001218d  lea     rdx, [rbp+9B0h+var_830]
0x180012194  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012198  inc     rax
0x18001219b  cmp     [rdx+rax*2], si
0x18001219f  jnz     short loc_180012198
0x1800121a1  lea     eax, ds:2[rax*2]
0x1800121a8  mov     dword ptr [rbp+9B0h+var_838+4], esi
0x1800121ae  lea     rdx, [rbp+9B0h+var_830]
0x1800121b5  mov     dword ptr [rbp+9B0h+var_838], eax
0x1800121bb  lea     rax, [rbp+9B0h+var_850]
0x1800121c2  mov     [rbp+9B0h+var_840], rdx
0x1800121c9  mov     r9d, 2
0x1800121cf  mov     [rsp+0AB0h+lpOutBuffer], rax
0x1800121d4  lea     rdx, RasDdmTraceError
0x1800121db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800121e2  call    McGenEventWrite_EventWriteTransfer
0x1800121e7  jmp     short loc_180012246
0x1800121e9  mov     ecx, 4
0x1800121ee  lea     rax, [rsp+0AB0h+OutBuffer]
0x1800121f3  mov     edi, esi
0x1800121f5  lea     edx, [rcx+7Ch]
0x1800121f8  movups  xmm0, xmmword ptr [rax]
0x1800121fb  movups  xmm1, xmmword ptr [rax+10h]
0x1800121ff  movups  xmmword ptr [rbx], xmm0
0x180012202  movups  xmm0, xmmword ptr [rax+20h]
0x180012206  movups  xmmword ptr [rbx+10h], xmm1
0x18001220a  movups  xmm1, xmmword ptr [rax+30h]
0x18001220e  movups  xmmword ptr [rbx+20h], xmm0
0x180012212  movups  xmm0, xmmword ptr [rax+40h]
0x180012216  movups  xmmword ptr [rbx+30h], xmm1
0x18001221a  movups  xmm1, xmmword ptr [rax+50h]
0x18001221e  movups  xmmword ptr [rbx+40h], xmm0
0x180012222  movups  xmm0, xmmword ptr [rax+60h]
0x180012226  movups  xmmword ptr [rbx+50h], xmm1
0x18001222a  movups  xmm1, xmmword ptr [rax+70h]
0x18001222e  add     rax, rdx
0x180012231  movups  xmmword ptr [rbx+60h], xmm0
0x180012235  movups  xmmword ptr [rbx+70h], xmm1
0x180012239  add     rbx, rdx
0x18001223c  sub     rcx, 1
0x180012240  jnz     short loc_1800121F8
0x180012242  mov     eax, [rax]
0x180012244  mov     [rbx], eax
0x180012246  mov     eax, edi
0x180012248  mov     rcx, [rbp+9B0h+var_30]
0x18001224f  xor     rcx, rsp; StackCookie
0x180012252  call    __security_check_cookie
0x180012257  add     rsp, 0A98h
0x18001225e  pop     rdi
0x18001225f  pop     rsi
0x180012260  pop     rbx
0x180012261  pop     rbp
0x180012262  retn
```
