# AslLogPrintf

- ea: `0x180003110`
- end: `0x1800031cf`
- name: `AslLogPrintf`
- size: `191`
- prototype: `__int64 __fastcall(struct _ASL_LOG *, char *Format)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002f7c`
- `0x1800089d0`

## callees

- `0x180003110`
- `0x180007200`
- `0x18000c030`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180003160`
- `msvcrt!_vsnprintf` at `0x180003160`

## pseudocode

```c
__int64 AslLogPrintf(struct _ASL_LOG *a1, char *Format, ...)
{
  unsigned int v3; // eax
  size_t v5; // r8
  char Buffer[1023]; // [rsp+30h] [rbp-418h] BYREF
  char v7; // [rsp+42Fh] [rbp-19h]
  va_list va; // [rsp+460h] [rbp+18h] BYREF

  va_start(va, Format);
  if ( !a1 )
    return 3221225485LL;
  Buffer[0] = 0;
  v3 = _vsnprintf(Buffer, 0x3FFu, Format, va);
  if ( v3 < 0x400 )
  {
    if ( v3 == 1023 )
      v7 = 0;
    v5 = -1;
    do
      ++v5;
    while ( Buffer[v5] );
    AslLogpWriteLog(a1, Buffer, v5);
    return 0;
  }
  else
  {
    v7 = 0;
    return 2147483653LL;
  }
}

```

## disassembly

```asm
0x180003110  mov     r11, rsp
0x180003113  mov     [r11+10h], rdx
0x180003117  mov     [r11+18h], r8
0x18000311b  mov     [r11+20h], r9
0x18000311f  push    rbx
0x180003120  sub     rsp, 440h
0x180003127  mov     rax, cs:__security_cookie
0x18000312e  xor     rax, rsp
0x180003131  mov     [rsp+448h+var_18], rax
0x180003139  mov     [rsp+448h+var_428], 0
0x180003142  mov     rbx, rcx
0x180003145  lea     r9, [r11+18h]; ArgList
0x180003149  test    rcx, rcx
0x18000314c  jz      short loc_180003190
0x18000314e  mov     r8, rdx; Format
0x180003151  mov     [rsp+448h+Buffer], 0
0x180003156  mov     edx, 3FFh; BufferCount
0x18000315b  lea     rcx, [rsp+448h+Buffer]; Buffer
0x180003160  call    cs:__imp__vsnprintf
0x180003166  test    eax, eax
0x180003168  jns     short loc_180003197
0x18000316a  mov     [rsp+448h+var_19], 0
0x180003172  mov     eax, 80000005h
0x180003177  mov     rcx, [rsp+448h+var_18]
0x18000317f  xor     rcx, rsp; StackCookie
0x180003182  call    __security_check_cookie
0x180003187  add     rsp, 440h
0x18000318e  pop     rbx
0x18000318f  retn
0x180003190  mov     eax, 0C000000Dh
0x180003195  jmp     short loc_180003177
0x180003197  cmp     eax, 3FFh
0x18000319c  ja      short loc_18000316A
0x18000319e  jnz     short loc_1800031A8
0x1800031a0  mov     [rsp+448h+var_19], 0
0x1800031a8  lea     rax, [rsp+448h+Buffer]
0x1800031ad  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800031b4  inc     r8; unsigned __int64
0x1800031b7  cmp     byte ptr [rax+r8], 0
0x1800031bc  jnz     short loc_1800031B4
0x1800031be  lea     rdx, [rsp+448h+Buffer]; char *
0x1800031c3  mov     rcx, rbx; struct _ASL_LOG *
0x1800031c6  call    ?AslLogpWriteLog@@YAXPEAU_ASL_LOG@@PEBD_K@Z; AslLogpWriteLog(_ASL_LOG *,char const *,unsigned __int64)
0x1800031cb  xor     eax, eax
0x1800031cd  jmp     short loc_180003177
```
