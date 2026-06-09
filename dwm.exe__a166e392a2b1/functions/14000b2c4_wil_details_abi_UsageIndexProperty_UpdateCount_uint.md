# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000b2c4`
- end: `0x14000b30d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140004ee0`
- `0x140008660`
- `0x14000ac60`

## callees

- `0x14000b2c4`
- `0x14000bebc`

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
0x14000b2c4  sub     rsp, 28h
0x14000b2c8  lea     r8, [rcx+4]; Source
0x14000b2cc  cmp     [r8], edx
0x14000b2cf  jz      short loc_14000B308
0x14000b2d1  mov     al, [rcx+2]
0x14000b2d4  mov     [r8], edx
0x14000b2d7  cmp     al, 1
0x14000b2d9  jnz     short loc_14000B2F3
0x14000b2db  mov     r9d, 2
0x14000b2e1  mov     [rsp+28h+arg_8], dx
0x14000b2e6  movzx   eax, dx
0x14000b2e9  lea     r8, [rsp+28h+arg_8]
0x14000b2ee  mov     edx, r9d
0x14000b2f1  jmp     short loc_14000B2FF
0x14000b2f3  cmp     al, 2
0x14000b2f5  jnz     short loc_14000B308
0x14000b2f7  mov     edx, 4; DestinationSize
0x14000b2fc  mov     r9d, edx; SourceSize
0x14000b2ff  mov     rcx, [rcx+10h]; Destination
0x14000b303  call    memcpy_s
0x14000b308  add     rsp, 28h
0x14000b30c  retn
```
