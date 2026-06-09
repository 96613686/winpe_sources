# DllInitClasses(int)

- ea: `0x18000318c`
- end: `0x1800031d9`
- name: `?DllInitClasses@@YAXH@Z`
- size: `77`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800032d8`

## callees

- `0x18000318c`
- `0x18001f010`

## pseudocode

```c
void __fastcall DllInitClasses(unsigned int a1)
{
  __int64 i; // rbx
  void (__fastcall *v3)(_QWORD, _QWORD); // rax

  for ( i = 0; i != 5; ++i )
  {
    v3 = (void (__fastcall *)(_QWORD, _QWORD))*(&g_Templates + 5 * i + 3);
    if ( v3 )
      v3(a1, *(&g_Templates + 5 * i + 1));
  }
}

```

## disassembly

```asm
0x18000318c  mov     [rsp+arg_0], rbx
0x180003191  mov     [rsp+arg_8], rsi
0x180003196  push    rdi
0x180003197  sub     rsp, 20h
0x18000319b  mov     edi, ecx
0x18000319d  lea     rsi, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x1800031a4  xor     ebx, ebx
0x1800031a6  lea     rdx, [rbx+rbx*4]
0x1800031aa  mov     rax, [rsi+rdx*8+18h]
0x1800031af  test    rax, rax
0x1800031b2  jz      short loc_1800031C0
0x1800031b4  mov     rdx, [rsi+rdx*8+8]
0x1800031b9  mov     ecx, edi
0x1800031bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c0  inc     rbx
0x1800031c3  cmp     rbx, 5
0x1800031c7  jnz     short loc_1800031A6
0x1800031c9  mov     rbx, [rsp+28h+arg_0]
0x1800031ce  mov     rsi, [rsp+28h+arg_8]
0x1800031d3  add     rsp, 20h
0x1800031d7  pop     rdi
0x1800031d8  retn
```
