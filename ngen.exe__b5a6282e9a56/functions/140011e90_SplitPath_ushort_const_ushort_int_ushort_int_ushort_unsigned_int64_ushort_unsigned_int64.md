# SplitPath(ushort const *,ushort *,int,ushort *,int,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x140011e90`
- end: `0x140011f47`
- name: `?SplitPath@@YAXPEBGPEAGH1H1_K12@Z`
- size: `183`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned __int16 *, __int64, unsigned __int16 *, int, unsigned __int16 *Source, wchar_t *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001281c`

## callees

- `0x140011e90`
- `0x140011f48`

## import_xrefs

- `ucrtbase_clr0400!wcsncpy_s` at `0x140011f04`
- `ucrtbase_clr0400!wcsncpy_s` at `0x140011f2f`
- `ucrtbase_clr0400!wcsncpy_s` at `0x140011f04`
- `ucrtbase_clr0400!wcsncpy_s` at `0x140011f2f`

## pseudocode

```c
void __fastcall SplitPath(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        int a5,
        unsigned __int16 *Source,
        wchar_t *a7,
        unsigned __int16 *a8,
        unsigned __int64 a9)
{
  rsize_t v11; // r9
  rsize_t v12; // r9
  unsigned __int64 v13; // [rsp+50h] [rbp-10h] BYREF
  const unsigned __int16 *v14; // [rsp+58h] [rbp-8h] BYREF
  rsize_t MaxCount; // [rsp+78h] [rbp+18h] BYREF
  rsize_t v16; // [rsp+88h] [rbp+28h] BYREF

  SplitPathInterior(
    a1,
    (const unsigned __int16 **)&Source,
    &MaxCount,
    (const unsigned __int16 **)&a7,
    &v16,
    &v14,
    &v13,
    (const unsigned __int16 **)&a9,
    (unsigned __int64 *)&a8);
  if ( a2 && Source )
  {
    v11 = 3;
    if ( MaxCount < 3 )
      v11 = MaxCount;
    wcsncpy_s(a2, 3u, Source, v11);
  }
  if ( a4 && a7 )
  {
    v12 = 256;
    if ( v16 < 0x100 )
      v12 = v16;
    wcsncpy_s(a4, 0x104u, a7, v12);
  }
}

```

## disassembly

```asm
0x140011e90  mov     r11, rsp
0x140011e93  mov     [r11+8], rbx
0x140011e97  mov     [r11+18h], rdi
0x140011e9b  push    rbp
0x140011e9c  mov     rbp, rsp
0x140011e9f  sub     rsp, 60h
0x140011ea3  lea     rax, [rbp+arg_38]
0x140011ea7  mov     rdi, rdx
0x140011eaa  mov     [r11-28h], rax
0x140011eae  lea     r8, [rbp+MaxCount]; unsigned __int64 *
0x140011eb2  lea     rax, [rbp+arg_40]
0x140011eb6  mov     rbx, r9
0x140011eb9  mov     [r11-30h], rax
0x140011ebd  lea     r9, [rbp+arg_30]; unsigned __int16 **
0x140011ec1  lea     rax, [rbp+var_10]
0x140011ec5  mov     [r11-38h], rax
0x140011ec9  lea     rdx, [rbp+Source]; unsigned __int16 **
0x140011ecd  lea     rax, [rbp+var_8]
0x140011ed1  mov     [r11-40h], rax
0x140011ed5  lea     rax, [rbp+arg_18]
0x140011ed9  mov     [r11-48h], rax
0x140011edd  call    ?SplitPathInterior@@YAXPEBGPEAPEBGPEA_K121212@Z; SplitPathInterior(ushort const *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *)
0x140011ee2  test    rdi, rdi
0x140011ee5  jz      short loc_140011F0A
0x140011ee7  mov     r8, [rbp+Source]; Source
0x140011eeb  test    r8, r8
0x140011eee  jz      short loc_140011F0A
0x140011ef0  mov     edx, 3; SizeInWords
0x140011ef5  mov     rcx, rdi; Destination
0x140011ef8  cmp     [rbp+MaxCount], rdx
0x140011efc  mov     r9d, edx
0x140011eff  cmovb   r9, [rbp+MaxCount]; MaxCount
0x140011f04  call    cs:__imp_wcsncpy_s
0x140011f0a  test    rbx, rbx
0x140011f0d  jz      short loc_140011F35
0x140011f0f  mov     r8, [rbp+arg_30]; Source
0x140011f13  test    r8, r8
0x140011f16  jz      short loc_140011F35
0x140011f18  mov     r9d, 100h
0x140011f1e  mov     edx, 104h; SizeInWords
0x140011f23  cmp     [rbp+arg_18], r9
0x140011f27  mov     rcx, rbx; Destination
0x140011f2a  cmovb   r9, [rbp+arg_18]; MaxCount
0x140011f2f  call    cs:__imp_wcsncpy_s
0x140011f35  lea     r11, [rsp+60h+var_s0]
0x140011f3a  mov     rbx, [r11+10h]
0x140011f3e  mov     rdi, [r11+20h]
0x140011f42  mov     rsp, r11
0x140011f45  pop     rbp
0x140011f46  retn
```
