# _attributes_array_t::SetCount(ulong)

- ea: `0x18000ef4c`
- end: `0x18000efba`
- name: `?SetCount@_attributes_array_t@@QEAAJK@Z`
- size: `110`
- prototype: `__int64 __fastcall(LPVOID *this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d274`
- `0x180017c3c`

## callees

- `0x18000d458`
- `0x18000ef4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ef7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _attributes_array_t::SetCount(LPVOID *this, unsigned int a2)
{
  __int64 v2; // rdi
  __int64 v5; // rbx
  _BYTE *v6; // rax

  v2 = a2;
  if ( a2 > 0x1C71C71 )
    return 2147942934LL;
  _attributes_array_t::FreeAll(this);
  v5 = 144 * v2;
  v6 = CoTaskMemAlloc(144 * v2);
  this[1] = v6;
  if ( !v6 )
    return 2147942414LL;
  for ( ; v5; --v5 )
    *v6++ = 0;
  *(_DWORD *)this = v2;
  return 0;
}

```

## disassembly

```asm
0x18000ef4c  mov     [rsp+arg_0], rbx
0x18000ef51  mov     [rsp+arg_8], rsi
0x18000ef56  push    rdi
0x18000ef57  sub     rsp, 20h
0x18000ef5b  mov     edi, edx
0x18000ef5d  mov     rsi, rcx
0x18000ef60  cmp     edx, 1C71C71h
0x18000ef66  jbe     short loc_18000EF6F
0x18000ef68  mov     eax, 80070216h
0x18000ef6d  jmp     short loc_18000EFAA
0x18000ef6f  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x18000ef74  lea     rbx, [rdi+rdi*8]
0x18000ef78  shl     rbx, 4
0x18000ef7c  mov     rcx, rbx; cb
0x18000ef7f  call    cs:__imp_CoTaskMemAlloc
0x18000ef85  mov     [rsi+8], rax
0x18000ef89  test    rax, rax
0x18000ef8c  jnz     short loc_18000EF95
0x18000ef8e  mov     eax, 8007000Eh
0x18000ef93  jmp     short loc_18000EFAA
0x18000ef95  test    rbx, rbx
0x18000ef98  jz      short loc_18000EFA6
0x18000ef9a  mov     byte ptr [rax], 0
0x18000ef9d  inc     rax
0x18000efa0  sub     rbx, 1
0x18000efa4  jnz     short loc_18000EF9A
0x18000efa6  mov     [rsi], edi
0x18000efa8  xor     eax, eax
0x18000efaa  mov     rbx, [rsp+28h+arg_0]
0x18000efaf  mov     rsi, [rsp+28h+arg_8]
0x18000efb4  add     rsp, 20h
0x18000efb8  pop     rdi
0x18000efb9  retn
```
