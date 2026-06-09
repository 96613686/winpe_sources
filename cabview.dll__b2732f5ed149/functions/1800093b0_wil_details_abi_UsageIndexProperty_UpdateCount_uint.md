# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800093b0`
- end: `0x1800093f9`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005898`
- `0x180007ddc`
- `0x180008994`

## callees

- `0x1800093b0`
- `0x18000a310`

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
0x1800093b0  sub     rsp, 28h
0x1800093b4  lea     r8, [rcx+4]; Source
0x1800093b8  cmp     [r8], edx
0x1800093bb  jz      short loc_1800093F4
0x1800093bd  mov     al, [rcx+2]
0x1800093c0  mov     [r8], edx
0x1800093c3  cmp     al, 1
0x1800093c5  jnz     short loc_1800093DF
0x1800093c7  mov     r9d, 2
0x1800093cd  mov     [rsp+28h+arg_8], dx
0x1800093d2  movzx   eax, dx
0x1800093d5  lea     r8, [rsp+28h+arg_8]
0x1800093da  mov     edx, r9d
0x1800093dd  jmp     short loc_1800093EB
0x1800093df  cmp     al, 2
0x1800093e1  jnz     short loc_1800093F4
0x1800093e3  mov     edx, 4; DestinationSize
0x1800093e8  mov     r9d, edx; SourceSize
0x1800093eb  mov     rcx, [rcx+10h]; Destination
0x1800093ef  call    memcpy_s
0x1800093f4  add     rsp, 28h
0x1800093f8  retn
```
