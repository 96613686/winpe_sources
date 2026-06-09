# Dhcpv6AppendOption

- ea: `0x180002cac`
- end: `0x180002f7a`
- name: `Dhcpv6AppendOption`
- size: `718`
- prototype: `__int64 __fastcall(void *Src, unsigned __int16, u_short, _DWORD *, _QWORD *, unsigned __int64)`
- caller_count: `12`
- callee_count: `18`
- tags: ``

## callers

- `0x180001ed4`
- `0x180002328`
- `0x1800027e0`
- `0x180013b6c`
- `0x1800170cc`
- `0x180017ffc`
- `0x180018678`
- `0x180018740`
- `0x18001f77c`
- `0x18001fc58`
- `0x1800200d8`
- `0x180027e20`

## callees

- `0x180002cac`
- `0x18000e0d8`
- `0x18000e324`
- `0x18000e5bc`
- `0x18000feb0`
- `0x18002b528`
- `0x18002b598`
- `0x18002b678`
- `0x18002b938`
- `0x18002bb94`
- `0x18002bdec`
- `0x18002bfcc`
- `0x18002c038`
- `0x18002c0c4`
- `0x18002c178`
- `0x18002c21c`
- `0x18002c2e0`
- `0x18002c444`

## import_xrefs

- `WS2_32!__imp_htons` at `0x180002d28`
- `WS2_32!__imp_htons` at `0x180002f55`
- `WS2_32!__imp_htons` at `0x180002d28`
- `WS2_32!__imp_htons` at `0x180002f55`

## pseudocode

```c
__int64 __fastcall Dhcpv6AppendOption(
        void *Src,
        unsigned __int16 a2,
        u_short a3,
        _DWORD *a4,
        _QWORD *a5,
        unsigned __int64 a6)
{
  unsigned int v6; // r12d
  unsigned int v7; // r14d
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  __int64 v12; // r15
  __int64 v13; // rbx
  u_short v14; // ax
  _DWORD *v15; // rcx
  unsigned int v16; // eax
  u_short v18; // [rsp+90h] [rbp+8h] BYREF

  v6 = a3;
  v7 = a2;
  v18 = 0;
  if ( !Src )
    return 87;
  if ( !a4 )
    return 87;
  v11 = a5;
  if ( !a5 )
    return 87;
  v12 = *a5;
  if ( !*a5 )
    return 87;
  v13 = a6;
  if ( !a6 || !a2 )
    return 87;
  if ( v12 + 4 > a6 )
    return 122;
  v14 = htons(a3);
  v15 = (_DWORD *)*v11;
  *a4 += 4;
  *v15 = v14;
  *v11 = v15 + 1;
  if ( v6 > 0x10 )
  {
    switch ( v6 )
    {
      case 0x11u:
        v16 = Dhcpv6AddVendorSpecInfo(Src, a4, v11, v13);
        goto LABEL_45;
      case 0x12u:
        v16 = Dhcpv6AddOptionInterfaceId(Src, a4, v11, v13);
        goto LABEL_45;
      case 0x15u:
      case 0x18u:
        goto LABEL_42;
      case 0x19u:
        v16 = Dhcpv6AddOptionIapd(Src, a4, v11, v13);
        goto LABEL_45;
      case 0x1Du:
      case 0x1Eu:
LABEL_42:
        v16 = DhcpV6AddOptionNameList(Src, v7, v13);
        goto LABEL_45;
      case 0x2Au:
        v16 = Dhcpv6AddOptionLifeTime(Src, a4, v11, v13);
        goto LABEL_45;
    }
    goto LABEL_39;
  }
  switch ( v6 )
  {
    case 0x10u:
      v16 = Dhcpv6AddVendorClassOption(Src, a4, v11, v13);
      goto LABEL_45;
    case 1u:
      v16 = Dhcpv6AddOptionClientId(Src, a4, v11, v13);
      goto LABEL_45;
    case 2u:
      v16 = Dhcpv6AddOptionServerId(Src, a4, v11, v13);
      goto LABEL_45;
    case 3u:
      v16 = Dhcpv6AddOptionIana(Src, a4, v11, v13);
      goto LABEL_45;
    case 4u:
      v16 = Dhcpv6AddOptionIata(Src, a4, v11, v13);
      goto LABEL_45;
    case 5u:
      v16 = Dhcpv6AddOptionIAAddr(Src, a4, v11, v13);
      goto LABEL_45;
    case 6u:
      v16 = Dhcpv6AddOptionORO(Src, a4, v11, v13);
      goto LABEL_45;
    case 8u:
      v16 = Dhcpv6AddOptionElapsedTime(Src, a4, v11, v13);
      goto LABEL_45;
    case 0xDu:
      v16 = Dhcpv6AddOptionStatusCode(Src, a4, v11, v13);
      goto LABEL_45;
  }
  if ( v6 != 15 )
  {
LABEL_39:
    v16 = Dhcpv6AddGenericOption(Src, v13);
    goto LABEL_45;
  }
  v16 = Dhcpv6AddUserClassOption(Src, a4, v11, v13);
LABEL_45:
  v10 = v16;
  if ( !v16 )
  {
    v10 = Dhcpv6CalculateOptLen(*v11, v12, &v18);
    if ( !v10 )
      *(_WORD *)(v12 + 2) = htons(v18);
  }
  return v10;
}

```

