# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18001a158`
- end: `0x18001a1a1`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016d78`
- `0x180018cc8`
- `0x180019a40`

## callees

- `0x18001a158`
- `0x18001aea4`

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
0x18001a158  sub     rsp, 28h
0x18001a15c  lea     r8, [rcx+4]; Source
0x18001a160  cmp     [r8], edx
0x18001a163  jz      short loc_18001A19C
0x18001a165  mov     al, [rcx+2]
0x18001a168  mov     [r8], edx
0x18001a16b  cmp     al, 1
0x18001a16d  jnz     short loc_18001A187
0x18001a16f  mov     r9d, 2
0x18001a175  mov     [rsp+28h+arg_8], dx
0x18001a17a  movzx   eax, dx
0x18001a17d  lea     r8, [rsp+28h+arg_8]
0x18001a182  mov     edx, r9d
0x18001a185  jmp     short loc_18001A193
0x18001a187  cmp     al, 2
0x18001a189  jnz     short loc_18001A19C
0x18001a18b  mov     edx, 4; DestinationSize
0x18001a190  mov     r9d, edx; SourceSize
0x18001a193  mov     rcx, [rcx+10h]; Destination
0x18001a197  call    memcpy_s
0x18001a19c  add     rsp, 28h
0x18001a1a0  retn
```
