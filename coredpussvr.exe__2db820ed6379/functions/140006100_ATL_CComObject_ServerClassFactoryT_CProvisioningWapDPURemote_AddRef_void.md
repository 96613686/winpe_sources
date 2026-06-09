# ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::AddRef(void)

- ea: `0x140006100`
- end: `0x140006129`
- name: `?AddRef@?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@UEAAKXZ`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006100`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::AddRef(__int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x140006100  mov     r9d, 7FFFFFFFh
0x140006106  jmp     short loc_140006116
0x140006108  lea     edx, [r8+1]
0x14000610c  mov     eax, r8d
0x14000610f  lock cmpxchg [rcx+8], edx
0x140006114  jz      short loc_140006121
0x140006116  mov     r8d, [rcx+8]
0x14000611a  cmp     r8d, r9d
0x14000611d  jnz     short loc_140006108
0x14000611f  jmp     short loc_140006125
0x140006121  lea     r9d, [r8+1]
0x140006125  mov     eax, r9d
0x140006128  retn
```
