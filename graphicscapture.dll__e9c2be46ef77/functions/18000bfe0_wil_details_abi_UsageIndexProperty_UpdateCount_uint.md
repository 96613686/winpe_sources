# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000bfe0`
- end: `0x18000c029`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180008778`
- `0x18000aa88`
- `0x18000b78c`

## callees

- `0x18000bfe0`
- `0x18000d014`

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
0x18000bfe0  sub     rsp, 28h
0x18000bfe4  lea     r8, [rcx+4]; Source
0x18000bfe8  cmp     [r8], edx
0x18000bfeb  jz      short loc_18000C024
0x18000bfed  mov     al, [rcx+2]
0x18000bff0  mov     [r8], edx
0x18000bff3  cmp     al, 1
0x18000bff5  jnz     short loc_18000C00F
0x18000bff7  mov     r9d, 2
0x18000bffd  mov     [rsp+28h+arg_8], dx
0x18000c002  movzx   eax, dx
0x18000c005  lea     r8, [rsp+28h+arg_8]
0x18000c00a  mov     edx, r9d
0x18000c00d  jmp     short loc_18000C01B
0x18000c00f  cmp     al, 2
0x18000c011  jnz     short loc_18000C024
0x18000c013  mov     edx, 4; DestinationSize
0x18000c018  mov     r9d, edx; SourceSize
0x18000c01b  mov     rcx, [rcx+10h]; Destination
0x18000c01f  call    memcpy_s
0x18000c024  add     rsp, 28h
0x18000c028  retn
```
