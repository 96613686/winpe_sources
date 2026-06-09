# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800095cc`
- end: `0x180009616`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180003958`
- `0x180006250`
- `0x180008dfc`

## callees

- `0x1800095cc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000960b`
- `msvcrt!memcpy_s` at `0x18000960b`

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
0x1800095cc  sub     rsp, 28h
0x1800095d0  lea     r8, [rcx+4]; Source
0x1800095d4  cmp     [r8], edx
0x1800095d7  jz      short loc_180009611
0x1800095d9  mov     al, [rcx+2]
0x1800095dc  mov     [r8], edx
0x1800095df  cmp     al, 1
0x1800095e1  jnz     short loc_1800095FB
0x1800095e3  mov     r9d, 2
0x1800095e9  mov     [rsp+28h+arg_8], dx
0x1800095ee  movzx   eax, dx
0x1800095f1  lea     r8, [rsp+28h+arg_8]
0x1800095f6  mov     edx, r9d
0x1800095f9  jmp     short loc_180009607
0x1800095fb  cmp     al, 2
0x1800095fd  jnz     short loc_180009611
0x1800095ff  mov     edx, 4; DestinationSize
0x180009604  mov     r9d, edx; SourceSize
0x180009607  mov     rcx, [rcx+10h]; Destination
0x18000960b  call    cs:__imp_memcpy_s
0x180009611  add     rsp, 28h
0x180009615  retn
```
