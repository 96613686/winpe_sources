# EapLm::BaseEapLibraryManager::BaseGetEapMethodConfig(EapHost::EapMethodType const &)

- ea: `0x18002c590`
- end: `0x18002c720`
- name: `?BaseGetEapMethodConfig@BaseEapLibraryManager@EapLm@@IEAA?AV?$SmartPointer@UIEapMethod@EapLm@@@@AEBVEapMethodType@EapHost@@@Z`
- size: `400`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180016e44`

## callees

- `0x1800017a0`
- `0x180012c10`
- `0x180012d18`
- `0x1800139a4`
- `0x1800151ec`
- `0x18002b298`
- `0x18002b85c`
- `0x18002c590`
- `0x18002ca08`
- `0x18002db64`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c6b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c6b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall EapLm::BaseEapLibraryManager::BaseGetEapMethodConfig(_QWORD *a1, __int64 *a2, __int64 a3)
{
  ReferenceCounted *v6; // r9
  ReferenceCounted *v7; // rbx
  __int64 *v8; // r14
  ReferenceCounted *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rax
  ReferenceCounted *v13; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v14; // [rsp+38h] [rbp-91h] BYREF
  ReferenceCounted *v15; // [rsp+48h] [rbp-81h] BYREF
  _OWORD v16[3]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v17[96]; // [rsp+80h] [rbp-49h] BYREF

  v14 = a2;
  memset(v16, 0, sizeof(v16));
  LOBYTE(v16[0]) = *(_BYTE *)(a3 + 8);
  *(_QWORD *)((char *)v16 + 4) = *(_QWORD *)(a3 + 12);
  HIDWORD(v16[0]) = *(_DWORD *)(a3 + 24);
  LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(&v14, (__int64)(a1 + 10));
  std::_Tree<std::_Tmap_traits<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot,std::less<crt_ref<_EAP_METHOD_INFO>>,std::allocator<std::pair<crt_ref<_EAP_METHOD_INFO> const,EapLm::_EapMethodSlot>>,0>>::find(
    a1 + 17,
    &v13,
    v16);
  v6 = v13;
  if ( v13 == (ReferenceCounted *)a1[17] )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v17, 0x80420011, (const struct EapHost::EapMethodType *)a3, 0x57u);
    EapHost::EapError::FillRootCauseString(
      (EapHost::EapError *)v17,
      0,
      *(unsigned __int8 *)(a3 + 8),
      *(unsigned int *)(a3 + 24));
    EapHost::EapException::Throw((const struct EapHost::EapError *)v17);
  }
  v7 = 0;
  v13 = 0;
  v8 = (__int64 *)((char *)v6 + 80);
  v9 = 0;
  if ( !*((_QWORD *)v6 + 10) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD *, ReferenceCounted **, __int64, _QWORD))(*a1 + 40LL))(
            a1,
            &v15,
            a3,
            *((unsigned int *)v6 + 22));
    SmartPointer<EapLm::IEapMethod>::operator=(&v13, v10);
    if ( v15 )
      ReferenceCounted::Release(v15);
    v7 = v13;
    v9 = v13;
    (*(void (__fastcall **)(ReferenceCounted *))(*(_QWORD *)v13 + 8LL))(v13);
    SmartPointer<EapLm::IEapMethod>::operator=(v8, &v13);
  }
  v11 = *v8;
  *a2 = *v8;
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  if ( v9 )
    ReferenceCounted::Release(v7);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 2));
  Free<HeapAllocator>(v16);
  return a2;
}

```

## disassembly

