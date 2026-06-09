# DdmDevice::RaiseProtocolFailureEvent(_PROTOCOL_SRV_FAILURE *)

- ea: `0x1800398c0`
- end: `0x180039deb`
- name: `?RaiseProtocolFailureEvent@DdmDevice@@UEAAXPEAU_PROTOCOL_SRV_FAILURE@@@Z`
- size: `1323`
- prototype: `void __fastcall(DdmDevice *__hidden this, struct _PROTOCOL_SRV_FAILURE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x18000ace4`
- `0x180019c88`
- `0x1800398c0`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180039a09`
- `KERNEL32!MultiByteToWideChar` at `0x180039afc`
- `KERNEL32!MultiByteToWideChar` at `0x180039b65`
- `KERNEL32!MultiByteToWideChar` at `0x180039c35`
- `KERNEL32!MultiByteToWideChar` at `0x180039c78`
- `KERNEL32!MultiByteToWideChar` at `0x180039cc2`
- `KERNEL32!MultiByteToWideChar` at `0x180039d0e`
- `KERNEL32!MultiByteToWideChar` at `0x180039a09`
- `KERNEL32!MultiByteToWideChar` at `0x180039afc`
- `KERNEL32!MultiByteToWideChar` at `0x180039b65`
- `KERNEL32!MultiByteToWideChar` at `0x180039c35`
- `KERNEL32!MultiByteToWideChar` at `0x180039c78`
- `KERNEL32!MultiByteToWideChar` at `0x180039cc2`
- `KERNEL32!MultiByteToWideChar` at `0x180039d0e`
- `rtutils!RouterLogEventW` at `0x180039acb`
- `rtutils!RouterLogEventW` at `0x180039acb`
- `rtutils!RouterLogEventStringW` at `0x180039db4`
- `rtutils!RouterLogEventStringW` at `0x180039db4`

## string_xrefs

- `0x180039977`: `DdmDevice::RaiseProtocolFailureEvent: Entered, hPort=%d, Error=%d`

## pseudocode

```c
void __fastcall DdmDevice::RaiseProtocolFailureEvent(const wchar_t *this, const CHAR *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  LPWSTR v6; // r11
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  DWORD v12; // r9d
  DWORD v13; // r8d
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  WCHAR *v18; // r8
  const wchar_t *v19; // r8
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h]
  char *v23; // [rsp+68h] [rbp-98h]
  WCHAR pszSrc[16]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+94h] [rbp-6Ch]
  __int128 v27; // [rsp+A4h] [rbp-5Ch]
  int v28; // [rsp+B4h] [rbp-4Ch]
  WCHAR WideCharStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  int v30; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v31[2044]; // [rsp+2E4h] [rbp+1E4h] BYREF

  v23 = 0;
  v22 = 0;
  v30 = 0;
  memset_0(v31, 0, sizeof(v31));
  v25 = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v20 = 0;
  if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v30) = 0;
    LOWORD(v25) = 0;
    if ( this )
      v4 = *((unsigned int *)this + 24);
    else
      v4 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v25, v4);
    v5 = (__int64)(this + 48);
    if ( !this )
      v5 = 96;
    FormatRRASErrorString(
      &v30,
      L"DdmDevice::RaiseProtocolFailureEvent: Entered, hPort=%d, Error=%d",
      *(_QWORD *)v5,
      *(unsigned int *)a2);
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v30,
        (unsigned int)&v20,
        0,
        (__int64)&v25);
  }
  (*(void (__fastcall **)(const wchar_t *, _QWORD))(*(_QWORD *)this + 80LL))(this, *(unsigned int *)a2);
  if ( a2[4] )
  {
    MultiByteToWideChar(0, 0, a2 + 4, -1, WideCharStr, 257);
    v6 = gblpszUnknown;
  }
  else
  {
    StringCbCopyW(WideCharStr, 0x220u, gblpszUnknown);
  }
  plpszSubStringArray = (LPWSTR)(this + 546);
  v7 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 <= 0x2C4u )
  {
    if ( v7 != 708 )
    {
      v8 = v7 - 71;
      if ( v8 )
      {
        v9 = v8 - 535;
        if ( !v9 )
          return;
        v10 = v9 - 42;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 == 42 )
            {
              *(_QWORD *)&v22 = WideCharStr;
              *((_QWORD *)&v22 + 1) = this + 357;
              if ( (unsigned int)dword_1800CF4E4 <= 1 )
                return;
              v12 = 3;
              v13 = 20249;
              goto LABEL_21;
            }
            goto LABEL_33;
          }
          MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
          *(_QWORD *)&v22 = pszSrc;
          *((_QWORD *)&v22 + 1) = WideCharStr;
          v23 = (char *)(this + 357);
          if ( (unsigned int)dword_1800CF4E4 <= 1 )
            return;
          v12 = 4;
          v13 = 20258;
        }
        else
        {
          MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
          *(_QWORD *)&v22 = pszSrc;
          *((_QWORD *)&v22 + 1) = WideCharStr;
          v23 = (char *)(this + 357);
          if ( (unsigned int)dword_1800CF4E4 <= 1 )
            return;
          v12 = 4;
          v13 = 20256;
        }
      }
      else
      {
        *(_QWORD *)&v22 = this + 357;
        if ( (unsigned int)dword_1800CF4E4 <= 1 )
          return;
        v12 = 2;
        v13 = 20261;
      }
