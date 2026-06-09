# NamedInstanceBuilder_CreateInstance

- ea: `0x140091cc4`
- end: `0x140091d58`
- name: `NamedInstanceBuilder_CreateInstance`
- size: `148`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int, int, __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400318d4`

## callees

- `0x140005a00`
- `0x140091cc4`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140091cdf`
- `KERNEL32!GlobalAlloc` at `0x140091cdf`

## pseudocode

```c
NamedInstanceBuilder *__fastcall NamedInstanceBuilder_CreateInstance(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        int a9,
        int a10,
        unsigned __int16 a11)
{
  NamedInstanceBuilder *result; // rax

  result = (NamedInstanceBuilder *)GlobalAlloc(0, 0x110u);
  if ( result )
    return NamedInstanceBuilder::NamedInstanceBuilder(result, a1, a2, a3, a4, a5, a6, a7, a8, 3u, 1u, a11);
  return result;
}

```

## disassembly

```asm
0x140091cc4  push    rbx
0x140091cc6  push    rbp
0x140091cc7  push    rsi
0x140091cc8  push    rdi
0x140091cc9  sub     rsp, 68h
0x140091ccd  mov     esi, edx
0x140091ccf  mov     rbp, rcx
0x140091cd2  mov     edx, 110h; dwBytes
0x140091cd7  xor     ecx, ecx; uFlags
0x140091cd9  mov     ebx, r9d
0x140091cdc  mov     rdi, r8
0x140091cdf  call    cs:__imp_GlobalAlloc
0x140091ce5  mov     r10, rax
0x140091ce8  test    rax, rax
0x140091ceb  jz      short loc_140091D4F
0x140091ced  movzx   r9d, [rsp+88h+arg_50]
0x140091cf6  mov     r8d, esi; unsigned int
0x140091cf9  mov     ecx, [rsp+88h+arg_38]
0x140091d00  mov     rdx, rbp; unsigned __int8 *
0x140091d03  mov     eax, [rsp+88h+arg_28]
0x140091d0a  mov     [rsp+88h+var_30], r9w; unsigned __int16
0x140091d10  mov     r9, rdi; unsigned __int8 *
0x140091d13  mov     [rsp+88h+var_38], 1; unsigned __int16
0x140091d1a  mov     [rsp+88h+var_40], 3; unsigned __int16
0x140091d21  mov     [rsp+88h+var_48], ecx; unsigned int
0x140091d25  mov     rcx, [rsp+88h+arg_30]
0x140091d2d  mov     [rsp+88h+var_50], rcx; unsigned __int8 *
0x140091d32  mov     rcx, r10; this
0x140091d35  mov     [rsp+88h+var_58], eax; unsigned int
0x140091d39  mov     rax, [rsp+88h+arg_20]
0x140091d41  mov     [rsp+88h+var_60], rax; unsigned __int8 *
0x140091d46  mov     [rsp+88h+var_68], ebx; unsigned int
0x140091d4a  call    ??0NamedInstanceBuilder@@QEAA@PEAEI0I0I0IGGG@Z; NamedInstanceBuilder::NamedInstanceBuilder(uchar *,uint,uchar *,uint,uchar *,uint,uchar *,uint,ushort,ushort,ushort)
0x140091d4f  add     rsp, 68h
0x140091d53  pop     rdi
0x140091d54  pop     rsi
0x140091d55  pop     rbp
0x140091d56  pop     rbx
0x140091d57  retn
```
