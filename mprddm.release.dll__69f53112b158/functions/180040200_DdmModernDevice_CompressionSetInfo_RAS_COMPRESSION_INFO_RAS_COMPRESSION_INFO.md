# DdmModernDevice::CompressionSetInfo(_RAS_COMPRESSION_INFO *,_RAS_COMPRESSION_INFO *)

- ea: `0x180040200`
- end: `0x180040585`
- name: `?CompressionSetInfo@DdmModernDevice@@UEAAKPEAU_RAS_COMPRESSION_INFO@@0@Z`
- size: `901`
- prototype: `__int64 __fastcall(DdmModernDevice *this, struct _RAS_COMPRESSION_INFO *, struct _RAS_COMPRESSION_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180002be6`
- `0x180007d00`
- `0x180040200`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800404c3`
- `KERNEL32!DeviceIoControl` at `0x1800404c3`
- `KERNEL32!GetLastError` at `0x1800404d7`
- `KERNEL32!GetLastError` at `0x1800404d7`

## string_xrefs

- `0x1800402da`: `CompressionSetInfo`
- `0x180040512`: `IOCTL_NDISWAN_SET_COMPRESSION_INFO failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::CompressionSetInfo(
        DdmModernDevice *this,
        struct _RAS_COMPRESSION_INFO *a2,
        struct _RAS_COMPRESSION_INFO *a3)
{
  DWORD LastError; // r14d
  __int64 v7; // rdx
  __int128 v8; // xmm0
  char v9; // cl
  __int64 v10; // xmm1_8
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm1
  unsigned int v14; // ecx
  unsigned int v15; // esi
  size_t v16; // r8
  __int128 v17; // xmm0
  char v18; // cl
  __int64 v19; // xmm1_8
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm1
  unsigned int v23; // eax
  __int64 v24; // rdx
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD OutBuffer[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+70h] [rbp-90h]
  __int128 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+94h] [rbp-6Ch]
  char v34; // [rsp+98h] [rbp-68h]
  __int16 v35; // [rsp+9Ah] [rbp-66h]
  _BYTE v36[36]; // [rsp+9Ch] [rbp-64h]
  int v37; // [rsp+C0h] [rbp-40h]
  unsigned int v38; // [rsp+C4h] [rbp-3Ch]
  _BYTE v39[256]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+1C8h] [rbp+C8h]
  __int128 v41; // [rsp+1D0h] [rbp+D0h]
  __int64 v42; // [rsp+1E0h] [rbp+E0h]
  __int128 v43; // [rsp+1E8h] [rbp+E8h]
  __int64 v44; // [rsp+1F8h] [rbp+F8h]
  int v45; // [rsp+200h] [rbp+100h]
  int v46; // [rsp+204h] [rbp+104h]
  char v47; // [rsp+208h] [rbp+108h]
  __int16 v48; // [rsp+20Ah] [rbp+10Ah]
  _BYTE v49[36]; // [rsp+20Ch] [rbp+10Ch]
  int v50; // [rsp+230h] [rbp+130h]
  unsigned int v51; // [rsp+234h] [rbp+134h]
  _BYTE v52[264]; // [rsp+238h] [rbp+138h] BYREF
  __int128 v53; // [rsp+340h] [rbp+240h] BYREF
  int v54; // [rsp+350h] [rbp+250h] BYREF
  __int128 v55; // [rsp+354h] [rbp+254h]
  __int128 v56; // [rsp+364h] [rbp+264h]
  int v57; // [rsp+374h] [rbp+274h]
  int v58; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v59[2044]; // [rsp+384h] [rbp+284h] BYREF

  BytesReturned[0] = 0;
  LastError = 0;
  memset_0(OutBuffer, 0, 0x2E8u);
  v58 = 0;
  memset_0(v59, 0, sizeof(v59));
  v54 = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  v53 = 0;
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v54) = 0;
    v7 = this ? *((unsigned int *)this + 24) : 0xFFFFFFFFLL;
    ConvertPortNoToString(&v54, v7);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)L"CompressionSetInfo",
        (unsigned int)&v53,
        0,
        (__int64)&v54);
  }
  v8 = *(_OWORD *)((char *)a2 + 8);
  v9 = *((_BYTE *)a2 + 64);
  v10 = *((_QWORD *)a2 + 6);
  OutBuffer[0] = *((_QWORD *)this + 14);
  OutBuffer[1] = *(_QWORD *)a2;
  v29 = *((_QWORD *)a2 + 3);
  v33 = *((_DWORD *)a2 + 15);
  v37 = *((_DWORD *)a2 + 26);
  v32 = *((_DWORD *)a2 + 14);
  v35 = *((_WORD *)a2 + 33);
  v31 = v10;
  v34 = v9;
  v28 = v8;
  v30 = *((_OWORD *)a2 + 2);
  if ( v9 )
  {
    v13 = *(_OWORD *)((char *)a2 + 84);
    *(_OWORD *)v36 = *(_OWORD *)((char *)a2 + 68);
    *(_OWORD *)&v36[16] = v13;
  }
  else
  {
    v11 = *(_OWORD *)((char *)a2 + 72);
    *(_WORD *)v36 = *((_WORD *)a2 + 34);
    v12 = *(_OWORD *)((char *)a2 + 88);
    *(_WORD *)&v36[2] = *((_WORD *)a2 + 35);
    *(_OWORD *)&v36[4] = v11;
    *(_OWORD *)&v36[20] = v12;
  }
  v14 = *((_DWORD *)a2 + 27);
  v15 = 256;
  v38 = v14;
  if ( v14 )
  {
    v16 = 256;
    if ( v14 < 0x100 )
      v16 = v14;
    memcpy_0(v39, (char *)a2 + 112, v16);
  }
  v17 = *(_OWORD *)((char *)a3 + 8);
  v18 = *((_BYTE *)a3 + 64);
  v19 = *((_QWORD *)a3 + 6);
  v40 = *(_QWORD *)a3;
  v42 = *((_QWORD *)a3 + 3);
  v46 = *((_DWORD *)a3 + 15);
  v50 = *((_DWORD *)a3 + 26);
  v45 = *((_DWORD *)a3 + 14);
  v48 = *((_WORD *)a3 + 33);
  v44 = v19;
  v47 = v18;
  v41 = v17;
  v43 = *((_OWORD *)a3 + 2);
  if ( v18 )
  {
    v22 = *(_OWORD *)((char *)a3 + 84);
    *(_OWORD *)v49 = *(_OWORD *)((char *)a3 + 68);
    *(_OWORD *)&v49[16] = v22;
  }
  else
  {
    v20 = *(_OWORD *)((char *)a3 + 72);
    *(_WORD *)v49 = *((_WORD *)a3 + 34);
    v21 = *(_OWORD *)((char *)a3 + 88);
    *(_WORD *)&v49[2] = *((_WORD *)a3 + 35);
    *(_OWORD *)&v49[4] = v20;
    *(_OWORD *)&v49[20] = v21;
  }
  v23 = *((_DWORD *)a3 + 27);
  v51 = v23;
  if ( v23 )
  {
    if ( v23 < 0x100 )
      v15 = v23;
    memcpy_0(v52, (char *)a3 + 112, v15);
  }
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x120040u, OutBuffer, 0x2E8u, OutBuffer, 0x2E8u, BytesReturned, 0) )
  {
    LastError = GetLastError();
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v24 = *((unsigned int *)this + 24);
      LOWORD(v58) = 0;
      LOWORD(v54) = 0;
      ConvertPortNoToString(&v54, v24);
      FormatRRASErrorString(&v58, L"IOCTL_NDISWAN_SET_COMPRESSION_INFO failed with error 0x%x", LastError);
      if ( (byte_1800CF404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v58,
          (unsigned int)&v53,
          0,
          (__int64)&v54);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180040200  push    rbp
0x180040202  push    rbx
0x180040203  push    rsi
0x180040204  push    rdi
0x180040205  push    r12
0x180040207  push    r14
0x180040209  push    r15
0x18004020b  lea     rbp, [rsp-0A90h]
0x180040213  sub     rsp, 0B90h
0x18004021a  mov     rax, cs:__security_cookie
0x180040221  xor     rax, rsp
0x180040224  mov     [rbp+0AC0h+var_40], rax
0x18004022b  mov     rbx, r8
0x18004022e  mov     rdi, rdx
0x180040231  mov     r15, rcx
0x180040234  xor     r12d, r12d
0x180040237  xor     edx, edx; Val
0x180040239  mov     [rsp+0BC0h+BytesReturned], r12d
0x18004023e  mov     r8d, 2E8h; Size
0x180040244  lea     rcx, [rsp+0BC0h+OutBuffer]; void *
0x180040249  mov     r14d, r12d
0x18004024c  call    memset_0
0x180040251  xor     edx, edx; Val
0x180040253  mov     [rbp+0AC0h+var_840], r12d
0x18004025a  mov     r8d, 7FCh; Size
0x180040260  lea     rcx, [rbp+0AC0h+var_83C]; void *
0x180040267  call    memset_0
0x18004026c  xorps   xmm0, xmm0
0x18004026f  mov     [rbp+0AC0h+var_870], r12d
0x180040276  xor     eax, eax
0x180040278  test    cs:byte_1800CF404, 8
0x18004027f  movups  [rbp+0AC0h+var_86C], xmm0
0x180040286  mov     [rbp+0AC0h+var_84C], eax
0x18004028c  movups  [rbp+0AC0h+var_85C], xmm0
0x180040293  movups  [rbp+0AC0h+var_880], xmm0
0x18004029a  jz      short loc_1800402F9
0x18004029c  mov     word ptr [rbp+0AC0h+var_870], r12w
0x1800402a4  test    r15, r15
0x1800402a7  jz      short loc_1800402AF
0x1800402a9  mov     edx, [r15+60h]
0x1800402ad  jmp     short loc_1800402B2
0x1800402af  or      edx, 0FFFFFFFFh
0x1800402b2  lea     rcx, [rbp+0AC0h+var_870]
0x1800402b9  call    ConvertPortNoToString
0x1800402be  test    cs:byte_1800CF404, 8
0x1800402c5  jz      short loc_1800402F9
0x1800402c7  lea     rax, [rbp+0AC0h+var_870]
0x1800402ce  mov     qword ptr [rsp+0BC0h+nOutBufferSize], rax
0x1800402d3  lea     r9, [rbp+0AC0h+var_880]
0x1800402da  lea     r8, aCompressionset; "CompressionSetInfo"
0x1800402e1  mov     [rsp+0BC0h+lpOutBuffer], r12
0x1800402e6  lea     rdx, RasDdmParamTraceError
0x1800402ed  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800402f4  call    McTemplateU0zjzz_EventWriteTransfer
0x1800402f9  mov     rax, [r15+70h]
0x1800402fd  movups  xmm0, xmmword ptr [rdi+8]
0x180040301  mov     cl, [rdi+40h]
0x180040304  movsd   xmm1, qword ptr [rdi+30h]
0x180040309  mov     [rsp+0BC0h+OutBuffer], rax
0x18004030e  mov     rax, [rdi]
0x180040311  mov     [rsp+0BC0h+var_B68], rax
0x180040316  mov     rax, [rdi+18h]
0x18004031a  mov     [rsp+0BC0h+var_B50], rax
0x18004031f  mov     eax, [rdi+3Ch]
0x180040322  mov     [rbp+0AC0h+var_B2C], eax
0x180040325  mov     eax, [rdi+68h]
0x180040328  mov     [rbp+0AC0h+var_B00], eax
0x18004032b  mov     eax, [rdi+38h]
0x18004032e  mov     [rbp+0AC0h+var_B30], eax
0x180040331  movzx   eax, word ptr [rdi+42h]
0x180040335  mov     [rbp+0AC0h+var_B26], ax
0x180040339  movsd   [rbp+0AC0h+var_B38], xmm1
0x18004033e  mov     [rbp+0AC0h+var_B28], cl
0x180040341  movdqu  [rsp+0BC0h+var_B60], xmm0
0x180040347  movups  xmm0, xmmword ptr [rdi+20h]
0x18004034b  movups  [rsp+0BC0h+var_B48], xmm0
0x180040350  test    cl, cl
0x180040352  jnz     short loc_18004037A
0x180040354  movzx   eax, word ptr [rdi+44h]
0x180040358  movups  xmm0, xmmword ptr [rdi+48h]
0x18004035c  mov     word ptr [rbp+0AC0h+var_B24], ax
0x180040360  mov     al, [rdi+46h]
0x180040363  movups  xmm1, xmmword ptr [rdi+58h]
0x180040367  mov     byte ptr [rbp+0AC0h+var_B24+2], al
0x18004036a  mov     al, [rdi+47h]
0x18004036d  mov     byte ptr [rbp+0AC0h+var_B24+3], al
0x180040370  movaps  [rbp+0AC0h+var_B24+4], xmm0
0x180040374  movaps  [rbp+0AC0h+var_B10], xmm1
0x180040378  jmp     short loc_18004038A
0x18004037a  movups  xmm0, xmmword ptr [rdi+44h]
0x18004037e  movups  xmm1, xmmword ptr [rdi+54h]
0x180040382  movups  [rbp+0AC0h+var_B24], xmm0
0x180040386  movups  xmmword ptr [rbp-54h], xmm1
0x18004038a  mov     ecx, [rdi+6Ch]
0x18004038d  mov     esi, 100h
0x180040392  mov     [rbp+0AC0h+var_AFC], ecx
0x180040395  test    ecx, ecx
0x180040397  jz      short loc_1800403AF
0x180040399  cmp     ecx, esi
0x18004039b  lea     rdx, [rdi+70h]; Src
0x18004039f  mov     r8d, esi
0x1800403a2  cmovb   r8d, ecx; Size
0x1800403a6  lea     rcx, [rbp+0AC0h+var_AF8]; void *
0x1800403aa  call    memcpy_0
0x1800403af  mov     rax, [rbx]
0x1800403b2  movups  xmm0, xmmword ptr [rbx+8]
0x1800403b6  mov     cl, [rbx+40h]
0x1800403b9  movsd   xmm1, qword ptr [rbx+30h]
0x1800403be  mov     [rbp+0AC0h+var_9F8], rax
0x1800403c5  mov     rax, [rbx+18h]
0x1800403c9  mov     [rbp+0AC0h+var_9E0], rax
0x1800403d0  mov     eax, [rbx+3Ch]
0x1800403d3  mov     [rbp+0AC0h+var_9BC], eax
0x1800403d9  mov     eax, [rbx+68h]
0x1800403dc  mov     [rbp+0AC0h+var_990], eax
0x1800403e2  mov     eax, [rbx+38h]
0x1800403e5  mov     [rbp+0AC0h+var_9C0], eax
0x1800403eb  movzx   eax, word ptr [rbx+42h]
0x1800403ef  mov     [rbp+0AC0h+var_9B6], ax
0x1800403f6  movsd   [rbp+0AC0h+var_9C8], xmm1
0x1800403fe  mov     [rbp+0AC0h+var_9B8], cl
0x180040404  movdqu  [rbp+0AC0h+var_9F0], xmm0
0x18004040c  movups  xmm0, xmmword ptr [rbx+20h]
0x180040410  movups  [rbp+0AC0h+var_9D8], xmm0
0x180040417  test    cl, cl
0x180040419  jnz     short loc_180040450
0x18004041b  movzx   eax, word ptr [rbx+44h]
0x18004041f  movups  xmm0, xmmword ptr [rbx+48h]
0x180040423  mov     word ptr [rbp+0AC0h+var_9B4], ax
0x18004042a  mov     al, [rbx+46h]
0x18004042d  movups  xmm1, xmmword ptr [rbx+58h]
0x180040431  mov     byte ptr [rbp+0AC0h+var_9B4+2], al
0x180040437  mov     al, [rbx+47h]
0x18004043a  mov     byte ptr [rbp+0AC0h+var_9B4+3], al
0x180040440  movaps  [rbp+0AC0h+var_9B4+4], xmm0
0x180040447  movaps  [rbp+0AC0h+var_9A0], xmm1
0x18004044e  jmp     short loc_180040466
0x180040450  movups  xmm0, xmmword ptr [rbx+44h]
0x180040454  movups  xmm1, xmmword ptr [rbx+54h]
0x180040458  movups  [rbp+0AC0h+var_9B4], xmm0
0x18004045f  movups  xmmword ptr [rbp+11Ch], xmm1
0x180040466  mov     eax, [rbx+6Ch]
0x180040469  mov     [rbp+0AC0h+var_98C], eax
0x18004046f  test    eax, eax
0x180040471  jz      short loc_18004048B
0x180040473  cmp     eax, esi
0x180040475  lea     rdx, [rbx+70h]; Src
0x180040479  lea     rcx, [rbp+0AC0h+var_988]; void *
0x180040480  cmovb   esi, eax
0x180040483  mov     r8d, esi; Size
0x180040486  call    memcpy_0
0x18004048b  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180040492  lea     rax, [rsp+0BC0h+BytesReturned]
0x180040497  mov     [rsp+0BC0h+lpOverlapped], r12; lpOverlapped
0x18004049c  lea     r8, [rsp+0BC0h+OutBuffer]; lpInBuffer
0x1800404a1  mov     [rsp+0BC0h+lpBytesReturned], rax; lpBytesReturned
0x1800404a6  mov     r9d, 2E8h; nInBufferSize
0x1800404ac  lea     rax, [rsp+0BC0h+OutBuffer]
0x1800404b1  mov     [rsp+0BC0h+nOutBufferSize], 2E8h; nOutBufferSize
0x1800404b9  mov     edx, 120040h; dwIoControlCode
0x1800404be  mov     [rsp+0BC0h+lpOutBuffer], rax; lpOutBuffer
0x1800404c3  call    cs:__imp_DeviceIoControl
0x1800404ca  nop     dword ptr [rax+rax+00h]
0x1800404cf  test    eax, eax
0x1800404d1  jnz     loc_180040560
0x1800404d7  call    cs:__imp_GetLastError
0x1800404de  nop     dword ptr [rax+rax+00h]
0x1800404e3  test    cs:byte_1800CF404, 8
0x1800404ea  mov     r14d, eax
0x1800404ed  jz      short loc_180040560
0x1800404ef  mov     edx, [r15+60h]
0x1800404f3  lea     rcx, [rbp+0AC0h+var_870]
0x1800404fa  mov     word ptr [rbp+0AC0h+var_840], r12w
0x180040502  mov     word ptr [rbp+0AC0h+var_870], r12w
0x18004050a  call    ConvertPortNoToString
0x18004050f  mov     r8d, r14d
0x180040512  lea     rdx, aIoctlNdiswanSe_0; "IOCTL_NDISWAN_SET_COMPRESSION_INFO fail"...
0x180040519  lea     rcx, [rbp+0AC0h+var_840]
0x180040520  call    FormatRRASErrorString
0x180040525  test    cs:byte_1800CF404, 8
0x18004052c  jz      short loc_180040560
0x18004052e  lea     rax, [rbp+0AC0h+var_870]
0x180040535  mov     qword ptr [rsp+0BC0h+nOutBufferSize], rax
0x18004053a  lea     r9, [rbp+0AC0h+var_880]
0x180040541  lea     r8, [rbp+0AC0h+var_840]
0x180040548  mov     [rsp+0BC0h+lpOutBuffer], r12
0x18004054d  lea     rdx, RasDdmParamTraceError
0x180040554  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004055b  call    McTemplateU0zjzz_EventWriteTransfer
0x180040560  mov     eax, r14d
0x180040563  mov     rcx, [rbp+0AC0h+var_40]
0x18004056a  xor     rcx, rsp; StackCookie
0x18004056d  call    __security_check_cookie
0x180040572  add     rsp, 0B90h
0x180040579  pop     r15
0x18004057b  pop     r14
0x18004057d  pop     r12
0x18004057f  pop     rdi
0x180040580  pop     rsi
0x180040581  pop     rbx
0x180040582  pop     rbp
0x180040583  retn
```
