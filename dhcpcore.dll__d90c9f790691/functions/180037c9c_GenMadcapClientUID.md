# GenMadcapClientUID

- ea: `0x180037c9c`
- end: `0x180037d20`
- name: `GenMadcapClientUID`
- size: `132`
- prototype: `RPC_STATUS __fastcall(__int64, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002a450`
- `0x180038adc`

## callees

- `0x18001cef0`
- `0x180037c9c`
- `0x18004d9e8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180037cf0`
- `RPCRT4!UuidCreate` at `0x180037cf0`

## pseudocode

```c
RPC_STATUS __fastcall GenMadcapClientUID(__int64 a1, unsigned int *a2)
{
  __int64 v2; // r9
  RPC_STATUS result; // eax
  UUID v5; // xmm0
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  v2 = *a2;
  Uuid = 0;
  if ( (unsigned int)v2 >= 0x11 )
  {
    result = UuidCreate(&Uuid);
    v5 = Uuid;
    *(_BYTE *)a1 = 0;
    if ( result )
      result = 1334;
    *(UUID *)(a1 + 1) = v5;
  }
  else
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 78, WPP_907a2eddec1a34e45e1ef99b43abf7b7_Traceguids, v2);
    return 87;
  }
  return result;
}

```

## disassembly

```asm
0x180037c9c  push    rbx
0x180037c9e  sub     rsp, 40h
0x180037ca2  mov     rax, cs:__security_cookie
0x180037ca9  xor     rax, rsp
0x180037cac  mov     [rsp+48h+var_18], rax
0x180037cb1  mov     r9d, [rdx]
0x180037cb4  xorps   xmm0, xmm0
0x180037cb7  mov     rbx, rcx
0x180037cba  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180037cbf  cmp     r9d, 11h
0x180037cc3  jnb     short loc_180037CEB
0x180037cc5  test    byte ptr cs:xmmword_1800616A0, 2
0x180037ccc  jz      short loc_180037CE4
0x180037cce  mov     edx, 4Eh ; 'N'
0x180037cd3  lea     r8, WPP_907a2eddec1a34e45e1ef99b43abf7b7_Traceguids
0x180037cda  mov     ecx, 401h
0x180037cdf  call    WPP_SF_d
0x180037ce4  mov     eax, 57h ; 'W'
0x180037ce9  jmp     short loc_180037D0D
0x180037ceb  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180037cf0  call    cs:__imp_UuidCreate
0x180037cf6  movups  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180037cfb  test    eax, eax
0x180037cfd  mov     byte ptr [rbx], 0
0x180037d00  mov     ecx, 536h
0x180037d05  cmovnz  eax, ecx
0x180037d08  movdqu  xmmword ptr [rbx+1], xmm0
0x180037d0d  mov     rcx, [rsp+48h+var_18]
0x180037d12  xor     rcx, rsp; StackCookie
0x180037d15  call    __security_check_cookie
0x180037d1a  add     rsp, 40h
0x180037d1e  pop     rbx
0x180037d1f  retn
```
