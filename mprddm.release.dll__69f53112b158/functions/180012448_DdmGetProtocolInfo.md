# DdmGetProtocolInfo

- ea: `0x180012448`
- end: `0x18001267e`
- name: `DdmGetProtocolInfo`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017fc8`

## callees

- `0x180007c0c`
- `0x180012448`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180012545`
- `KERNEL32!DeviceIoControl` at `0x180012545`
- `KERNEL32!GetLastError` at `0x180012559`
- `KERNEL32!GetLastError` at `0x180012559`

## string_xrefs

- `0x1800124be`: `DdmGetProtocolInfo`
- `0x18001257f`: `IOCTL_NDISWAN_GET_PROTOCOL_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmGetProtocolInfo(__int64 a1, _OWORD *a2)
{
  DWORD v3; // esi
  __int64 v4; // r8
  __int64 v5; // rdi
  __int64 v6; // rax
  DWORD LastError; // eax
  __int64 v8; // r8
  __int64 v9; // rcx
  _OWORD *v10; // rax
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE OutBuffer[528]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+260h] [rbp+160h] BYREF
  const wchar_t *v22; // [rsp+270h] [rbp+170h]
  int v23; // [rsp+278h] [rbp+178h]
  int v24; // [rsp+27Ch] [rbp+17Ch]
  int v25; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v26[2044]; // [rsp+284h] [rbp+184h] BYREF

  BytesReturned[0] = 0;
  v3 = 0;
  memset_0(OutBuffer, 0, 0x204u);
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v5 = -1;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( aDdmgetprotocol[v6] );
    v22 = L"DdmGetProtocolInfo";
    v23 = 2 * v6 + 2;
    v24 = 0;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasDdmTraceInfo,
      v4,
      2u,
      &v21);
  }
  if ( DeviceIoControl(gblDdmDriverInfo, 0x1200A8u, 0, 0, OutBuffer, 0x204u, BytesReturned, 0) )
  {
    v9 = 4;
    v10 = OutBuffer;
    do
    {
      v11 = v10[1];
      *a2 = *v10;
      v12 = v10[2];
      a2[1] = v11;
      v13 = v10[3];
      a2[2] = v12;
      v14 = v10[4];
      a2[3] = v13;
      v15 = v10[5];
      a2[4] = v14;
      v16 = v10[6];
      a2[5] = v15;
      v17 = v10[7];
      v10 += 8;
      a2[6] = v16;
      a2 += 8;
      *(a2 - 1) = v17;
      --v9;
    }
    while ( v9 );
    *(_DWORD *)a2 = *(_DWORD *)v10;
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(&v25, L"IOCTL_NDISWAN_GET_PROTOCOL_INFO failed with error 0x%x", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        do
          ++v5;
        while ( *(_WORD *)&v26[2 * v5 - 4] );
        v24 = 0;
        v23 = 2 * v5 + 2;
        v22 = (const wchar_t *)&v25;
        McGenEventWrite_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasDdmTraceError,
          v8,
          2u,
          &v21);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180012448  mov     [rsp-8+arg_0], rbx
0x18001244d  mov     [rsp-8+arg_10], rsi
0x180012452  push    rbp
0x180012453  push    rdi
0x180012454  push    r14
0x180012456  lea     rbp, [rsp-990h]
0x18001245e  sub     rsp, 0A90h
0x180012465  mov     rax, cs:__security_cookie
0x18001246c  xor     rax, rsp
0x18001246f  mov     [rbp+9A0h+var_20], rax
0x180012476  mov     rbx, rdx
0x180012479  lea     rcx, [rsp+0AA0h+OutBuffer]; void *
0x18001247e  xor     r14d, r14d
0x180012481  xor     edx, edx; Val
0x180012483  mov     r8d, 204h; Size
0x180012489  mov     [rsp+0AA0h+BytesReturned], r14d
0x18001248e  mov     esi, r14d
0x180012491  call    memset_0
0x180012496  xor     edx, edx; Val
0x180012498  mov     [rbp+9A0h+var_820], r14d
0x18001249f  mov     r8d, 7FCh; Size
0x1800124a5  lea     rcx, [rbp+9A0h+var_81C]; void *
0x1800124ac  call    memset_0
0x1800124b1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800124b5  test    cs:byte_1800CF404, 10h
0x1800124bc  jz      short loc_180012512
0x1800124be  lea     rcx, aDdmgetprotocol; "DdmGetProtocolInfo"
0x1800124c5  mov     rax, rdi
0x1800124c8  inc     rax
0x1800124cb  cmp     [rcx+rax*2], r14w
0x1800124d0  jnz     short loc_1800124C8
0x1800124d2  lea     eax, ds:2[rax*2]
0x1800124d9  mov     [rbp+9A0h+var_830], rcx
0x1800124e0  mov     [rbp+9A0h+var_828], eax
0x1800124e6  lea     rdx, RasDdmTraceInfo
0x1800124ed  lea     rax, [rbp+9A0h+var_840]
0x1800124f4  mov     [rbp+9A0h+var_824], r14d
0x1800124fb  mov     r9d, 2
0x180012501  mov     [rsp+0AA0h+lpOutBuffer], rax
0x180012506  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001250d  call    McGenEventWrite_EventWriteTransfer
0x180012512  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180012519  lea     rax, [rsp+0AA0h+BytesReturned]
0x18001251e  mov     [rsp+0AA0h+lpOverlapped], r14; lpOverlapped
0x180012523  xor     r9d, r9d; nInBufferSize
0x180012526  mov     [rsp+0AA0h+lpBytesReturned], rax; lpBytesReturned
0x18001252b  xor     r8d, r8d; lpInBuffer
0x18001252e  lea     rax, [rsp+0AA0h+OutBuffer]
0x180012533  mov     [rsp+0AA0h+nOutBufferSize], 204h; nOutBufferSize
0x18001253b  mov     edx, 1200A8h; dwIoControlCode
0x180012540  mov     [rsp+0AA0h+lpOutBuffer], rax; lpOutBuffer
0x180012545  call    cs:__imp_DeviceIoControl
0x18001254c  nop     dword ptr [rax+rax+00h]
0x180012551  test    eax, eax
0x180012553  jnz     loc_1800125F9
0x180012559  call    cs:__imp_GetLastError
0x180012560  nop     dword ptr [rax+rax+00h]
0x180012565  test    cs:byte_1800CF404, 8
0x18001256c  mov     esi, eax
0x18001256e  jz      loc_180012654
0x180012574  mov     r8d, eax
0x180012577  mov     word ptr [rbp+9A0h+var_820], r14w
0x18001257f  lea     rdx, aIoctlNdiswanGe; "IOCTL_NDISWAN_GET_PROTOCOL_INFO failed "...
0x180012586  lea     rcx, [rbp+9A0h+var_820]
0x18001258d  call    FormatRRASErrorString
0x180012592  test    cs:byte_1800CF404, 8
0x180012599  jz      loc_180012654
0x18001259f  lea     rax, [rbp+9A0h+var_820]
0x1800125a6  inc     rdi
0x1800125a9  cmp     [rax+rdi*2], r14w
0x1800125ae  jnz     short loc_1800125A6
0x1800125b0  lea     eax, ds:2[rdi*2]
0x1800125b7  mov     [rbp+9A0h+var_824], r14d
0x1800125be  lea     rdx, [rbp+9A0h+var_820]
0x1800125c5  mov     [rbp+9A0h+var_828], eax
0x1800125cb  lea     rax, [rbp+9A0h+var_840]
0x1800125d2  mov     [rbp+9A0h+var_830], rdx
0x1800125d9  mov     r9d, 2
0x1800125df  mov     [rsp+0AA0h+lpOutBuffer], rax
0x1800125e4  lea     rdx, RasDdmTraceError
0x1800125eb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800125f2  call    McGenEventWrite_EventWriteTransfer
0x1800125f7  jmp     short loc_180012654
0x1800125f9  mov     ecx, 4
0x1800125fe  lea     rax, [rsp+0AA0h+OutBuffer]
0x180012603  lea     edx, [rcx+7Ch]
0x180012606  movups  xmm0, xmmword ptr [rax]
0x180012609  movups  xmm1, xmmword ptr [rax+10h]
0x18001260d  movups  xmmword ptr [rbx], xmm0
0x180012610  movups  xmm0, xmmword ptr [rax+20h]
0x180012614  movups  xmmword ptr [rbx+10h], xmm1
0x180012618  movups  xmm1, xmmword ptr [rax+30h]
0x18001261c  movups  xmmword ptr [rbx+20h], xmm0
0x180012620  movups  xmm0, xmmword ptr [rax+40h]
0x180012624  movups  xmmword ptr [rbx+30h], xmm1
0x180012628  movups  xmm1, xmmword ptr [rax+50h]
0x18001262c  movups  xmmword ptr [rbx+40h], xmm0
0x180012630  movups  xmm0, xmmword ptr [rax+60h]
0x180012634  movups  xmmword ptr [rbx+50h], xmm1
0x180012638  movups  xmm1, xmmword ptr [rax+70h]
0x18001263c  add     rax, rdx
0x18001263f  movups  xmmword ptr [rbx+60h], xmm0
0x180012643  add     rbx, rdx
0x180012646  movups  xmmword ptr [rbx-10h], xmm1
0x18001264a  sub     rcx, 1
0x18001264e  jnz     short loc_180012606
0x180012650  mov     eax, [rax]
0x180012652  mov     [rbx], eax
0x180012654  mov     eax, esi
0x180012656  mov     rcx, [rbp+9A0h+var_20]
0x18001265d  xor     rcx, rsp; StackCookie
0x180012660  call    __security_check_cookie
0x180012665  lea     r11, [rsp+0AA0h+var_10]
0x18001266d  mov     rbx, [r11+20h]
0x180012671  mov     rsi, [r11+30h]
0x180012675  mov     rsp, r11
0x180012678  pop     r14
0x18001267a  pop     rdi
0x18001267b  pop     rbp
0x18001267c  retn
```
