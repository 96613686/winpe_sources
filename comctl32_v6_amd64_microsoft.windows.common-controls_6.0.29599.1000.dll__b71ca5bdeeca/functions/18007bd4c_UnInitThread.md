# UnInitThread

- ea: `0x18007bd4c`
- end: `0x18007be99`
- name: `UnInitThread`
- size: `333`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007bbb0`
- `0x180130150`
- `0x180141580`
- `0x1801bdfe0`

## callees

- `0x18007bd4c`
- `0x18007d2f8`
- `0x18008344c`
- `0x1800ed764`
- `0x1800f911c`
- `0x1800ff2b8`
- `0x180179af0`
- `0x180179b5c`
- `0x180179b7c`
- `0x18018c2c0`
- `0x18018c480`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007bd6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007bdd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007bd6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007bdd9`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18007be86`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18007be86`
- `GDI32!DeleteObject` at `0x18007be34`
- `GDI32!DeleteObject` at `0x18007be34`
- `UxTheme!BufferedPaintUnInit` at `0x18007bdb3`
- `UxTheme!BufferedPaintUnInit` at `0x18007bdb3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007bdbf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007bdbf`
- `DUser!DUserFlushDeferredMessages` at `0x18007bd89`
- `DUser!DUserFlushDeferredMessages` at `0x18007bd89`
- `DUser!DUserFlushMessages` at `0x18007bd83`
- `DUser!DUserFlushMessages` at `0x18007bd83`
- `DUser!DeleteHandle` at `0x18007bd9f`
- `DUser!DeleteHandle` at `0x18007bd9f`

## pseudocode

