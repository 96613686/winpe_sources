# FltpCleanupNameControl

- ea: `0x18005c5a0`
- end: `0x18005c5f2`
- name: `FltpCleanupNameControl`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180022b4c`
- `0x1800509d0`
- `0x18005aa30`
- `0x18005b920`
- `0x18005e010`
- `0x180066990`
- `0x1800674b0`
- `0x180068900`
- `0x180078690`

## callees

- `0x18005c5a0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005c5e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005c5e4`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c5c9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18005c5c9`

## pseudocode

```c
void __fastcall FltpCleanupNameControl(__int64 a1)
{
  int v1; // eax
  void *v3; // rcx

  v1 = *(_DWORD *)(a1 + 16);
  if ( (v1 & 1) != 0 )
  {
    v3 = *(void **)(a1 + 8);
    if ( (v1 & 2) != 0 )
    {
      ExFreeToPagedLookasideList(&stru_18003F440, v3);
      *(_DWORD *)(a1 + 16) &= ~2u;
    }
    else
    {
      ExFreePoolWithTag(v3, 0x346E4D46u);
    }
    *(_DWORD *)(a1 + 16) &= ~1u;
  }
}

```

## disassembly

```asm
0x18005c5a0  push    rbx
0x18005c5a2  sub     rsp, 20h
0x18005c5a6  mov     eax, [rcx+10h]
0x18005c5a9  mov     rbx, rcx
0x18005c5ac  test    al, 1
0x18005c5ae  jnz     short loc_18005C5B7
0x18005c5b0  add     rsp, 20h
0x18005c5b4  pop     rbx
0x18005c5b5  retn
0x18005c5b7  mov     rcx, [rcx+8]; P
0x18005c5bb  test    al, 2
0x18005c5bd  jz      short loc_18005C5DF
0x18005c5bf  mov     rdx, rcx; Entry
0x18005c5c2  lea     rcx, stru_18003F440; Lookaside
0x18005c5c9  call    cs:__imp_ExFreeToPagedLookasideList
0x18005c5d0  nop     dword ptr [rax+rax+00h]
0x18005c5d5  and     dword ptr [rbx+10h], 0FFFFFFFDh
0x18005c5d9  and     dword ptr [rbx+10h], 0FFFFFFFEh
0x18005c5dd  jmp     short loc_18005C5B0
0x18005c5df  mov     edx, 346E4D46h; Tag
0x18005c5e4  call    cs:__imp_ExFreePoolWithTag
0x18005c5eb  nop     dword ptr [rax+rax+00h]
0x18005c5f0  jmp     short loc_18005C5D9
```
