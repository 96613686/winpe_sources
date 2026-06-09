# ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)

- ea: `0x18000d0e8`
- end: `0x18000d106`
- name: `??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `25`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d0dc`
- `0x18000d200`
- `0x18000d430`
- `0x18000d6e0`
- `0x180015f10`
- `0x180015fc4`
- `0x1800160ac`
- `0x180017ea0`
- `0x1800182b0`
- `0x1800188e0`
- `0x18001b8f0`
- `0x18001e8b0`
- `0x18001eb30`
- `0x18001ede0`
- `0x18001efa0`
- `0x18001f170`
- `0x18001f680`
- `0x18001f7e0`
- `0x18001f990`
- `0x18001fb30`
- `0x1800216e8`
- `0x180021770`
- `0x180021e14`
- `0x1800224cc`
- `0x180028310`

## callees

- `0x18000d0e8`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000d0e8  sub     rsp, 28h
0x18000d0ec  mov     rcx, [rcx]
0x18000d0ef  test    rcx, rcx
0x18000d0f2  jz      short loc_18000D101
0x18000d0f4  mov     rax, [rcx]
0x18000d0f7  mov     rax, [rax+10h]
0x18000d0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d100  nop
0x18000d101  add     rsp, 28h
0x18000d105  retn
```
