# CEventFactory::ReserveBufferSpace(void)

- ea: `0x18001ec50`
- end: `0x18001ec89`
- name: `?ReserveBufferSpace@CEventFactory@@QEAAPEAEXZ`
- size: `57`
- prototype: `unsigned __int8 *__fastcall(CEventFactory *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800125c8`
- `0x180018b28`

## callees

- `0x18001ec50`
- `0x180020c98`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001ec58`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x18001ec58`

## pseudocode

```c
unsigned __int8 *__fastcall CEventFactory::ReserveBufferSpace(union _SLIST_HEADER *this)
{
  unsigned __int8 *result; // rax

  result = (unsigned __int8 *)InterlockedPopEntrySList(this + 7);
  if ( !result )
  {
    result = (unsigned __int8 *)operator new[](0x10013u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !result )
      return result;
    *((_DWORD *)result + 4) = 0xFFFF;
  }
  result += 20;
  return result;
}

```

## disassembly

```asm
0x18001ec50  sub     rsp, 28h
0x18001ec54  add     rcx, 70h ; 'p'; ListHead
0x18001ec58  call    cs:__imp_InterlockedPopEntrySList
0x18001ec5e  test    rax, rax
0x18001ec61  jnz     short loc_18001EC80
0x18001ec63  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ec6a  mov     ecx, 10013h; unsigned __int64
0x18001ec6f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001ec74  test    rax, rax
0x18001ec77  jz      short loc_18001EC84
0x18001ec79  mov     dword ptr [rax+10h], 0FFFFh
0x18001ec80  add     rax, 14h
0x18001ec84  add     rsp, 28h
0x18001ec88  retn
```
