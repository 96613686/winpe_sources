# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000c414`
- end: `0x18000c45d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800087e4`
- `0x18000ac18`
- `0x18000b85c`

## callees

- `0x18000c414`
- `0x18000e6e8`

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
0x18000c414  sub     rsp, 28h
0x18000c418  lea     r8, [rcx+4]; Source
0x18000c41c  cmp     [r8], edx
0x18000c41f  jz      short loc_18000C458
0x18000c421  mov     al, [rcx+2]
0x18000c424  mov     [r8], edx
0x18000c427  cmp     al, 1
0x18000c429  jnz     short loc_18000C443
0x18000c42b  mov     r9d, 2
0x18000c431  mov     [rsp+28h+arg_8], dx
0x18000c436  movzx   eax, dx
0x18000c439  lea     r8, [rsp+28h+arg_8]
0x18000c43e  mov     edx, r9d
0x18000c441  jmp     short loc_18000C44F
0x18000c443  cmp     al, 2
0x18000c445  jnz     short loc_18000C458
0x18000c447  mov     edx, 4; DestinationSize
0x18000c44c  mov     r9d, edx; SourceSize
0x18000c44f  mov     rcx, [rcx+10h]; Destination
0x18000c453  call    memcpy_s
0x18000c458  add     rsp, 28h
0x18000c45c  retn
```
