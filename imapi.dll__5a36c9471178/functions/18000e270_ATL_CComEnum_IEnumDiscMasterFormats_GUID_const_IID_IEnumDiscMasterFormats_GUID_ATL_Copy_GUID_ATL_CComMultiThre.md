# ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Reset(void)

- ea: `0x18000e270`
- end: `0x18000e2a6`
- name: `?Reset@?$CComEnum@UIEnumDiscMasterFormats@@$1?IID_IEnumDiscMasterFormats@@3U_GUID@@BU3@V?$_Copy@U_GUID@@@ATL@@VCComMultiThreadModel@5@@ATL@@UEAAJXZ`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e293`
- `KERNEL32!LeaveCriticalSection` at `0x18000e293`
- `KERNEL32!EnterCriticalSection` at `0x18000e281`
- `KERNEL32!EnterCriticalSection` at `0x18000e281`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumDiscMasterFormats,&_GUID const IID_IEnumDiscMasterFormats,_GUID,ATL::_Copy<_GUID>,ATL::CComMultiThreadModel>::Reset(
        __int64 a1)
{
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  return 0;
}

```

## disassembly

```asm
0x18000e270  mov     [rsp+arg_0], rbx
0x18000e275  push    rdi
0x18000e276  sub     rsp, 20h
0x18000e27a  mov     rdi, rcx
0x18000e27d  add     rcx, 68h ; 'h'; lpCriticalSection
0x18000e281  call    cs:__imp_EnterCriticalSection
0x18000e287  mov     rax, [rdi+10h]
0x18000e28b  lea     rcx, [rdi+68h]; lpCriticalSection
0x18000e28f  mov     [rdi+20h], rax
0x18000e293  call    cs:__imp_LeaveCriticalSection
0x18000e299  mov     rbx, [rsp+28h+arg_0]
0x18000e29e  xor     eax, eax
0x18000e2a0  add     rsp, 20h
0x18000e2a4  pop     rdi
0x18000e2a5  retn
```
