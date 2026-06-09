# ATL::CAtlPlex::Create(ATL::CAtlPlex * &,unsigned __int64,unsigned __int64)

- ea: `0x180017630`
- end: `0x180017683`
- name: `?Create@CAtlPlex@ATL@@SAPEAU12@AEAPEAU12@_K1@Z`
- size: `83`
- prototype: `struct ATL::CAtlPlex *__fastcall(struct ATL::CAtlPlex **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18001acd4`
- `0x18001ad80`
- `0x18001aea8`

## callees

- `0x180002b74`
- `0x180017630`

## import_xrefs

- `msvcrt!malloc` at `0x180017665`
- `msvcrt!malloc` at `0x180017665`

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
0x180017630  push    rbx
0x180017632  sub     rsp, 20h
0x180017636  mov     rbx, rcx
0x180017639  mov     [rsp+28h+arg_18], 0
0x180017642  lea     rcx, [rsp+28h+arg_18]
0x180017647  call    ??$AtlMultiply@_K@ATL@@YAJPEA_K_K1@Z; ATL::AtlMultiply<unsigned __int64>(unsigned __int64 *,unsigned __int64,unsigned __int64)
0x18001764c  test    eax, eax
0x18001764e  js      short loc_18001767B
0x180017650  mov     rcx, [rsp+28h+arg_18]
0x180017655  mov     rax, rcx
0x180017658  not     rax
0x18001765b  cmp     rax, 8
0x18001765f  jb      short loc_18001767B
0x180017661  add     rcx, 8; Size
0x180017665  call    cs:__imp_malloc
0x18001766b  test    rax, rax
0x18001766e  jz      short loc_18001767B
0x180017670  mov     rcx, [rbx]
0x180017673  mov     [rax], rcx
0x180017676  mov     [rbx], rax
0x180017679  jmp     short loc_18001767D
0x18001767b  xor     eax, eax
0x18001767d  add     rsp, 20h
0x180017681  pop     rbx
0x180017682  retn
```
