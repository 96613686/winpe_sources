# LcmCmCloseAf

- ea: `0x1400018a0`
- end: `0x140001914`
- name: `LcmCmCloseAf`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400018a0`
- `0x14001d39c`

## import_xrefs

- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x1400018d3`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x1400018d3`

## pseudocode

```c
__int64 __fastcall LcmCmCloseAf(__int64 a1)
{
  if ( *(_DWORD *)a1 != 827601484 )
    return 3221291029LL;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 376), 0xFFFFFFFF) == 1 )
  {
    NdisCmCloseAddressFamilyComplete(0, *(NDIS_HANDLE *)(a1 + 352));
    _InterlockedExchange64((volatile __int64 *)(a1 + 352), 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
      FreeAdapter(a1);
  }
  return 259;
}

```

## disassembly

```asm
0x1400018a0  push    rbx
0x1400018a2  sub     rsp, 20h
0x1400018a6  cmp     dword ptr [rcx], 3154324Ch
0x1400018ac  mov     rbx, rcx
0x1400018af  jnz     short loc_140001903
0x1400018b1  mov     [rsp+28h+arg_8], rdi
0x1400018b6  mov     edi, 0FFFFFFFFh
0x1400018bb  mov     eax, edi
0x1400018bd  lock xadd [rcx+178h], eax
0x1400018c5  cmp     eax, 1
0x1400018c8  jnz     short loc_1400018F2
0x1400018ca  mov     rdx, [rcx+160h]; NdisAfHandle
0x1400018d1  xor     ecx, ecx; Status
0x1400018d3  call    cs:__imp_NdisCmCloseAddressFamilyComplete
0x1400018da  nop     dword ptr [rax+rax+00h]
0x1400018df  xor     eax, eax
0x1400018e1  xchg    rax, [rbx+160h]
0x1400018e8  lock xadd [rbx+4], edi
0x1400018ed  cmp     edi, 1
0x1400018f0  jz      short loc_14000190A
0x1400018f2  mov     rdi, [rsp+28h+arg_8]
0x1400018f7  mov     eax, 103h
0x1400018fc  add     rsp, 20h
0x140001900  pop     rbx
0x140001901  retn
0x140001903  mov     eax, 0C0010015h
0x140001908  jmp     short loc_1400018FC
0x14000190a  mov     rcx, rbx
0x14000190d  call    FreeAdapter
0x140001912  jmp     short loc_1400018F2
```
