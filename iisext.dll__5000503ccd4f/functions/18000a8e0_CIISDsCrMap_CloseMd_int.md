# CIISDsCrMap::CloseMd(int)

- ea: `0x18000a8e0`
- end: `0x18000a944`
- name: `?CloseMd@CIISDsCrMap@@QEAAJH@Z`
- size: `100`
- prototype: `__int64 __fastcall(CIISDsCrMap *__hidden this, int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000b22c`
- `0x18000b6b0`
- `0x18000b7a8`
- `0x18000bd80`
- `0x18000c0ac`
- `0x18000d4c0`
- `0x18000d5dc`
- `0x18000d81c`
- `0x18000d930`

## callees

- `0x18000a8e0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::CloseMd(CIISDsCrMap *this, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx

  v4 = *((_QWORD *)this + 7);
  if ( v4 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 144LL))(v4, *((unsigned int *)this + 16));
  v5 = *((_QWORD *)this + 7);
  *((_DWORD *)this + 16) = 0;
  if ( v5 && a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 160LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18000a8e0  mov     [rsp+arg_0], rbx
0x18000a8e5  mov     [rsp+arg_8], rsi
0x18000a8ea  push    rdi
0x18000a8eb  sub     rsp, 20h
0x18000a8ef  mov     rdi, rcx
0x18000a8f2  mov     esi, edx
0x18000a8f4  mov     rcx, [rcx+38h]
0x18000a8f8  test    rcx, rcx
0x18000a8fb  jz      short loc_18000A90F
0x18000a8fd  mov     rax, [rcx]
0x18000a900  mov     edx, [rdi+40h]
0x18000a903  mov     rax, [rax+90h]
0x18000a90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a90f  mov     rcx, [rdi+38h]
0x18000a913  mov     dword ptr [rdi+40h], 0
0x18000a91a  test    rcx, rcx
0x18000a91d  jz      short loc_18000A932
0x18000a91f  test    esi, esi
0x18000a921  jz      short loc_18000A932
0x18000a923  mov     rax, [rcx]
0x18000a926  mov     rax, [rax+0A0h]
0x18000a92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a932  mov     rbx, [rsp+28h+arg_0]
0x18000a937  xor     eax, eax
0x18000a939  mov     rsi, [rsp+28h+arg_8]
0x18000a93e  add     rsp, 20h
0x18000a942  pop     rdi
0x18000a943  retn
```
