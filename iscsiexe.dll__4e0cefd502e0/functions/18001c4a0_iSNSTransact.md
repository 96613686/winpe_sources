# iSNSTransact

- ea: `0x18001c4a0`
- end: `0x18001c4f1`
- name: `iSNSTransact`
- size: `81`
- prototype: `__int64 __fastcall(SOCKET s, const char *, int, __int64, _DWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c124`
- `0x18000c474`
- `0x18000ce28`
- `0x18000d6f0`

## callees

- `0x18001c138`
- `0x18001c4a0`

## import_xrefs

- `WS2_32!__imp_send` at `0x18001c4bb`
- `WS2_32!__imp_send` at `0x18001c4bb`

## pseudocode

```c
__int64 __fastcall iSNSTransact(SOCKET s, const char *a2, int a3, __int64 a4, _DWORD *a5)
{
  int v8; // eax
  __int64 v9; // rdx

  v8 = send(s, a2, a3, 0);
  if ( v8 == -1 || v8 != a3 )
    return 1;
  else
    return iSNSReadMessage(s, v9, a4, a5);
}

```

## disassembly

```asm
0x18001c4a0  mov     [rsp+arg_0], rbx
0x18001c4a5  mov     [rsp+arg_8], rsi
0x18001c4aa  push    rdi
0x18001c4ab  sub     rsp, 20h
0x18001c4af  mov     rsi, r9
0x18001c4b2  mov     ebx, r8d
0x18001c4b5  xor     r9d, r9d; flags
0x18001c4b8  mov     rdi, rcx
0x18001c4bb  call    cs:__imp_send
0x18001c4c1  cmp     eax, 0FFFFFFFFh
0x18001c4c4  jz      short loc_18001C4DC
0x18001c4c6  cmp     eax, ebx
0x18001c4c8  jnz     short loc_18001C4DC
0x18001c4ca  mov     r9, [rsp+28h+arg_20]
0x18001c4cf  mov     r8, rsi
0x18001c4d2  mov     rcx, rdi; s
0x18001c4d5  call    iSNSReadMessage
0x18001c4da  jmp     short loc_18001C4E1
0x18001c4dc  mov     eax, 1
0x18001c4e1  mov     rbx, [rsp+28h+arg_0]
0x18001c4e6  mov     rsi, [rsp+28h+arg_8]
0x18001c4eb  add     rsp, 20h
0x18001c4ef  pop     rdi
0x18001c4f0  retn
```
