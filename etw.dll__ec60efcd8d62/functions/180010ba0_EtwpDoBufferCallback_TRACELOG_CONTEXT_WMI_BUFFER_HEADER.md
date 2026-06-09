# EtwpDoBufferCallback(_TRACELOG_CONTEXT *,_WMI_BUFFER_HEADER *)

- ea: `0x180010ba0`
- end: `0x180010bf8`
- name: `?EtwpDoBufferCallback@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_WMI_BUFFER_HEADER@@@Z`
- size: `88`
- prototype: `unsigned int __fastcall(struct _TRACELOG_CONTEXT *, struct _WMI_BUFFER_HEADER *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f384`
- `0x1800108d0`
- `0x180014b10`

## callees

- `0x180010ba0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall EtwpDoBufferCallback(struct _TRACELOG_CONTEXT *a1, struct _WMI_BUFFER_HEADER *a2)
{
  *((_DWORD *)a1 + 49) = *((_DWORD *)a2 + 10);
  *((_DWORD *)a1 + 123) = *((_DWORD *)a2 + 12);
  ++*((_DWORD *)a1 + 26);
  *((_QWORD *)a1 + 23) = a2;
  *((_DWORD *)a1 + 48) = *((_DWORD *)a2 + 12);
  return (*((unsigned int (__fastcall **)(char *))a1 + 60))((char *)a1 + 80) == 0 ? 0x4C7 : 0;
}

```

## disassembly

```asm
0x180010ba0  mov     [rsp+arg_0], rcx
0x180010ba5  sub     rsp, 38h
0x180010ba9  lea     r8, [rcx+50h]
0x180010bad  mov     eax, [rdx+28h]
0x180010bb0  mov     [r8+74h], eax
0x180010bb4  mov     eax, [rdx+30h]
0x180010bb7  mov     [r8+19Ch], eax
0x180010bbe  inc     dword ptr [r8+18h]
0x180010bc2  mov     [r8+68h], rdx
0x180010bc6  mov     eax, [rdx+30h]
0x180010bc9  mov     [r8+70h], eax
0x180010bcd  mov     rcx, r8
0x180010bd0  mov     rax, [r8+190h]
0x180010bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bdc  mov     [rsp+38h+var_10], eax
0x180010be0  jmp     short loc_180010BE8
0x180010be2  xor     eax, eax
0x180010be4  mov     [rsp+38h+var_10], eax
0x180010be8  neg     eax
0x180010bea  sbb     eax, eax
0x180010bec  not     eax
0x180010bee  and     eax, 4C7h
0x180010bf3  add     rsp, 38h
0x180010bf7  retn
0x180015af3  push    rbp
0x180015af5  sub     rsp, 20h
0x180015af9  mov     rbp, rdx
0x180015afc  mov     rax, [rcx]
0x180015aff  mov     edx, [rax]
0x180015b01  mov     rax, [rbp+40h]
0x180015b05  mov     ecx, [rax+20h]
0x180015b08  shr     ecx, 1Ch
0x180015b0b  not     cl
0x180015b0d  and     cl, 1
0x180015b10  mov     [rbp+20h], cl
0x180015b13  mov     al, [rbp+20h]
0x180015b16  test    al, al
0x180015b18  jz      short loc_180015B2B
0x180015b1a  cmp     edx, 0C0000005h
0x180015b20  jnz     short loc_180015B2B
0x180015b22  mov     dword ptr [rbp+24h], 1
0x180015b29  jmp     short loc_180015B32
0x180015b2b  mov     dword ptr [rbp+24h], 0
0x180015b32  mov     eax, [rbp+24h]
0x180015b35  add     rsp, 20h
0x180015b39  pop     rbp
0x180015b3a  retn
```
