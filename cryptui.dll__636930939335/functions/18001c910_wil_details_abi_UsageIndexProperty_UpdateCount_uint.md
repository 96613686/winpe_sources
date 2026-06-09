# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18001c910`
- end: `0x18001c95a`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180017d34`
- `0x18001b6ac`
- `0x18001c1dc`

## callees

- `0x18001c910`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001c94f`
- `msvcrt!memcpy_s` at `0x18001c94f`

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
0x18001c910  sub     rsp, 28h
0x18001c914  lea     r8, [rcx+4]; Source
0x18001c918  cmp     [r8], edx
0x18001c91b  jz      short loc_18001C955
0x18001c91d  mov     al, [rcx+2]
0x18001c920  mov     [r8], edx
0x18001c923  cmp     al, 1
0x18001c925  jnz     short loc_18001C93F
0x18001c927  mov     r9d, 2
0x18001c92d  mov     [rsp+28h+arg_8], dx
0x18001c932  movzx   eax, dx
0x18001c935  lea     r8, [rsp+28h+arg_8]
0x18001c93a  mov     edx, r9d
0x18001c93d  jmp     short loc_18001C94B
0x18001c93f  cmp     al, 2
0x18001c941  jnz     short loc_18001C955
0x18001c943  mov     edx, 4; DestinationSize
0x18001c948  mov     r9d, edx; SourceSize
0x18001c94b  mov     rcx, [rcx+10h]; Destination
0x18001c94f  call    cs:__imp_memcpy_s
0x18001c955  add     rsp, 28h
0x18001c959  retn
```
