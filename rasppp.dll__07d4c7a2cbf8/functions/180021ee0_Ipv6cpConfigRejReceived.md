# Ipv6cpConfigRejReceived

- ea: `0x180021ee0`
- end: `0x18002203f`
- name: `Ipv6cpConfigRejReceived`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180021ee0`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180021f4e`: `Ip6cpConfigRejReceived`
- `0x180021f8a`: `Ipv6cpConfigRejReceived: Reject received for Interface Id`
- `0x180021fb7`: `Ipv6cpConfigRejReceived: Rejected an option that we did not send.  Terminating PPP`
- `0x180021fe0`: `Ip6cpConfigRejReceived: done %d`

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
  v7 = *((_QWORD *)&xmmword_18004C800 + 1);
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      L"Ip6cpConfigRejReceived");
    v7 = *((_QWORD *)&xmmword_18004C800 + 1);
  }
  if ( v6 >= 2u )
  {
    if ( a2[4] == 1 )
    {
      if ( (_QWORD)xmmword_18004C800 )
      {
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
          gRasIpv6cpEtwContext,
          xmmword_18004C800,
          L"Ipv6cpConfigRejReceived: Reject received for Interface Id");
        v7 = *((_QWORD *)&xmmword_18004C800 + 1);
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
        v7 = *((_QWORD *)&xmmword_18004C800 + 1);
      }
      v5 = 722;
    }
  }
  if ( v7 )
  {
    LOWORD(v9) = 0;
    FormatRRASErrorString(&v9, L"Ip6cpConfigRejReceived: done %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180021ee0  mov     [rsp+arg_0], rbx
0x180021ee5  mov     [rsp+arg_8], rsi
0x180021eea  push    rdi
0x180021eeb  sub     rsp, 830h
0x180021ef2  mov     rax, cs:__security_cookie
0x180021ef9  xor     rax, rsp
0x180021efc  mov     [rsp+838h+var_18], rax
0x180021f04  movzx   r8d, byte ptr [rdx+2]
0x180021f09  mov     ecx, 100h
0x180021f0e  movzx   edi, byte ptr [rdx+3]
0x180021f12  mov     rsi, rdx
0x180021f15  imul    r8d, ecx
0x180021f19  xor     eax, eax
0x180021f1b  sub     di, 4
0x180021f1f  mov     [rsp+838h+var_818], eax
0x180021f23  xor     edx, edx; Val
0x180021f25  lea     rcx, [rsp+838h+var_814]; void *
0x180021f2a  xor     ebx, ebx
0x180021f2c  add     di, r8w
0x180021f30  mov     r8d, 7FCh; Size
0x180021f36  call    memset_0
0x180021f3b  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180021f42  test    rax, rax
0x180021f45  jz      short loc_180021F6B
0x180021f47  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021f4e  lea     r8, aIp6cpconfigrej_0; "Ip6cpConfigRejReceived"
0x180021f55  mov     rdx, rax
0x180021f58  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f64  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180021f6b  cmp     di, 2
0x180021f6f  jb      short loc_180021FD9
0x180021f71  cmp     byte ptr [rsi+4], 1
0x180021f75  jnz     short loc_180021FAB
0x180021f77  mov     rdx, qword ptr cs:xmmword_18004C800
0x180021f7e  test    rdx, rdx
0x180021f81  jz      short loc_180021FA4
0x180021f83  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021f8a  lea     r8, aIpv6cpconfigre; "Ipv6cpConfigRejReceived: Reject receive"...
0x180021f91  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9d  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180021fa4  mov     ebx, 2DCh
0x180021fa9  jmp     short loc_180021FD9
0x180021fab  test    rax, rax
0x180021fae  jz      short loc_180021FD4
0x180021fb0  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021fb7  lea     r8, aIpv6cpconfigre_0; "Ipv6cpConfigRejReceived: Rejected an op"...
0x180021fbe  mov     rdx, rax
0x180021fc1  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fcd  mov     rax, qword ptr cs:xmmword_18004C800+8
0x180021fd4  mov     ebx, 2D2h
0x180021fd9  test    rax, rax
0x180021fdc  jz      short loc_180022018
0x180021fde  xor     ecx, ecx
0x180021fe0  lea     rdx, aIp6cpconfigrej; "Ip6cpConfigRejReceived: done %d"
0x180021fe7  mov     word ptr [rsp+838h+var_818], cx
0x180021fec  mov     r8d, ebx
0x180021fef  lea     rcx, [rsp+838h+var_818]
0x180021ff4  call    FormatRRASErrorString
0x180021ff9  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022000  lea     r8, [rsp+838h+var_818]
0x180022005  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002200c  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022018  mov     eax, ebx
0x18002201a  mov     rcx, [rsp+838h+var_18]
0x180022022  xor     rcx, rsp; StackCookie
0x180022025  call    __security_check_cookie
0x18002202a  lea     r11, [rsp+838h+var_8]
0x180022032  mov     rbx, [r11+10h]
0x180022036  mov     rsi, [r11+18h]
0x18002203a  mov     rsp, r11
0x18002203d  pop     rdi
0x18002203e  retn
```
