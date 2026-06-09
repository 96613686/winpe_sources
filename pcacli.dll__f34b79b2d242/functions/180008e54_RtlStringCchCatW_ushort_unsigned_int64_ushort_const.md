# RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180008e54`
- end: `0x180008ea0`
- name: `?RtlStringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800092ac`
- `0x18000b0e0`

## callees

- `0x180006fb8`
- `0x180008e54`
- `0x180009258`

## pseudocode

```c
__int64 __fastcall RtlStringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  __int64 v6; // r8
  __int64 v7; // r11
  __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = 0;
  result = RtlStringValidateDestAndLengthW(a1, a2, &v8);
  if ( (int)result >= 0 )
    return RtlStringCopyWorkerW(&a1[v8], v7 - v8, v6, a3);
  return result;
}

```

## disassembly

```asm
0x180008e54  mov     [rsp+arg_0], rbx
0x180008e59  push    rdi
0x180008e5a  sub     rsp, 30h
0x180008e5e  mov     rdi, r8
0x180008e61  mov     [rsp+38h+arg_18], 0
0x180008e6a  lea     r8, [rsp+38h+arg_18]
0x180008e6f  mov     r11, rdx
0x180008e72  mov     rbx, rcx
0x180008e75  call    RtlStringValidateDestAndLengthW
0x180008e7a  test    eax, eax
0x180008e7c  js      short loc_180008E95
0x180008e7e  mov     rax, [rsp+38h+arg_18]
0x180008e83  mov     r9, rdi
0x180008e86  sub     r11, rax
0x180008e89  mov     rdx, r11
0x180008e8c  lea     rcx, [rbx+rax*2]
0x180008e90  call    RtlStringCopyWorkerW
0x180008e95  mov     rbx, [rsp+38h+arg_0]
0x180008e9a  add     rsp, 30h
0x180008e9e  pop     rdi
0x180008e9f  retn
```
