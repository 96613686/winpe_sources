# CMSMQQueueInfos::~CMSMQQueueInfos(void)

- ea: `0x18001f0a8`
- end: `0x18001f133`
- name: `??1CMSMQQueueInfos@@UEAA@XZ`
- size: `139`
- prototype: `void __fastcall(CMSMQQueueInfos *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ac58`
- `0x18000b050`
- `0x18000b600`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x180003848`
- `0x18001f0a8`
- `0x18001fbbc`
- `0x18001fbe8`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001f115`
- `KERNEL32!DeleteCriticalSection` at `0x18001f115`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f0b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001f0b8`
- `mqrt!MQLocateEnd` at `0x18001f103`
- `mqrt!MQLocateEnd` at `0x18001f103`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQQueueInfos::~CMSMQQueueInfos(CMSMQQueueInfos *this)
{
  void *v2; // rcx

  SysFreeString(*((BSTR *)this + 16));
  CMSMQQuery::FreeRestriction(*((struct tagMQRESTRICTION **)this + 17));
  operator delete(*((void **)this + 17));
  CMSMQQuery::FreeColumnSet(*((struct tagMQCOLUMNSET **)this + 18));
  operator delete(*((void **)this + 18));
  operator delete(*((void **)this + 19));
  v2 = (void *)*((_QWORD *)this + 15);
  if ( v2 )
  {
    MQLocateEnd(v2);
    *((_QWORD *)this + 15) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  R<IADs>::~R<IADs>((char *)this + 72);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQQueueInfos *)((char *)this + 24));
}

```

## disassembly

```asm
0x18001f0a8  push    rbx
0x18001f0aa  sub     rsp, 20h
0x18001f0ae  mov     rbx, rcx
0x18001f0b1  mov     rcx, [rcx+80h]; bstrString
0x18001f0b8  call    cs:__imp_SysFreeString
0x18001f0be  mov     rcx, [rbx+88h]; struct tagMQRESTRICTION *
0x18001f0c5  call    ?FreeRestriction@CMSMQQuery@@SAXPEAUtagMQRESTRICTION@@@Z; CMSMQQuery::FreeRestriction(tagMQRESTRICTION *)
0x18001f0ca  mov     rcx, [rbx+88h]; Block
0x18001f0d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f0d6  mov     rcx, [rbx+90h]; struct tagMQCOLUMNSET *
0x18001f0dd  call    ?FreeColumnSet@CMSMQQuery@@SAXPEAUtagMQCOLUMNSET@@@Z; CMSMQQuery::FreeColumnSet(tagMQCOLUMNSET *)
0x18001f0e2  mov     rcx, [rbx+90h]; Block
0x18001f0e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f0ee  mov     rcx, [rbx+98h]; Block
0x18001f0f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001f0fa  mov     rcx, [rbx+78h]; hEnum
0x18001f0fe  test    rcx, rcx
0x18001f101  jz      short loc_18001F111
0x18001f103  call    cs:__imp_MQLocateEnd
0x18001f109  mov     qword ptr [rbx+78h], 0
0x18001f111  lea     rcx, [rbx+50h]; lpCriticalSection
0x18001f115  call    cs:__imp_DeleteCriticalSection
0x18001f11b  nop
0x18001f11c  lea     rcx, [rbx+48h]
0x18001f120  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18001f125  lea     rcx, [rbx+18h]; this
0x18001f129  add     rsp, 20h
0x18001f12d  pop     rbx
0x18001f12e  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
