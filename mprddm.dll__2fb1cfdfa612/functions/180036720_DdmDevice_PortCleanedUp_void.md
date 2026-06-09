# DdmDevice::PortCleanedUp(void)

- ea: `0x180036720`
- end: `0x1800368ea`
- name: `?PortCleanedUp@DdmDevice@@UEAAXXZ`
- size: `458`
- prototype: `void __fastcall(DdmDevice *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180036720`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x1800367b9`
- `msvcrt!_itow_s` at `0x180036872`
- `msvcrt!_itow_s` at `0x1800367b9`
- `msvcrt!_itow_s` at `0x180036872`

## string_xrefs

- `0x1800367c9`: `%s: Stopping protocol engine cleanup done. (hport: %ld)`
- `0x18003687c`: `Ignoring PROTOCOL_RESSRV_PortCleanedUp notification for port: %ld as it is already in listening state`

## pseudocode

```c
void __fastcall DdmDevice::PortCleanedUp(DdmDevice *this)
{
  char v2; // al
  int *v3; // rdi
  __int64 v4; // rax
  int v5; // ecx
  __int128 v6; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v8; // [rsp+44h] [rbp-BCh]
  __int128 v9; // [rsp+54h] [rbp-ACh]
  int v10; // [rsp+64h] [rbp-9Ch]
  int v11; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v12[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v11 = 0;
  memset_0(v12, 0, sizeof(v12));
  *(_DWORD *)Buffer = 0;
  v10 = 0;
  v2 = byte_1800C8404;
  v8 = 0;
  v9 = 0;
  v6 = 0;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    v3 = (int *)((char *)this + 96);
    LOWORD(v11) = 0;
    Buffer[0] = 0;
    if ( this && *v3 != -1 )
      _itow_s(*v3, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v11,
      L"%s: Stopping protocol engine cleanup done. (hport: %ld)",
      L"DdmDevice::PortCleanedUp",
      *(_QWORD *)v3);
    v2 = byte_1800C8404;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v11,
        (unsigned int)&v6,
        0,
        (__int64)Buffer);
      v2 = byte_1800C8404;
    }
  }
  if ( *((_DWORD *)this + 26) )
  {
    *((_DWORD *)this + 33) &= 0xFFFFAFFF;
    v4 = *(_QWORD *)this;
    if ( *((_DWORD *)this + 26) == 9 )
      (*(void (__fastcall **)(DdmDevice *))(v4 + 184))(this);
    else
      (*(void (__fastcall **)(DdmDevice *))(v4 + 176))(this);
  }
  else if ( (v2 & 8) != 0 )
  {
    v5 = *((_DWORD *)this + 24);
    LOWORD(v11) = 0;
    Buffer[0] = 0;
    if ( v5 != -1 )
      _itow_s(v5, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v11,
      L"Ignoring PROTOCOL_RESSRV_PortCleanedUp notification for port: %ld as it is already in listening state",
      *((_QWORD *)this + 12));
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v11,
        (unsigned int)&v6,
        0,
        (__int64)Buffer);
  }
}

