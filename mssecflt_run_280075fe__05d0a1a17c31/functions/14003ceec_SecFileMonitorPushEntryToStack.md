# SecFileMonitorPushEntryToStack

- ea: `0x14003ceec`
- end: `0x14003cfaf`
- name: `SecFileMonitorPushEntryToStack`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003c94c`

## callees

- `0x140011610`
- `0x14003ceec`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003cf1a`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14003cf1a`

## pseudocode

```c
__int64 __fastcall SecFileMonitorPushEntryToStack(struct _SLIST_ENTRY *a1, __int64 a2, __int64 a3, PSLIST_ENTRY *a4)
{
  unsigned int v8; // ebx
  PSLIST_ENTRY v9; // r10
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, __int64, __int64); // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  PSLIST_ENTRY v14; // rax

  ++*(_DWORD *)(a3 + 20);
  v8 = 0;
  v9 = ExpInterlockedPopEntrySList((PSLIST_HEADER)a3);
  if ( v9
    || (v10 = *(unsigned int *)(a3 + 44),
        v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(a3 + 48),
        v12 = *(unsigned int *)(a3 + 40),
        v13 = *(unsigned int *)(a3 + 36),
        ++*(_DWORD *)(a3 + 24),
        (v9 = (PSLIST_ENTRY)v11(v13, v10, v12)) != 0) )
  {
    v9[1].Next = a1;
    *((_WORD *)&v9[1].Next + 4) = *(_WORD *)a2;
    *((_WORD *)&v9[1].Next + 5) = *(_WORD *)(a2 + 2);
    v9[2].Next = *(struct _SLIST_ENTRY **)(a2 + 8);
    v14 = *a4;
    if ( *((PSLIST_ENTRY **)&(*a4)->Next + 1) != a4 )
      __fastfail(3u);
    v9->Next = v14;
    *((_QWORD *)&v9->Next + 1) = a4;
    *((_QWORD *)&v14->Next + 1) = v9;
    *a4 = v9;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v8;
}

```

## disassembly

```asm
0x14003ceec  mov     rax, rsp
0x14003ceef  mov     [rax+8], rbx
0x14003cef3  mov     [rax+10h], rbp
0x14003cef7  mov     [rax+18h], rsi
0x14003cefb  mov     [rax+20h], rdi
0x14003ceff  push    r14
0x14003cf01  sub     rsp, 20h
0x14003cf05  inc     dword ptr [r8+14h]
0x14003cf09  mov     rbp, rcx
0x14003cf0c  mov     rcx, r8; ListHead
0x14003cf0f  mov     rdi, r9
0x14003cf12  mov     rsi, r8
0x14003cf15  mov     r14, rdx
0x14003cf18  xor     ebx, ebx
0x14003cf1a  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003cf21  nop     dword ptr [rax+rax+00h]
0x14003cf26  mov     r10, rax
0x14003cf29  test    rax, rax
0x14003cf2c  jnz     short loc_14003CF54
0x14003cf2e  mov     edx, [rsi+2Ch]
0x14003cf31  mov     rax, [rsi+30h]
0x14003cf35  mov     r8d, [rsi+28h]
0x14003cf39  mov     ecx, [rsi+24h]
0x14003cf3c  inc     dword ptr [rsi+18h]
0x14003cf3f  call    cs:__guard_dispatch_icall_fptr
0x14003cf45  mov     r10, rax
0x14003cf48  test    rax, rax
0x14003cf4b  jnz     short loc_14003CF54
0x14003cf4d  mov     ebx, 0C000009Ah
0x14003cf52  jmp     short loc_14003CF91
0x14003cf54  mov     [r10+10h], rbp
0x14003cf58  movzx   eax, word ptr [r14]
0x14003cf5c  mov     [r10+18h], ax
0x14003cf61  movzx   eax, word ptr [r14+2]
0x14003cf66  mov     [r10+1Ah], ax
0x14003cf6b  mov     rax, [r14+8]
0x14003cf6f  mov     [r10+20h], rax
0x14003cf73  mov     rax, [rdi]
0x14003cf76  cmp     [rax+8], rdi
0x14003cf7a  jz      short loc_14003CF83
0x14003cf7c  mov     ecx, 3
0x14003cf81  int     29h; Win8: RtlFailFast(ecx)
0x14003cf83  mov     [r10], rax
0x14003cf86  mov     [r10+8], rdi
0x14003cf8a  mov     [rax+8], r10
0x14003cf8e  mov     [rdi], r10
0x14003cf91  mov     rbp, [rsp+28h+arg_8]
0x14003cf96  mov     eax, ebx
0x14003cf98  mov     rbx, [rsp+28h+arg_0]
0x14003cf9d  mov     rsi, [rsp+28h+arg_10]
0x14003cfa2  mov     rdi, [rsp+28h+arg_18]
0x14003cfa7  add     rsp, 20h
0x14003cfab  pop     r14
0x14003cfad  retn
```
