# CdOpenExistingFcb

- ea: `0x14000e4a0`
- end: `0x14000e53d`
- name: `CdOpenExistingFcb`
- size: `157`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, char, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000c8b4`

## callees

- `0x14000d400`
- `0x14000e4a0`

## pseudocode

```c
NTSTATUS __fastcall CdOpenExistingFcb(PIRP *Context, __int64 a2, __int64 *a3, int a4, char a5, __int64 a6)
{
  ACCESS_MASK DesiredAccess; // edi
  int v9; // ecx

  DesiredAccess = *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL);
  if ( (((a4 != 2 ? 0x116 : 0) | 0x50040) & DesiredAccess) != 0 )
    return -1073741790;
  if ( a6 )
  {
    v9 = (a5 != 0 ? 4 : 0) | *(_DWORD *)(a6 + 4) & 8;
    if ( (*(_DWORD *)(a6 + 4) & 3) != 0 )
      v9 |= 2u;
  }
  else
  {
    v9 = a5 != 0 ? 4 : 0;
  }
  return CdCompleteFcbOpen(Context, a2, *(_QWORD *)(*a3 + 120), a3, a4, v9, DesiredAccess);
}

```

## disassembly

```asm
0x14000e4a0  mov     [rsp+arg_0], rbx
0x14000e4a5  mov     [rsp+arg_8], rsi
0x14000e4aa  push    rdi
0x14000e4ab  sub     rsp, 40h
0x14000e4af  mov     rax, [rdx+8]
0x14000e4b3  mov     r11, r8
0x14000e4b6  mov     rbx, rdx
0x14000e4b9  mov     rsi, rcx
0x14000e4bc  mov     edi, [rax+10h]
0x14000e4bf  lea     eax, [r9-2]
0x14000e4c3  neg     eax
0x14000e4c5  sbb     r10d, r10d
0x14000e4c8  and     r10d, 116h
0x14000e4cf  or      r10d, 50040h
0x14000e4d6  test    edi, r10d
0x14000e4d9  jz      short loc_14000E4E2
0x14000e4db  mov     eax, 0C0000022h
0x14000e4e0  jmp     short loc_14000E52C
0x14000e4e2  neg     [rsp+48h+arg_20]
0x14000e4e6  mov     rax, [rsp+48h+arg_28]
0x14000e4eb  sbb     edx, edx
0x14000e4ed  and     edx, 4
0x14000e4f0  test    rax, rax
0x14000e4f3  jz      short loc_14000E508
0x14000e4f5  mov     eax, [rax+4]
0x14000e4f8  mov     ecx, eax
0x14000e4fa  and     ecx, 8
0x14000e4fd  or      ecx, edx
0x14000e4ff  test    al, 3
0x14000e501  jz      short loc_14000E50A
0x14000e503  or      ecx, 2
0x14000e506  jmp     short loc_14000E50A
0x14000e508  mov     ecx, edx
0x14000e50a  mov     r8, [r8]
0x14000e50d  mov     rdx, rbx
0x14000e510  mov     [rsp+48h+DesiredAccess], edi; DesiredAccess
0x14000e514  mov     [rsp+48h+var_20], ecx; int
0x14000e518  mov     rcx, rsi; Context
0x14000e51b  mov     [rsp+48h+var_28], r9d; int
0x14000e520  mov     r9, r11
0x14000e523  mov     r8, [r8+78h]
0x14000e527  call    CdCompleteFcbOpen
0x14000e52c  mov     rbx, [rsp+48h+arg_0]
0x14000e531  mov     rsi, [rsp+48h+arg_8]
0x14000e536  add     rsp, 40h
0x14000e53a  pop     rdi
0x14000e53b  retn
```
