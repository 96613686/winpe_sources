# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002bf0`
- end: `0x180002c12`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002bf0`
- `0x180002c18`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180002bf0  test    rcx, rcx
0x180002bf3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMSEnumDiscRecordersObj@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMSEnumDiscRecordersObj>>::CreateInstance(void *,_GUID const &,void * *)
0x180002bf9  test    r8, r8
0x180002bfc  jnz     short loc_180002C05
0x180002bfe  mov     eax, 80004003h
0x180002c03  jmp     short locret_180002C11
0x180002c05  mov     qword ptr [r8], 0
0x180002c0c  mov     eax, 80040110h
0x180002c11  retn
```
