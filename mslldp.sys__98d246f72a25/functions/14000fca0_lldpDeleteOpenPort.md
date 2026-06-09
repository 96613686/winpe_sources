# lldpDeleteOpenPort

- ea: `0x14000fca0`
- end: `0x14000fce9`
- name: `lldpDeleteOpenPort`
- size: `73`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400063bc`

## callees

- `0x1400061d4`
- `0x140010530`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fcd6`

## pseudocode

```c
void __fastcall lldpDeleteOpenPort(_QWORD *P)
{
  __int64 v2; // rcx

  lldpDereferencePort(P[3]);
  v2 = P[2];
  P[3] = 0;
  lldpDereferenceClient(v2);
  P[2] = 0;
  *(_BYTE *)P = 0;
  ExFreePoolWithTag(P, 0x50444C4Cu);
}

```

## disassembly

```asm
0x14000fca0  push    rbx
0x14000fca2  sub     rsp, 20h
0x14000fca6  mov     rbx, rcx
0x14000fca9  mov     rcx, [rcx+18h]
0x14000fcad  call    lldpDereferencePort
0x14000fcb2  mov     rcx, [rbx+10h]
0x14000fcb6  mov     qword ptr [rbx+18h], 0
0x14000fcbe  call    lldpDereferenceClient
0x14000fcc3  mov     edx, 50444C4Ch; Tag
0x14000fcc8  mov     qword ptr [rbx+10h], 0
0x14000fcd0  mov     rcx, rbx; P
0x14000fcd3  mov     byte ptr [rbx], 0
0x14000fcd6  call    cs:__imp_ExFreePoolWithTag
0x14000fcdd  nop     dword ptr [rax+rax+00h]
0x14000fce2  add     rsp, 20h
0x14000fce6  pop     rbx
0x14000fce7  retn
```
