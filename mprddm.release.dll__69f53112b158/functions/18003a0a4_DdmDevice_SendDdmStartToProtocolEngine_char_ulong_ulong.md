# DdmDevice::SendDdmStartToProtocolEngine(char *,ulong,ulong)

- ea: `0x18003a0a4`
- end: `0x18003a44b`
- name: `?SendDdmStartToProtocolEngine@DdmDevice@@QEAAKPEADKK@Z`
- size: `935`
- prototype: `unsigned int __fastcall(DdmDevice *__hidden this, char *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002d390`
- `0x180041d00`
- `0x18004c1e0`

## callees

- `0x180002be6`
- `0x180007d00`
- `0x18003a0a4`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180092b90`
- `0x180095010`

## import_xrefs

- `msvcrt!wcstombs` at `0x18003a363`
- `msvcrt!wcstombs` at `0x18003a363`
- `KERNEL32!WideCharToMultiByte` at `0x18003a310`
- `KERNEL32!WideCharToMultiByte` at `0x18003a345`
- `KERNEL32!WideCharToMultiByte` at `0x18003a310`
- `KERNEL32!WideCharToMultiByte` at `0x18003a345`
- `rtutils!LogEventW` at `0x18003a2d6`
- `rtutils!LogEventW` at `0x18003a2d6`

## string_xrefs

- `0x18003a182`: `DdmDevice::SendDdmStartToProtocolEngine`
- `0x18003a23c`: `SendDdmStartToProtocolEngine: Port: %ws setting  PPP NOAUTH `

## pseudocode

```c
__int64 __fastcall DdmDevice::SendDdmStartToProtocolEngine(DdmDevice *this, char *a2, unsigned int a3, int a4)
{
  size_t v4; // r14
  char v8; // cl
  __int64 v9; // rdx
  __int64 v10; // r9
  bool v11; // zf
  __int64 v12; // rax
  __int64 v13; // rax
  __int128 v14; // xmm0
  void (__fastcall *v15)(DdmDevice *, __int64, _BYTE *, _DWORD *); // rax
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  _DWORD v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h]
  _BYTE v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+68h] [rbp-98h]
  char Dest[17]; // [rsp+6Ch] [rbp-94h] BYREF
  _BYTE v26[1503]; // [rsp+7Dh] [rbp-83h] BYREF
  int v27; // [rsp+65Ch] [rbp+55Ch]
  _BYTE v28[20]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v29[20]; // [rsp+674h] [rbp+574h] BYREF
  __int128 v30; // [rsp+688h] [rbp+588h]
  int v31; // [rsp+698h] [rbp+598h]
  CHAR MultiByteStr[257]; // [rsp+69Ch] [rbp+59Ch] BYREF
  CHAR lpMultiByteStr[5267]; // [rsp+79Dh] [rbp+69Dh] BYREF
  __int128 v34; // [rsp+1C30h] [rbp+1B30h] BYREF
  LPWSTR plpwsSubStrings[4]; // [rsp+1C40h] [rbp+1B40h] BYREF
  int v36; // [rsp+1C60h] [rbp+1B60h] BYREF
  __int128 v37; // [rsp+1C64h] [rbp+1B64h]
  __int128 v38; // [rsp+1C74h] [rbp+1B74h]
  int v39; // [rsp+1C84h] [rbp+1B84h]
  int v40; // [rsp+1C90h] [rbp+1B90h] BYREF
  _BYTE v41[2044]; // [rsp+1C94h] [rbp+1B94h] BYREF

  v4 = a3;
  v21[1] = 0;
  memset_0(v23, 0, 0x1BD0u);
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v8 = byte_1800CF404;
  v36 = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  v34 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v40) = 0;
    LOWORD(v36) = 0;
    if ( this )
      v9 = *((unsigned int *)this + 24);
    else
      v9 = 0xFFFFFFFFLL;
    ConvertPortNoToString(&v36, v9);
    v10 = (__int64)this + 96;
    if ( !this )
      v10 = 96;
    FormatRRASErrorString(&v40, L"%s (hport: %ld)", L"DdmDevice::SendDdmStartToProtocolEngine", *(_QWORD *)v10);
    v8 = byte_1800CF404;
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v40,
        (unsigned int)&v34,
        0,
        (__int64)&v36);
      v8 = byte_1800CF404;
    }
  }
  v11 = (*((_DWORD *)this + 33) & 0x20000) == 0;
  v12 = *((_QWORD *)this + 12);
  v22 = v12;
  v21[0] = 8;
  v24 = a4;
  if ( !v11 )
  {
    v31 |= 0x40u;
    if ( (v8 & 0x10) != 0 )
    {
      LOWORD(v40) = 0;
      LOWORD(v36) = 0;
      ConvertPortNoToString(&v36, (unsigned int)v12);
      FormatRRASErrorString(&v40, L"SendDdmStartToProtocolEngine: Port: %ws setting  PPP NOAUTH ", (char *)this + 714);
      if ( (byte_1800CF404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v40,
          (unsigned int)&v34,
          0,
          (__int64)&v36);
    }
    plpwsSubStrings[0] = (LPWSTR)((char *)this + 1092);
    plpwsSubStrings[1] = (LPWSTR)((char *)this + 682);
    plpwsSubStrings[3] = (LPWSTR)((char *)this + 714);
    plpwsSubStrings[2] = (LPWSTR)((char *)this + 168);
    LogEventW(4u, 0x4F37u, 4u, plpwsSubStrings);
    WideCharToMultiByte(0, 0x400u, (LPCWCH)this + 84, -1, MultiByteStr, 257, 0, 0);
    WideCharToMultiByte(0, 0x400u, (LPCWCH)this + 341, -1, lpMultiByteStr, 16, 0, 0);
  }
  wcstombs(Dest, (const wchar_t *)this + 357, 0x11u);
  if ( a2 && (_DWORD)v4 )
  {
    memcpy_0(v26, a2, v4);
    v27 = v4;
  }
  v13 = *(_QWORD *)this;
  v14 = *(_OWORD *)((char *)this + 1076);
  v20[0] = 20;
  v15 = *(void (__fastcall **)(DdmDevice *, __int64, _BYTE *, _DWORD *))(v13 + 416);
  v30 = v14;
  v15(this, 12, v28, v20);
  v16 = *(_QWORD *)this;
  v20[0] = 20;
  (*(void (__fastcall **)(DdmDevice *, __int64, _BYTE *, _DWORD *))(v16 + 416))(this, 13, v29, v20);
  v17 = (unsigned __int16)*((_DWORD *)this + 34);
  if ( v17 == 15 )
  {
    v18 = 1;
  }
  else
  {
    v18 = 2;
    if ( v17 != 16 )
      v18 = 0;
  }
  return ((__int64 (__fastcall *)(_DWORD *))qword_1800CE4C8[10 * v18])(v21);
}

