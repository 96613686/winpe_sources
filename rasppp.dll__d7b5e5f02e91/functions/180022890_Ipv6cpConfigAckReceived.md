# Ipv6cpConfigAckReceived

- ea: `0x180022890`
- end: `0x180022a0a`
- name: `Ipv6cpConfigAckReceived`
- size: `378`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180022890`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x1800228e5`: `Ipv6cpConfigAckReceived`
- `0x180022986`: `Invalid Packet received in configack`
- `0x1800229aa`: `Ipv6cpConfigAckReceived: done %d`

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
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"Ipv6cpConfigAckReceived");
  v4 = (unsigned __int16)(*(unsigned __int8 *)(a2 + 3) + (*(unsigned __int8 *)(a2 + 2) << 8));
  if ( v4 != *(unsigned __int8 *)(a2 + 5) + 4LL )
    goto LABEL_12;
  v5 = 0;
  if ( qword_18004D820 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *, _QWORD, __int64))gRasIpv6cpByteTemplateFunc)(
      gRasIpv6cpEtwContext,
      qword_18004D820,
      L"DumpingByte pReceiveBuf",
      a2 != 0 ? (unsigned int)v4 : 0,
      a2);
  if ( *(_QWORD *)(a1 + 40) != a1 + 40
    && (*(_BYTE *)(a2 + 4) != 1 || *(_BYTE *)(a2 + 5) != 10 || *(_QWORD *)(a2 + 6) != *(_QWORD *)(a1 + 72)) )
  {
    if ( (_QWORD)xmmword_18004D800 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
        gRasIpv6cpEtwContext,
        xmmword_18004D800,
        L"Invalid Packet received in configack");
LABEL_12:
    v5 = 722;
  }
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    LOWORD(v7) = 0;
    FormatRRASErrorString((wchar_t *)&v7, L"Ipv6cpConfigAckReceived: done %d", v5);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180022890  mov     [rsp+arg_0], rbx
0x180022895  mov     [rsp+arg_10], rsi
0x18002289a  push    rdi
0x18002289b  sub     rsp, 840h
0x1800228a2  mov     rax, cs:__security_cookie
0x1800228a9  xor     rax, rsp
0x1800228ac  mov     [rsp+848h+var_18], rax
0x1800228b4  mov     rdi, rdx
0x1800228b7  mov     rsi, rcx
0x1800228ba  xor     eax, eax
0x1800228bc  lea     rcx, [rsp+848h+var_814]; void *
0x1800228c1  xor     edx, edx; Val
0x1800228c3  mov     [rsp+848h+var_818], eax
0x1800228c7  mov     r8d, 7FCh; Size
0x1800228cd  call    memset_0
0x1800228d2  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800228d9  test    rdx, rdx
0x1800228dc  jz      short loc_1800228F8
0x1800228de  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800228e5  lea     r8, aIpv6cpconfigac; "Ipv6cpConfigAckReceived"
0x1800228ec  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800228f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228f8  movzx   eax, byte ptr [rdi+3]
0x1800228fc  mov     ecx, 100h
0x180022901  movzx   edx, byte ptr [rdi+2]
0x180022905  imul    edx, ecx
0x180022908  add     dx, ax
0x18002290b  movzx   eax, byte ptr [rdi+5]
0x18002290f  add     rax, 4
0x180022913  movzx   ecx, dx
0x180022916  cmp     rcx, rax
0x180022919  jnz     short loc_180022999
0x18002291b  mov     rdx, cs:qword_18004D820
0x180022922  xor     ebx, ebx
0x180022924  test    rdx, rdx
0x180022927  jz      short loc_180022954
0x180022929  mov     rax, rdi
0x18002292c  mov     [rsp+848h+var_828], rdi
0x180022931  neg     rax
0x180022934  lea     r8, aDumpingbytePre; "DumpingByte pReceiveBuf"
0x18002293b  mov     rax, cs:gRasIpv6cpByteTemplateFunc
0x180022942  sbb     r9d, r9d
0x180022945  and     r9d, ecx
0x180022948  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002294f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022954  lea     rax, [rsi+28h]
0x180022958  cmp     [rax], rax
0x18002295b  jz      short loc_18002299E
0x18002295d  cmp     byte ptr [rdi+4], 1
0x180022961  jnz     short loc_180022973
0x180022963  cmp     byte ptr [rdi+5], 0Ah
0x180022967  jnz     short loc_180022973
0x180022969  mov     rax, [rsi+48h]
0x18002296d  cmp     [rdi+6], rax
0x180022971  jz      short loc_18002299E
0x180022973  mov     rdx, qword ptr cs:xmmword_18004D800
0x18002297a  test    rdx, rdx
0x18002297d  jz      short loc_180022999
0x18002297f  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022986  lea     r8, aInvalidPacketR; "Invalid Packet received in configack"
0x18002298d  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022999  mov     ebx, 2D2h
0x18002299e  cmp     qword ptr cs:xmmword_18004D800+8, 0
0x1800229a6  jz      short loc_1800229E2
0x1800229a8  xor     ecx, ecx
0x1800229aa  lea     rdx, aIpv6cpconfigac_0; "Ipv6cpConfigAckReceived: done %d"
0x1800229b1  mov     word ptr [rsp+848h+var_818], cx
0x1800229b6  mov     r8d, ebx
0x1800229b9  lea     rcx, [rsp+848h+var_818]
0x1800229be  call    FormatRRASErrorString
0x1800229c3  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x1800229ca  lea     r8, [rsp+848h+var_818]
0x1800229cf  mov     rcx, cs:gRasIpv6cpEtwContext
0x1800229d6  mov     rax, cs:gRasIpv6cpTemplateFunc
0x1800229dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229e2  mov     eax, ebx
0x1800229e4  mov     rcx, [rsp+848h+var_18]
0x1800229ec  xor     rcx, rsp; StackCookie
0x1800229ef  call    __security_check_cookie
0x1800229f4  lea     r11, [rsp+848h+var_8]
0x1800229fc  mov     rbx, [r11+10h]
0x180022a00  mov     rsi, [r11+20h]
0x180022a04  mov     rsp, r11
0x180022a07  pop     rdi
0x180022a08  retn
```
