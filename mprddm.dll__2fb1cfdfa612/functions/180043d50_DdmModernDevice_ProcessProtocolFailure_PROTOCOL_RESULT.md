# DdmModernDevice::ProcessProtocolFailure(_PROTOCOL_RESULT *)

- ea: `0x180043d50`
- end: `0x180043f25`
- name: `?ProcessProtocolFailure@DdmModernDevice@@UEAAKPEAU_PROTOCOL_RESULT@@@Z`
- size: `469`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, struct _PROTOCOL_RESULT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180043d50`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180043dfc`
- `msvcrt!_itow_s` at `0x180043e8a`
- `msvcrt!_itow_s` at `0x180043dfc`
- `msvcrt!_itow_s` at `0x180043e8a`

## string_xrefs

- `0x180043e05`: `DdmModernDevice::ProcessProtocolFailure`
- `0x180043e94`: `DdmModernDevice::ProcessProtocolFailure`
- `0x180043e10`: `%s: protocol engine failed (hport: %ld): Error: %d`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::ProcessProtocolFailure(DdmModernDevice *this, struct _PROTOCOL_RESULT *a2)
{
  unsigned int v4; // esi
  bool v5; // zf
  char v6; // al
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rdx
  int v11; // [rsp+20h] [rbp-E0h]
  __int128 v12; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+44h] [rbp-BCh]
  __int128 v15; // [rsp+54h] [rbp-ACh]
  int v16; // [rsp+64h] [rbp-9Ch]
  int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v4 = *((_DWORD *)a2 + 16);
  *((_DWORD *)this + 2864) |= 0x10u;
  v5 = *((_DWORD *)this + 32) == 2;
  *(_DWORD *)Buffer = 0;
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v12 = 0;
  if ( v5 )
    *((_DWORD *)this + 33) |= 0x100000u;
  v6 = byte_1800C8404;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v7 = *((_DWORD *)this + 24);
    LOWORD(v17) = 0;
    Buffer[0] = 0;
    if ( v7 != -1 )
      _itow_s(v7, Buffer, 0x14u, 10);
    v11 = *((_DWORD *)a2 + 2);
    FormatRRASErrorString(
      &v17,
      L"%s: protocol engine failed (hport: %ld): Error: %d",
      L"DdmModernDevice::ProcessProtocolFailure",
      *((_QWORD *)this + 12),
      v11);
    v6 = byte_1800C8404;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v17,
        (unsigned int)&v12,
        0,
        (__int64)Buffer);
      v6 = byte_1800C8404;
    }
  }
  if ( (v6 & 0x10) != 0 )
  {
    v8 = *((_DWORD *)this + 24);
    LOWORD(v17) = 0;
    Buffer[0] = 0;
    if ( v8 != -1 )
      _itow_s(v8, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v17,
      L"%s: disconnecting... (hport: %ld)",
      L"DdmModernDevice::ProcessProtocolFailure",
      *((_QWORD *)this + 12));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v17,
        (unsigned int)&v12,
        0,
        (__int64)Buffer);
  }
  v9 = *(_QWORD *)this;
  *((_DWORD *)this + 2780) = 8193;
  (*(void (__fastcall **)(DdmModernDevice *))(v9 + 504))(this);
  return v4;
}

