# CFileStream::Write(void const *,ulong,ulong *)

- ea: `0x18000dea0`
- end: `0x18000def5`
- name: `?Write@CFileStream@@UEAAJPEBXKPEAK@Z`
- size: `85`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000dea0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000deca`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000deca`

## pseudocode

```c
__int64 __fastcall CFileStream::Write(CFileStream *this, const void *a2, unsigned int a3, unsigned int *a4)
{
  if ( a3 != _o_fwrite(a2, 1, a3, *((_QWORD *)this + 68)) )
    return 2147680368LL;
  if ( a4 )
    *a4 = a3;
  return 0;
}

```

## disassembly

```asm
0x18000dea0  mov     [rsp+arg_0], rbx
0x18000dea5  mov     [rsp+arg_8], rsi
0x18000deaa  push    rdi
0x18000deab  sub     rsp, 20h
0x18000deaf  mov     rax, rdx
0x18000deb2  mov     esi, r8d
0x18000deb5  mov     rdi, r9
0x18000deb8  mov     r8d, r8d
0x18000debb  mov     r9, [rcx+220h]
0x18000dec2  mov     edx, 1
0x18000dec7  mov     rcx, rax
0x18000deca  call    cs:__imp__o_fwrite
0x18000ded0  cmp     rsi, rax
0x18000ded3  jnz     short loc_18000DEE0
0x18000ded5  test    rdi, rdi
0x18000ded8  jz      short loc_18000DEDC
0x18000deda  mov     [rdi], esi
0x18000dedc  xor     eax, eax
0x18000dede  jmp     short loc_18000DEE5
0x18000dee0  mov     eax, 80030070h
0x18000dee5  mov     rbx, [rsp+28h+arg_0]
0x18000deea  mov     rsi, [rsp+28h+arg_8]
0x18000deef  add     rsp, 20h
0x18000def3  pop     rdi
0x18000def4  retn
```
