# CHidPairing::_Deinitialize(void)

- ea: `0x1800b0c14`
- end: `0x1800b0d7c`
- name: `?_Deinitialize@CHidPairing@@AEAAXXZ`
- size: `360`
- prototype: `void __fastcall(CHidPairing *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800af57c`
- `0x1800af74c`

## callees

- `0x1800b05dc`
- `0x1800b0c14`
- `0x1800b8834`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c24`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800b0c31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0d0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0cf1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0d0e`
- `deviceassociation!DafCloseAssociationContext` at `0x1800b0d48`
- `deviceassociation!DafCloseAssociationContext` at `0x1800b0d48`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800b0d2b`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800b0d2b`

## pseudocode

```c
void __fastcall CHidPairing::_Deinitialize(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  void *SpinCount; // rcx
  HANDLE v5; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  void *v7; // rcx
  void *v8; // rcx
  HANDLE v9; // rcx

  DeleteCriticalSection(this + 5);
  DeleteCriticalSection(this + 6);
  OwningThread = this[7].OwningThread;
  if ( OwningThread )
  {
    CloseHandle(OwningThread);
    this[7].OwningThread = 0;
  }
  LockSemaphore = this[7].LockSemaphore;
  if ( LockSemaphore )
  {
    CloseHandle(LockSemaphore);
    this[7].LockSemaphore = 0;
  }
  SpinCount = (void *)this[7].SpinCount;
  if ( SpinCount )
  {
    CloseHandle(SpinCount);
    this[7].SpinCount = 0;
  }
  v5 = this[8].OwningThread;
  if ( v5 )
  {
    CloseHandle(v5);
    this[8].OwningThread = 0;
  }
  DebugInfo = this[8].DebugInfo;
  if ( DebugInfo )
  {
    CloseHandle(DebugInfo);
    this[8].DebugInfo = 0;
  }
  v7 = *(void **)&this[8].LockCount;
  if ( v7 )
  {
    CloseHandle(v7);
    *(_QWORD *)&this[8].LockCount = 0;
  }
  v8 = (void *)this[8].SpinCount;
  if ( v8 )
  {
    CloseHandle(v8);
    this[8].SpinCount = 0;
  }
  v9 = this[8].LockSemaphore;
  if ( v9 )
  {
    CloseHandle(v9);
    this[8].LockSemaphore = 0;
  }
  if ( this[9].LockSemaphore )
  {
    DevCloseObjectQuery();
    this[9].LockSemaphore = 0;
  }
  if ( *(_QWORD *)&this[7].LockCount )
  {
    if ( (int)DafCloseAssociationContext() < 0 )
      UnattendLogW(2, L"CHidPairing::_Deinitialize - DafCloseAssociationContext failed");
    *(_QWORD *)&this[7].LockCount = 0;
  }
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&this[3]);
}

```

## disassembly

```asm
0x1800b0c14  push    rbx
0x1800b0c16  sub     rsp, 20h
0x1800b0c1a  mov     rbx, rcx
0x1800b0c1d  add     rcx, 0C8h; lpCriticalSection
0x1800b0c24  call    cs:__imp_DeleteCriticalSection
0x1800b0c2a  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x1800b0c31  call    cs:__imp_DeleteCriticalSection
0x1800b0c37  mov     rcx, [rbx+128h]; hObject
0x1800b0c3e  test    rcx, rcx
0x1800b0c41  jz      short loc_1800B0C54
0x1800b0c43  call    cs:__imp_CloseHandle
0x1800b0c49  mov     qword ptr [rbx+128h], 0
0x1800b0c54  mov     rcx, [rbx+130h]; hObject
0x1800b0c5b  test    rcx, rcx
0x1800b0c5e  jz      short loc_1800B0C71
0x1800b0c60  call    cs:__imp_CloseHandle
0x1800b0c66  mov     qword ptr [rbx+130h], 0
0x1800b0c71  mov     rcx, [rbx+138h]; hObject
0x1800b0c78  test    rcx, rcx
0x1800b0c7b  jz      short loc_1800B0C8E
0x1800b0c7d  call    cs:__imp_CloseHandle
0x1800b0c83  mov     qword ptr [rbx+138h], 0
0x1800b0c8e  mov     rcx, [rbx+150h]; hObject
0x1800b0c95  test    rcx, rcx
0x1800b0c98  jz      short loc_1800B0CAB
0x1800b0c9a  call    cs:__imp_CloseHandle
0x1800b0ca0  mov     qword ptr [rbx+150h], 0
0x1800b0cab  mov     rcx, [rbx+140h]; hObject
0x1800b0cb2  test    rcx, rcx
0x1800b0cb5  jz      short loc_1800B0CC8
0x1800b0cb7  call    cs:__imp_CloseHandle
0x1800b0cbd  mov     qword ptr [rbx+140h], 0
0x1800b0cc8  mov     rcx, [rbx+148h]; hObject
0x1800b0ccf  test    rcx, rcx
0x1800b0cd2  jz      short loc_1800B0CE5
0x1800b0cd4  call    cs:__imp_CloseHandle
0x1800b0cda  mov     qword ptr [rbx+148h], 0
0x1800b0ce5  mov     rcx, [rbx+160h]; hObject
0x1800b0cec  test    rcx, rcx
0x1800b0cef  jz      short loc_1800B0D02
0x1800b0cf1  call    cs:__imp_CloseHandle
0x1800b0cf7  mov     qword ptr [rbx+160h], 0
0x1800b0d02  mov     rcx, [rbx+158h]; hObject
0x1800b0d09  test    rcx, rcx
0x1800b0d0c  jz      short loc_1800B0D1F
0x1800b0d0e  call    cs:__imp_CloseHandle
0x1800b0d14  mov     qword ptr [rbx+158h], 0
0x1800b0d1f  mov     rcx, [rbx+180h]
0x1800b0d26  test    rcx, rcx
0x1800b0d29  jz      short loc_1800B0D3C
0x1800b0d2b  call    cs:__imp_DevCloseObjectQuery
0x1800b0d31  mov     qword ptr [rbx+180h], 0
0x1800b0d3c  mov     rcx, [rbx+120h]
0x1800b0d43  test    rcx, rcx
0x1800b0d46  jz      short loc_1800B0D6E
0x1800b0d48  call    cs:__imp_DafCloseAssociationContext
0x1800b0d4e  test    eax, eax
0x1800b0d50  jns     short loc_1800B0D63
0x1800b0d52  lea     rdx, aChidpairingDei; "CHidPairing::_Deinitialize - DafCloseAs"...
0x1800b0d59  mov     ecx, 2
0x1800b0d5e  call    UnattendLogW
0x1800b0d63  mov     qword ptr [rbx+120h], 0
0x1800b0d6e  lea     rcx, [rbx+78h]
0x1800b0d72  add     rsp, 20h
0x1800b0d76  pop     rbx
0x1800b0d77  jmp     ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V32@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
```
