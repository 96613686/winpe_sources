# ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Skip(ulong)

- ea: `0x18000e680`
- end: `0x18000e6c6`
- name: `?Skip@?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@UEAAJK@Z`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e6cc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e6ae`
- `KERNEL32!LeaveCriticalSection` at `0x18000e6ae`
- `KERNEL32!EnterCriticalSection` at `0x18000e698`
- `KERNEL32!EnterCriticalSection` at `0x18000e698`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Skip(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  v4 = ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Skip(
         a1,
         a2);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  return v4;
}

```

## disassembly

```asm
0x18000e680  mov     [rsp+arg_0], rbx
0x18000e685  mov     [rsp+arg_8], rsi
0x18000e68a  push    rdi
0x18000e68b  sub     rsp, 20h
0x18000e68f  mov     rdi, rcx
0x18000e692  mov     ebx, edx
0x18000e694  add     rcx, 68h ; 'h'; lpCriticalSection
0x18000e698  call    cs:__imp_EnterCriticalSection
0x18000e69e  mov     edx, ebx
0x18000e6a0  mov     rcx, rdi
0x18000e6a3  call    ?Skip@?$CComEnumImpl@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@@ATL@@UEAAJK@Z; ATL::CComEnumImpl<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>>::Skip(ulong)
0x18000e6a8  lea     rcx, [rdi+68h]; lpCriticalSection
0x18000e6ac  mov     ebx, eax
0x18000e6ae  call    cs:__imp_LeaveCriticalSection
0x18000e6b4  mov     rsi, [rsp+28h+arg_8]
0x18000e6b9  mov     eax, ebx
0x18000e6bb  mov     rbx, [rsp+28h+arg_0]
0x18000e6c0  add     rsp, 20h
0x18000e6c4  pop     rdi
0x18000e6c5  retn
```