LABEL_21:
      RouterLogEventW(hLogHandle, 2u, v13, v12, &plpszSubStringArray, 0);
      return;
    }
LABEL_39:
    MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
    *(_QWORD *)&v22 = pszSrc;
    *((_QWORD *)&v22 + 1) = WideCharStr;
    v23 = (char *)(this + 357);
    if ( (unsigned int)dword_1800CF4E4 <= 1 )
      return;
    v12 = 4;
    v13 = 20257;
    goto LABEL_21;
  }
  v14 = v7 - 718;
  if ( !v14 )
    return;
  v15 = v14 - 14;
  if ( v15 )
  {
    v16 = v15 - 2;
    if ( !v16 )
      return;
    v17 = v16 - 1059;
    if ( !v17 )
      goto LABEL_39;
    if ( v17 == 457 )
      return;
  }
LABEL_33:
  if ( !a2[4] )
  {
    if ( this[84] )
    {
      if ( this[341] )
      {
        StringCbCopyW(WideCharStr, 0x220u, this + 341);
        StringCbCatW(WideCharStr, 0x220u, L"\\");
        v18 = (WCHAR *)(this + 84);
        goto LABEL_38;
      }
      v19 = this + 84;
    }
    else
    {
      v19 = v6;
    }
    StringCbCopyW(WideCharStr, 0x220u, v19);
LABEL_48:
    *(_QWORD *)&v22 = this + 357;
    *((_QWORD *)&v22 + 1) = WideCharStr;
    if ( dword_1800CF4E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4F1Fu, 3u, &plpszSubStringArray, *(_DWORD *)a2, 3u);
    return;
  }
  if ( !a2[261] )
  {
    MultiByteToWideChar(0, 0, a2 + 4, -1, WideCharStr, 257);
    goto LABEL_48;
  }
  if ( MultiByteToWideChar(0, 0, a2 + 261, -1, WideCharStr, 257) )
  {
    StringCbCatW(WideCharStr, 0x220u, L"\\");
    if ( MultiByteToWideChar(0, 0, a2 + 4, -1, pszSrc, 16) )
    {
      v18 = pszSrc;
LABEL_38:
      StringCbCatW(WideCharStr, 0x220u, v18);
      goto LABEL_48;
    }
  }
}