```

## disassembly

```asm
0x180036720  mov     [rsp-8+arg_8], rbx
0x180036725  mov     [rsp-8+arg_10], rdi
0x18003672a  push    rbp
0x18003672b  lea     rbp, [rsp-780h]
0x180036733  sub     rsp, 880h
0x18003673a  mov     rax, cs:__security_cookie
0x180036741  xor     rax, rsp
0x180036744  mov     [rbp+780h+var_10], rax
0x18003674b  mov     rbx, rcx
0x18003674e  xor     eax, eax
0x180036750  lea     rcx, [rsp+880h+var_80C]; void *
0x180036755  mov     [rsp+880h+var_810], eax
0x180036759  xor     edx, edx; Val
0x18003675b  mov     r8d, 7FCh; Size
0x180036761  call    memset_0
0x180036766  xor     eax, eax
0x180036768  xorps   xmm0, xmm0
0x18003676b  mov     dword ptr [rsp+880h+Buffer], eax
0x18003676f  mov     [rsp+880h+var_81C], eax
0x180036773  mov     al, cs:byte_1800C8404
0x180036779  movups  [rsp+880h+var_83C], xmm0
0x18003677e  movups  [rsp+880h+var_82C], xmm0
0x180036783  movups  [rsp+880h+var_850], xmm0
0x180036788  test    al, 8
0x18003678a  jz      loc_18003681A
0x180036790  xor     eax, eax
0x180036792  lea     rdi, [rbx+60h]
0x180036796  mov     word ptr [rsp+880h+var_810], ax
0x18003679b  mov     [rsp+880h+Buffer], ax
0x1800367a0  test    rbx, rbx
0x1800367a3  jz      short loc_1800367BF
0x1800367a5  cmp     dword ptr [rdi], 0FFFFFFFFh
0x1800367a8  jz      short loc_1800367BF
0x1800367aa  mov     ecx, [rdi]; Value
0x1800367ac  lea     r9d, [rax+0Ah]; Radix
0x1800367b0  lea     r8d, [rax+14h]; BufferCount
0x1800367b4  lea     rdx, [rsp+880h+Buffer]; Buffer
0x1800367b9  call    cs:__imp__itow_s
0x1800367bf  mov     r9, [rdi]
0x1800367c2  lea     r8, aDdmdevicePortc; "DdmDevice::PortCleanedUp"
0x1800367c9  lea     rdx, aSStoppingProto; "%s: Stopping protocol engine cleanup do"...
0x1800367d0  lea     rcx, [rsp+880h+var_810]
0x1800367d5  call    FormatRRASErrorString
0x1800367da  mov     al, cs:byte_1800C8404
0x1800367e0  test    al, 8
0x1800367e2  jz      short loc_18003681A
0x1800367e4  lea     rax, [rsp+880h+Buffer]
0x1800367e9  mov     [rsp+880h+var_858], rax
0x1800367ee  lea     r9, [rsp+880h+var_850]
0x1800367f3  lea     r8, [rsp+880h+var_810]
0x1800367f8  mov     [rsp+880h+var_860], 0
0x180036801  lea     rdx, RasDdmParamTraceError
0x180036808  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003680f  call    McTemplateU0zjzz_EventWriteTransfer
0x180036814  mov     al, cs:byte_1800C8404
0x18003681a  cmp     dword ptr [rbx+68h], 0
0x18003681e  jz      short loc_18003684D
0x180036820  and     dword ptr [rbx+84h], 0FFFFAFFFh
0x18003682a  mov     rcx, rbx
0x18003682d  cmp     dword ptr [rbx+68h], 9
0x180036831  mov     rax, [rbx]
0x180036834  jz      short loc_18003683F
0x180036836  mov     rax, [rax+0B0h]
0x18003683d  jmp     short loc_180036846
0x18003683f  mov     rax, [rax+0B8h]
0x180036846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003684b  jmp     short loc_1800368C6
0x18003684d  test    al, 8
0x18003684f  jz      short loc_1800368C6
0x180036851  mov     ecx, [rbx+60h]; Value
0x180036854  xor     eax, eax
0x180036856  mov     word ptr [rsp+880h+var_810], ax
0x18003685b  mov     [rsp+880h+Buffer], ax
0x180036860  cmp     ecx, 0FFFFFFFFh
0x180036863  jz      short loc_180036878
0x180036865  lea     r9d, [rax+0Ah]; Radix
0x180036869  lea     r8d, [rax+14h]; BufferCount
0x18003686d  lea     rdx, [rsp+880h+Buffer]; Buffer
0x180036872  call    cs:__imp__itow_s
0x180036878  mov     r8, [rbx+60h]
0x18003687c  lea     rdx, aIgnoringProtoc_0; "Ignoring PROTOCOL_RESSRV_PortCleanedUp "...
0x180036883  lea     rcx, [rsp+880h+var_810]
0x180036888  call    FormatRRASErrorString
0x18003688d  test    cs:byte_1800C8404, 8
0x180036894  jz      short loc_1800368C6
0x180036896  lea     rax, [rsp+880h+Buffer]
0x18003689b  mov     [rsp+880h+var_858], rax
0x1800368a0  lea     r9, [rsp+880h+var_850]
0x1800368a5  lea     r8, [rsp+880h+var_810]
0x1800368aa  mov     [rsp+880h+var_860], 0
0x1800368b3  lea     rdx, RasDdmParamTraceError
0x1800368ba  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800368c1  call    McTemplateU0zjzz_EventWriteTransfer
0x1800368c6  mov     rcx, [rbp+780h+var_10]
0x1800368cd  xor     rcx, rsp; StackCookie
0x1800368d0  call    __security_check_cookie
0x1800368d5  lea     r11, [rsp+880h+var_s0]
0x1800368dd  mov     rbx, [r11+18h]
0x1800368e1  mov     rdi, [r11+20h]
0x1800368e5  mov     rsp, r11
0x1800368e8  pop     rbp
0x1800368e9  retn
```
