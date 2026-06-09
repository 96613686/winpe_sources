# DdmModernDevice::CompressionGetInfo(_RAS_COMPRESSION_INFO *,_RAS_COMPRESSION_INFO *)

- ea: `0x18003fe60`
- end: `0x1800401f3`
- name: `?CompressionGetInfo@DdmModernDevice@@UEAAKPEAU_RAS_COMPRESSION_INFO@@0@Z`
- size: `915`
- prototype: `__int64 __fastcall(DdmModernDevice *this, struct _RAS_COMPRESSION_INFO *, struct _RAS_COMPRESSION_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002be6`
- `0x180007d00`
- `0x18003fe60`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18003ff97`
- `KERNEL32!DeviceIoControl` at `0x18003ff97`
- `KERNEL32!GetLastError` at `0x18003ffab`
- `KERNEL32!GetLastError` at `0x18003ffab`

## string_xrefs

- `0x18003ff3a`: `CompressionGetInfo`
- `0x18003ffe9`: `IOCTL_NDISWAN_GET_COMPRESSION_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::CompressionGetInfo(
        DdmModernDevice *this,
        struct _RAS_COMPRESSION_INFO *a2,
        struct _RAS_COMPRESSION_INFO *a3)
{
  DWORD LastError; // r14d
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int128 v9; // xmm0
  char v10; // cl
  __int64 v11; // xmm1_8
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  char v14; // al
  __int128 v15; // xmm1
  unsigned int v16; // ecx
  unsigned int v17; // esi
  size_t v18; // r8
  __int128 v19; // xmm0
  char v20; // cl
  __int64 v21; // xmm1_8
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  char v24; // al
  __int128 v25; // xmm1
  unsigned int v26; // eax
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int128 v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  char v37; // [rsp+98h] [rbp-68h]
  __int16 v38; // [rsp+9Ah] [rbp-66h]
  _BYTE v39[36]; // [rsp+9Ch] [rbp-64h]
  int v40; // [rsp+C0h] [rbp-40h]
  unsigned int Size; // [rsp+C4h] [rbp-3Ch]
  _QWORD Size_4[33]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v43; // [rsp+1D0h] [rbp+D0h]
  __int64 v44; // [rsp+1E0h] [rbp+E0h]
  __int128 v45; // [rsp+1E8h] [rbp+E8h]
  __int64 v46; // [rsp+1F8h] [rbp+F8h]
  int v47; // [rsp+200h] [rbp+100h]
  int v48; // [rsp+204h] [rbp+104h]
  char v49; // [rsp+208h] [rbp+108h]
  __int16 v50; // [rsp+20Ah] [rbp+10Ah]
  _BYTE v51[36]; // [rsp+20Ch] [rbp+10Ch]
  int v52; // [rsp+230h] [rbp+130h]
  unsigned int Src; // [rsp+234h] [rbp+134h]
  size_t Src_4; // [rsp+238h] [rbp+138h] BYREF
  __int128 v55; // [rsp+340h] [rbp+240h] BYREF
  int v56; // [rsp+350h] [rbp+250h] BYREF
  __int128 v57; // [rsp+354h] [rbp+254h]
  __int128 v58; // [rsp+364h] [rbp+264h]
  int v59; // [rsp+374h] [rbp+274h]
  int v60; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v61[2044]; // [rsp+384h] [rbp+284h] BYREF

