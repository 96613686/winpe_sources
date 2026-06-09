# _FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$0

- ea: `0x18001433a`
- end: `0x180014346`
- name: `_FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d16c`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>(a2 + 88);
}

```

## disassembly

```asm
0x18001433a  lea     rcx, [rdx+58h]
0x180014341  jmp     ??1?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@QEAA@XZ; Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>::~AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>(void)
```
