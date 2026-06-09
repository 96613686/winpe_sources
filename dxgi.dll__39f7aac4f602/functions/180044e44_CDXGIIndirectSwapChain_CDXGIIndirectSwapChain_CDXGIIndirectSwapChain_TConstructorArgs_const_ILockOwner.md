# CDXGIIndirectSwapChain::CDXGIIndirectSwapChain(CDXGIIndirectSwapChain::TConstructorArgs const &,ILockOwner *)

- ea: `0x180044e44`
- end: `0x180045077`
- name: `??0CDXGIIndirectSwapChain@@QEAA@AEBUTConstructorArgs@0@PEAUILockOwner@@@Z`
- size: `563`
- prototype: `CDXGIIndirectSwapChain *__fastcall(CDXGIIndirectSwapChain *__hidden this, const struct CDXGIIndirectSwapChain::TConstructorArgs *, struct ILockOwner *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180044a2c`

## callees

- `0x18000fd40`
- `0x1800147b4`
- `0x18001b4a8`
- `0x180044e44`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045066`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004503f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004503f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045004`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045004`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CDXGIIndirectSwapChain *__fastcall CDXGIIndirectSwapChain::CDXGIIndirectSwapChain(
        CDXGIIndirectSwapChain *this,
        const struct CDXGIIndirectSwapChain::TConstructorArgs *a2,
        struct ILockOwner *a3)
{
  __int64 v4; // r8
  int Data; // [rsp+50h] [rbp+20h] BYREF
  const struct CDXGIIndirectSwapChain::TConstructorArgs *Type; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = a2;
  *((_QWORD *)this + 18) = a3;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 17) = 0;
  CDestructionNotifier::CDestructionNotifier((CDXGIIndirectSwapChain *)((char *)this + 16));
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 72) = 3;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 296);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 320);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 344);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 368);
  *((_QWORD *)this + 49) = 0;
  *((_WORD *)this + 200) = 0;
  *((_BYTE *)this + 402) = 0;
  *((_DWORD *)this + 101) = 1;
  *((_WORD *)this + 204) = 0;
  *((_QWORD *)this + 52) = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 424);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 448);
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 60) = v4;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  *((_WORD *)this + 244) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 512);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 536);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 560);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>((char *)this + 584);
  *((_DWORD *)this + 152) = -1;
  if ( (unsigned int)IsRemoteDevice() )
  {
    *((_DWORD *)this + 101) = 2;
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\GraphicsDrivers",
            0,
            0x80000000,
            &hKey) )
    {
      LODWORD(Type) = 0;
      Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(
              hKey,
              L"TerminateIndirectOnStallRemoteMultiplier",
              0,
              (LPDWORD)&Type,
              (LPBYTE)&Data,
              &cbData)
        && (_DWORD)Type == 4
        && (unsigned int)(Data - 1) <= 0x3E7 )
      {
        *((_DWORD *)this + 101) = Data;
      }
      RegCloseKey(hKey);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180044e44  mov     [rsp-18h+Type], rdx
0x180044e49  push    rbp
0x180044e4a  push    rbx
0x180044e4b  push    rdi
0x180044e4c  mov     rbp, rsp
0x180044e4f  sub     rsp, 30h
0x180044e53  mov     rbx, rcx
0x180044e56  mov     [rcx+90h], r8
0x180044e5d  xor     edi, edi
0x180044e5f  mov     [rcx+98h], rdi
0x180044e66  mov     [rcx+88h], rdi
0x180044e6d  add     rcx, 10h; this
0x180044e71  call    ??0CDestructionNotifier@@QEAA@XZ; CDestructionNotifier::CDestructionNotifier(void)
0x180044e76  mov     [rbx+0A0h], rdi
0x180044e7d  mov     [rbx+0B8h], rdi
0x180044e84  mov     [rbx+0C0h], rdi
0x180044e8b  mov     [rbx+0C8h], rdi
0x180044e92  mov     [rbx+0D0h], rdi
0x180044e99  mov     [rbx+0D8h], rdi
0x180044ea0  mov     [rbx+0E0h], rdi
0x180044ea7  mov     [rbx+0E8h], rdi
0x180044eae  mov     [rbx+0F0h], rdi
0x180044eb5  mov     [rbx+0F8h], rdi
0x180044ebc  mov     [rbx+100h], rdi
0x180044ec3  mov     [rbx+108h], rdi
0x180044eca  mov     [rbx+110h], rdi
0x180044ed1  mov     [rbx+118h], rdi
0x180044ed8  mov     dword ptr [rbx+120h], 3
0x180044ee2  lea     rcx, [rbx+128h]
0x180044ee9  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044eee  lea     rcx, [rbx+140h]
0x180044ef5  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044efa  lea     rcx, [rbx+158h]
0x180044f01  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044f06  lea     rcx, [rbx+170h]
0x180044f0d  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044f12  mov     [rbx+188h], rdi
0x180044f19  mov     [rbx+190h], di
0x180044f20  mov     [rbx+192h], dil
0x180044f27  mov     dword ptr [rbx+194h], 1
0x180044f31  mov     [rbx+198h], di
0x180044f38  mov     [rbx+1A0h], rdi
0x180044f3f  lea     rcx, [rbx+1A8h]
0x180044f46  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044f4b  lea     rcx, [rbx+1C0h]
0x180044f52  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044f57  mov     [rbx+1D8h], rdi
0x180044f5e  mov     [rbx+1E0h], r8
0x180044f65  test    r8, r8
0x180044f68  jz      short loc_180044F7A
0x180044f6a  mov     rax, [r8]
0x180044f6d  mov     rcx, r8
0x180044f70  mov     rax, [rax+8]
0x180044f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f79  nop
0x180044f7a  mov     [rbx+1E8h], di
0x180044f81  mov     [rbx+1F0h], rdi
0x180044f88  mov     [rbx+1F8h], rdi
0x180044f8f  lea     rcx, [rbx+200h]
0x180044f96  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044f9b  lea     rcx, [rbx+218h]
0x180044fa2  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044fa7  lea     rcx, [rbx+230h]
0x180044fae  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044fb3  lea     rcx, [rbx+248h]
0x180044fba  call    ??$?0V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@$$QEAV?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@Vany@std@@@std@@@std@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>>>(std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<wil::details::apartment_variable_base<1,wil::apartment_variable_platform> * const,std::any>>>>> &&)
0x180044fbf  mov     dword ptr [rbx+260h], 0FFFFFFFFh
0x180044fc9  call    ?IsRemoteDevice@@YAHXZ; IsRemoteDevice(void)
0x180044fce  test    eax, eax
0x180044fd0  jz      loc_18004506C
0x180044fd6  mov     dword ptr [rbx+194h], 2
0x180044fe0  mov     [rbp+hKey], rdi
0x180044fe4  lea     rax, [rbp+hKey]
0x180044fe8  mov     [rsp+30h+phkResult], rax; phkResult
0x180044fed  mov     r9d, 80000000h; samDesired
0x180044ff3  xor     r8d, r8d; ulOptions
0x180044ff6  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Gra"...
0x180044ffd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180045004  call    cs:__imp_RegOpenKeyExW
0x18004500a  test    eax, eax
0x18004500c  jnz     short loc_18004506C
0x18004500e  mov     dword ptr [rbp+Type], edi
0x180045011  mov     [rbp+Data], edi
0x180045014  mov     [rbp+cbData], 4
0x18004501b  lea     rax, [rbp+cbData]
0x18004501f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180045024  lea     rax, [rbp+Data]
0x180045028  mov     [rsp+30h+phkResult], rax; lpData
0x18004502d  lea     r9, [rbp+Type]; lpType
0x180045031  xor     r8d, r8d; lpReserved
0x180045034  lea     rdx, aTerminateindir_0; "TerminateIndirectOnStallRemoteMultiplie"...
0x18004503b  mov     rcx, [rbp+hKey]; hKey
0x18004503f  call    cs:__imp_RegQueryValueExW
0x180045045  test    eax, eax
0x180045047  jnz     short loc_180045062
0x180045049  cmp     dword ptr [rbp+Type], 4
0x18004504d  jnz     short loc_180045062
0x18004504f  mov     ecx, [rbp+Data]
0x180045052  lea     eax, [rcx-1]
0x180045055  cmp     eax, 3E7h
0x18004505a  ja      short loc_180045062
0x18004505c  mov     [rbx+194h], ecx
0x180045062  mov     rcx, [rbp+hKey]; hKey
0x180045066  call    cs:__imp_RegCloseKey
0x18004506c  mov     rax, rbx
0x18004506f  add     rsp, 30h
0x180045073  pop     rdi
0x180045074  pop     rbx
0x180045075  pop     rbp
0x180045076  retn
```
