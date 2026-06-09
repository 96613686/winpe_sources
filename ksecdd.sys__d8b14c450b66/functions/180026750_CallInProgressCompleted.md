# CallInProgressCompleted

- ea: `0x180026750`
- end: `0x18002679b`
- name: `CallInProgressCompleted`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e94`

## callees

- `0x180010920`
- `0x180026750`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x180026786`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x180026786`

## pseudocode

```c
__int64 __fastcall CallInProgressCompleted(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v3; // rbx

  v3 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, _QWORD))*v3)(v3[1], *(unsigned int *)(a1 + 8), a2, a3, v3[2]);
    ExFreeToLookasideListEx(&Lookaside, v3);
  }
  return 0;
}

```

## disassembly

```asm
0x180026750  push    rbx
0x180026752  sub     rsp, 30h
0x180026756  mov     rbx, [rcx]
0x180026759  test    rbx, rbx
0x18002675c  jz      short loc_180026792
0x18002675e  mov     r9, [rbx+10h]
0x180026762  mov     rax, [rbx]
0x180026765  mov     [rsp+38h+var_18], r9
0x18002676a  mov     r9d, r8d
0x18002676d  mov     r8, rdx
0x180026770  mov     edx, [rcx+8]
0x180026773  mov     rcx, [rbx+8]
0x180026777  call    _guard_dispatch_icall
0x18002677c  mov     rdx, rbx; Entry
0x18002677f  lea     rcx, Lookaside; Lookaside
0x180026786  call    cs:__imp_ExFreeToLookasideListEx
0x18002678d  nop     dword ptr [rax+rax+00h]
0x180026792  xor     eax, eax
0x180026794  add     rsp, 30h
0x180026798  pop     rbx
0x180026799  retn
```
