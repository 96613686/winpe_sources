# BfsLookupPolicyEntryHashTable

- ea: `0x140008e38`
- end: `0x140008ec3`
- name: `BfsLookupPolicyEntryHashTable`
- size: `139`
- prototype: `__int64 __fastcall(PRTL_DYNAMIC_HASH_TABLE HashTable)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140006db4`
- `0x140006eb0`
- `0x1400071d4`
- `0x1400073e0`
- `0x140007a20`
- `0x140007cf0`
- `0x140007fec`
- `0x140008728`
- `0x140009014`
- `0x1400092a4`
- `0x14000a64c`

## callees

- `0x140008e38`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x140008e5e`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140008e5e`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140008ea8`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x140008ea8`
- `ntoskrnl!RtlEqualSid` at `0x140008e79`
- `ntoskrnl!RtlEqualSid` at `0x140008e90`
- `ntoskrnl!RtlEqualSid` at `0x140008e79`
- `ntoskrnl!RtlEqualSid` at `0x140008e90`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsLookupPolicyEntryHashTable(
        PRTL_DYNAMIC_HASH_TABLE HashTable,
        ULONG_PTR a2,
        void *a3,
        void *a4)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v8; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF

  memset(&Context, 0, sizeof(Context));
  for ( result = RtlLookupEntryHashTable(HashTable, a2, &Context); ; result = RtlGetNextEntryHashTable(
                                                                                HashTable,
                                                                                &Context) )
  {
    v8 = result;
    if ( !result )
      break;
    if ( RtlEqualSid(a3, result[1].Linkage.Flink) && RtlEqualSid(a4, v8[1].Linkage.Blink) )
      return v8;
  }
  return result;
}

```

## disassembly

```asm
0x140008e38  push    rbx
0x140008e3a  push    rbp
0x140008e3b  push    rsi
0x140008e3c  push    rdi
0x140008e3d  sub     rsp, 48h
0x140008e41  mov     rbp, r8
0x140008e44  xorps   xmm0, xmm0
0x140008e47  xor     eax, eax
0x140008e49  lea     r8, [rsp+68h+Context]; Context
0x140008e4e  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x140008e53  mov     [rsp+68h+Context.Signature], rax
0x140008e58  mov     rsi, r9
0x140008e5b  mov     rdi, rcx
0x140008e5e  call    cs:__imp_RtlLookupEntryHashTable
0x140008e65  nop     dword ptr [rax+rax+00h]
0x140008e6a  mov     rbx, rax
0x140008e6d  test    rax, rax
0x140008e70  jz      short loc_140008EB9
0x140008e72  mov     rdx, [rax+18h]; Sid2
0x140008e76  mov     rcx, rbp; Sid1
0x140008e79  call    cs:__imp_RtlEqualSid
0x140008e80  nop     dword ptr [rax+rax+00h]
0x140008e85  test    al, al
0x140008e87  jz      short loc_140008EA0
0x140008e89  mov     rdx, [rbx+20h]; Sid2
0x140008e8d  mov     rcx, rsi; Sid1
0x140008e90  call    cs:__imp_RtlEqualSid
0x140008e97  nop     dword ptr [rax+rax+00h]
0x140008e9c  test    al, al
0x140008e9e  jnz     short loc_140008EB6
0x140008ea0  lea     rdx, [rsp+68h+Context]; Context
0x140008ea5  mov     rcx, rdi; HashTable
0x140008ea8  call    cs:__imp_RtlGetNextEntryHashTable
0x140008eaf  nop     dword ptr [rax+rax+00h]
0x140008eb4  jmp     short loc_140008E6A
0x140008eb6  mov     rax, rbx
0x140008eb9  add     rsp, 48h
0x140008ebd  pop     rdi
0x140008ebe  pop     rsi
0x140008ebf  pop     rbp
0x140008ec0  pop     rbx
0x140008ec1  retn
```
