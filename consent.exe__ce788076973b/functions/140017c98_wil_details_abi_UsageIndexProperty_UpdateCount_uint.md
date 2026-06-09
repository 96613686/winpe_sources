# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140017c98`
- end: `0x140017ce2`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140008d1c`
- `0x140014dfc`
- `0x14001795c`

## callees

- `0x140017c98`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140017cd7`
- `msvcrt!memcpy_s` at `0x140017cd7`

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
0x140017c98  sub     rsp, 28h
0x140017c9c  lea     r8, [rcx+4]; Source
0x140017ca0  cmp     [r8], edx
0x140017ca3  jz      short loc_140017CDD
0x140017ca5  mov     al, [rcx+2]
0x140017ca8  mov     [r8], edx
0x140017cab  cmp     al, 1
0x140017cad  jnz     short loc_140017CC7
0x140017caf  mov     r9d, 2
0x140017cb5  mov     [rsp+28h+arg_8], dx
0x140017cba  movzx   eax, dx
0x140017cbd  lea     r8, [rsp+28h+arg_8]
0x140017cc2  mov     edx, r9d
0x140017cc5  jmp     short loc_140017CD3
0x140017cc7  cmp     al, 2
0x140017cc9  jnz     short loc_140017CDD
0x140017ccb  mov     edx, 4; DestinationSize
0x140017cd0  mov     r9d, edx; SourceSize
0x140017cd3  mov     rcx, [rcx+10h]; Destination
0x140017cd7  call    cs:__imp_memcpy_s
0x140017cdd  add     rsp, 28h
0x140017ce1  retn
```
