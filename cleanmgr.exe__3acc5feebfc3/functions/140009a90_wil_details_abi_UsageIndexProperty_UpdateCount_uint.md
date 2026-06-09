# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140009a90`
- end: `0x140009ad9`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140007778`
- `0x140008dc8`
- `0x140009610`

## callees

- `0x1400069a8`
- `0x140009a90`

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
0x140009a90  sub     rsp, 28h
0x140009a94  lea     r8, [rcx+4]; Source
0x140009a98  cmp     [r8], edx
0x140009a9b  jz      short loc_140009AD4
0x140009a9d  mov     al, [rcx+2]
0x140009aa0  mov     [r8], edx
0x140009aa3  cmp     al, 1
0x140009aa5  jnz     short loc_140009ABF
0x140009aa7  mov     r9d, 2
0x140009aad  mov     [rsp+28h+arg_8], dx
0x140009ab2  movzx   eax, dx
0x140009ab5  lea     r8, [rsp+28h+arg_8]
0x140009aba  mov     edx, r9d
0x140009abd  jmp     short loc_140009ACB
0x140009abf  cmp     al, 2
0x140009ac1  jnz     short loc_140009AD4
0x140009ac3  mov     edx, 4; DestinationSize
0x140009ac8  mov     r9d, edx; SourceSize
0x140009acb  mov     rcx, [rcx+10h]; Destination
0x140009acf  call    memcpy_s
0x140009ad4  add     rsp, 28h
0x140009ad8  retn
```
