# UpdateDirEntry

- ea: `0x180019ec0`
- end: `0x180019f8a`
- name: `UpdateDirEntry`
- size: `202`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800075f4`
- `0x18000fd08`
- `0x180010088`
- `0x180010284`
- `0x1800105d0`
- `0x1800108e4`
- `0x180010fd4`
- `0x1800115ac`
- `0x180013364`

## callees

- `0x180019b9c`
- `0x180019ec0`
- `0x18001a0c0`
- `0x18001a138`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall UpdateDirEntry(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 result; // ax
  unsigned int TTDirectory; // esi
  __int16 v7; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF

  v8 = 0;
  v7 = 0;
  if ( a3 > *(_DWORD *)(a1 + 8) )
    return 1000;
  TTDirectory = GetTTDirectory(a1, a2, &v8);
  if ( !TTDirectory )
    return 0;
  HIDWORD(v8) = a3;
  result = ZeroLongWordGap(a1, DWORD2(v8), a3, 0);
  if ( !result )
  {
    result = CalcChecksum(a1, DWORD2(v8), a3, (char *)&v8 + 4);
    if ( !result )
      return WriteGeneric(a1, (__int64)&v8, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v7);
  }
  return result;
}

```

## disassembly

```asm
0x180019ec0  mov     [rsp+arg_18], rbx
0x180019ec5  push    rbp
0x180019ec6  push    rsi
0x180019ec7  push    rdi
0x180019ec8  sub     rsp, 50h
0x180019ecc  mov     rax, cs:__security_cookie
0x180019ed3  xor     rax, rsp
0x180019ed6  mov     [rsp+68h+var_20], rax
0x180019edb  xor     ebp, ebp
0x180019edd  xorps   xmm0, xmm0
0x180019ee0  mov     edi, r8d
0x180019ee3  mov     rbx, rcx
0x180019ee6  movups  [rsp+68h+var_30], xmm0
0x180019eeb  mov     [rsp+68h+var_38], bp
0x180019ef0  cmp     r8d, [rcx+8]
0x180019ef4  jbe     short loc_180019EFD
0x180019ef6  mov     eax, 3E8h
0x180019efb  jmp     short loc_180019F6D
0x180019efd  lea     r8, [rsp+68h+var_30]
0x180019f02  call    GetTTDirectory
0x180019f07  mov     esi, eax
0x180019f09  test    eax, eax
0x180019f0b  jz      short loc_180019F6B
0x180019f0d  mov     edx, dword ptr [rsp+68h+var_30+8]
0x180019f11  xor     r9d, r9d
0x180019f14  mov     r8d, edi
0x180019f17  mov     dword ptr [rsp+68h+var_30+0Ch], edi
0x180019f1b  mov     rcx, rbx
0x180019f1e  call    ZeroLongWordGap
0x180019f23  test    ax, ax
0x180019f26  jnz     short loc_180019F6D
0x180019f28  mov     edx, dword ptr [rsp+68h+var_30+8]
0x180019f2c  lea     r9, [rsp+68h+var_30+4]
0x180019f31  mov     r8d, edi
0x180019f34  mov     rcx, rbx
0x180019f37  call    CalcChecksum
0x180019f3c  test    ax, ax
0x180019f3f  jnz     short loc_180019F6D
0x180019f41  lea     rax, [rsp+68h+var_38]
0x180019f46  mov     r8d, 10h
0x180019f4c  mov     [rsp+68h+var_40], rax
0x180019f51  lea     r9, DIRECTORY_CONTROL
0x180019f58  lea     rdx, [rsp+68h+var_30]
0x180019f5d  mov     [rsp+68h+var_48], esi
0x180019f61  mov     rcx, rbx
0x180019f64  call    WriteGeneric
0x180019f69  jmp     short loc_180019F6D
0x180019f6b  mov     eax, ebp
0x180019f6d  mov     rcx, [rsp+68h+var_20]
0x180019f72  xor     rcx, rsp; StackCookie
0x180019f75  call    __security_check_cookie
0x180019f7a  mov     rbx, [rsp+68h+arg_18]
0x180019f82  add     rsp, 50h
0x180019f86  pop     rdi
0x180019f87  pop     rsi
0x180019f88  pop     rbp
0x180019f89  retn
```
