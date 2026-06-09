# Ssl3InitMacHashLookasideList

- ea: `0x180084948`
- end: `0x1800849f9`
- name: `Ssl3InitMacHashLookasideList`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180082664`

## callees

- `0x180084948`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180084974`
- `ntoskrnl!ExAllocatePool2` at `0x180084974`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800849da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800849da`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800849ae`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800849ae`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1800849c6`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1800849c6`

## pseudocode

```c
__int64 __fastcall Ssl3InitMacHashLookasideList(volatile signed __int64 *a1, unsigned int a2)
{
  SIZE_T Size; // rsi
  struct _PAGED_LOOKASIDE_LIST *Pool2; // rbx

  Size = a2;
  if ( !*a1 )
  {
    Pool2 = (struct _PAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 1650945603);
    if ( !Pool2 )
      return 3221225495LL;
    ExInitializePagedLookasideList(Pool2, 0, 0, 0, Size, 0x62676E43u, 0);
    if ( _InterlockedCompareExchange64(a1, (signed __int64)Pool2, 0) )
    {
      ExDeletePagedLookasideList(Pool2);
      ExFreePoolWithTag(Pool2, 0x62676E43u);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180084948  mov     [rsp+arg_8], rbx
0x18008494d  mov     [rsp+arg_10], rsi
0x180084952  push    rdi
0x180084953  sub     rsp, 40h
0x180084957  cmp     qword ptr [rcx], 0
0x18008495b  mov     rdi, rcx
0x18008495e  mov     esi, edx
0x180084960  jnz     loc_1800849E6
0x180084966  mov     edx, 80h
0x18008496b  mov     r8d, 62676E43h
0x180084971  lea     ecx, [rdx-40h]
0x180084974  call    cs:__imp_ExAllocatePool2
0x18008497b  nop     dword ptr [rax+rax+00h]
0x180084980  mov     rbx, rax
0x180084983  test    rax, rax
0x180084986  jnz     short loc_18008498F
0x180084988  mov     eax, 0C0000017h
0x18008498d  jmp     short loc_1800849E8
0x18008498f  xor     eax, eax
0x180084991  xor     r9d, r9d; Flags
0x180084994  mov     [rsp+48h+Depth], ax; Depth
0x180084999  xor     r8d, r8d; Free
0x18008499c  mov     [rsp+48h+Tag], 62676E43h; Tag
0x1800849a4  xor     edx, edx; Allocate
0x1800849a6  mov     rcx, rbx; Lookaside
0x1800849a9  mov     [rsp+48h+Size], rsi; Size
0x1800849ae  call    cs:__imp_ExInitializePagedLookasideList
0x1800849b5  nop     dword ptr [rax+rax+00h]
0x1800849ba  xor     eax, eax
0x1800849bc  lock cmpxchg [rdi], rbx
0x1800849c1  jz      short loc_1800849E6
0x1800849c3  mov     rcx, rbx; Lookaside
0x1800849c6  call    cs:__imp_ExDeletePagedLookasideList
0x1800849cd  nop     dword ptr [rax+rax+00h]
0x1800849d2  mov     edx, 62676E43h; Tag
0x1800849d7  mov     rcx, rbx; P
0x1800849da  call    cs:__imp_ExFreePoolWithTag
0x1800849e1  nop     dword ptr [rax+rax+00h]
0x1800849e6  xor     eax, eax
0x1800849e8  mov     rbx, [rsp+48h+arg_8]
0x1800849ed  mov     rsi, [rsp+48h+arg_10]
0x1800849f2  add     rsp, 40h
0x1800849f6  pop     rdi
0x1800849f7  retn
```
