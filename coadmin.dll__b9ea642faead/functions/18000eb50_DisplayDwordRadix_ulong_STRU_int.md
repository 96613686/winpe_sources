# DisplayDwordRadix(ulong,STRU *,int)

- ea: `0x18000eb50`
- end: `0x18000ebb9`
- name: `?DisplayDwordRadix@@YAJKPEAVSTRU@@H@Z`
- size: `105`
- prototype: `__int64 __fastcall(unsigned int, struct STRU *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000238c`
- `0x18000e978`
- `0x18000ec98`

## callees

- `0x18000eb50`
- `0x18000fb50`

## import_xrefs

- `msvcrt!_ultow` at `0x18000eb8b`
- `msvcrt!_ultow` at `0x18000eb8b`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000eb99`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000eb99`

## pseudocode

```c
int __fastcall DisplayDwordRadix(unsigned int a1, struct STRU *a2, int a3)
{
  int result; // eax
  wchar_t Buffer[8]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v6[28]; // [rsp+30h] [rbp-38h] BYREF

  memset(v6, 0, sizeof(v6));
  *(_OWORD *)Buffer = 0;
  if ( !a2 )
    return -2147024809;
  _ultow(a1, Buffer, a3);
  result = STRU::Copy(a2, Buffer);
  if ( result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000eb50  push    rbx
0x18000eb52  sub     rsp, 60h
0x18000eb56  mov     rax, cs:__security_cookie
0x18000eb5d  xor     rax, rsp
0x18000eb60  mov     [rsp+68h+var_18], rax
0x18000eb65  xorps   xmm0, xmm0
0x18000eb68  mov     rbx, rdx
0x18000eb6b  movups  xmmword ptr [rsp+68h+var_38], xmm0
0x18000eb70  movups  xmmword ptr [rsp+68h+var_38+0Ch], xmm0
0x18000eb75  movups  xmmword ptr [rsp+68h+Buffer], xmm0
0x18000eb7a  test    rdx, rdx
0x18000eb7d  jnz     short loc_18000EB86
0x18000eb7f  mov     eax, 80070057h
0x18000eb84  jmp     short loc_18000EBA6
0x18000eb86  lea     rdx, [rsp+68h+Buffer]; Buffer
0x18000eb8b  call    cs:__imp__ultow
0x18000eb91  lea     rdx, [rsp+68h+Buffer]
0x18000eb96  mov     rcx, rbx
0x18000eb99  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000eb9f  xor     ecx, ecx
0x18000eba1  test    eax, eax
0x18000eba3  cmovns  eax, ecx
0x18000eba6  mov     rcx, [rsp+68h+var_18]
0x18000ebab  xor     rcx, rsp; StackCookie
0x18000ebae  call    __security_check_cookie
0x18000ebb3  add     rsp, 60h
0x18000ebb7  pop     rbx
0x18000ebb8  retn
```
