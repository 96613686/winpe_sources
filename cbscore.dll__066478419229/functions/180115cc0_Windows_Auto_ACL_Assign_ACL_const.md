# Windows::Auto<_ACL>::Assign(_ACL const *)

- ea: `0x180115cc0`
- end: `0x180115e54`
- name: `?Assign@?$Auto@U_ACL@@@Windows@@QEAAJPEBU_ACL@@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180116538`

## callees

- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800eb920`
- `0x1800ef360`
- `0x180115cc0`
- `0x1802cf7cc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180115dc9`
- `ntdll!RtlAllocateHeap` at `0x180115dc9`
- `ntdll!RtlValidAcl` at `0x180115d0b`
- `ntdll!RtlValidAcl` at `0x180115d0b`
- `ntdll!RtlQueryInformationAcl` at `0x180115d67`
- `ntdll!RtlQueryInformationAcl` at `0x180115d67`

## string_xrefs

- `0x180115d1b`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115d7a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115ddd`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180115e03`: `m_pACL`
- `0x180115da0`: `::RtlQueryInformationAcl( pAcl, &SizeInfo, sizeof SizeInfo, ::AclSizeInformation)`
- `0x180115d41`: `pAcl == 0 || ::RtlValidAcl(pAcl)`
- `0x180115d32`: `Windows::Auto<struct _ACL>::Assign`
- `0x180115d91`: `Windows::Auto<struct _ACL>::Assign`
- `0x180115df4`: `Windows::Auto<struct _ACL>::Assign`

## pseudocode

```c
__int64 __fastcall Windows::Auto<_ACL>::Assign(_QWORD *a1, struct _ACL *a2)
{
  NTSTATUS v5; // eax
  PVOID Heap; // rax
  const char *v7; // [rsp+20h] [rbp-40h] BYREF
  const char *v8; // [rsp+28h] [rbp-38h]
  __int64 v9; // [rsp+30h] [rbp-30h]
  const char *v10; // [rsp+38h] [rbp-28h]
  __int64 Information; // [rsp+40h] [rbp-20h] BYREF
  int v12; // [rsp+48h] [rbp-18h]
  int v13; // [rsp+50h] [rbp-10h] BYREF

  v13 = 0;
  Information = 0;
  v12 = 0;
  if ( *a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180115E53LL);
  }
  if ( a2 )
  {
    if ( !RtlValidAcl(a2) )
    {
      v9 = 980;
      v7 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v8 = "Windows::Auto<struct _ACL>::Assign";
      v10 = "pAcl == 0 || ::RtlValidAcl(pAcl)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v13,
               &v7);
    }
    v5 = RtlQueryInformationAcl(a2, &Information, 0xCu, AclSizeInformation);
    if ( v5 < 0 )
    {
      v9 = 988;
      v7 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v8 = "Windows::Auto<struct _ACL>::Assign";
      v10 = "::RtlQueryInformationAcl( pAcl, &SizeInfo, sizeof SizeInfo, ::AclSizeInformation)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v13,
               &v7,
               (unsigned int)v5);
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(HIDWORD(Information) + v12));
    *a1 = Heap;
    if ( !Heap )
    {
      v9 = 995;
      v7 = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v8 = "Windows::Auto<struct _ACL>::Assign";
      v10 = "m_pACL";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
               &v13,
               &v7);
    }
    memcpy_0(Heap, a2, (unsigned int)(HIDWORD(Information) + v12));
  }
  return 0;
}

