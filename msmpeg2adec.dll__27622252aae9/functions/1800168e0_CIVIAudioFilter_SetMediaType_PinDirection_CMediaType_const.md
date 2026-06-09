# CIVIAudioFilter::SetMediaType(_PinDirection,CMediaType const *)

- ea: `0x1800168e0`
- end: `0x180016eec`
- name: `?SetMediaType@CIVIAudioFilter@@MEAAJW4_PinDirection@@PEBVCMediaType@@@Z`
- size: `1548`
- prototype: `int(CIVIAudioFilter *__hidden this, enum _PinDirection, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011860`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x180010c10`
- `0x1800168e0`
- `0x180029ec8`
- `0x180033bf0`
- `0x180036c60`
- `0x1800886f0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016e21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016eb6`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::SetMediaType(
        CIVIAudioFilter *this,
        enum _PinDirection a2,
        const struct CMediaType *a3)
{
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  int v7; // r15d
  __int64 v8; // rcx
  int v9; // eax
  __int16 v10; // dx
  int v11; // edx
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rdx
  int v15; // ecx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  struct _AMMediaType *v20; // r14
  unsigned int v21; // edi
  __int128 Buf2; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v25[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  _BYTE v31[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+B0h] [rbp-50h]

  if ( a2 == PINDIR_INPUT )
  {
    v5 = *(_OWORD *)a3;
    v6 = *((_OWORD *)a3 + 1);
    *((_DWORD *)this + 4307) = 0;
    *((_DWORD *)this + 4291) = 0;
    v7 = 0;
    *((_DWORD *)this + 60) = 1;
    Buf1 = v5;
    Buf2 = v6;
    if ( !memcmp_0(&Buf1, &MEDIATYPE_DVD_ENCRYPTED_PACK, 0x10u) )
    {
      *((_DWORD *)this + 132) = 1;
    }
    else if ( !memcmp_0(&Buf1, &MEDIATYPE_MPEG2_PES, 0x10u) )
    {
      *((_DWORD *)this + 132) = 2;
    }
    else if ( !memcmp_0(&Buf1, &MEDIATYPE_Audio, 0x10u) )
    {
      *((_DWORD *)this + 132) = 3;
    }
    else if ( !memcmp_0(&Buf1, &MEDIATYPE_Stream, 0x10u) )
    {
      *((_DWORD *)this + 132) = 3;
    }
    else
    {
      *((_DWORD *)this + 132) = 0;
    }
    if ( !memcmp_0(&Buf2, &MEDIASUBTYPE_DTS, 0x10u) || !memcmp_0(&Buf2, MEDIASUBTYPE_DTS2, 0x10u) )
    {
      *((_DWORD *)this + 1613) = 6;
    }
    else if ( !memcmp_0(&Buf2, &MEDIASUBTYPE_DVD_LPCM_AUDIO, 0x10u) )
    {
      *((_DWORD *)this + 1613) = 5;
      *((_DWORD *)this + 4291) = 1;
      *(_QWORD *)((char *)this + 6140) = 2;
      *((_DWORD *)this + 1537) = 0;
      if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_WaveFormatEx.Data1
        && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_WaveFormatEx.Data4 )
      {
        v8 = *((_QWORD *)a3 + 10);
        if ( v8 )
        {
          if ( *((_DWORD *)a3 + 18) >= 0x12u )
          {
            v9 = *(_DWORD *)(v8 + 4);
            if ( v9 == 48000 || v9 == 96000 )
            {
              v10 = *(_WORD *)(v8 + 14);
              if ( ((v10 - 16) & 0xFFF3) == 0 && v10 != 28 )
              {
                v11 = *(unsigned __int16 *)(v8 + 2);
                if ( (unsigned __int16)(v11 - 1) <= 7u )
                {
                  *((_DWORD *)this + 1535) = v11;
                  *((_DWORD *)this + 1536) = (*(unsigned __int16 *)(v8 + 14) >> 2) & 3;
                  *((_DWORD *)this + 1537) = (*(_DWORD *)(v8 + 4) & 0x80) == 0;
                }
              }
            }
          }
        }
      }
    }
    else if ( !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG2_AUDIO, 0x10u)
           || !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG1Payload, 0x10u)
           || !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG1AudioPayload, 0x10u)
           || !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG1Audio, 0x10u) )
    {
      *((_DWORD *)this + 1613) = 4;
      *((_DWORD *)this + 4291) = 1;
    }
    else if ( !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG_ADTS_AAC, 0x10u)
           || !memcmp_0(&Buf2, MEDIASUBTYPE_RAW_AAC1, 0x10u)
           || !memcmp_0(&Buf2, &MEDIASUBTYPE_MPEG_LOAS, 0x10u) )
    {
      if ( !(unsigned int)IsLicensedComponentAAC_Internal() )
      {
        *((_DWORD *)this + 4307) = 1;
        v12 = *((_QWORD *)this + 13);
        if ( v12 )
          (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v12 + 24LL))(v12, 7, 0, 0);
      }
      *((_DWORD *)this + 1613) = 9;
      *((_DWORD *)this + 132) = 4;
      if ( !memcmp_0(MEDIASUBTYPE_RAW_AAC1, &Buf2, 0x10u) )
      {
        *((_QWORD *)this + 825) = 0;
        v25[1] = 0;
        if ( *(_QWORD *)&FORMAT_WaveFormatEx.Data1 != *(_QWORD *)((char *)a3 + 44) )
          return 2147746346LL;
        if ( *(_QWORD *)FORMAT_WaveFormatEx.Data4 != *(_QWORD *)((char *)a3 + 52) )
          return 2147746346LL;
        v13 = *((_QWORD *)a3 + 10);
        if ( !v13 )
          return 2147746346LL;
        if ( *(_WORD *)v13 != 255 )
          return 2147746346LL;
        v14 = *(unsigned __int16 *)(v13 + 16);
        if ( (unsigned int)v14 < 2 )
          return 2147746346LL;
        if ( *(_DWORD *)(v13 + 4) > 0xBB80u )
          return 2147746346LL;
        if ( *(_WORD *)(v13 + 2) > 6u )
          return 2147746346LL;
        v30 = 0;
        v28 = v13 + 18;
        v29 = v13 + 18 + v14;
        v26 = v29;
        v27 = v13 + 18;
        v23 = 8 * v14;
        v25[0] = 0;
        memset_0(v31, 0, 0x114u);
        if ( (unsigned int)AudioSpecificConfig(v25, v31, &v23) || v33 > 6 || v32 > 0xBB80 )
          return 2147746346LL;
        v15 = *(_DWORD *)(v13 + 4);
        if ( v15 != v32 )
        {
          if ( v15 != 2 * v32 )
            return 2147746346LL;
          v7 = 1;
        }
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_MPEG_ADTS_AAC, &Buf2, 0x10u) )
      {
        *((_QWORD *)this + 825) = 1;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_MPEG_LOAS, &Buf2, 0x10u) )
      {
        *((_DWORD *)this + 1650) = 0;
        *((_DWORD *)this + 1651) = 1;
      }
    }
    else
    {
      *((_DWORD *)this + 1613) = 0;
    }
    *((_DWORD *)this + 1615) = 0;
    if ( *(_QWORD *)((char *)a3 + 44) != *(_QWORD *)&FORMAT_WaveFormatEx.Data1
      || *(_QWORD *)((char *)a3 + 52) != *(_QWORD *)FORMAT_WaveFormatEx.Data4
      || (v16 = *((_QWORD *)a3 + 10)) == 0
      || (v17 = *(_DWORD *)(v16 + 4), (*((_DWORD *)this + 1615) = v17) == 0) )
    {
      *((_DWORD *)this + 1615) = 48000;
    }
    if ( a3 != (CIVIAudioFilter *)((char *)this + 352) )
    {
      if ( *((_DWORD *)this + 106) )
      {
        CoTaskMemFree(*((LPVOID *)this + 54));
        *((_DWORD *)this + 106) = 0;
        *((_QWORD *)this + 54) = 0;
      }
      *((_QWORD *)this + 52) = 0;
      CopyMediaType((struct _AMMediaType *)this + 4, (const struct _AMMediaType *)a3);
    }
    if ( v7 )
    {
      v18 = *((_QWORD *)this + 54);
      if ( !v18 )
        return 2147746346LL;
      *(_DWORD *)(v18 + 4) >>= 1;
    }
    if ( *((_QWORD *)this + 830) )
      AACAudioDecoderClose((char *)this + 6640);
    return 0;
  }
  if ( a2 != PINDIR_OUTPUT )
    return 0;
  v20 = (struct _AMMediaType *)((char *)this + 440);
  v21 = 0;
  if ( a3 != (CIVIAudioFilter *)((char *)this + 440) )
  {
    if ( *((_DWORD *)this + 128) )
    {
      CoTaskMemFree(*((LPVOID *)this + 65));
      v20->cbFormat = 0;
      v20->pbFormat = 0;
    }
    v20->pUnk = 0;
    CopyMediaType(v20, (const struct _AMMediaType *)a3);
  }
  if ( !*((_QWORD *)this + 65) )
    return (unsigned int)-2147024882;
  return v21;
}

```

