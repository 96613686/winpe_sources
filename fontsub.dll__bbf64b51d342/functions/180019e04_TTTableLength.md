# TTTableLength

- ea: `0x180019e04`
- end: `0x180019e5b`
- name: `TTTableLength`
- size: `87`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x18000740c`
- `0x1800089c8`
- `0x180009010`
- `0x180009544`
- `0x18000ef20`
- `0x1800105d0`
- `0x1800109fc`
- `0x1800118bc`
- `0x180013364`
- `0x1800154a4`
- `0x1800175f4`
- `0x180017b6c`
- `0x1800198f8`
- `0x180019b18`

## callees

- `0x180019b9c`
- `0x180019e04`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall TTTableLength(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  if ( !(unsigned int)GetTTDirectory(a1, a2, (__int64)&v4) )
    return 0;
  result = HIDWORD(v4);
  if ( (unsigned int)(DWORD2(v4) + HIDWORD(v4)) < DWORD2(v4)
    || (unsigned int)(DWORD2(v4) + HIDWORD(v4)) > *(_DWORD *)(a1 + 8) )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019e04  push    rbx
0x180019e06  sub     rsp, 40h
0x180019e0a  mov     rax, cs:__security_cookie
0x180019e11  xor     rax, rsp
0x180019e14  mov     [rsp+48h+var_18], rax
0x180019e19  xorps   xmm0, xmm0
0x180019e1c  lea     r8, [rsp+48h+var_28]
0x180019e21  movups  [rsp+48h+var_28], xmm0
0x180019e26  mov     rbx, rcx
0x180019e29  call    GetTTDirectory
0x180019e2e  test    eax, eax
0x180019e30  jz      short loc_180019E46
0x180019e32  mov     ecx, dword ptr [rsp+48h+var_28+8]
0x180019e36  mov     eax, dword ptr [rsp+48h+var_28+0Ch]
0x180019e3a  lea     edx, [rcx+rax]
0x180019e3d  cmp     edx, ecx
0x180019e3f  jb      short loc_180019E46
0x180019e41  cmp     edx, [rbx+8]
0x180019e44  jbe     short loc_180019E48
0x180019e46  xor     eax, eax
0x180019e48  mov     rcx, [rsp+48h+var_18]
0x180019e4d  xor     rcx, rsp; StackCookie
0x180019e50  call    __security_check_cookie
0x180019e55  add     rsp, 40h
0x180019e59  pop     rbx
0x180019e5a  retn
```