```c
__int64 UnInitThread()
{
  DirectUI *Value; // rdi
  struct DirectUI::ElTls *v2; // rdx
  DirectUI *v3; // rcx
  const char *v4; // rdx
  DirectUI *v5; // rbx
  void *v6; // rdx
  void *v7; // rcx
  DirectUI *v8; // rbx
  DirectUI::TransitionHandler *v9; // rcx
  void *v10; // rdx
  struct DirectUI::CStyleSheetManager *v11; // rax
  void *v12; // rdx

  if ( DirectUI::g_dwElSlot == -1 )
    return 2147500037LL;
  Value = (DirectUI *)TlsGetValue(DirectUI::g_dwElSlot);
  if ( !Value )
    return 2147745802LL;
  DUserFlushMessages();
  DUserFlushDeferredMessages();
  if ( (int)--*((_DWORD *)Value + 2) <= 0 )
  {
    DeleteHandle(*(_QWORD *)Value);
    DirectUI::UiaUninitThread(Value, v2);
    if ( *((_BYTE *)Value + 25) )
      BufferedPaintUnInit();
    if ( *((_BYTE *)Value + 24) )
      CoUninitialize();
    DirectUI::FontCache::UninitThread();
    if ( DirectUI::g_fTraceElementLeaks )
    {
      v3 = (DirectUI *)*((_QWORD *)TlsGetValue(DirectUI::g_dwElSlot) + 7);
      if ( v3 && *(_DWORD *)v3 )
      {
        DirectUI::BTreeLookup<DirectUI::Element *,DirectUI::CallstackTracker *>::Enum(
          v3,
          DirectUI::ReportLeakedElementsCB);
        DirectUI::ElementLeakTrace(
          (DirectUI *)"\n"
                      " Not all Elements were destroyed and can cause crashes later! \n"
                      " See the debugger output for the list of addresses or dump contents of DirectUI::g_pLeakedElementL"
                      "ist\n"
                      " For the object type, typecast each address to DirectUI::Element* in VS \n"
                      " OR \n"
                      " Use \"dds 0xaddress L1\" on x86 or \"dqs 0xaddress L1\" on x64 \n",
          v4);
      }
      DirectUI::DestroyLeakedElementList(v3);
      DirectUI::CallstackTracker::Uninit();
    }
    v5 = (DirectUI *)*((_QWORD *)Value + 2);
    (**(void (__fastcall ***)(DirectUI *, _QWORD))v5)(v5, 0);
    DirectUI::AccHFree(v5, v6);
    v7 = (void *)*((_QWORD *)Value + 9);
    if ( v7 )
    {
      DeleteObject(v7);
      *((_QWORD *)Value + 9) = 0;
    }
    v8 = (DirectUI *)*((_QWORD *)Value + 10);
    if ( v8 )
    {
      v9 = (DirectUI::TransitionHandler *)*((_QWORD *)Value + 10);
      *((_QWORD *)Value + 10) = 0;
      DirectUI::TransitionHandler::~TransitionHandler(v9);
      DirectUI::AccHFree(v8, v10);
    }
    v11 = DirectUI::CStyleSheetManager::s_Get();
    if ( v11 )
      DirectUI::StyleSheetCache::CCacheThread::UnregisterThread(
        (struct DirectUI::CStyleSheetManager *)((char *)v11 + 88),
        (unsigned int)v12);
    DirectUI::AccHFree(Value, v12);
    TlsSetValue(DirectUI::g_dwElSlot, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18007bd4c  mov     [rsp+arg_0], rbx
0x18007bd51  push    rdi
0x18007bd52  sub     rsp, 20h
0x18007bd56  mov     ecx, cs:?g_dwElSlot@DirectUI@@3KA; dwTlsIndex
0x18007bd5c  cmp     ecx, 0FFFFFFFFh
0x18007bd5f  jnz     short loc_18007BD6B
0x18007bd61  mov     eax, 80004005h
0x18007bd66  jmp     loc_18007BE8E
0x18007bd6b  call    cs:__imp_TlsGetValue
0x18007bd71  mov     rdi, rax
0x18007bd74  test    rax, rax
0x18007bd77  jnz     short loc_18007BD83
0x18007bd79  mov     eax, 8004000Ah
0x18007bd7e  jmp     loc_18007BE8E
0x18007bd83  call    cs:__imp_DUserFlushMessages
0x18007bd89  call    cs:__imp_DUserFlushDeferredMessages
0x18007bd8f  dec     dword ptr [rdi+8]
0x18007bd92  cmp     dword ptr [rdi+8], 0
0x18007bd96  jg      loc_18007BE8C
0x18007bd9c  mov     rcx, [rdi]
0x18007bd9f  call    cs:__imp_DeleteHandle
0x18007bda5  mov     rcx, rdi; this
0x18007bda8  call    ?UiaUninitThread@DirectUI@@YAXPEAUElTls@1@@Z; DirectUI::UiaUninitThread(DirectUI::ElTls *)
0x18007bdad  cmp     byte ptr [rdi+19h], 0
0x18007bdb1  jz      short loc_18007BDB9
0x18007bdb3  call    cs:__imp_BufferedPaintUnInit
0x18007bdb9  cmp     byte ptr [rdi+18h], 0
0x18007bdbd  jz      short loc_18007BDC5
0x18007bdbf  call    cs:__imp_CoUninitialize
0x18007bdc5  call    ?UninitThread@FontCache@DirectUI@@SAXXZ; DirectUI::FontCache::UninitThread(void)
0x18007bdca  cmp     cs:?g_fTraceElementLeaks@DirectUI@@3HA, 0; int DirectUI::g_fTraceElementLeaks
0x18007bdd1  jz      short loc_18007BE0F
0x18007bdd3  mov     ecx, cs:?g_dwElSlot@DirectUI@@3KA; dwTlsIndex
0x18007bdd9  call    cs:__imp_TlsGetValue
0x18007bddf  mov     rcx, [rax+38h]
0x18007bde3  test    rcx, rcx
0x18007bde6  jz      short loc_18007BE05
0x18007bde8  cmp     dword ptr [rcx], 0
0x18007bdeb  jbe     short loc_18007BE05
0x18007bded  lea     rdx, ?ReportLeakedElementsCB@DirectUI@@YAXPEAVElement@1@PEAVCallstackTracker@1@@Z; DirectUI::ReportLeakedElementsCB(DirectUI::Element *,DirectUI::CallstackTracker *)
0x18007bdf4  call    ?Enum@?$BTreeLookup@PEAVElement@DirectUI@@PEAVCallstackTracker@2@@DirectUI@@QEAAXP6AXPEAVElement@2@PEAVCallstackTracker@2@@Z@Z; DirectUI::BTreeLookup<DirectUI::Element *,DirectUI::CallstackTracker *>::Enum(void (*)(DirectUI::Element *,DirectUI::CallstackTracker *))
0x18007bdf9  lea     rcx, aNotAllElements; "\n Not all Elements were destroyed and "...
0x18007be00  call    ?ElementLeakTrace@DirectUI@@YAXPEBDZZ; DirectUI::ElementLeakTrace(char const *,...)
0x18007be05  call    ?DestroyLeakedElementList@DirectUI@@YAXXZ; DirectUI::DestroyLeakedElementList(void)
0x18007be0a  call    ?Uninit@CallstackTracker@DirectUI@@SAXXZ; DirectUI::CallstackTracker::Uninit(void)
0x18007be0f  mov     rbx, [rdi+10h]
0x18007be13  xor     edx, edx
0x18007be15  mov     rcx, rbx
0x18007be18  mov     rax, [rbx]
0x18007be1b  mov     rax, [rax]
0x18007be1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007be23  mov     rcx, rbx; this
0x18007be26  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x18007be2b  mov     rcx, [rdi+48h]; ho
0x18007be2f  test    rcx, rcx
0x18007be32  jz      short loc_18007BE42
0x18007be34  call    cs:__imp_DeleteObject
0x18007be3a  mov     qword ptr [rdi+48h], 0
0x18007be42  mov     rbx, [rdi+50h]
0x18007be46  test    rbx, rbx
0x18007be49  jz      short loc_18007BE63
0x18007be4b  mov     rcx, rbx; this
0x18007be4e  mov     qword ptr [rdi+50h], 0
0x18007be56  call    ??1TransitionHandler@DirectUI@@QEAA@XZ; DirectUI::TransitionHandler::~TransitionHandler(void)
0x18007be5b  mov     rcx, rbx; this
0x18007be5e  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x18007be63  call    ?s_Get@CStyleSheetManager@DirectUI@@SAPEAV12@XZ; DirectUI::CStyleSheetManager::s_Get(void)
0x18007be68  test    rax, rax
0x18007be6b  jz      short loc_18007BE76
0x18007be6d  lea     rcx, [rax+58h]; this
0x18007be71  call    ?UnregisterThread@CCacheThread@StyleSheetCache@DirectUI@@QEAAJK@Z; DirectUI::StyleSheetCache::CCacheThread::UnregisterThread(ulong)
0x18007be76  mov     rcx, rdi; this
0x18007be79  call    ?AccHFree@DirectUI@@YAXPEAX@Z; DirectUI::AccHFree(void *)
0x18007be7e  mov     ecx, cs:?g_dwElSlot@DirectUI@@3KA; dwTlsIndex
0x18007be84  xor     edx, edx; lpTlsValue
0x18007be86  call    cs:__imp_TlsSetValue
0x18007be8c  xor     eax, eax
0x18007be8e  mov     rbx, [rsp+28h+arg_0]
0x18007be93  add     rsp, 20h
0x18007be97  pop     rdi
0x18007be98  retn
```
