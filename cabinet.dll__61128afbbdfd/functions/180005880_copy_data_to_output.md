# copy_data_to_output

- ea: `0x180005880`
- end: `0x1800058dc`
- name: `copy_data_to_output`
- size: `92`
- prototype: `void *__fastcall(__int64, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000548c`

## callees

- `0x180005880`
- `0x1800067c0`
- `0x18001b625`

## pseudocode

```c
void *__fastcall copy_data_to_output(__int64 a1, unsigned int a2, void *a3)
{
  void *v5; // rcx
  void *result; // rax

  v5 = *(void **)(a1 + 11032);
  result = a3;
  if ( v5 )
  {
    result = memcpy_0(v5, a3, (int)a2);
    if ( *(_DWORD *)(a1 + 11988) )
    {
      if ( *(_DWORD *)(a1 + 11996) < 0x8000u )
        return (void *)decoder_translate_e8(a1, *(_QWORD *)(a1 + 11032), a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005880  mov     [rsp+arg_0], rbx
0x180005885  push    rdi
0x180005886  sub     rsp, 20h
0x18000588a  mov     rbx, rcx
0x18000588d  movsxd  rdi, edx
0x180005890  mov     rcx, [rcx+2B18h]; void *
0x180005897  mov     rax, r8
0x18000589a  test    rcx, rcx
0x18000589d  jz      short loc_1800058D1
0x18000589f  mov     r8, rdi; Size
0x1800058a2  mov     rdx, rax; Src
0x1800058a5  call    memcpy_0
0x1800058aa  cmp     dword ptr [rbx+2ED4h], 0
0x1800058b1  jz      short loc_1800058D1
0x1800058b3  cmp     dword ptr [rbx+2EDCh], 8000h
0x1800058bd  jnb     short loc_1800058D1
0x1800058bf  mov     rdx, [rbx+2B18h]
0x1800058c6  mov     r8d, edi
0x1800058c9  mov     rcx, rbx
0x1800058cc  call    decoder_translate_e8
0x1800058d1  mov     rbx, [rsp+28h+arg_0]
0x1800058d6  add     rsp, 20h
0x1800058da  pop     rdi
0x1800058db  retn
```
