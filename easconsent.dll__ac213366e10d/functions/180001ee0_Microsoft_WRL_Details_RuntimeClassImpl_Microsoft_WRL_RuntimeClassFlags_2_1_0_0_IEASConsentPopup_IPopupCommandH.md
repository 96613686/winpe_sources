# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::AddRef(void)

- ea: `0x180001ee0`
- end: `0x180001f09`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f10`

## callees

- `0x180001ee0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 20);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180001ee0  mov     r9d, 7FFFFFFFh
0x180001ee6  jmp     short loc_180001EF6
0x180001ee8  lea     edx, [r8+1]
0x180001eec  mov     eax, r8d
0x180001eef  lock cmpxchg [rcx+14h], edx
0x180001ef4  jz      short loc_180001F01
0x180001ef6  mov     r8d, [rcx+14h]
0x180001efa  cmp     r8d, r9d
0x180001efd  jnz     short loc_180001EE8
0x180001eff  jmp     short loc_180001F05
0x180001f01  lea     r9d, [r8+1]
0x180001f05  mov     eax, r9d
0x180001f08  retn
```
