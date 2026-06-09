# flush_out

- ea: `0x14000ec84`
- end: `0x14000ecf8`
- name: `flush_out`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d820`
- `0x14000ef9c`
- `0x14000f1f0`
- `0x14000f270`

## callees

- `0x14000ec84`
- `0x140019010`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x14000ecaf`
- `WS2_32!__imp_htonl` at `0x14000ecaf`

## pseudocode

```c
__int64 __fastcall flush_out(__int64 a1, int a2)
{
  u_long *v2; // rbx
  unsigned int v4; // eax
  int v5; // ecx
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // rcx

  v2 = *(u_long **)(a1 + 48);
  v4 = 0x80000000;
  v5 = *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 48) - 4;
  if ( a2 != 1 )
    v4 = 0;
  *v2 = htonl(v4 | v5);
  v6 = *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 24);
  if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(a1 + 16))(*(_QWORD *)a1, *(_QWORD *)(a1 + 24), v6) != v6 )
    return 0;
  v8 = *(_QWORD *)(a1 + 24);
  result = 1;
  *(_QWORD *)(a1 + 48) = v8;
  *(_QWORD *)(a1 + 32) = v8 + 4;
  return result;
}

```

## disassembly

```asm
0x14000ec84  mov     [rsp+arg_0], rbx
0x14000ec89  push    rdi
0x14000ec8a  sub     rsp, 20h
0x14000ec8e  mov     rbx, [rcx+30h]
0x14000ec92  mov     rdi, rcx
0x14000ec95  mov     ecx, [rcx+20h]
0x14000ec98  xor     r8d, r8d
0x14000ec9b  mov     eax, 80000000h
0x14000eca0  sub     ecx, [rdi+30h]
0x14000eca3  sub     ecx, 4
0x14000eca6  cmp     edx, 1
0x14000eca9  cmovnz  eax, r8d
0x14000ecad  or      ecx, eax; hostlong
0x14000ecaf  call    cs:__imp_htonl
0x14000ecb5  mov     [rbx], eax
0x14000ecb7  mov     ebx, [rdi+20h]
0x14000ecba  sub     ebx, [rdi+18h]
0x14000ecbd  mov     rdx, [rdi+18h]
0x14000ecc1  mov     r8d, ebx
0x14000ecc4  mov     rcx, [rdi]
0x14000ecc7  mov     rax, [rdi+10h]
0x14000eccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ecd0  cmp     eax, ebx
0x14000ecd2  jz      short loc_14000ECD8
0x14000ecd4  xor     eax, eax
0x14000ecd6  jmp     short loc_14000ECED
0x14000ecd8  mov     rcx, [rdi+18h]
0x14000ecdc  mov     eax, 1
0x14000ece1  mov     [rdi+30h], rcx
0x14000ece5  add     rcx, 4
0x14000ece9  mov     [rdi+20h], rcx
0x14000eced  mov     rbx, [rsp+28h+arg_0]
0x14000ecf2  add     rsp, 20h
0x14000ecf6  pop     rdi
0x14000ecf7  retn
```
