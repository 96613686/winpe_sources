# PROTOCOL::SendCompletion(long,ulong)

- ea: `0x180003bc0`
- end: `0x180003bff`
- name: `?SendCompletion@PROTOCOL@@UEAAXJK@Z`
- size: `63`
- prototype: `void __fastcall(PROTOCOL *__hidden this, int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003414`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003bd7`

## pseudocode

```c
void __fastcall PROTOCOL::SendCompletion(PROTOCOL *this, signed int a2, int a3)
{
  *((_DWORD *)this + 48) = GetTickCount();
  PROTOCOL::DispatchSendCompletion(this, a2, a3);
}

```

## disassembly

```asm
0x180003bc0  mov     [rsp+arg_0], rbx
0x180003bc5  mov     [rsp+arg_8], rsi
0x180003bca  push    rdi
0x180003bcb  sub     rsp, 20h
0x180003bcf  mov     ebx, r8d
0x180003bd2  mov     edi, edx
0x180003bd4  mov     rsi, rcx
0x180003bd7  call    cs:__imp_GetTickCount
0x180003bdd  mov     r8d, ebx; unsigned int
0x180003be0  mov     edx, edi; int
0x180003be2  mov     rcx, rsi; this
0x180003be5  mov     [rsi+0C0h], eax
0x180003beb  mov     rbx, [rsp+28h+arg_0]
0x180003bf0  mov     rsi, [rsp+28h+arg_8]
0x180003bf5  add     rsp, 20h
0x180003bf9  pop     rdi
0x180003bfa  jmp     ?DispatchSendCompletion@PROTOCOL@@AEAAXJK@Z; PROTOCOL::DispatchSendCompletion(long,ulong)
```
