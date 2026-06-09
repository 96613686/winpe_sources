# ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Next(ulong,_GUID *,ulong *)

- ea: `0x18000c990`
- end: `0x18000c9d9`
- name: `?Next@?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@UEAAJKPEAU_GUID@@PEAK@Z`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c9e0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000c9c6`
- `KERNEL32!LeaveCriticalSection` at `0x18000c9c6`
- `KERNEL32!EnterCriticalSection` at `0x18000c9aa`
- `KERNEL32!EnterCriticalSection` at `0x18000c9aa`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Next(
        __int64 a1,
        unsigned int a2,
        char *a3,
        _DWORD *a4)
{
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  LODWORD(a4) = ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Next(
                  a1,
                  a2,
                  a3,
                  a4);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x18000c990  push    rbx
0x18000c992  push    rbp
0x18000c993  push    rsi
0x18000c994  push    rdi
0x18000c995  push    r14
0x18000c997  sub     rsp, 20h
0x18000c99b  mov     rbp, rcx
0x18000c99e  mov     rbx, r9
0x18000c9a1  add     rcx, 68h ; 'h'; lpCriticalSection
0x18000c9a5  mov     rdi, r8
0x18000c9a8  mov     esi, edx
0x18000c9aa  call    cs:__imp_EnterCriticalSection
0x18000c9b0  mov     r9, rbx
0x18000c9b3  mov     r8, rdi
0x18000c9b6  mov     edx, esi
0x18000c9b8  mov     rcx, rbp
0x18000c9bb  call    ?Next@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJKPEAU_GUID@@PEAK@Z; ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Next(ulong,_GUID *,ulong *)
0x18000c9c0  lea     rcx, [rbp+68h]; lpCriticalSection
0x18000c9c4  mov     ebx, eax
0x18000c9c6  call    cs:__imp_LeaveCriticalSection
0x18000c9cc  mov     eax, ebx
0x18000c9ce  add     rsp, 20h
0x18000c9d2  pop     r14
0x18000c9d4  pop     rdi
0x18000c9d5  pop     rsi
0x18000c9d6  pop     rbp
0x18000c9d7  pop     rbx
0x18000c9d8  retn
```
