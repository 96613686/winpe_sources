# MupiPrefixCacheSizePolicyCheck

- ea: `0x140010b5c`
- end: `0x140010bb0`
- name: `MupiPrefixCacheSizePolicyCheck`
- size: `84`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010a80`
- `0x14001d744`

## callees

- `0x140010b5c`
- `0x140010e48`

## pseudocode

```c
__int64 MupiPrefixCacheSizePolicyCheck()
{
  __int64 *v0; // rbx
  __int64 result; // rax
  __int64 *v2; // rcx

  v0 = (__int64 *)qword_14000A9E0;
  while ( v0 != &qword_14000A9E0 )
  {
    result = (unsigned int)(dword_14000A9FC - dword_14000AA08);
    if ( (unsigned int)result <= dword_14000A9F8 )
      break;
    v2 = v0 - 15;
    v0 = (__int64 *)*v0;
    if ( !*((_DWORD *)v2 + 34) )
      result = MupiRemoveKnownPrefixEntry((char *)v2);
  }
  return result;
}

```

## disassembly

```asm
0x140010b5c  mov     [rsp+arg_0], rbx
0x140010b61  push    rdi
0x140010b62  sub     rsp, 20h
0x140010b66  mov     rbx, cs:qword_14000A9E0
0x140010b6d  lea     rdi, qword_14000A9E0
0x140010b74  jmp     short loc_140010B9F
0x140010b76  mov     eax, cs:dword_14000A9FC
0x140010b7c  sub     eax, cs:dword_14000AA08
0x140010b82  cmp     eax, cs:dword_14000A9F8
0x140010b88  jbe     short loc_140010BA4
0x140010b8a  lea     rcx, [rbx-78h]; P
0x140010b8e  mov     rbx, [rbx]
0x140010b91  cmp     dword ptr [rcx+88h], 0
0x140010b98  jnz     short loc_140010B9F
0x140010b9a  call    MupiRemoveKnownPrefixEntry
0x140010b9f  cmp     rbx, rdi
0x140010ba2  jnz     short loc_140010B76
0x140010ba4  mov     rbx, [rsp+28h+arg_0]
0x140010ba9  add     rsp, 20h
0x140010bad  pop     rdi
0x140010bae  retn
```
