# xdr_opaque

- ea: `0x14000b618`
- end: `0x14000b6bf`
- name: `xdr_opaque`
- size: `167`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b4d8`
- `0x14000b6c8`
- `0x14000ba50`

## callees

- `0x14000b618`
- `0x140019010`

## pseudocode

```c
__int64 __fastcall xdr_opaque(__int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx

  if ( !a3 )
    return 1;
  v4 = 4 - (a3 & 3);
  if ( (a3 & 3) == 0 )
    v4 = a3 & 3;
  if ( *(_DWORD *)a1 != 1 )
  {
    if ( *(_DWORD *)a1 )
      return *(_DWORD *)a1 == 2;
    if ( (*(unsigned int (**)(void))(*(_QWORD *)(a1 + 8) + 24LL))() )
    {
      if ( v4 )
        return (*(__int64 (__fastcall **)(__int64, char *, _QWORD))(*(_QWORD *)(a1 + 8) + 24LL))(a1, byte_140021B98, v4);
      return 1;
    }
    return 0;
  }
  if ( !(*(unsigned int (**)(void))(*(_QWORD *)(a1 + 8) + 16LL))() )
    return 0;
  if ( !v4 )
    return 1;
  return (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)(a1 + 8) + 16LL))(a1, qword_140021B20, v4);
}

```

## disassembly

```asm
0x14000b618  mov     [rsp+arg_0], rbx
0x14000b61d  push    rdi
0x14000b61e  sub     rsp, 20h
0x14000b622  mov     rdi, rcx
0x14000b625  test    r8d, r8d
0x14000b628  jz      loc_14000B6AF
0x14000b62e  mov     eax, r8d
0x14000b631  mov     ebx, 4
0x14000b636  and     eax, 3
0x14000b639  sub     ebx, eax
0x14000b63b  test    eax, eax
0x14000b63d  cmovz   ebx, eax
0x14000b640  cmp     dword ptr [rcx], 1
0x14000b643  jnz     short loc_14000B676
0x14000b645  mov     rax, [rcx+8]
0x14000b649  mov     rax, [rax+10h]
0x14000b64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b652  test    eax, eax
0x14000b654  jz      short loc_14000B6A1
0x14000b656  test    ebx, ebx
0x14000b658  jz      short loc_14000B6AF
0x14000b65a  mov     rax, [rdi+8]
0x14000b65e  lea     rdx, qword_140021B20
0x14000b665  mov     rax, [rax+10h]
0x14000b669  mov     rcx, rdi
0x14000b66c  mov     r8d, ebx
0x14000b66f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b674  jmp     short loc_14000B6B4
0x14000b676  cmp     dword ptr [rcx], 0
0x14000b679  jnz     short loc_14000B6A5
0x14000b67b  mov     rax, [rcx+8]
0x14000b67f  mov     rax, [rax+18h]
0x14000b683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b688  test    eax, eax
0x14000b68a  jz      short loc_14000B6A1
0x14000b68c  test    ebx, ebx
0x14000b68e  jz      short loc_14000B6AF
0x14000b690  mov     rax, [rdi+8]
0x14000b694  lea     rdx, byte_140021B98
0x14000b69b  mov     rax, [rax+18h]
0x14000b69f  jmp     short loc_14000B669
0x14000b6a1  xor     eax, eax
0x14000b6a3  jmp     short loc_14000B6B4
0x14000b6a5  xor     eax, eax
0x14000b6a7  cmp     dword ptr [rcx], 2
0x14000b6aa  setz    al
0x14000b6ad  jmp     short loc_14000B6B4
0x14000b6af  mov     eax, 1
0x14000b6b4  mov     rbx, [rsp+28h+arg_0]
0x14000b6b9  add     rsp, 20h
0x14000b6bd  pop     rdi
0x14000b6be  retn
```
