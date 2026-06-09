# ReleaseKeyArray(IMVKey * *,ulong)

- ea: `0x180015934`
- end: `0x180015982`
- name: `?ReleaseKeyArray@@YAXPEAPEAUIMVKey@@K@Z`
- size: `78`
- prototype: `void __fastcall(struct IMVKey **, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014d28`
- `0x180015474`

## callees

- `0x180015934`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001597b`

## pseudocode

```c
void __fastcall ReleaseKeyArray(struct IMVKey **a1, unsigned int a2)
{
  __int64 i; // rbx
  struct IMVKey *v5; // rcx

  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v5 = a1[i];
    if ( v5 )
      (*(void (__fastcall **)(struct IMVKey *))(*(_QWORD *)v5 + 16LL))(v5);
  }
  CoTaskMemFree(a1);
}

```

## disassembly

```asm
0x180015934  mov     [rsp+arg_0], rbx
0x180015939  mov     [rsp+arg_8], rsi
0x18001593e  push    rdi
0x18001593f  sub     rsp, 20h
0x180015943  mov     esi, edx
0x180015945  mov     rdi, rcx
0x180015948  xor     ebx, ebx
0x18001594a  test    edx, edx
0x18001594c  jz      short loc_180015969
0x18001594e  mov     rcx, [rdi+rbx*8]
0x180015952  test    rcx, rcx
0x180015955  jz      short loc_180015963
0x180015957  mov     rax, [rcx]
0x18001595a  mov     rax, [rax+10h]
0x18001595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015963  inc     ebx
0x180015965  cmp     ebx, esi
0x180015967  jb      short loc_18001594E
0x180015969  mov     rcx, rdi
0x18001596c  mov     rbx, [rsp+28h+arg_0]
0x180015971  mov     rsi, [rsp+28h+arg_8]
0x180015976  add     rsp, 20h
0x18001597a  pop     rdi
0x18001597b  jmp     cs:__imp_CoTaskMemFree
```
