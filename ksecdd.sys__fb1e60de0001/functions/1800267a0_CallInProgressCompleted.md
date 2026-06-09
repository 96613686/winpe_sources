# CallInProgressCompleted

- ea: `0x1800267a0`
- end: `0x1800267eb`
- name: `CallInProgressCompleted`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e94`

## callees

- `0x180010980`
- `0x1800267a0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800267d6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1800267d6`

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
0x1800267a0  push    rbx
0x1800267a2  sub     rsp, 30h
0x1800267a6  mov     rbx, [rcx]
0x1800267a9  test    rbx, rbx
0x1800267ac  jz      short loc_1800267E2
0x1800267ae  mov     r9, [rbx+10h]
0x1800267b2  mov     rax, [rbx]
0x1800267b5  mov     [rsp+38h+var_18], r9
0x1800267ba  mov     r9d, r8d
0x1800267bd  mov     r8, rdx
0x1800267c0  mov     edx, [rcx+8]
0x1800267c3  mov     rcx, [rbx+8]
0x1800267c7  call    _guard_dispatch_icall
0x1800267cc  mov     rdx, rbx; Entry
0x1800267cf  lea     rcx, Lookaside; Lookaside
0x1800267d6  call    cs:__imp_ExFreeToLookasideListEx
0x1800267dd  nop     dword ptr [rax+rax+00h]
0x1800267e2  xor     eax, eax
0x1800267e4  add     rsp, 30h
0x1800267e8  pop     rbx
0x1800267e9  retn
```