  BytesReturned[0] = 0;
  LastError = 0;
  memset_0(&v30, 0, 0x2E0u);
  v60 = 0;
  memset_0(v61, 0, sizeof(v61));
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v58 = 0;
  v55 = 0;
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v56) = 0;
    v7 = this ? *((unsigned int *)this + 24) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v56, v7);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"CompressionGetInfo",
        (unsigned int)&v55,
        0,
        (__int64)&v56);
  }
  OutBuffer = *((_QWORD *)this + 14);
  if ( DeviceIoControl(gblDdmDriverInfo, 0x120044u, &OutBuffer, 0x2E8u, &OutBuffer, 0x2E8u, BytesReturned, 0) )
  {
    v9 = v31;
    v10 = v37;
    v11 = v34;
    *(_QWORD *)a2 = v30;
    *((_QWORD *)a2 + 3) = v32;
    *((_DWORD *)a2 + 15) = v36;
    *((_DWORD *)a2 + 26) = v40;
    *((_DWORD *)a2 + 14) = v35;
    *((_WORD *)a2 + 33) = v38;
    *((_BYTE *)a2 + 64) = v10;
    *(_OWORD *)((char *)a2 + 8) = v9;
    *((_OWORD *)a2 + 2) = v33;
    *((_QWORD *)a2 + 6) = v11;
    if ( v10 )
    {
      v15 = *(_OWORD *)&v39[16];
      *(_OWORD *)((char *)a2 + 68) = *(_OWORD *)v39;
      *(_OWORD *)((char *)a2 + 84) = v15;
    }
    else
    {
      v12 = *(_OWORD *)&v39[4];
      v13 = *(_OWORD *)&v39[20];
      *((_WORD *)a2 + 34) = *(_WORD *)v39;
      *((_BYTE *)a2 + 70) = v39[2];
      v14 = v39[3];
      *(_OWORD *)((char *)a2 + 72) = v12;
      *((_BYTE *)a2 + 71) = v14;
      *(_OWORD *)((char *)a2 + 88) = v13;
    }
    v16 = Size;
    v17 = 256;
    *((_DWORD *)a2 + 27) = Size;
    if ( v16 )
    {
      v18 = 256;
      if ( v16 < 0x100 )
        v18 = v16;
      memcpy_0((char *)a2 + 112, Size_4, v18);
    }
    v19 = v43;
    v20 = v49;
    v21 = v46;
    *(_QWORD *)a3 = Size_4[32];
    *((_QWORD *)a3 + 3) = v44;
    *((_DWORD *)a3 + 15) = v48;
    *((_DWORD *)a3 + 26) = v52;
    *((_DWORD *)a3 + 14) = v47;
    *((_WORD *)a3 + 33) = v50;
    *((_BYTE *)a3 + 64) = v20;
    *(_OWORD *)((char *)a3 + 8) = v19;
    *((_OWORD *)a3 + 2) = v45;
    *((_QWORD *)a3 + 6) = v21;
    if ( v20 )
    {
      v25 = *(_OWORD *)&v51[16];
      *(_OWORD *)((char *)a3 + 68) = *(_OWORD *)v51;
      *(_OWORD *)((char *)a3 + 84) = v25;
    }
    else
    {
      v22 = *(_OWORD *)&v51[4];
      v23 = *(_OWORD *)&v51[20];
      *((_WORD *)a3 + 34) = *(_WORD *)v51;
      *((_BYTE *)a3 + 70) = v51[2];
      v24 = v51[3];
      *(_OWORD *)((char *)a3 + 72) = v22;
      *((_BYTE *)a3 + 71) = v24;
      *(_OWORD *)((char *)a3 + 88) = v23;
    }
    v26 = Src;
    *((_DWORD *)a3 + 27) = Src;
    if ( v26 )
    {
      if ( v26 < 0x100 )
        v17 = v26;
      memcpy_0((char *)a3 + 112, &Src_4, v17);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v8 = *((unsigned int *)this + 24);
      LOWORD(v60) = 0;
      LOWORD(v56) = 0;
      ConvertPortNoToString(&v56, v8);
      FormatRRASErrorString(&v60, L"IOCTL_NDISWAN_GET_COMPRESSION_INFO failed with error 0x%x", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v60,
          (unsigned int)&v55,
          0,
          (__int64)&v56);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18003fe60  mov     [rsp-8+arg_18], rbx
0x18003fe65  push    rbp
0x18003fe66  push    rsi
0x18003fe67  push    rdi
0x18003fe68  push    r14
0x18003fe6a  push    r15
0x18003fe6c  lea     rbp, [rsp-0A90h]
0x18003fe74  sub     rsp, 0B90h
0x18003fe7b  mov     rax, cs:__security_cookie
0x18003fe82  xor     rax, rsp
0x18003fe85  mov     [rbp+0AB0h+var_30], rax
0x18003fe8c  mov     rbx, r8
0x18003fe8f  mov     rdi, rdx
0x18003fe92  mov     rsi, rcx
0x18003fe95  xor     r15d, r15d
0x18003fe98  xor     edx, edx; Val
0x18003fe9a  mov     [rsp+0BB0h+BytesReturned], r15d
0x18003fe9f  mov     r8d, 2E0h; Size
0x18003fea5  lea     rcx, [rsp+0BB0h+var_B58]; void *
0x18003feaa  mov     r14d, r15d
0x18003fead  call    memset_0
0x18003feb2  xor     edx, edx; Val
0x18003feb4  mov     [rbp+0AB0h+var_830], r15d
0x18003febb  mov     r8d, 7FCh; Size
0x18003fec1  lea     rcx, [rbp+0AB0h+var_82C]; void *
0x18003fec8  call    memset_0
0x18003fecd  xorps   xmm0, xmm0
0x18003fed0  mov     [rbp+0AB0h+var_860], r15d
0x18003fed7  xor     eax, eax
0x18003fed9  test    cs:byte_1800CF404, 8
0x18003fee0  movups  [rbp+0AB0h+var_85C], xmm0
0x18003fee7  mov     [rbp+0AB0h+var_83C], eax
0x18003feed  movups  [rbp+0AB0h+var_84C], xmm0
0x18003fef4  movups  [rbp+0AB0h+var_870], xmm0
0x18003fefb  jz      short loc_18003FF59
0x18003fefd  mov     word ptr [rbp+0AB0h+var_860], r15w
0x18003ff05  test    rsi, rsi
0x18003ff08  jz      short loc_18003FF0F
0x18003ff0a  mov     edx, [rsi+60h]
0x18003ff0d  jmp     short loc_18003FF12
0x18003ff0f  or      edx, 0FFFFFFFFh
0x18003ff12  lea     rcx, [rbp+0AB0h+var_860]
0x18003ff19  call    ConvertPortNoToString
0x18003ff1e  test    cs:byte_1800CF404, 8
0x18003ff25  jz      short loc_18003FF59
0x18003ff27  lea     rax, [rbp+0AB0h+var_860]
0x18003ff2e  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x18003ff33  lea     r9, [rbp+0AB0h+var_870]
0x18003ff3a  lea     r8, aCompressionget; "CompressionGetInfo"
0x18003ff41  mov     [rsp+0BB0h+lpOutBuffer], r15
0x18003ff46  lea     rdx, RasDdmParamTraceError
0x18003ff4d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ff54  call    McTemplateU0zjzz_EventWriteTransfer
0x18003ff59  mov     rax, [rsi+70h]
0x18003ff5d  lea     r8, [rsp+0BB0h+OutBuffer]; lpInBuffer
0x18003ff62  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x18003ff69  mov     r9d, 2E8h; nInBufferSize
0x18003ff6f  mov     [rsp+0BB0h+OutBuffer], rax
0x18003ff74  mov     edx, 120044h; dwIoControlCode
0x18003ff79  mov     [rsp+0BB0h+lpOverlapped], r15; lpOverlapped
0x18003ff7e  lea     rax, [rsp+0BB0h+BytesReturned]
0x18003ff83  mov     [rsp+0BB0h+lpBytesReturned], rax; lpBytesReturned
0x18003ff88  lea     rax, [rsp+0BB0h+OutBuffer]
0x18003ff8d  mov     [rsp+0BB0h+nOutBufferSize], r9d; nOutBufferSize
0x18003ff92  mov     [rsp+0BB0h+lpOutBuffer], rax; lpOutBuffer
0x18003ff97  call    cs:__imp_DeviceIoControl
0x18003ff9e  nop     dword ptr [rax+rax+00h]
0x18003ffa3  test    eax, eax
0x18003ffa5  jnz     loc_180040040
0x18003ffab  call    cs:__imp_GetLastError
0x18003ffb2  nop     dword ptr [rax+rax+00h]
0x18003ffb7  test    cs:byte_1800CF404, 8
0x18003ffbe  mov     r14d, eax
0x18003ffc1  jz      loc_1800401C9
0x18003ffc7  mov     edx, [rsi+60h]
0x18003ffca  lea     rcx, [rbp+0AB0h+var_860]
0x18003ffd1  mov     word ptr [rbp+0AB0h+var_830], r15w
0x18003ffd9  mov     word ptr [rbp+0AB0h+var_860], r15w
0x18003ffe1  call    ConvertPortNoToString
0x18003ffe6  mov     r8d, r14d
0x18003ffe9  lea     rdx, aIoctlNdiswanGe_4; "IOCTL_NDISWAN_GET_COMPRESSION_INFO fail"...
0x18003fff0  lea     rcx, [rbp+0AB0h+var_830]
0x18003fff7  call    FormatRRASErrorString
0x18003fffc  test    cs:byte_1800CF404, 8
0x180040003  jz      loc_1800401C9
0x180040009  lea     rax, [rbp+0AB0h+var_860]
0x180040010  mov     qword ptr [rsp+0BB0h+nOutBufferSize], rax
0x180040015  lea     r9, [rbp+0AB0h+var_870]
0x18004001c  lea     r8, [rbp+0AB0h+var_830]
0x180040023  mov     [rsp+0BB0h+lpOutBuffer], r15
0x180040028  lea     rdx, RasDdmParamTraceError
0x18004002f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180040036  call    McTemplateU0zjzz_EventWriteTransfer
0x18004003b  jmp     loc_1800401C9
0x180040040  mov     rax, [rsp+0BB0h+var_B58]
0x180040045  movaps  xmm0, [rsp+0BB0h+var_B50]
0x18004004a  mov     cl, [rbp+0AB0h+var_B18]
0x18004004d  movsd   xmm1, [rbp+0AB0h+var_B28]
0x180040052  mov     [rdi], rax
0x180040055  mov     rax, [rsp+0BB0h+var_B40]
0x18004005a  mov     [rdi+18h], rax
0x18004005e  mov     eax, [rbp+0AB0h+var_B1C]
0x180040061  mov     [rdi+3Ch], eax
0x180040064  mov     eax, [rbp+0AB0h+var_AF0]
0x180040067  mov     [rdi+68h], eax
0x18004006a  mov     eax, [rbp+0AB0h+var_B20]
0x18004006d  mov     [rdi+38h], eax
0x180040070  movzx   eax, [rbp+0AB0h+var_B16]
0x180040074  mov     [rdi+42h], ax
0x180040078  mov     [rdi+40h], cl
0x18004007b  movdqu  xmmword ptr [rdi+8], xmm0
0x180040080  movups  xmm0, [rsp+0BB0h+var_B38]
0x180040085  movups  xmmword ptr [rdi+20h], xmm0
0x180040089  movsd   qword ptr [rdi+30h], xmm1
0x18004008e  test    cl, cl
0x180040090  jnz     short loc_1800400B8
0x180040092  movzx   eax, word ptr [rbp+0AB0h+var_B14]
0x180040096  movaps  xmm0, [rbp+0AB0h+var_B14+4]
0x18004009a  movaps  xmm1, [rbp+0AB0h+var_B00]
0x18004009e  mov     [rdi+44h], ax
0x1800400a2  mov     al, byte ptr [rbp+0AB0h+var_B14+2]
0x1800400a5  mov     [rdi+46h], al
0x1800400a8  mov     al, byte ptr [rbp+0AB0h+var_B14+3]
0x1800400ab  movups  xmmword ptr [rdi+48h], xmm0
0x1800400af  mov     [rdi+47h], al
0x1800400b2  movups  xmmword ptr [rdi+58h], xmm1
0x1800400b6  jmp     short loc_1800400C8
0x1800400b8  movups  xmm0, [rbp+0AB0h+var_B14]
0x1800400bc  movups  xmm1, xmmword ptr [rbp-54h]
0x1800400c0  movups  xmmword ptr [rdi+44h], xmm0
0x1800400c4  movups  xmmword ptr [rdi+54h], xmm1
0x1800400c8  mov     ecx, dword ptr [rbp+0AB0h+Size]
0x1800400cb  mov     esi, 100h
0x1800400d0  mov     [rdi+6Ch], ecx
0x1800400d3  test    ecx, ecx
0x1800400d5  jz      short loc_1800400ED
0x1800400d7  cmp     ecx, esi
0x1800400d9  lea     rdx, [rbp+0AB0h+Size+4]; Src
0x1800400dd  mov     r8d, esi
0x1800400e0  cmovb   r8d, ecx; Size
0x1800400e4  lea     rcx, [rdi+70h]; void *
0x1800400e8  call    memcpy_0
0x1800400ed  mov     rax, [rbp+0AB0h+var_9E8]
0x1800400f4  movaps  xmm0, [rbp+0AB0h+var_9E0]
0x1800400fb  mov     cl, [rbp+0AB0h+var_9A8]
0x180040101  movsd   xmm1, [rbp+0AB0h+var_9B8]
0x180040109  mov     [rbx], rax
0x18004010c  mov     rax, [rbp+0AB0h+var_9D0]
0x180040113  mov     [rbx+18h], rax
0x180040117  mov     eax, [rbp+0AB0h+var_9AC]
0x18004011d  mov     [rbx+3Ch], eax
0x180040120  mov     eax, [rbp+0AB0h+var_980]
0x180040126  mov     [rbx+68h], eax
0x180040129  mov     eax, [rbp+0AB0h+var_9B0]
0x18004012f  mov     [rbx+38h], eax
0x180040132  movzx   eax, [rbp+0AB0h+var_9A6]
0x180040139  mov     [rbx+42h], ax
0x18004013d  mov     [rbx+40h], cl
0x180040140  movdqu  xmmword ptr [rbx+8], xmm0
0x180040145  movups  xmm0, [rbp+0AB0h+var_9C8]
0x18004014c  movups  xmmword ptr [rbx+20h], xmm0
0x180040150  movsd   qword ptr [rbx+30h], xmm1
0x180040155  test    cl, cl
0x180040157  jnz     short loc_18004018E
0x180040159  movzx   eax, word ptr [rbp+0AB0h+var_9A4]
0x180040160  movaps  xmm0, [rbp+0AB0h+var_9A4+4]
0x180040167  movaps  xmm1, [rbp+0AB0h+var_990]
0x18004016e  mov     [rbx+44h], ax
0x180040172  mov     al, byte ptr [rbp+0AB0h+var_9A4+2]
0x180040178  mov     [rbx+46h], al
0x18004017b  mov     al, byte ptr [rbp+0AB0h+var_9A4+3]
0x180040181  movups  xmmword ptr [rbx+48h], xmm0
0x180040185  mov     [rbx+47h], al
0x180040188  movups  xmmword ptr [rbx+58h], xmm1
0x18004018c  jmp     short loc_1800401A4
0x18004018e  movups  xmm0, [rbp+0AB0h+var_9A4]
0x180040195  movups  xmm1, xmmword ptr [rbp+11Ch]
0x18004019c  movups  xmmword ptr [rbx+44h], xmm0
0x1800401a0  movups  xmmword ptr [rbx+54h], xmm1
0x1800401a4  mov     eax, dword ptr [rbp+0AB0h+Src]
0x1800401aa  mov     [rbx+6Ch], eax
0x1800401ad  test    eax, eax
0x1800401af  jz      short loc_1800401C9
0x1800401b1  cmp     eax, esi
0x1800401b3  lea     rcx, [rbx+70h]; void *
0x1800401b7  lea     rdx, [rbp+0AB0h+Src+4]; Src
0x1800401be  cmovb   esi, eax
0x1800401c1  mov     r8d, esi; Size
0x1800401c4  call    memcpy_0
0x1800401c9  mov     eax, r14d
0x1800401cc  mov     rcx, [rbp+0AB0h+var_30]
0x1800401d3  xor     rcx, rsp; StackCookie
0x1800401d6  call    __security_check_cookie
0x1800401db  mov     rbx, [rsp+0BB0h+arg_18]
0x1800401e3  add     rsp, 0B90h
0x1800401ea  pop     r15
0x1800401ec  pop     r14
0x1800401ee  pop     rdi
0x1800401ef  pop     rsi
0x1800401f0  pop     rbp
0x1800401f1  retn
```