```

## disassembly

```asm
0x180115cc0  mov     [rsp-8+arg_10], rbx
0x180115cc5  mov     [rsp-8+arg_18], rdi
0x180115cca  push    rbp
0x180115ccb  mov     rbp, rsp
0x180115cce  sub     rsp, 60h
0x180115cd2  mov     rax, cs:__security_cookie
0x180115cd9  xor     rax, rsp
0x180115cdc  mov     [rbp+var_8], rax
0x180115ce0  xor     eax, eax
0x180115ce2  mov     [rbp+var_10], 0
0x180115ce9  mov     rbx, rdx
0x180115cec  mov     rdi, rcx
0x180115cef  mov     [rbp+Information], rax
0x180115cf3  mov     [rbp+var_18], eax
0x180115cf6  cmp     [rcx], rax
0x180115cf9  jnz     loc_180115E49
0x180115cff  test    rdx, rdx
0x180115d02  jz      loc_180115E28
0x180115d08  mov     rcx, rdx; Acl
0x180115d0b  call    cs:__imp_RtlValidAcl
0x180115d12  nop     dword ptr [rax+rax+00h]
0x180115d17  test    al, al
0x180115d19  jnz     short loc_180115D56
0x180115d1b  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115d22  mov     [rbp+var_30], 3D4h
0x180115d2a  mov     [rbp+var_40], rax
0x180115d2e  lea     rdx, [rbp+var_40]
0x180115d32  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x180115d39  mov     [rbp+var_38], rax
0x180115d3d  lea     rcx, [rbp+var_10]
0x180115d41  lea     rax, aPacl0Rtlvalida; "pAcl == 0 || ::RtlValidAcl(pAcl)"
0x180115d48  mov     [rbp+var_28], rax
0x180115d4c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180115d51  jmp     loc_180115E2A
0x180115d56  mov     r9d, 2; InformationClass
0x180115d5c  lea     rdx, [rbp+Information]; Information
0x180115d60  mov     rcx, rbx; Acl
0x180115d63  lea     r8d, [r9+0Ah]; InformationLength
0x180115d67  call    cs:__imp_RtlQueryInformationAcl
0x180115d6e  nop     dword ptr [rax+rax+00h]
0x180115d73  mov     r8d, eax
0x180115d76  test    eax, eax
0x180115d78  jns     short loc_180115DB2
0x180115d7a  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115d81  mov     [rbp+var_30], 3DCh
0x180115d89  mov     [rbp+var_40], rax
0x180115d8d  lea     rdx, [rbp+var_40]
0x180115d91  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x180115d98  mov     [rbp+var_38], rax
0x180115d9c  lea     rcx, [rbp+var_10]
0x180115da0  lea     rax, aRtlqueryinform; "::RtlQueryInformationAcl( pAcl, &SizeIn"...
0x180115da7  mov     [rbp+var_28], rax
0x180115dab  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180115db0  jmp     short loc_180115E2A
0x180115db2  mov     rcx, gs:60h
0x180115dbb  xor     edx, edx; Flags
0x180115dbd  mov     r8d, [rbp+var_18]
0x180115dc1  add     r8d, dword ptr [rbp+Information+4]; Size
0x180115dc5  mov     rcx, [rcx+30h]; HeapHandle
0x180115dc9  call    cs:__imp_RtlAllocateHeap
0x180115dd0  nop     dword ptr [rax+rax+00h]
0x180115dd5  mov     [rdi], rax
0x180115dd8  test    rax, rax
0x180115ddb  jnz     short loc_180115E15
0x180115ddd  lea     rax, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180115de4  mov     [rbp+var_30], 3E3h
0x180115dec  mov     [rbp+var_40], rax
0x180115df0  lea     rdx, [rbp+var_40]
0x180115df4  lea     rax, aWindowsAutoStr_0; "Windows::Auto<struct _ACL>::Assign"
0x180115dfb  mov     [rbp+var_38], rax
0x180115dff  lea     rcx, [rbp+var_10]
0x180115e03  lea     rax, aMPacl; "m_pACL"
0x180115e0a  mov     [rbp+var_28], rax
0x180115e0e  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180115e13  jmp     short loc_180115E2A
0x180115e15  mov     r8d, [rbp+var_18]
0x180115e19  mov     rdx, rbx; Src
0x180115e1c  add     r8d, dword ptr [rbp+Information+4]; Size
0x180115e20  mov     rcx, rax; void *
0x180115e23  call    memcpy_0
0x180115e28  xor     eax, eax
0x180115e2a  mov     rcx, [rbp+var_8]
0x180115e2e  xor     rcx, rsp; StackCookie
0x180115e31  call    __security_check_cookie
0x180115e36  lea     r11, [rsp+60h+var_s0]
0x180115e3b  mov     rbx, [r11+20h]
0x180115e3f  mov     rdi, [r11+28h]
0x180115e43  mov     rsp, r11
0x180115e46  pop     rbp
0x180115e47  retn
0x180115e49  mov     ecx, 0C00000E5h; int
0x180115e4e  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