```

## disassembly

```asm
0x1800398c0  mov     [rsp-8+arg_10], rbx
0x1800398c5  push    rbp
0x1800398c6  push    rsi
0x1800398c7  push    rdi
0x1800398c8  push    r12
0x1800398ca  push    r13
0x1800398cc  push    r14
0x1800398ce  push    r15
0x1800398d0  lea     rbp, [rsp-9F0h]
0x1800398d8  sub     rsp, 0AF0h
0x1800398df  mov     rax, cs:__security_cookie
0x1800398e6  xor     rax, rsp
0x1800398e9  mov     [rbp+0A20h+var_40], rax
0x1800398f0  mov     rsi, rdx
0x1800398f3  mov     rbx, rcx
0x1800398f6  xorps   xmm0, xmm0
0x1800398f9  lea     rcx, [rbp+0A20h+var_83C]; void *
0x180039900  xor     r14d, r14d
0x180039903  xor     edx, edx; Val
0x180039905  mov     r8d, 7FCh; Size
0x18003990b  mov     [rsp+0B20h+var_AB8], r14
0x180039910  movdqu  [rsp+0B20h+var_AC8], xmm0
0x180039916  mov     [rbp+0A20h+var_840], r14d
0x18003991d  call    memset_0
0x180039922  xorps   xmm0, xmm0
0x180039925  mov     [rbp+0A20h+var_A90], r14d
0x180039929  xor     eax, eax
0x18003992b  test    cs:byte_1800CF404, 8
0x180039932  movups  [rbp+0A20h+var_A8C], xmm0
0x180039936  mov     [rbp+0A20h+var_A6C], eax
0x180039939  movups  [rbp+0A20h+var_A7C], xmm0
0x18003993d  movups  [rsp+0B20h+var_AE0], xmm0
0x180039942  jz      loc_1800399CA
0x180039948  mov     word ptr [rbp+0A20h+var_840], r14w
0x180039950  mov     word ptr [rbp+0A20h+var_A90], r14w
0x180039955  test    rbx, rbx
0x180039958  jz      short loc_18003995F
0x18003995a  mov     edx, [rbx+60h]
0x18003995d  jmp     short loc_180039962
0x18003995f  or      edx, 0FFFFFFFFh
0x180039962  lea     rcx, [rbp+0A20h+var_A90]
0x180039966  call    ConvertPortNoToString
0x18003996b  mov     r9d, [rsi]
0x18003996e  lea     r8, [rbx+60h]
0x180039972  mov     eax, 60h ; '`'
0x180039977  lea     rdx, aDdmdeviceRaise; "DdmDevice::RaiseProtocolFailureEvent: E"...
0x18003997e  test    rbx, rbx
0x180039981  lea     rcx, [rbp+0A20h+var_840]
0x180039988  cmovz   r8, rax
0x18003998c  mov     r8, [r8]
0x18003998f  call    FormatRRASErrorString
0x180039994  test    cs:byte_1800CF404, 8
0x18003999b  jz      short loc_1800399CA
0x18003999d  lea     rax, [rbp+0A20h+var_A90]
0x1800399a1  mov     qword ptr [rsp+0B20h+cchWideChar], rax
0x1800399a6  lea     r9, [rsp+0B20h+var_AE0]
0x1800399ab  lea     r8, [rbp+0A20h+var_840]
0x1800399b2  mov     [rsp+0B20h+lpWideCharStr], r14
0x1800399b7  lea     rdx, RasDdmParamTraceError
0x1800399be  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800399c5  call    McTemplateU0zjzz_EventWriteTransfer
0x1800399ca  mov     rax, [rbx]
0x1800399cd  mov     rcx, rbx
0x1800399d0  mov     edx, [rsi]
0x1800399d2  mov     rax, [rax+50h]
0x1800399d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800399db  lea     rdi, [rsi+4]
0x1800399df  or      r13d, 0FFFFFFFFh
0x1800399e3  mov     r12d, 220h
0x1800399e9  cmp     [rdi], r14b
0x1800399ec  jz      short loc_180039A1E
0x1800399ee  lea     rax, [rbp+0A20h+WideCharStr]
0x1800399f2  mov     [rsp+0B20h+cchWideChar], 101h; cchWideChar
0x1800399fa  mov     r9d, r13d; cbMultiByte
0x1800399fd  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039a02  mov     r8, rdi; lpMultiByteStr
0x180039a05  xor     edx, edx; dwFlags
0x180039a07  xor     ecx, ecx; CodePage
0x180039a09  call    cs:__imp_MultiByteToWideChar
0x180039a10  nop     dword ptr [rax+rax+00h]
0x180039a15  mov     r11, cs:gblpszUnknown
0x180039a1c  jmp     short loc_180039A34
0x180039a1e  mov     r11, cs:gblpszUnknown
0x180039a25  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x180039a29  mov     r8, r11; pszSrc
0x180039a2c  mov     rdx, r12; cbDest
0x180039a2f  call    StringCbCopyW
0x180039a34  lea     rax, [rbx+444h]
0x180039a3b  mov     ecx, 2C4h
0x180039a40  mov     [rsp+0B20h+plpszSubStringArray], rax
0x180039a45  mov     r15d, 2
0x180039a4b  mov     eax, [rsi]
0x180039a4d  cmp     eax, ecx
0x180039a4f  ja      loc_180039BD5
0x180039a55  jz      loc_180039CA2
0x180039a5b  sub     eax, 47h ; 'G'
0x180039a5e  jz      loc_180039BAE
0x180039a64  sub     eax, 217h
0x180039a69  jz      loc_180039DC0
0x180039a6f  sub     eax, 2Ah ; '*'
0x180039a72  jz      loc_180039B45
0x180039a78  sub     eax, 1
0x180039a7b  jz      short loc_180039ADC
0x180039a7d  cmp     eax, 2Ah ; '*'
0x180039a80  jnz     loc_180039C04
0x180039a86  cmp     cs:dword_1800CF4E4, 1
0x180039a8d  lea     rax, [rbp+0A20h+WideCharStr]
0x180039a91  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039a96  lea     rax, [rbx+2CAh]
0x180039a9d  mov     qword ptr [rsp+0B20h+var_AC8+8], rax
0x180039aa2  jbe     loc_180039DC0
0x180039aa8  lea     r9d, [r15+1]; dwSubStringCount
0x180039aac  mov     r8d, 4F19h; dwMessageId
0x180039ab2  mov     rcx, cs:hLogHandle; hLogHandle
0x180039ab9  lea     rax, [rsp+0B20h+plpszSubStringArray]
0x180039abe  mov     [rsp+0B20h+cchWideChar], r14d; dwErrorCode
0x180039ac3  mov     edx, r15d; dwEventType
0x180039ac6  mov     [rsp+0B20h+lpWideCharStr], rax; plpszSubStringArray
0x180039acb  call    cs:__imp_RouterLogEventW
0x180039ad2  nop     dword ptr [rax+rax+00h]
0x180039ad7  jmp     loc_180039DC0
0x180039adc  lea     rax, [rsp+0B20h+pszSrc]
0x180039ae1  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180039ae9  lea     r8, [rsi+105h]; lpMultiByteStr
0x180039af0  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039af5  mov     r9d, r13d; cbMultiByte
0x180039af8  xor     edx, edx; dwFlags
0x180039afa  xor     ecx, ecx; CodePage
0x180039afc  call    cs:__imp_MultiByteToWideChar
0x180039b03  nop     dword ptr [rax+rax+00h]
0x180039b08  cmp     cs:dword_1800CF4E4, 1
0x180039b0f  lea     rax, [rsp+0B20h+pszSrc]
0x180039b14  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039b19  lea     rax, [rbp+0A20h+WideCharStr]
0x180039b1d  mov     qword ptr [rsp+0B20h+var_AC8+8], rax
0x180039b22  lea     rax, [rbx+2CAh]
0x180039b29  mov     [rsp+0B20h+var_AB8], rax
0x180039b2e  jbe     loc_180039DC0
0x180039b34  mov     r9d, 4
0x180039b3a  mov     r8d, 4F22h
0x180039b40  jmp     loc_180039AB2
0x180039b45  lea     rax, [rsp+0B20h+pszSrc]
0x180039b4a  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180039b52  lea     r8, [rsi+105h]; lpMultiByteStr
0x180039b59  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039b5e  mov     r9d, r13d; cbMultiByte
0x180039b61  xor     edx, edx; dwFlags
0x180039b63  xor     ecx, ecx; CodePage
0x180039b65  call    cs:__imp_MultiByteToWideChar
0x180039b6c  nop     dword ptr [rax+rax+00h]
0x180039b71  cmp     cs:dword_1800CF4E4, 1
0x180039b78  lea     rax, [rsp+0B20h+pszSrc]
0x180039b7d  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039b82  lea     rax, [rbp+0A20h+WideCharStr]
0x180039b86  mov     qword ptr [rsp+0B20h+var_AC8+8], rax
0x180039b8b  lea     rax, [rbx+2CAh]
0x180039b92  mov     [rsp+0B20h+var_AB8], rax
0x180039b97  jbe     loc_180039DC0
0x180039b9d  mov     r9d, 4
0x180039ba3  mov     r8d, 4F20h
0x180039ba9  jmp     loc_180039AB2
0x180039bae  cmp     cs:dword_1800CF4E4, 1
0x180039bb5  lea     rax, [rbx+2CAh]
0x180039bbc  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039bc1  jbe     loc_180039DC0
0x180039bc7  mov     r9d, r15d
0x180039bca  mov     r8d, 4F25h
0x180039bd0  jmp     loc_180039AB2
0x180039bd5  sub     eax, 2CEh
0x180039bda  jz      loc_180039DC0
0x180039be0  sub     eax, 0Eh
0x180039be3  jz      short loc_180039C04
0x180039be5  sub     eax, r15d
0x180039be8  jz      loc_180039DC0
0x180039bee  sub     eax, 423h
0x180039bf3  jz      loc_180039CA2
0x180039bf9  cmp     eax, 1C9h
0x180039bfe  jz      loc_180039DC0
0x180039c04  cmp     [rdi], r14b
0x180039c07  jz      loc_180039D1C
0x180039c0d  lea     r8, [rsi+105h]; lpMultiByteStr
0x180039c14  mov     [rsp+0B20h+cchWideChar], 101h; cchWideChar
0x180039c1c  xor     edx, edx; dwFlags
0x180039c1e  lea     rax, [rbp+0A20h+WideCharStr]
0x180039c22  xor     ecx, ecx; CodePage
0x180039c24  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039c29  mov     r9d, r13d; cbMultiByte
0x180039c2c  cmp     [r8], r14b
0x180039c2f  jz      loc_180039D0B
0x180039c35  call    cs:__imp_MultiByteToWideChar
0x180039c3c  nop     dword ptr [rax+rax+00h]
0x180039c41  test    eax, eax
0x180039c43  jz      loc_180039DC0
0x180039c49  lea     r8, asc_180098AD8; "\\"
0x180039c50  mov     rdx, r12; cbDest
0x180039c53  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x180039c57  call    StringCbCatW
0x180039c5c  lea     rax, [rsp+0B20h+pszSrc]
0x180039c61  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180039c69  mov     r9d, r13d; cbMultiByte
0x180039c6c  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039c71  mov     r8, rdi; lpMultiByteStr
0x180039c74  xor     edx, edx; dwFlags
0x180039c76  xor     ecx, ecx; CodePage
0x180039c78  call    cs:__imp_MultiByteToWideChar
0x180039c7f  nop     dword ptr [rax+rax+00h]
0x180039c84  test    eax, eax
0x180039c86  jz      loc_180039DC0
0x180039c8c  lea     r8, [rsp+0B20h+pszSrc]; pszSrc
0x180039c91  mov     rdx, r12; cbDest
0x180039c94  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x180039c98  call    StringCbCatW
0x180039c9d  jmp     loc_180039D6A
0x180039ca2  lea     rax, [rsp+0B20h+pszSrc]
0x180039ca7  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180039caf  lea     r8, [rsi+105h]; lpMultiByteStr
0x180039cb6  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180039cbb  mov     r9d, r13d; cbMultiByte
0x180039cbe  xor     edx, edx; dwFlags
0x180039cc0  xor     ecx, ecx; CodePage
0x180039cc2  call    cs:__imp_MultiByteToWideChar
0x180039cc9  nop     dword ptr [rax+rax+00h]
0x180039cce  cmp     cs:dword_1800CF4E4, 1
0x180039cd5  lea     rax, [rsp+0B20h+pszSrc]
0x180039cda  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039cdf  lea     rax, [rbp+0A20h+WideCharStr]
0x180039ce3  mov     qword ptr [rsp+0B20h+var_AC8+8], rax
0x180039ce8  lea     rax, [rbx+2CAh]
0x180039cef  mov     [rsp+0B20h+var_AB8], rax
0x180039cf4  jbe     loc_180039DC0
0x180039cfa  mov     r9d, 4
0x180039d00  mov     r8d, 4F21h
0x180039d06  jmp     loc_180039AB2
0x180039d0b  mov     r8, rdi; lpMultiByteStr
0x180039d0e  call    cs:__imp_MultiByteToWideChar
0x180039d15  nop     dword ptr [rax+rax+00h]
0x180039d1a  jmp     short loc_180039D6A
0x180039d1c  lea     rdi, [rbx+0A8h]
0x180039d23  mov     rdx, r12; cbDest
0x180039d26  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x180039d2a  cmp     [rdi], r14w
0x180039d2e  jz      short loc_180039D62
0x180039d30  lea     r8, [rbx+2AAh]; pszSrc
0x180039d37  cmp     [r8], r14w
0x180039d3b  jz      short loc_180039D5D
0x180039d3d  call    StringCbCopyW
0x180039d42  lea     r8, asc_180098AD8; "\\"
0x180039d49  mov     rdx, r12; cbDest
0x180039d4c  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x180039d50  call    StringCbCatW
0x180039d55  mov     r8, rdi
0x180039d58  jmp     loc_180039C91
0x180039d5d  mov     r8, rdi
0x180039d60  jmp     short loc_180039D65
0x180039d62  mov     r8, r11; pszSrc
0x180039d65  call    StringCbCopyW
0x180039d6a  cmp     cs:dword_1800CF4E4, r14d
0x180039d71  lea     rax, [rbx+2CAh]
0x180039d78  mov     qword ptr [rsp+0B20h+var_AC8], rax
0x180039d7d  lea     rax, [rbp+0A20h+WideCharStr]
0x180039d81  mov     qword ptr [rsp+0B20h+var_AC8+8], rax
0x180039d86  jbe     short loc_180039DC0
0x180039d88  mov     eax, [rsi]
0x180039d8a  mov     r9d, 3; dwSubStringCount
0x180039d90  mov     rcx, cs:hLogHandle; hLogHandle
0x180039d97  mov     r8d, 4F1Fh; dwMessageId
0x180039d9d  mov     [rsp+0B20h+dwErrorIndex], r9d; dwErrorIndex
0x180039da2  mov     [rsp+0B20h+cchWideChar], eax; dwErrorCode
0x180039da6  lea     rax, [rsp+0B20h+plpszSubStringArray]
0x180039dab  lea     edx, [r9-2]; dwEventType
0x180039daf  mov     [rsp+0B20h+lpWideCharStr], rax; plpszSubStringArray
0x180039db4  call    cs:__imp_RouterLogEventStringW
0x180039dbb  nop     dword ptr [rax+rax+00h]
0x180039dc0  mov     rcx, [rbp+0A20h+var_40]
0x180039dc7  xor     rcx, rsp; StackCookie
0x180039dca  call    __security_check_cookie
0x180039dcf  mov     rbx, [rsp+0B20h+arg_10]
0x180039dd7  add     rsp, 0AF0h
0x180039dde  pop     r15
0x180039de0  pop     r14
0x180039de2  pop     r13
0x180039de4  pop     r12
0x180039de6  pop     rdi
0x180039de7  pop     rsi
0x180039de8  pop     rbp
0x180039de9  retn
```
