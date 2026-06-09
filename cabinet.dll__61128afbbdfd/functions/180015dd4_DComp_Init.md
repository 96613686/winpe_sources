# DComp_Init

- ea: `0x180015dd4`
- end: `0x180015e6c`
- name: `DComp_Init`
- size: `152`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015bc8`

## callees

- `0x180015dd4`
- `0x180016070`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall DComp_Init(__int64 a1, char a2)
{
  __int64 (__fastcall *v4)(_QWORD); // rax
  __int64 v5; // rax
  __int64 v6; // rdx

  *(_DWORD *)(a1 + 376) = 1 << a2;
  *(_DWORD *)(a1 + 368) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  *(_DWORD *)(a1 + 372) = (1 << a2) - 1;
  v4 = *(__int64 (__fastcall **)(_QWORD))(a1 + 8);
  *(_BYTE *)(a1 + 396) = a2;
  v5 = v4((unsigned int)(1 << a2));
  *(_QWORD *)(a1 + 344) = v5;
  if ( !v5 )
    return 1;
  *(_QWORD *)(a1 + 360) = v5;
  LOBYTE(v6) = a2;
  *(_QWORD *)(a1 + 352) = v5 + *(int *)(a1 + 376);
  Lz_Init(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x180015dd4  mov     [rsp+arg_0], rbx
0x180015dd9  push    rdi
0x180015dda  sub     rsp, 20h
0x180015dde  mov     rbx, rcx
0x180015de1  mov     r8d, 1
0x180015de7  mov     cl, dl
0x180015de9  mov     dil, dl
0x180015dec  shl     r8d, cl
0x180015def  mov     ecx, r8d
0x180015df2  mov     [rbx+178h], r8d
0x180015df9  mov     dword ptr [rbx+170h], 0
0x180015e03  lea     eax, [r8-1]
0x180015e07  mov     dword ptr [rbx+190h], 0
0x180015e11  mov     [rbx+174h], eax
0x180015e17  mov     rax, [rbx+8]
0x180015e1b  mov     [rbx+18Ch], dl
0x180015e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e26  mov     [rbx+158h], rax
0x180015e2d  mov     rcx, rax
0x180015e30  test    rax, rax
0x180015e33  jz      short loc_180015E5C
0x180015e35  mov     [rbx+168h], rax
0x180015e3c  mov     dl, dil
0x180015e3f  movsxd  rax, dword ptr [rbx+178h]
0x180015e46  add     rax, rcx
0x180015e49  mov     rcx, rbx
0x180015e4c  mov     [rbx+160h], rax
0x180015e53  call    Lz_Init
0x180015e58  xor     eax, eax
0x180015e5a  jmp     short loc_180015E61
0x180015e5c  mov     eax, 1
0x180015e61  mov     rbx, [rsp+28h+arg_0]
0x180015e66  add     rsp, 20h
0x180015e6a  pop     rdi
0x180015e6b  retn
```
