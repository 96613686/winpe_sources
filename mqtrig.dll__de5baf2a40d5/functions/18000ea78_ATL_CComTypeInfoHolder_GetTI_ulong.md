# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000ea78`
- end: `0x18000ebe8`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `368`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e994`
- `0x18000ec84`
- `0x18000efc8`

## callees

- `0x1800030d8`
- `0x18000ea78`
- `0x18000f06c`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000eb57`
- `ATL!__imp_AtlComPtrAssign` at `0x18000eb57`
- `ATL!__imp_AtlModuleAddTermFunc` at `0x18000eb7e`
- `ATL!__imp_AtlModuleAddTermFunc` at `0x18000eb7e`
- `KERNEL32!LeaveCriticalSection` at `0x18000ebd3`
- `KERNEL32!LeaveCriticalSection` at `0x18000ebd3`
- `KERNEL32!EnterCriticalSection` at `0x18000eaaa`
- `KERNEL32!EnterCriticalSection` at `0x18000eaaa`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000ead7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000ead7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  int (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v7; // rax
  struct ITypeInfo *v8; // rdx
  ITypeLib *pptlib; // [rsp+30h] [rbp-10h] BYREF
  int (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // [rsp+60h] [rbp+20h] BYREF
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+30h] BYREF
  __int64 v12; // [rsp+78h] [rbp+38h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  NameCache = 0;
  EnterCriticalSection(&CriticalSection);
  if ( !*((_QWORD *)this + 3) )
  {
    pptlib = 0;
    NameCache = LoadRegTypeLib(
                  *((const GUID *const *)this + 1),
                  *((_WORD *)this + 8),
                  *((_WORD *)this + 9),
                  lcid,
                  &pptlib);
    if ( NameCache >= 0 )
    {
      v11 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    *(_QWORD *)this,
                    &v11);
      if ( NameCache >= 0 )
      {
        v6 = v11;
        v10 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v11;
        if ( v11 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v11)[1])(v11);
          v6 = v11;
        }
        v12 = 0;
        if ( (**v6)(v6, &GUID_00020412_0000_0000_c000_000000000046, &v12) >= 0 )
          AtlComPtrAssign(&v10, v12);
        v7 = (__int64)v10;
        v10 = 0;
        *((_QWORD *)this + 3) = v7;
        AtlModuleAddTermFunc(&_Module, ATL::CComTypeInfoHolder::Cleanup, this);
        ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(&v12);
        ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)&v10);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)&v11);
    }
  }
  v8 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v8);
  }
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18000ea78  mov     [rsp-18h+arg_8], rbx
0x18000ea7d  push    rbp
0x18000ea7e  push    rsi
0x18000ea7f  push    rdi
0x18000ea80  mov     rbp, rsp
0x18000ea83  sub     rsp, 40h
0x18000ea87  mov     esi, edx
0x18000ea89  mov     rbx, rcx
0x18000ea8c  cmp     qword ptr [rcx+18h], 0
0x18000ea91  jz      short loc_18000EAA1
0x18000ea93  cmp     qword ptr [rcx+28h], 0
0x18000ea98  jz      short loc_18000EAA1
0x18000ea9a  xor     eax, eax
0x18000ea9c  jmp     loc_18000EBDB
0x18000eaa1  xor     edi, edi
0x18000eaa3  lea     rcx, CriticalSection; lpCriticalSection
0x18000eaaa  call    cs:__imp_EnterCriticalSection
0x18000eab0  cmp     [rbx+18h], rdi
0x18000eab4  jnz     loc_18000EBB2
0x18000eaba  mov     [rbp+var_10], rdi
0x18000eabe  lea     rax, [rbp+var_10]
0x18000eac2  mov     [rsp+40h+pptlib], rax; pptlib
0x18000eac7  mov     r9d, esi; lcid
0x18000eaca  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18000eacf  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18000ead3  mov     rcx, [rbx+8]; rguid
0x18000ead7  call    cs:__imp_LoadRegTypeLib
0x18000eadd  mov     edi, eax
0x18000eadf  test    eax, eax
0x18000eae1  js      loc_18000EBB2
0x18000eae7  mov     [rbp+arg_10], 0
0x18000eaef  mov     rcx, [rbp+var_10]
0x18000eaf3  mov     rax, [rcx]
0x18000eaf6  lea     r8, [rbp+arg_10]
0x18000eafa  mov     rdx, [rbx]
0x18000eafd  mov     rax, [rax+30h]
0x18000eb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb06  mov     edi, eax
0x18000eb08  test    eax, eax
0x18000eb0a  js      loc_18000EB98
0x18000eb10  mov     rcx, [rbp+arg_10]
0x18000eb14  mov     [rbp+arg_0], rcx
0x18000eb18  test    rcx, rcx
0x18000eb1b  jz      short loc_18000EB2D
0x18000eb1d  mov     rax, [rcx]
0x18000eb20  mov     rax, [rax+8]
0x18000eb24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb29  mov     rcx, [rbp+arg_10]
0x18000eb2d  mov     [rbp+arg_18], 0
0x18000eb35  mov     rax, [rcx]
0x18000eb38  lea     r8, [rbp+arg_18]
0x18000eb3c  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000eb43  mov     rax, [rax]
0x18000eb46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb4b  test    eax, eax
0x18000eb4d  js      short loc_18000EB5D
0x18000eb4f  mov     rdx, [rbp+arg_18]
0x18000eb53  lea     rcx, [rbp+arg_0]
0x18000eb57  call    cs:__imp_AtlComPtrAssign
0x18000eb5d  mov     rax, [rbp+arg_0]
0x18000eb61  mov     [rbp+arg_0], 0
0x18000eb69  mov     [rbx+18h], rax
0x18000eb6d  mov     r8, rbx
0x18000eb70  lea     rdx, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x18000eb77  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18000eb7e  call    cs:__imp_AtlModuleAddTermFunc
0x18000eb84  nop
0x18000eb85  lea     rcx, [rbp+arg_18]
0x18000eb89  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000eb8e  nop
0x18000eb8f  lea     rcx, [rbp+arg_0]
0x18000eb93  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000eb98  mov     rcx, [rbp+var_10]
0x18000eb9c  mov     rax, [rcx]
0x18000eb9f  mov     rax, [rax+10h]
0x18000eba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eba8  nop
0x18000eba9  lea     rcx, [rbp+arg_10]
0x18000ebad  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000ebb2  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18000ebb6  test    rdx, rdx
0x18000ebb9  jz      short loc_18000EBCC
0x18000ebbb  cmp     qword ptr [rbx+28h], 0
0x18000ebc0  jnz     short loc_18000EBCC
0x18000ebc2  mov     rcx, rbx; this
0x18000ebc5  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000ebca  mov     edi, eax
0x18000ebcc  lea     rcx, CriticalSection; lpCriticalSection
0x18000ebd3  call    cs:__imp_LeaveCriticalSection
0x18000ebd9  mov     eax, edi
0x18000ebdb  mov     rbx, [rsp+40h+arg_8]
0x18000ebe0  add     rsp, 40h
0x18000ebe4  pop     rdi
0x18000ebe5  pop     rsi
0x18000ebe6  pop     rbp
0x18000ebe7  retn
```
