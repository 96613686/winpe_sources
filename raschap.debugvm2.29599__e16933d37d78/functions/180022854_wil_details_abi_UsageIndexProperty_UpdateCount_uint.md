# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180022854`
- end: `0x18002289d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180011d74`
- `0x18001fc70`
- `0x18002217c`

## callees

- `0x1800118a4`
- `0x180022854`

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
0x180022854  sub     rsp, 28h
0x180022858  lea     r8, [rcx+4]; Source
0x18002285c  cmp     [r8], edx
0x18002285f  jz      short loc_180022898
0x180022861  mov     al, [rcx+2]
0x180022864  mov     [r8], edx
0x180022867  cmp     al, 1
0x180022869  jnz     short loc_180022883
0x18002286b  mov     r9d, 2
0x180022871  mov     [rsp+28h+arg_8], dx
0x180022876  movzx   eax, dx
0x180022879  lea     r8, [rsp+28h+arg_8]
0x18002287e  mov     edx, r9d
0x180022881  jmp     short loc_18002288F
0x180022883  cmp     al, 2
0x180022885  jnz     short loc_180022898
0x180022887  mov     edx, 4; DestinationSize
0x18002288c  mov     r9d, edx; SourceSize
0x18002288f  mov     rcx, [rcx+10h]; Destination
0x180022893  call    memcpy_s
0x180022898  add     rsp, 28h
0x18002289c  retn
```
