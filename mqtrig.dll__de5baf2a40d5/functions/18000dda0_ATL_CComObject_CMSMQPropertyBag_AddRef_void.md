# ATL::CComObject<CMSMQPropertyBag>::AddRef(void)

- ea: `0x18000dda0`
- end: `0x18000ddb3`
- name: `?AddRef@?$CComObject@VCMSMQPropertyBag@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ddc0`

## callees

- `0x18000dda0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQPropertyBag>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 16);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000dda0  mov     edx, [rcx+10h]
0x18000dda3  mov     eax, 7FFFFFFFh
0x18000dda8  cmp     edx, eax
0x18000ddaa  jz      short locret_18000DDB2
0x18000ddac  lea     eax, [rdx+1]
0x18000ddaf  mov     [rcx+10h], eax
0x18000ddb2  retn
```
