# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180016224`
- end: `0x18001626d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000b164`
- `0x180012d60`
- `0x18001599c`

## callees

- `0x18000afe0`
- `0x180016224`

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
0x180016224  sub     rsp, 28h
0x180016228  lea     r8, [rcx+4]; Source
0x18001622c  cmp     [r8], edx
0x18001622f  jz      short loc_180016268
0x180016231  mov     al, [rcx+2]
0x180016234  mov     [r8], edx
0x180016237  cmp     al, 1
0x180016239  jnz     short loc_180016253
0x18001623b  mov     r9d, 2
0x180016241  mov     [rsp+28h+arg_8], dx
0x180016246  movzx   eax, dx
0x180016249  lea     r8, [rsp+28h+arg_8]
0x18001624e  mov     edx, r9d
0x180016251  jmp     short loc_18001625F
0x180016253  cmp     al, 2
0x180016255  jnz     short loc_180016268
0x180016257  mov     edx, 4; DestinationSize
0x18001625c  mov     r9d, edx; SourceSize
0x18001625f  mov     rcx, [rcx+10h]; Destination
0x180016263  call    memcpy_s
0x180016268  add     rsp, 28h
0x18001626c  retn
```