```asm
0x18002c590  push    rbp
0x18002c592  push    rbx
0x18002c593  push    rsi
0x18002c594  push    rdi
0x18002c595  push    r12
0x18002c597  push    r14
0x18002c599  push    r15
0x18002c59b  lea     rbp, [rsp-27h]
0x18002c5a0  sub     rsp, 0F0h
0x18002c5a7  mov     rax, cs:__security_cookie
0x18002c5ae  xor     rax, rsp
0x18002c5b1  mov     [rbp+57h+var_40], rax
0x18002c5b5  mov     rsi, r8
0x18002c5b8  mov     r15, rdx
0x18002c5bb  mov     r12, rcx
0x18002c5be  mov     [rsp+120h+var_E8], rdx
0x18002c5c3  xorps   xmm0, xmm0
0x18002c5c6  movups  [rbp+57h+var_D0], xmm0
0x18002c5ca  movups  [rbp+57h+var_C0], xmm0
0x18002c5ce  movups  [rbp+57h+var_B0], xmm0
0x18002c5d2  mov     al, [r8+8]
0x18002c5d6  mov     byte ptr [rbp+57h+var_D0], al
0x18002c5d9  mov     eax, [r8+0Ch]
0x18002c5dd  mov     dword ptr [rbp+57h+var_D0+4], eax
0x18002c5e0  mov     eax, [r8+10h]
0x18002c5e4  mov     dword ptr [rbp+57h+var_D0+8], eax
0x18002c5e7  mov     eax, [r8+18h]
0x18002c5eb  mov     dword ptr [rbp+57h+var_D0+0Ch], eax
0x18002c5ee  lea     rdx, [rcx+50h]
0x18002c5f2  lea     rcx, [rsp+120h+var_E8]
0x18002c5f7  call    ??0?$LockSentry@VCriticalSection@@$0A@@@QEAA@AEAVCriticalSection@@@Z; LockSentry<CriticalSection,0>::LockSentry<CriticalSection,0>(CriticalSection &)
0x18002c5fc  nop
0x18002c5fd  lea     rbx, [r12+88h]
0x18002c605  lea     r8, [rbp+57h+var_D0]
0x18002c609  lea     rdx, [rsp+120h+var_F0]
0x18002c60e  mov     rcx, rbx
0x18002c611  call    ?find@?$_Tree@V?$_Tmap_traits@V?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@U?$less@V?$crt_ref@U_EAP_METHOD_INFO@@@@@std@@V?$allocator@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@5@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$crt_ref@U_EAP_METHOD_INFO@@@@U_EapMethodSlot@EapLm@@@std@@@std@@@std@@@2@AEBV?$crt_ref@U_EAP_METHOD_INFO@@@@@Z; std::_Tree<std::_Tmap_traits<crt_ref<_EAP_METHOD_INFO>,EapLm::_EapMethodSlot,std::less<crt_ref<_EAP_METHOD_INFO>>,std::allocator<std::pair<crt_ref<_EAP_METHOD_INFO> const,EapLm::_EapMethodSlot>>,0>>::find(crt_ref<_EAP_METHOD_INFO> const &)
0x18002c616  mov     r9, [rsp+120h+var_F0]
0x18002c61b  cmp     r9, [rbx]
0x18002c61e  jz      loc_18002C6EA
0x18002c624  xor     ebx, ebx
0x18002c626  mov     [rsp+120h+var_F0], rbx
0x18002c62b  lea     r14, [r9+50h]
0x18002c62f  xor     edi, edi
0x18002c631  cmp     [r14], rdi
0x18002c634  jnz     short loc_18002C692
0x18002c636  mov     rax, [r12]
0x18002c63a  mov     r9d, [r9+58h]
0x18002c63e  mov     r8, rsi
0x18002c641  lea     rdx, [rsp+120h+var_D8]
0x18002c646  mov     rcx, r12
0x18002c649  mov     rax, [rax+28h]
0x18002c64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c652  mov     rdx, rax
0x18002c655  lea     rcx, [rsp+120h+var_F0]
0x18002c65a  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18002c65f  mov     rcx, [rsp+120h+var_D8]; this
0x18002c664  test    rcx, rcx
0x18002c667  jz      short loc_18002C66E
0x18002c669  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002c66e  mov     rbx, [rsp+120h+var_F0]
0x18002c673  mov     rdi, rbx
0x18002c676  mov     rax, [rbx]
0x18002c679  mov     rcx, rbx
0x18002c67c  mov     rax, [rax+8]
0x18002c680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c685  lea     rdx, [rsp+120h+var_F0]
0x18002c68a  mov     rcx, r14
0x18002c68d  call    ??4?$SmartPointer@UIEapMethod@EapLm@@@@QEAAAEAV0@AEBV0@@Z; SmartPointer<EapLm::IEapMethod>::operator=(SmartPointer<EapLm::IEapMethod> const &)
0x18002c692  mov     rax, [r14]
0x18002c695  mov     [r15], rax
0x18002c698  test    rax, rax
0x18002c69b  jz      short loc_18002C6A1
0x18002c69d  lock inc dword ptr [rax+8]
0x18002c6a1  test    rdi, rdi
0x18002c6a4  jz      short loc_18002C6AF
0x18002c6a6  mov     rcx, rbx; this
0x18002c6a9  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18002c6ae  nop
0x18002c6af  mov     rcx, [rsp+120h+var_E8]
0x18002c6b4  add     rcx, 10h; lpCriticalSection
0x18002c6b8  call    cs:__imp_LeaveCriticalSection
0x18002c6be  nop
0x18002c6bf  lea     rcx, [rbp+57h+var_D0]
0x18002c6c3  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<HeapAllocator>(_EAP_METHOD_INFO &)
0x18002c6c8  nop
0x18002c6c9  mov     rax, r15
0x18002c6cc  mov     rcx, [rbp+57h+var_40]
0x18002c6d0  xor     rcx, rsp; StackCookie
0x18002c6d3  call    __security_check_cookie
0x18002c6d8  add     rsp, 0F0h
0x18002c6df  pop     r15
0x18002c6e1  pop     r14
0x18002c6e3  pop     r12
0x18002c6e5  pop     rdi
0x18002c6e6  pop     rsi
0x18002c6e7  pop     rbx
0x18002c6e8  pop     rbp
0x18002c6e9  retn
0x18002c6ea  mov     r9d, 57h ; 'W'; unsigned int
0x18002c6f0  mov     r8, rsi; struct EapHost::EapMethodType *
0x18002c6f3  mov     edx, 80420011h; unsigned int
0x18002c6f8  lea     rcx, [rbp+57h+var_A0]; this
0x18002c6fc  call    ??0EapError@EapHost@@QEAA@IPEBVEapMethodType@1@I@Z; EapHost::EapError::EapError(uint,EapHost::EapMethodType const *,uint)
0x18002c701  nop
0x18002c702  movzx   r8d, byte ptr [rsi+8]
0x18002c707  mov     r9d, [rsi+18h]
0x18002c70b  xor     edx, edx; unsigned int
0x18002c70d  lea     rcx, [rbp+57h+var_A0]; this
0x18002c711  call    ?FillRootCauseString@EapError@EapHost@@QEAAXKZZ; EapHost::EapError::FillRootCauseString(ulong,...)
0x18002c716  lea     rcx, [rbp+57h+var_A0]; struct EapHost::EapError *
0x18002c71a  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
```
