# Ipv6cpConfigRejReceived

- ea: `0x180022b90`
- end: `0x180022cf0`
- name: `Ipv6cpConfigRejReceived`
- size: `352`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180022b90`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180022bfe`: `Ip6cpConfigRejReceived`
- `0x180022c3a`: `Ipv6cpConfigRejReceived: Reject received for Interface Id`
- `0x180022c67`: `Ipv6cpConfigRejReceived: Rejected an option that we did not send.  Terminating PPP`
- `0x180022c90`: `Ip6cpConfigRejReceived: done %d`

## pseudocode

```c
__int64 __fastcall Ipv6cpConfigRejReceived(__int64 a1, unsigned __int8 *a2)
{
  __int16 v3; // r8
  __int16 v4; // di
  unsigned int v5; // ebx
  unsigned __int16 v6; // di
  __int64 v7; // rax
  int v9; // [rsp+20h] [rbp-818h] BYREF
  _BYTE v10[2044]; // [rsp+24h] [rbp-814h] BYREF

  v3 = a2[2] << 8;
  v4 = a2[3] - 4;
  v9 = 0;
  v5 = 0;
  v6 = v3 + v4;
  memset_0(v10, 0, sizeof(v10));
  v7 = *((_QWORD *)&xmmword_18004D800 + 1);
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"Ip6cpConfigRejReceived");
    v7 = *((_QWORD *)&xmmword_18004D800 + 1);
  }
  if ( v6 >= 2u )
  {
    if ( a2[4] == 1 )
    {
      if ( (_QWORD)xmmword_18004D800 )
      {
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          xmmword_18004D800,
          L"Ipv6cpConfigRejReceived: Reject received for Interface Id");
        v7 = *((_QWORD *)&xmmword_18004D800 + 1);
      }
      v5 = 732;
    }
    else
    {
      if ( v7 )
      {
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          v7,
          L"Ipv6cpConfigRejReceived: Rejected an option that we did not send.  Terminating PPP");
        v7 = *((_QWORD *)&xmmword_18004D800 + 1);
      }
      v5 = 722;
    }
  }
  if ( v7 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString((wchar_t *)&v9, L"Ip6cpConfigRejReceived: done %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180022b90  mov     [rsp+arg_0], rbx
0x180022b95  mov     [rsp+arg_8], rsi
0x180022b9a  push    rdi
0x180022b9b  sub     rsp, 830h
0x180022ba2  mov     rax, cs:__security_cookie
0x180022ba9  xor     rax, rsp
0x180022bac  mov     [rsp+838h+var_18], rax
0x180022bb4  movzx   r8d, byte ptr [rdx+2]
0x180022bb9  mov     ecx, 100h
0x180022bbe  movzx   edi, byte ptr [rdx+3]
0x180022bc2  mov     rsi, rdx
0x180022bc5  imul    r8d, ecx
0x180022bc9  xor     eax, eax
0x180022bcb  sub     di, 4
0x180022bcf  mov     [rsp+838h+var_818], eax
0x180022bd3  xor     edx, edx; Val
0x180022bd5  lea     rcx, [rsp+838h+var_814]; void *
0x180022bda  xor     ebx, ebx
0x180022bdc  add     di, r8w
0x180022be0  mov     r8d, 7FCh; Size
0x180022be6  call    memset_0
0x180022beb  mov     rax, qword ptr cs:xmmword_18004D800+8
0x180022bf2  test    rax, rax
0x180022bf5  jz      short loc_180022C1B
0x180022bf7  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022bfe  lea     r8, aIp6cpconfigrej_0; "Ip6cpConfigRejReceived"
0x180022c05  mov     rdx, rax
0x180022c08  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c14  mov     rax, qword ptr cs:xmmword_18004D800+8
0x180022c1b  cmp     di, 2
0x180022c1f  jb      short loc_180022C89
0x180022c21  cmp     byte ptr [rsi+4], 1
0x180022c25  jnz     short loc_180022C5B
0x180022c27  mov     rdx, qword ptr cs:xmmword_18004D800
0x180022c2e  test    rdx, rdx
0x180022c31  jz      short loc_180022C54
0x180022c33  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022c3a  lea     r8, aIpv6cpconfigre; "Ipv6cpConfigRejReceived: Reject receive"...
0x180022c41  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c4d  mov     rax, qword ptr cs:xmmword_18004D800+8
0x180022c54  mov     ebx, 2DCh
0x180022c59  jmp     short loc_180022C89
0x180022c5b  test    rax, rax
0x180022c5e  jz      short loc_180022C84
0x180022c60  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022c67  lea     r8, aIpv6cpconfigre_0; "Ipv6cpConfigRejReceived: Rejected an op"...
0x180022c6e  mov     rdx, rax
0x180022c71  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c7d  mov     rax, qword ptr cs:xmmword_18004D800+8
0x180022c84  mov     ebx, 2D2h
0x180022c89  test    rax, rax
0x180022c8c  jz      short loc_180022CC8
0x180022c8e  xor     ecx, ecx
0x180022c90  lea     rdx, aIp6cpconfigrej; "Ip6cpConfigRejReceived: done %d"
0x180022c97  mov     word ptr [rsp+838h+var_818], cx
0x180022c9c  mov     r8d, ebx
0x180022c9f  lea     rcx, [rsp+838h+var_818]
0x180022ca4  call    FormatRRASErrorString
0x180022ca9  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180022cb0  lea     r8, [rsp+838h+var_818]
0x180022cb5  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022cbc  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cc8  mov     eax, ebx
0x180022cca  mov     rcx, [rsp+838h+var_18]
0x180022cd2  xor     rcx, rsp; StackCookie
0x180022cd5  call    __security_check_cookie
0x180022cda  lea     r11, [rsp+838h+var_8]
0x180022ce2  mov     rbx, [r11+10h]
0x180022ce6  mov     rsi, [r11+18h]
0x180022cea  mov     rsp, r11
0x180022ced  pop     rdi
0x180022cee  retn
```
