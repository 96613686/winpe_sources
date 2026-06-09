# Ssl3InitMacHashLookasideList

- ea: `0x180083958`
- end: `0x180083a09`
- name: `Ssl3InitMacHashLookasideList`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081674`

## callees

- `0x180083958`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180083984`
- `ntoskrnl!ExAllocatePool2` at `0x180083984`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800839ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800839ea`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800839be`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1800839be`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1800839d6`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1800839d6`

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
0x180083958  mov     [rsp+arg_8], rbx
0x18008395d  mov     [rsp+arg_10], rsi
0x180083962  push    rdi
0x180083963  sub     rsp, 40h
0x180083967  cmp     qword ptr [rcx], 0
0x18008396b  mov     rdi, rcx
0x18008396e  mov     esi, edx
0x180083970  jnz     loc_1800839F6
0x180083976  mov     edx, 80h
0x18008397b  mov     r8d, 62676E43h
0x180083981  lea     ecx, [rdx-40h]
0x180083984  call    cs:__imp_ExAllocatePool2
0x18008398b  nop     dword ptr [rax+rax+00h]
0x180083990  mov     rbx, rax
0x180083993  test    rax, rax
0x180083996  jnz     short loc_18008399F
0x180083998  mov     eax, 0C0000017h
0x18008399d  jmp     short loc_1800839F8
0x18008399f  xor     eax, eax
0x1800839a1  xor     r9d, r9d; Flags
0x1800839a4  mov     [rsp+48h+Depth], ax; Depth
0x1800839a9  xor     r8d, r8d; Free
0x1800839ac  mov     [rsp+48h+Tag], 62676E43h; Tag
0x1800839b4  xor     edx, edx; Allocate
0x1800839b6  mov     rcx, rbx; Lookaside
0x1800839b9  mov     [rsp+48h+Size], rsi; Size
0x1800839be  call    cs:__imp_ExInitializePagedLookasideList
0x1800839c5  nop     dword ptr [rax+rax+00h]
0x1800839ca  xor     eax, eax
0x1800839cc  lock cmpxchg [rdi], rbx
0x1800839d1  jz      short loc_1800839F6
0x1800839d3  mov     rcx, rbx; Lookaside
0x1800839d6  call    cs:__imp_ExDeletePagedLookasideList
0x1800839dd  nop     dword ptr [rax+rax+00h]
0x1800839e2  mov     edx, 62676E43h; Tag
0x1800839e7  mov     rcx, rbx; P
0x1800839ea  call    cs:__imp_ExFreePoolWithTag
0x1800839f1  nop     dword ptr [rax+rax+00h]
0x1800839f6  xor     eax, eax
0x1800839f8  mov     rbx, [rsp+48h+arg_8]
0x1800839fd  mov     rsi, [rsp+48h+arg_10]
0x180083a02  add     rsp, 40h
0x180083a06  pop     rdi
0x180083a07  retn
```
