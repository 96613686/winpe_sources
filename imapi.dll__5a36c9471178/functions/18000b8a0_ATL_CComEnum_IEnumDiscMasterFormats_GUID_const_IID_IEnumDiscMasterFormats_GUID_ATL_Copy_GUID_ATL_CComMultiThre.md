# ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Clone(IEnumDiscMasterFormats * *)

- ea: `0x18000b8a0`
- end: `0x18000b8e8`
- name: `?Clone@?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@UEAAJPEAPEAUIEnumDiscMasterFormats@@@Z`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b8f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000b8d0`
- `KERNEL32!LeaveCriticalSection` at `0x18000b8d0`
- `KERNEL32!EnterCriticalSection` at `0x18000b8b9`
- `KERNEL32!EnterCriticalSection` at `0x18000b8b9`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Clone(
        __int64 a1,
        char **a2)
{
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  LODWORD(a2) = ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Clone(
                  a1,
                  a2);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x18000b8a0  mov     [rsp+arg_0], rbx
0x18000b8a5  mov     [rsp+arg_8], rsi
0x18000b8aa  push    rdi
0x18000b8ab  sub     rsp, 20h
0x18000b8af  mov     rdi, rcx
0x18000b8b2  mov     rbx, rdx
0x18000b8b5  add     rcx, 68h ; 'h'; lpCriticalSection
0x18000b8b9  call    cs:__imp_EnterCriticalSection
0x18000b8bf  mov     rdx, rbx
0x18000b8c2  mov     rcx, rdi
0x18000b8c5  call    ?Clone@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumDiscMasterFormats@@@Z; ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Clone(IEnumDiscMasterFormats * *)
0x18000b8ca  lea     rcx, [rdi+68h]; lpCriticalSection
0x18000b8ce  mov     ebx, eax
0x18000b8d0  call    cs:__imp_LeaveCriticalSection
0x18000b8d6  mov     rsi, [rsp+28h+arg_8]
0x18000b8db  mov     eax, ebx
0x18000b8dd  mov     rbx, [rsp+28h+arg_0]
0x18000b8e2  add     rsp, 20h
0x18000b8e6  pop     rdi
0x18000b8e7  retn
```
