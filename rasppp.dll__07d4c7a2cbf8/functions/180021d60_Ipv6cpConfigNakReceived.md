# Ipv6cpConfigNakReceived

- ea: `0x180021d60`
- end: `0x180021ecc`
- name: `Ipv6cpConfigNakReceived`
- size: `364`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180021d60`
- `0x180022504`
- `0x180023500`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x180021dd0`: `Ip6cpConfigNakReceived`
- `0x180021e6b`: `Ip6cpConfigNakReceived: done %d`

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
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
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
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
  {
    LOWORD(v8) = 0;
    FormatRRASErrorString(&v8, L"Ip6cpConfigNakReceived: done %d", UniqueInterfaceId);
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
      &v8);
  }
  return UniqueInterfaceId;
}

```

## disassembly

```asm
0x180021d60  mov     [rsp+arg_10], rbx
0x180021d65  push    rbp
0x180021d66  push    rsi
0x180021d67  push    rdi
0x180021d68  push    r14
0x180021d6a  push    r15
0x180021d6c  sub     rsp, 830h
0x180021d73  mov     rax, cs:__security_cookie
0x180021d7a  xor     rax, rsp
0x180021d7d  mov     [rsp+858h+var_38], rax
0x180021d85  movzx   eax, byte ptr [rdx+3]
0x180021d89  lea     rsi, [rdx+4]
0x180021d8d  movzx   ebx, byte ptr [rdx+2]
0x180021d91  mov     rdi, rcx
0x180021d94  sub     ax, 4
0x180021d98  mov     ecx, 100h
0x180021d9d  imul    ebx, ecx
0x180021da0  xor     edx, edx; Val
0x180021da2  mov     r8d, 7FCh; Size
0x180021da8  lea     rcx, [rsp+858h+var_834]; void *
0x180021dad  xor     ebp, ebp
0x180021daf  add     bx, ax
0x180021db2  xor     eax, eax
0x180021db4  mov     [rsp+858h+var_838], eax
0x180021db8  call    memset_0
0x180021dbd  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021dc4  test    rdx, rdx
0x180021dc7  jz      short loc_180021DE3
0x180021dc9  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021dd0  lea     r8, aIp6cpconfignak_0; "Ip6cpConfigNakReceived"
0x180021dd7  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021de3  cmp     bx, 2
0x180021de7  jb      short loc_180021E5F
0x180021de9  cmp     byte ptr [rsi], 1
0x180021dec  jnz     short loc_180021E3B
0x180021dee  cmp     dword ptr [rdi], 0
0x180021df1  jnz     short loc_180021E5A
0x180021df3  cmp     bx, 0Ah
0x180021df7  jb      short loc_180021E34
0x180021df9  lea     r15, [rdi+48h]
0x180021dfd  mov     rax, [r15]
0x180021e00  lea     r14, [rsi+2]
0x180021e04  cmp     [r14], rax
0x180021e07  jz      short loc_180021E20
0x180021e09  mov     rdx, r14
0x180021e0c  mov     rcx, rdi
0x180021e0f  call    IsLocalInterfaceIdUnique
0x180021e14  test    eax, eax
0x180021e16  jz      short loc_180021E20
0x180021e18  mov     rax, [r14]
0x180021e1b  mov     [r15], rax
0x180021e1e  jmp     short loc_180021E34
0x180021e20  mov     r8, rdi
0x180021e23  lea     rdx, IsLocalInterfaceIdUnique
0x180021e2a  mov     rcx, r15; pbBuffer
0x180021e2d  call    Ipv6cpGetUniqueInterfaceId
0x180021e32  mov     ebp, eax
0x180021e34  or      dword ptr [rdi+0A4h], 1
0x180021e3b  movzx   ecx, byte ptr [rsi+1]
0x180021e3f  test    cl, cl
0x180021e41  jz      short loc_180021E50
0x180021e43  movzx   eax, cx
0x180021e46  cmp     cx, bx
0x180021e49  jnb     short loc_180021E50
0x180021e4b  sub     bx, ax
0x180021e4e  jmp     short loc_180021E55
0x180021e50  xor     eax, eax
0x180021e52  movzx   ebx, ax
0x180021e55  add     rsi, rcx
0x180021e58  jmp     short loc_180021DE3
0x180021e5a  mov     ebp, 2DCh
0x180021e5f  cmp     qword ptr cs:xmmword_18004C800+8, 0
0x180021e67  jz      short loc_180021EA3
0x180021e69  xor     eax, eax
0x180021e6b  lea     rdx, aIp6cpconfignak; "Ip6cpConfigNakReceived: done %d"
0x180021e72  mov     r8d, ebp
0x180021e75  mov     word ptr [rsp+858h+var_838], ax
0x180021e7a  lea     rcx, [rsp+858h+var_838]
0x180021e7f  call    FormatRRASErrorString
0x180021e84  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180021e8b  lea     r8, [rsp+858h+var_838]
0x180021e90  mov     rcx, cs:gRasIpv6cpEtwContext
0x180021e97  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180021e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ea3  mov     eax, ebp
0x180021ea5  mov     rcx, [rsp+858h+var_38]
0x180021ead  xor     rcx, rsp; StackCookie
0x180021eb0  call    __security_check_cookie
0x180021eb5  mov     rbx, [rsp+858h+arg_10]
0x180021ebd  add     rsp, 830h
0x180021ec4  pop     r15
0x180021ec6  pop     r14
0x180021ec8  pop     rdi
0x180021ec9  pop     rsi
0x180021eca  pop     rbp
0x180021ecb  retn
```
