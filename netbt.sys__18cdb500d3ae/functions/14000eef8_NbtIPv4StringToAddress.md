# NbtIPv4StringToAddress

- ea: `0x14000eef8`
- end: `0x14000efce`
- name: `NbtIPv4StringToAddress`
- size: `214`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140009844`
- `0x14000d594`
- `0x14000efd4`
- `0x14002571c`
- `0x140028f44`
- `0x14002ab80`
- `0x14004d740`
- `0x14004f224`

## callees

- `0x14000eef8`
- `0x140028830`
- `0x140030f40`

## import_xrefs

- `ntoskrnl!RtlIpv4StringToAddressA` at `0x14000ef98`
- `ntoskrnl!RtlIpv4StringToAddressA` at `0x14000ef98`

## pseudocode

```c
__int64 __fastcall NbtIPv4StringToAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int16 v4; // di
  unsigned __int64 v5; // r8
  unsigned int v6; // ebx
  char v7; // al
  unsigned __int32 v9; // ecx
  in_addr Addr; // [rsp+20h] [rbp-38h] BYREF
  PCSTR Terminator; // [rsp+28h] [rbp-30h] BYREF
  CHAR S[16]; // [rsp+30h] [rbp-28h] BYREF

  Terminator = 0;
  *(_OWORD *)S = 0;
  v4 = a2;
  Addr = 0;
  v5 = 0;
  while ( 1 )
  {
    LOBYTE(a2) = *(_BYTE *)(a1 + v5);
    S[v5] = a2;
    if ( (unsigned __int8)(a2 - 48) > 9u && (_BYTE)a2 != 46 )
      break;
    if ( ++v5 >= 0xF )
    {
      if ( v5 >= 0x10 )
        _report_rangecheckfailure(a1, a2, v5, a4);
      break;
    }
  }
  v6 = 0;
  S[v5] = 0;
  while ( v5 <= 0xF )
  {
    v7 = *(_BYTE *)(a1 + v5);
    if ( !v7 )
      break;
    if ( v7 != 32 )
      return v6;
    ++v5;
  }
  if ( RtlIpv4StringToAddressA(S, 1u, &Terminator, &Addr) >= 0 )
  {
    v9 = _byteswap_ulong(Addr.S_un.S_addr);
    if ( (v4 & 0x3000) == 0 || HIBYTE(v9) < 0xE0u )
      return v9;
  }
  return v6;
}

```

## disassembly

```asm
0x14000eef8  mov     [rsp+arg_0], rbx
0x14000eefd  push    rdi
0x14000eefe  sub     rsp, 50h
0x14000ef02  mov     rax, cs:__security_cookie
0x14000ef09  xor     rax, rsp
0x14000ef0c  mov     [rsp+58h+var_18], rax
0x14000ef11  xorps   xmm0, xmm0
0x14000ef14  mov     [rsp+58h+Terminator], 0
0x14000ef1d  movups  xmmword ptr [rsp+58h+S], xmm0
0x14000ef22  mov     edi, edx
0x14000ef24  mov     dword ptr [rsp+58h+Addr.S_un], 0
0x14000ef2c  xor     r8d, r8d
0x14000ef2f  mov     dl, [rcx+r8]
0x14000ef33  mov     [rsp+r8+58h+S], dl
0x14000ef38  lea     eax, [rdx-30h]
0x14000ef3b  cmp     al, 9
0x14000ef3d  jbe     short loc_14000EF44
0x14000ef3f  cmp     dl, 2Eh ; '.'
0x14000ef42  jnz     short loc_14000EF53
0x14000ef44  inc     r8
0x14000ef47  cmp     r8, 0Fh
0x14000ef4b  jb      short loc_14000EF2F
0x14000ef4d  cmp     r8, 10h
0x14000ef51  jnb     short loc_14000EFC8
0x14000ef53  xor     ebx, ebx
0x14000ef55  mov     [rsp+r8+58h+S], bl
0x14000ef5a  cmp     r8, 0Fh
0x14000ef5e  ja      short loc_14000EF87
0x14000ef60  mov     al, [rcx+r8]
0x14000ef64  test    al, al
0x14000ef66  jz      short loc_14000EF87
0x14000ef68  cmp     al, 20h ; ' '
0x14000ef6a  jz      short loc_14000EFC3
0x14000ef6c  mov     eax, ebx
0x14000ef6e  mov     rcx, [rsp+58h+var_18]
0x14000ef73  xor     rcx, rsp; StackCookie
0x14000ef76  call    __security_check_cookie
0x14000ef7b  mov     rbx, [rsp+58h+arg_0]
0x14000ef80  add     rsp, 50h
0x14000ef84  pop     rdi
0x14000ef85  retn
0x14000ef87  lea     r9, [rsp+58h+Addr]; Addr
0x14000ef8c  mov     dl, 1; Strict
0x14000ef8e  lea     r8, [rsp+58h+Terminator]; Terminator
0x14000ef93  lea     rcx, [rsp+58h+S]; S
0x14000ef98  call    cs:__imp_RtlIpv4StringToAddressA
0x14000ef9f  nop     dword ptr [rax+rax+00h]
0x14000efa4  test    eax, eax
0x14000efa6  js      short loc_14000EF6C
0x14000efa8  mov     ecx, dword ptr [rsp+58h+Addr.S_un]
0x14000efac  bswap   ecx
0x14000efae  test    edi, 3000h
0x14000efb4  jz      short loc_14000EFBF
0x14000efb6  mov     eax, ecx
0x14000efb8  shr     eax, 18h
0x14000efbb  cmp     al, 0E0h
0x14000efbd  jnb     short loc_14000EF6C
0x14000efbf  mov     ebx, ecx
0x14000efc1  jmp     short loc_14000EF6C
0x14000efc3  inc     r8
0x14000efc6  jmp     short loc_14000EF5A
0x14000efc8  call    __report_rangecheckfailure
```
