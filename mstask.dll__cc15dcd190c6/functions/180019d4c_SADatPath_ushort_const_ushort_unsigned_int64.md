# SADatPath(ushort const *,ushort *,unsigned __int64)

- ea: `0x180019d4c`
- end: `0x180019da5`
- name: `?SADatPath@@YAXPEBGPEAG_K@Z`
- size: `89`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800199e4`
- `0x180019bb0`

## callees

- `0x180001840`
- `0x180006f90`
- `0x18001aac0`

## pseudocode

```c
void __fastcall SADatPath(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v2; // r11d
  unsigned __int16 *v3; // r10
  unsigned __int16 v4[8]; // [rsp+20h] [rbp-28h] BYREF

  *(_OWORD *)v4 = *(_OWORD *)L"\\SA.DAT";
  StringCchCopyW(a2, 0x105u, a1);
  StringCchCatW(v3, v2, v4);
}

```

## disassembly

```asm
0x180019d4c  sub     rsp, 48h
0x180019d50  mov     rax, cs:__security_cookie
0x180019d57  xor     rax, rsp
0x180019d5a  mov     [rsp+48h+var_18], rax
0x180019d5f  movups  xmm0, xmmword ptr cs:aSaDat; "\\SA.DAT"
0x180019d66  mov     r10, rdx
0x180019d69  mov     r8, rcx; unsigned __int16 *
0x180019d6c  mov     r11d, 105h
0x180019d72  mov     rcx, r10; unsigned __int16 *
0x180019d75  mov     edx, r11d; unsigned __int64
0x180019d78  movdqu  xmmword ptr [rsp+48h+var_28], xmm0
0x180019d7e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019d83  lea     r8, [rsp+48h+var_28]; unsigned __int16 *
0x180019d88  mov     edx, r11d; unsigned __int64
0x180019d8b  mov     rcx, r10; unsigned __int16 *
0x180019d8e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019d93  mov     rcx, [rsp+48h+var_18]
0x180019d98  xor     rcx, rsp; StackCookie
0x180019d9b  call    __security_check_cookie
0x180019da0  add     rsp, 48h
0x180019da4  retn
```
