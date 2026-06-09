# PAL_System_CondAlloc

- ea: `0x18001f03c`
- end: `0x18001f081`
- name: `PAL_System_CondAlloc`
- size: `69`
- prototype: `__int64 __fastcall(BOOL bManualReset)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180025520`
- `0x1800259b4`
- `0x180029af0`

## callees

- `0x18001f03c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f064`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f064`

## pseudocode

```c
__int64 __fastcall PAL_System_CondAlloc(BOOL bManualReset, _QWORD *a2)
{
  unsigned int v3; // ebx
  HANDLE EventW; // rax

  if ( a2 )
  {
    v3 = -2147467259;
    EventW = CreateEventW(0, bManualReset, 0, 0);
    if ( EventW )
    {
      *a2 = EventW;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18001f03c  mov     [rsp+arg_0], rbx
0x18001f041  push    rdi
0x18001f042  sub     rsp, 20h
0x18001f046  mov     rdi, rdx
0x18001f049  test    rdx, rdx
0x18001f04c  jnz     short loc_18001F055
0x18001f04e  mov     ebx, 80070057h
0x18001f053  jmp     short loc_18001F074
0x18001f055  mov     edx, ecx; bManualReset
0x18001f057  xor     r9d, r9d; lpName
0x18001f05a  xor     ecx, ecx; lpEventAttributes
0x18001f05c  xor     r8d, r8d; bInitialState
0x18001f05f  mov     ebx, 80004005h
0x18001f064  call    cs:__imp_CreateEventW
0x18001f06a  test    rax, rax
0x18001f06d  jz      short loc_18001F074
0x18001f06f  mov     [rdi], rax
0x18001f072  xor     ebx, ebx
0x18001f074  mov     eax, ebx
0x18001f076  mov     rbx, [rsp+28h+arg_0]
0x18001f07b  add     rsp, 20h
0x18001f07f  pop     rdi
0x18001f080  retn
```
