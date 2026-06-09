# DdmModernDevice::CompressionSetInfo(_RAS_COMPRESSION_INFO *,_RAS_COMPRESSION_INFO *)

- ea: `0x18003e940`
- end: `0x18003ecd3`
- name: `?CompressionSetInfo@DdmModernDevice@@UEAAKPEAU_RAS_COMPRESSION_INFO@@0@Z`
- size: `915`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, struct _RAS_COMPRESSION_INFO *, struct _RAS_COMPRESSION_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002ba6`
- `0x180007c50`
- `0x18003e940`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003ea00`
- `msvcrt!_itow_s` at `0x18003ec4f`
- `msvcrt!_itow_s` at `0x18003ea00`
- `msvcrt!_itow_s` at `0x18003ec4f`
- `KERNEL32!DeviceIoControl` at `0x18003ec01`
- `KERNEL32!DeviceIoControl` at `0x18003ec01`
- `KERNEL32!GetLastError` at `0x18003ec0f`
- `KERNEL32!GetLastError` at `0x18003ec0f`

## string_xrefs

- `0x18003ea24`: `CompressionSetInfo`
- `0x18003ec58`: `IOCTL_NDISWAN_SET_COMPRESSION_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::CompressionSetInfo(
        DdmModernDevice *this,
        struct _RAS_COMPRESSION_INFO *a2,
        struct _RAS_COMPRESSION_INFO *a3)
{
  char v6; // dl
  int v7; // ecx
  DWORD LastError; // r14d
  __int128 v9; // xmm0
  char v10; // cl
  __int64 v11; // xmm1_8
  unsigned int v12; // ecx
  unsigned int v13; // esi
  size_t v14; // r8
  __int128 v15; // xmm0
  char v16; // cl
  __int64 v17; // xmm1_8
  unsigned int v18; // eax
  int v19; // ecx
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD OutBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  __int128 v25; // [rsp+78h] [rbp-88h]
  __int64 v26; // [rsp+88h] [rbp-78h]
  int v27; // [rsp+90h] [rbp-70h]
  int v28; // [rsp+94h] [rbp-6Ch]
  char v29; // [rsp+98h] [rbp-68h]
  __int16 v30; // [rsp+9Ah] [rbp-66h]
  __int16 v31; // [rsp+9Ch] [rbp-64h]
  char v32; // [rsp+9Eh] [rbp-62h]
  char v33; // [rsp+9Fh] [rbp-61h]
  __m256i v34; // [rsp+A0h] [rbp-60h]
  int v35; // [rsp+C0h] [rbp-40h]
  unsigned int v36; // [rsp+C4h] [rbp-3Ch]
  _BYTE v37[256]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+1C8h] [rbp+C8h]
  __int128 v39; // [rsp+1D0h] [rbp+D0h]
  __int64 v40; // [rsp+1E0h] [rbp+E0h]
  __int128 v41; // [rsp+1E8h] [rbp+E8h]
  __int64 v42; // [rsp+1F8h] [rbp+F8h]
  int v43; // [rsp+200h] [rbp+100h]
  int v44; // [rsp+204h] [rbp+104h]
  char v45; // [rsp+208h] [rbp+108h]
  __int16 v46; // [rsp+20Ah] [rbp+10Ah]
  __int16 v47; // [rsp+20Ch] [rbp+10Ch]
  char v48; // [rsp+20Eh] [rbp+10Eh]
  char v49; // [rsp+20Fh] [rbp+10Fh]
  __m256i v50; // [rsp+210h] [rbp+110h]
  int v51; // [rsp+230h] [rbp+130h]
  unsigned int v52; // [rsp+234h] [rbp+134h]
  _BYTE v53[264]; // [rsp+238h] [rbp+138h] BYREF
  __int128 v54; // [rsp+340h] [rbp+240h] BYREF
  wchar_t Buffer[2]; // [rsp+350h] [rbp+250h] BYREF
  __int128 v56; // [rsp+354h] [rbp+254h]
  __int128 v57; // [rsp+364h] [rbp+264h]
  int v58; // [rsp+374h] [rbp+274h]
  int v59; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v60[2044]; // [rsp+384h] [rbp+284h] BYREF

  BytesReturned[0] = 0;
  memset_0(OutBuffer, 0, 0x2E8u);
  v59 = 0;
  memset_0(v60, 0, sizeof(v60));
  v6 = byte_1800C8404;
  *(_DWORD *)Buffer = 0;
  v58 = 0;
  v56 = 0;
  v57 = 0;
  v54 = 0;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    Buffer[0] = 0;
    if ( this )
    {
      v7 = *((_DWORD *)this + 24);
      if ( v7 != -1 )
      {
        _itow_s(v7, Buffer, 0x14u, 10);
        v6 = byte_1800C8404;
      }
    }
    if ( (v6 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"CompressionSetInfo",
        (unsigned int)&v54,
        0,
        (__int64)Buffer);
  }
  LastError = 0;
  v9 = *(_OWORD *)((char *)a2 + 8);
  v10 = *((_BYTE *)a2 + 64);
  v11 = *((_QWORD *)a2 + 6);
  OutBuffer[0] = *((_QWORD *)this + 14);
  OutBuffer[1] = *(_QWORD *)a2;
  v24 = *((_QWORD *)a2 + 3);
  v28 = *((_DWORD *)a2 + 15);
  v35 = *((_DWORD *)a2 + 26);
  v27 = *((_DWORD *)a2 + 14);
  v30 = *((_WORD *)a2 + 33);
  v31 = *((_WORD *)a2 + 34);
  v32 = *((_BYTE *)a2 + 70);
  v33 = *((_BYTE *)a2 + 71);
  v26 = v11;
  v29 = v10;
  v23 = v9;
  v25 = *((_OWORD *)a2 + 2);
  *(_OWORD *)v34.m256i_i8 = *(_OWORD *)((char *)a2 + 72);
  if ( v10 )
    *(_OWORD *)((char *)&v34.m256i_u64[1] + 4) = *(_OWORD *)((char *)a2 + 84);
  else
    *(_OWORD *)&v34.m256i_u64[2] = *(_OWORD *)((char *)a2 + 88);
  v12 = *((_DWORD *)a2 + 27);
  v13 = 256;
  v36 = v12;
  if ( v12 )
  {
    v14 = 256;
    if ( v12 < 0x100 )
      v14 = v12;
    memcpy_0(v37, (char *)a2 + 112, v14);
  }
  v15 = *(_OWORD *)((char *)a3 + 8);
  v16 = *((_BYTE *)a3 + 64);
  v17 = *((_QWORD *)a3 + 6);
  v38 = *(_QWORD *)a3;
  v40 = *((_QWORD *)a3 + 3);
  v44 = *((_DWORD *)a3 + 15);
  v51 = *((_DWORD *)a3 + 26);
  v43 = *((_DWORD *)a3 + 14);
  v46 = *((_WORD *)a3 + 33);
  v47 = *((_WORD *)a3 + 34);
  v48 = *((_BYTE *)a3 + 70);
  v49 = *((_BYTE *)a3 + 71);
  v42 = v17;
  v45 = v16;
  v39 = v15;
  v41 = *((_OWORD *)a3 + 2);
  *(_OWORD *)v50.m256i_i8 = *(_OWORD *)((char *)a3 + 72);
  if ( v16 )
    *(_OWORD *)((char *)&v50.m256i_u64[1] + 4) = *(_OWORD *)((char *)a3 + 84);
  else
    *(_OWORD *)&v50.m256i_u64[2] = *(_OWORD *)((char *)a3 + 88);
  v18 = *((_DWORD *)a3 + 27);
  v52 = v18;
  if ( v18 )
  {
    if ( v18 < 0x100 )
      v13 = v18;
    memcpy_0(v53, (char *)a3 + 112, v13);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x120040u, OutBuffer, 0x2E8u, OutBuffer, 0x2E8u, BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v59) = 0;
      Buffer[0] = 0;
      v19 = *((_DWORD *)this + 24);
      if ( v19 != -1 )
        _itow_s(v19, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v59, L"IOCTL_NDISWAN_SET_COMPRESSION_INFO failed with error 0x%x", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v59,
          (unsigned int)&v54,
          0,
          (__int64)Buffer);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18003e940  mov     [rsp-8+arg_18], rbx
0x18003e945  push    rbp
0x18003e946  push    rsi
0x18003e947  push    rdi
0x18003e948  push    r14
0x18003e94a  push    r15
0x18003e94c  lea     rbp, [rsp-0A90h]
0x18003e954  sub     rsp, 0B90h
0x18003e95b  mov     rax, cs:__security_cookie
0x18003e962  xor     rax, rsp
0x18003e965  mov     [rbp+0AB0h+var_30], rax
0x18003e96c  mov     rbx, r8
0x18003e96f  mov     [rsp+0BB0h+BytesReturned], 0
0x18003e977  mov     rdi, rdx
0x18003e97a  mov     r15, rcx
0x18003e97d  xor     edx, edx; Val
0x18003e97f  lea     rcx, [rsp+0BB0h+OutBuffer]; void *
0x18003e984  mov     r8d, 2E8h; Size
0x18003e98a  call    memset_0
0x18003e98f  xor     eax, eax
0x18003e991  lea     rcx, [rbp+0AB0h+var_82C]; void *
0x18003e998  xor     edx, edx; Val
0x18003e99a  mov     [rbp+0AB0h+var_830], eax
0x18003e9a0  mov     r8d, 7FCh; Size
0x18003e9a6  call    memset_0
0x18003e9ab  mov     dl, cs:byte_1800C8404
0x18003e9b1  xor     eax, eax
0x18003e9b3  mov     dword ptr [rbp+0AB0h+Buffer], eax
0x18003e9b9  xorps   xmm0, xmm0
0x18003e9bc  mov     [rbp+0AB0h+var_83C], eax
0x18003e9c2  movups  [rbp+0AB0h+var_85C], xmm0
0x18003e9c9  movups  [rbp+0AB0h+var_84C], xmm0
0x18003e9d0  movups  [rbp+0AB0h+var_870], xmm0
0x18003e9d7  test    dl, 8
0x18003e9da  jz      short loc_18003EA47
0x18003e9dc  mov     [rbp+0AB0h+Buffer], ax
0x18003e9e3  test    r15, r15
0x18003e9e6  jz      short loc_18003EA0C
0x18003e9e8  mov     ecx, [r15+60h]; Value
0x18003e9ec  cmp     ecx, 0FFFFFFFFh
0x18003e9ef  jz      short loc_18003EA0C
0x18003e9f1  lea     r9d, [rax+0Ah]; Radix
0x18003e9f5  lea     r8d, [rax+14h]; BufferCount
0x18003e9f9  lea     rdx, [rbp+0AB0h+Buffer]; Buffer
0x18003ea00  call    cs:__imp__itow_s
0x18003ea06  mov     dl, cs:byte_1800C8404
0x18003ea0c  test    dl, 8
0x18003ea0f  jz      short loc_18003EA47
0x18003ea11  lea     rax, [rbp+0AB0h+Buffer]
0x18003ea18  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x18003ea1d  lea     r9, [rbp+0AB0h+var_870]
0x18003ea24  lea     r8, aCompressionset; "CompressionSetInfo"
0x18003ea2b  mov     [rsp+0BB0h+lpOutBuffer], 0
0x18003ea34  lea     rdx, RasDdmParamTraceError
0x18003ea3b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ea42  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ea47  mov     rax, [r15+70h]
0x18003ea4b  xor     r14d, r14d
0x18003ea4e  movups  xmm0, xmmword ptr [rdi+8]
0x18003ea52  mov     cl, [rdi+40h]
0x18003ea55  movsd   xmm1, qword ptr [rdi+30h]
0x18003ea5a  mov     [rsp+0BB0h+OutBuffer], rax
0x18003ea5f  mov     rax, [rdi]
0x18003ea62  mov     [rsp+0BB0h+var_B58], rax
0x18003ea67  mov     rax, [rdi+18h]
0x18003ea6b  mov     [rsp+0BB0h+var_B40], rax
0x18003ea70  mov     eax, [rdi+3Ch]
0x18003ea73  mov     [rbp+0AB0h+var_B1C], eax
0x18003ea76  mov     eax, [rdi+68h]
0x18003ea79  mov     [rbp+0AB0h+var_AF0], eax
0x18003ea7c  mov     eax, [rdi+38h]
0x18003ea7f  mov     [rbp+0AB0h+var_B20], eax
0x18003ea82  movzx   eax, word ptr [rdi+42h]
0x18003ea86  mov     [rbp+0AB0h+var_B16], ax
0x18003ea8a  movzx   eax, word ptr [rdi+44h]
0x18003ea8e  mov     [rbp+0AB0h+var_B14], ax
0x18003ea92  mov     al, [rdi+46h]
0x18003ea95  mov     [rbp+0AB0h+var_B12], al
0x18003ea98  mov     al, [rdi+47h]
0x18003ea9b  mov     [rbp+0AB0h+var_B11], al
0x18003ea9e  movsd   [rbp+0AB0h+var_B28], xmm1
0x18003eaa3  mov     [rbp+0AB0h+var_B18], cl
0x18003eaa6  movdqu  [rsp+0BB0h+var_B50], xmm0
0x18003eaac  movups  xmm0, xmmword ptr [rdi+20h]
0x18003eab0  movups  [rsp+0BB0h+var_B38], xmm0
0x18003eab5  movups  xmm0, xmmword ptr [rdi+48h]
0x18003eab9  movaps  [rbp+0AB0h+var_B10], xmm0
0x18003eabd  test    cl, cl
0x18003eabf  jnz     short loc_18003EACB
0x18003eac1  movups  xmm1, xmmword ptr [rdi+58h]
0x18003eac5  movaps  [rbp+0AB0h+var_B00], xmm1
0x18003eac9  jmp     short loc_18003EAD3
0x18003eacb  movups  xmm1, xmmword ptr [rdi+54h]
0x18003eacf  movups  [rbp+0AB0h+var_B10+0Ch], xmm1
0x18003ead3  mov     ecx, [rdi+6Ch]
0x18003ead6  mov     esi, 100h
0x18003eadb  mov     [rbp+0AB0h+var_AEC], ecx
0x18003eade  test    ecx, ecx
0x18003eae0  jz      short loc_18003EAF8
0x18003eae2  cmp     ecx, esi
0x18003eae4  lea     rdx, [rdi+70h]; Src
0x18003eae8  mov     r8d, esi
0x18003eaeb  cmovb   r8d, ecx; Size
0x18003eaef  lea     rcx, [rbp+0AB0h+var_AE8]; void *
0x18003eaf3  call    memcpy_0
0x18003eaf8  mov     rax, [rbx]
0x18003eafb  movups  xmm0, xmmword ptr [rbx+8]
0x18003eaff  mov     cl, [rbx+40h]
0x18003eb02  movsd   xmm1, qword ptr [rbx+30h]
0x18003eb07  mov     [rbp+0AB0h+var_9E8], rax
0x18003eb0e  mov     rax, [rbx+18h]
0x18003eb12  mov     [rbp+0AB0h+var_9D0], rax
0x18003eb19  mov     eax, [rbx+3Ch]
0x18003eb1c  mov     [rbp+0AB0h+var_9AC], eax
0x18003eb22  mov     eax, [rbx+68h]
0x18003eb25  mov     [rbp+0AB0h+var_980], eax
0x18003eb2b  mov     eax, [rbx+38h]
0x18003eb2e  mov     [rbp+0AB0h+var_9B0], eax
0x18003eb34  movzx   eax, word ptr [rbx+42h]
0x18003eb38  mov     [rbp+0AB0h+var_9A6], ax
0x18003eb3f  movzx   eax, word ptr [rbx+44h]
0x18003eb43  mov     [rbp+0AB0h+var_9A4], ax
0x18003eb4a  mov     al, [rbx+46h]
0x18003eb4d  mov     [rbp+0AB0h+var_9A2], al
0x18003eb53  mov     al, [rbx+47h]
0x18003eb56  mov     [rbp+0AB0h+var_9A1], al
0x18003eb5c  movsd   [rbp+0AB0h+var_9B8], xmm1
0x18003eb64  mov     [rbp+0AB0h+var_9A8], cl
0x18003eb6a  movdqu  [rbp+0AB0h+var_9E0], xmm0
0x18003eb72  movups  xmm0, xmmword ptr [rbx+20h]
0x18003eb76  movups  [rbp+0AB0h+var_9C8], xmm0
0x18003eb7d  movups  xmm0, xmmword ptr [rbx+48h]
0x18003eb81  movaps  [rbp+0AB0h+var_9A0], xmm0
0x18003eb88  test    cl, cl
0x18003eb8a  jnz     short loc_18003EB99
0x18003eb8c  movups  xmm1, xmmword ptr [rbx+58h]
0x18003eb90  movaps  [rbp+0AB0h+var_990], xmm1
0x18003eb97  jmp     short loc_18003EBA4
0x18003eb99  movups  xmm1, xmmword ptr [rbx+54h]
0x18003eb9d  movups  [rbp+0AB0h+var_9A0+0Ch], xmm1
0x18003eba4  mov     eax, [rbx+6Ch]
0x18003eba7  mov     [rbp+0AB0h+var_97C], eax
0x18003ebad  test    eax, eax
0x18003ebaf  jz      short loc_18003EBC9
0x18003ebb1  cmp     eax, esi
0x18003ebb3  lea     rdx, [rbx+70h]; Src
0x18003ebb7  lea     rcx, [rbp+0AB0h+var_978]; void *
0x18003ebbe  cmovb   esi, eax
0x18003ebc1  mov     r8d, esi; Size
0x18003ebc4  call    memcpy_0
0x18003ebc9  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x18003ebd0  lea     rax, [rsp+0BB0h+BytesReturned]
0x18003ebd5  mov     [rsp+0BB0h+lpOverlapped], r14; lpOverlapped
0x18003ebda  lea     r8, [rsp+0BB0h+OutBuffer]; lpInBuffer
0x18003ebdf  mov     [rsp+0BB0h+lpBytesReturned], rax; lpBytesReturned
0x18003ebe4  mov     r9d, 2E8h; nInBufferSize
0x18003ebea  lea     rax, [rsp+0BB0h+OutBuffer]
0x18003ebef  mov     [rsp+0BB0h+nOutBufferSize], 2E8h; nOutBufferSize
0x18003ebf7  mov     edx, 120040h; dwIoControlCode
0x18003ebfc  mov     [rsp+0BB0h+lpOutBuffer], rax; lpOutBuffer
0x18003ec01  call    cs:__imp_DeviceIoControl
0x18003ec07  test    eax, eax
0x18003ec09  jnz     loc_18003ECAA
0x18003ec0f  call    cs:__imp_GetLastError
0x18003ec15  test    cs:byte_1800C8404, 8
0x18003ec1c  mov     r14d, eax
0x18003ec1f  jz      loc_18003ECAA
0x18003ec25  xor     ecx, ecx
0x18003ec27  mov     word ptr [rbp+0AB0h+var_830], cx
0x18003ec2e  mov     [rbp+0AB0h+Buffer], cx
0x18003ec35  mov     ecx, [r15+60h]; Value
0x18003ec39  cmp     ecx, 0FFFFFFFFh
0x18003ec3c  jz      short loc_18003EC55
0x18003ec3e  mov     r9d, 0Ah; Radix
0x18003ec44  lea     rdx, [rbp+0AB0h+Buffer]; Buffer
0x18003ec4b  lea     r8d, [r9+0Ah]; BufferCount
0x18003ec4f  call    cs:__imp__itow_s
0x18003ec55  mov     r8d, r14d
0x18003ec58  lea     rdx, aIoctlNdiswanSe_0; "IOCTL_NDISWAN_SET_COMPRESSION_INFO fail"...
0x18003ec5f  lea     rcx, [rbp+0AB0h+var_830]
0x18003ec66  call    FormatRRASErrorString
0x18003ec6b  test    cs:byte_1800C8404, 8
0x18003ec72  jz      short loc_18003ECAA
0x18003ec74  lea     rax, [rbp+0AB0h+Buffer]
0x18003ec7b  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x18003ec80  lea     r9, [rbp+0AB0h+var_870]
0x18003ec87  lea     r8, [rbp+0AB0h+var_830]
0x18003ec8e  mov     [rsp+0BB0h+lpOutBuffer], 0
0x18003ec97  lea     rdx, RasDdmParamTraceError
0x18003ec9e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003eca5  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ecaa  mov     eax, r14d
0x18003ecad  mov     rcx, [rbp+0AB0h+var_30]
0x18003ecb4  xor     rcx, rsp; StackCookie
0x18003ecb7  call    __security_check_cookie
0x18003ecbc  mov     rbx, [rsp+0BB0h+arg_18]
0x18003ecc4  add     rsp, 0B90h
0x18003eccb  pop     r15
0x18003eccd  pop     r14
0x18003eccf  pop     rdi
0x18003ecd0  pop     rsi
0x18003ecd1  pop     rbp
0x18003ecd2  retn
```
