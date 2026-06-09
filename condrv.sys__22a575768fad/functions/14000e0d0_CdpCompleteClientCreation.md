# CdpCompleteClientCreation

- ea: `0x14000e0d0`
- end: `0x14000e128`
- name: `CdpCompleteClientCreation`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000afd0`
- `0x14000e0d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e0f6`

## pseudocode

```c
__int64 __fastcall CdpCompleteClientCreation(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v4; // rcx

  v4 = (_QWORD *)*a3;
  if ( *(int *)(a2 + 48) < 0 )
    CdpFreeClient(v4);
  else
    v4[2] = *(_QWORD *)(a2 + 56);
  ExFreePoolWithTag(a3, 0);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x14000e0d0  mov     [rsp+arg_0], rbx
0x14000e0d5  push    rdi
0x14000e0d6  sub     rsp, 20h
0x14000e0da  cmp     dword ptr [rdx+30h], 0
0x14000e0de  mov     rdi, r8
0x14000e0e1  mov     rcx, [r8]; P
0x14000e0e4  mov     rbx, rdx
0x14000e0e7  jl      short loc_14000E121
0x14000e0e9  mov     rax, [rdx+38h]
0x14000e0ed  mov     [rcx+10h], rax
0x14000e0f1  xor     edx, edx; Tag
0x14000e0f3  mov     rcx, rdi; P
0x14000e0f6  call    cs:__imp_ExFreePoolWithTag
0x14000e0fd  nop     dword ptr [rax+rax+00h]
0x14000e102  cmp     byte ptr [rbx+41h], 0
0x14000e106  jz      short loc_14000E113
0x14000e108  mov     rax, [rbx+0B8h]
0x14000e10f  or      byte ptr [rax+3], 1
0x14000e113  mov     rbx, [rsp+28h+arg_0]
0x14000e118  xor     eax, eax
0x14000e11a  add     rsp, 20h
0x14000e11e  pop     rdi
0x14000e11f  retn
0x14000e121  call    CdpFreeClient
0x14000e126  jmp     short loc_14000E0F1
```
