# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800104c4`
- end: `0x18001050d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cbec`
- `0x18000ec44`
- `0x18001005c`

## callees

- `0x18000ca48`
- `0x1800104c4`

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
0x1800104c4  sub     rsp, 28h
0x1800104c8  lea     r8, [rcx+4]; Source
0x1800104cc  cmp     [r8], edx
0x1800104cf  jz      short loc_180010508
0x1800104d1  mov     al, [rcx+2]
0x1800104d4  mov     [r8], edx
0x1800104d7  cmp     al, 1
0x1800104d9  jnz     short loc_1800104F3
0x1800104db  mov     r9d, 2
0x1800104e1  mov     [rsp+28h+arg_8], dx
0x1800104e6  movzx   eax, dx
0x1800104e9  lea     r8, [rsp+28h+arg_8]
0x1800104ee  mov     edx, r9d
0x1800104f1  jmp     short loc_1800104FF
0x1800104f3  cmp     al, 2
0x1800104f5  jnz     short loc_180010508
0x1800104f7  mov     edx, 4; DestinationSize
0x1800104fc  mov     r9d, edx; SourceSize
0x1800104ff  mov     rcx, [rcx+10h]; Destination
0x180010503  call    memcpy_s
0x180010508  add     rsp, 28h
0x18001050c  retn
```
