# MRxDAVInvalidateFileInfoCache

- ea: `0x140025808`
- end: `0x140025866`
- name: `MRxDAVInvalidateFileInfoCache`
- size: `94`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400128a0`
- `0x1400130e0`
- `0x140022a80`

## callees

- `0x140025758`
- `0x140025808`
- `0x14002593c`

## pseudocode

```c
__int64 __fastcall MRxDAVInvalidateFileInfoCache(__int64 a1)
{
  __int64 v2; // rcx
  __int64 *v3; // rbx
  __int64 v4; // rdx
  __int64 v5; // rdx

  v2 = *(_QWORD *)(a1 + 56);
  v3 = (__int64 *)(a1 + 648);
  if ( *(_BYTE *)(a1 + 32) )
    v4 = *(_QWORD *)(v2 + 120);
  else
    v4 = *v3;
  MRxDAVInvalidateBasicFileInfoCacheWithName(v2 + 360, v4);
  v5 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(a1 + 32) )
    v3 = (__int64 *)(v5 + 120);
  return MRxDAVInvalidateStandardFileInfoCacheWithName(v5 + 360, *v3);
}

```

## disassembly

```asm
0x140025808  mov     [rsp+arg_0], rbx
0x14002580d  push    rdi
0x14002580e  sub     rsp, 20h
0x140025812  mov     rdi, rcx
0x140025815  mov     rcx, [rcx+38h]
0x140025819  cmp     byte ptr [rdi+20h], 0
0x14002581d  lea     rbx, [rdi+288h]
0x140025824  jnz     short loc_14002582B
0x140025826  mov     rdx, [rbx]
0x140025829  jmp     short loc_14002582F
0x14002582b  mov     rdx, [rcx+78h]
0x14002582f  add     rcx, 168h
0x140025836  call    MRxDAVInvalidateBasicFileInfoCacheWithName
0x14002583b  mov     rdx, [rdi+38h]
0x14002583f  cmp     byte ptr [rdi+20h], 0
0x140025843  lea     rcx, [rdx+78h]
0x140025847  cmovnz  rbx, rcx
0x14002584b  lea     rcx, [rdx+168h]
0x140025852  mov     rdx, [rbx]
0x140025855  call    MRxDAVInvalidateStandardFileInfoCacheWithName
0x14002585a  mov     rbx, [rsp+28h+arg_0]
0x14002585f  add     rsp, 20h
0x140025863  pop     rdi
0x140025864  retn
```
