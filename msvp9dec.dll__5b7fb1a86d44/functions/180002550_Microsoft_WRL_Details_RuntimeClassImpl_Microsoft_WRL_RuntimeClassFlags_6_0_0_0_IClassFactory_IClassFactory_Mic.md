# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)

- ea: `0x180002550`
- end: `0x180002578`
- name: `?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$0A@$0A@$0A@UIClassFactory@@U4@VNil@Details@23@V5623@V5623@@Details@WRL@Microsoft@@IEAAKXZ`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002090`
- `0x1800040b0`

## callees

- `0x180002550`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(
        __int64 a1)
{
  signed __int32 i; // edx

  for ( i = *(_DWORD *)(a1 + 20); i != 0x7FFFFFFF; i = *(_DWORD *)(a1 + 20) )
  {
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), i - 1, i) )
      break;
  }
  return (unsigned int)(i - 1);
}

```

## disassembly

```asm
0x180002550  mov     edx, [rcx+14h]
0x180002553  cmp     edx, 7FFFFFFFh
0x180002559  jz      short loc_180002574
0x18000255b  lea     r8d, [rdx-1]
0x18000255f  mov     eax, edx
0x180002561  lock cmpxchg [rcx+14h], r8d
0x180002567  jz      short loc_180002574
0x180002569  mov     edx, [rcx+14h]
0x18000256c  cmp     edx, 7FFFFFFFh
0x180002572  jnz     short loc_18000255B
0x180002574  lea     eax, [rdx-1]
0x180002577  retn
```
