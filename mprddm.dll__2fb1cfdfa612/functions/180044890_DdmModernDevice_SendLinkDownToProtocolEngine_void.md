# DdmModernDevice::SendLinkDownToProtocolEngine(void)

- ea: `0x180044890`
- end: `0x180044b8d`
- name: `?SendLinkDownToProtocolEngine@DdmModernDevice@@QEAAXXZ`
- size: `765`
- prototype: `void __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003dea0`
- `0x18003f510`

## callees

- `0x180007c50`
- `0x180044890`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180044963`
- `msvcrt!_itow_s` at `0x180044a70`
- `msvcrt!_itow_s` at `0x180044b0d`
- `msvcrt!_itow_s` at `0x180044963`
- `msvcrt!_itow_s` at `0x180044a70`
- `msvcrt!_itow_s` at `0x180044b0d`

## string_xrefs

- `0x18004496f`: `DdmModernDevice::SendLinkDownToProtocolEngine`
- `0x180044979`: `%s: (hport: %ld, ProtocolEngineReceiveFlags: 0x%x)`
- `0x180044a7a`: `SendLinkDownToProtocolEngine: SendMessageToProtocolEngine(PROTOCOL_MSG_LineDown) on hPort:%ld returned 0x%x`
- `0x180044b17`: `Skipping PROTOCOL_MSG_LineDown for hPort:%d as protocol was not started.`

## pseudocode

```c
void __fastcall DdmModernDevice::SendLinkDownToProtocolEngine(DdmModernDevice *this)
{
  char v2; // al
  int *v3; // rdi
  __int64 v4; // rax
  int v5; // ecx
  unsigned int v6; // eax
  __int64 (__fastcall *v7)(__int64 *); // rax
  unsigned int v8; // edi
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h]
  __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  int v14; // [rsp+48h] [rbp-B8h]
  __int128 v15; // [rsp+1C10h] [rbp+1B10h] BYREF
  wchar_t Buffer[2]; // [rsp+1C20h] [rbp+1B20h] BYREF
  __int128 v17; // [rsp+1C24h] [rbp+1B24h]
  __int128 v18; // [rsp+1C34h] [rbp+1B34h]
  int v19; // [rsp+1C44h] [rbp+1B44h]
  int v20; // [rsp+1C50h] [rbp+1B50h] BYREF
  _BYTE v21[2044]; // [rsp+1C54h] [rbp+1B54h] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v11 = 6;
  *(_DWORD *)Buffer = 0;
  v19 = 0;
  v12 = 0;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  memset_0(&v13, 0, 0x1BD0u);
  v2 = byte_1800C8404;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    v3 = (int *)((char *)this + 96);
    LOWORD(v20) = 0;
    Buffer[0] = 0;
    if ( this && *v3 != -1 )
      _itow_s(*v3, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v20,
      L"%s: (hport: %ld, ProtocolEngineReceiveFlags: 0x%x)",
      L"DdmModernDevice::SendLinkDownToProtocolEngine",
      *(_QWORD *)v3,
      *((_DWORD *)this + 2864));
    v2 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v20,
        (unsigned int)&v15,
        0,
        (__int64)Buffer);
      v2 = byte_1800C8404;
    }
  }
  if ( (*((_BYTE *)this + 11456) & 0x24) != 0 )
  {
    v4 = *((_QWORD *)this + 12);
    v5 = (unsigned __int16)*((_DWORD *)this + 34);
    LODWORD(v11) = 6;
    v12 = v4;
    v13 = 0;
    v14 = 0;
    if ( v5 == 15 )
    {
      v6 = ((__int64 (__fastcall *)(__int64 *))qword_1800C7518)(&v11);
    }
    else
    {
      v7 = (__int64 (__fastcall *)(__int64 *))qword_1800C74C8[0];
      if ( v5 == 16 )
        v7 = (__int64 (__fastcall *)(__int64 *))qword_1800C7568;
      v6 = v7(&v11);
    }
    v8 = v6;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      LOWORD(v20) = 0;
      Buffer[0] = 0;
      v9 = *((_DWORD *)this + 24);
      if ( v9 != -1 )
        _itow_s(v9, Buffer, 0x14u, 10);
      FormatRRASErrorString(
        &v20,
        L"SendLinkDownToProtocolEngine: SendMessageToProtocolEngine(PROTOCOL_MSG_LineDown) on hPort:%ld returned 0x%x",
        *((_QWORD *)this + 12),
        v8);
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v20,
          (unsigned int)&v15,
          0,
          (__int64)Buffer);
    }
    *((_DWORD *)this + 2864) = 0;
  }
  else if ( (v2 & 0x10) != 0 )
  {
    v10 = *((_DWORD *)this + 24);
    LOWORD(v20) = 0;
    Buffer[0] = 0;
    if ( v10 != -1 )
      _itow_s(v10, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v20,
      L"Skipping PROTOCOL_MSG_LineDown for hPort:%d as protocol was not started.",
      *((_QWORD *)this + 12));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v20,
        (unsigned int)&v15,
        0,
        (__int64)Buffer);
  }
}

