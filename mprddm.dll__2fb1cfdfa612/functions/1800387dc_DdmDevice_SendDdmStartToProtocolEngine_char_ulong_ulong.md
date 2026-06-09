# DdmDevice::SendDdmStartToProtocolEngine(char *,ulong,ulong)

- ea: `0x1800387dc`
- end: `0x180038bac`
- name: `?SendDdmStartToProtocolEngine@DdmDevice@@QEAAKPEADKK@Z`
- size: `976`
- prototype: `unsigned int __fastcall(DdmDevice *__hidden this, char *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002b1d0`
- `0x1800404d0`
- `0x18004acc0`

## callees

- `0x180002ba6`
- `0x180007c50`
- `0x1800387dc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800388c1`
- `msvcrt!_itow_s` at `0x180038998`
- `msvcrt!_itow_s` at `0x1800388c1`
- `msvcrt!_itow_s` at `0x180038998`
- `msvcrt!wcstombs` at `0x180038ace`
- `msvcrt!wcstombs` at `0x180038ace`
- `KERNEL32!WideCharToMultiByte` at `0x180038a7f`
- `KERNEL32!WideCharToMultiByte` at `0x180038ab6`
- `KERNEL32!WideCharToMultiByte` at `0x180038a7f`
- `KERNEL32!WideCharToMultiByte` at `0x180038ab6`
- `rtutils!LogEventW` at `0x180038a43`
- `rtutils!LogEventW` at `0x180038a43`

## string_xrefs

- `0x1800388ca`: `DdmDevice::SendDdmStartToProtocolEngine`
- `0x1800389a5`: `SendDdmStartToProtocolEngine: Port: %ws setting  PPP NOAUTH `

## pseudocode

```c
__int64 __fastcall DdmDevice::SendDdmStartToProtocolEngine(DdmDevice *this, char *a2, unsigned int a3, int a4)
{
  size_t v4; // r14
  char v8; // cl
  int *v9; // rbx
  bool v10; // zf
  int v11; // ecx
  __int64 v12; // rax
  __int128 v13; // xmm0
  void (__fastcall *v14)(DdmDevice *, __int64, _BYTE *, _DWORD *); // rax
  __int64 v15; // rax
  int v16; // ecx
  __int64 (__fastcall *v18)(__int64 *); // rax
  _DWORD v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+58h] [rbp-A8h]
  _BYTE v22[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v23; // [rsp+68h] [rbp-98h]
  char Dest[17]; // [rsp+6Ch] [rbp-94h] BYREF
  _BYTE v25[1503]; // [rsp+7Dh] [rbp-83h] BYREF
  int v26; // [rsp+65Ch] [rbp+55Ch]
  _BYTE v27[20]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v28[20]; // [rsp+674h] [rbp+574h] BYREF
  __int128 v29; // [rsp+688h] [rbp+588h]
  int v30; // [rsp+698h] [rbp+598h]
  CHAR MultiByteStr[257]; // [rsp+69Ch] [rbp+59Ch] BYREF
  CHAR lpMultiByteStr[5267]; // [rsp+79Dh] [rbp+69Dh] BYREF
  __int128 v33; // [rsp+1C30h] [rbp+1B30h] BYREF
  LPWSTR plpwsSubStrings[2]; // [rsp+1C40h] [rbp+1B40h] BYREF
  __int128 v35; // [rsp+1C50h] [rbp+1B50h]
  wchar_t Buffer[2]; // [rsp+1C60h] [rbp+1B60h] BYREF
  __int128 v37; // [rsp+1C64h] [rbp+1B64h]
  __int128 v38; // [rsp+1C74h] [rbp+1B74h]
  int v39; // [rsp+1C84h] [rbp+1B84h]
  int v40; // [rsp+1C90h] [rbp+1B90h] BYREF
  _BYTE v41[2044]; // [rsp+1C94h] [rbp+1B94h] BYREF

  v4 = a3;
  v20 = 8;
  v21 = 0;
  memset_0(v22, 0, 0x1BD0u);
  v19[0] = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v8 = byte_1800C8404;
  *(_DWORD *)Buffer = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  v33 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v40) = 0;
    v9 = (int *)((char *)this + 96);
    Buffer[0] = 0;
    if ( this && *v9 != -1 )
      _itow_s(*v9, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v40, L"%s (hport: %ld)", L"DdmDevice::SendDdmStartToProtocolEngine", *(_QWORD *)v9);
    v8 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v40,
        (unsigned int)&v33,
        0,
        (__int64)Buffer);
      v8 = byte_1800C8404;
    }
  }
  v10 = (*((_DWORD *)this + 33) & 0x20000) == 0;
  v21 = *((_QWORD *)this + 12);
  LODWORD(v20) = 8;
  v23 = a4;
  if ( !v10 )
  {
    v30 |= 0x40u;
    *(_OWORD *)plpwsSubStrings = 0;
    v35 = 0;
    if ( (v8 & 0x10) != 0 )
    {
      v11 = *((_DWORD *)this + 24);
      LOWORD(v40) = 0;
      Buffer[0] = 0;
      if ( v11 != -1 )
        _itow_s(v11, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v40, L"SendDdmStartToProtocolEngine: Port: %ws setting  PPP NOAUTH ", (char *)this + 714);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v40,
          (unsigned int)&v33,
          0,
          (__int64)Buffer);
    }
    plpwsSubStrings[0] = (LPWSTR)((char *)this + 1092);
    plpwsSubStrings[1] = (LPWSTR)((char *)this + 682);
    *((_QWORD *)&v35 + 1) = (char *)this + 714;
    *(_QWORD *)&v35 = (char *)this + 168;
    LogEventW(4u, 0x4F37u, 4u, plpwsSubStrings);
    WideCharToMultiByte(0, 0x400u, (LPCWCH)this + 84, -1, MultiByteStr, 257, 0, 0);
    WideCharToMultiByte(0, 0x400u, (LPCWCH)this + 341, -1, lpMultiByteStr, 16, 0, 0);
  }
  wcstombs(Dest, (const wchar_t *)this + 357, 0x11u);
  if ( a2 && (_DWORD)v4 )
  {
    memcpy_0(v25, a2, v4);
    v26 = v4;
  }
  v12 = *(_QWORD *)this;
  v13 = *(_OWORD *)((char *)this + 1076);
  v19[0] = 20;
  v14 = *(void (__fastcall **)(DdmDevice *, __int64, _BYTE *, _DWORD *))(v12 + 416);
  v29 = v13;
  v14(this, 12, v27, v19);
  v15 = *(_QWORD *)this;
  v19[0] = 20;
  (*(void (__fastcall **)(DdmDevice *, __int64, _BYTE *, _DWORD *))(v15 + 416))(this, 13, v28, v19);
  v16 = (unsigned __int16)*((_DWORD *)this + 34);
  if ( v16 == 15 )
    return ((__int64 (__fastcall *)(__int64 *))qword_1800C7518)(&v20);
  v18 = (__int64 (__fastcall *)(__int64 *))qword_1800C74C8[0];
  if ( v16 == 16 )
    v18 = (__int64 (__fastcall *)(__int64 *))qword_1800C7568;
  return v18(&v20);
}

```

