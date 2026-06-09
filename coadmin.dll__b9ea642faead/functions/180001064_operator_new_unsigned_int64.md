# operator new(unsigned __int64)

- ea: `0x180001064`
- end: `0x18000109d`
- name: `??2@YAPEAX_K@Z`
- size: `57`
- prototype: `void *__fastcall(size_t Size)`
- caller_count: `12`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010bc`
- `0x1800021e4`
- `0x180003590`
- `0x1800068d4`
- `0x180009dd0`
- `0x18000a0b0`
- `0x18000b988`
- `0x18000c360`
- `0x18000c8d0`
- `0x18000c9a0`
- `0x18000ca70`
- `0x18000dafc`

## callees

- `0x180001064`
- `0x180001842`
- `0x18000184e`

## pseudocode

```c
void *__fastcall operator new(size_t Size)
{
  size_t i; // rdi
  void *v2; // rbx

  for ( i = Size; ; Size = i )
  {
    v2 = malloc_0(Size);
    if ( v2 || !callnewh_0(i) )
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x180001064  mov     [rsp+arg_0], rbx
0x180001069  push    rdi
0x18000106a  sub     rsp, 20h
0x18000106e  mov     rdi, rcx
0x180001071  jmp     short loc_180001082
0x180001073  mov     rcx, rdi; Size
0x180001076  call    _callnewh_0
0x18000107b  test    eax, eax
0x18000107d  jz      short loc_18000108F
0x18000107f  mov     rcx, rdi; Size
0x180001082  call    malloc_0
0x180001087  mov     rbx, rax
0x18000108a  test    rax, rax
0x18000108d  jz      short loc_180001073
0x18000108f  mov     rax, rbx
0x180001092  mov     rbx, [rsp+28h+arg_0]
0x180001097  add     rsp, 20h
0x18000109b  pop     rdi
0x18000109c  retn
```
