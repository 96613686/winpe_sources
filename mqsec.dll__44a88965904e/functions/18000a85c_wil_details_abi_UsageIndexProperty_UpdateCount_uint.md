# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000a85c`
- end: `0x18000a8a6`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180006750`
- `0x180009288`
- `0x18000a034`

## callees

- `0x18000a85c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a89b`
- `msvcrt!memcpy_s` at `0x18000a89b`

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
0x18000a85c  sub     rsp, 28h
0x18000a860  lea     r8, [rcx+4]; Source
0x18000a864  cmp     [r8], edx
0x18000a867  jz      short loc_18000A8A1
0x18000a869  mov     al, [rcx+2]
0x18000a86c  mov     [r8], edx
0x18000a86f  cmp     al, 1
0x18000a871  jnz     short loc_18000A88B
0x18000a873  mov     r9d, 2
0x18000a879  mov     [rsp+28h+arg_8], dx
0x18000a87e  movzx   eax, dx
0x18000a881  lea     r8, [rsp+28h+arg_8]
0x18000a886  mov     edx, r9d
0x18000a889  jmp     short loc_18000A897
0x18000a88b  cmp     al, 2
0x18000a88d  jnz     short loc_18000A8A1
0x18000a88f  mov     edx, 4; DestinationSize
0x18000a894  mov     r9d, edx; SourceSize
0x18000a897  mov     rcx, [rcx+10h]; Destination
0x18000a89b  call    cs:__imp_memcpy_s
0x18000a8a1  add     rsp, 28h
0x18000a8a5  retn
```
