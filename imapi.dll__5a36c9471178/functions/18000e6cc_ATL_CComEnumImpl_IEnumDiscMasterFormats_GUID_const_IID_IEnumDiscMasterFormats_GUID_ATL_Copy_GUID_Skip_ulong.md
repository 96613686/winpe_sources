# ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Skip(ulong)

- ea: `0x18000e6cc`
- end: `0x18000e6fe`
- name: `?Skip@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJK@Z`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e680`

## callees

- `0x18000e6cc`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Skip(
        __int64 a1,
        unsigned int a2)
{
  __int64 v4; // rax
  unsigned int v5; // ecx
  __int64 v6; // rax

  if ( !a2 )
    return 2147942487LL;
  v4 = *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 32);
  v5 = a2;
  v6 = v4 >> 4;
  if ( a2 > (unsigned int)v6 )
    v5 = v6;
  *(_QWORD *)(a1 + 32) += 16LL * v5;
  return a2 != v5;
}

```

## disassembly

```asm
0x18000e6cc  mov     r8, rcx
0x18000e6cf  test    edx, edx
0x18000e6d1  jnz     short loc_18000E6D9
0x18000e6d3  mov     eax, 80070057h
0x18000e6d8  retn
0x18000e6d9  mov     rax, [rcx+18h]
0x18000e6dd  sub     rax, [rcx+20h]
0x18000e6e1  mov     ecx, edx
0x18000e6e3  sar     rax, 4
0x18000e6e7  cmp     edx, eax
0x18000e6e9  cmova   ecx, eax
0x18000e6ec  mov     eax, ecx
0x18000e6ee  shl     rax, 4
0x18000e6f2  add     [r8+20h], rax
0x18000e6f6  xor     eax, eax
0x18000e6f8  cmp     edx, ecx
0x18000e6fa  setnz   al
0x18000e6fd  retn
```
