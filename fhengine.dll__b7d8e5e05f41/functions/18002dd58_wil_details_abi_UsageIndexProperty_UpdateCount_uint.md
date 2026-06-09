# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18002dd58`
- end: `0x18002dda2`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180028d24`
- `0x18002c1e8`
- `0x18002d504`

## callees

- `0x18002dd58`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002dd97`
- `msvcrt!memcpy_s` at `0x18002dd97`

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
0x18002dd58  sub     rsp, 28h
0x18002dd5c  lea     r8, [rcx+4]; Source
0x18002dd60  cmp     [r8], edx
0x18002dd63  jz      short loc_18002DD9D
0x18002dd65  mov     al, [rcx+2]
0x18002dd68  mov     [r8], edx
0x18002dd6b  cmp     al, 1
0x18002dd6d  jnz     short loc_18002DD87
0x18002dd6f  mov     r9d, 2
0x18002dd75  mov     [rsp+28h+arg_8], dx
0x18002dd7a  movzx   eax, dx
0x18002dd7d  lea     r8, [rsp+28h+arg_8]
0x18002dd82  mov     edx, r9d
0x18002dd85  jmp     short loc_18002DD93
0x18002dd87  cmp     al, 2
0x18002dd89  jnz     short loc_18002DD9D
0x18002dd8b  mov     edx, 4; DestinationSize
0x18002dd90  mov     r9d, edx; SourceSize
0x18002dd93  mov     rcx, [rcx+10h]; Destination
0x18002dd97  call    cs:__imp_memcpy_s
0x18002dd9d  add     rsp, 28h
0x18002dda1  retn
```
