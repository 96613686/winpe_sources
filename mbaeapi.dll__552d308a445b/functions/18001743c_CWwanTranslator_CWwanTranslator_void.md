# CWwanTranslator::~CWwanTranslator(void)

- ea: `0x18001743c`
- end: `0x1800174e7`
- name: `??1CWwanTranslator@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(CWwanTranslator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001bfb0`

## callees

- `0x1800028b0`
- `0x1800170cc`
- `0x1800173a0`
- `0x18001743c`
- `0x1800174f0`
- `0x18003b4bc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800174aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800174aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017462`

## pseudocode

```c
void __fastcall CWwanTranslator::~CWwanTranslator(CWwanTranslator *this)
{
  void *v2; // rcx
  void *v3; // rdi
  volatile signed __int32 *v4; // rcx

  CWwanTranslator::StopListening(this);
  *((_QWORD *)this + 4) = 0;
  v2 = (void *)*((_QWORD *)this + 18);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 18) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    SlotBindingMap::~SlotBindingMap(*((SlotBindingMap **)this + 17));
    operator delete(v3);
  }
  std::vector<std::wstring>::~vector<std::wstring>((char *)this + 112);
  std::vector<std::wstring>::~vector<std::wstring>((char *)this + 88);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  std::_Tree<std::_Tmap_traits<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>,0>>((void **)this + 2);
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x18001743c  mov     [rsp+arg_0], rbx
0x180017441  push    rdi
0x180017442  sub     rsp, 20h
0x180017446  mov     rbx, rcx
0x180017449  call    ?StopListening@CWwanTranslator@@QEAAJXZ; CWwanTranslator::StopListening(void)
0x18001744e  mov     qword ptr [rbx+20h], 0
0x180017456  mov     rcx, [rbx+90h]; hObject
0x18001745d  test    rcx, rcx
0x180017460  jz      short loc_180017473
0x180017462  call    cs:__imp_CloseHandle
0x180017468  mov     qword ptr [rbx+90h], 0
0x180017473  mov     rdi, [rbx+88h]
0x18001747a  test    rdi, rdi
0x18001747d  jz      short loc_180017494
0x18001747f  mov     rcx, rdi; this
0x180017482  call    ??1SlotBindingMap@@QEAA@XZ; SlotBindingMap::~SlotBindingMap(void)
0x180017487  mov     edx, 50h ; 'P'
0x18001748c  mov     rcx, rdi; Block
0x18001748f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017494  lea     rcx, [rbx+70h]
0x180017498  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001749d  lea     rcx, [rbx+58h]
0x1800174a1  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800174a6  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800174aa  call    cs:__imp_DeleteCriticalSection
0x1800174b0  lea     rcx, [rbx+10h]
0x1800174b4  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@UWTModemParameters@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>,0>>::~_Tree<std::_Tmap_traits<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>,0>>(void)
0x1800174b9  mov     rcx, [rbx+8]
0x1800174bd  test    rcx, rcx
0x1800174c0  jz      short loc_1800174DC
0x1800174c2  or      eax, 0FFFFFFFFh
0x1800174c5  lock xadd [rcx+0Ch], eax
0x1800174ca  cmp     eax, 1
0x1800174cd  jnz     short loc_1800174DC
0x1800174cf  mov     rax, [rcx]
0x1800174d2  mov     rax, [rax+8]
0x1800174d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174db  nop
0x1800174dc  mov     rbx, [rsp+28h+arg_0]
0x1800174e1  add     rsp, 20h
0x1800174e5  pop     rdi
0x1800174e6  retn
```
