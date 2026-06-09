# ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)

- ea: `0x18000f0b8`
- end: `0x18000f115`
- name: `?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z`
- size: `93`
- prototype: `struct ATL::CAtlPlex *__fastcall(struct ATL::CAtlPlex **, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bac8`
- `0x18000bff8`

## callees

- `0x180008f50`
- `0x18000f0b8`

## import_xrefs

- `msvcrt!malloc` at `0x18000f0f7`
- `msvcrt!malloc` at `0x18000f0f7`

## pseudocode

```c
struct ATL::CAtlPlex *__fastcall ATL::CAtlPlex::Create(struct ATL::CAtlPlex **a1, __int64 a2)
{
  struct ATL::CAtlPlex *result; // rax
  __int64 v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&v4, a2, 48) < 0 )
    return 0;
  if ( (unsigned __int64)~v4 < 8 )
    return 0;
  result = (struct ATL::CAtlPlex *)malloc(v4 + 8);
  if ( !result )
    return 0;
  *(_QWORD *)result = *a1;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x18000f0b8  mov     [rsp+arg_10], r8
0x18000f0bd  push    rbx
0x18000f0be  sub     rsp, 20h
0x18000f0c2  mov     rbx, rcx
0x18000f0c5  mov     [rsp+28h+arg_10], 0
0x18000f0ce  lea     rcx, [rsp+28h+arg_10]
0x18000f0d3  mov     r8d, 30h ; '0'
0x18000f0d9  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18000f0de  test    eax, eax
0x18000f0e0  js      short loc_18000F10D
0x18000f0e2  mov     rcx, [rsp+28h+arg_10]
0x18000f0e7  mov     rax, rcx
0x18000f0ea  not     rax
0x18000f0ed  cmp     rax, 8
0x18000f0f1  jb      short loc_18000F10D
0x18000f0f3  add     rcx, 8; Size
0x18000f0f7  call    cs:__imp_malloc
0x18000f0fd  test    rax, rax
0x18000f100  jz      short loc_18000F10D
0x18000f102  mov     rcx, [rbx]
0x18000f105  mov     [rax], rcx
0x18000f108  mov     [rbx], rax
0x18000f10b  jmp     short loc_18000F10F
0x18000f10d  xor     eax, eax
0x18000f10f  add     rsp, 20h
0x18000f113  pop     rbx
0x18000f114  retn
```
