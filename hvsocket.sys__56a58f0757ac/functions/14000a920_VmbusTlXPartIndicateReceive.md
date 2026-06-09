# VmbusTlXPartIndicateReceive

- ea: `0x14000a920`
- end: `0x14000a9fb`
- name: `VmbusTlXPartIndicateReceive`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140003890`
- `0x14000975c`
- `0x14000a920`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a942`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000a942`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a9e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000a9e1`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartIndicateReceive(__int64 a1, __int64 a2, int a3, unsigned int a4, __int64 a5)
{
  __int64 v6; // rsi
  _QWORD *v9; // rax
  void *v10; // rbx
  int v12; // esi

  v6 = a4;
  v9 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 112) + 704LL));
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = a2;
    *((_DWORD *)v9 + 4) = a3;
    v9[3] = v6;
    v9[9] = a5;
    v12 = VmbusTlQueueAndDeliverData(a1, v9);
    if ( v12 < 0 )
    {
      if ( (unsigned int)dword_140013058 > 2 )
        HvsocketTraceEndpointError((const int *)"VmbusTlXPartIndicateReceive", 1261, 3221225495LL, a1);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 112) + 704LL), v10);
    }
    return (unsigned int)v12;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError((const int *)"VmbusTlXPartIndicateReceive", 1247, 3221225495LL, a1);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14000a920  push    rbx
0x14000a922  push    rbp
0x14000a923  push    rsi
0x14000a924  push    rdi
0x14000a925  push    r14
0x14000a927  sub     rsp, 20h
0x14000a92b  mov     rdi, rcx
0x14000a92e  mov     esi, r9d
0x14000a931  mov     rcx, [rcx+70h]
0x14000a935  mov     ebp, r8d
0x14000a938  add     rcx, 2C0h; Lookaside
0x14000a93f  mov     r14, rdx
0x14000a942  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000a949  nop     dword ptr [rax+rax+00h]
0x14000a94e  mov     rbx, rax
0x14000a951  test    rax, rax
0x14000a954  jnz     short loc_14000A982
0x14000a956  mov     edx, cs:dword_140013058
0x14000a95c  cmp     edx, 2
0x14000a95f  jbe     short loc_14000A97B
0x14000a961  mov     r9, rdi
0x14000a964  lea     rcx, aVmbustlxpartin; "VmbusTlXPartIndicateReceive"
0x14000a96b  mov     edx, 4DFh
0x14000a970  mov     r8d, 0C0000017h
0x14000a976  call    HvsocketTraceEndpointError
0x14000a97b  mov     eax, 0C0000017h
0x14000a980  jmp     short loc_14000A9EF
0x14000a982  mov     qword ptr [rax], 0
0x14000a989  mov     rdx, rbx
0x14000a98c  mov     [rax+8], r14
0x14000a990  mov     rcx, rdi
0x14000a993  mov     [rax+10h], ebp
0x14000a996  mov     [rax+18h], rsi
0x14000a99a  mov     rax, [rsp+48h+arg_20]
0x14000a99f  mov     [rbx+48h], rax
0x14000a9a3  call    VmbusTlQueueAndDeliverData
0x14000a9a8  mov     esi, eax
0x14000a9aa  test    eax, eax
0x14000a9ac  jns     short loc_14000A9ED
0x14000a9ae  mov     ecx, cs:dword_140013058
0x14000a9b4  cmp     ecx, 2
0x14000a9b7  jbe     short loc_14000A9D3
0x14000a9b9  mov     r9, rdi
0x14000a9bc  lea     rcx, aVmbustlxpartin; "VmbusTlXPartIndicateReceive"
0x14000a9c3  mov     edx, 4EDh
0x14000a9c8  mov     r8d, 0C0000017h
0x14000a9ce  call    HvsocketTraceEndpointError
0x14000a9d3  mov     rcx, [rdi+70h]
0x14000a9d7  mov     rdx, rbx; Entry
0x14000a9da  add     rcx, 2C0h; Lookaside
0x14000a9e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000a9e8  nop     dword ptr [rax+rax+00h]
0x14000a9ed  mov     eax, esi
0x14000a9ef  add     rsp, 20h
0x14000a9f3  pop     r14
0x14000a9f5  pop     rdi
0x14000a9f6  pop     rsi
0x14000a9f7  pop     rbp
0x14000a9f8  pop     rbx
0x14000a9f9  retn
```
