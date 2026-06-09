# ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)

- ea: `0x180014128`
- end: `0x18001417b`
- name: `?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z`
- size: `83`
- prototype: `struct ATL::CAtlPlex *__fastcall(struct ATL::CAtlPlex **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157e8`
- `0x180015884`
- `0x18001a4fc`

## callees

- `0x180002dec`
- `0x180014128`

## import_xrefs

- `msvcrt!malloc` at `0x18001415d`
- `msvcrt!malloc` at `0x18001415d`

## pseudocode

```c
struct ATL::CAtlPlex *__fastcall ATL::CAtlPlex::Create(struct ATL::CAtlPlex **a1)
{
  struct ATL::CAtlPlex *result; // rax
  __int64 v3; // [rsp+48h] [rbp+20h] BYREF

  v3 = 0;
  if ( (int)ATL::AtlMultiply<unsigned __int64>(&v3) < 0 )
    return 0;
  if ( (unsigned __int64)~v3 < 8 )
    return 0;
  result = (struct ATL::CAtlPlex *)malloc(v3 + 8);
  if ( !result )
    return 0;
  *(_QWORD *)result = *a1;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180014128  push    rbx
0x18001412a  sub     rsp, 20h
0x18001412e  mov     rbx, rcx
0x180014131  mov     [rsp+28h+arg_18], 0
0x18001413a  lea     rcx, [rsp+28h+arg_18]
0x18001413f  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x180014144  test    eax, eax
0x180014146  js      short loc_180014173
0x180014148  mov     rcx, [rsp+28h+arg_18]
0x18001414d  mov     rax, rcx
0x180014150  not     rax
0x180014153  cmp     rax, 8
0x180014157  jb      short loc_180014173
0x180014159  add     rcx, 8; Size
0x18001415d  call    cs:__imp_malloc
0x180014163  test    rax, rax
0x180014166  jz      short loc_180014173
0x180014168  mov     rcx, [rbx]
0x18001416b  mov     [rax], rcx
0x18001416e  mov     [rbx], rax
0x180014171  jmp     short loc_180014175
0x180014173  xor     eax, eax
0x180014175  add     rsp, 20h
0x180014179  pop     rbx
0x18001417a  retn
```
