# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(void)

- ea: `0x180005e30`
- end: `0x180005e59`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005e60`
- `0x180005e70`

## callees

- `0x180005e30`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 28);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 28), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x180005e30  mov     r9d, 7FFFFFFFh
0x180005e36  jmp     short loc_180005E46
0x180005e38  lea     edx, [r8+1]
0x180005e3c  mov     eax, r8d
0x180005e3f  lock cmpxchg [rcx+1Ch], edx
0x180005e44  jz      short loc_180005E51
0x180005e46  mov     r8d, [rcx+1Ch]
0x180005e4a  cmp     r8d, r9d
0x180005e4d  jnz     short loc_180005E38
0x180005e4f  jmp     short loc_180005E55
0x180005e51  lea     r9d, [r8+1]
0x180005e55  mov     eax, r9d
0x180005e58  retn
```
