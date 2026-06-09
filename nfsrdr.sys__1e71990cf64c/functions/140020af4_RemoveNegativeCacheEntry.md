# RemoveNegativeCacheEntry

- ea: `0x140020af4`
- end: `0x140020b5d`
- name: `RemoveNegativeCacheEntry`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x14001bbbc`
- `0x14001c694`
- `0x140030ef0`

## callees

- `0x140005c90`
- `0x140008a50`
- `0x140009ea0`
- `0x140014650`
- `0x1400200d0`
- `0x140020488`
- `0x140020af4`

## pseudocode

```c
void __fastcall RemoveNegativeCacheEntry(__int64 a1, __int64 a2, const UNICODE_STRING *a3)
{
  __int64 *v4; // rax
  __int64 v5; // rbx

  if ( a2 )
  {
    if ( a3 )
    {
      v4 = HacQueryAndReference(*(PRKMUTEX *)(a2 + 72), a3);
      v5 = (__int64)v4;
      if ( v4 )
      {
        if ( (unsigned __int8)HacIsNegativeCacheEntry(v4) )
        {
          HacUnMarkNegativeCacheFlag(v5);
          HacInvalidateAttributes(v5);
          HacOrphanEntry(v5);
        }
        HacDereference(a1, v5);
      }
    }
  }
}

```

## disassembly

```asm
0x140020af4  test    rdx, rdx
0x140020af7  jz      short locret_140020B5B
0x140020af9  mov     [rsp+arg_0], rbx
0x140020afe  push    rdi
0x140020aff  sub     rsp, 20h
0x140020b03  mov     rax, rdx
0x140020b06  mov     rdi, rcx
0x140020b09  test    r8, r8
0x140020b0c  jz      short loc_140020B51
0x140020b0e  mov     rcx, [rax+48h]; Mutex
0x140020b12  mov     rdx, r8; String2
0x140020b15  call    HacQueryAndReference
0x140020b1a  mov     rbx, rax
0x140020b1d  test    rax, rax
0x140020b20  jz      short loc_140020B51
0x140020b22  mov     rcx, rax
0x140020b25  call    HacIsNegativeCacheEntry
0x140020b2a  test    al, al
0x140020b2c  jz      short loc_140020B46
0x140020b2e  mov     rcx, rbx
0x140020b31  call    HacUnMarkNegativeCacheFlag
0x140020b36  mov     rcx, rbx
0x140020b39  call    HacInvalidateAttributes
0x140020b3e  mov     rcx, rbx
0x140020b41  call    HacOrphanEntry
0x140020b46  mov     rdx, rbx
0x140020b49  mov     rcx, rdi
0x140020b4c  call    HacDereference
0x140020b51  mov     rbx, [rsp+28h+arg_0]
0x140020b56  add     rsp, 20h
0x140020b5a  pop     rdi
0x140020b5b  retn
```
