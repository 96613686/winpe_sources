# WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)

- ea: `0x18000c528`
- end: `0x18000c553`
- name: `?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z`
- size: `43`
- prototype: `struct _WST_ACTIVE_ENGINE_CONTEXT *__fastcall(struct _WST_CONTEXT *, struct _GUID *)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d0`
- `0x180008e60`
- `0x18000a29c`
- `0x18000be70`
- `0x18000bf1c`
- `0x18000c7d0`
- `0x18000da80`
- `0x180014150`
- `0x18001a020`
- `0x18001a3b4`

## callees

- `0x18000c528`

## pseudocode

```c
struct _WST_ACTIVE_ENGINE_CONTEXT *__fastcall WSTGetActiveContextByAuthScheme(
        struct _WST_CONTEXT *a1,
        struct _GUID *a2)
{
  struct _WST_ACTIVE_ENGINE_CONTEXT *v2; // r8
  struct _WST_ACTIVE_ENGINE_CONTEXT *result; // rax
  __int64 v4; // rcx

  v2 = (struct _WST_CONTEXT *)((char *)a1 + 56);
  for ( result = (struct _WST_ACTIVE_ENGINE_CONTEXT *)*((_QWORD *)a1 + 7);
        result != v2;
        result = *(struct _WST_ACTIVE_ENGINE_CONTEXT **)result )
  {
    v4 = *((_QWORD *)result + 3) - *(_QWORD *)&a2->Data1;
    if ( !v4 )
      v4 = *((_QWORD *)result + 4) - *(_QWORD *)a2->Data4;
    if ( !v4 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c528  lea     r8, [rcx+38h]
0x18000c52c  mov     rax, [r8]
0x18000c52f  cmp     rax, r8
0x18000c532  jz      short loc_18000C54B
0x18000c534  mov     rcx, [rax+18h]
0x18000c538  sub     rcx, [rdx]
0x18000c53b  jnz     short loc_18000C545
0x18000c53d  mov     rcx, [rax+20h]
0x18000c541  sub     rcx, [rdx+8]
0x18000c545  test    rcx, rcx
0x18000c548  jnz     short loc_18000C54E
0x18000c54a  retn
0x18000c54b  xor     eax, eax
0x18000c54d  retn
0x18000c54e  mov     rax, [rax]
0x18000c551  jmp     short loc_18000C52F
```
