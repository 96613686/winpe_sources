# QuicPacketKeyCreate

- ea: `0x140008af8`
- end: `0x140008ba4`
- name: `QuicPacketKeyCreate`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140036f1c`

## callees

- `0x140008af8`
- `0x140008bb0`
- `0x140035480`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003fdf8`

## pseudocode

```c
bool __fastcall QuicPacketKeyCreate(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v8; // r9d
  __int64 v9; // rcx
  int v10; // ebx
  _BYTE v12[80]; // [rsp+30h] [rbp-78h] BYREF

  memset(v12, 0, 0x48u);
  if ( (unsigned __int8)CxPlatParseTrafficSecrets(a1, a4, v12) )
  {
    v10 = QuicPacketKeyDerive(a2, *(_QWORD *)(a1 + 40), (unsigned int)v12, v8, 1, a5);
    if ( v10 < 0 )
    {
      LOBYTE(v9) = byte_14005C48D;
      if ( byte_14005C48D < 0 )
        McTemplateU0pqs_EtwWriteTransfer(
          v9,
          (const EVENT_DESCRIPTOR *)QuicTlsErrorStatus,
          *(_QWORD *)(a1 + 72),
          v10,
          "QuicPacketKeyDerive");
    }
  }
  else
  {
    v10 = -1073741811;
  }
  return v10 >= 0;
}

```

## disassembly

```asm
0x140008af8  mov     [rsp+arg_10], rbx
0x140008afd  push    rbp
0x140008afe  push    rsi
0x140008aff  push    rdi
0x140008b00  sub     rsp, 90h
0x140008b07  mov     rax, cs:__security_cookie
0x140008b0e  xor     rax, rsp
0x140008b11  mov     [rsp+0A8h+var_28], rax
0x140008b19  mov     rbp, [rsp+0A8h+arg_20]
0x140008b21  mov     esi, edx
0x140008b23  xor     edx, edx; Val
0x140008b25  mov     rdi, rcx
0x140008b28  lea     rcx, [rsp+0A8h+var_78]; void *
0x140008b2d  mov     rbx, r9
0x140008b30  lea     r8d, [rdx+48h]; Size
0x140008b34  call    memset
0x140008b39  lea     r8, [rsp+0A8h+var_78]
0x140008b3e  mov     rdx, rbx
0x140008b41  mov     rcx, rdi
0x140008b44  call    CxPlatParseTrafficSecrets
0x140008b49  test    al, al
0x140008b4b  jz      short loc_140008B9D
0x140008b4d  mov     rdx, [rdi+28h]
0x140008b51  lea     r8, [rsp+0A8h+var_78]
0x140008b56  mov     [rsp+0A8h+var_80], rbp
0x140008b5b  mov     ecx, esi
0x140008b5d  mov     byte ptr [rsp+0A8h+var_88], 1
0x140008b62  call    QuicPacketKeyDerive
0x140008b67  mov     ebx, eax
0x140008b69  test    eax, eax
0x140008b6b  js      loc_14003D696
0x140008b71  shr     ebx, 1Fh
0x140008b74  xor     bl, 1
0x140008b77  mov     al, bl
0x140008b79  mov     rcx, [rsp+0A8h+var_28]
0x140008b81  xor     rcx, rsp; StackCookie
0x140008b84  call    __security_check_cookie
0x140008b89  mov     rbx, [rsp+0A8h+arg_10]
0x140008b91  add     rsp, 90h
0x140008b98  pop     rdi
0x140008b99  pop     rsi
0x140008b9a  pop     rbp
0x140008b9b  retn
0x140008b9d  mov     ebx, 0C000000Dh
0x140008ba2  jmp     short loc_140008B71
0x14003d696  mov     cl, cs:byte_14005C48D
0x14003d69c  test    cl, cl
0x14003d69e  jns     loc_140008B71
0x14003d6a4  mov     r8, [rdi+48h]
0x14003d6a8  lea     rax, aQuicpacketkeyd; "QuicPacketKeyDerive"
0x14003d6af  mov     r9d, ebx
0x14003d6b2  mov     [rsp+0A8h+var_88], rax
0x14003d6b7  lea     rdx, QuicTlsErrorStatus
0x14003d6be  call    McTemplateU0pqs_EtwWriteTransfer
0x14003d6c3  nop
0x14003d6c4  jmp     loc_140008B71
```
