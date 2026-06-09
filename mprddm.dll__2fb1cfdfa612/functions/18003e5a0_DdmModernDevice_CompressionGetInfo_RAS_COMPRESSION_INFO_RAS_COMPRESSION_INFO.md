# DdmModernDevice::CompressionGetInfo(_RAS_COMPRESSION_INFO *,_RAS_COMPRESSION_INFO *)

- ea: `0x18003e5a0`
- end: `0x18003e92d`
- name: `?CompressionGetInfo@DdmModernDevice@@UEAAKPEAU_RAS_COMPRESSION_INFO@@0@Z`
- size: `909`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, struct _RAS_COMPRESSION_INFO *, struct _RAS_COMPRESSION_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002ba6`
- `0x180007c50`
- `0x18003e5a0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003e65d`
- `msvcrt!_itow_s` at `0x18003e730`
- `msvcrt!_itow_s` at `0x18003e65d`
- `msvcrt!_itow_s` at `0x18003e730`
- `KERNEL32!DeviceIoControl` at `0x18003e6e3`
- `KERNEL32!DeviceIoControl` at `0x18003e6e3`
- `KERNEL32!GetLastError` at `0x18003e6f1`
- `KERNEL32!GetLastError` at `0x18003e6f1`

## string_xrefs

- `0x18003e681`: `CompressionGetInfo`
- `0x18003e739`: `IOCTL_NDISWAN_GET_COMPRESSION_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::CompressionGetInfo(
        DdmModernDevice *this,
        struct _RAS_COMPRESSION_INFO *a2,
        struct _RAS_COMPRESSION_INFO *a3)
{
  char v6; // dl
  int v7; // ecx
  DWORD LastError; // r14d
  int v9; // ecx
  __int128 v10; // xmm0
  char v11; // cl
  __int64 v12; // xmm1_8
  __int128 v13; // xmm0
  unsigned int v14; // ecx
  unsigned int v15; // esi
  size_t v16; // r8
  __int128 v17; // xmm0
  char v18; // cl
  __int64 v19; // xmm1_8
  __int128 v20; // xmm0
  unsigned int v21; // eax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD OutBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  __int128 v27; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h]
  int v30; // [rsp+94h] [rbp-6Ch]
  char v31; // [rsp+98h] [rbp-68h]
  __int16 v32; // [rsp+9Ah] [rbp-66h]
  __int16 v33; // [rsp+9Ch] [rbp-64h]
  char v34; // [rsp+9Eh] [rbp-62h]
  char v35; // [rsp+9Fh] [rbp-61h]
  __m256i v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+C0h] [rbp-40h]
  unsigned int Size; // [rsp+C4h] [rbp-3Ch]
  _QWORD Size_4[33]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v40; // [rsp+1D0h] [rbp+D0h]
  __int64 v41; // [rsp+1E0h] [rbp+E0h]
  __int128 v42; // [rsp+1E8h] [rbp+E8h]
  __int64 v43; // [rsp+1F8h] [rbp+F8h]
  int v44; // [rsp+200h] [rbp+100h]
  int v45; // [rsp+204h] [rbp+104h]
  char v46; // [rsp+208h] [rbp+108h]
  __int16 v47; // [rsp+20Ah] [rbp+10Ah]
  __int16 v48; // [rsp+20Ch] [rbp+10Ch]
  char v49; // [rsp+20Eh] [rbp+10Eh]
  char v50; // [rsp+20Fh] [rbp+10Fh]
  __m256i v51; // [rsp+210h] [rbp+110h]
  int v52; // [rsp+230h] [rbp+130h]
  unsigned int Src; // [rsp+234h] [rbp+134h]
  size_t Src_4; // [rsp+238h] [rbp+138h] BYREF
  __int128 v55; // [rsp+340h] [rbp+240h] BYREF
  wchar_t Buffer[2]; // [rsp+350h] [rbp+250h] BYREF
  __int128 v57; // [rsp+354h] [rbp+254h]
  __int128 v58; // [rsp+364h] [rbp+264h]
  int v59; // [rsp+374h] [rbp+274h]
  int v60; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v61[2044]; // [rsp+384h] [rbp+284h] BYREF

  BytesReturned[0] = 0;
  memset_0(OutBuffer, 0, 0x2E8u);
  v60 = 0;
  memset_0(v61, 0, sizeof(v61));
  v6 = byte_1800C8404;
  *(_DWORD *)Buffer = 0;
  v59 = 0;
  v57 = 0;
  v58 = 0;
  v55 = 0;
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
        (unsigned int)L"CompressionGetInfo",
        (unsigned int)&v55,
        0,
        (__int64)Buffer);
  }
  OutBuffer[0] = *((_QWORD *)this + 14);
  if ( DeviceIoControl(gblDdmDriverInfo, 0x120044u, OutBuffer, 0x2E8u, OutBuffer, 0x2E8u, BytesReturned, 0) )
  {
    LastError = 0;
    v10 = v25;
    v11 = v31;
    v12 = v28;
    *(_QWORD *)a2 = OutBuffer[1];
    *((_QWORD *)a2 + 3) = v26;
    *((_DWORD *)a2 + 15) = v30;
    *((_DWORD *)a2 + 26) = v37;
    *((_DWORD *)a2 + 14) = v29;
    *((_WORD *)a2 + 33) = v32;
    *((_WORD *)a2 + 34) = v33;
    *((_BYTE *)a2 + 70) = v34;
    *((_BYTE *)a2 + 71) = v35;
    *((_BYTE *)a2 + 64) = v11;
    *(_OWORD *)((char *)a2 + 8) = v10;
    *((_OWORD *)a2 + 2) = v27;
    v13 = *(_OWORD *)v36.m256i_i8;
    *((_QWORD *)a2 + 6) = v12;
    *(_OWORD *)((char *)a2 + 72) = v13;
    if ( v11 )
      *(_OWORD *)((char *)a2 + 84) = *(_OWORD *)((char *)&v36.m256i_u64[1] + 4);
    else
      *(_OWORD *)((char *)a2 + 88) = *(_OWORD *)&v36.m256i_u64[2];
    v14 = Size;
    v15 = 256;
    *((_DWORD *)a2 + 27) = Size;
    if ( v14 )
    {
      v16 = 256;
      if ( v14 < 0x100 )
        v16 = v14;
      memcpy_0((char *)a2 + 112, Size_4, v16);
    }
    v17 = v40;
    v18 = v46;
    v19 = v43;
    *(_QWORD *)a3 = Size_4[32];
    *((_QWORD *)a3 + 3) = v41;
    *((_DWORD *)a3 + 15) = v45;
    *((_DWORD *)a3 + 26) = v52;
    *((_DWORD *)a3 + 14) = v44;
    *((_WORD *)a3 + 33) = v47;
    *((_WORD *)a3 + 34) = v48;
    *((_BYTE *)a3 + 70) = v49;
    *((_BYTE *)a3 + 71) = v50;
    *((_BYTE *)a3 + 64) = v18;
    *(_OWORD *)((char *)a3 + 8) = v17;
    *((_OWORD *)a3 + 2) = v42;
    v20 = *(_OWORD *)v51.m256i_i8;
    *((_QWORD *)a3 + 6) = v19;
    *(_OWORD *)((char *)a3 + 72) = v20;
    if ( v18 )
      *(_OWORD *)((char *)a3 + 84) = *(_OWORD *)((char *)&v51.m256i_u64[1] + 4);
    else
      *(_OWORD *)((char *)a3 + 88) = *(_OWORD *)&v51.m256i_u64[2];
    v21 = Src;
    *((_DWORD *)a3 + 27) = Src;
    if ( v21 )
    {
      if ( v21 < 0x100 )
        v15 = v21;
      memcpy_0((char *)a3 + 112, &Src_4, v15);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v60) = 0;
      Buffer[0] = 0;
      v9 = *((_DWORD *)this + 24);
      if ( v9 != -1 )
        _itow_s(v9, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v60, L"IOCTL_NDISWAN_GET_COMPRESSION_INFO failed with error 0x%x", LastError);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v60,
          (unsigned int)&v55,
          0,
          (__int64)Buffer);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18003e5a0  push    rbp
