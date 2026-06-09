# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180012144`
- end: `0x18001218e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180010ad0`
- `0x180011788`
- `0x180011d58`

## callees

- `0x180012144`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180012183`
- `msvcrt!memcpy_s` at `0x180012183`

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
0x180012144  sub     rsp, 28h
0x180012148  lea     r8, [rcx+4]; Source
0x18001214c  cmp     [r8], edx
0x18001214f  jz      short loc_180012189
0x180012151  mov     al, [rcx+2]
0x180012154  mov     [r8], edx
0x180012157  cmp     al, 1
0x180012159  jnz     short loc_180012173
0x18001215b  mov     r9d, 2
0x180012161  mov     [rsp+28h+arg_8], dx
0x180012166  movzx   eax, dx
0x180012169  lea     r8, [rsp+28h+arg_8]
0x18001216e  mov     edx, r9d
0x180012171  jmp     short loc_18001217F
0x180012173  cmp     al, 2
0x180012175  jnz     short loc_180012189
0x180012177  mov     edx, 4; DestinationSize
0x18001217c  mov     r9d, edx; SourceSize
0x18001217f  mov     rcx, [rcx+10h]; Destination
0x180012183  call    cs:__imp_memcpy_s
0x180012189  add     rsp, 28h
0x18001218d  retn
```