## disassembly

```asm
0x1800387dc  push    rbp
0x1800387de  push    rbx
0x1800387df  push    rsi
0x1800387e0  push    rdi
0x1800387e1  push    r14
0x1800387e3  push    r15
0x1800387e5  lea     rbp, [rsp-23A8h]
0x1800387ed  mov     eax, 24A8h
0x1800387f2  call    _alloca_probe
0x1800387f7  sub     rsp, rax
0x1800387fa  mov     rax, cs:__security_cookie
0x180038801  xor     rax, rsp
0x180038804  mov     [rbp+23D0h+var_40], rax
0x18003880b  mov     r14d, r8d
0x18003880e  mov     r15, rdx
0x180038811  mov     rsi, rcx
0x180038814  mov     [rsp+24D0h+var_2480], 8
0x18003881d  xor     edx, edx; Val
0x18003881f  mov     [rsp+24D0h+var_2478], 0
0x180038828  mov     r8d, 1BD0h; Size
0x18003882e  lea     rcx, [rsp+24D0h+var_2470]; void *
0x180038833  mov     edi, r9d
0x180038836  call    memset_0
0x18003883b  xor     eax, eax
0x18003883d  mov     [rsp+24D0h+var_2490], 0
0x180038845  xor     edx, edx; Val
0x180038847  mov     [rbp+23D0h+var_840], eax
0x18003884d  mov     r8d, 7FCh; Size
0x180038853  lea     rcx, [rbp+23D0h+var_83C]; void *
0x18003885a  call    memset_0
0x18003885f  mov     cl, cs:byte_1800C8404
0x180038865  xor     eax, eax
0x180038867  mov     dword ptr [rbp+23D0h+Buffer], eax
0x18003886d  xorps   xmm0, xmm0
0x180038870  mov     [rbp+23D0h+var_84C], eax
0x180038876  movups  [rbp+23D0h+var_86C], xmm0
0x18003887d  movups  [rbp+23D0h+var_85C], xmm0
0x180038884  movups  [rbp+23D0h+var_8A0], xmm0
0x18003888b  test    cl, 10h
0x18003888e  jz      loc_18003892B
0x180038894  mov     word ptr [rbp+23D0h+var_840], ax
0x18003889b  lea     rbx, [rsi+60h]
0x18003889f  mov     [rbp+23D0h+Buffer], ax
0x1800388a6  test    rsi, rsi
0x1800388a9  jz      short loc_1800388C7
0x1800388ab  cmp     dword ptr [rbx], 0FFFFFFFFh
0x1800388ae  jz      short loc_1800388C7
0x1800388b0  mov     ecx, [rbx]; Value
0x1800388b2  lea     r9d, [rax+0Ah]; Radix
0x1800388b6  lea     r8d, [rax+14h]; BufferCount
0x1800388ba  lea     rdx, [rbp+23D0h+Buffer]; Buffer
0x1800388c1  call    cs:__imp__itow_s
0x1800388c7  mov     r9, [rbx]
0x1800388ca  lea     r8, aDdmdeviceSendd; "DdmDevice::SendDdmStartToProtocolEngine"
0x1800388d1  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x1800388d8  lea     rcx, [rbp+23D0h+var_840]
0x1800388df  call    FormatRRASErrorString
0x1800388e4  mov     cl, cs:byte_1800C8404
0x1800388ea  test    cl, 10h
0x1800388ed  jz      short loc_18003892B
0x1800388ef  lea     rax, [rbp+23D0h+Buffer]
0x1800388f6  mov     qword ptr [rsp+24D0h+cbMultiByte], rax
0x1800388fb  lea     r9, [rbp+23D0h+var_8A0]
0x180038902  lea     r8, [rbp+23D0h+var_840]
0x180038909  mov     [rsp+24D0h+lpMultiByteStr], 0
0x180038912  lea     rdx, RasDdmParamTraceInfo
0x180038919  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038920  call    McTemplateU0zjzz_EventWriteTransfer
0x180038925  mov     cl, cs:byte_1800C8404
0x18003892b  test    dword ptr [rsi+84h], 20000h
0x180038935  mov     rax, [rsi+60h]
0x180038939  mov     [rsp+24D0h+var_2478], rax
0x18003893e  mov     dword ptr [rsp+24D0h+var_2480], 8
0x180038946  mov     [rsp+24D0h+var_2468], edi
0x18003894a  jz      loc_180038ABC
0x180038950  or      [rbp+23D0h+var_1E38], 40h
0x180038957  xorps   xmm0, xmm0
0x18003895a  movups  xmmword ptr [rbp+23D0h+plpwsSubStrings], xmm0
0x180038961  movups  [rbp+23D0h+var_880], xmm0
0x180038968  test    cl, 10h
0x18003896b  jz      loc_1800389F7
0x180038971  mov     ecx, [rsi+60h]; Value
0x180038974  xor     eax, eax
0x180038976  mov     word ptr [rbp+23D0h+var_840], ax
0x18003897d  mov     [rbp+23D0h+Buffer], ax
0x180038984  cmp     ecx, 0FFFFFFFFh
0x180038987  jz      short loc_18003899E
0x180038989  lea     r9d, [rax+0Ah]; Radix
0x18003898d  lea     r8d, [rax+14h]; BufferCount
0x180038991  lea     rdx, [rbp+23D0h+Buffer]; Buffer
0x180038998  call    cs:__imp__itow_s
0x18003899e  lea     r8, [rsi+2CAh]
0x1800389a5  lea     rdx, aSendddmstartto; "SendDdmStartToProtocolEngine: Port: %ws"...
0x1800389ac  lea     rcx, [rbp+23D0h+var_840]
0x1800389b3  call    FormatRRASErrorString
0x1800389b8  test    cs:byte_1800C8404, 10h
0x1800389bf  jz      short loc_1800389F7
0x1800389c1  lea     rax, [rbp+23D0h+Buffer]
0x1800389c8  mov     qword ptr [rsp+24D0h+cbMultiByte], rax
0x1800389cd  lea     r9, [rbp+23D0h+var_8A0]
0x1800389d4  lea     r8, [rbp+23D0h+var_840]
0x1800389db  mov     [rsp+24D0h+lpMultiByteStr], 0
0x1800389e4  lea     rdx, RasDdmParamTraceInfo
0x1800389eb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800389f2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800389f7  lea     rax, [rsi+444h]
0x1800389fe  mov     ecx, 4; wEventType
0x180038a03  mov     [rbp+23D0h+plpwsSubStrings], rax
0x180038a0a  lea     rdi, [rsi+2AAh]
0x180038a11  lea     rax, [rsi+2CAh]
0x180038a18  mov     [rbp+23D0h+plpwsSubStrings+8], rdi
0x180038a1f  lea     rbx, [rsi+0A8h]
0x180038a26  mov     qword ptr [rbp+23D0h+var_880+8], rax
0x180038a2d  lea     r9, [rbp+23D0h+plpwsSubStrings]; plpwsSubStrings
0x180038a34  mov     qword ptr [rbp+23D0h+var_880], rbx
0x180038a3b  mov     r8d, ecx; cNumberOfSubStrings
0x180038a3e  mov     edx, 4F37h; dwMessageId
0x180038a43  call    cs:__imp_LogEventW
0x180038a49  mov     [rsp+24D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180038a52  lea     rax, [rbp+23D0h+MultiByteStr]
0x180038a59  mov     r8, rbx; lpWideCharStr
0x180038a5c  mov     [rsp+24D0h+lpDefaultChar], 0; lpDefaultChar
0x180038a65  mov     ebx, 400h
0x180038a6a  mov     [rsp+24D0h+cbMultiByte], 101h; cbMultiByte
0x180038a72  mov     edx, ebx; dwFlags
0x180038a74  mov     [rsp+24D0h+lpMultiByteStr], rax; lpMultiByteStr
0x180038a79  or      r9d, 0FFFFFFFFh; cchWideChar
0x180038a7d  xor     ecx, ecx; CodePage
0x180038a7f  call    cs:__imp_WideCharToMultiByte
0x180038a85  mov     [rsp+24D0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180038a8e  lea     rax, [rbp+23D0h+var_1D33]
0x180038a95  mov     [rsp+24D0h+lpDefaultChar], 0; lpDefaultChar
0x180038a9e  or      r9d, 0FFFFFFFFh; cchWideChar
0x180038aa2  mov     [rsp+24D0h+cbMultiByte], 10h; cbMultiByte
0x180038aaa  mov     r8, rdi; lpWideCharStr
0x180038aad  mov     edx, ebx; dwFlags
0x180038aaf  mov     [rsp+24D0h+lpMultiByteStr], rax; lpMultiByteStr
0x180038ab4  xor     ecx, ecx; CodePage
0x180038ab6  call    cs:__imp_WideCharToMultiByte
0x180038abc  lea     rdx, [rsi+2CAh]; Source
0x180038ac3  mov     r8d, 11h; MaxCount
0x180038ac9  lea     rcx, [rsp+24D0h+Dest]; Dest
0x180038ace  call    cs:__imp_wcstombs
0x180038ad4  test    r15, r15
0x180038ad7  jz      short loc_180038AF5
0x180038ad9  test    r14d, r14d
0x180038adc  jz      short loc_180038AF5
0x180038ade  mov     r8, r14; Size
0x180038ae1  lea     rcx, [rsp+24D0h+var_2453]; void *
0x180038ae6  mov     rdx, r15; Src
0x180038ae9  call    memcpy_0
0x180038aee  mov     [rbp+23D0h+var_1E74], r14d
0x180038af5  mov     rax, [rsi]
0x180038af8  lea     r9, [rsp+24D0h+var_2490]
0x180038afd  movups  xmm0, xmmword ptr [rsi+434h]
0x180038b04  lea     r8, [rbp+23D0h+var_1E70]
0x180038b0b  mov     [rsp+24D0h+var_2490], 14h
0x180038b13  mov     edx, 0Ch
0x180038b18  mov     rcx, rsi
0x180038b1b  mov     rax, [rax+1A0h]
0x180038b22  movdqu  [rbp+23D0h+var_1E48], xmm0
0x180038b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b2f  mov     rax, [rsi]
0x180038b32  lea     r9, [rsp+24D0h+var_2490]
0x180038b37  lea     r8, [rbp+23D0h+var_1E5C]
0x180038b3e  mov     [rsp+24D0h+var_2490], 14h
0x180038b46  mov     edx, 0Dh
0x180038b4b  mov     rcx, rsi
0x180038b4e  mov     rax, [rax+1A0h]
0x180038b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b5a  mov     ecx, [rsi+88h]
0x180038b60  movzx   ecx, cx
0x180038b63  cmp     ecx, 0Fh
0x180038b66  jnz     short loc_180038B71
0x180038b68  mov     rax, cs:qword_1800C7518
0x180038b6f  jmp     short loc_180038B83
0x180038b71  mov     rax, cs:qword_1800C74C8
0x180038b78  cmp     ecx, 10h
0x180038b7b  cmovz   rax, cs:qword_1800C7568
0x180038b83  lea     rcx, [rsp+24D0h+var_2480]
0x180038b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b8d  mov     rcx, [rbp+23D0h+var_40]
0x180038b94  xor     rcx, rsp; StackCookie
0x180038b97  call    __security_check_cookie
0x180038b9c  add     rsp, 24A8h
0x180038ba3  pop     r15
0x180038ba5  pop     r14
0x180038ba7  pop     rdi
0x180038ba8  pop     rsi
0x180038ba9  pop     rbx
0x180038baa  pop     rbp
0x180038bab  retn
```
