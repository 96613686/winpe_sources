# operator new(unsigned __int64,zerofill_t)

- ea: `0x180005da0`
- end: `0x180005ddc`
- name: `??2@YAPEAX_KUzerofill_t@@@Z`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `41`
- callee_count: `3`
- tags: ``

## callers

- `0x180001520`
- `0x180002810`
- `0x180002dd0`
- `0x180003810`
- `0x180003b40`
- `0x180004bb0`
- `0x180005e70`
- `0x180006bc0`
- `0x180008c30`
- `0x1800093a8`
- `0x18000b350`
- `0x18000bbec`
- `0x18000bf38`
- `0x18000c2b0`
- `0x18000c424`
- `0x18000cc70`
- `0x18000d158`
- `0x18000d4ac`
- `0x18000d534`
- `0x18000da58`
- `0x18000e1a8`
- `0x18000f640`
- `0x18000fb6c`
- `0x180010430`
- `0x180010f28`
- `0x180011180`
- `0x180011568`
- `0x180011d10`
- `0x1800146c8`
- `0x180014b54`
- `0x180015250`
- `0x1800158e8`
- `0x180015b1c`
- `0x180015e20`
- `0x1800161a4`
- `0x180016260`
- `0x1800166cc`
- `0x18001681c`
- `0x1800168e0`
- `0x180016940`
- `0x180016a70`

## callees

- `0x180005da0`
- `0x180008042`
- `0x18000805c`

## pseudocode

```c
void *__fastcall operator new(unsigned __int64 a1)
{
  void *result; // rax
  void *v3; // rbx

  result = operator new(a1, (const struct std::nothrow_t *)&std::nothrow);
  v3 = result;
  if ( result )
  {
    memset_0(result, 0, a1);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180005da0  mov     [rsp+arg_0], rbx
0x180005da5  push    rdi
0x180005da6  sub     rsp, 20h
0x180005daa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005db1  mov     rdi, rcx
0x180005db4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005db9  mov     rbx, rax
0x180005dbc  test    rax, rax
0x180005dbf  jz      short loc_180005DD1
0x180005dc1  mov     r8, rdi; Size
0x180005dc4  xor     edx, edx; Val
0x180005dc6  mov     rcx, rax; void *
0x180005dc9  call    memset_0
0x180005dce  mov     rax, rbx
0x180005dd1  mov     rbx, [rsp+28h+arg_0]
0x180005dd6  add     rsp, 20h
0x180005dda  pop     rdi
0x180005ddb  retn
```
