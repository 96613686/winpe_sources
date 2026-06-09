# RasConnectionBase::~RasConnectionBase(void)

- ea: `0x1800088c8`
- end: `0x180008916`
- name: `??1RasConnectionBase@@QEAA@XZ`
- size: `78`
- prototype: `void __fastcall(RasConnectionBase *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000871c`

## callees

- `0x180004d04`
- `0x180008168`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800088d8`
- `KERNEL32!DeleteCriticalSection` at `0x1800088d8`

## pseudocode

```c
void __fastcall RasConnectionBase::~RasConnectionBase(RasConnectionBase *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 23);
  std::wstring::_Tidy_deallocate((char *)this + 152);
  std::wstring::_Tidy_deallocate((char *)this + 96);
  std::wstring::_Tidy_deallocate((char *)this + 64);
  std::wstring::_Tidy_deallocate((char *)this + 8);
}

```

## disassembly

```asm
0x1800088c8  push    rbx
0x1800088ca  sub     rsp, 20h
0x1800088ce  mov     rbx, rcx
0x1800088d1  add     rcx, 0D8h; lpCriticalSection
0x1800088d8  call    cs:__imp_DeleteCriticalSection
0x1800088de  lea     rcx, [rbx+0B8h]
0x1800088e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800088ea  lea     rcx, [rbx+98h]
0x1800088f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800088f6  lea     rcx, [rbx+60h]
0x1800088fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800088ff  lea     rcx, [rbx+40h]
0x180008903  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180008908  lea     rcx, [rbx+8]
0x18000890c  add     rsp, 20h
0x180008910  pop     rbx
0x180008911  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
