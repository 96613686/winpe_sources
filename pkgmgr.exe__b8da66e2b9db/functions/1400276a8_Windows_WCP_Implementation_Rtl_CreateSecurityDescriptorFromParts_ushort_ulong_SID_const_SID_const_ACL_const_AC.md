# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x1400276a8`
- end: `0x140027850`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `424`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140027248`

## callees

- `0x140002360`
- `0x140026548`
- `0x1400272fc`
- `0x1400276a8`

## import_xrefs

- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140027742`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x140027742`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x14002777d`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x14002777d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1400276f0`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1400276f0`
- `ntdll!RtlFreeHeap` at `0x1400277ec`
- `ntdll!RtlFreeHeap` at `0x140027827`
- `ntdll!RtlFreeHeap` at `0x1400277ec`
- `ntdll!RtlFreeHeap` at `0x140027827`

## string_xrefs

- `0x1400276fa`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002774c`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x140027787`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x14002770d`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x14002775f`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x14002779a`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x140027718`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x14002776a`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`
- `0x1400277a5`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4)
{
  NTSTATUS v6; // eax
  const char *v7; // rcx
  int v9; // ebx
  PVOID v10; // r8
  __int128 P; // [rsp+20h] [rbp-60h] BYREF
  __int64 v12; // [rsp+30h] [rbp-50h]
  const char *v13; // [rsp+38h] [rbp-48h]
  int v14; // [rsp+40h] [rbp-40h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]

  v14 = 0;
  v16 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v6 < 0 )
  {
    v12 = 346;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v13 = v7;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v14,
             &P,
             (unsigned int)v6);
  }
  v6 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
  if ( v6 < 0 )
  {
    v12 = 355;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
    goto LABEL_3;
  }
  v6 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
  if ( v6 < 0 )
  {
    v12 = 363;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    v7 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
    goto LABEL_3;
  }
  P = 0u;
  v9 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&P, SecurityDescriptor);
  if ( v9 >= 0 )
  {
    v10 = ::P;
    *(_OWORD *)&::P = P;
    if ( v10 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    return 0;
  }
  else
  {
    if ( (_QWORD)P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1400276a8  mov     [rsp-8+arg_0], rbx
0x1400276ad  mov     [rsp-8+arg_8], rdi
0x1400276b2  push    rbp
0x1400276b3  mov     rbp, rsp
0x1400276b6  sub     rsp, 80h
0x1400276bd  mov     rax, cs:__security_cookie
0x1400276c4  xor     rax, rsp
0x1400276c7  mov     [rbp+var_10], rax
0x1400276cb  xor     eax, eax
0x1400276cd  mov     [rbp+var_40], 0
0x1400276d4  xorps   xmm0, xmm0
0x1400276d7  mov     [rbp+var_18], rax
0x1400276db  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1400276df  mov     rdi, r9
0x1400276e2  mov     rbx, r8
0x1400276e5  lea     edx, [rax+1]; Revision
0x1400276e8  movups  [rbp+SecurityDescriptor], xmm0
0x1400276ec  movups  [rbp+var_28], xmm0
0x1400276f0  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400276f6  test    eax, eax
0x1400276f8  jns     short loc_140027738
0x1400276fa  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027701  mov     [rbp+var_50], 15Ah
0x140027709  mov     qword ptr [rbp+P], rcx
0x14002770d  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x140027714  mov     qword ptr [rbp+P+8], rcx
0x140027718  lea     rcx, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x14002771f  mov     [rbp+var_48], rcx
0x140027723  lea     rdx, [rbp+P]
0x140027727  lea     rcx, [rbp+var_40]
0x14002772b  mov     r8d, eax
0x14002772e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140027733  jmp     loc_14002782F
0x140027738  xor     r8d, r8d; OwnerDefaulted
0x14002773b  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002773f  mov     rdx, rbx; Owner
0x140027742  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140027748  test    eax, eax
0x14002774a  jns     short loc_140027773
0x14002774c  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x140027753  mov     [rbp+var_50], 163h
0x14002775b  mov     qword ptr [rbp+P], rcx
0x14002775f  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x140027766  mov     qword ptr [rbp+P+8], rcx
0x14002776a  lea     rcx, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x140027771  jmp     short loc_14002771F
0x140027773  xor     r8d, r8d; GroupDefaulted
0x140027776  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002777a  mov     rdx, rdi; Group
0x14002777d  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140027783  test    eax, eax
0x140027785  jns     short loc_1400277B1
0x140027787  lea     rcx, aOnecoreBaseWcp_1; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x14002778e  mov     [rbp+var_50], 16Bh
0x140027796  mov     qword ptr [rbp+P], rcx
0x14002779a  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x1400277a1  mov     qword ptr [rbp+P+8], rcx
0x1400277a5  lea     rcx, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x1400277ac  jmp     loc_14002771F
0x1400277b1  lea     rdx, [rbp+SecurityDescriptor]
0x1400277b5  mov     qword ptr [rbp+P], 0
0x1400277bd  lea     rcx, [rbp+P]
0x1400277c1  mov     qword ptr [rbp+P+8], 0
0x1400277c9  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x1400277ce  mov     ebx, eax
0x1400277d0  test    eax, eax
0x1400277d2  jns     short loc_1400277F6
0x1400277d4  mov     r8, qword ptr [rbp+P]; P
0x1400277d8  test    r8, r8
0x1400277db  jz      short loc_1400277F2
0x1400277dd  mov     rcx, gs:60h
0x1400277e6  xor     edx, edx; Flags
0x1400277e8  mov     rcx, [rcx+30h]; HeapHandle
0x1400277ec  call    cs:__imp_RtlFreeHeap
0x1400277f2  mov     eax, ebx
0x1400277f4  jmp     short loc_14002782F
0x1400277f6  mov     rax, qword ptr [rbp+P]
0x1400277fa  mov     r8, qword ptr cs:P; P
0x140027801  mov     qword ptr cs:P, rax
0x140027808  mov     rax, qword ptr [rbp+P+8]
0x14002780c  mov     qword ptr cs:P+8, rax
0x140027813  test    r8, r8
0x140027816  jz      short loc_14002782D
0x140027818  mov     rcx, gs:60h
0x140027821  xor     edx, edx; Flags
0x140027823  mov     rcx, [rcx+30h]; HeapHandle
0x140027827  call    cs:__imp_RtlFreeHeap
0x14002782d  xor     eax, eax
0x14002782f  mov     rcx, [rbp+var_10]
0x140027833  xor     rcx, rsp; StackCookie
0x140027836  call    __security_check_cookie
0x14002783b  lea     r11, [rsp+80h+var_s0]
0x140027843  mov     rbx, [r11+10h]
0x140027847  mov     rdi, [r11+18h]
0x14002784b  mov     rsp, r11
0x14002784e  pop     rbp
0x14002784f  retn
```
