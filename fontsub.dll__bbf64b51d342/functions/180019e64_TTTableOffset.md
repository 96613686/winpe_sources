# TTTableOffset

- ea: `0x180019e64`
- end: `0x180019eba`
- name: `TTTableOffset`
- size: `86`
- prototype: ``
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x18000740c`
- `0x1800079b8`
- `0x1800089c8`
- `0x180009010`
- `0x180009544`
- `0x18000acf4`
- `0x18000b040`
- `0x18000b5d0`
- `0x18000bdd4`
- `0x18000db8c`
- `0x18000e214`
- `0x18000ef20`
- `0x180010088`
- `0x1800105d0`
- `0x1800109fc`
- `0x180010fd4`
- `0x1800118bc`
- `0x180013364`
- `0x180013ee0`
- `0x1800143f0`
- `0x180014bc0`
- `0x1800154a4`
- `0x1800175f4`
- `0x180017b6c`
- `0x180017f04`
- `0x1800198f8`
- `0x180019a40`
- `0x180019c00`

## callees

- `0x180019b9c`
- `0x180019e64`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall TTTableOffset(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int128 v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  if ( !(unsigned int)GetTTDirectory(a1, a2, (__int64)&v4) )
    return 0;
  result = DWORD2(v4);
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
0x180019e64  push    rbx
0x180019e66  sub     rsp, 40h
0x180019e6a  mov     rax, cs:__security_cookie
0x180019e71  xor     rax, rsp
0x180019e74  mov     [rsp+48h+var_18], rax
0x180019e79  xorps   xmm0, xmm0
0x180019e7c  lea     r8, [rsp+48h+var_28]
0x180019e81  movups  [rsp+48h+var_28], xmm0
0x180019e86  mov     rbx, rcx
0x180019e89  call    GetTTDirectory
0x180019e8e  test    eax, eax
0x180019e90  jz      short loc_180019EA5
0x180019e92  mov     eax, dword ptr [rsp+48h+var_28+8]
0x180019e96  mov     edx, dword ptr [rsp+48h+var_28+0Ch]
0x180019e9a  add     edx, eax
0x180019e9c  cmp     edx, eax
0x180019e9e  jb      short loc_180019EA5
0x180019ea0  cmp     edx, [rbx+8]
0x180019ea3  jbe     short loc_180019EA7
0x180019ea5  xor     eax, eax
0x180019ea7  mov     rcx, [rsp+48h+var_18]
0x180019eac  xor     rcx, rsp; StackCookie
0x180019eaf  call    __security_check_cookie
0x180019eb4  add     rsp, 40h
0x180019eb8  pop     rbx
0x180019eb9  retn
```
