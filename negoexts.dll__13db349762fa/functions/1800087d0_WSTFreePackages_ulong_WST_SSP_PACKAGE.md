# WSTFreePackages(ulong *,_WST_SSP_PACKAGE * *)

- ea: `0x1800087d0`
- end: `0x18000886e`
- name: `?WSTFreePackages@@YAXPEAKPEAPEAU_WST_SSP_PACKAGE@@@Z`
- size: `158`
- prototype: `void __fastcall(unsigned int *, struct _WST_SSP_PACKAGE **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001414`
- `0x1800085c0`
- `0x180008880`
- `0x180008ca0`
- `0x180008e60`

## callees

- `0x1800087d0`
- `0x180008c58`
- `0x180020010`

## pseudocode

```c
void __fastcall WSTFreePackages(unsigned int *a1, struct _WST_SSP_PACKAGE **a2)
{
  unsigned int i; // ebx
  struct _WST_SSP_PACKAGE *v5; // rcx
  basessp::BaseSSP *v6; // rax

  if ( a2 )
  {
    for ( i = 0; i < *a1; ++i )
    {
      v5 = a2[i];
      if ( v5 )
      {
        WSTDereferencePackage(v5);
        a2[i] = 0;
      }
    }
    v6 = WSTGlobalBaseSSP;
    *a1 = 0;
    if ( *((_DWORD *)v6 + 52) == 1 )
      (*(void (__fastcall **)(struct _WST_SSP_PACKAGE **))(*((_QWORD *)v6 + 30) + 392LL))(a2);
    else
      (*(void (__fastcall **)(struct _WST_SSP_PACKAGE **))(*((_QWORD *)v6 + 31) + 8LL))(a2);
  }
}

```

## disassembly

```asm
0x1800087d0  test    rdx, rdx
0x1800087d3  jz      locret_180008860
0x1800087d9  mov     [rsp+arg_18], rsi
0x1800087de  push    r14
0x1800087e0  sub     rsp, 20h
0x1800087e4  mov     [rsp+28h+arg_0], rbx
0x1800087e9  mov     r14, rdx
0x1800087ec  mov     [rsp+28h+arg_8], rbp
0x1800087f1  mov     rsi, rcx
0x1800087f4  xor     ebp, ebp
0x1800087f6  mov     ebx, ebp
0x1800087f8  cmp     [rcx], ebx
0x1800087fa  jbe     short loc_180008823
0x1800087fc  mov     [rsp+28h+arg_10], rdi
0x180008801  mov     eax, ebx
0x180008803  mov     rcx, [r14+rax*8]; struct _WST_SSP_PACKAGE *
0x180008807  lea     rdi, [r14+rax*8]
0x18000880b  test    rcx, rcx
0x18000880e  jz      short loc_180008818
0x180008810  call    ?WSTDereferencePackage@@YAXPEAU_WST_SSP_PACKAGE@@@Z; WSTDereferencePackage(_WST_SSP_PACKAGE *)
0x180008815  mov     [rdi], rbp
0x180008818  inc     ebx
0x18000881a  cmp     ebx, [rsi]
0x18000881c  jb      short loc_180008801
0x18000881e  mov     rdi, [rsp+28h+arg_10]
0x180008823  mov     rax, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * WSTGlobalBaseSSP
0x18000882a  mov     rcx, r14
0x18000882d  mov     rbx, [rsp+28h+arg_0]
0x180008832  mov     [rsi], ebp
0x180008834  mov     rbp, [rsp+28h+arg_8]
0x180008839  cmp     dword ptr [rax+0D0h], 1
0x180008840  jnz     short loc_180008861
0x180008842  mov     rax, [rax+0F0h]
0x180008849  mov     rax, [rax+188h]
0x180008850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008855  mov     rsi, [rsp+28h+arg_18]
0x18000885a  add     rsp, 20h
0x18000885e  pop     r14
0x180008860  retn
0x180008861  mov     rax, [rax+0F8h]
0x180008868  mov     rax, [rax+8]
0x18000886c  jmp     short loc_180008850
```
