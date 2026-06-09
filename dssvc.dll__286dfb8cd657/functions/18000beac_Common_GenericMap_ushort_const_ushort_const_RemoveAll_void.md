# Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)

- ea: `0x18000beac`
- end: `0x18000bf21`
- name: `?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ`
- size: `117`
- prototype: `__int64 __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bd38`

## callees

- `0x18000beac`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000bee7`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000bee7`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18000becf`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18000becf`

## pseudocode

```c
__int64 *__fastcall Common::GenericMap<unsigned short const *,unsigned short const *>::RemoveAll(PRTL_AVL_TABLE Table)
{
  __int64 *result; // rax
  __int64 v3; // rdi
  __int64 v4; // rsi
  struct _RTL_BALANCED_LINKS *Parent; // rax
  struct _RTL_BALANCED_LINKS *LeftChild; // rax
  PVOID RestartKey; // [rsp+30h] [rbp+8h] BYREF

  while ( 1 )
  {
    RestartKey = 0;
    result = (__int64 *)RtlEnumerateGenericTableWithoutSplayingAvl(Table, &RestartKey);
    if ( !result )
      break;
    v3 = *result;
    v4 = result[1];
    RtlDeleteElementGenericTableAvl(Table, result);
    Parent = Table[1].BalancedRoot.Parent;
    if ( Parent )
      ((void (__fastcall *)(__int64))Parent)(v3);
    LeftChild = Table[1].BalancedRoot.LeftChild;
    if ( LeftChild )
      ((void (__fastcall *)(__int64))LeftChild)(v4);
  }
  return result;
}

```

## disassembly

```asm
0x18000beac  mov     [rsp+arg_8], rbx
0x18000beb1  mov     [rsp+arg_10], rsi
0x18000beb6  push    rdi
0x18000beb7  sub     rsp, 20h
0x18000bebb  mov     rbx, rcx
0x18000bebe  lea     rdx, [rsp+28h+RestartKey]; RestartKey
0x18000bec3  mov     [rsp+28h+RestartKey], 0
0x18000becc  mov     rcx, rbx; Table
0x18000becf  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18000bed5  test    rax, rax
0x18000bed8  jz      short loc_18000BF11
0x18000beda  mov     rdi, [rax]
0x18000bedd  mov     rdx, rax; Buffer
0x18000bee0  mov     rsi, [rax+8]
0x18000bee4  mov     rcx, rbx; Table
0x18000bee7  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000beed  mov     rax, [rbx+68h]
0x18000bef1  test    rax, rax
0x18000bef4  jz      short loc_18000BEFE
0x18000bef6  mov     rcx, rdi
0x18000bef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befe  mov     rax, [rbx+70h]
0x18000bf02  test    rax, rax
0x18000bf05  jz      short loc_18000BEBE
0x18000bf07  mov     rcx, rsi
0x18000bf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf0f  jmp     short loc_18000BEBE
0x18000bf11  mov     rbx, [rsp+28h+arg_8]
0x18000bf16  mov     rsi, [rsp+28h+arg_10]
0x18000bf1b  add     rsp, 20h
0x18000bf1f  pop     rdi
0x18000bf20  retn
```
