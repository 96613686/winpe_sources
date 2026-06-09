# DdmDevice::ProtocolStopped(ulong)

- ea: `0x180037d60`
- end: `0x180037f29`
- name: `?ProtocolStopped@DdmDevice@@UEAAXK@Z`
- size: `457`
- prototype: `void __fastcall(DdmDevice *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180037d60`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180037df8`
- `msvcrt!_itow_s` at `0x180037eaf`
- `msvcrt!_itow_s` at `0x180037df8`
- `msvcrt!_itow_s` at `0x180037eaf`

## string_xrefs

- `0x180037e01`: `DdmDevice::ProtocolStopped`
- `0x180037e08`: `%s: Protocol engine stopped (hport: %ld)`
- `0x180037eb9`: `Ignoring PROTOCOL_RESSRV_Stopped notification for port: %ld, state: %d`

## pseudocode

```c
void __fastcall DdmDevice::ProtocolStopped(DdmDevice *this, unsigned int a2)
{
  char v4; // al
  int *v5; // rdi
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v9; // [rsp+44h] [rbp-BCh]
  __int128 v10; // [rsp+54h] [rbp-ACh]
  int v11; // [rsp+64h] [rbp-9Ch]
  int v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v13[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  *(_DWORD *)Buffer = 0;
  v11 = 0;
  v4 = byte_1800C8404;
  v9 = 0;
  v10 = 0;
  v7 = 0;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v5 = (int *)((char *)this + 96);
    LOWORD(v12) = 0;
    Buffer[0] = 0;
    if ( this && *v5 != -1 )
      _itow_s(*v5, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v12,
      L"%s: Protocol engine stopped (hport: %ld)",
      L"DdmDevice::ProtocolStopped",
      *(_QWORD *)v5);
    v4 = byte_1800C8404;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v12,
        (unsigned int)&v7,
        0,
        (__int64)Buffer);
      v4 = byte_1800C8404;
    }
  }
  if ( *((_DWORD *)this + 26) == 9 || !*((_DWORD *)this + 26) )
  {
    if ( (v4 & 8) != 0 )
    {
      v6 = *((_DWORD *)this + 24);
      LOWORD(v12) = 0;
      Buffer[0] = 0;
      if ( v6 != -1 )
        _itow_s(v6, Buffer, 0x14u, 10);
      FormatRRASErrorString(
        &v12,
        L"Ignoring PROTOCOL_RESSRV_Stopped notification for port: %ld, state: %d",
        *((_QWORD *)this + 12),
        *((unsigned int *)this + 26));
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v12,
          (unsigned int)&v7,
          0,
          (__int64)Buffer);
    }
  }
  else
  {
    (*(void (__fastcall **)(DdmDevice *))(*(_QWORD *)this + 176LL))(this);
    (*(void (__fastcall **)(DdmDevice *, _QWORD))(*(_QWORD *)this + 80LL))(this, a2);
  }
}

