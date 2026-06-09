# CTSThread::OnPostExitThreadProc(void)

- ea: `0x180025f34`
- end: `0x180025fc6`
- name: `?OnPostExitThreadProc@CTSThread@@AEAAXXZ`
- size: `146`
- prototype: `void __fastcall(CTSThread *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180027150`

## callees

- `0x1800010f8`
- `0x180025be4`
- `0x180025f34`
- `0x180027b6c`
- `0x180027b98`

## string_xrefs

- `0x180025f4e`: `Thread has exited revert back to initialized - Start`
- `0x180025f99`: `Thread has exited revert back to initialized - Done`

## pseudocode

```c
void __fastcall CTSThread::OnPostExitThreadProc(CTSThread *this, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  const char *v8; // [rsp+40h] [rbp+8h] BYREF

  if ( (unsigned int)dword_180044008 > 5 )
  {
    v8 = "Thread has exited revert back to initialized - Start";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)byte_18003F9A9,
      a3,
      a4,
      (const unsigned __int16 **)&v8);
  }
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  CTSThread::InternalRundownThread(this);
  CTSReaderWriterLock::WriteUnlock((CTSThread *)((char *)this + 148));
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v8 = "Thread has exited revert back to initialized - Done";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v5,
      (__int64)qword_18003F988,
      v6,
      v7,
      (const unsigned __int16 **)&v8);
  }
}

```

## disassembly

```asm
0x180025f34  mov     r11, rsp
0x180025f37  mov     [r11+10h], rbx
0x180025f3b  push    rdi
0x180025f3c  sub     rsp, 30h
0x180025f40  mov     rdi, rcx
0x180025f43  mov     eax, cs:dword_180044008
0x180025f49  cmp     eax, 5
0x180025f4c  jbe     short loc_180025F6D
0x180025f4e  lea     rax, aThreadHasExite_0; "Thread has exited revert back to initia"...
0x180025f55  mov     [r11+8], rax
0x180025f59  lea     rdx, byte_18003F9A9
0x180025f60  lea     rax, [r11+8]
0x180025f64  mov     [r11-18h], rax
0x180025f68  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180025f6d  lea     rbx, [rdi+94h]
0x180025f74  mov     rcx, rbx; this
0x180025f77  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x180025f7c  mov     rcx, rdi; this
0x180025f7f  call    ?InternalRundownThread@CTSThread@@AEAAJXZ; CTSThread::InternalRundownThread(void)
0x180025f84  mov     rcx, rbx; this
0x180025f87  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x180025f8c  mov     r11d, cs:dword_180044008
0x180025f93  cmp     r11d, 5
0x180025f97  jbe     short loc_180025FBB
0x180025f99  lea     rax, aThreadHasExite; "Thread has exited revert back to initia"...
0x180025fa0  mov     [rsp+38h+arg_0], rax
0x180025fa5  lea     rdx, qword_18003F988
0x180025fac  lea     rax, [rsp+38h+arg_0]
0x180025fb1  mov     [rsp+38h+var_18], rax
0x180025fb6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180025fbb  mov     rbx, [rsp+38h+arg_8]
0x180025fc0  add     rsp, 30h
0x180025fc4  pop     rdi
0x180025fc5  retn
```
