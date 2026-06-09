# StringToNewString(ushort *,ulong,ushort * *)

- ea: `0x18002d8b4`
- end: `0x18002d92d`
- name: `?StringToNewString@@YAJPEAGKPEAPEAG@Z`
- size: `121`
- prototype: `__int64 __fastcall(unsigned __int16 *Src, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18002c604`
- `0x18002d934`

## callees

- `0x18002d8b4`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18002d8f3`
- `ole32!CoTaskMemAlloc` at `0x18002d8f3`

## pseudocode

```c
__int64 __fastcall StringToNewString(unsigned __int16 *Src, unsigned int a2, unsigned __int16 **a3)
{
  unsigned __int16 *v7; // rax

  if ( a2 > 0x7FFFFFFE )
    return 2147942934LL;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(a2 + 1, 2u));
  *a3 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, Src, 2 * a2 + 2);
  return 0;
}

```

## disassembly

```asm
0x18002d8b4  mov     [rsp+arg_0], rbx
0x18002d8b9  mov     [rsp+arg_8], rsi
0x18002d8be  push    rdi
0x18002d8bf  sub     rsp, 20h
0x18002d8c3  mov     rsi, r8
0x18002d8c6  mov     ebx, edx
0x18002d8c8  mov     rdi, rcx
0x18002d8cb  cmp     edx, 7FFFFFFEh
0x18002d8d1  jbe     short loc_18002D8DA
0x18002d8d3  mov     eax, 80070216h
0x18002d8d8  jmp     short loc_18002D91D
0x18002d8da  lea     ecx, [rdx+1]
0x18002d8dd  mov     eax, 2
0x18002d8e2  mul     rcx
0x18002d8e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d8ec  cmovb   rax, rcx
0x18002d8f0  mov     rcx, rax; cb
0x18002d8f3  call    cs:__imp_CoTaskMemAlloc
0x18002d8f9  mov     [rsi], rax
0x18002d8fc  mov     rcx, rax; void *
0x18002d8ff  test    rax, rax
0x18002d902  jnz     short loc_18002D90B
0x18002d904  mov     eax, 8007000Eh
0x18002d909  jmp     short loc_18002D91D
0x18002d90b  lea     r8d, ds:2[rbx*2]; Size
0x18002d913  mov     rdx, rdi; Src
0x18002d916  call    memcpy_0
0x18002d91b  xor     eax, eax
0x18002d91d  mov     rbx, [rsp+28h+arg_0]
0x18002d922  mov     rsi, [rsp+28h+arg_8]
0x18002d927  add     rsp, 20h
0x18002d92b  pop     rdi
0x18002d92c  retn
```
