# Ipv6cpConfigNakReceived

- ea: `0x180022a10`
- end: `0x180022b7d`
- name: `Ipv6cpConfigNakReceived`
- size: `365`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180022a10`
- `0x1800231e4`
- `0x180024210`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180022a80`: `Ip6cpConfigNakReceived`
- `0x180022b1b`: `Ip6cpConfigNakReceived: done %d`

## pseudocode

```c
__int64 __fastcall Ipv6cpConfigNakReceived(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  unsigned int UniqueInterfaceId; // ebp
  unsigned __int16 v5; // bx
  __int64 v6; // rcx
  int v8; // [rsp+20h] [rbp-838h] BYREF
  _BYTE v9[2044]; // [rsp+24h] [rbp-834h] BYREF

  v2 = a2 + 4;
  UniqueInterfaceId = 0;
  v5 = *(unsigned __int8 *)(a2 + 3) - 4 + (*(unsigned __int8 *)(a2 + 2) << 8);
  v8 = 0;
  memset_0(v9, 0, sizeof(v9));
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"Ip6cpConfigNakReceived");
  while ( v5 >= 2u )
  {
    if ( *(_BYTE *)v2 == 1 )
    {
      if ( *(_DWORD *)a1 )
      {
        UniqueInterfaceId = 732;
        break;
      }
      if ( v5 >= 0xAu )
      {
        if ( *(_QWORD *)(v2 + 2) == *(_QWORD *)(a1 + 72) || !(unsigned int)IsLocalInterfaceIdUnique(a1, v2 + 2) )
          UniqueInterfaceId = Ipv6cpGetUniqueInterfaceId((BYTE *)(a1 + 72));
        else
          *(_QWORD *)(a1 + 72) = *(_QWORD *)(v2 + 2);
      }
      *(_DWORD *)(a1 + 164) |= 1u;
    }
    v6 = *(unsigned __int8 *)(v2 + 1);
    if ( (_BYTE)v6 && (unsigned __int16)v6 < v5 )
      v5 -= v6;
    else
      v5 = 0;
    v2 += v6;
  }
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"Ip6cpConfigNakReceived: done %d", UniqueInterfaceId);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      &v8);
  }
  return UniqueInterfaceId;
}

```

## disassembly

```asm
0x180022a10  mov     [rsp+arg_10], rbx
0x180022a15  push    rbp
0x180022a16  push    rsi
0x180022a17  push    rdi
0x180022a18  push    r14
0x180022a1a  push    r15
0x180022a1c  sub     rsp, 830h
0x180022a23  mov     rax, cs:__security_cookie
0x180022a2a  xor     rax, rsp
0x180022a2d  mov     [rsp+858h+var_38], rax
0x180022a35  movzx   eax, byte ptr [rdx+3]
0x180022a39  lea     rsi, [rdx+4]
0x180022a3d  movzx   ebx, byte ptr [rdx+2]
0x180022a41  mov     rdi, rcx
0x180022a44  sub     ax, 4
0x180022a48  mov     ecx, 100h
0x180022a4d  imul    ebx, ecx
0x180022a50  xor     edx, edx; Val
0x180022a52  mov     r8d, 7FCh; Size
0x180022a58  lea     rcx, [rsp+858h+var_834]; void *
0x180022a5d  xor     ebp, ebp
0x180022a5f  add     bx, ax
0x180022a62  xor     eax, eax
0x180022a64  mov     [rsp+858h+var_838], eax
0x180022a68  call    memset_0
0x180022a6d  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180022a74  test    rdx, rdx
0x180022a77  jz      short loc_180022A93
0x180022a79  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022a80  lea     r8, aIp6cpconfignak_0; "Ip6cpConfigNakReceived"
0x180022a87  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a93  cmp     bx, 2
0x180022a97  jb      short loc_180022B0F
0x180022a99  cmp     byte ptr [rsi], 1
0x180022a9c  jnz     short loc_180022AEB
0x180022a9e  cmp     dword ptr [rdi], 0
0x180022aa1  jnz     short loc_180022B0A
0x180022aa3  cmp     bx, 0Ah
0x180022aa7  jb      short loc_180022AE4
0x180022aa9  lea     r15, [rdi+48h]
0x180022aad  mov     rax, [r15]
0x180022ab0  lea     r14, [rsi+2]
0x180022ab4  cmp     [r14], rax
0x180022ab7  jz      short loc_180022AD0
0x180022ab9  mov     rdx, r14
0x180022abc  mov     rcx, rdi
0x180022abf  call    IsLocalInterfaceIdUnique
0x180022ac4  test    eax, eax
0x180022ac6  jz      short loc_180022AD0
0x180022ac8  mov     rax, [r14]
0x180022acb  mov     [r15], rax
0x180022ace  jmp     short loc_180022AE4
0x180022ad0  mov     r8, rdi
0x180022ad3  lea     rdx, IsLocalInterfaceIdUnique
0x180022ada  mov     rcx, r15; pbBuffer
0x180022add  call    Ipv6cpGetUniqueInterfaceId
0x180022ae2  mov     ebp, eax
0x180022ae4  or      dword ptr [rdi+0A4h], 1
0x180022aeb  movzx   ecx, byte ptr [rsi+1]
0x180022aef  test    cl, cl
0x180022af1  jz      short loc_180022B00
0x180022af3  movzx   eax, cx
0x180022af6  cmp     cx, bx
0x180022af9  jnb     short loc_180022B00
0x180022afb  sub     bx, ax
0x180022afe  jmp     short loc_180022B05
0x180022b00  xor     eax, eax
0x180022b02  movzx   ebx, ax
0x180022b05  add     rsi, rcx
0x180022b08  jmp     short loc_180022A93
0x180022b0a  mov     ebp, 2DCh
0x180022b0f  cmp     qword ptr cs:xmmword_18004D800+8, 0
0x180022b17  jz      short loc_180022B53
0x180022b19  xor     eax, eax
0x180022b1b  lea     rdx, aIp6cpconfignak; "Ip6cpConfigNakReceived: done %d"
0x180022b22  mov     r8d, ebp
0x180022b25  mov     word ptr [rsp+858h+var_838], ax
0x180022b2a  lea     rcx, [rsp+858h+var_838]
0x180022b2f  call    FormatRRASErrorString
0x180022b34  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180022b3b  lea     r8, [rsp+858h+var_838]
0x180022b40  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022b47  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b53  mov     eax, ebp
0x180022b55  mov     rcx, [rsp+858h+var_38]
0x180022b5d  xor     rcx, rsp; StackCookie
0x180022b60  call    __security_check_cookie
0x180022b65  mov     rbx, [rsp+858h+arg_10]
0x180022b6d  add     rsp, 830h
0x180022b74  pop     r15
0x180022b76  pop     r14
0x180022b78  pop     rdi
0x180022b79  pop     rsi
0x180022b7a  pop     rbp
0x180022b7b  retn
```
