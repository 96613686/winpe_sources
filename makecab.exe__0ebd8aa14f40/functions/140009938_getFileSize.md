# getFileSize

- ea: `0x140009938`
- end: `0x1400099cb`
- name: `getFileSize`
- size: `147`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140003c88`
- `0x14000488c`
- `0x140007e18`

## callees

- `0x140008620`
- `0x140009938`
- `0x14000e450`

## import_xrefs

- `msvcrt!_stat` at `0x14000996e`
- `msvcrt!_stat` at `0x14000996e`

## pseudocode

```c
__int64 __fastcall getFileSize(const char *a1, __int64 a2)
{
  const char *v4; // rdx
  stat Stat; // [rsp+20h] [rbp-48h] BYREF

  memset(&Stat, 0, sizeof(Stat));
  if ( _stat(a1, &Stat) == -1 )
  {
    v4 = "Could not find file: %1";
LABEL_3:
    ErrSet(a2, (int)v4, "%s", a1);
    return 0xFFFFFFFFLL;
  }
  if ( (Stat.st_mode & 0x6000) != 0 )
  {
    v4 = "%1 is not a file";
    goto LABEL_3;
  }
  return (unsigned int)Stat.st_size;
}

```

## disassembly

```asm
0x140009938  mov     [rsp+arg_10], rbx
0x14000993d  push    rdi
0x14000993e  sub     rsp, 60h
0x140009942  mov     rax, cs:__security_cookie
0x140009949  xor     rax, rsp
0x14000994c  mov     [rsp+68h+var_18], rax
0x140009951  xorps   xmm0, xmm0
0x140009954  mov     rdi, rdx
0x140009957  lea     rdx, [rsp+68h+Stat]; Stat
0x14000995c  mov     rbx, rcx
0x14000995f  movups  xmmword ptr [rsp+68h+Stat.st_dev], xmm0
0x140009964  movups  xmmword ptr [rsp+68h+Stat.st_rdev], xmm0
0x140009969  movups  xmmword ptr [rsp+68h+Stat.st_mtime], xmm0
0x14000996e  call    cs:__imp__stat
0x140009974  cmp     eax, 0FFFFFFFFh
0x140009977  jnz     short loc_140009997
0x140009979  lea     rdx, aCouldNotFindFi; "Could not find file: %1"
0x140009980  lea     r8, aS_4; "%s"
0x140009987  mov     r9, rbx
0x14000998a  mov     rcx, rdi
0x14000998d  call    ErrSet
0x140009992  or      eax, 0FFFFFFFFh
0x140009995  jmp     short loc_1400099B0
0x140009997  mov     eax, 6000h
0x14000999c  test    [rsp+68h+Stat.st_mode], ax
0x1400099a1  jz      short loc_1400099AC
0x1400099a3  lea     rdx, a1IsNotAFile; "%1 is not a file"
0x1400099aa  jmp     short loc_140009980
0x1400099ac  mov     eax, [rsp+68h+Stat.st_size]
0x1400099b0  mov     rcx, [rsp+68h+var_18]
0x1400099b5  xor     rcx, rsp; StackCookie
0x1400099b8  call    __security_check_cookie
0x1400099bd  mov     rbx, [rsp+68h+arg_10]
0x1400099c5  add     rsp, 60h
0x1400099c9  pop     rdi
0x1400099ca  retn
```
