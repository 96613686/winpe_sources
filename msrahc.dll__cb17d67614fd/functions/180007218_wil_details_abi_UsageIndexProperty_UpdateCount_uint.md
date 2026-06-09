# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180007218`
- end: `0x180007262`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003f14`
- `0x180005dd4`
- `0x180006960`

## callees

- `0x180007218`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007257`
- `msvcrt!memcpy_s` at `0x180007257`

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
0x180007218  sub     rsp, 28h
0x18000721c  lea     r8, [rcx+4]; Source
0x180007220  cmp     [r8], edx
0x180007223  jz      short loc_18000725D
0x180007225  mov     al, [rcx+2]
0x180007228  mov     [r8], edx
0x18000722b  cmp     al, 1
0x18000722d  jnz     short loc_180007247
0x18000722f  mov     r9d, 2
0x180007235  mov     [rsp+28h+arg_8], dx
0x18000723a  movzx   eax, dx
0x18000723d  lea     r8, [rsp+28h+arg_8]
0x180007242  mov     edx, r9d
0x180007245  jmp     short loc_180007253
0x180007247  cmp     al, 2
0x180007249  jnz     short loc_18000725D
0x18000724b  mov     edx, 4; DestinationSize
0x180007250  mov     r9d, edx; SourceSize
0x180007253  mov     rcx, [rcx+10h]; Destination
0x180007257  call    cs:__imp_memcpy_s
0x18000725d  add     rsp, 28h
0x180007261  retn
```