0x18003e5a2  push    rbx
0x18003e5a3  push    rsi
0x18003e5a4  push    rdi
0x18003e5a5  push    r14
0x18003e5a7  lea     rbp, [rsp-0A90h]
0x18003e5af  sub     rsp, 0B90h
0x18003e5b6  mov     rax, cs:__security_cookie
0x18003e5bd  xor     rax, rsp
0x18003e5c0  mov     [rbp+0AB0h+var_30], rax
0x18003e5c7  mov     rbx, r8
0x18003e5ca  mov     [rsp+0BB0h+BytesReturned], 0
0x18003e5d2  mov     rdi, rdx
0x18003e5d5  mov     rsi, rcx
0x18003e5d8  mov     r14d, 2E8h
0x18003e5de  lea     rcx, [rsp+0BB0h+OutBuffer]; void *
0x18003e5e3  mov     r8d, r14d; Size
0x18003e5e6  xor     edx, edx; Val
0x18003e5e8  call    memset_0
0x18003e5ed  xor     eax, eax
0x18003e5ef  lea     rcx, [rbp+0AB0h+var_82C]; void *
0x18003e5f6  xor     edx, edx; Val
0x18003e5f8  mov     [rbp+0AB0h+var_830], eax
0x18003e5fe  mov     r8d, 7FCh; Size
0x18003e604  call    memset_0
0x18003e609  mov     dl, cs:byte_1800C8404
0x18003e60f  xor     eax, eax
0x18003e611  mov     dword ptr [rbp+0AB0h+Buffer], eax
0x18003e617  xorps   xmm0, xmm0
0x18003e61a  mov     [rbp+0AB0h+var_83C], eax
0x18003e620  movups  [rbp+0AB0h+var_85C], xmm0
0x18003e627  movups  [rbp+0AB0h+var_84C], xmm0
0x18003e62e  movups  [rbp+0AB0h+var_870], xmm0
0x18003e635  test    dl, 8
0x18003e638  jz      short loc_18003E6A4
0x18003e63a  mov     [rbp+0AB0h+Buffer], ax
0x18003e641  test    rsi, rsi
0x18003e644  jz      short loc_18003E669
0x18003e646  mov     ecx, [rsi+60h]; Value
0x18003e649  cmp     ecx, 0FFFFFFFFh
0x18003e64c  jz      short loc_18003E669
0x18003e64e  lea     r9d, [rax+0Ah]; Radix
0x18003e652  lea     r8d, [rax+14h]; BufferCount
0x18003e656  lea     rdx, [rbp+0AB0h+Buffer]; Buffer
0x18003e65d  call    cs:__imp__itow_s
0x18003e663  mov     dl, cs:byte_1800C8404
0x18003e669  test    dl, 8
0x18003e66c  jz      short loc_18003E6A4
0x18003e66e  lea     rax, [rbp+0AB0h+Buffer]
0x18003e675  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x18003e67a  lea     r9, [rbp+0AB0h+var_870]
0x18003e681  lea     r8, aCompressionget; "CompressionGetInfo"
0x18003e688  mov     [rsp+0BB0h+lpOutBuffer], 0
0x18003e691  lea     rdx, RasDdmParamTraceError
0x18003e698  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e69f  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e6a4  mov     rax, [rsi+70h]
0x18003e6a8  lea     r8, [rsp+0BB0h+OutBuffer]; lpInBuffer
0x18003e6ad  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x18003e6b4  mov     r9d, r14d; nInBufferSize
0x18003e6b7  mov     [rsp+0BB0h+OutBuffer], rax
0x18003e6bc  mov     edx, 120044h; dwIoControlCode
0x18003e6c1  mov     [rsp+0BB0h+lpOverlapped], 0; lpOverlapped
0x18003e6ca  lea     rax, [rsp+0BB0h+BytesReturned]
0x18003e6cf  mov     [rsp+0BB0h+lpBytesReturned], rax; lpBytesReturned
0x18003e6d4  lea     rax, [rsp+0BB0h+OutBuffer]
0x18003e6d9  mov     [rsp+0BB0h+nOutBufferSize], r14d; nOutBufferSize
0x18003e6de  mov     [rsp+0BB0h+lpOutBuffer], rax; lpOutBuffer
0x18003e6e3  call    cs:__imp_DeviceIoControl
0x18003e6e9  test    eax, eax
0x18003e6eb  jnz     loc_18003E794
0x18003e6f1  call    cs:__imp_GetLastError
0x18003e6f7  test    cs:byte_1800C8404, 8
0x18003e6fe  mov     r14d, eax
0x18003e701  jz      loc_18003E90D
0x18003e707  xor     ecx, ecx
0x18003e709  mov     word ptr [rbp+0AB0h+var_830], cx
0x18003e710  mov     [rbp+0AB0h+Buffer], cx
0x18003e717  mov     ecx, [rsi+60h]; Value
0x18003e71a  cmp     ecx, 0FFFFFFFFh
0x18003e71d  jz      short loc_18003E736
0x18003e71f  mov     r9d, 0Ah; Radix
0x18003e725  lea     rdx, [rbp+0AB0h+Buffer]; Buffer
0x18003e72c  lea     r8d, [r9+0Ah]; BufferCount
0x18003e730  call    cs:__imp__itow_s
0x18003e736  mov     r8d, r14d
0x18003e739  lea     rdx, aIoctlNdiswanGe_4; "IOCTL_NDISWAN_GET_COMPRESSION_INFO fail"...
0x18003e740  lea     rcx, [rbp+0AB0h+var_830]
0x18003e747  call    FormatRRASErrorString
0x18003e74c  test    cs:byte_1800C8404, 8
0x18003e753  jz      loc_18003E90D
0x18003e759  lea     rax, [rbp+0AB0h+Buffer]
0x18003e760  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x18003e765  lea     r9, [rbp+0AB0h+var_870]
0x18003e76c  lea     r8, [rbp+0AB0h+var_830]
0x18003e773  mov     [rsp+0BB0h+lpOutBuffer], 0
0x18003e77c  lea     rdx, RasDdmParamTraceError
0x18003e783  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003e78a  call    McTemplateU0zjzz_EventWriteTransfer
0x18003e78f  jmp     loc_18003E90D
0x18003e794  mov     rax, [rsp+0BB0h+var_B58]
0x18003e799  xor     r14d, r14d
0x18003e79c  movaps  xmm0, [rsp+0BB0h+var_B50]
0x18003e7a1  mov     cl, [rbp+0AB0h+var_B18]
0x18003e7a4  movsd   xmm1, [rbp+0AB0h+var_B28]
0x18003e7a9  mov     [rdi], rax
0x18003e7ac  mov     rax, [rsp+0BB0h+var_B40]
0x18003e7b1  mov     [rdi+18h], rax
0x18003e7b5  mov     eax, [rbp+0AB0h+var_B1C]
0x18003e7b8  mov     [rdi+3Ch], eax
0x18003e7bb  mov     eax, [rbp+0AB0h+var_AF0]
0x18003e7be  mov     [rdi+68h], eax
0x18003e7c1  mov     eax, [rbp+0AB0h+var_B20]
0x18003e7c4  mov     [rdi+38h], eax
0x18003e7c7  movzx   eax, [rbp+0AB0h+var_B16]
0x18003e7cb  mov     [rdi+42h], ax
0x18003e7cf  movzx   eax, [rbp+0AB0h+var_B14]
0x18003e7d3  mov     [rdi+44h], ax
0x18003e7d7  mov     al, [rbp+0AB0h+var_B12]
0x18003e7da  mov     [rdi+46h], al
0x18003e7dd  mov     al, [rbp+0AB0h+var_B11]
0x18003e7e0  mov     [rdi+47h], al
0x18003e7e3  mov     [rdi+40h], cl
0x18003e7e6  movdqu  xmmword ptr [rdi+8], xmm0
0x18003e7eb  movups  xmm0, [rsp+0BB0h+var_B38]
0x18003e7f0  movups  xmmword ptr [rdi+20h], xmm0
0x18003e7f4  movaps  xmm0, [rbp+0AB0h+var_B10]
0x18003e7f8  movsd   qword ptr [rdi+30h], xmm1
0x18003e7fd  movups  xmmword ptr [rdi+48h], xmm0
0x18003e801  test    cl, cl
0x18003e803  jnz     short loc_18003E80F
0x18003e805  movaps  xmm1, [rbp+0AB0h+var_B00]
0x18003e809  movups  xmmword ptr [rdi+58h], xmm1
0x18003e80d  jmp     short loc_18003E817
0x18003e80f  movups  xmm1, [rbp+0AB0h+var_B10+0Ch]
0x18003e813  movups  xmmword ptr [rdi+54h], xmm1
0x18003e817  mov     ecx, dword ptr [rbp+0AB0h+Size]
0x18003e81a  mov     esi, 100h
0x18003e81f  mov     [rdi+6Ch], ecx
0x18003e822  test    ecx, ecx
0x18003e824  jz      short loc_18003E83C
0x18003e826  cmp     ecx, esi
0x18003e828  lea     rdx, [rbp+0AB0h+Size+4]; Src
0x18003e82c  mov     r8d, esi
0x18003e82f  cmovb   r8d, ecx; Size
0x18003e833  lea     rcx, [rdi+70h]; void *
0x18003e837  call    memcpy_0
0x18003e83c  mov     rax, [rbp+0AB0h+var_9E8]
0x18003e843  movaps  xmm0, [rbp+0AB0h+var_9E0]
0x18003e84a  mov     cl, [rbp+0AB0h+var_9A8]
0x18003e850  movsd   xmm1, [rbp+0AB0h+var_9B8]
0x18003e858  mov     [rbx], rax
0x18003e85b  mov     rax, [rbp+0AB0h+var_9D0]
0x18003e862  mov     [rbx+18h], rax
0x18003e866  mov     eax, [rbp+0AB0h+var_9AC]
0x18003e86c  mov     [rbx+3Ch], eax
0x18003e86f  mov     eax, [rbp+0AB0h+var_980]
0x18003e875  mov     [rbx+68h], eax
0x18003e878  mov     eax, [rbp+0AB0h+var_9B0]
0x18003e87e  mov     [rbx+38h], eax
0x18003e881  movzx   eax, [rbp+0AB0h+var_9A6]
0x18003e888  mov     [rbx+42h], ax
0x18003e88c  movzx   eax, [rbp+0AB0h+var_9A4]
0x18003e893  mov     [rbx+44h], ax
0x18003e897  mov     al, [rbp+0AB0h+var_9A2]
0x18003e89d  mov     [rbx+46h], al
0x18003e8a0  mov     al, [rbp+0AB0h+var_9A1]
0x18003e8a6  mov     [rbx+47h], al
0x18003e8a9  mov     [rbx+40h], cl
0x18003e8ac  movdqu  xmmword ptr [rbx+8], xmm0
0x18003e8b1  movups  xmm0, [rbp+0AB0h+var_9C8]
0x18003e8b8  movups  xmmword ptr [rbx+20h], xmm0
0x18003e8bc  movaps  xmm0, [rbp+0AB0h+var_9A0]
0x18003e8c3  movsd   qword ptr [rbx+30h], xmm1
0x18003e8c8  movups  xmmword ptr [rbx+48h], xmm0
0x18003e8cc  test    cl, cl
0x18003e8ce  jnz     short loc_18003E8DD
0x18003e8d0  movaps  xmm1, [rbp+0AB0h+var_990]
0x18003e8d7  movups  xmmword ptr [rbx+58h], xmm1
0x18003e8db  jmp     short loc_18003E8E8
0x18003e8dd  movups  xmm1, [rbp+0AB0h+var_9A0+0Ch]
0x18003e8e4  movups  xmmword ptr [rbx+54h], xmm1
0x18003e8e8  mov     eax, dword ptr [rbp+0AB0h+Src]
0x18003e8ee  mov     [rbx+6Ch], eax
0x18003e8f1  test    eax, eax
0x18003e8f3  jz      short loc_18003E90D
0x18003e8f5  cmp     eax, esi
0x18003e8f7  lea     rcx, [rbx+70h]; void *
0x18003e8fb  lea     rdx, [rbp+0AB0h+Src+4]; Src
0x18003e902  cmovb   esi, eax
0x18003e905  mov     r8d, esi; Size
0x18003e908  call    memcpy_0
0x18003e90d  mov     eax, r14d
0x18003e910  mov     rcx, [rbp+0AB0h+var_30]
0x18003e917  xor     rcx, rsp; StackCookie
0x18003e91a  call    __security_check_cookie
0x18003e91f  add     rsp, 0B90h
0x18003e926  pop     r14
0x18003e928  pop     rdi
0x18003e929  pop     rsi
0x18003e92a  pop     rbx
0x18003e92b  pop     rbp
0x18003e92c  retn
```