```

## disassembly

```asm
0x180043d50  mov     [rsp-8+arg_10], rbx
0x180043d55  push    rbp
0x180043d56  push    rsi
0x180043d57  push    rdi
0x180043d58  lea     rbp, [rsp-780h]
0x180043d60  sub     rsp, 880h
0x180043d67  mov     rax, cs:__security_cookie
0x180043d6e  xor     rax, rsp
0x180043d71  mov     [rbp+790h+var_20], rax
0x180043d78  mov     rdi, rdx
0x180043d7b  mov     rbx, rcx
0x180043d7e  xor     eax, eax
0x180043d80  lea     rcx, [rsp+890h+var_81C]; void *
0x180043d85  xor     edx, edx; Val
0x180043d87  mov     [rsp+890h+var_820], eax
0x180043d8b  mov     r8d, 7FCh; Size
0x180043d91  call    memset_0
0x180043d96  mov     esi, [rdi+40h]
0x180043d99  xor     eax, eax
0x180043d9b  or      dword ptr [rbx+2CC0h], 10h
0x180043da2  xorps   xmm0, xmm0
0x180043da5  cmp     dword ptr [rbx+80h], 2
0x180043dac  mov     dword ptr [rsp+890h+Buffer], eax
0x180043db0  movups  [rsp+890h+var_84C], xmm0
0x180043db5  mov     [rsp+890h+var_82C], eax
0x180043db9  movups  [rsp+890h+var_83C], xmm0
0x180043dbe  movups  [rsp+890h+var_860], xmm0
0x180043dc3  jnz     short loc_180043DCD
0x180043dc5  bts     dword ptr [rbx+84h], 14h
0x180043dcd  mov     al, cs:byte_1800C8404
0x180043dd3  test    al, 8
0x180043dd5  jz      loc_180043E65
0x180043ddb  mov     ecx, [rbx+60h]; Value
0x180043dde  xor     eax, eax
0x180043de0  mov     word ptr [rsp+890h+var_820], ax
0x180043de5  mov     [rsp+890h+Buffer], ax
0x180043dea  cmp     ecx, 0FFFFFFFFh
0x180043ded  jz      short loc_180043E02
0x180043def  lea     r9d, [rax+0Ah]; Radix
0x180043df3  lea     r8d, [rax+14h]; BufferCount
0x180043df7  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180043dfc  call    cs:__imp__itow_s
0x180043e02  mov     eax, [rdi+8]
0x180043e05  lea     r8, aDdmmoderndevic_26; "DdmModernDevice::ProcessProtocolFailure"
0x180043e0c  mov     r9, [rbx+60h]
0x180043e10  lea     rdx, aSProtocolEngin_1; "%s: protocol engine failed (hport: %ld)"...
0x180043e17  lea     rcx, [rsp+890h+var_820]
0x180043e1c  mov     dword ptr [rsp+890h+var_870], eax
0x180043e20  call    FormatRRASErrorString
0x180043e25  mov     al, cs:byte_1800C8404
0x180043e2b  test    al, 8
0x180043e2d  jz      short loc_180043E65
0x180043e2f  lea     rax, [rsp+890h+Buffer]
0x180043e34  mov     [rsp+890h+var_868], rax
0x180043e39  lea     r9, [rsp+890h+var_860]
0x180043e3e  lea     r8, [rsp+890h+var_820]
0x180043e43  mov     [rsp+890h+var_870], 0
0x180043e4c  lea     rdx, RasDdmParamTraceError
0x180043e53  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043e5a  call    McTemplateU0zjzz_EventWriteTransfer
0x180043e5f  mov     al, cs:byte_1800C8404
0x180043e65  test    al, 10h
0x180043e67  jz      short loc_180043EE5
0x180043e69  mov     ecx, [rbx+60h]; Value
0x180043e6c  xor     eax, eax
0x180043e6e  mov     word ptr [rsp+890h+var_820], ax
0x180043e73  mov     [rsp+890h+Buffer], ax
0x180043e78  cmp     ecx, 0FFFFFFFFh
0x180043e7b  jz      short loc_180043E90
0x180043e7d  lea     r9d, [rax+0Ah]; Radix
0x180043e81  lea     r8d, [rax+14h]; BufferCount
0x180043e85  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180043e8a  call    cs:__imp__itow_s
0x180043e90  mov     r9, [rbx+60h]
0x180043e94  lea     r8, aDdmmoderndevic_26; "DdmModernDevice::ProcessProtocolFailure"
0x180043e9b  lea     rdx, aSDisconnecting; "%s: disconnecting... (hport: %ld)"
0x180043ea2  lea     rcx, [rsp+890h+var_820]
0x180043ea7  call    FormatRRASErrorString
0x180043eac  test    cs:byte_1800C8404, 10h
0x180043eb3  jz      short loc_180043EE5
0x180043eb5  lea     rax, [rsp+890h+Buffer]
0x180043eba  mov     [rsp+890h+var_868], rax
0x180043ebf  lea     r9, [rsp+890h+var_860]
0x180043ec4  lea     r8, [rsp+890h+var_820]
0x180043ec9  mov     [rsp+890h+var_870], 0
0x180043ed2  lea     rdx, RasDdmParamTraceInfo
0x180043ed9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043ee0  call    McTemplateU0zjzz_EventWriteTransfer
0x180043ee5  mov     rdx, [rbx]
0x180043ee8  mov     rcx, rbx
0x180043eeb  mov     dword ptr [rbx+2B70h], 2001h
0x180043ef5  mov     rax, [rdx+1F8h]
0x180043efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f01  mov     eax, esi
0x180043f03  mov     rcx, [rbp+790h+var_20]
0x180043f0a  xor     rcx, rsp; StackCookie
0x180043f0d  call    __security_check_cookie
0x180043f12  mov     rbx, [rsp+890h+arg_10]
0x180043f1a  add     rsp, 880h
0x180043f21  pop     rdi
0x180043f22  pop     rsi
0x180043f23  pop     rbp
0x180043f24  retn
```
