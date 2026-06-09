# ATL::CComTypeInfoHolder::GetTI(ulong,ITypeInfo * *)

- ea: `0x180002734`
- end: `0x180002838`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJKPEAPEAUITypeInfo@@@Z`
- size: `260`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int, struct ITypeInfo **)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004790`
- `0x180004a10`
- `0x180004f70`

## callees

- `0x180002734`
- `0x180010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180002760`
- `KERNEL32!EnterCriticalSection` at `0x180002760`
- `KERNEL32!LeaveCriticalSection` at `0x180002820`
- `KERNEL32!LeaveCriticalSection` at `0x180002820`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800027a0`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800027a0`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ITypeLib *this, LCID a2, struct ITypeInfo **a3)
{
  HRESULT v5; // ebx
  ITypeLib *pptlib; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+50h] [rbp+18h] BYREF

  pptlib = this;
  *a3 = 0;
  v5 = -2147467259;
  EnterCriticalSection(&CriticalSection);
  if ( !qword_180017130 )
  {
    pptlib = 0;
    v5 = LoadRegTypeLib(rguid, word_180017128, word_18001712A, a2, &pptlib);
    if ( v5 >= 0 )
    {
      v8 = 0;
      v5 = ((__int64 (__fastcall *)(ITypeLib *, GUID *, __int64 *))pptlib->lpVtbl->GetTypeInfoOfGuid)(
             pptlib,
             ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::_tih[0],
             &v8);
      if ( v5 >= 0 )
        qword_180017130 = v8;
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
    }
  }
  *a3 = (struct ITypeInfo *)qword_180017130;
  if ( qword_180017130 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180017130 + 8LL))(qword_180017130);
    v5 = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002734  mov     [rsp+arg_8], rbx
0x180002739  mov     [rsp+arg_18], rsi
0x18000273e  mov     [rsp+arg_0], rcx
0x180002743  push    rdi
0x180002744  sub     rsp, 30h
0x180002748  lea     rcx, CriticalSection; lpCriticalSection
0x18000274f  mov     qword ptr [r8], 0
0x180002756  mov     rdi, r8
0x180002759  mov     esi, edx
0x18000275b  mov     ebx, 80004005h
0x180002760  call    cs:__imp_EnterCriticalSection
0x180002766  cmp     cs:qword_180017130, 0
0x18000276e  jnz     loc_1800027F5
0x180002774  movzx   r8d, cs:word_18001712A; wVerMinor
0x18000277c  lea     rax, [rsp+38h+arg_0]
0x180002781  movzx   edx, cs:word_180017128; wVerMajor
0x180002788  mov     r9d, esi; lcid
0x18000278b  mov     rcx, cs:rguid; rguid
0x180002792  mov     [rsp+38h+pptlib], rax; pptlib
0x180002797  mov     [rsp+38h+arg_0], 0
0x1800027a0  call    cs:__imp_LoadRegTypeLib
0x1800027a6  mov     ebx, eax
0x1800027a8  test    eax, eax
0x1800027aa  js      short loc_1800027F5
0x1800027ac  mov     rcx, [rsp+38h+arg_0]
0x1800027b1  lea     r8, [rsp+38h+arg_10]
0x1800027b6  mov     rdx, cs:?_tih@?$IDispatchImpl@UILogScripting@@$1?IID_ILogScripting@@3U_GUID@@B$1?LIBID_IISLog@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<ILogScripting,&_GUID const IID_ILogScripting,&_GUID const LIBID_IISLog,1,0,ATL::CComTypeInfoHolder>::_tih
0x1800027bd  mov     [rsp+38h+arg_10], 0
0x1800027c6  mov     rax, [rcx]
0x1800027c9  mov     rax, [rax+30h]
0x1800027cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d2  mov     ebx, eax
0x1800027d4  test    eax, eax
0x1800027d6  js      short loc_1800027E4
0x1800027d8  mov     rax, [rsp+38h+arg_10]
0x1800027dd  mov     cs:qword_180017130, rax
0x1800027e4  mov     rcx, [rsp+38h+arg_0]
0x1800027e9  mov     rax, [rcx]
0x1800027ec  mov     rax, [rax+10h]
0x1800027f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f5  mov     rax, cs:qword_180017130
0x1800027fc  mov     [rdi], rax
0x1800027ff  mov     rcx, cs:qword_180017130
0x180002806  test    rcx, rcx
0x180002809  jz      short loc_180002819
0x18000280b  mov     rax, [rcx]
0x18000280e  mov     rax, [rax+8]
0x180002812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002817  xor     ebx, ebx
0x180002819  lea     rcx, CriticalSection; lpCriticalSection
0x180002820  call    cs:__imp_LeaveCriticalSection
0x180002826  mov     rsi, [rsp+38h+arg_18]
0x18000282b  mov     eax, ebx
0x18000282d  mov     rbx, [rsp+38h+arg_8]
0x180002832  add     rsp, 30h
0x180002836  pop     rdi
0x180002837  retn
```
