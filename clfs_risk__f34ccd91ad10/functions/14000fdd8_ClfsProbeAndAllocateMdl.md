# ClfsProbeAndAllocateMdl

- ea: `0x14000fdd8`
- end: `0x14000fe6c`
- name: `ClfsProbeAndAllocateMdl`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400420fc`
- `0x1400434dc`

## callees

- `0x14000fdd8`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14000fe3b`
- `ntoskrnl!IoAllocateMdl` at `0x14000fe3b`
- `ntoskrnl!ProbeForWrite` at `0x14000fe06`
- `ntoskrnl!ProbeForWrite` at `0x14000fe06`

## pseudocode

```c
__int64 __fastcall ClfsProbeAndAllocateMdl(
        char a1,
        volatile void *a2,
        ULONG a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PMDL *a7)
{
  PMDL Mdl; // rax

  if ( a1 == 1 )
    ProbeForWrite(a2, a3, 8u);
  Mdl = IoAllocateMdl((PVOID)a2, a3, 0, 1u, 0);
  *a7 = Mdl;
  return Mdl == 0 ? 0xC000009A : 0;
}

```

## disassembly

```asm
0x14000fdd8  mov     rax, rsp
0x14000fddb  mov     [rax+8], rbx
0x14000fddf  mov     [rax+20h], rsi
0x14000fde3  mov     [rax+18h], r8d
0x14000fde7  mov     [rax+10h], rdx
0x14000fdeb  push    rdi
0x14000fdec  sub     rsp, 30h
0x14000fdf0  mov     edi, r8d
0x14000fdf3  mov     rsi, rdx
0x14000fdf6  cmp     cl, 1
0x14000fdf9  jnz     short loc_14000FE27
0x14000fdfb  xor     ebx, ebx
0x14000fdfd  mov     edx, edi; Length
0x14000fdff  lea     r8d, [rbx+8]; Alignment
0x14000fe03  mov     rcx, rsi; Address
0x14000fe06  call    cs:__imp_ProbeForWrite
0x14000fe0d  nop     dword ptr [rax+rax+00h]
0x14000fe12  jmp     short loc_14000FE1F
0x14000fe14  mov     ebx, eax
0x14000fe16  mov     edi, [rsp+38h+arg_10]
0x14000fe1a  mov     rsi, [rsp+38h+arg_8]
0x14000fe1f  test    ebx, ebx
0x14000fe21  jns     short loc_14000FE27
0x14000fe23  mov     eax, ebx
0x14000fe25  jmp     short loc_14000FE5B
0x14000fe27  mov     [rsp+38h+Irp], 0; Irp
0x14000fe30  mov     r9b, 1; ChargeQuota
0x14000fe33  xor     r8d, r8d; SecondaryBuffer
0x14000fe36  mov     edx, edi; Length
0x14000fe38  mov     rcx, rsi; VirtualAddress
0x14000fe3b  call    cs:__imp_IoAllocateMdl
0x14000fe42  nop     dword ptr [rax+rax+00h]
0x14000fe47  mov     rcx, [rsp+38h+arg_30]
0x14000fe4c  mov     [rcx], rax
0x14000fe4f  neg     rax
0x14000fe52  sbb     eax, eax
0x14000fe54  not     eax
0x14000fe56  and     eax, 0C000009Ah
0x14000fe5b  mov     rbx, [rsp+38h+arg_0]
0x14000fe60  mov     rsi, [rsp+38h+arg_18]
0x14000fe65  add     rsp, 30h
0x14000fe69  pop     rdi
0x14000fe6a  retn
```
