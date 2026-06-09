# PsmpNotificationsGetApplicationIdentityFromApplication

- ea: `0x18000da40`
- end: `0x18000dac0`
- name: `PsmpNotificationsGetApplicationIdentityFromApplication`
- size: `128`
- prototype: `_WORD *__fastcall(__int64, _DWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009b40`
- `0x18000d934`
- `0x1800114d0`

## callees

- `0x18000da40`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000da70`
- `ntdll!RtlCopySid` at `0x18000da70`

## pseudocode

```c
_WORD *__fastcall PsmpNotificationsGetApplicationIdentityFromApplication(__int64 a1, _DWORD *a2)
{
  _WORD *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdx
  _WORD *v6; // rbx
  _WORD *result; // rax

  v3 = *(_WORD **)(a1 + 8);
  a2[17] = *(_DWORD *)(*(_QWORD *)(a1 + 312) + 4LL);
  RtlCopySid(0x44u, a2, *(PSID *)(*(_QWORD *)(a1 + 312) + 40LL));
  v4 = 2147483646;
  v5 = 232;
  v6 = a2 + 18;
  do
  {
    if ( !v4 )
      break;
    if ( !*v3 )
      break;
    *v6++ = *v3++;
    --v4;
    --v5;
  }
  while ( v5 );
  result = v6 - 1;
  if ( v5 )
    result = v6;
  *result = 0;
  return result;
}

```

## disassembly

```asm
0x18000da40  mov     [rsp+arg_0], rbx
0x18000da45  push    rdi
0x18000da46  sub     rsp, 20h
0x18000da4a  mov     rax, [rcx+138h]
0x18000da51  mov     rbx, rdx
0x18000da54  mov     rdi, [rcx+8]
0x18000da58  mov     r8d, [rax+4]
0x18000da5c  mov     [rdx+44h], r8d
0x18000da60  mov     r8, [rcx+138h]
0x18000da67  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000da6c  mov     r8, [r8+28h]; SourceSid
0x18000da70  call    cs:__imp_RtlCopySid
0x18000da76  mov     eax, 7FFFFFFEh
0x18000da7b  mov     edx, 0E8h
0x18000da80  add     rbx, 48h ; 'H'
0x18000da84  test    rax, rax
0x18000da87  jz      short loc_18000DAA5
0x18000da89  movzx   ecx, word ptr [rdi]
0x18000da8c  test    cx, cx
0x18000da8f  jz      short loc_18000DAA5
0x18000da91  mov     [rbx], cx
0x18000da94  add     rdi, 2
0x18000da98  add     rbx, 2
0x18000da9c  dec     rax
0x18000da9f  sub     rdx, 1
0x18000daa3  jnz     short loc_18000DA84
0x18000daa5  test    rdx, rdx
0x18000daa8  lea     rax, [rbx-2]
0x18000daac  cmovnz  rax, rbx
0x18000dab0  mov     rbx, [rsp+28h+arg_0]
0x18000dab5  xor     ecx, ecx
0x18000dab7  mov     [rax], cx
0x18000daba  add     rsp, 20h
0x18000dabe  pop     rdi
0x18000dabf  retn
```
