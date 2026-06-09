# RtlStringVPrintfWorkerA

- ea: `0x1800071a0`
- end: `0x1800071ee`
- name: `RtlStringVPrintfWorkerA`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800076f8`
- `0x180008ea8`

## callees

- `0x1800071a0`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x1800071bc`
- `msvcrt!_vsnprintf` at `0x1800071bc`

## pseudocode

```c
__int64 __fastcall RtlStringVPrintfWorkerA(char *a1, __int64 a2, __int64 a3, const char *a4, va_list ArgList)
{
  unsigned __int64 v5; // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 result; // rax

  v5 = a2 - 1;
  v7 = _vsnprintf(a1, a2 - 1, a4, ArgList);
  if ( v7 < 0 || (v8 = v7, v7 > v5) )
  {
    a1[v5] = 0;
    return 2147483653LL;
  }
  else
  {
    result = 0;
    if ( v8 == v5 )
      a1[v5] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800071a0  mov     [rsp+arg_0], rbx
0x1800071a5  push    rdi
0x1800071a6  sub     rsp, 20h
0x1800071aa  lea     rbx, [rdx-1]
0x1800071ae  mov     r8, r9; Format
0x1800071b1  mov     r9, [rsp+28h+ArgList]; ArgList
0x1800071b6  mov     rdx, rbx; BufferCount
0x1800071b9  mov     rdi, rcx
0x1800071bc  call    cs:__imp__vsnprintf
0x1800071c2  test    eax, eax
0x1800071c4  js      short loc_1800071DA
0x1800071c6  movsxd  rdx, eax
0x1800071c9  cmp     rdx, rbx
0x1800071cc  ja      short loc_1800071DA
0x1800071ce  xor     eax, eax
0x1800071d0  cmp     rdx, rbx
0x1800071d3  jnz     short loc_1800071E3
0x1800071d5  mov     [rbx+rdi], al
0x1800071d8  jmp     short loc_1800071E3
0x1800071da  mov     byte ptr [rbx+rdi], 0
0x1800071de  mov     eax, 80000005h
0x1800071e3  mov     rbx, [rsp+28h+arg_0]
0x1800071e8  add     rsp, 20h
0x1800071ec  pop     rdi
0x1800071ed  retn
```
