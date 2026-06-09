# Locator_DependentSID

- ea: `0x1800204b0`
- end: `0x1800204fd`
- name: `Locator_DependentSID`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800204b0`
- `0x180045010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800204cf`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800204cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800204e0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800204e0`

## pseudocode

```c
char *__fastcall Locator_DependentSID(__int64 a1, __int64 a2)
{
  char *v3; // rbx

  v3 = (char *)(**(__int64 (***)(void))(a2 + 16))();
  if ( IsValidSid(v3) )
    return &v3[GetLengthSid(v3) + *(_QWORD *)(a2 + 40)];
  else
    return 0;
}

```

## disassembly

```asm
0x1800204b0  mov     [rsp+arg_0], rbx
0x1800204b5  push    rdi
0x1800204b6  sub     rsp, 20h
0x1800204ba  mov     rdi, rdx
0x1800204bd  mov     rdx, [rdx+10h]
0x1800204c1  mov     rax, [rdx]
0x1800204c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204c9  mov     rcx, rax; pSid
0x1800204cc  mov     rbx, rax
0x1800204cf  call    cs:__imp_IsValidSid
0x1800204d5  test    eax, eax
0x1800204d7  jnz     short loc_1800204DD
0x1800204d9  xor     eax, eax
0x1800204db  jmp     short loc_1800204F2
0x1800204dd  mov     rcx, rbx; pSid
0x1800204e0  call    cs:__imp_GetLengthSid
0x1800204e6  mov     ecx, eax
0x1800204e8  mov     rax, [rdi+28h]
0x1800204ec  add     rax, rcx
0x1800204ef  add     rax, rbx
0x1800204f2  mov     rbx, [rsp+28h+arg_0]
0x1800204f7  add     rsp, 20h
0x1800204fb  pop     rdi
0x1800204fc  retn
```
