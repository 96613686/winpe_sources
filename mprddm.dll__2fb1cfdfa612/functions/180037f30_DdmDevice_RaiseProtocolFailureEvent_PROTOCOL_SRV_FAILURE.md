# DdmDevice::RaiseProtocolFailureEvent(_PROTOCOL_SRV_FAILURE *)

- ea: `0x180037f30`
- end: `0x1800384db`
- name: `?RaiseProtocolFailureEvent@DdmDevice@@UEAAXPEAU_PROTOCOL_SRV_FAILURE@@@Z`
- size: `1451`
- prototype: `void __fastcall(DdmDevice *__hidden this, struct _PROTOCOL_SRV_FAILURE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x1800193a8`
- `0x180037f30`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180037fe2`
- `msvcrt!_itow_s` at `0x180037fe2`
- `KERNEL32!MultiByteToWideChar` at `0x180038081`
- `KERNEL32!MultiByteToWideChar` at `0x180038194`
- `KERNEL32!MultiByteToWideChar` at `0x1800381f7`
- `KERNEL32!MultiByteToWideChar` at `0x1800382c1`
- `KERNEL32!MultiByteToWideChar` at `0x180038303`
- `KERNEL32!MultiByteToWideChar` at `0x180038347`
- `KERNEL32!MultiByteToWideChar` at `0x18003838d`
- `KERNEL32!MultiByteToWideChar` at `0x180038081`
- `KERNEL32!MultiByteToWideChar` at `0x180038194`
- `KERNEL32!MultiByteToWideChar` at `0x1800381f7`
- `KERNEL32!MultiByteToWideChar` at `0x1800382c1`
- `KERNEL32!MultiByteToWideChar` at `0x180038303`
- `KERNEL32!MultiByteToWideChar` at `0x180038347`
- `KERNEL32!MultiByteToWideChar` at `0x18003838d`
- `rtutils!RouterLogEventW` at `0x180038169`
- `rtutils!RouterLogEventW` at `0x180038169`
- `rtutils!RouterLogEventStringW` at `0x1800384ab`
- `rtutils!RouterLogEventStringW` at `0x1800384ab`

## string_xrefs

- `0x180037feb`: `DdmDevice::RaiseProtocolFailureEvent: Entered, hPort=%d, Error=%d`

## pseudocode

```c
void __fastcall DdmDevice::RaiseProtocolFailureEvent(DdmDevice *this, const CHAR *a2)
{
  int *v4; // rbx
  WCHAR *v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rbx
  LPWSTR v8; // r8
  __int64 v9; // rcx
  LPWSTR v10; // r9
  __int64 v11; // rdx
  WCHAR *v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  DWORD v18; // r9d
  DWORD v19; // r8d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  WCHAR *v24; // r8
  WCHAR *v25; // r14
  WCHAR *v26; // rax
  WCHAR *v27; // rdx
  WCHAR *v28; // rcx
  WCHAR *v29; // rax
  WCHAR *v30; // rcx
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  WCHAR pszSrc[16]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Buffer[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v36; // [rsp+94h] [rbp-6Ch]
  __int128 v37; // [rsp+A4h] [rbp-5Ch]
  int v38; // [rsp+B4h] [rbp-4Ch]
  WCHAR WideCharStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  int v40; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v41[2044]; // [rsp+2E4h] [rbp+1E4h] BYREF

  v40 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  v33 = 0;
  memset_0(v41, 0, sizeof(v41));
  *(_DWORD *)Buffer = 0;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  v31 = 0;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v40) = 0;
    v4 = (int *)((char *)this + 96);
    Buffer[0] = 0;
    if ( this && *v4 != -1 )
      _itow_s(*v4, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v40,
      L"DdmDevice::RaiseProtocolFailureEvent: Entered, hPort=%d, Error=%d",
      *(_QWORD *)v4,
      *(unsigned int *)a2);
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v40,
        (unsigned int)&v31,
        0,
        (__int64)Buffer);
  }
  (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 80LL))(this, *(unsigned int *)a2);
  v5 = WideCharStr;
  v6 = 2147483646;
  v7 = 272;
  if ( a2[4] )
  {
    MultiByteToWideChar(0, 0, a2 + 4, -1, WideCharStr, 257);
    v8 = gblpszUnknown;
  }
  else
  {
    v8 = gblpszUnknown;
    v9 = 2147483646;
    v10 = gblpszUnknown;
    v11 = 272;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v5++ = *v10++;
      --v9;
      --v11;
    }
    while ( v11 );
    v12 = v5 - 1;
    if ( v11 )
      v12 = v5;
    *v12 = 0;
  }
  plpszSubStringArray[0] = (LPWSTR)((char *)this + 1092);
  v13 = *(_DWORD *)a2;
  if ( *(_DWORD *)a2 <= 0x2C4u )
  {
    if ( v13 != 708 )
    {
      v14 = v13 - 71;
      if ( v14 )
      {
        v15 = v14 - 535;
        if ( !v15 )
          return;
        v16 = v15 - 42;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            if ( v17 == 42 )
            {
              plpszSubStringArray[1] = WideCharStr;
              *(_QWORD *)&v33 = (char *)this + 714;
              if ( (unsigned int)dword_1800C84E4 <= 1 )
                return;
              v18 = 3;
              v19 = 20249;
              goto LABEL_25;
            }
            goto LABEL_37;
          }
          MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
          plpszSubStringArray[1] = pszSrc;
          *(_QWORD *)&v33 = WideCharStr;
          *((_QWORD *)&v33 + 1) = (char *)this + 714;
          if ( (unsigned int)dword_1800C84E4 <= 1 )
            return;
          v18 = 4;
          v19 = 20258;
        }
        else
        {
          MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
          plpszSubStringArray[1] = pszSrc;
          *(_QWORD *)&v33 = WideCharStr;
          *((_QWORD *)&v33 + 1) = (char *)this + 714;
          if ( (unsigned int)dword_1800C84E4 <= 1 )
            return;
          v18 = 4;
          v19 = 20256;
        }
      }
      else
      {
        plpszSubStringArray[1] = (LPWSTR)((char *)this + 714);
        if ( (unsigned int)dword_1800C84E4 <= 1 )
          return;
        v18 = 2;
        v19 = 20261;
      }
