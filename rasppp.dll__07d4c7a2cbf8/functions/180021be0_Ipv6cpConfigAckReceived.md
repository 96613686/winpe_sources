# Ipv6cpConfigAckReceived

- ea: `0x180021be0`
- end: `0x180021d59`
- name: `Ipv6cpConfigAckReceived`
- size: `377`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180021be0`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180021c35`: `Ipv6cpConfigAckReceived`
- `0x180021cd6`: `Invalid Packet received in configack`
- `0x180021cfa`: `Ipv6cpConfigAckReceived: done %d`

## pseudocode

```c
__int64 __fastcall Ipv6cpConfigAckReceived(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-818h] BYREF
  _BYTE v8[2044]; // [rsp+34h] [rbp-814h] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      L"Ipv6cpConfigAckReceived");
  v4 = (unsigned __int16)(*(unsigned __int8 *)(a2 + 3) + (*(unsigned __int8 *)(a2 + 2) << 8));
  if ( v4 != *(unsigned __int8 *)(a2 + 5) + 4LL )
    goto LABEL_12;
  v5 = 0;
  if ( qword_18004C820 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004C820,
      L"DumpingByte pReceiveBuf",
      a2 != 0 ? (unsigned int)v4 : 0,
      a2);
  if ( *(_QWORD *)(a1 + 40) != a1 + 40
    && (*(_BYTE *)(a2 + 4) != 1 || *(_BYTE *)(a2 + 5) != 10 || *(_QWORD *)(a2 + 6) != *(_QWORD *)(a1 + 72)) )
  {
    if ( (_QWORD)xmmword_18004C800 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        xmmword_18004C800,
        L"Invalid Packet received in configack");
LABEL_12:
    v5 = 722;
  }
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString(&v7, L"Ipv6cpConfigAckReceived: done %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180021be0  mov     [rsp+arg_0], rbx
0x180021be5  mov     [rsp+arg_10], rsi
0x180021bea  push    rdi
0x180021beb  sub     rsp, 840h
0x180021bf2  mov     rax, cs:__security_cookie
0x180021bf9  xor     rax, rsp
0x180021bfc  mov     [rsp+848h+var_18], rax
0x180021c04  mov     rdi, rdx
0x180021c07  mov     rsi, rcx
0x180021c0a  xor     eax, eax
0x180021c0c  lea     rcx, [rsp+848h+var_814]; void *
0x180021c11  xor     edx, edx; Val
0x180021c13  mov     [rsp+848h+var_818], eax
0x180021c17  mov     r8d, 7FCh; Size
0x180021c1d  call    memset_0
0x180021c22  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021c29  test    rdx, rdx
0x180021c2c  jz      short loc_180021C48
0x180021c2e  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021c35  lea     r8, aIpv6cpconfigac; "Ipv6cpConfigAckReceived"
0x180021c3c  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c48  movzx   eax, byte ptr [rdi+3]
0x180021c4c  mov     ecx, 100h
0x180021c51  movzx   edx, byte ptr [rdi+2]
0x180021c55  imul    edx, ecx
0x180021c58  add     dx, ax
0x180021c5b  movzx   eax, byte ptr [rdi+5]
0x180021c5f  add     rax, 4
0x180021c63  movzx   ecx, dx
0x180021c66  cmp     rcx, rax
0x180021c69  jnz     short loc_180021CE9
0x180021c6b  mov     rdx, cs:qword_18004C820
0x180021c72  xor     ebx, ebx
0x180021c74  test    rdx, rdx
0x180021c77  jz      short loc_180021CA4
0x180021c79  mov     rax, rdi
0x180021c7c  mov     [rsp+848h+var_828], rdi
0x180021c81  neg     rax
0x180021c84  lea     r8, aDumpingbytePre; "DumpingByte pReceiveBuf"
0x180021c8b  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x180021c92  sbb     r9d, r9d
0x180021c95  and     r9d, ecx
0x180021c98  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ca4  lea     rax, [rsi+28h]
0x180021ca8  cmp     [rax], rax
0x180021cab  jz      short loc_180021CEE
0x180021cad  cmp     byte ptr [rdi+4], 1
0x180021cb1  jnz     short loc_180021CC3
0x180021cb3  cmp     byte ptr [rdi+5], 0Ah
0x180021cb7  jnz     short loc_180021CC3
0x180021cb9  mov     rax, [rsi+48h]
0x180021cbd  cmp     [rdi+6], rax
0x180021cc1  jz      short loc_180021CEE
0x180021cc3  mov     rdx, qword ptr cs:xmmword_18004C800
0x180021cca  test    rdx, rdx
0x180021ccd  jz      short loc_180021CE9
0x180021ccf  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021cd6  lea     r8, aInvalidPacketR; "Invalid Packet received in configack"
0x180021cdd  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ce9  mov     ebx, 2D2h
0x180021cee  cmp     qword ptr cs:xmmword_18004C800+8, 0
0x180021cf6  jz      short loc_180021D32
0x180021cf8  xor     ecx, ecx
0x180021cfa  lea     rdx, aIpv6cpconfigac_0; "Ipv6cpConfigAckReceived: done %d"
0x180021d01  mov     word ptr [rsp+848h+var_818], cx
0x180021d06  mov     r8d, ebx
0x180021d09  lea     rcx, [rsp+848h+var_818]
0x180021d0e  call    FormatRRASErrorString
0x180021d13  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021d1a  lea     r8, [rsp+848h+var_818]
0x180021d1f  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021d26  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d32  mov     eax, ebx
0x180021d34  mov     rcx, [rsp+848h+var_18]
0x180021d3c  xor     rcx, rsp; StackCookie
0x180021d3f  call    __security_check_cookie
0x180021d44  lea     r11, [rsp+848h+var_8]
0x180021d4c  mov     rbx, [r11+10h]
0x180021d50  mov     rsi, [r11+20h]
0x180021d54  mov     rsp, r11
0x180021d57  pop     rdi
0x180021d58  retn
```
