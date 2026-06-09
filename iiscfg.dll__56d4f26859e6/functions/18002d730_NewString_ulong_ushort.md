# NewString(ulong,ushort * *)

- ea: `0x18002d730`
- end: `0x18002d783`
- name: `?NewString@@YAJKPEAPEAG@Z`
- size: `83`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18002c2d4`
- `0x18002c604`
- `0x18002d934`

## callees

- `0x18002d730`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002d760`
- `ole32!CoTaskMemAlloc` at `0x18002d760`

## pseudocode

```c
__int64 __fastcall NewString(unsigned int a1, unsigned __int16 **a2)
{
  __int64 result; // rax
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rcx

  if ( a1 > 0x7FFFFFFE )
    return 2147942934LL;
  v4 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(a1 + 1, 2u));
  *a2 = v4;
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  result = 0;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x18002d730  push    rbx
0x18002d732  sub     rsp, 20h
0x18002d736  mov     rbx, rdx
0x18002d739  cmp     ecx, 7FFFFFFEh
0x18002d73f  jbe     short loc_18002D748
0x18002d741  mov     eax, 80070216h
0x18002d746  jmp     short loc_18002D77D
0x18002d748  inc     ecx
0x18002d74a  mov     eax, 2
0x18002d74f  mul     rcx
0x18002d752  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d759  cmovb   rax, rcx
0x18002d75d  mov     rcx, rax; cb
0x18002d760  call    cs:__imp_CoTaskMemAlloc
0x18002d766  mov     [rbx], rax
0x18002d769  mov     rcx, rax
0x18002d76c  test    rax, rax
0x18002d76f  jnz     short loc_18002D778
0x18002d771  mov     eax, 8007000Eh
0x18002d776  jmp     short loc_18002D77D
0x18002d778  xor     eax, eax
0x18002d77a  mov     [rcx], ax
0x18002d77d  add     rsp, 20h
0x18002d781  pop     rbx
0x18002d782  retn
```
