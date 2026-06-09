# CTS_TLS_ThreadDescriptor::AddThreadToList(ITSThread *)

- ea: `0x1800233b8`
- end: `0x180023477`
- name: `?AddThreadToList@CTS_TLS_ThreadDescriptor@@AEAAJPEAVITSThread@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CTS_TLS_ThreadDescriptor *__hidden this, struct ITSThread *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800234e0`
- `0x180027150`

## callees

- `0x18000160c`
- `0x1800232d8`
- `0x1800233b8`
- `0x18002c010`

## string_xrefs

- `0x180023413`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x1800233f5`: `AddThreadToList`
- `0x180023426`: `Fail to add thread to list`

## pseudocode

```c
__int64 __fastcall CTS_TLS_ThreadDescriptor::AddThreadToList(CTS_TLS_ThreadDescriptor *this, struct ITSThread *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned int v6; // ebx
  const char *v8; // [rsp+50h] [rbp-18h] BYREF
  const char *v9; // [rsp+58h] [rbp-10h] BYREF
  int v10; // [rsp+70h] [rbp+8h] BYREF
  int v11; // [rsp+80h] [rbp+18h] BYREF
  const char *v12; // [rsp+88h] [rbp+20h] BYREF

  if ( CVPtrList::AddHead((CTS_TLS_ThreadDescriptor *)((char *)this + 48), a2) )
  {
    (*(void (__fastcall **)(struct ITSThread *))(*(_QWORD *)a2 + 8LL))(a2);
    return 0;
  }
  else
  {
    v6 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v10 = 3446;
      v12 = "AddThreadToList";
      v11 = -2147467259;
      v8 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v9 = "Fail to add thread to list";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (__int64)byte_18003F28B,
        v4,
        v5,
        (const unsigned __int16 **)&v9,
        (__int64)&v11,
        (const unsigned __int16 **)&v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v12);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800233b8  push    rbx
0x1800233ba  sub     rsp, 60h
0x1800233be  mov     rbx, rdx
0x1800233c1  add     rcx, 30h ; '0'; this
0x1800233c5  call    ?AddHead@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddHead(void *)
0x1800233ca  test    rax, rax
0x1800233cd  jz      short loc_1800233E5
0x1800233cf  mov     rax, [rbx]
0x1800233d2  mov     rcx, rbx
0x1800233d5  mov     rax, [rax+8]
0x1800233d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233de  xor     ebx, ebx
0x1800233e0  jmp     loc_18002346F
0x1800233e5  mov     eax, cs:dword_180044008
0x1800233eb  mov     ebx, 80004005h
0x1800233f0  cmp     eax, 2
0x1800233f3  jbe     short loc_18002346F
0x1800233f5  lea     rax, aAddthreadtolis; "AddThreadToList"
0x1800233fc  mov     [rsp+68h+arg_0], 0D76h
0x180023404  mov     [rsp+68h+arg_18], rax
0x18002340c  lea     rdx, byte_18003F28B
0x180023413  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x18002341a  mov     [rsp+68h+arg_10], ebx
0x180023421  mov     [rsp+68h+var_18], rax
0x180023426  lea     rax, aFailToAddThrea_0; "Fail to add thread to list"
0x18002342d  mov     [rsp+68h+var_10], rax
0x180023432  lea     rax, [rsp+68h+arg_18]
0x18002343a  mov     [rsp+68h+var_28], rax
0x18002343f  lea     rax, [rsp+68h+arg_0]
0x180023444  mov     [rsp+68h+var_30], rax
0x180023449  lea     rax, [rsp+68h+var_18]
0x18002344e  mov     [rsp+68h+var_38], rax
0x180023453  lea     rax, [rsp+68h+arg_10]
0x18002345b  mov     [rsp+68h+var_40], rax
0x180023460  lea     rax, [rsp+68h+var_10]
0x180023465  mov     [rsp+68h+var_48], rax
0x18002346a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002346f  mov     eax, ebx
0x180023471  add     rsp, 60h
0x180023475  pop     rbx
0x180023476  retn
```
