# Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(ushort,ulong,_SID const *,_SID const *,_ACL const *,_ACL const *,Windows::Auto<_SECURITY_DESCRIPTOR> *)

- ea: `0x1800135f4`
- end: `0x18001376e`
- name: `?CreateSecurityDescriptorFromParts@Rtl@Implementation@WCP@Windows@@YAJGKPEBU_SID@@0PEBU_ACL@@1PEAV?$Auto@U_SECURITY_DESCRIPTOR@@@4@@Z`
- size: `378`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013040`

## callees

- `0x180001540`
- `0x180012fd8`
- `0x180013194`
- `0x1800135f4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001370e`
- `ntdll!RtlFreeHeap` at `0x18001374a`
- `ntdll!RtlFreeHeap` at `0x18001370e`
- `ntdll!RtlFreeHeap` at `0x18001374a`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180013688`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180013688`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800136af`
- `ntdll!RtlSetGroupSecurityDescriptor` at `0x1800136af`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001362f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18001362f`

## string_xrefs

- `0x18001364a`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180013643`: `RtlCreateSecurityDescriptor( &AbsoluteSD, (1))`
- `0x180013660`: `Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts`
- `0x1800136c3`: `::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)`
- `0x18001369c`: `::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)`

## pseudocode

```c
__int64 __fastcall Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts(
        __int64 a1,
        __int64 a2,
        void *a3,
        void *a4)
{
  int v6; // ebx
  const char *v7; // rax
  PVOID v9; // r8
  __int128 P; // [rsp+20h] [rbp-50h] BYREF
  __int64 v11; // [rsp+30h] [rbp-40h]
  const char *v12; // [rsp+38h] [rbp-38h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+60h] [rbp-10h]

  v14 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v6 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v6 < 0 )
  {
    v11 = 346;
    v7 = "RtlCreateSecurityDescriptor( &AbsoluteSD, (1))";
LABEL_3:
    v12 = v7;
    *(_QWORD *)&P = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    *((_QWORD *)&P + 1) = "Windows::WCP::Implementation::Rtl::CreateSecurityDescriptorFromParts";
    RtlReportErrorOrigination(&P, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v6);
    return (unsigned int)v6;
  }
  v6 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, a3, 0);
  if ( v6 < 0 )
  {
    v11 = 355;
    v7 = "::RtlSetOwnerSecurityDescriptor( &AbsoluteSD, (PSID)Owner, 0)";
    goto LABEL_3;
  }
  v6 = RtlSetGroupSecurityDescriptor(SecurityDescriptor, a4, 0);
  if ( v6 < 0 )
  {
    v11 = 363;
    v7 = "::RtlSetGroupSecurityDescriptor( &AbsoluteSD, (PSID)Group, 0)";
    goto LABEL_3;
  }
  P = 0u;
  v6 = Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(&P, SecurityDescriptor);
  if ( v6 < 0 )
  {
    if ( (_QWORD)P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
    return (unsigned int)v6;
  }
  v9 = ::P;
  *(_OWORD *)&::P = P;
  if ( v9 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return 0;
}

```

## disassembly

