# ACWCUserStringLen(wchar_t *)

- ea: `0x140009008`
- end: `0x140009069`
- name: `?ACWCUserStringLen@@YAKPEA_W@Z`
- size: `97`
- prototype: `unsigned int __fastcall(wchar_t *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140004314`
- `0x1400058fc`
- `0x140007e3c`
- `0x1400085f4`
- `0x14000bb00`
- `0x14002186c`
- `0x140022b28`
- `0x1400242b4`

## callees

- `0x140009008`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140009025`
- `ntoskrnl!ProbeForRead` at `0x140009025`
- `ntoskrnl!ExRaiseStatus` at `0x140009049`
- `ntoskrnl!ExRaiseStatus` at `0x140009049`

## pseudocode

```c
__int64 __fastcall ACWCUserStringLen(wchar_t *a1)
{
  wchar_t *v1; // rdi
  unsigned int v2; // ebx

  v1 = a1;
  v2 = 0;
  ProbeForRead(a1, 2u, 1u);
  while ( *v1 )
  {
    ++v1;
    if ( ++v2 == -1 )
      ExRaiseStatus(-1073741675);
  }
  return v2;
}

```

## disassembly

```asm
0x140009008  mov     [rsp+arg_0], rbx
0x14000900d  mov     [rsp+arg_8], rsi
0x140009012  push    rdi
0x140009013  sub     rsp, 20h
0x140009017  xor     esi, esi
0x140009019  mov     rdi, rcx
0x14000901c  mov     ebx, esi
0x14000901e  lea     edx, [rsi+2]; Length
0x140009021  lea     r8d, [rsi+1]; Alignment
0x140009025  call    cs:__imp_ProbeForRead
0x14000902c  nop     dword ptr [rax+rax+00h]
0x140009031  movzx   eax, word ptr [rdi]
0x140009034  test    ax, ax
0x140009037  jz      short loc_140009056
0x140009039  add     rdi, 2
0x14000903d  inc     ebx
0x14000903f  cmp     ebx, 0FFFFFFFFh
0x140009042  jnz     short loc_140009031
0x140009044  mov     ecx, 0C0000095h; Status
0x140009049  call    cs:__imp_ExRaiseStatus
0x140009056  mov     rsi, [rsp+28h+arg_8]
0x14000905b  mov     eax, ebx
0x14000905d  mov     rbx, [rsp+28h+arg_0]
0x140009062  add     rsp, 20h
0x140009066  pop     rdi
0x140009067  retn
```
