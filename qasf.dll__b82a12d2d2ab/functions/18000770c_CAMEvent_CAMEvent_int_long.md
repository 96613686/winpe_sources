# CAMEvent::CAMEvent(int,long *)

- ea: `0x18000770c`
- end: `0x18000774f`
- name: `??0CAMEvent@@QEAA@HPEAJ@Z`
- size: `67`
- prototype: `CAMEvent *__fastcall(CAMEvent *__hidden this, int, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bb0`
- `0x18001bf60`

## callees

- `0x18000770c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180007724`
- `KERNEL32!CreateEventW` at `0x180007724`

## pseudocode

```c
CAMEvent *__fastcall CAMEvent::CAMEvent(CAMEvent *this, BOOL a2, int *a3)
{
  HANDLE EventW; // rax

  EventW = CreateEventW(0, a2, 0, 0);
  *(_QWORD *)this = EventW;
  if ( !EventW && a3 && *a3 >= 0 )
    *a3 = -2147024882;
  return this;
}

```

## disassembly

```asm
0x18000770c  mov     [rsp+arg_0], rbx
0x180007711  push    rdi
0x180007712  sub     rsp, 20h
0x180007716  mov     rbx, r8
0x180007719  mov     rdi, rcx
0x18000771c  xor     r8d, r8d; bInitialState
0x18000771f  xor     ecx, ecx; lpEventAttributes
0x180007721  xor     r9d, r9d; lpName
0x180007724  call    cs:__imp_CreateEventW
0x18000772a  mov     [rdi], rax
0x18000772d  test    rax, rax
0x180007730  jnz     short loc_180007741
0x180007732  test    rbx, rbx
0x180007735  jz      short loc_180007741
0x180007737  cmp     [rbx], eax
0x180007739  jl      short loc_180007741
0x18000773b  mov     dword ptr [rbx], 8007000Eh
0x180007741  mov     rbx, [rsp+28h+arg_0]
0x180007746  mov     rax, rdi
0x180007749  add     rsp, 20h
0x18000774d  pop     rdi
0x18000774e  retn
```