LABEL_25:
      RouterLogEventW(hLogHandle, 2u, v19, v18, plpszSubStringArray, 0);
      return;
    }
LABEL_43:
    MultiByteToWideChar(0, 0, a2 + 261, -1, pszSrc, 16);
    plpszSubStringArray[1] = pszSrc;
    *(_QWORD *)&v33 = WideCharStr;
    *((_QWORD *)&v33 + 1) = (char *)this + 714;
    if ( (unsigned int)dword_1800C84E4 <= 1 )
      return;
    v18 = 4;
    v19 = 20257;
    goto LABEL_25;
  }
  v20 = v13 - 718;
  if ( !v20 )
    return;
  v21 = v20 - 14;
  if ( v21 )
  {
    v22 = v21 - 2;
    if ( !v22 )
      return;
    v23 = v22 - 1059;
    if ( !v23 )
      goto LABEL_43;
    if ( v23 == 457 )
      return;
  }
LABEL_37:
  if ( !a2[4] )
  {
    v25 = (WCHAR *)((char *)this + 168);
    if ( *((_WORD *)this + 84) )
    {
      v26 = (WCHAR *)((char *)this + 682);
      if ( *((_WORD *)this + 341) )
      {
        v27 = WideCharStr;
        do
        {
          if ( !v6 )
            break;
          if ( !*v26 )
            break;
          *v27++ = *v26++;
          --v6;
          --v7;
        }
        while ( v7 );
        v28 = v27 - 1;
        if ( v7 )
          v28 = v27;
        *v28 = 0;
        StringCbCatW(WideCharStr, 0x220u, L"\\");
        v24 = (WCHAR *)((char *)this + 168);
        goto LABEL_42;
      }
      v29 = WideCharStr;
      do
      {
        if ( !v6 )
          break;
        if ( !*v25 )
          break;
        *v29++ = *v25++;
        --v6;
        --v7;
      }
      while ( v7 );
    }
    else
    {
      v29 = WideCharStr;
      do
      {
        if ( !v6 )
          break;
        if ( !*v8 )
          break;
        *v29++ = *v8++;
        --v6;
        --v7;
      }
      while ( v7 );
    }
    v30 = v29 - 1;
    if ( v7 )
      v30 = v29;
    *v30 = 0;
    goto LABEL_67;
  }
  if ( !a2[261] )
  {
    MultiByteToWideChar(0, 0, a2 + 4, -1, WideCharStr, 257);
LABEL_67:
    plpszSubStringArray[1] = (LPWSTR)((char *)this + 714);
    *(_QWORD *)&v33 = WideCharStr;
    if ( dword_1800C84E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4F1Fu, 3u, plpszSubStringArray, *(_DWORD *)a2, 3u);
    return;
  }
  if ( MultiByteToWideChar(0, 0, a2 + 261, -1, WideCharStr, 257) )
  {
    StringCbCatW(WideCharStr, 0x220u, L"\\");
    if ( MultiByteToWideChar(0, 0, a2 + 4, -1, pszSrc, 16) )
    {
      v24 = pszSrc;
LABEL_42:
      StringCbCatW(WideCharStr, 0x220u, v24);
      goto LABEL_67;
    }
  }
}