```

## disassembly

```asm
0x18003a0a4  push    rbp
0x18003a0a6  push    rbx
0x18003a0a7  push    rsi
0x18003a0a8  push    rdi
0x18003a0a9  push    r13
0x18003a0ab  push    r14
0x18003a0ad  push    r15
0x18003a0af  lea     rbp, [rsp-23A0h]
0x18003a0b7  mov     eax, 24A0h
0x18003a0bc  call    _alloca_probe
0x18003a0c1  sub     rsp, rax
0x18003a0c4  mov     rax, cs:__security_cookie
0x18003a0cb  xor     rax, rsp
0x18003a0ce  mov     [rbp+23D0h+var_40], rax
0x18003a0d5  mov     r14d, r8d
0x18003a0d8  mov     r15, rdx
0x18003a0db  mov     rsi, rcx
0x18003a0de  xor     eax, eax
0x18003a0e0  xor     edx, edx; Val
0x18003a0e2  mov     [rsp+24D0h+var_247C], eax
0x18003a0e6  mov     r8d, 1BD0h; Size
0x18003a0ec  lea     rcx, [rsp+24D0h+var_2470]; void *
0x18003a0f1  mov     ebx, r9d
0x18003a0f4  call    memset_0
0x18003a0f9  xor     r13d, r13d
0x18003a0fc  lea     rcx, [rbp+23D0h+var_83C]; void *
0x18003a103  xor     edx, edx; Val
0x18003a105  mov     [rbp+23D0h+var_840], r13d
0x18003a10c  mov     r8d, 7FCh; Size
0x18003a112  call    memset_0
0x18003a117  mov     cl, cs:byte_1800CF404
0x18003a11d  xorps   xmm0, xmm0
0x18003a120  xor     eax, eax
0x18003a122  mov     [rbp+23D0h+var_870], r13d
0x18003a129  mov     [rbp+23D0h+var_84C], eax
0x18003a12f  movups  [rbp+23D0h+var_86C], xmm0
0x18003a136  movups  [rbp+23D0h+var_85C], xmm0
0x18003a13d  movups  [rbp+23D0h+var_8A0], xmm0
0x18003a144  test    cl, 10h
0x18003a147  jz      loc_18003A1E6
0x18003a14d  mov     word ptr [rbp+23D0h+var_840], r13w
0x18003a155  mov     word ptr [rbp+23D0h+var_870], r13w
0x18003a15d  test    rsi, rsi
0x18003a160  jz      short loc_18003A167
0x18003a162  mov     edx, [rsi+60h]
0x18003a165  jmp     short loc_18003A16A
0x18003a167  or      edx, 0FFFFFFFFh
0x18003a16a  lea     rcx, [rbp+23D0h+var_870]
0x18003a171  call    ConvertPortNoToString
0x18003a176  mov     eax, 60h ; '`'
0x18003a17b  lea     r9, [rsi+60h]
0x18003a17f  test    rsi, rsi
0x18003a182  lea     r8, aDdmdeviceSendd; "DdmDevice::SendDdmStartToProtocolEngine"
0x18003a189  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x18003a190  cmovz   r9, rax
0x18003a194  lea     rcx, [rbp+23D0h+var_840]
0x18003a19b  mov     r9, [r9]
0x18003a19e  call    FormatRRASErrorString
0x18003a1a3  mov     cl, cs:byte_1800CF404
0x18003a1a9  test    cl, 10h
0x18003a1ac  jz      short loc_18003A1E6
0x18003a1ae  lea     rax, [rbp+23D0h+var_870]
0x18003a1b5  mov     qword ptr [rsp+24D0h+cbMultiByte], rax
0x18003a1ba  lea     r9, [rbp+23D0h+var_8A0]
0x18003a1c1  lea     r8, [rbp+23D0h+var_840]
0x18003a1c8  mov     [rsp+24D0h+lpMultiByteStr], r13
0x18003a1cd  lea     rdx, RasDdmParamTraceInfo
0x18003a1d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003a1db  call    McTemplateU0zjzz_EventWriteTransfer
0x18003a1e0  mov     cl, cs:byte_1800CF404
0x18003a1e6  test    dword ptr [rsi+84h], 20000h
0x18003a1f0  mov     rax, [rsi+60h]
0x18003a1f4  mov     [rsp+24D0h+var_2478], rax
0x18003a1f9  mov     [rsp+24D0h+var_2480], 8
0x18003a201  mov     [rsp+24D0h+var_2468], ebx
0x18003a205  jz      loc_18003A351
0x18003a20b  or      [rbp+23D0h+var_1E38], 40h
0x18003a212  test    cl, 10h
0x18003a215  jz      short loc_18003A28A
0x18003a217  mov     edx, eax
0x18003a219  mov     word ptr [rbp+23D0h+var_840], r13w
0x18003a221  lea     rcx, [rbp+23D0h+var_870]
0x18003a228  mov     word ptr [rbp+23D0h+var_870], r13w
0x18003a230  call    ConvertPortNoToString
0x18003a235  lea     r8, [rsi+2CAh]
0x18003a23c  lea     rdx, aSendddmstartto; "SendDdmStartToProtocolEngine: Port: %ws"...
0x18003a243  lea     rcx, [rbp+23D0h+var_840]
0x18003a24a  call    FormatRRASErrorString
0x18003a24f  test    cs:byte_1800CF404, 10h
0x18003a256  jz      short loc_18003A28A
0x18003a258  lea     rax, [rbp+23D0h+var_870]
0x18003a25f  mov     qword ptr [rsp+24D0h+cbMultiByte], rax
0x18003a264  lea     r9, [rbp+23D0h+var_8A0]
0x18003a26b  lea     r8, [rbp+23D0h+var_840]
0x18003a272  mov     [rsp+24D0h+lpMultiByteStr], r13
0x18003a277  lea     rdx, RasDdmParamTraceInfo
0x18003a27e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003a285  call    McTemplateU0zjzz_EventWriteTransfer
0x18003a28a  lea     rax, [rsi+444h]
0x18003a291  mov     ecx, 4; wEventType
0x18003a296  mov     [rbp+23D0h+plpwsSubStrings], rax
0x18003a29d  lea     rdi, [rsi+2AAh]
0x18003a2a4  lea     rax, [rsi+2CAh]
0x18003a2ab  mov     [rbp+23D0h+var_888], rdi
0x18003a2b2  lea     rbx, [rsi+0A8h]
0x18003a2b9  mov     [rbp+23D0h+var_878], rax
0x18003a2c0  lea     r9, [rbp+23D0h+plpwsSubStrings]; plpwsSubStrings
0x18003a2c7  mov     [rbp+23D0h+var_880], rbx
0x18003a2ce  mov     r8d, ecx; cNumberOfSubStrings
0x18003a2d1  mov     edx, 4F37h; dwMessageId
0x18003a2d6  call    cs:__imp_LogEventW
0x18003a2dd  nop     dword ptr [rax+rax+00h]
0x18003a2e2  mov     [rsp+24D0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18003a2e7  lea     rax, [rbp+23D0h+MultiByteStr]
0x18003a2ee  mov     r8, rbx; lpWideCharStr
0x18003a2f1  mov     [rsp+24D0h+lpDefaultChar], r13; lpDefaultChar
0x18003a2f6  mov     ebx, 400h
0x18003a2fb  mov     [rsp+24D0h+cbMultiByte], 101h; cbMultiByte
0x18003a303  mov     edx, ebx; dwFlags
0x18003a305  mov     [rsp+24D0h+lpMultiByteStr], rax; lpMultiByteStr
0x18003a30a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003a30e  xor     ecx, ecx; CodePage
0x18003a310  call    cs:__imp_WideCharToMultiByte
0x18003a317  nop     dword ptr [rax+rax+00h]
0x18003a31c  mov     [rsp+24D0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18003a321  lea     rax, [rbp+23D0h+var_1D33]
0x18003a328  mov     [rsp+24D0h+lpDefaultChar], r13; lpDefaultChar
0x18003a32d  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003a331  mov     [rsp+24D0h+cbMultiByte], 10h; cbMultiByte
0x18003a339  mov     r8, rdi; lpWideCharStr
0x18003a33c  mov     edx, ebx; dwFlags
0x18003a33e  mov     [rsp+24D0h+lpMultiByteStr], rax; lpMultiByteStr
0x18003a343  xor     ecx, ecx; CodePage
0x18003a345  call    cs:__imp_WideCharToMultiByte
0x18003a34c  nop     dword ptr [rax+rax+00h]
0x18003a351  lea     rdx, [rsi+2CAh]; Source
0x18003a358  mov     r8d, 11h; MaxCount
0x18003a35e  lea     rcx, [rsp+24D0h+Dest]; Dest
0x18003a363  call    cs:__imp_wcstombs
0x18003a36a  nop     dword ptr [rax+rax+00h]
0x18003a36f  test    r15, r15
0x18003a372  jz      short loc_18003A390
0x18003a374  test    r14d, r14d
0x18003a377  jz      short loc_18003A390
0x18003a379  mov     r8, r14; Size
0x18003a37c  lea     rcx, [rsp+24D0h+var_2453]; void *
0x18003a381  mov     rdx, r15; Src
0x18003a384  call    memcpy_0
0x18003a389  mov     [rbp+23D0h+var_1E74], r14d
0x18003a390  mov     rax, [rsi]
0x18003a393  lea     r9, [rsp+24D0h+var_2490]
0x18003a398  movups  xmm0, xmmword ptr [rsi+434h]
0x18003a39f  mov     ebx, 14h
0x18003a3a4  lea     r8, [rbp+23D0h+var_1E70]
0x18003a3ab  mov     rcx, rsi
0x18003a3ae  mov     [rsp+24D0h+var_2490], ebx
0x18003a3b2  mov     rax, [rax+1A0h]
0x18003a3b9  movdqu  [rbp+23D0h+var_1E48], xmm0
0x18003a3c1  lea     edx, [rbx-8]
0x18003a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3c9  mov     rax, [rsi]
0x18003a3cc  lea     r9, [rsp+24D0h+var_2490]
0x18003a3d1  lea     r8, [rbp+23D0h+var_1E5C]
0x18003a3d8  mov     [rsp+24D0h+var_2490], ebx
0x18003a3dc  lea     edx, [rbx-7]
0x18003a3df  mov     rcx, rsi
0x18003a3e2  mov     rax, [rax+1A0h]
0x18003a3e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3ee  mov     ecx, [rsi+88h]
0x18003a3f4  movzx   ecx, cx
0x18003a3f7  cmp     ecx, 0Fh
0x18003a3fa  jnz     short loc_18003A401
0x18003a3fc  lea     eax, [rbx-13h]
0x18003a3ff  jmp     short loc_18003A40D
0x18003a401  cmp     ecx, 10h
0x18003a404  mov     eax, 2
0x18003a409  cmovnz  rax, r13
0x18003a40d  lea     rax, [rax+rax*4]
0x18003a411  add     rax, rax
0x18003a414  lea     rdx, qword_1800CE4C8
0x18003a41b  lea     rcx, [rsp+24D0h+var_2480]
0x18003a420  mov     rax, [rdx+rax*8]
0x18003a424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a429  mov     rcx, [rbp+23D0h+var_40]
0x18003a430  xor     rcx, rsp; StackCookie
0x18003a433  call    __security_check_cookie
0x18003a438  add     rsp, 24A0h
0x18003a43f  pop     r15
0x18003a441  pop     r14
0x18003a443  pop     r13
0x18003a445  pop     rdi
0x18003a446  pop     rsi
0x18003a447  pop     rbx
0x18003a448  pop     rbp
0x18003a449  retn
```
