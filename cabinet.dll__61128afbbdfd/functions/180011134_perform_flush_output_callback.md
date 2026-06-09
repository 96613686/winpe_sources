# perform_flush_output_callback

- ea: `0x180011134`
- end: `0x1800111b7`
- name: `perform_flush_output_callback`
- size: `131`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800019d0`
- `0x18000f50c`
- `0x18000fa50`
- `0x180011068`

## callees

- `0x18000ea34`
- `0x180011134`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall perform_flush_output_callback(__int64 a1)
{
  char v2; // al
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 2200) )
  {
    v2 = *(_BYTE *)(a1 + 44);
    if ( v2 < 32 )
      output_bits(a1, (unsigned __int8)(v2 - 16), 0);
    if ( *(_DWORD *)(a1 + 2184) - *(_DWORD *)(a1 + 2176) > 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 17328))(
        *(_QWORD *)(a1 + 17304),
        *(_QWORD *)(a1 + 2176),
        (unsigned int)(*(_DWORD *)(a1 + 2184) - *(_DWORD *)(a1 + 2176)),
        *(unsigned int *)(a1 + 2200));
  }
  result = *(_QWORD *)(a1 + 2176);
  *(_QWORD *)(a1 + 2184) = result;
  *(_DWORD *)(a1 + 2200) = 0;
  *(_BYTE *)(a1 + 44) = 32;
  *(_DWORD *)(a1 + 40) = 0;
  return result;
}

```

## disassembly

```asm
0x180011134  push    rbx
0x180011136  sub     rsp, 30h
0x18001113a  cmp     dword ptr [rcx+898h], 0
0x180011141  mov     rbx, rcx
0x180011144  jbe     short loc_18001118E
0x180011146  mov     al, [rcx+2Ch]
0x180011149  cmp     al, 20h ; ' '
0x18001114b  jge     short loc_18001115A
0x18001114d  sub     al, 10h
0x18001114f  xor     r8d, r8d
0x180011152  movzx   edx, al
0x180011155  call    output_bits
0x18001115a  mov     eax, [rbx+888h]
0x180011160  sub     eax, [rbx+880h]
0x180011166  test    eax, eax
0x180011168  jle     short loc_18001118E
0x18001116a  mov     r9d, [rbx+898h]
0x180011171  mov     r8d, eax
0x180011174  mov     rax, [rbx+43B0h]
0x18001117b  mov     rdx, [rbx+880h]
0x180011182  mov     rcx, [rbx+4398h]
0x180011189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001118e  mov     rax, [rbx+880h]
0x180011195  mov     [rbx+888h], rax
0x18001119c  mov     dword ptr [rbx+898h], 0
0x1800111a6  mov     byte ptr [rbx+2Ch], 20h ; ' '
0x1800111aa  mov     dword ptr [rbx+28h], 0
0x1800111b1  add     rsp, 30h
0x1800111b5  pop     rbx
0x1800111b6  retn
```
