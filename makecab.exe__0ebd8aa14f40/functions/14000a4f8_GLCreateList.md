# GLCreateList

- ea: `0x14000a4f8`
- end: `0x14000a55b`
- name: `GLCreateList`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400034e4`
- `0x140003d28`
- `0x140007120`
- `0x14000a3f8`

## callees

- `0x140008620`
- `0x14000a4f8`

## import_xrefs

- `msvcrt!malloc` at `0x14000a512`
- `msvcrt!malloc` at `0x14000a512`

## pseudocode

```c
_QWORD *__fastcall GLCreateList(__int64 a1, __int64 a2, const char *a3, __int64 a4)
{
  _QWORD *result; // rax

  result = malloc(0x30u);
  if ( result )
  {
    *result = 0;
    result[1] = 0;
    result[2] = a1;
    result[3] = a2;
    *((_DWORD *)result + 8) = 0;
    result[5] = 0;
  }
  else
  {
    ErrSet(a4, "Out of memory creating %1 list", "%s", a3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a4f8  push    rbx
0x14000a4fa  push    rbp
0x14000a4fb  push    rsi
0x14000a4fc  push    rdi
0x14000a4fd  sub     rsp, 28h
0x14000a501  mov     rdi, rcx
0x14000a504  mov     rsi, r9
0x14000a507  mov     ecx, 30h ; '0'; Size
0x14000a50c  mov     rbp, r8
0x14000a50f  mov     rbx, rdx
0x14000a512  call    cs:__imp_malloc
0x14000a518  xor     ecx, ecx
0x14000a51a  test    rax, rax
0x14000a51d  jnz     short loc_14000A53C
0x14000a51f  mov     r9, rbp
0x14000a522  lea     r8, aS_4; "%s"
0x14000a529  lea     rdx, aOutOfMemoryCre; "Out of memory creating %1 list"
0x14000a530  mov     rcx, rsi
0x14000a533  call    ErrSet
0x14000a538  xor     eax, eax
0x14000a53a  jmp     short loc_14000A552
0x14000a53c  mov     [rax], rcx
0x14000a53f  mov     [rax+8], rcx
0x14000a543  mov     [rax+10h], rdi
0x14000a547  mov     [rax+18h], rbx
0x14000a54b  mov     [rax+20h], ecx
0x14000a54e  mov     [rax+28h], rcx
0x14000a552  add     rsp, 28h
0x14000a556  pop     rdi
0x14000a557  pop     rsi
0x14000a558  pop     rbp
0x14000a559  pop     rbx
0x14000a55a  retn
```
