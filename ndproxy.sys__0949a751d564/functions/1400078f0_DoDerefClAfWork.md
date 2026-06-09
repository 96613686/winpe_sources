# DoDerefClAfWork

- ea: `0x1400078f0`
- end: `0x14000793a`
- name: `DoDerefClAfWork`
- size: `74`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400011b0`
- `0x140002100`
- `0x140002fd0`
- `0x140003940`
- `0x14000f750`
- `0x1400100b0`
- `0x140011850`
- `0x140014ca0`
- `0x1400156d8`

## callees

- `0x140001030`
- `0x1400078f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140007906`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007906`
- `NDIS!NdisClCloseAddressFamily` at `0x140007916`
- `NDIS!NdisClCloseAddressFamily` at `0x140007916`

## pseudocode

```c
NDIS_STATUS __fastcall DoDerefClAfWork(__int64 a1)
{
  NDIS_STATUS result; // eax

  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 184), *(_BYTE *)(a1 + 192));
  result = NdisClCloseAddressFamily(*(NDIS_HANDLE *)(a1 + 24));
  if ( result != 259 )
    return PxClCloseAfComplete(result, (void *)a1);
  return result;
}

```

## disassembly

```asm
0x1400078f0  push    rbx
0x1400078f2  sub     rsp, 20h
0x1400078f6  mov     rbx, rcx
0x1400078f9  add     rcx, 0B8h; SpinLock
0x140007900  mov     dl, [rbx+0C0h]; NewIrql
0x140007906  call    cs:__imp_KeReleaseSpinLock
0x14000790d  nop     dword ptr [rax+rax+00h]
0x140007912  mov     rcx, [rbx+18h]; NdisAfHandle
0x140007916  call    cs:__imp_NdisClCloseAddressFamily
0x14000791d  nop     dword ptr [rax+rax+00h]
0x140007922  cmp     eax, 103h
0x140007927  jz      short loc_140007933
0x140007929  mov     rdx, rbx
0x14000792c  mov     ecx, eax
0x14000792e  call    PxClCloseAfComplete
0x140007933  add     rsp, 20h
0x140007937  pop     rbx
0x140007938  retn
```
