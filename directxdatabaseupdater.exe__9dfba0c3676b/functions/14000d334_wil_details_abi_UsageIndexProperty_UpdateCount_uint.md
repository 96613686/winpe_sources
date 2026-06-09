# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000d334`
- end: `0x14000d37d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140006e48`
- `0x140009ae0`
- `0x14000ab4c`

## callees

- `0x14000d334`
- `0x14000eff0`

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
0x14000d334  sub     rsp, 28h
0x14000d338  lea     r8, [rcx+4]; Source
0x14000d33c  cmp     [r8], edx
0x14000d33f  jz      short loc_14000D378
0x14000d341  mov     al, [rcx+2]
0x14000d344  mov     [r8], edx
0x14000d347  cmp     al, 1
0x14000d349  jnz     short loc_14000D363
0x14000d34b  mov     r9d, 2
0x14000d351  mov     [rsp+28h+arg_8], dx
0x14000d356  movzx   eax, dx
0x14000d359  lea     r8, [rsp+28h+arg_8]
0x14000d35e  mov     edx, r9d
0x14000d361  jmp     short loc_14000D36F
0x14000d363  cmp     al, 2
0x14000d365  jnz     short loc_14000D378
0x14000d367  mov     edx, 4; DestinationSize
0x14000d36c  mov     r9d, edx; SourceSize
0x14000d36f  mov     rcx, [rcx+10h]; Destination
0x14000d373  call    memcpy_s
0x14000d378  add     rsp, 28h
0x14000d37c  retn
```
