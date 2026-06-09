# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800155d4`
- end: `0x18001561d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000f2e4`
- `0x180012d18`
- `0x18001523c`

## callees

- `0x18000f160`
- `0x1800155d4`

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
0x1800155d4  sub     rsp, 28h
0x1800155d8  lea     r8, [rcx+4]; Source
0x1800155dc  cmp     [r8], edx
0x1800155df  jz      short loc_180015618
0x1800155e1  mov     al, [rcx+2]
0x1800155e4  mov     [r8], edx
0x1800155e7  cmp     al, 1
0x1800155e9  jnz     short loc_180015603
0x1800155eb  mov     r9d, 2
0x1800155f1  mov     [rsp+28h+arg_8], dx
0x1800155f6  movzx   eax, dx
0x1800155f9  lea     r8, [rsp+28h+arg_8]
0x1800155fe  mov     edx, r9d
0x180015601  jmp     short loc_18001560F
0x180015603  cmp     al, 2
0x180015605  jnz     short loc_180015618
0x180015607  mov     edx, 4; DestinationSize
0x18001560c  mov     r9d, edx; SourceSize
0x18001560f  mov     rcx, [rcx+10h]; Destination
0x180015613  call    memcpy_s
0x180015618  add     rsp, 28h
0x18001561c  retn
```
