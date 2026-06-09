# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180014bc4`
- end: `0x180014c0e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000e338`
- `0x180011258`
- `0x180014090`

## callees

- `0x180014bc4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180014c03`
- `msvcrt!memcpy_s` at `0x180014c03`

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
0x180014bc4  sub     rsp, 28h
0x180014bc8  lea     r8, [rcx+4]; Source
0x180014bcc  cmp     [r8], edx
0x180014bcf  jz      short loc_180014C09
0x180014bd1  mov     al, [rcx+2]
0x180014bd4  mov     [r8], edx
0x180014bd7  cmp     al, 1
0x180014bd9  jnz     short loc_180014BF3
0x180014bdb  mov     r9d, 2
0x180014be1  mov     [rsp+28h+arg_8], dx
0x180014be6  movzx   eax, dx
0x180014be9  lea     r8, [rsp+28h+arg_8]
0x180014bee  mov     edx, r9d
0x180014bf1  jmp     short loc_180014BFF
0x180014bf3  cmp     al, 2
0x180014bf5  jnz     short loc_180014C09
0x180014bf7  mov     edx, 4; DestinationSize
0x180014bfc  mov     r9d, edx; SourceSize
0x180014bff  mov     rcx, [rcx+10h]; Destination
0x180014c03  call    cs:__imp_memcpy_s
0x180014c09  add     rsp, 28h
0x180014c0d  retn
```
