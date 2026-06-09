# FCFreeShadowBuffer

- ea: `0x140002530`
- end: `0x140002572`
- name: `FCFreeShadowBuffer`
- size: `66`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400027a0`
- `0x140002a00`

## callees

- `0x140002530`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002544`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002544`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002560`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002560`

## pseudocode

```c
void __fastcall FCFreeShadowBuffer(__int64 a1, void *a2, char a3)
{
  if ( a3 == 1 )
  {
    ExFreeToNPagedLookasideList(&gShadowBufferList, a2);
  }
  else if ( a3 == 2 )
  {
    ExFreePoolWithTag(a2, 0x62734346u);
  }
}

```

## disassembly

```asm
0x140002530  sub     rsp, 28h
0x140002534  mov     rax, rdx
0x140002537  cmp     r8b, 1
0x14000253b  jnz     short loc_140002552
0x14000253d  lea     rcx, gShadowBufferList; Lookaside
0x140002544  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000254b  nop     dword ptr [rax+rax+00h]
0x140002550  jmp     short loc_14000256C
0x140002552  cmp     r8b, 2
0x140002556  jnz     short loc_14000256C
0x140002558  mov     edx, 62734346h; Tag
0x14000255d  mov     rcx, rax; P
0x140002560  call    cs:__imp_ExFreePoolWithTag
0x140002567  nop     dword ptr [rax+rax+00h]
0x14000256c  add     rsp, 28h
0x140002570  retn
```
