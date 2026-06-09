# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14001b0f0`
- end: `0x14001b13a`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140017e10`
- `0x140019cd8`
- `0x14001a9fc`

## callees

- `0x14001b0f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14001b12f`
- `msvcrt!memcpy_s` at `0x14001b12f`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x14001b0f0  sub     rsp, 28h
0x14001b0f4  lea     r8, [rcx+4]; Source
0x14001b0f8  cmp     [r8], edx
0x14001b0fb  jz      short loc_14001B135
0x14001b0fd  mov     al, [rcx+2]
0x14001b100  mov     [r8], edx
0x14001b103  cmp     al, 1
0x14001b105  jnz     short loc_14001B11F
0x14001b107  mov     r9d, 2
0x14001b10d  mov     [rsp+28h+arg_8], dx
0x14001b112  movzx   eax, dx
0x14001b115  lea     r8, [rsp+28h+arg_8]
0x14001b11a  mov     edx, r9d
0x14001b11d  jmp     short loc_14001B12B
0x14001b11f  cmp     al, 2
0x14001b121  jnz     short loc_14001B135
0x14001b123  mov     edx, 4; DestinationSize
0x14001b128  mov     r9d, edx; SourceSize
0x14001b12b  mov     rcx, [rcx+10h]; Destination
0x14001b12f  call    cs:__imp_memcpy_s
0x14001b135  add     rsp, 28h
0x14001b139  retn
```