```

## disassembly

```asm
0x180044890  mov     [rsp-8+arg_8], rbx
0x180044895  mov     [rsp-8+arg_10], rdi
0x18004489a  push    rbp
0x18004489b  lea     rbp, [rsp-2360h]
0x1800448a3  mov     eax, 2460h
0x1800448a8  call    _alloca_probe
0x1800448ad  sub     rsp, rax
0x1800448b0  mov     rax, cs:__security_cookie
0x1800448b7  xor     rax, rsp
0x1800448ba  mov     [rbp+2360h+var_10], rax
0x1800448c1  mov     rbx, rcx
0x1800448c4  xor     eax, eax
0x1800448c6  lea     rcx, [rbp+2360h+var_80C]; void *
0x1800448cd  mov     [rbp+2360h+var_810], eax
0x1800448d3  xor     edx, edx; Val
0x1800448d5  mov     r8d, 7FCh; Size
0x1800448db  call    memset_0
0x1800448e0  xor     eax, eax
0x1800448e2  mov     [rsp+2460h+var_2430], 6
0x1800448eb  xorps   xmm0, xmm0
0x1800448ee  mov     dword ptr [rbp+2360h+Buffer], eax
0x1800448f4  xor     edx, edx; Val
0x1800448f6  mov     [rbp+2360h+var_81C], eax
0x1800448fc  mov     r8d, 1BD0h; Size
0x180044902  mov     [rsp+2460h+var_2428], rax
0x180044907  lea     rcx, [rsp+2460h+var_2420]; void *
0x18004490c  movups  [rbp+2360h+var_83C], xmm0
0x180044913  movups  [rbp+2360h+var_82C], xmm0
0x18004491a  movups  [rbp+2360h+var_850], xmm0
0x180044921  call    memset_0
0x180044926  mov     al, cs:byte_1800C8404
0x18004492c  test    al, 10h
0x18004492e  jz      loc_1800449D6
0x180044934  xor     eax, eax
0x180044936  lea     rdi, [rbx+60h]
0x18004493a  mov     word ptr [rbp+2360h+var_810], ax
0x180044941  mov     [rbp+2360h+Buffer], ax
0x180044948  test    rbx, rbx
0x18004494b  jz      short loc_180044969
0x18004494d  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180044950  jz      short loc_180044969
0x180044952  mov     ecx, [rdi]; Value
0x180044954  lea     r9d, [rax+0Ah]; Radix
0x180044958  lea     r8d, [rax+14h]; BufferCount
0x18004495c  lea     rdx, [rbp+2360h+Buffer]; Buffer
0x180044963  call    cs:__imp__itow_s
0x180044969  mov     eax, [rbx+2CC0h]
0x18004496f  lea     r8, aDdmmoderndevic_34; "DdmModernDevice::SendLinkDownToProtocol"...
0x180044976  mov     r9, [rdi]
0x180044979  lea     rdx, aSHportLdProtoc; "%s: (hport: %ld, ProtocolEngineReceiveF"...
0x180044980  lea     rcx, [rbp+2360h+var_810]
0x180044987  mov     dword ptr [rsp+2460h+var_2440], eax
0x18004498b  call    FormatRRASErrorString
0x180044990  mov     al, cs:byte_1800C8404
0x180044996  test    al, 10h
0x180044998  jz      short loc_1800449D6
0x18004499a  lea     rax, [rbp+2360h+Buffer]
0x1800449a1  mov     [rsp+2460h+var_2438], rax
0x1800449a6  lea     r9, [rbp+2360h+var_850]
0x1800449ad  lea     r8, [rbp+2360h+var_810]
0x1800449b4  mov     [rsp+2460h+var_2440], 0
0x1800449bd  lea     rdx, RasDdmParamTraceInfo
0x1800449c4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800449cb  call    McTemplateU0zjzz_EventWriteTransfer
0x1800449d0  mov     al, cs:byte_1800C8404
0x1800449d6  test    byte ptr [rbx+2CC0h], 24h
0x1800449dd  jz      loc_180044ADE
0x1800449e3  mov     ecx, [rbx+88h]
0x1800449e9  mov     rax, [rbx+60h]
0x1800449ed  movzx   ecx, cx
0x1800449f0  mov     dword ptr [rsp+2460h+var_2430], 6
0x1800449f8  mov     [rsp+2460h+var_2428], rax
0x1800449fd  mov     [rsp+2460h+var_2420], 0
0x180044a06  mov     [rsp+2460h+var_2418], 0
0x180044a0e  cmp     ecx, 0Fh
0x180044a11  jnz     short loc_180044A1C
0x180044a13  mov     rax, cs:qword_1800C7518
0x180044a1a  jmp     short loc_180044A2E
0x180044a1c  mov     rax, cs:qword_1800C74C8
0x180044a23  cmp     ecx, 10h
0x180044a26  cmovz   rax, cs:qword_1800C7568
0x180044a2e  lea     rcx, [rsp+2460h+var_2430]
0x180044a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044a38  test    cs:byte_1800C8404, 10h
0x180044a3f  mov     edi, eax
0x180044a41  jz      loc_180044ACF
0x180044a47  xor     ecx, ecx
0x180044a49  mov     word ptr [rbp+2360h+var_810], cx
0x180044a50  mov     [rbp+2360h+Buffer], cx
0x180044a57  mov     ecx, [rbx+60h]; Value
0x180044a5a  cmp     ecx, 0FFFFFFFFh
0x180044a5d  jz      short loc_180044A76
0x180044a5f  mov     r9d, 0Ah; Radix
0x180044a65  lea     rdx, [rbp+2360h+Buffer]; Buffer
0x180044a6c  lea     r8d, [r9+0Ah]; BufferCount
0x180044a70  call    cs:__imp__itow_s
0x180044a76  mov     r8, [rbx+60h]
0x180044a7a  lea     rdx, aSendlinkdownto; "SendLinkDownToProtocolEngine: SendMessa"...
0x180044a81  mov     r9d, edi
0x180044a84  lea     rcx, [rbp+2360h+var_810]
0x180044a8b  call    FormatRRASErrorString
0x180044a90  test    cs:byte_1800C8404, 10h
0x180044a97  jz      short loc_180044ACF
0x180044a99  lea     rax, [rbp+2360h+Buffer]
0x180044aa0  mov     [rsp+2460h+var_2438], rax
0x180044aa5  lea     r9, [rbp+2360h+var_850]
0x180044aac  lea     r8, [rbp+2360h+var_810]
0x180044ab3  mov     [rsp+2460h+var_2440], 0
0x180044abc  lea     rdx, RasDdmParamTraceInfo
0x180044ac3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044aca  call    McTemplateU0zjzz_EventWriteTransfer
0x180044acf  mov     dword ptr [rbx+2CC0h], 0
0x180044ad9  jmp     loc_180044B69
0x180044ade  test    al, 10h
0x180044ae0  jz      loc_180044B69
0x180044ae6  mov     ecx, [rbx+60h]; Value
0x180044ae9  xor     eax, eax
0x180044aeb  mov     word ptr [rbp+2360h+var_810], ax
0x180044af2  mov     [rbp+2360h+Buffer], ax
0x180044af9  cmp     ecx, 0FFFFFFFFh
0x180044afc  jz      short loc_180044B13
0x180044afe  lea     r9d, [rax+0Ah]; Radix
0x180044b02  lea     r8d, [rax+14h]; BufferCount
0x180044b06  lea     rdx, [rbp+2360h+Buffer]; Buffer
0x180044b0d  call    cs:__imp__itow_s
0x180044b13  mov     r8, [rbx+60h]
0x180044b17  lea     rdx, aSkippingProtoc; "Skipping PROTOCOL_MSG_LineDown for hPor"...
0x180044b1e  lea     rcx, [rbp+2360h+var_810]
0x180044b25  call    FormatRRASErrorString
0x180044b2a  test    cs:byte_1800C8404, 10h
0x180044b31  jz      short loc_180044B69
0x180044b33  lea     rax, [rbp+2360h+Buffer]
0x180044b3a  mov     [rsp+2460h+var_2438], rax
0x180044b3f  lea     r9, [rbp+2360h+var_850]
0x180044b46  lea     r8, [rbp+2360h+var_810]
0x180044b4d  mov     [rsp+2460h+var_2440], 0
0x180044b56  lea     rdx, RasDdmParamTraceInfo
0x180044b5d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180044b64  call    McTemplateU0zjzz_EventWriteTransfer
0x180044b69  mov     rcx, [rbp+2360h+var_10]
0x180044b70  xor     rcx, rsp; StackCookie
0x180044b73  call    __security_check_cookie
0x180044b78  lea     r11, [rsp+2460h+var_s0]
0x180044b80  mov     rbx, [r11+18h]
0x180044b84  mov     rdi, [r11+20h]
0x180044b88  mov     rsp, r11
0x180044b8b  pop     rbp
0x180044b8c  retn
```
