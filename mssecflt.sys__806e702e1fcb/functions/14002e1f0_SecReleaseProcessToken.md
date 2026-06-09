# SecReleaseProcessToken

- ea: `0x14002e1f0`
- end: `0x14002e23a`
- name: `SecReleaseProcessToken`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140006b6c`
- `0x140040a08`

## callees

- `0x14002e1f0`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002e220`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14002e220`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e204`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e204`

## pseudocode

```c
void __fastcall SecReleaseProcessToken(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 64);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 64) = 0;
  }
  if ( *(_QWORD *)a1 )
  {
    PsDereferencePrimaryToken(*(PACCESS_TOKEN *)a1);
    *(_QWORD *)a1 = 0;
  }
}

```

## disassembly

```asm
0x14002e1f0  push    rbx
0x14002e1f2  sub     rsp, 20h
0x14002e1f6  mov     rbx, rcx
0x14002e1f9  mov     rcx, [rcx+40h]; P
0x14002e1fd  test    rcx, rcx
0x14002e200  jz      short loc_14002E218
0x14002e202  xor     edx, edx; Tag
0x14002e204  call    cs:__imp_ExFreePoolWithTag
0x14002e20b  nop     dword ptr [rax+rax+00h]
0x14002e210  mov     qword ptr [rbx+40h], 0
0x14002e218  mov     rcx, [rbx]; PrimaryToken
0x14002e21b  test    rcx, rcx
0x14002e21e  jz      short loc_14002E233
0x14002e220  call    cs:__imp_PsDereferencePrimaryToken
0x14002e227  nop     dword ptr [rax+rax+00h]
0x14002e22c  mov     qword ptr [rbx], 0
0x14002e233  add     rsp, 20h
0x14002e237  pop     rbx
0x14002e238  retn
```
