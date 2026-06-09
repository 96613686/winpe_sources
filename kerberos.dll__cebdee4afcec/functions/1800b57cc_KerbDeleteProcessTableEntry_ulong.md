# KerbDeleteProcessTableEntry(ulong)

- ea: `0x1800b57cc`
- end: `0x1800b5880`
- name: `?KerbDeleteProcessTableEntry@@YAXK@Z`
- size: `180`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800a6d10`

## callees

- `0x18007108c`
- `0x18008b70c`
- `0x1800b56c4`
- `0x1800b57cc`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800b582a`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800b582a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800b580a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x1800b580a`
- `ntdll!RtlReleaseResource` at `0x1800b5869`
- `ntdll!RtlReleaseResource` at `0x1800b5869`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800b57f4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800b57f4`

## string_xrefs

- `0x1800b5834`: `KerbDeleteProcessTableEntry deleted pin kdc entry %p for process id %d (%#x)\n`
- `0x1800b583e`: `KerbDeleteProcessTableEntry`

## pseudocode

```c
void __fastcall KerbDeleteProcessTableEntry(int a1)
{
  struct _KERB_PROCESS_TABLE_ENTRY *v2; // rax
  struct _KERB_PROCESS_TABLE_ENTRY *v3; // rbx
  _DWORD Buffer[18]; // [rsp+40h] [rbp-48h] BYREF

  memset_0(Buffer, 0, 0x40u);
  RtlAcquireResourceExclusive(&KerbGlobalProcessTableLock, 1u);
  Buffer[0] = a1;
  v2 = (struct _KERB_PROCESS_TABLE_ENTRY *)RtlLookupElementGenericTableAvl(&KerbGlobalProcessTable, Buffer);
  v3 = v2;
  if ( v2 )
  {
    KerbCleanupProcessTableEntry(v2);
    RtlDeleteElementGenericTableAvl(&KerbGlobalProcessTable, v3);
    KerbTracerT::Log(
      22,
      "KerbDeleteProcessTableEntry",
      1781,
      "KerbDeleteProcessTableEntry deleted pin kdc entry %p for process id %d (%#x)\n",
      (const void *)WORD1(v3),
      a1,
      a1);
  }
  RtlReleaseResource(&KerbGlobalProcessTableLock);
}

```

## disassembly

```asm
0x1800b57cc  mov     [rsp+arg_0], rbx
0x1800b57d1  push    rdi
0x1800b57d2  sub     rsp, 80h
0x1800b57d9  xor     edx, edx; Val
0x1800b57db  mov     edi, ecx
0x1800b57dd  lea     rcx, [rsp+88h+Buffer]; void *
0x1800b57e2  lea     r8d, [rdx+40h]; Size
0x1800b57e6  call    memset_0
0x1800b57eb  mov     dl, 1; Wait
0x1800b57ed  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x1800b57f4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800b57fa  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800b57ff  mov     [rsp+88h+Buffer], edi
0x1800b5803  lea     rcx, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; Table
0x1800b580a  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1800b5810  mov     rbx, rax
0x1800b5813  test    rax, rax
0x1800b5816  jz      short loc_1800B5862
0x1800b5818  mov     rcx, rax; struct _KERB_PROCESS_TABLE_ENTRY *
0x1800b581b  call    ?KerbCleanupProcessTableEntry@@YAXPEAU_KERB_PROCESS_TABLE_ENTRY@@@Z; KerbCleanupProcessTableEntry(_KERB_PROCESS_TABLE_ENTRY *)
0x1800b5820  mov     rdx, rbx; Buffer
0x1800b5823  lea     rcx, ?KerbGlobalProcessTable@@3U_RTL_AVL_TABLE@@A; Table
0x1800b582a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800b5830  shr     rbx, 10h
0x1800b5834  lea     r9, aKerbdeleteproc_0; "KerbDeleteProcessTableEntry deleted pin"...
0x1800b583b  movzx   eax, bx
0x1800b583e  lea     rdx, aKerbdeleteproc; "KerbDeleteProcessTableEntry"
0x1800b5845  mov     [rsp+88h+var_58], edi
0x1800b5849  mov     r8d, 6F5h
0x1800b584f  mov     [rsp+88h+var_60], edi
0x1800b5853  mov     ecx, 16h
0x1800b5858  mov     [rsp+88h+var_68], rax
0x1800b585d  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800b5862  lea     rcx, ?KerbGlobalProcessTableLock@@3U_RTL_RESOURCE@@A; Resource
0x1800b5869  call    cs:__imp_RtlReleaseResource
0x1800b586f  mov     rbx, [rsp+88h+arg_0]
0x1800b5877  add     rsp, 80h
0x1800b587e  pop     rdi
0x1800b587f  retn
```
