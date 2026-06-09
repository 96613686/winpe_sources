# _anonymous_namespace_::__vcp_CreateFile

- ea: `0x180001190`
- end: `0x1800011ed`
- name: `_anonymous_namespace_::__vcp_CreateFile`
- size: `93`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, int, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001674`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800011e2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800011e2`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::__vcp_CreateFile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  _DWORD v8[4]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]
  __int64 v10; // [rsp+48h] [rbp-10h]

  v8[1] = (unsigned __int16)a6;
  v8[3] = 0;
  v8[0] = 32;
  v10 = a7;
  v9 = a4;
  v8[2] = a6 & 0xFFFF0000;
  return CreateFile2(a1, a2, a3, a5, v8);
}

```

## disassembly

```asm
0x180001190  mov     r11, rsp
0x180001193  sub     rsp, 58h
0x180001197  mov     r10d, [rsp+58h+arg_28]
0x18000119f  movzx   eax, r10w
0x1800011a3  and     r10d, 0FFFF0000h
0x1800011aa  mov     [rsp+58h+var_24], eax
0x1800011ae  mov     rax, [rsp+58h+arg_30]
0x1800011b6  mov     [rsp+58h+var_1C], 0
0x1800011be  mov     [rsp+58h+var_28], 20h ; ' '
0x1800011c6  mov     [r11-10h], rax
0x1800011ca  lea     rax, [r11-28h]
0x1800011ce  mov     [r11-18h], r9
0x1800011d2  mov     r9d, [rsp+58h+arg_20]
0x1800011da  mov     [r11-38h], rax
0x1800011de  mov     [r11-20h], r10d
0x1800011e2  call    cs:__imp_CreateFile2
0x1800011e8  add     rsp, 58h
0x1800011ec  retn
```
