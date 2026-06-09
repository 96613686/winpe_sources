# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::AddRef(void)

- ea: `0x180009720`
- end: `0x180009749`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009750`

## callees

- `0x180009720`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::AddRef(
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
0x180009720  mov     r9d, 7FFFFFFFh
0x180009726  jmp     short loc_180009736
0x180009728  lea     edx, [r8+1]
0x18000972c  mov     eax, r8d
0x18000972f  lock cmpxchg [rcx+14h], edx
0x180009734  jz      short loc_180009741
0x180009736  mov     r8d, [rcx+14h]
0x18000973a  cmp     r8d, r9d
0x18000973d  jnz     short loc_180009728
0x18000973f  jmp     short loc_180009745
0x180009741  lea     r9d, [r8+1]
0x180009745  mov     eax, r9d
0x180009748  retn
```