```

## disassembly

```asm
0x180037f30  mov     [rsp-8+arg_10], rbx
0x180037f35  push    rbp
0x180037f36  push    rsi
0x180037f37  push    rdi
0x180037f38  push    r12
0x180037f3a  push    r13
0x180037f3c  push    r14
0x180037f3e  push    r15
0x180037f40  lea     rbp, [rsp-9F0h]
0x180037f48  sub     rsp, 0AF0h
0x180037f4f  mov     rax, cs:__security_cookie
0x180037f56  xor     rax, rsp
0x180037f59  mov     [rbp+0A20h+var_40], rax
0x180037f60  xorps   xmm0, xmm0
0x180037f63  mov     r15, rdx
0x180037f66  mov     rdi, rcx
0x180037f69  xor     r12d, r12d
0x180037f6c  xor     edx, edx; Val
0x180037f6e  mov     [rbp+0A20h+var_840], r12d
0x180037f75  lea     rcx, [rbp+0A20h+var_83C]; void *
0x180037f7c  mov     r8d, 7FCh; Size
0x180037f82  movups  xmmword ptr [rsp+0B20h+plpszSubStringArray], xmm0
0x180037f87  movups  [rsp+0B20h+var_AC0], xmm0
0x180037f8c  call    memset_0
0x180037f91  xorps   xmm0, xmm0
0x180037f94  mov     dword ptr [rbp+0A20h+Buffer], r12d
0x180037f98  xor     eax, eax
0x180037f9a  test    cs:byte_1800C8404, 8
0x180037fa1  movups  [rbp+0A20h+var_A8C], xmm0
0x180037fa5  mov     [rbp+0A20h+var_A6C], eax
0x180037fa8  movups  [rbp+0A20h+var_A7C], xmm0
0x180037fac  movups  [rsp+0B20h+var_AE0], xmm0
0x180037fb1  jz      loc_180038037
0x180037fb7  mov     word ptr [rbp+0A20h+var_840], r12w
0x180037fbf  lea     rbx, [rdi+60h]
0x180037fc3  mov     [rbp+0A20h+Buffer], r12w
0x180037fc8  test    rdi, rdi
0x180037fcb  jz      short loc_180037FE8
0x180037fcd  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180037fd0  jz      short loc_180037FE8
0x180037fd2  mov     ecx, [rbx]; Value
0x180037fd4  lea     r9d, [r12+0Ah]; Radix
0x180037fd9  lea     r8d, [r12+14h]; BufferCount
0x180037fde  lea     rdx, [rbp+0A20h+Buffer]; Buffer
0x180037fe2  call    cs:__imp__itow_s
0x180037fe8  mov     r9d, [r15]
0x180037feb  lea     rdx, aDdmdeviceRaise; "DdmDevice::RaiseProtocolFailureEvent: E"...
0x180037ff2  mov     r8, [rbx]
0x180037ff5  lea     rcx, [rbp+0A20h+var_840]
0x180037ffc  call    FormatRRASErrorString
0x180038001  test    cs:byte_1800C8404, 8
0x180038008  jz      short loc_180038037
0x18003800a  lea     rax, [rbp+0A20h+Buffer]
0x18003800e  mov     qword ptr [rsp+0B20h+cchWideChar], rax
0x180038013  lea     r9, [rsp+0B20h+var_AE0]
0x180038018  lea     r8, [rbp+0A20h+var_840]
0x18003801f  mov     [rsp+0B20h+lpWideCharStr], r12
0x180038024  lea     rdx, RasDdmParamTraceError
0x18003802b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038032  call    McTemplateU0zjzz_EventWriteTransfer
0x180038037  mov     rax, [rdi]
0x18003803a  mov     rcx, rdi
0x18003803d  mov     edx, [r15]
0x180038040  mov     rax, [rax+50h]
0x180038044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038049  or      r11d, 0FFFFFFFFh
0x18003804d  lea     r14, [r15+4]
0x180038051  lea     rax, [rbp+0A20h+WideCharStr]
0x180038055  mov     esi, 7FFFFFFEh
0x18003805a  mov     ebx, 110h
0x18003805f  mov     r13d, 2
0x180038065  cmp     [r14], r12b
0x180038068  jz      short loc_180038094
0x18003806a  mov     [rsp+0B20h+cchWideChar], 101h; cchWideChar
0x180038072  mov     r9d, r11d; cbMultiByte
0x180038075  mov     r8, r14; lpMultiByteStr
0x180038078  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x18003807d  xor     edx, edx; dwFlags
0x18003807f  xor     ecx, ecx; CodePage
0x180038081  call    cs:__imp_MultiByteToWideChar
0x180038087  mov     r8, cs:gblpszUnknown
0x18003808e  or      r11d, 0FFFFFFFFh
0x180038092  jmp     short loc_1800380D5
0x180038094  mov     r8, cs:gblpszUnknown
0x18003809b  mov     rcx, rsi
0x18003809e  mov     r9, r8
0x1800380a1  mov     rdx, rbx
0x1800380a4  test    rcx, rcx
0x1800380a7  jz      short loc_1800380C6
0x1800380a9  movzx   r10d, word ptr [r9]
0x1800380ad  test    r10w, r10w
0x1800380b1  jz      short loc_1800380C6
0x1800380b3  mov     [rax], r10w
0x1800380b7  add     r9, r13
0x1800380ba  add     rax, r13
0x1800380bd  dec     rcx
0x1800380c0  sub     rdx, 1
0x1800380c4  jnz     short loc_1800380A4
0x1800380c6  test    rdx, rdx
0x1800380c9  lea     rcx, [rax-2]
0x1800380cd  cmovnz  rcx, rax
0x1800380d1  mov     [rcx], r12w
0x1800380d5  lea     rax, [rdi+444h]
0x1800380dc  mov     ecx, 2C4h
0x1800380e1  mov     [rsp+0B20h+plpszSubStringArray], rax
0x1800380e6  mov     eax, [r15]
0x1800380e9  cmp     eax, ecx
0x1800380eb  ja      loc_180038261
0x1800380f1  jz      loc_180038327
0x1800380f7  sub     eax, 47h ; 'G'
0x1800380fa  jz      loc_18003823A
0x180038100  sub     eax, 217h
0x180038105  jz      loc_1800384B1
0x18003810b  sub     eax, 2Ah ; '*'
0x18003810e  jz      loc_1800381D7
0x180038114  sub     eax, 1
0x180038117  jz      short loc_180038174
0x180038119  cmp     eax, 2Ah ; '*'
0x18003811c  jnz     loc_180038290
0x180038122  cmp     cs:dword_1800C84E4, 1
0x180038129  lea     rax, [rbp+0A20h+WideCharStr]
0x18003812d  mov     [rsp+0B20h+plpszSubStringArray+8], rax
0x180038132  lea     rax, [rdi+2CAh]
0x180038139  mov     qword ptr [rsp+0B20h+var_AC0], rax
0x18003813e  jbe     loc_1800384B1
0x180038144  mov     r9d, 3; dwSubStringCount
0x18003814a  mov     r8d, 4F19h; dwMessageId
0x180038150  mov     rcx, cs:hLogHandle; hLogHandle
0x180038157  lea     rax, [rsp+0B20h+plpszSubStringArray]
0x18003815c  mov     [rsp+0B20h+cchWideChar], r12d; dwErrorCode
0x180038161  mov     edx, r13d; dwEventType
0x180038164  mov     [rsp+0B20h+lpWideCharStr], rax; plpszSubStringArray
0x180038169  call    cs:__imp_RouterLogEventW
0x18003816f  jmp     loc_1800384B1
0x180038174  lea     rax, [rsp+0B20h+pszSrc]
0x180038179  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180038181  lea     r8, [r15+105h]; lpMultiByteStr
0x180038188  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x18003818d  mov     r9d, r11d; cbMultiByte
0x180038190  xor     edx, edx; dwFlags
0x180038192  xor     ecx, ecx; CodePage
0x180038194  call    cs:__imp_MultiByteToWideChar
0x18003819a  cmp     cs:dword_1800C84E4, 1
0x1800381a1  lea     rax, [rsp+0B20h+pszSrc]
0x1800381a6  mov     [rsp+0B20h+plpszSubStringArray+8], rax
0x1800381ab  lea     rax, [rbp+0A20h+WideCharStr]
0x1800381af  mov     qword ptr [rsp+0B20h+var_AC0], rax
0x1800381b4  lea     rax, [rdi+2CAh]
0x1800381bb  mov     qword ptr [rsp+0B20h+var_AC0+8], rax
0x1800381c0  jbe     loc_1800384B1
0x1800381c6  mov     r9d, 4
0x1800381cc  mov     r8d, 4F22h
0x1800381d2  jmp     loc_180038150
0x1800381d7  lea     rax, [rsp+0B20h+pszSrc]
0x1800381dc  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x1800381e4  lea     r8, [r15+105h]; lpMultiByteStr
0x1800381eb  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x1800381f0  mov     r9d, r11d; cbMultiByte
0x1800381f3  xor     edx, edx; dwFlags
0x1800381f5  xor     ecx, ecx; CodePage
0x1800381f7  call    cs:__imp_MultiByteToWideChar
0x1800381fd  cmp     cs:dword_1800C84E4, 1
0x180038204  lea     rax, [rsp+0B20h+pszSrc]
0x180038209  mov     [rsp+0B20h+plpszSubStringArray+8], rax
0x18003820e  lea     rax, [rbp+0A20h+WideCharStr]
0x180038212  mov     qword ptr [rsp+0B20h+var_AC0], rax
0x180038217  lea     rax, [rdi+2CAh]
0x18003821e  mov     qword ptr [rsp+0B20h+var_AC0+8], rax
0x180038223  jbe     loc_1800384B1
0x180038229  mov     r9d, 4
0x18003822f  mov     r8d, 4F20h
0x180038235  jmp     loc_180038150
0x18003823a  cmp     cs:dword_1800C84E4, 1
0x180038241  lea     rax, [rdi+2CAh]
0x180038248  mov     [rsp+0B20h+plpszSubStringArray+8], rax
0x18003824d  jbe     loc_1800384B1
0x180038253  mov     r9d, r13d
0x180038256  mov     r8d, 4F25h
0x18003825c  jmp     loc_180038150
0x180038261  sub     eax, 2CEh
0x180038266  jz      loc_1800384B1
0x18003826c  sub     eax, 0Eh
0x18003826f  jz      short loc_180038290
0x180038271  sub     eax, r13d
0x180038274  jz      loc_1800384B1
0x18003827a  sub     eax, 423h
0x18003827f  jz      loc_180038327
0x180038285  cmp     eax, 1C9h
0x18003828a  jz      loc_1800384B1
0x180038290  cmp     [r14], r12b
0x180038293  jz      loc_180038398
0x180038299  lea     r8, [r15+105h]; lpMultiByteStr
0x1800382a0  mov     [rsp+0B20h+cchWideChar], 101h; cchWideChar
0x1800382a8  xor     edx, edx; dwFlags
0x1800382aa  lea     rax, [rbp+0A20h+WideCharStr]
0x1800382ae  xor     ecx, ecx; CodePage
0x1800382b0  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x1800382b5  mov     r9d, r11d; cbMultiByte
0x1800382b8  cmp     [r8], r12b
0x1800382bb  jz      loc_18003838A
0x1800382c1  call    cs:__imp_MultiByteToWideChar
0x1800382c7  test    eax, eax
0x1800382c9  jz      loc_1800384B1
0x1800382cf  mov     ebx, 220h
0x1800382d4  lea     r8, asc_180091AD8; "\\"
0x1800382db  mov     edx, ebx; cbDest
0x1800382dd  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x1800382e1  call    StringCbCatW
0x1800382e6  lea     rax, [rsp+0B20h+pszSrc]
0x1800382eb  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x1800382f3  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800382f7  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x1800382fc  mov     r8, r14; lpMultiByteStr
0x1800382ff  xor     edx, edx; dwFlags
0x180038301  xor     ecx, ecx; CodePage
0x180038303  call    cs:__imp_MultiByteToWideChar
0x180038309  test    eax, eax
0x18003830b  jz      loc_1800384B1
0x180038311  lea     r8, [rsp+0B20h+pszSrc]; pszSrc
0x180038316  mov     rdx, rbx; cbDest
0x180038319  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x18003831d  call    StringCbCatW
0x180038322  jmp     loc_180038460
0x180038327  lea     rax, [rsp+0B20h+pszSrc]
0x18003832c  mov     [rsp+0B20h+cchWideChar], 10h; cchWideChar
0x180038334  lea     r8, [r15+105h]; lpMultiByteStr
0x18003833b  mov     [rsp+0B20h+lpWideCharStr], rax; lpWideCharStr
0x180038340  mov     r9d, r11d; cbMultiByte
0x180038343  xor     edx, edx; dwFlags
0x180038345  xor     ecx, ecx; CodePage
0x180038347  call    cs:__imp_MultiByteToWideChar
0x18003834d  cmp     cs:dword_1800C84E4, 1
0x180038354  lea     rax, [rsp+0B20h+pszSrc]
0x180038359  mov     [rsp+0B20h+plpszSubStringArray+8], rax
0x18003835e  lea     rax, [rbp+0A20h+WideCharStr]
0x180038362  mov     qword ptr [rsp+0B20h+var_AC0], rax
0x180038367  lea     rax, [rdi+2CAh]
0x18003836e  mov     qword ptr [rsp+0B20h+var_AC0+8], rax
0x180038373  jbe     loc_1800384B1
0x180038379  mov     r9d, 4
0x18003837f  mov     r8d, 4F21h
0x180038385  jmp     loc_180038150
0x18003838a  mov     r8, r14; lpMultiByteStr
0x18003838d  call    cs:__imp_MultiByteToWideChar
0x180038393  jmp     loc_180038460
0x180038398  lea     r14, [rdi+0A8h]
0x18003839f  cmp     [r14], r12w
0x1800383a3  jz      loc_18003842D
0x1800383a9  lea     rax, [rdi+2AAh]
0x1800383b0  cmp     [rax], r12w
0x1800383b4  jz      short loc_180038407
0x1800383b6  lea     rdx, [rbp+0A20h+WideCharStr]
0x1800383ba  test    rsi, rsi
0x1800383bd  jz      short loc_1800383D9
0x1800383bf  movzx   ecx, word ptr [rax]
0x1800383c2  test    cx, cx
0x1800383c5  jz      short loc_1800383D9
0x1800383c7  mov     [rdx], cx
0x1800383ca  add     rax, r13
0x1800383cd  add     rdx, r13
0x1800383d0  dec     rsi
0x1800383d3  sub     rbx, 1
0x1800383d7  jnz     short loc_1800383BA
0x1800383d9  test    rbx, rbx
0x1800383dc  lea     rcx, [rdx-2]
0x1800383e0  mov     ebx, 220h
0x1800383e5  lea     r8, asc_180091AD8; "\\"
0x1800383ec  cmovnz  rcx, rdx
0x1800383f0  mov     edx, ebx; cbDest
0x1800383f2  mov     [rcx], r12w
0x1800383f6  lea     rcx, [rbp+0A20h+WideCharStr]; pszDest
0x1800383fa  call    StringCbCatW
0x1800383ff  mov     r8, r14
0x180038402  jmp     loc_180038316
0x180038407  lea     rax, [rbp+0A20h+WideCharStr]
0x18003840b  test    rsi, rsi
0x18003840e  jz      short loc_180038451
0x180038410  movzx   ecx, word ptr [r14]
0x180038414  test    cx, cx
0x180038417  jz      short loc_180038451
0x180038419  mov     [rax], cx
0x18003841c  add     r14, r13
0x18003841f  add     rax, r13
0x180038422  dec     rsi
0x180038425  sub     rbx, 1
0x180038429  jnz     short loc_18003840B
0x18003842b  jmp     short loc_180038451
0x18003842d  lea     rax, [rbp+0A20h+WideCharStr]
0x180038431  test    rsi, rsi
0x180038434  jz      short loc_180038451
0x180038436  movzx   ecx, word ptr [r8]
0x18003843a  test    cx, cx
0x18003843d  jz      short loc_180038451
0x18003843f  mov     [rax], cx
0x180038442  add     r8, r13
0x180038445  add     rax, r13
0x180038448  dec     rsi
0x18003844b  sub     rbx, 1
0x18003844f  jnz     short loc_180038431
0x180038451  test    rbx, rbx
  ... truncated ...
```
