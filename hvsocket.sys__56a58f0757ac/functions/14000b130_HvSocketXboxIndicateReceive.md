# HvSocketXboxIndicateReceive

- ea: `0x14000b130`
- end: `0x14000b20b`
- name: `HvSocketXboxIndicateReceive`
- size: `219`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140003890`
- `0x14000975c`
- `0x14000b130`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000b152`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000b152`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b1f1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000b1f1`

## pseudocode

```c
__int64 __fastcall HvSocketXboxIndicateReceive(__int64 a1, __int64 a2, int a3, unsigned int a4, __int64 a5)
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
        HvsocketTraceEndpointError((const int *)"HvSocketXboxIndicateReceive", 1101, 3221225495LL, a1);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a1 + 112) + 704LL), v10);
    }
    return (unsigned int)v12;
  }
  else
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError((const int *)"HvSocketXboxIndicateReceive", 1087, 3221225495LL, a1);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x14000b130  push    rbx
0x14000b132  push    rbp
0x14000b133  push    rsi
0x14000b134  push    rdi
0x14000b135  push    r14
0x14000b137  sub     rsp, 20h
0x14000b13b  mov     rdi, rcx
0x14000b13e  mov     esi, r9d
0x14000b141  mov     rcx, [rcx+70h]
0x14000b145  mov     ebp, r8d
0x14000b148  add     rcx, 2C0h; Lookaside
0x14000b14f  mov     r14, rdx
0x14000b152  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000b159  nop     dword ptr [rax+rax+00h]
0x14000b15e  mov     rbx, rax
0x14000b161  test    rax, rax
0x14000b164  jnz     short loc_14000B192
0x14000b166  mov     edx, cs:dword_140013058
0x14000b16c  cmp     edx, 2
0x14000b16f  jbe     short loc_14000B18B
0x14000b171  mov     r9, rdi
0x14000b174  lea     rcx, aHvsocketxboxin; "HvSocketXboxIndicateReceive"
0x14000b17b  mov     edx, 43Fh
0x14000b180  mov     r8d, 0C0000017h
0x14000b186  call    HvsocketTraceEndpointError
0x14000b18b  mov     eax, 0C0000017h
0x14000b190  jmp     short loc_14000B1FF
0x14000b192  mov     qword ptr [rax], 0
0x14000b199  mov     rdx, rbx
0x14000b19c  mov     [rax+8], r14
0x14000b1a0  mov     rcx, rdi
0x14000b1a3  mov     [rax+10h], ebp
0x14000b1a6  mov     [rax+18h], rsi
0x14000b1aa  mov     rax, [rsp+48h+arg_20]
0x14000b1af  mov     [rbx+48h], rax
0x14000b1b3  call    VmbusTlQueueAndDeliverData
0x14000b1b8  mov     esi, eax
0x14000b1ba  test    eax, eax
0x14000b1bc  jns     short loc_14000B1FD
0x14000b1be  mov     ecx, cs:dword_140013058
0x14000b1c4  cmp     ecx, 2
0x14000b1c7  jbe     short loc_14000B1E3
0x14000b1c9  mov     r9, rdi
0x14000b1cc  lea     rcx, aHvsocketxboxin; "HvSocketXboxIndicateReceive"
0x14000b1d3  mov     edx, 44Dh
0x14000b1d8  mov     r8d, 0C0000017h
0x14000b1de  call    HvsocketTraceEndpointError
0x14000b1e3  mov     rcx, [rdi+70h]
0x14000b1e7  mov     rdx, rbx; Entry
0x14000b1ea  add     rcx, 2C0h; Lookaside
0x14000b1f1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000b1f8  nop     dword ptr [rax+rax+00h]
0x14000b1fd  mov     eax, esi
0x14000b1ff  add     rsp, 20h
0x14000b203  pop     r14
0x14000b205  pop     rdi
0x14000b206  pop     rsi
0x14000b207  pop     rbp
0x14000b208  pop     rbx
0x14000b209  retn
```
