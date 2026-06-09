# CTSThread::PushEventFilter(ITSEventFilter *)

- ea: `0x180026168`
- end: `0x18002622c`
- name: `?PushEventFilter@CTSThread@@AEAAJPEAVITSEventFilter@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, struct ITSEventFilter *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024bb0`
- `0x180028934`

## callees

- `0x18000160c`
- `0x1800232d8`
- `0x180026168`
- `0x18002c010`

## string_xrefs

- `0x1800261c1`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`

## pseudocode

```c
__int64 __fastcall CTSThread::PushEventFilter(CTSThread *this, struct ITSEventFilter *a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  const char *v7; // [rsp+50h] [rbp-18h] BYREF
  const char *v8; // [rsp+58h] [rbp-10h] BYREF
  int v9; // [rsp+70h] [rbp+8h] BYREF
  int v10; // [rsp+80h] [rbp+18h] BYREF
  const char *v11; // [rsp+88h] [rbp+20h] BYREF

  if ( CVPtrList::AddHead((CTSThread *)((char *)this + 200), a2) )
  {
    (*(void (__fastcall **)(struct ITSEventFilter *))(*(_QWORD *)a2 + 8LL))(a2);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v9 = 2386;
      v11 = "PushEventFilter";
      v10 = -2147467259;
      v7 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      v8 = "Unable to add filter to queue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v3,
        (__int64)&byte_18003F5B7,
        v4,
        v5,
        (const unsigned __int16 **)&v8,
        (__int64)&v10,
        (const unsigned __int16 **)&v7,
        (__int64)&v9,
        (const unsigned __int16 **)&v11);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180026168  push    rbx
0x18002616a  sub     rsp, 60h
0x18002616e  mov     rbx, rdx
0x180026171  add     rcx, 0C8h; this
0x180026178  call    ?AddHead@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddHead(void *)
0x18002617d  test    rax, rax
0x180026180  jz      short loc_180026198
0x180026182  mov     rax, [rbx]
0x180026185  mov     rcx, rbx
0x180026188  mov     rax, [rax+8]
0x18002618c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026191  xor     eax, eax
0x180026193  jmp     loc_180026226
0x180026198  mov     eax, cs:dword_180044008
0x18002619e  cmp     eax, 2
0x1800261a1  jbe     short loc_180026221
0x1800261a3  lea     rax, aPusheventfilte; "PushEventFilter"
0x1800261aa  mov     [rsp+68h+arg_0], 952h
0x1800261b2  mov     [rsp+68h+arg_18], rax
0x1800261ba  lea     rdx, byte_18003F5B7
0x1800261c1  lea     rax, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800261c8  mov     [rsp+68h+arg_10], 80004005h
0x1800261d3  mov     [rsp+68h+var_18], rax
0x1800261d8  lea     rax, aUnableToAddFil; "Unable to add filter to queue"
0x1800261df  mov     [rsp+68h+var_10], rax
0x1800261e4  lea     rax, [rsp+68h+arg_18]
0x1800261ec  mov     [rsp+68h+var_28], rax
0x1800261f1  lea     rax, [rsp+68h+arg_0]
0x1800261f6  mov     [rsp+68h+var_30], rax
0x1800261fb  lea     rax, [rsp+68h+var_18]
0x180026200  mov     [rsp+68h+var_38], rax
0x180026205  lea     rax, [rsp+68h+arg_10]
0x18002620d  mov     [rsp+68h+var_40], rax
0x180026212  lea     rax, [rsp+68h+var_10]
0x180026217  mov     [rsp+68h+var_48], rax
0x18002621c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180026221  mov     eax, 8007000Eh
0x180026226  add     rsp, 60h
0x18002622a  pop     rbx
0x18002622b  retn
```
