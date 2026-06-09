# CContentDirectoryChangeListener::~CContentDirectoryChangeListener(void)

- ea: `0x18002260c`
- end: `0x1800226ee`
- name: `??1CContentDirectoryChangeListener@@UEAA@XZ`
- size: `226`
- prototype: `void __fastcall(CContentDirectoryChangeListener *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022960`

## callees

- `0x180007840`
- `0x180008430`
- `0x18000ab48`
- `0x18002260c`
- `0x180024220`
- `0x180024548`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800226a5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800226a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022683`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002266c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002266c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CContentDirectoryChangeListener::~CContentDirectoryChangeListener(
        CContentDirectoryChangeListener *this,
        __int64 a2,
        __int64 a3)
{
  CContentDirectoryChangeListenerForDms **v4; // rsi
  CContentDirectoryChangeListenerForDms *v5; // rbp
  bool v6; // zf
  CChangeListenerRegistrar *v7; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  CContentDirectoryChangeListenerForDms *v9; // rcx
  _BYTE v10[72]; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)this = &CContentDirectoryChangeListener::`vftable'{for `IChangeNotifySource'};
  *((_QWORD *)this + 1) = &CContentDirectoryChangeListener::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPersistIDList>'};
  v4 = (CContentDirectoryChangeListenerForDms **)((char *)this + 72);
  if ( *((_DWORD *)this + 16) == 1 )
    CContentDirectoryChangeListenerForDms::ReleaseClientRef(
      *v4,
      *((const unsigned __int16 **)this + 11),
      *((const struct _ITEMIDLIST_ABSOLUTE **)this + 10));
  v5 = *v4;
  LOBYTE(a3) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v10, (char *)*v4 + 72, a3);
  v6 = (*((_DWORD *)v5 + 46))-- == 1;
  if ( v6 && !WindowsIsStringEmpty(*((HSTRING *)v5 + 14)) )
  {
    v7 = (CChangeListenerRegistrar *)*((_QWORD *)v5 + 21);
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v5 + 14), 0);
    CChangeListenerRegistrar::RemoveChangeListener(v7, v5, StringRawBuffer);
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)this + 88);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)this + 80);
  v9 = *v4;
  if ( *v4 )
  {
    *v4 = 0;
    (*(void (__fastcall **)(CContentDirectoryChangeListenerForDms *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18002260c  push    rbx
0x18002260e  push    rbp
0x18002260f  push    rsi
0x180022610  push    rdi
0x180022611  push    r14
0x180022613  push    r15
0x180022615  sub     rsp, 38h
0x180022619  mov     rdi, rcx
0x18002261c  lea     rax, ??_7CContentDirectoryChangeListener@@6BIChangeNotifySource@@@; const CContentDirectoryChangeListener::`vftable'{for `IChangeNotifySource'}
0x180022623  mov     [rcx], rax
0x180022626  lea     rax, ??_7CContentDirectoryChangeListener@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIPersistIDList@@@Details@WRL@Microsoft@@@; const CContentDirectoryChangeListener::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IPersistIDList>'}
0x18002262d  mov     [rcx+8], rax
0x180022631  lea     rsi, [rcx+48h]
0x180022635  cmp     dword ptr [rcx+40h], 1
0x180022639  jnz     short loc_18002264B
0x18002263b  mov     r8, [rcx+50h]; struct _ITEMIDLIST_ABSOLUTE *
0x18002263f  mov     rdx, [rcx+58h]; unsigned __int16 *
0x180022643  mov     rcx, [rsi]; this
0x180022646  call    ?ReleaseClientRef@CContentDirectoryChangeListenerForDms@@QEAAXPEBGPEBU_ITEMIDLIST_ABSOLUTE@@@Z; CContentDirectoryChangeListenerForDms::ReleaseClientRef(ushort const *,_ITEMIDLIST_ABSOLUTE const *)
0x18002264b  mov     rbp, [rsi]
0x18002264e  lea     rdx, [rbp+48h]
0x180022652  mov     r8b, 1
0x180022655  lea     rcx, [rsp+68h+var_48]
0x18002265a  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x18002265f  add     dword ptr [rbp+0B8h], 0FFFFFFFFh
0x180022666  jnz     short loc_180022697
0x180022668  mov     rcx, [rbp+70h]; string
0x18002266c  call    cs:__imp_WindowsIsStringEmpty
0x180022672  test    eax, eax
0x180022674  jnz     short loc_180022697
0x180022676  mov     rbx, [rbp+0A8h]
0x18002267d  xor     edx, edx; length
0x18002267f  mov     rcx, [rbp+70h]; string
0x180022683  call    cs:__imp_WindowsGetStringRawBuffer
0x180022689  mov     r8, rax; unsigned __int16 *
0x18002268c  mov     rdx, rbp; struct CContentDirectoryChangeListenerForDms *
0x18002268f  mov     rcx, rbx; this
0x180022692  call    ?RemoveChangeListener@CChangeListenerRegistrar@@QEAAXPEBVCContentDirectoryChangeListenerForDms@@PEBG@Z; CChangeListenerRegistrar::RemoveChangeListener(CContentDirectoryChangeListenerForDms const *,ushort const *)
0x180022697  lea     rcx, [rsp+68h+var_48]
0x18002269c  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1800226a1  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800226a5  call    cs:__imp_DeleteCriticalSection
0x1800226ab  lea     rcx, [rdi+58h]
0x1800226af  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800226b4  lea     rcx, [rdi+50h]
0x1800226b8  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800226bd  nop
0x1800226be  mov     rcx, [rsi]
0x1800226c1  test    rcx, rcx
0x1800226c4  jz      short loc_1800226DA
0x1800226c6  mov     qword ptr [rsi], 0
0x1800226cd  mov     rax, [rcx]
0x1800226d0  mov     rax, [rax+10h]
0x1800226d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226d9  nop
0x1800226da  mov     dword ptr [rdi+14h], 0C0000001h
0x1800226e1  add     rsp, 38h
0x1800226e5  pop     r15
0x1800226e7  pop     r14
0x1800226e9  pop     rdi
0x1800226ea  pop     rsi
0x1800226eb  pop     rbp
0x1800226ec  pop     rbx
0x1800226ed  retn
```
