# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::AddRef(void)

- ea: `0x18000b540`
- end: `0x18000b569`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEmptyVolumeCache@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b540`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 12);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x18000b540  mov     r9d, 7FFFFFFFh
0x18000b546  jmp     short loc_18000B556
0x18000b548  lea     edx, [r8+1]
0x18000b54c  mov     eax, r8d
0x18000b54f  lock cmpxchg [rcx+0Ch], edx
0x18000b554  jz      short loc_18000B561
0x18000b556  mov     r8d, [rcx+0Ch]
0x18000b55a  cmp     r8d, r9d
0x18000b55d  jnz     short loc_18000B548
0x18000b55f  jmp     short loc_18000B565
0x18000b561  lea     r9d, [r8+1]
0x18000b565  mov     eax, r9d
0x18000b568  retn
```
