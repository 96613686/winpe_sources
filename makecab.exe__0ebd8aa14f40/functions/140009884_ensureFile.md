# ensureFile

- ea: `0x140009884`
- end: `0x14000992f`
- name: `ensureFile`
- size: `171`
- prototype: `__int64 __fastcall(char *FileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140007934`

## callees

- `0x140008620`
- `0x14000907c`
- `0x140009884`

## import_xrefs

- `msvcrt!_unlink` at `0x1400098f2`
- `msvcrt!_unlink` at `0x1400098f2`
- `msvcrt!_errno` at `0x1400098c1`
- `msvcrt!_errno` at `0x1400098c1`
- `msvcrt!_open` at `0x1400098b6`
- `msvcrt!_open` at `0x1400098b6`
- `msvcrt!_close` at `0x1400098e9`
- `msvcrt!_close` at `0x1400098e9`

## string_xrefs

- `0x140009911`: `Cannot create %1: %2`

## pseudocode

```c
__int64 __fastcall ensureFile(char *FileName, const char *a2, __int64 a3)
{
  int v6; // eax

  if ( !(unsigned int)ensureDirectory(FileName, 1, a3) )
    goto LABEL_6;
  v6 = _open(FileName, 258, 384);
  if ( v6 != -1 )
  {
    _close(v6);
    _unlink(FileName);
    return 1;
  }
  if ( *_errno() == 24 )
    ErrSet(a3, "No more file handles: %1", "%s", FileName);
  else
LABEL_6:
    ErrSet(a3, "Cannot create %1: %2", "%s%s", a2, FileName);
  return 0;
}

```

## disassembly

```asm
0x140009884  mov     [rsp+arg_0], rbx
0x140009889  mov     [rsp+arg_8], rsi
0x14000988e  push    rdi
0x14000988f  sub     rsp, 30h
0x140009893  mov     rsi, rdx
0x140009896  mov     rdi, r8
0x140009899  mov     edx, 1
0x14000989e  mov     rbx, rcx
0x1400098a1  call    ensureDirectory
0x1400098a6  test    eax, eax
0x1400098a8  jz      short loc_1400098FF
0x1400098aa  mov     edx, 102h; OpenFlag
0x1400098af  mov     rcx, rbx; FileName
0x1400098b2  lea     r8d, [rdx+7Eh]
0x1400098b6  call    cs:__imp__open
0x1400098bc  cmp     eax, 0FFFFFFFFh
0x1400098bf  jnz     short loc_1400098E7
0x1400098c1  call    cs:__imp__errno
0x1400098c7  cmp     dword ptr [rax], 18h
0x1400098ca  jnz     short loc_1400098FF
0x1400098cc  mov     r9, rbx
0x1400098cf  lea     r8, aS_4; "%s"
0x1400098d6  lea     rdx, aNoMoreFileHand; "No more file handles: %1"
0x1400098dd  mov     rcx, rdi
0x1400098e0  call    ErrSet
0x1400098e5  jmp     short loc_14000991D
0x1400098e7  mov     ecx, eax; FileHandle
0x1400098e9  call    cs:__imp__close
0x1400098ef  mov     rcx, rbx; FileName
0x1400098f2  call    cs:__imp__unlink
0x1400098f8  mov     eax, 1
0x1400098fd  jmp     short loc_14000991F
0x1400098ff  mov     r9, rsi
0x140009902  mov     [rsp+38h+var_18], rbx
0x140009907  lea     r8, aSS_1; "%s%s"
0x14000990e  mov     rcx, rdi
0x140009911  lea     rdx, aCannotCreate12; "Cannot create %1: %2"
0x140009918  call    ErrSet
0x14000991d  xor     eax, eax
0x14000991f  mov     rbx, [rsp+38h+arg_0]
0x140009924  mov     rsi, [rsp+38h+arg_8]
0x140009929  add     rsp, 30h
0x14000992d  pop     rdi
0x14000992e  retn
```
