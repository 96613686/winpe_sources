# KsecUpdateUserTokenSessionId(void *,ulong)

- ea: `0x18000da6c`
- end: `0x18000dacb`
- name: `?KsecUpdateUserTokenSessionId@@YAJPEAXK@Z`
- size: `95`
- prototype: `__int64 __fastcall(void *Src, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800053e0`

## callees

- `0x180007a64`
- `0x18000da6c`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000da8f`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000da8f`
- `ntoskrnl!SeSetSessionIdTokenWithLinked` at `0x18000dab2`
- `ntoskrnl!SeSetSessionIdTokenWithLinked` at `0x18000dab2`

## pseudocode

```c
__int64 __fastcall KsecUpdateUserTokenSessionId(void *Src, unsigned int a2)
{
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF

  if ( a2 < 0x10 )
    return 3221225485LL;
  v3 = 0;
  if ( ((unsigned __int8)Src & 7) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(&v3, Src, 0x10u);
  return SeSetSessionIdTokenWithLinked(v3, DWORD2(v3));
}

```

## disassembly

```asm
0x18000da6c  sub     rsp, 38h
0x18000da70  mov     r8d, 10h
0x18000da76  cmp     edx, r8d
0x18000da79  jnb     short loc_18000DA82
0x18000da7b  mov     eax, 0C000000Dh
0x18000da80  jmp     short loc_18000DAC5
0x18000da82  xorps   xmm0, xmm0
0x18000da85  movups  [rsp+38h+var_18], xmm0
0x18000da8a  test    cl, 7
0x18000da8d  jz      short loc_18000DA9B
0x18000da8f  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000da96  nop     dword ptr [rax+rax+00h]
0x18000da9b  mov     rdx, rcx; Src
0x18000da9e  lea     rcx, [rsp+38h+var_18]; void *
0x18000daa3  call    RtlCopyFromUser
0x18000daa8  nop
0x18000daa9  mov     edx, dword ptr [rsp+38h+var_18+8]
0x18000daad  mov     rcx, qword ptr [rsp+38h+var_18]
0x18000dab2  call    cs:__imp_SeSetSessionIdTokenWithLinked
0x18000dab9  nop     dword ptr [rax+rax+00h]
0x18000dabe  jmp     short loc_18000DAC5
0x18000dac0  mov     eax, 0C0000005h
0x18000dac5  add     rsp, 38h
0x18000dac9  retn
```
