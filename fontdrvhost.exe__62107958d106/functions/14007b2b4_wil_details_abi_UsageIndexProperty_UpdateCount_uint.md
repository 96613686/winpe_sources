# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14007b2b4`
- end: `0x14007b2fd`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140075778`
- `0x14007863c`
- `0x14007ac0c`

## callees

- `0x14007b2b4`
- `0x14007bed8`

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
0x14007b2b4  sub     rsp, 28h
0x14007b2b8  lea     r8, [rcx+4]; Source
0x14007b2bc  cmp     [r8], edx
0x14007b2bf  jz      short loc_14007B2F8
0x14007b2c1  mov     al, [rcx+2]
0x14007b2c4  mov     [r8], edx
0x14007b2c7  cmp     al, 1
0x14007b2c9  jnz     short loc_14007B2E3
0x14007b2cb  mov     r9d, 2
0x14007b2d1  mov     [rsp+28h+arg_8], dx
0x14007b2d6  movzx   eax, dx
0x14007b2d9  lea     r8, [rsp+28h+arg_8]
0x14007b2de  mov     edx, r9d
0x14007b2e1  jmp     short loc_14007B2EF
0x14007b2e3  cmp     al, 2
0x14007b2e5  jnz     short loc_14007B2F8
0x14007b2e7  mov     edx, 4; DestinationSize
0x14007b2ec  mov     r9d, edx; SourceSize
0x14007b2ef  mov     rcx, [rcx+10h]; Destination
0x14007b2f3  call    memcpy_s
0x14007b2f8  add     rsp, 28h
0x14007b2fc  retn
```
