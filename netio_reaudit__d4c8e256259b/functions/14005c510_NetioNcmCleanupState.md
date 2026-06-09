# NetioNcmCleanupState

- ea: `0x14005c510`
- end: `0x14005c5b8`
- name: `NetioNcmCleanupState`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14005c510`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x14005c521`
- `ntoskrnl!RtlDeleteHashTable` at `0x14005c534`
- `ntoskrnl!RtlDeleteHashTable` at `0x14005c521`
- `ntoskrnl!RtlDeleteHashTable` at `0x14005c534`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c571`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c571`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientUnregister` at `0x14005c58e`
- `ext-ms-win-kmpdc-l1-1-0!Pdcv2ActivationClientUnregister` at `0x14005c58e`

## pseudocode

```c
void NetioNcmCleanupState()
{
  PVOID *v0; // rbx
  PVOID *v1; // rax
  PVOID **v2; // rdx
  PVOID *v3; // rcx

  RtlDeleteHashTable(&stru_14009B008);
  RtlDeleteHashTable(&stru_14009B030);
  v0 = (PVOID *)qword_14009B098;
  while ( v0 != &qword_14009B098 )
  {
    v1 = (PVOID *)*v0;
    if ( *((PVOID **)*v0 + 1) != v0 || (v2 = (PVOID **)v0[1], *v2 != v0) )
      __fastfail(3u);
    *v2 = v1;
    v3 = v0;
    v1[1] = v2;
    v0 = v1;
    ExFreePoolWithTag(v3, 0);
  }
  if ( qword_14009B0A8 )
  {
    Pdcv2ActivationClientUnregister();
    qword_14009B0A8 = 0;
  }
}

```

## disassembly

```asm
0x14005c510  mov     [rsp+arg_0], rbx
0x14005c515  push    rdi
0x14005c516  sub     rsp, 20h
0x14005c51a  lea     rcx, stru_14009B008; HashTable
0x14005c521  call    cs:__imp_RtlDeleteHashTable
0x14005c528  nop     dword ptr [rax+rax+00h]
0x14005c52d  lea     rcx, stru_14009B030; HashTable
0x14005c534  call    cs:__imp_RtlDeleteHashTable
0x14005c53b  nop     dword ptr [rax+rax+00h]
0x14005c540  mov     rbx, cs:qword_14009B098
0x14005c547  lea     rdi, qword_14009B098
0x14005c54e  jmp     short loc_14005C57D
0x14005c550  mov     rax, [rbx]
0x14005c553  cmp     [rax+8], rbx
0x14005c557  jnz     short loc_14005C5B1
0x14005c559  mov     rdx, [rbx+8]
0x14005c55d  cmp     [rdx], rbx
0x14005c560  jnz     short loc_14005C5B1
0x14005c562  mov     [rdx], rax
0x14005c565  mov     rcx, rbx; P
0x14005c568  mov     [rax+8], rdx
0x14005c56c  mov     rbx, rax
0x14005c56f  xor     edx, edx; Tag
0x14005c571  call    cs:__imp_ExFreePoolWithTag
0x14005c578  nop     dword ptr [rax+rax+00h]
0x14005c57d  cmp     rbx, rdi
0x14005c580  jnz     short loc_14005C550
0x14005c582  mov     rcx, cs:qword_14009B0A8
0x14005c589  test    rcx, rcx
0x14005c58c  jz      short loc_14005C5A5
0x14005c58e  call    cs:__imp_Pdcv2ActivationClientUnregister
0x14005c595  nop     dword ptr [rax+rax+00h]
0x14005c59a  mov     cs:qword_14009B0A8, 0
0x14005c5a5  mov     rbx, [rsp+28h+arg_0]
0x14005c5aa  add     rsp, 20h
0x14005c5ae  pop     rdi
0x14005c5af  retn
0x14005c5b1  mov     ecx, 3
0x14005c5b6  int     29h; Win8: RtlFailFast(ecx)
```
