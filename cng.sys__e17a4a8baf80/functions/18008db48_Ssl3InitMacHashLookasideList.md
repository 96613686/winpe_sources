# Ssl3InitMacHashLookasideList

- ea: `0x18008db48`
- end: `0x18008dbf9`
- name: `Ssl3InitMacHashLookasideList`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008b864`

## callees

- `0x18008db48`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18008db74`
- `ntoskrnl!ExAllocatePool2` at `0x18008db74`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008dbda`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008dbda`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18008dbae`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18008dbae`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18008dbc6`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x18008dbc6`

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
0x18008db48  mov     [rsp+arg_8], rbx
0x18008db4d  mov     [rsp+arg_10], rsi
0x18008db52  push    rdi
0x18008db53  sub     rsp, 40h
0x18008db57  cmp     qword ptr [rcx], 0
0x18008db5b  mov     rdi, rcx
0x18008db5e  mov     esi, edx
0x18008db60  jnz     loc_18008DBE6
0x18008db66  mov     edx, 80h
0x18008db6b  mov     r8d, 62676E43h
0x18008db71  lea     ecx, [rdx-40h]
0x18008db74  call    cs:__imp_ExAllocatePool2
0x18008db7b  nop     dword ptr [rax+rax+00h]
0x18008db80  mov     rbx, rax
0x18008db83  test    rax, rax
0x18008db86  jnz     short loc_18008DB8F
0x18008db88  mov     eax, 0C0000017h
0x18008db8d  jmp     short loc_18008DBE8
0x18008db8f  xor     eax, eax
0x18008db91  xor     r9d, r9d; Flags
0x18008db94  mov     [rsp+48h+Depth], ax; Depth
0x18008db99  xor     r8d, r8d; Free
0x18008db9c  mov     [rsp+48h+Tag], 62676E43h; Tag
0x18008dba4  xor     edx, edx; Allocate
0x18008dba6  mov     rcx, rbx; Lookaside
0x18008dba9  mov     [rsp+48h+Size], rsi; Size
0x18008dbae  call    cs:__imp_ExInitializePagedLookasideList
0x18008dbb5  nop     dword ptr [rax+rax+00h]
0x18008dbba  xor     eax, eax
0x18008dbbc  lock cmpxchg [rdi], rbx
0x18008dbc1  jz      short loc_18008DBE6
0x18008dbc3  mov     rcx, rbx; Lookaside
0x18008dbc6  call    cs:__imp_ExDeletePagedLookasideList
0x18008dbcd  nop     dword ptr [rax+rax+00h]
0x18008dbd2  mov     edx, 62676E43h; Tag
0x18008dbd7  mov     rcx, rbx; P
0x18008dbda  call    cs:__imp_ExFreePoolWithTag
0x18008dbe1  nop     dword ptr [rax+rax+00h]
0x18008dbe6  xor     eax, eax
0x18008dbe8  mov     rbx, [rsp+48h+arg_8]
0x18008dbed  mov     rsi, [rsp+48h+arg_10]
0x18008dbf2  add     rsp, 40h
0x18008dbf6  pop     rdi
0x18008dbf7  retn
```
