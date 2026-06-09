# DereferenceAf

- ea: `0x140001920`
- end: `0x14000197f`
- name: `DereferenceAf`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001d60`
- `0x1400021c0`

## callees

- `0x140001920`
- `0x14001d39c`

## import_xrefs

- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x14000194a`
- `NDIS!NdisCmCloseAddressFamilyComplete` at `0x14000194a`

## pseudocode

```c
void __fastcall DereferenceAf(__int64 a1)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 376), 0xFFFFFFFF) == 1 )
  {
    NdisCmCloseAddressFamilyComplete(0, *(NDIS_HANDLE *)(a1 + 352));
    _InterlockedExchange64((volatile __int64 *)(a1 + 352), 0);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4), 0xFFFFFFFF) == 1 )
      FreeAdapter(a1);
  }
}

```

## disassembly

```asm
0x140001920  mov     [rsp+arg_8], rbx
0x140001925  push    rdi
0x140001926  sub     rsp, 20h
0x14000192a  mov     edi, 0FFFFFFFFh
0x14000192f  mov     rbx, rcx
0x140001932  mov     eax, edi
0x140001934  lock xadd [rcx+178h], eax
0x14000193c  cmp     eax, 1
0x14000193f  jnz     short loc_140001969
0x140001941  mov     rdx, [rcx+160h]; NdisAfHandle
0x140001948  xor     ecx, ecx; Status
0x14000194a  call    cs:__imp_NdisCmCloseAddressFamilyComplete
0x140001951  nop     dword ptr [rax+rax+00h]
0x140001956  xor     eax, eax
0x140001958  xchg    rax, [rbx+160h]
0x14000195f  lock xadd [rbx+4], edi
0x140001964  cmp     edi, 1
0x140001967  jz      short loc_140001975
0x140001969  mov     rbx, [rsp+28h+arg_8]
0x14000196e  add     rsp, 20h
0x140001972  pop     rdi
0x140001973  retn
0x140001975  mov     rcx, rbx
0x140001978  call    FreeAdapter
0x14000197d  jmp     short loc_140001969
```
