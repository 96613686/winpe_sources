# GetDeviceInfo

- ea: `0x180003088`
- end: `0x1800030e9`
- name: `GetDeviceInfo`
- size: `97`
- prototype: `__int64 __fastcall(char *String1)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030f0`
- `0x18000dc2c`
- `0x18000f670`
- `0x1800118f0`
- `0x180014a20`
- `0x180014ad0`

## callees

- `0x180003088`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800030c9`
- `msvcrt!_stricmp` at `0x1800030c9`

## pseudocode

```c
char *__fastcall GetDeviceInfo(char *String1, int a2)
{
  char *v2; // rbx

  v2 = (char *)g_pDeviceInfoList;
  if ( a2 )
  {
    while ( v2 && _stricmp(String1, v2 + 133) )
      v2 = *(char **)v2;
  }
  else
  {
    while ( v2 && (*(_QWORD *)String1 != *(_QWORD *)(v2 + 100) || *((_QWORD *)String1 + 1) != *(_QWORD *)(v2 + 108)) )
      v2 = *(char **)v2;
  }
  return v2;
}

```

## disassembly

```asm
0x180003088  mov     [rsp+arg_0], rbx
0x18000308d  push    rdi
0x18000308e  sub     rsp, 20h
0x180003092  mov     rbx, cs:g_pDeviceInfoList
0x180003099  mov     rdi, rcx
0x18000309c  test    edx, edx
0x18000309e  jnz     short loc_1800030D6
0x1800030a0  jmp     short loc_1800030B8
0x1800030a2  mov     rax, [rcx]
0x1800030a5  cmp     rax, [rbx+64h]
0x1800030a9  jnz     short loc_1800030B5
0x1800030ab  mov     rax, [rcx+8]
0x1800030af  cmp     rax, [rbx+6Ch]
0x1800030b3  jz      short loc_1800030DB
0x1800030b5  mov     rbx, [rbx]
0x1800030b8  test    rbx, rbx
0x1800030bb  jnz     short loc_1800030A2
0x1800030bd  jmp     short loc_1800030DB
0x1800030bf  lea     rdx, [rbx+85h]; String2
0x1800030c6  mov     rcx, rdi; String1
0x1800030c9  call    cs:__imp__stricmp
0x1800030cf  test    eax, eax
0x1800030d1  jz      short loc_1800030DB
0x1800030d3  mov     rbx, [rbx]
0x1800030d6  test    rbx, rbx
0x1800030d9  jnz     short loc_1800030BF
0x1800030db  mov     rax, rbx
0x1800030de  mov     rbx, [rsp+28h+arg_0]
0x1800030e3  add     rsp, 20h
0x1800030e7  pop     rdi
0x1800030e8  retn
```
