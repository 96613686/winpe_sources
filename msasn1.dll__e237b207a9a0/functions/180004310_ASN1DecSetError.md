# ASN1DecSetError

- ea: `0x180004310`
- end: `0x18000432c`
- name: `ASN1DecSetError`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `41`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800014b0`
- `0x1800016e0`
- `0x180001a00`
- `0x180001b30`
- `0x180001c20`
- `0x180001f50`
- `0x180001f80`
- `0x1800020a0`
- `0x1800022c0`
- `0x180002390`
- `0x1800026b0`
- `0x180002bf0`
- `0x180002c20`
- `0x180003070`
- `0x1800030d0`
- `0x180003270`
- `0x1800036f0`
- `0x180003a60`
- `0x180003be0`
- `0x180004030`
- `0x180004340`
- `0x180004444`
- `0x1800044d0`
- `0x180004760`
- `0x180004810`
- `0x180004a60`
- `0x180004ee0`
- `0x1800051a0`
- `0x180005250`
- `0x180005300`
- `0x180005f50`
- `0x1800062ec`
- `0x180006600`
- `0x180009c10`
- `0x180009e70`
- `0x180009f20`
- `0x180009fa0`
- `0x18000a040`
- `0x18000a860`
- `0x18000a8e0`

## callees

- `0x180004310`

## pseudocode

```c
__int64 __fastcall ASN1DecSetError(__int64 a1, unsigned int a2)
{
  __int64 v2; // rax

  if ( a1 )
  {
    do
    {
      v2 = *(_QWORD *)(a1 + 56);
      *(_DWORD *)(a1 + 32) = a2;
      if ( a1 == v2 )
        break;
      a1 = v2;
    }
    while ( v2 );
  }
  return a2;
}

```

## disassembly

```asm
0x180004310  test    rcx, rcx
0x180004313  jz      short loc_180004329
0x180004315  mov     rax, [rcx+38h]
0x180004319  mov     [rcx+20h], edx
0x18000431c  cmp     rcx, rax
0x18000431f  jz      short loc_180004329
0x180004321  mov     rcx, rax
0x180004324  test    rax, rax
0x180004327  jnz     short loc_180004315
0x180004329  mov     eax, edx
0x18000432b  retn
```
