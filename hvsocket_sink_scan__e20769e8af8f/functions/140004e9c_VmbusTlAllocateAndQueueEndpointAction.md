# VmbusTlAllocateAndQueueEndpointAction

- ea: `0x140004e9c`
- end: `0x140004f26`
- name: `VmbusTlAllocateAndQueueEndpointAction`
- size: `138`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140002a40`
- `0x140003fe0`
- `0x1400049a0`
- `0x14000a7c0`
- `0x14000b520`

## callees

- `0x140004e9c`
- `0x1400058d0`
- `0x14000975c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140004ec1`
- `ntoskrnl!ExAllocatePool2` at `0x140004ec1`

## pseudocode

```c
__int64 __fastcall VmbusTlAllocateAndQueueEndpointAction(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 Pool2; // rax

  Pool2 = ExAllocatePool2(64, 56, 1768975958);
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 48) = 1;
    VmbusTlQueueEndpointAction(a1, Pool2, a2, a3);
    return 259;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError((const int *)"VmbusTlAllocateAndQueueEndpointAction", 72, 3221225495LL, a1);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x140004e9c  mov     [rsp+arg_0], rbx
0x140004ea1  mov     [rsp+arg_8], rsi
0x140004ea6  push    rdi
0x140004ea7  sub     rsp, 20h
0x140004eab  mov     esi, edx
0x140004ead  mov     rdi, r8
0x140004eb0  mov     edx, 38h ; '8'
0x140004eb5  mov     rbx, rcx
0x140004eb8  mov     r8d, 69706E56h
0x140004ebe  lea     ecx, [rdx+8]
0x140004ec1  call    cs:__imp_ExAllocatePool2
0x140004ec8  nop     dword ptr [rax+rax+00h]
0x140004ecd  test    rax, rax
0x140004ed0  jnz     short loc_140004EFB
0x140004ed2  mov     edx, cs:dword_140013058
0x140004ed8  mov     edi, 0C0000017h
0x140004edd  cmp     edx, 2
0x140004ee0  jbe     short loc_140004EF7
0x140004ee2  mov     r9, rbx
0x140004ee5  lea     edx, [rax+48h]
0x140004ee8  mov     r8d, edi
0x140004eeb  lea     rcx, aVmbustlallocat; "VmbusTlAllocateAndQueueEndpointAction"
0x140004ef2  call    HvsocketTraceEndpointError
0x140004ef7  mov     eax, edi
0x140004ef9  jmp     short loc_140004F15
0x140004efb  mov     r9, rdi
0x140004efe  mov     byte ptr [rax+30h], 1
0x140004f02  mov     r8d, esi
0x140004f05  mov     rdx, rax
0x140004f08  mov     rcx, rbx
0x140004f0b  call    VmbusTlQueueEndpointAction
0x140004f10  mov     eax, 103h
0x140004f15  mov     rbx, [rsp+28h+arg_0]
0x140004f1a  mov     rsi, [rsp+28h+arg_8]
0x140004f1f  add     rsp, 20h
0x140004f23  pop     rdi
0x140004f24  retn
```