```

## disassembly

```asm
0x180037d60  mov     [rsp-8+arg_10], rbx
0x180037d65  push    rbp
0x180037d66  push    rsi
0x180037d67  push    rdi
0x180037d68  lea     rbp, [rsp-780h]
0x180037d70  sub     rsp, 880h
0x180037d77  mov     rax, cs:__security_cookie
0x180037d7e  xor     rax, rsp
0x180037d81  mov     [rbp+790h+var_20], rax
0x180037d88  mov     esi, edx
0x180037d8a  mov     rbx, rcx
0x180037d8d  xor     eax, eax
0x180037d8f  lea     rcx, [rsp+890h+var_81C]; void *
0x180037d94  xor     edx, edx; Val
0x180037d96  mov     [rsp+890h+var_820], eax
0x180037d9a  mov     r8d, 7FCh; Size
0x180037da0  call    memset_0
0x180037da5  xor     eax, eax
0x180037da7  xorps   xmm0, xmm0
0x180037daa  mov     dword ptr [rsp+890h+Buffer], eax
0x180037dae  mov     [rsp+890h+var_82C], eax
0x180037db2  mov     al, cs:byte_1800C8404
0x180037db8  movups  [rsp+890h+var_84C], xmm0
0x180037dbd  movups  [rsp+890h+var_83C], xmm0
0x180037dc2  movups  [rsp+890h+var_860], xmm0
0x180037dc7  test    al, 8
0x180037dc9  jz      loc_180037E59
0x180037dcf  xor     eax, eax
0x180037dd1  lea     rdi, [rbx+60h]
0x180037dd5  mov     word ptr [rsp+890h+var_820], ax
0x180037dda  mov     [rsp+890h+Buffer], ax
0x180037ddf  test    rbx, rbx
0x180037de2  jz      short loc_180037DFE
0x180037de4  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180037de7  jz      short loc_180037DFE
0x180037de9  mov     ecx, [rdi]; Value
0x180037deb  lea     r9d, [rax+0Ah]; Radix
0x180037def  lea     r8d, [rax+14h]; BufferCount
0x180037df3  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180037df8  call    cs:__imp__itow_s
0x180037dfe  mov     r9, [rdi]
0x180037e01  lea     r8, aDdmdeviceProto_3; "DdmDevice::ProtocolStopped"
0x180037e08  lea     rdx, aSProtocolEngin; "%s: Protocol engine stopped (hport: %ld"...
0x180037e0f  lea     rcx, [rsp+890h+var_820]
0x180037e14  call    FormatRRASErrorString
0x180037e19  mov     al, cs:byte_1800C8404
0x180037e1f  test    al, 8
0x180037e21  jz      short loc_180037E59
0x180037e23  lea     rax, [rsp+890h+Buffer]
0x180037e28  mov     [rsp+890h+var_868], rax
0x180037e2d  lea     r9, [rsp+890h+var_860]
0x180037e32  lea     r8, [rsp+890h+var_820]
0x180037e37  mov     [rsp+890h+var_870], 0
0x180037e40  lea     rdx, RasDdmParamTraceError
0x180037e47  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180037e4e  call    McTemplateU0zjzz_EventWriteTransfer
0x180037e53  mov     al, cs:byte_1800C8404
0x180037e59  cmp     dword ptr [rbx+68h], 9
0x180037e5d  jz      short loc_180037E8A
0x180037e5f  cmp     dword ptr [rbx+68h], 0
0x180037e63  jz      short loc_180037E8A
0x180037e65  mov     rax, [rbx]
0x180037e68  mov     rcx, rbx
0x180037e6b  mov     rax, [rax+0B0h]
0x180037e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e77  mov     rax, [rbx]
0x180037e7a  mov     edx, esi
0x180037e7c  mov     rcx, rbx
0x180037e7f  mov     rax, [rax+50h]
0x180037e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e88  jmp     short loc_180037F07
0x180037e8a  test    al, 8
0x180037e8c  jz      short loc_180037F07
0x180037e8e  mov     ecx, [rbx+60h]; Value
0x180037e91  xor     eax, eax
0x180037e93  mov     word ptr [rsp+890h+var_820], ax
0x180037e98  mov     [rsp+890h+Buffer], ax
0x180037e9d  cmp     ecx, 0FFFFFFFFh
0x180037ea0  jz      short loc_180037EB5
0x180037ea2  lea     r9d, [rax+0Ah]; Radix
0x180037ea6  lea     r8d, [rax+14h]; BufferCount
0x180037eaa  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180037eaf  call    cs:__imp__itow_s
0x180037eb5  mov     r9d, [rbx+68h]
0x180037eb9  lea     rdx, aIgnoringProtoc; "Ignoring PROTOCOL_RESSRV_Stopped notifi"...
0x180037ec0  mov     r8, [rbx+60h]
0x180037ec4  lea     rcx, [rsp+890h+var_820]
0x180037ec9  call    FormatRRASErrorString
0x180037ece  test    cs:byte_1800C8404, 8
0x180037ed5  jz      short loc_180037F07
0x180037ed7  lea     rax, [rsp+890h+Buffer]
0x180037edc  mov     [rsp+890h+var_868], rax
0x180037ee1  lea     r9, [rsp+890h+var_860]
0x180037ee6  lea     r8, [rsp+890h+var_820]
0x180037eeb  mov     [rsp+890h+var_870], 0
0x180037ef4  lea     rdx, RasDdmParamTraceError
0x180037efb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180037f02  call    McTemplateU0zjzz_EventWriteTransfer
0x180037f07  mov     rcx, [rbp+790h+var_20]
0x180037f0e  xor     rcx, rsp; StackCookie
0x180037f11  call    __security_check_cookie
0x180037f16  mov     rbx, [rsp+890h+arg_10]
0x180037f1e  add     rsp, 880h
0x180037f25  pop     rdi
0x180037f26  pop     rsi
0x180037f27  pop     rbp
0x180037f28  retn
```