## disassembly

```asm
0x180002cac  mov     rax, rsp
0x180002caf  push    rbx
0x180002cb0  push    rbp
0x180002cb1  push    rsi
0x180002cb2  push    rdi
0x180002cb3  push    r12
0x180002cb5  push    r13
0x180002cb7  push    r14
0x180002cb9  push    r15
0x180002cbb  sub     rsp, 48h
0x180002cbf  xor     r13d, r13d
0x180002cc2  movzx   r12d, r8w
0x180002cc6  movzx   r14d, dx
0x180002cca  mov     rsi, r9
0x180002ccd  mov     [rax+8], r13w
0x180002cd2  mov     rbp, rcx
0x180002cd5  test    rcx, rcx
0x180002cd8  jnz     short loc_180002CE4
0x180002cda  mov     ebx, 57h ; 'W'
0x180002cdf  jmp     loc_180002F66
0x180002ce4  test    rsi, rsi
0x180002ce7  jz      short loc_180002CDA
0x180002ce9  mov     rdi, [rsp+88h+arg_20]
0x180002cf1  test    rdi, rdi
0x180002cf4  jz      short loc_180002CDA
0x180002cf6  mov     r15, [rdi]
0x180002cf9  test    r15, r15
0x180002cfc  jz      short loc_180002CDA
0x180002cfe  mov     rbx, [rsp+88h+arg_28]
0x180002d06  test    rbx, rbx
0x180002d09  jz      short loc_180002CDA
0x180002d0b  test    r14w, r14w
0x180002d0f  jz      short loc_180002CDA
0x180002d11  lea     rax, [r15+4]
0x180002d15  cmp     rax, rbx
0x180002d18  jbe     short loc_180002D24
0x180002d1a  mov     ebx, 7Ah ; 'z'
0x180002d1f  jmp     loc_180002F66
0x180002d24  movzx   ecx, r12w; hostshort
0x180002d28  call    cs:__imp_htons
0x180002d2f  nop     dword ptr [rax+rax+00h]
0x180002d34  mov     rcx, [rdi]
0x180002d37  add     dword ptr [rsi], 4
0x180002d3a  mov     word ptr [rsp+88h+var_58], ax
0x180002d3f  mov     word ptr [rsp+88h+var_58+2], r13w
0x180002d45  mov     eax, [rsp+88h+var_58]
0x180002d49  mov     [rcx], eax
0x180002d4b  lea     rax, [rcx+4]
0x180002d4f  mov     [rdi], rax
0x180002d52  mov     ecx, r12d
0x180002d55  cmp     r12d, 10h
0x180002d59  ja      loc_180002E82
0x180002d5f  jz      loc_180002E6C
0x180002d65  sub     ecx, 1
0x180002d68  jz      loc_180002E56
0x180002d6e  sub     ecx, 1
0x180002d71  jz      loc_180002E40
0x180002d77  sub     ecx, 1
0x180002d7a  jz      loc_180002E2A
0x180002d80  sub     ecx, 1
0x180002d83  jz      loc_180002E14
0x180002d89  sub     ecx, 1
0x180002d8c  jz      short loc_180002DFE
0x180002d8e  sub     ecx, 1
0x180002d91  jz      short loc_180002DE8
0x180002d93  sub     ecx, 2
0x180002d96  jz      short loc_180002DD2
0x180002d98  sub     ecx, 5
0x180002d9b  jz      short loc_180002DBC
0x180002d9d  cmp     ecx, 2
0x180002da0  jnz     loc_180002EB3
0x180002da6  mov     r9, rbx
0x180002da9  mov     r8, rdi
0x180002dac  mov     rdx, rsi
0x180002daf  mov     rcx, rbp
0x180002db2  call    Dhcpv6AddUserClassOption
0x180002db7  jmp     loc_180002F2E
0x180002dbc  mov     r9, rbx
0x180002dbf  mov     r8, rdi
0x180002dc2  mov     rdx, rsi
0x180002dc5  mov     rcx, rbp
0x180002dc8  call    Dhcpv6AddOptionStatusCode
0x180002dcd  jmp     loc_180002F2E
0x180002dd2  mov     r9, rbx
0x180002dd5  mov     r8, rdi
0x180002dd8  mov     rdx, rsi
0x180002ddb  mov     rcx, rbp
0x180002dde  call    Dhcpv6AddOptionElapsedTime
0x180002de3  jmp     loc_180002F2E
0x180002de8  mov     r9, rbx
0x180002deb  mov     r8, rdi
0x180002dee  mov     rdx, rsi
0x180002df1  mov     rcx, rbp
0x180002df4  call    Dhcpv6AddOptionORO
0x180002df9  jmp     loc_180002F2E
0x180002dfe  mov     r9, rbx
0x180002e01  mov     r8, rdi
0x180002e04  mov     rdx, rsi
0x180002e07  mov     rcx, rbp
0x180002e0a  call    Dhcpv6AddOptionIAAddr
0x180002e0f  jmp     loc_180002F2E
0x180002e14  mov     r9, rbx
0x180002e17  mov     r8, rdi
0x180002e1a  mov     rdx, rsi
0x180002e1d  mov     rcx, rbp
0x180002e20  call    Dhcpv6AddOptionIata
0x180002e25  jmp     loc_180002F2E
0x180002e2a  mov     r9, rbx
0x180002e2d  mov     r8, rdi
0x180002e30  mov     rdx, rsi
0x180002e33  mov     rcx, rbp
0x180002e36  call    Dhcpv6AddOptionIana
0x180002e3b  jmp     loc_180002F2E
0x180002e40  mov     r9, rbx
0x180002e43  mov     r8, rdi
0x180002e46  mov     rdx, rsi
0x180002e49  mov     rcx, rbp
0x180002e4c  call    Dhcpv6AddOptionServerId
0x180002e51  jmp     loc_180002F2E
0x180002e56  mov     r9, rbx
0x180002e59  mov     r8, rdi
0x180002e5c  mov     rdx, rsi
0x180002e5f  mov     rcx, rbp
0x180002e62  call    Dhcpv6AddOptionClientId
0x180002e67  jmp     loc_180002F2E
0x180002e6c  mov     r9, rbx
0x180002e6f  mov     r8, rdi
0x180002e72  mov     rdx, rsi
0x180002e75  mov     rcx, rbp
0x180002e78  call    Dhcpv6AddVendorClassOption
0x180002e7d  jmp     loc_180002F2E
0x180002e82  sub     ecx, 11h
0x180002e85  jz      loc_180002F1D
0x180002e8b  sub     ecx, 1
0x180002e8e  jz      short loc_180002F0A
0x180002e90  sub     ecx, 3
0x180002e93  jz      short loc_180002EF2
0x180002e95  sub     ecx, 3
0x180002e98  jz      short loc_180002EF2
0x180002e9a  sub     ecx, 1
0x180002e9d  jz      short loc_180002EDF
0x180002e9f  sub     ecx, 4
0x180002ea2  jz      short loc_180002EF2
0x180002ea4  sub     ecx, 1
0x180002ea7  jz      short loc_180002EF2
0x180002ea9  sub     ecx, 0Bh
0x180002eac  jz      short loc_180002EB3
0x180002eae  cmp     ecx, 1
0x180002eb1  jz      short loc_180002ECC
0x180002eb3  mov     r9, rdi
0x180002eb6  mov     [rsp+88h+var_68], rbx; __int64
0x180002ebb  mov     r8, rsi
0x180002ebe  movzx   edx, r14w
0x180002ec2  mov     rcx, rbp; Src
0x180002ec5  call    Dhcpv6AddGenericOption
0x180002eca  jmp     short loc_180002F2E
0x180002ecc  mov     r9, rbx
0x180002ecf  mov     r8, rdi
0x180002ed2  mov     rdx, rsi
0x180002ed5  mov     rcx, rbp
0x180002ed8  call    Dhcpv6AddOptionLifeTime
0x180002edd  jmp     short loc_180002F2E
0x180002edf  mov     r9, rbx
0x180002ee2  mov     r8, rdi
0x180002ee5  mov     rdx, rsi
0x180002ee8  mov     rcx, rbp
0x180002eeb  call    Dhcpv6AddOptionIapd
0x180002ef0  jmp     short loc_180002F2E
0x180002ef2  mov     edx, r14d; Size
0x180002ef5  mov     [rsp+88h+var_68], rbx; __int64
0x180002efa  mov     r9, rdi
0x180002efd  mov     r8, rsi
0x180002f00  mov     rcx, rbp; Src
0x180002f03  call    DhcpV6AddOptionNameList
0x180002f08  jmp     short loc_180002F2E
0x180002f0a  mov     r9, rbx
0x180002f0d  mov     r8, rdi
0x180002f10  mov     rdx, rsi
0x180002f13  mov     rcx, rbp
0x180002f16  call    Dhcpv6AddOptionInterfaceId
0x180002f1b  jmp     short loc_180002F2E
0x180002f1d  mov     r9, rbx
0x180002f20  mov     r8, rdi
0x180002f23  mov     rdx, rsi
0x180002f26  mov     rcx, rbp
0x180002f29  call    Dhcpv6AddVendorSpecInfo
0x180002f2e  mov     ebx, eax
0x180002f30  test    eax, eax
0x180002f32  jnz     short loc_180002F66
0x180002f34  mov     rcx, [rdi]
0x180002f37  lea     r8, [rsp+88h+arg_0]
0x180002f3f  mov     rdx, r15
0x180002f42  call    Dhcpv6CalculateOptLen
0x180002f47  mov     ebx, eax
0x180002f49  test    eax, eax
0x180002f4b  jnz     short loc_180002F66
0x180002f4d  movzx   ecx, [rsp+88h+arg_0]; hostshort
0x180002f55  call    cs:__imp_htons
0x180002f5c  nop     dword ptr [rax+rax+00h]
0x180002f61  mov     [r15+2], ax
0x180002f66  mov     eax, ebx
0x180002f68  add     rsp, 48h
0x180002f6c  pop     r15
0x180002f6e  pop     r14
0x180002f70  pop     r13
0x180002f72  pop     r12
0x180002f74  pop     rdi
0x180002f75  pop     rsi
0x180002f76  pop     rbp
0x180002f77  pop     rbx
0x180002f78  retn
```