```asm
0x1800135f4  mov     [rsp-18h+arg_0], rbx
0x1800135f9  push    rbp
0x1800135fa  push    rsi
0x1800135fb  push    rdi
0x1800135fc  mov     rbp, rsp
0x1800135ff  sub     rsp, 70h
0x180013603  mov     rax, cs:__security_cookie
0x18001360a  xor     rax, rsp
0x18001360d  mov     [rbp+var_8], rax
0x180013611  xor     eax, eax
0x180013613  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180013617  xorps   xmm0, xmm0
0x18001361a  mov     [rbp+var_10], rax
0x18001361e  mov     rsi, r9
0x180013621  mov     rdi, r8
0x180013624  movups  [rbp+SecurityDescriptor], xmm0
0x180013628  lea     edx, [rax+1]; Revision
0x18001362b  movups  [rbp+var_20], xmm0
0x18001362f  call    cs:__imp_RtlCreateSecurityDescriptor
0x180013635  mov     ebx, eax
0x180013637  test    eax, eax
0x180013639  jns     short loc_18001367E
0x18001363b  mov     [rbp+var_40], 15Ah
0x180013643  lea     rax, aRtlcreatesecur; "RtlCreateSecurityDescriptor( &AbsoluteS"...
0x18001364a  lea     rcx, aOnecoreBaseWcp; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180013651  mov     [rbp+var_38], rax
0x180013655  mov     qword ptr [rbp+P], rcx
0x180013659  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180013660  lea     rcx, aWindowsWcpImpl_1; "Windows::WCP::Implementation::Rtl::Crea"...
0x180013667  mov     r8d, ebx
0x18001366a  mov     qword ptr [rbp+P+8], rcx
0x18001366e  lea     rcx, [rbp+P]
0x180013672  call    RtlReportErrorOrigination
0x180013677  mov     eax, ebx
0x180013679  jmp     loc_180013752
0x18001367e  xor     r8d, r8d; OwnerDefaulted
0x180013681  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180013685  mov     rdx, rdi; Owner
0x180013688  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18001368e  mov     ebx, eax
0x180013690  test    eax, eax
0x180013692  jns     short loc_1800136A5
0x180013694  mov     [rbp+var_40], 163h
0x18001369c  lea     rax, aRtlsetownersec; "::RtlSetOwnerSecurityDescriptor( &Absol"...
0x1800136a3  jmp     short loc_18001364A
0x1800136a5  xor     r8d, r8d; GroupDefaulted
0x1800136a8  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800136ac  mov     rdx, rsi; Group
0x1800136af  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x1800136b5  mov     ebx, eax
0x1800136b7  test    eax, eax
0x1800136b9  jns     short loc_1800136CF
0x1800136bb  mov     [rbp+var_40], 16Bh
0x1800136c3  lea     rax, aRtlsetgroupsec; "::RtlSetGroupSecurityDescriptor( &Absol"...
0x1800136ca  jmp     loc_18001364A
0x1800136cf  lea     rdx, [rbp+SecurityDescriptor]
0x1800136d3  mov     qword ptr [rbp+P], 0
0x1800136db  lea     rcx, [rbp+P]
0x1800136df  mov     qword ptr [rbp+P+8], 0
0x1800136e7  call    ?Assign@?$Auto@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAJPEBU_SECURITY_DESCRIPTOR@@@Z; Windows::Auto<_SECURITY_DESCRIPTOR>::Assign(_SECURITY_DESCRIPTOR const *)
0x1800136ec  mov     ebx, eax
0x1800136ee  test    eax, eax
0x1800136f0  jns     short loc_180013719
0x1800136f2  mov     r8, qword ptr [rbp+P]; P
0x1800136f6  test    r8, r8
0x1800136f9  jz      loc_180013677
0x1800136ff  mov     rcx, gs:60h
0x180013708  xor     edx, edx; Flags
0x18001370a  mov     rcx, [rcx+30h]; HeapHandle
0x18001370e  call    cs:__imp_RtlFreeHeap
0x180013714  jmp     loc_180013677
0x180013719  mov     rax, qword ptr [rbp+P]
0x18001371d  mov     r8, qword ptr cs:P; P
0x180013724  mov     qword ptr cs:P, rax
0x18001372b  mov     rax, qword ptr [rbp+P+8]
0x18001372f  mov     qword ptr cs:P+8, rax
0x180013736  test    r8, r8
0x180013739  jz      short loc_180013750
0x18001373b  mov     rcx, gs:60h
0x180013744  xor     edx, edx; Flags
0x180013746  mov     rcx, [rcx+30h]; HeapHandle
0x18001374a  call    cs:__imp_RtlFreeHeap
0x180013750  xor     eax, eax
0x180013752  mov     rcx, [rbp+var_8]
0x180013756  xor     rcx, rsp; StackCookie
0x180013759  call    __security_check_cookie
0x18001375e  mov     rbx, [rsp+70h+arg_0]
0x180013766  add     rsp, 70h
0x18001376a  pop     rdi
0x18001376b  pop     rsi
0x18001376c  pop     rbp
0x18001376d  retn
```
