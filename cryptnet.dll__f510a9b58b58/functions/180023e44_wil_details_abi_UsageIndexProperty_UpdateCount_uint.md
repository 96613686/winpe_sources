# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180023e44`
- end: `0x180023e8e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b170`
- `0x18002160c`
- `0x180023930`

## callees

- `0x180023e44`

## import_xrefs

- `ntdll!memcpy_s` at `0x180023e83`
- `ntdll!memcpy_s` at `0x180023e83`

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
0x180023e44  sub     rsp, 28h
0x180023e48  lea     r8, [rcx+4]; Source
0x180023e4c  cmp     [r8], edx
0x180023e4f  jz      short loc_180023E89
0x180023e51  mov     al, [rcx+2]
0x180023e54  mov     [r8], edx
0x180023e57  cmp     al, 1
0x180023e59  jnz     short loc_180023E73
0x180023e5b  mov     r9d, 2
0x180023e61  mov     [rsp+28h+arg_8], dx
0x180023e66  movzx   eax, dx
0x180023e69  lea     r8, [rsp+28h+arg_8]
0x180023e6e  mov     edx, r9d
0x180023e71  jmp     short loc_180023E7F
0x180023e73  cmp     al, 2
0x180023e75  jnz     short loc_180023E89
0x180023e77  mov     edx, 4; DestinationSize
0x180023e7c  mov     r9d, edx; SourceSize
0x180023e7f  mov     rcx, [rcx+10h]; Destination
0x180023e83  call    cs:__imp_memcpy_s
0x180023e89  add     rsp, 28h
0x180023e8d  retn
```
