# UpdateDirEntryAll

- ea: `0x180019f90`
- end: `0x18001a059`
- name: `UpdateDirEntryAll`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800109fc`
- `0x180013364`

## callees

- `0x180019b9c`
- `0x180019f90`
- `0x18001a060`
- `0x18001a138`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall UpdateDirEntryAll(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int TTDirectory; // edi
  __int16 result; // ax
  __int16 v9; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+38h] [rbp-40h] BYREF

  v9 = 0;
  v10 = 0;
  if ( a3 > a4 + a3 )
    return 1000;
  if ( a4 + a3 > *(_DWORD *)(a1 + 8) )
    return 1000;
  TTDirectory = GetTTDirectory(a1, a2, (__int64)&v10);
  if ( !TTDirectory )
    return 1000;
  HIDWORD(v10) = a3;
  result = ZeroLongWordAlign(a1, a4, (char *)&v10 + 8);
  if ( !result )
  {
    result = CalcChecksum(a1, DWORD2(v10), HIDWORD(v10), (char *)&v10 + 4);
    if ( !result )
      return WriteGeneric(a1, (__int64)&v10, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v9);
  }
  return result;
}

```

## disassembly

```asm
0x180019f90  push    rbx
0x180019f92  push    rbp
0x180019f93  push    rsi
0x180019f94  push    rdi
0x180019f95  push    r14
0x180019f97  sub     rsp, 50h
0x180019f9b  mov     rax, cs:__security_cookie
0x180019fa2  xor     rax, rsp
0x180019fa5  mov     [rsp+78h+var_30], rax
0x180019faa  xor     ebp, ebp
0x180019fac  lea     eax, [r9+r8]
0x180019fb0  mov     [rsp+78h+var_48], bp
0x180019fb5  xorps   xmm0, xmm0
0x180019fb8  mov     r14d, r9d
0x180019fbb  mov     esi, r8d
0x180019fbe  mov     rbx, rcx
0x180019fc1  movups  [rsp+78h+var_40], xmm0
0x180019fc6  cmp     r8d, eax
0x180019fc9  ja      short loc_18001A03C
0x180019fcb  cmp     eax, [rcx+8]
0x180019fce  ja      short loc_18001A03C
0x180019fd0  lea     r8, [rsp+78h+var_40]
0x180019fd5  call    GetTTDirectory
0x180019fda  mov     edi, eax
0x180019fdc  test    eax, eax
0x180019fde  jz      short loc_18001A03C
0x180019fe0  lea     r8, [rsp+78h+var_40+8]
0x180019fe5  mov     dword ptr [rsp+78h+var_40+0Ch], esi
0x180019fe9  mov     edx, r14d
0x180019fec  mov     rcx, rbx
0x180019fef  call    ZeroLongWordAlign
0x180019ff4  test    ax, ax
0x180019ff7  jnz     short loc_18001A041
0x180019ff9  mov     r8d, dword ptr [rsp+78h+var_40+0Ch]
0x180019ffe  lea     r9, [rsp+78h+var_40+4]
0x18001a003  mov     edx, dword ptr [rsp+78h+var_40+8]
0x18001a007  mov     rcx, rbx
0x18001a00a  call    CalcChecksum
0x18001a00f  test    ax, ax
0x18001a012  jnz     short loc_18001A041
0x18001a014  lea     rax, [rsp+78h+var_48]
0x18001a019  mov     rcx, rbx
0x18001a01c  mov     [rsp+78h+var_50], rax
0x18001a021  lea     r8d, [rbp+10h]
0x18001a025  lea     r9, DIRECTORY_CONTROL
0x18001a02c  mov     [rsp+78h+var_58], edi
0x18001a030  lea     rdx, [rsp+78h+var_40]
0x18001a035  call    WriteGeneric
0x18001a03a  jmp     short loc_18001A041
0x18001a03c  mov     eax, 3E8h
0x18001a041  mov     rcx, [rsp+78h+var_30]
0x18001a046  xor     rcx, rsp; StackCookie
0x18001a049  call    __security_check_cookie
0x18001a04e  add     rsp, 50h
0x18001a052  pop     r14
0x18001a054  pop     rdi
0x18001a055  pop     rsi
0x18001a056  pop     rbp
0x18001a057  pop     rbx
0x18001a058  retn
```
