# GetAdapterAddressesInfo(void)

- ea: `0x180027f88`
- end: `0x180028074`
- name: `?GetAdapterAddressesInfo@@YAKXZ`
- size: `236`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800280e0`

## callees

- `0x180027f88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ffd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028035`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180027ffd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180028035`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028017`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180028017`
- `MobileNetworking!AcquireWriteLock` at `0x180027fb5`
- `MobileNetworking!AcquireWriteLock` at `0x180027fb5`
- `MobileNetworking!ReleaseWriteLock` at `0x180028061`
- `MobileNetworking!ReleaseWriteLock` at `0x180028061`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180027fe5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180027fe5`

## pseudocode

```c
__int64 GetAdapterAddressesInfo(void)
{
  IP_ADAPTER_ADDRESSES_LH *v0; // rax
  unsigned int i; // ebx
  ULONG AdaptersAddresses; // edi
  ULONG SizePointer; // [rsp+40h] [rbp+8h] BYREF

  SizePointer = 0;
  AcquireWriteLock(&Block, qword_180052DF0, "GetAdapterAddressesInfo", 36);
  v0 = Block;
  if ( !Block )
  {
    for ( i = 0; i < 5; ++i )
    {
      AdaptersAddresses = GetAdaptersAddresses(0, 0x1C6u, 0, v0, &SizePointer);
      if ( !AdaptersAddresses )
        goto LABEL_12;
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
      if ( AdaptersAddresses != 111 )
        goto LABEL_12;
      v0 = (IP_ADAPTER_ADDRESSES_LH *)malloc(SizePointer);
      Block = v0;
      if ( !v0 )
        goto LABEL_12;
    }
    if ( v0 )
    {
      free(v0);
      Block = 0;
    }
  }
LABEL_12:
  ReleaseWriteLock(&Block, qword_180052DF0, "GetAdapterAddressesInfo", 98);
  return 0;
}

```

## disassembly

```asm
0x180027f88  mov     [rsp+arg_8], rbx
0x180027f8d  push    rdi
0x180027f8e  sub     rsp, 30h
0x180027f92  mov     r9d, 24h ; '$'
0x180027f98  mov     [rsp+38h+arg_0], 0
0x180027fa0  lea     r8, aGetadapteraddr; "GetAdapterAddressesInfo"
0x180027fa7  lea     rdx, qword_180052DF0
0x180027fae  lea     rcx, Block
0x180027fb5  call    cs:__imp_AcquireWriteLock
0x180027fbb  mov     rax, cs:Block
0x180027fc2  test    rax, rax
0x180027fc5  jnz     short loc_180028046
0x180027fc7  xor     ebx, ebx
0x180027fc9  cmp     ebx, 5
0x180027fcc  jnb     short loc_18002802D
0x180027fce  lea     rcx, [rsp+38h+arg_0]
0x180027fd3  mov     r9, rax; AdapterAddresses
0x180027fd6  mov     [rsp+38h+SizePointer], rcx; SizePointer
0x180027fdb  xor     r8d, r8d; Reserved
0x180027fde  xor     ecx, ecx; Family
0x180027fe0  mov     edx, 1C6h; Flags
0x180027fe5  call    cs:__imp_GetAdaptersAddresses
0x180027feb  mov     edi, eax
0x180027fed  test    eax, eax
0x180027fef  jz      short loc_180028046
0x180027ff1  mov     rcx, cs:Block; Block
0x180027ff8  test    rcx, rcx
0x180027ffb  jz      short loc_18002800E
0x180027ffd  call    cs:__imp_free
0x180028003  mov     cs:Block, 0
0x18002800e  cmp     edi, 6Fh ; 'o'
0x180028011  jnz     short loc_180028046
0x180028013  mov     ecx, [rsp+38h+arg_0]; Size
0x180028017  call    cs:__imp_malloc
0x18002801d  mov     cs:Block, rax
0x180028024  test    rax, rax
0x180028027  jz      short loc_180028046
0x180028029  inc     ebx
0x18002802b  jmp     short loc_180027FC9
0x18002802d  test    rax, rax
0x180028030  jz      short loc_180028046
0x180028032  mov     rcx, rax; Block
0x180028035  call    cs:__imp_free
0x18002803b  mov     cs:Block, 0
0x180028046  mov     r9d, 62h ; 'b'
0x18002804c  lea     r8, aGetadapteraddr; "GetAdapterAddressesInfo"
0x180028053  lea     rdx, qword_180052DF0
0x18002805a  lea     rcx, Block
0x180028061  call    cs:__imp_ReleaseWriteLock
0x180028067  mov     rbx, [rsp+38h+arg_8]
0x18002806c  xor     eax, eax
0x18002806e  add     rsp, 30h
0x180028072  pop     rdi
0x180028073  retn
```
