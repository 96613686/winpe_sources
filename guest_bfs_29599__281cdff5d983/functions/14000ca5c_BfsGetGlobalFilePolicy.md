# BfsGetGlobalFilePolicy

- ea: `0x14000ca5c`
- end: `0x14000cb2d`
- name: `BfsGetGlobalFilePolicy`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d734`
- `0x14000d9dc`

## callees

- `0x1400017b0`
- `0x14000ca5c`
- `0x140012d00`

## import_xrefs

- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000cac8`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000cac8`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000cb12`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000cb12`
- `ntoskrnl!RtlEqualSid` at `0x14000cae3`
- `ntoskrnl!RtlEqualSid` at `0x14000cafa`
- `ntoskrnl!RtlEqualSid` at `0x14000cae3`
- `ntoskrnl!RtlEqualSid` at `0x14000cafa`

## pseudocode

```c
PRTL_DYNAMIC_HASH_TABLE_ENTRY __fastcall BfsGetGlobalFilePolicy(__int64 a1, unsigned __int8 *a2, unsigned __int8 *a3)
{
  struct _RTL_DYNAMIC_HASH_TABLE *v3; // rbp
  int v5; // edx
  ULONG_PTR v7; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY result; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v9; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 88);
  v5 = a2[1];
  v11 = 0;
  memset(&Context, 0, sizeof(Context));
  BfsUpdateHash(a2, (unsigned int)(4 * v5 + 8), &v11);
  BfsUpdateHash(a3, 4 * (unsigned int)a3[1] + 8, &v11);
  v7 = BfsFinalHash(&v11);
  for ( result = RtlLookupEntryHashTable(v3, v7, &Context); ; result = RtlGetNextEntryHashTable(v3, &Context) )
  {
    v9 = result;
    if ( !result )
      break;
    if ( RtlEqualSid(a2, result[1].Linkage.Flink) && RtlEqualSid(a3, v9[1].Linkage.Blink) )
      return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14000ca5c  push    rbx
0x14000ca5e  push    rbp
0x14000ca5f  push    rsi
0x14000ca60  push    rdi
0x14000ca61  sub     rsp, 48h
0x14000ca65  mov     rbp, [rcx+58h]
0x14000ca69  mov     rsi, rdx
0x14000ca6c  movzx   edx, byte ptr [rdx+1]
0x14000ca70  xor     eax, eax
0x14000ca72  mov     rdi, r8
0x14000ca75  mov     [rsp+68h+Context.Signature], rax
0x14000ca7a  xorps   xmm0, xmm0
0x14000ca7d  mov     [rsp+68h+arg_0], rax
0x14000ca82  lea     r8, [rsp+68h+arg_0]
0x14000ca87  mov     rcx, rsi
0x14000ca8a  lea     edx, ds:8[rdx*4]
0x14000ca91  movups  xmmword ptr [rsp+68h+Context.ChainHead], xmm0
0x14000ca96  call    BfsUpdateHash
0x14000ca9b  movzx   edx, byte ptr [rdi+1]
0x14000ca9f  lea     r8, [rsp+68h+arg_0]
0x14000caa4  mov     rcx, rdi
0x14000caa7  lea     edx, ds:8[rdx*4]
0x14000caae  call    BfsUpdateHash
0x14000cab3  lea     rcx, [rsp+68h+arg_0]
0x14000cab8  call    BfsFinalHash
0x14000cabd  mov     rdx, rax; Signature
0x14000cac0  lea     r8, [rsp+68h+Context]; Context
0x14000cac5  mov     rcx, rbp; HashTable
0x14000cac8  call    cs:__imp_RtlLookupEntryHashTable
0x14000cacf  nop     dword ptr [rax+rax+00h]
0x14000cad4  mov     rbx, rax
0x14000cad7  test    rax, rax
0x14000cada  jz      short loc_14000CB23
0x14000cadc  mov     rdx, [rax+18h]; Sid2
0x14000cae0  mov     rcx, rsi; Sid1
0x14000cae3  call    cs:__imp_RtlEqualSid
0x14000caea  nop     dword ptr [rax+rax+00h]
0x14000caef  test    al, al
0x14000caf1  jz      short loc_14000CB0A
0x14000caf3  mov     rdx, [rbx+20h]; Sid2
0x14000caf7  mov     rcx, rdi; Sid1
0x14000cafa  call    cs:__imp_RtlEqualSid
0x14000cb01  nop     dword ptr [rax+rax+00h]
0x14000cb06  test    al, al
0x14000cb08  jnz     short loc_14000CB20
0x14000cb0a  lea     rdx, [rsp+68h+Context]; Context
0x14000cb0f  mov     rcx, rbp; HashTable
0x14000cb12  call    cs:__imp_RtlGetNextEntryHashTable
0x14000cb19  nop     dword ptr [rax+rax+00h]
0x14000cb1e  jmp     short loc_14000CAD4
0x14000cb20  mov     rax, rbx
0x14000cb23  add     rsp, 48h
0x14000cb27  pop     rdi
0x14000cb28  pop     rsi
0x14000cb29  pop     rbp
0x14000cb2a  pop     rbx
0x14000cb2b  retn
```