## disassembly

```asm
0x1800168e0  mov     [rsp-8+arg_8], rbx
0x1800168e5  push    rbp
0x1800168e6  push    rsi
0x1800168e7  push    rdi
0x1800168e8  push    r14
0x1800168ea  push    r15
0x1800168ec  lea     rbp, [rsp-0C0h]
0x1800168f4  sub     rsp, 1C0h
0x1800168fb  mov     rax, cs:__security_cookie
0x180016902  xor     rax, rsp
0x180016905  mov     [rbp+0E0h+var_30], rax
0x18001690c  mov     rsi, r8
0x18001690f  mov     rbx, rcx
0x180016912  test    edx, edx
0x180016914  jnz     loc_180016E99
0x18001691a  movups  xmm0, xmmword ptr [r8]
0x18001691e  xor     edi, edi
0x180016920  lea     rdx, MEDIATYPE_DVD_ENCRYPTED_PACK; Buf2
0x180016927  movups  xmm1, xmmword ptr [r8+10h]
0x18001692c  mov     [rcx+434Ch], edi
0x180016932  mov     r8d, 10h; Size
0x180016938  mov     [rcx+430Ch], edi
0x18001693e  mov     r15d, edi
0x180016941  mov     dword ptr [rcx+0F0h], 1
0x18001694b  lea     rcx, [rsp+1E0h+Buf1]; Buf1
0x180016950  movups  [rsp+1E0h+Buf1], xmm0
0x180016955  movups  [rsp+1E0h+Buf2], xmm1
0x18001695a  call    memcmp_0
0x18001695f  test    eax, eax
0x180016961  jnz     short loc_18001696F
0x180016963  mov     dword ptr [rbx+210h], 1
0x18001696d  jmp     short loc_1800169EA
0x18001696f  mov     r8d, 10h; Size
0x180016975  lea     rdx, MEDIATYPE_MPEG2_PES; Buf2
0x18001697c  lea     rcx, [rsp+1E0h+Buf1]; Buf1
0x180016981  call    memcmp_0
0x180016986  test    eax, eax
0x180016988  jnz     short loc_180016996
0x18001698a  mov     dword ptr [rbx+210h], 2
0x180016994  jmp     short loc_1800169EA
0x180016996  mov     r8d, 10h; Size
0x18001699c  lea     rdx, MEDIATYPE_Audio; Buf2
0x1800169a3  lea     rcx, [rsp+1E0h+Buf1]; Buf1
0x1800169a8  call    memcmp_0
0x1800169ad  test    eax, eax
0x1800169af  jnz     short loc_1800169BD
0x1800169b1  mov     dword ptr [rbx+210h], 3
0x1800169bb  jmp     short loc_1800169EA
0x1800169bd  mov     r8d, 10h; Size
0x1800169c3  lea     rdx, MEDIATYPE_Stream; Buf2
0x1800169ca  lea     rcx, [rsp+1E0h+Buf1]; Buf1
0x1800169cf  call    memcmp_0
0x1800169d4  test    eax, eax
0x1800169d6  jnz     short loc_1800169E4
0x1800169d8  mov     dword ptr [rbx+210h], 3
0x1800169e2  jmp     short loc_1800169EA
0x1800169e4  mov     [rbx+210h], edi
0x1800169ea  mov     r8d, 10h; Size
0x1800169f0  lea     rdx, MEDIASUBTYPE_DTS; Buf2
0x1800169f7  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x1800169fc  call    memcmp_0
0x180016a01  test    eax, eax
0x180016a03  jz      loc_180016DC1
0x180016a09  mov     r8d, 10h; Size
0x180016a0f  lea     rdx, MEDIASUBTYPE_DTS2; Buf2
0x180016a16  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016a1b  call    memcmp_0
0x180016a20  test    eax, eax
0x180016a22  jz      loc_180016DC1
0x180016a28  mov     r8d, 10h; Size
0x180016a2e  lea     rdx, MEDIASUBTYPE_DVD_LPCM_AUDIO; Buf2
0x180016a35  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016a3a  call    memcmp_0
0x180016a3f  test    eax, eax
0x180016a41  jnz     loc_180016B18
0x180016a47  mov     dword ptr [rbx+1934h], 5
0x180016a51  mov     dword ptr [rbx+430Ch], 1
0x180016a5b  mov     qword ptr [rbx+17FCh], 2
0x180016a66  mov     [rbx+1804h], edi
0x180016a6c  mov     rax, [rsi+2Ch]
0x180016a70  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x180016a77  jnz     loc_180016DCB
0x180016a7d  mov     rax, [rsi+34h]
0x180016a81  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x180016a88  jnz     loc_180016DCB
0x180016a8e  mov     rcx, [rsi+50h]
0x180016a92  test    rcx, rcx
0x180016a95  jz      loc_180016DCB
0x180016a9b  cmp     dword ptr [rsi+48h], 12h
0x180016a9f  jb      loc_180016DCB
0x180016aa5  mov     eax, [rcx+4]
0x180016aa8  cmp     eax, 0BB80h
0x180016aad  jz      short loc_180016ABA
0x180016aaf  cmp     eax, 17700h
0x180016ab4  jnz     loc_180016DCB
0x180016aba  movzx   edx, word ptr [rcx+0Eh]
0x180016abe  mov     r8d, 0FFF3h
0x180016ac4  lea     eax, [rdx-10h]
0x180016ac7  test    r8w, ax
0x180016acb  jnz     loc_180016DCB
0x180016ad1  cmp     dx, 1Ch
0x180016ad5  jz      loc_180016DCB
0x180016adb  movzx   edx, word ptr [rcx+2]
0x180016adf  lea     eax, [rdx-1]
0x180016ae2  cmp     ax, 7
0x180016ae6  ja      loc_180016DCB
0x180016aec  mov     [rbx+17FCh], edx
0x180016af2  movzx   eax, word ptr [rcx+0Eh]
0x180016af6  shr     eax, 2
0x180016af9  and     eax, 3
0x180016afc  mov     [rbx+1800h], eax
0x180016b02  mov     eax, [rcx+4]
0x180016b05  shr     eax, 7
0x180016b08  not     eax
0x180016b0a  and     eax, 1
0x180016b0d  mov     [rbx+1804h], eax
0x180016b13  jmp     loc_180016DCB
0x180016b18  mov     r8d, 10h; Size
0x180016b1e  lea     rdx, MEDIASUBTYPE_MPEG2_AUDIO; Buf2
0x180016b25  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016b2a  call    memcmp_0
0x180016b2f  test    eax, eax
0x180016b31  jz      loc_180016DAB
0x180016b37  mov     r8d, 10h; Size
0x180016b3d  lea     rdx, MEDIASUBTYPE_MPEG1Payload; Buf2
0x180016b44  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016b49  call    memcmp_0
0x180016b4e  test    eax, eax
0x180016b50  jz      loc_180016DAB
0x180016b56  mov     r8d, 10h; Size
0x180016b5c  lea     rdx, MEDIASUBTYPE_MPEG1AudioPayload; Buf2
0x180016b63  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016b68  call    memcmp_0
0x180016b6d  test    eax, eax
0x180016b6f  jz      loc_180016DAB
0x180016b75  mov     r8d, 10h; Size
0x180016b7b  lea     rdx, MEDIASUBTYPE_MPEG1Audio; Buf2
0x180016b82  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016b87  call    memcmp_0
0x180016b8c  test    eax, eax
0x180016b8e  jz      loc_180016DAB
0x180016b94  mov     r8d, 10h; Size
0x180016b9a  lea     rdx, MEDIASUBTYPE_MPEG_ADTS_AAC; Buf2
0x180016ba1  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016ba6  call    memcmp_0
0x180016bab  test    eax, eax
0x180016bad  jz      short loc_180016BF0
0x180016baf  mov     r8d, 10h; Size
0x180016bb5  lea     rdx, MEDIASUBTYPE_RAW_AAC1; Buf2
0x180016bbc  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016bc1  call    memcmp_0
0x180016bc6  test    eax, eax
0x180016bc8  jz      short loc_180016BF0
0x180016bca  mov     r8d, 10h; Size
0x180016bd0  lea     rdx, MEDIASUBTYPE_MPEG_LOAS; Buf2
0x180016bd7  lea     rcx, [rsp+1E0h+Buf2]; Buf1
0x180016bdc  call    memcmp_0
0x180016be1  test    eax, eax
0x180016be3  jz      short loc_180016BF0
0x180016be5  mov     [rbx+1934h], edi
0x180016beb  jmp     loc_180016DCB
0x180016bf0  call    ?IsLicensedComponentAAC_Internal@@YAHXZ; IsLicensedComponentAAC_Internal(void)
0x180016bf5  test    eax, eax
0x180016bf7  jnz     short loc_180016C24
0x180016bf9  mov     dword ptr [rbx+434Ch], 1
0x180016c03  mov     rcx, [rbx+68h]
0x180016c07  test    rcx, rcx
0x180016c0a  jz      short loc_180016C24
0x180016c0c  mov     rax, [rcx]
0x180016c0f  xor     r9d, r9d
0x180016c12  xor     r8d, r8d
0x180016c15  mov     edx, 7
0x180016c1a  mov     rax, [rax+18h]
0x180016c1e  call    cs:__guard_dispatch_icall_fptr
0x180016c24  mov     r8d, 10h; Size
0x180016c2a  mov     dword ptr [rbx+1934h], 9
0x180016c34  lea     rdx, [rsp+1E0h+Buf2]; Buf2
0x180016c39  mov     dword ptr [rbx+210h], 4
0x180016c43  lea     rcx, MEDIASUBTYPE_RAW_AAC1; Buf1
0x180016c4a  call    memcmp_0
0x180016c4f  test    eax, eax
0x180016c51  jnz     loc_180016D56
0x180016c57  mov     [rbx+19C8h], rdi
0x180016c5e  mov     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x180016c65  mov     [rsp+1E0h+var_184], edi
0x180016c69  cmp     rax, [rsi+2Ch]
0x180016c6d  jnz     loc_180016E55
0x180016c73  mov     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x180016c7a  cmp     rax, [rsi+34h]
0x180016c7e  jnz     loc_180016E55
0x180016c84  mov     r14, [rsi+50h]
0x180016c88  test    r14, r14
0x180016c8b  jz      loc_180016E55
0x180016c91  mov     eax, 0FFh
0x180016c96  cmp     [r14], ax
0x180016c9a  jnz     loc_180016E55
0x180016ca0  movzx   edx, word ptr [r14+10h]
0x180016ca5  cmp     edx, 2
0x180016ca8  jb      loc_180016E55
0x180016cae  cmp     dword ptr [r14+4], 0BB80h
0x180016cb6  ja      loc_180016E55
0x180016cbc  cmp     word ptr [r14+2], 6
0x180016cc2  ja      loc_180016E55
0x180016cc8  lea     rcx, [r14+12h]
0x180016ccc  mov     [rbp+0E0h+var_160], rdi
0x180016cd0  mov     eax, edx
0x180016cd2  mov     [rsp+1E0h+var_170], rcx
0x180016cd7  add     rdx, rcx
0x180016cda  shl     eax, 3
0x180016cdd  mov     [rsp+1E0h+var_168], rdx
0x180016ce2  mov     r8d, 114h; Size
0x180016ce8  mov     [rsp+1E0h+var_180], rdx
0x180016ced  xor     edx, edx; Val
0x180016cef  mov     [rsp+1E0h+var_178], rcx
0x180016cf4  lea     rcx, [rbp+0E0h+var_150]; void *
0x180016cf8  mov     [rsp+1E0h+var_1A0], eax
0x180016cfc  mov     [rsp+1E0h+var_188], edi
0x180016d00  call    memset_0
0x180016d05  lea     r8, [rsp+1E0h+var_1A0]
0x180016d0a  lea     rdx, [rbp+0E0h+var_150]
0x180016d0e  lea     rcx, [rsp+1E0h+var_188]
0x180016d13  call    AudioSpecificConfig
0x180016d18  test    eax, eax
0x180016d1a  jnz     loc_180016E55
0x180016d20  cmp     [rbp+0E0h+var_130], 6
0x180016d24  jg      loc_180016E55
0x180016d2a  mov     eax, [rbp+0E0h+var_148]
0x180016d2d  cmp     eax, 0BB80h
0x180016d32  ja      loc_180016E55
0x180016d38  mov     ecx, [r14+4]
0x180016d3c  cmp     ecx, eax
0x180016d3e  jz      loc_180016DCB
0x180016d44  add     eax, eax
0x180016d46  cmp     ecx, eax
0x180016d48  jnz     loc_180016E55
0x180016d4e  mov     r15d, 1
0x180016d54  jmp     short loc_180016DCB
0x180016d56  mov     r8d, 10h; Size
0x180016d5c  lea     rdx, [rsp+1E0h+Buf2]; Buf2
0x180016d61  lea     rcx, MEDIASUBTYPE_MPEG_ADTS_AAC; Buf1
0x180016d68  call    memcmp_0
0x180016d6d  test    eax, eax
0x180016d6f  jnz     short loc_180016D7E
0x180016d71  mov     qword ptr [rbx+19C8h], 1
0x180016d7c  jmp     short loc_180016DCB
0x180016d7e  mov     r8d, 10h; Size
0x180016d84  lea     rdx, [rsp+1E0h+Buf2]; Buf2
0x180016d89  lea     rcx, MEDIASUBTYPE_MPEG_LOAS; Buf1
0x180016d90  call    memcmp_0
0x180016d95  test    eax, eax
0x180016d97  jnz     short loc_180016DCB
0x180016d99  mov     [rbx+19C8h], edi
0x180016d9f  mov     dword ptr [rbx+19CCh], 1
0x180016da9  jmp     short loc_180016DCB
0x180016dab  mov     dword ptr [rbx+1934h], 4
0x180016db5  mov     dword ptr [rbx+430Ch], 1
0x180016dbf  jmp     short loc_180016DCB
0x180016dc1  mov     dword ptr [rbx+1934h], 6
0x180016dcb  mov     [rbx+193Ch], edi
0x180016dd1  mov     rax, [rsi+2Ch]
0x180016dd5  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x180016ddc  jnz     short loc_180016E01
0x180016dde  mov     rax, [rsi+34h]
0x180016de2  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x180016de9  jnz     short loc_180016E01
0x180016deb  mov     rax, [rsi+50h]
0x180016def  test    rax, rax
0x180016df2  jz      short loc_180016E01
0x180016df4  mov     eax, [rax+4]
0x180016df7  mov     [rbx+193Ch], eax
0x180016dfd  test    eax, eax
0x180016dff  jnz     short loc_180016E0B
0x180016e01  mov     dword ptr [rbx+193Ch], 0BB80h
0x180016e0b  lea     r14, [rbx+160h]
0x180016e12  cmp     rsi, r14
0x180016e15  jz      short loc_180016E44
0x180016e17  cmp     [r14+48h], edi
0x180016e1b  jz      short loc_180016E35
0x180016e1d  mov     rcx, [r14+50h]; pv
0x180016e21  call    cs:__imp_CoTaskMemFree
0x180016e28  nop     dword ptr [rax+rax+00h]
0x180016e2d  mov     [r14+48h], edi
0x180016e31  mov     [r14+50h], rdi
0x180016e35  mov     rdx, rsi; struct _AMMediaType *
0x180016e38  mov     [r14+40h], rdi
0x180016e3c  mov     rcx, r14; struct _AMMediaType *
0x180016e3f  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180016e44  test    r15d, r15d
0x180016e47  jz      short loc_180016E5F
0x180016e49  mov     rax, [rbx+1B0h]
0x180016e50  test    rax, rax
0x180016e53  jnz     short loc_180016E5C
0x180016e55  mov     eax, 8004022Ah
0x180016e5a  jmp     short loc_180016E72
0x180016e5c  shr     dword ptr [rax+4], 1
0x180016e5f  lea     rcx, [rbx+19F0h]
0x180016e66  cmp     [rcx], rdi
0x180016e69  jz      short loc_180016E70
0x180016e6b  call    AACAudioDecoderClose
0x180016e70  xor     eax, eax
  ... truncated ...
```
