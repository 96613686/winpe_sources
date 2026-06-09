# Locator_DependentSIDArray

- ea: `0x180020510`
- end: `0x180020589`
- name: `Locator_DependentSIDArray`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180020104`
- `0x180020510`
- `0x180045010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020555`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180020555`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020562`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180020562`

## pseudocode

```c
char *__fastcall Locator_DependentSIDArray(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  char *v5; // rbx
  unsigned __int64 VariableNumber; // rdi
  unsigned __int64 v7; // rsi

  v2 = *(_QWORD *)(a2 + 16);
  v5 = (char *)(*(__int64 (__fastcall **)(__int64, __int64))v2)(a1, v2);
  if ( *(_QWORD *)(v2 + 32) )
    VariableNumber = GetVariableNumber(a1);
  else
    VariableNumber = *(_QWORD *)(v2 + 56);
  v7 = 0;
  if ( !VariableNumber )
    return &v5[*(_QWORD *)(a2 + 40)];
  while ( IsValidSid(v5) )
  {
    ++v7;
    v5 += GetLengthSid(v5);
    if ( v7 >= VariableNumber )
      return &v5[*(_QWORD *)(a2 + 40)];
  }
  return 0;
}

```

## disassembly

```asm
0x180020510  push    rbx
0x180020512  push    rbp
0x180020513  push    rsi
0x180020514  push    rdi
0x180020515  sub     rsp, 28h
0x180020519  mov     rdi, [rdx+10h]
0x18002051d  mov     rbp, rdx
0x180020520  mov     rdx, rdi
0x180020523  mov     rsi, rcx
0x180020526  mov     rax, [rdi]
0x180020529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002052e  mov     rdx, [rdi+20h]
0x180020532  mov     rbx, rax
0x180020535  test    rdx, rdx
0x180020538  jz      short loc_180020547
0x18002053a  mov     rcx, rsi
0x18002053d  call    GetVariableNumber
0x180020542  mov     rdi, rax
0x180020545  jmp     short loc_18002054B
0x180020547  mov     rdi, [rdi+38h]
0x18002054b  xor     esi, esi
0x18002054d  test    rdi, rdi
0x180020550  jz      short loc_180020575
0x180020552  mov     rcx, rbx; pSid
0x180020555  call    cs:__imp_IsValidSid
0x18002055b  test    eax, eax
0x18002055d  jz      short loc_180020585
0x18002055f  mov     rcx, rbx; pSid
0x180020562  call    cs:__imp_GetLengthSid
0x180020568  mov     eax, eax
0x18002056a  inc     rsi
0x18002056d  add     rbx, rax
0x180020570  cmp     rsi, rdi
0x180020573  jb      short loc_180020552
0x180020575  mov     rax, [rbp+28h]
0x180020579  add     rax, rbx
0x18002057c  add     rsp, 28h
0x180020580  pop     rdi
0x180020581  pop     rsi
0x180020582  pop     rbp
0x180020583  pop     rbx
0x180020584  retn
0x180020585  xor     eax, eax
0x180020587  jmp     short loc_18002057C
```
