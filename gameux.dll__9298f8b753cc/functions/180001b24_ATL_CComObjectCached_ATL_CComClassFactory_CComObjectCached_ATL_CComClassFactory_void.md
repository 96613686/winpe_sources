# ATL::CComObjectCached<ATL::CComClassFactory>::CComObjectCached<ATL::CComClassFactory>(void *)

- ea: `0x180001b24`
- end: `0x180001b3f`
- name: `??0?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@PEAX@Z`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002110`

## callees

- `0x180001b48`

## pseudocode

```c
_QWORD *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::CComObjectCached<ATL::CComClassFactory>(
        ATL::CComClassFactory *a1)
{
  _QWORD *v1; // rcx
  _QWORD *result; // rax

  ATL::CComClassFactory::CComClassFactory(a1);
  result = v1;
  *v1 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
  return result;
}

```

## disassembly

```asm
0x180001b24  sub     rsp, 28h
0x180001b28  call    ??0CComClassFactory@ATL@@QEAA@XZ; ATL::CComClassFactory::CComClassFactory(void)
0x180001b2d  lea     rdx, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180001b34  mov     rax, rcx
0x180001b37  mov     [rcx], rdx
0x180001b3a  add     rsp, 28h
0x180001b3e  retn
```
