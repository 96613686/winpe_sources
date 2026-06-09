# OncRpcBufMgrGetNextBufferDescriptor

- ea: `0x14001f860`
- end: `0x14001f883`
- name: `OncRpcBufMgrGetNextBufferDescriptor`
- size: `35`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d9f0`
- `0x140012c40`
- `0x140014ff4`
- `0x140025004`
- `0x140038850`
- `0x14003896c`
- `0x140038a68`

## callees

- `0x14001f860`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetNextBufferDescriptor(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx

  if ( !a2 )
    return 0;
  v2 = a2 + 24;
  v3 = *(_QWORD *)(a2 + 24);
  if ( v3 == v2 || v3 == a1 + 24 )
    return 0;
  else
    return v3 - 24;
}

```

## disassembly

```asm
0x14001f860  test    rdx, rdx
0x14001f863  jz      short loc_14001F880
0x14001f865  lea     rax, [rdx+18h]
0x14001f869  mov     rdx, [rax]
0x14001f86c  cmp     rdx, rax
0x14001f86f  jz      short loc_14001F880
0x14001f871  lea     rax, [rcx+18h]
0x14001f875  cmp     rdx, rax
0x14001f878  jz      short loc_14001F880
0x14001f87a  lea     rax, [rdx-18h]
0x14001f87e  retn
0x14001f880  xor     eax, eax
0x14001f882  retn
```
