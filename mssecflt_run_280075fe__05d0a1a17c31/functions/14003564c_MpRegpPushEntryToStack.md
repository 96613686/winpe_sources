# MpRegpPushEntryToStack

- ea: `0x14003564c`
- end: `0x140035719`
- name: `MpRegpPushEntryToStack`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140035480`
- `0x1400359b0`

## callees

- `0x140011610`
- `0x14003564c`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140035684`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140035684`

## pseudocode

```c
__int64 __fastcall MpRegpPushEntryToStack(PSLIST_ENTRY *a1, struct _SLIST_ENTRY *a2, __int64 a3)
{
  char *v4; // rsi
  union _SLIST_HEADER *v6; // rcx
  unsigned int v8; // edi
  PSLIST_ENTRY v9; // r9
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(__int64, __int64, __int64); // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  PSLIST_ENTRY v14; // rax

  v4 = (char *)RegData + 640;
  v6 = (union _SLIST_HEADER *)((char *)RegData + 640);
  v8 = 0;
  ++*((_DWORD *)RegData + 165);
  v9 = ExpInterlockedPopEntrySList(v6);
  if ( v9
    || (v10 = *((unsigned int *)v4 + 11),
        v11 = (__int64 (__fastcall *)(__int64, __int64, __int64))*((_QWORD *)v4 + 6),
        v12 = *((unsigned int *)v4 + 10),
        v13 = *((unsigned int *)v4 + 9),
        ++*((_DWORD *)v4 + 6),
        (v9 = (PSLIST_ENTRY)v11(v13, v10, v12)) != 0) )
  {
    v9[1].Next = a2;
    *((_WORD *)&v9[1].Next + 4) = *(_WORD *)a3;
    *((_WORD *)&v9[1].Next + 5) = *(_WORD *)(a3 + 2);
    v9[2].Next = *(struct _SLIST_ENTRY **)(a3 + 8);
    v14 = *a1;
    if ( *((PSLIST_ENTRY **)&(*a1)->Next + 1) != a1 )
      __fastfail(3u);
    v9->Next = v14;
    *((_QWORD *)&v9->Next + 1) = a1;
    *((_QWORD *)&v14->Next + 1) = v9;
    *a1 = v9;
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
0x14003564c  mov     rax, rsp
0x14003564f  mov     [rax+8], rbx
0x140035653  mov     [rax+10h], rbp
0x140035657  mov     [rax+18h], rsi
0x14003565b  mov     [rax+20h], rdi
0x14003565f  push    r14
0x140035661  sub     rsp, 20h
0x140035665  mov     rsi, cs:RegData
0x14003566c  mov     rbx, rcx
0x14003566f  add     rsi, 280h
0x140035676  mov     r14, r8
0x140035679  mov     rcx, rsi; ListHead
0x14003567c  mov     rbp, rdx
0x14003567f  xor     edi, edi
0x140035681  inc     dword ptr [rsi+14h]
0x140035684  call    cs:__imp_ExpInterlockedPopEntrySList
0x14003568b  nop     dword ptr [rax+rax+00h]
0x140035690  mov     r9, rax
0x140035693  test    rax, rax
0x140035696  jnz     short loc_1400356BE
0x140035698  mov     edx, [rsi+2Ch]
0x14003569b  mov     rax, [rsi+30h]
0x14003569f  mov     r8d, [rsi+28h]
0x1400356a3  mov     ecx, [rsi+24h]
0x1400356a6  inc     dword ptr [rsi+18h]
0x1400356a9  call    cs:__guard_dispatch_icall_fptr
0x1400356af  mov     r9, rax
0x1400356b2  test    rax, rax
0x1400356b5  jnz     short loc_1400356BE
0x1400356b7  mov     edi, 0C000009Ah
0x1400356bc  jmp     short loc_1400356FB
0x1400356be  mov     [r9+10h], rbp
0x1400356c2  movzx   eax, word ptr [r14]
0x1400356c6  mov     [r9+18h], ax
0x1400356cb  movzx   eax, word ptr [r14+2]
0x1400356d0  mov     [r9+1Ah], ax
0x1400356d5  mov     rax, [r14+8]
0x1400356d9  mov     [r9+20h], rax
0x1400356dd  mov     rax, [rbx]
0x1400356e0  cmp     [rax+8], rbx
0x1400356e4  jz      short loc_1400356ED
0x1400356e6  mov     ecx, 3
0x1400356eb  int     29h; Win8: RtlFailFast(ecx)
0x1400356ed  mov     [r9], rax
0x1400356f0  mov     [r9+8], rbx
0x1400356f4  mov     [rax+8], r9
0x1400356f8  mov     [rbx], r9
0x1400356fb  mov     rbx, [rsp+28h+arg_0]
0x140035700  mov     eax, edi
0x140035702  mov     rdi, [rsp+28h+arg_18]
0x140035707  mov     rbp, [rsp+28h+arg_8]
0x14003570c  mov     rsi, [rsp+28h+arg_10]
0x140035711  add     rsp, 20h
0x140035715  pop     r14
0x140035717  retn
```
