# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180009a88`
- end: `0x180009ad1`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800035a4`
- `0x180006954`
- `0x180009200`

## callees

- `0x180003404`
- `0x180009a88`

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
0x180009a88  sub     rsp, 28h
0x180009a8c  lea     r8, [rcx+4]; Source
0x180009a90  cmp     [r8], edx
0x180009a93  jz      short loc_180009ACC
0x180009a95  mov     al, [rcx+2]
0x180009a98  mov     [r8], edx
0x180009a9b  cmp     al, 1
0x180009a9d  jnz     short loc_180009AB7
0x180009a9f  mov     r9d, 2
0x180009aa5  mov     [rsp+28h+arg_8], dx
0x180009aaa  movzx   eax, dx
0x180009aad  lea     r8, [rsp+28h+arg_8]
0x180009ab2  mov     edx, r9d
0x180009ab5  jmp     short loc_180009AC3
0x180009ab7  cmp     al, 2
0x180009ab9  jnz     short loc_180009ACC
0x180009abb  mov     edx, 4; DestinationSize
0x180009ac0  mov     r9d, edx; SourceSize
0x180009ac3  mov     rcx, [rcx+10h]; Destination
0x180009ac7  call    memcpy_s
0x180009acc  add     rsp, 28h
0x180009ad0  retn
```
