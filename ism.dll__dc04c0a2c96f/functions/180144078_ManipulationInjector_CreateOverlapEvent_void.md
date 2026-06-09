# ManipulationInjector::CreateOverlapEvent(void)

- ea: `0x180144078`
- end: `0x180144125`
- name: `?CreateOverlapEvent@ManipulationInjector@@AEAAXXZ`
- size: `173`
- prototype: `void __fastcall(ManipulationInjector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801442c4`

## callees

- `0x18008dcac`
- `0x180116cf0`
- `0x180144078`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801440ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801440ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x1801440d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExA` at `0x1801440d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801440b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801440b9`

## pseudocode

```c
void __fastcall ManipulationInjector::CreateOverlapEvent(ManipulationInjector *this)
{
  HANDLE v2; // rax
  DWORD LastError; // eax
  struct _SECURITY_ATTRIBUTES SecurityDescriptor; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_QWORD *)this + 98) = 0;
  memset(&SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  SecurityDescriptor.nLength = 24;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;S-1-5-90-0)(A;;GA;;;AC)(A;;GA;;;WD)(A;;GA;;;S-1-15-3-1024-1502825166-1963708345-2616377461-25628970"
           "74-4192028372-3968301570-1997628692-1435953622)",
          1u,
          &SecurityDescriptor.lpSecurityDescriptor,
          0)
    || (v2 = CreateEventExA(&SecurityDescriptor, "ManipulationInjectorEnableOverlapEvent", 0, 0x1F0003u),
        (*((_QWORD *)this + 98) = v2) == 0) )
  {
    LastError = GetLastError();
    if ( LastError )
      wil::details::in1diag3::_FailFast_Win32(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\windows\\dwm\\manipulationinjector\\lib\\manipulationinjector.cpp",
        (const char *)LastError,
        SecurityDescriptor.nLength);
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecoreuap\\windows\\dwm\\manipulationinjector\\lib\\manipulationinjector.cpp",
      (const char *)0x80004005LL,
      SecurityDescriptor.nLength);
  }
}

```

## disassembly

```asm
0x180144078  push    rbx
0x18014407a  sub     rsp, 40h
0x18014407e  xor     eax, eax
0x180144080  mov     qword ptr [rcx+310h], 0
0x18014408b  xorps   xmm0, xmm0
0x18014408e  mov     [rsp+48h+var_18], rax
0x180144093  mov     rbx, rcx
0x180144096  mov     dword ptr [rsp+48h+var_18], eax
0x18014409a  movups  xmmword ptr [rsp+48h+SecurityDescriptor], xmm0
0x18014409f  lea     edx, [rax+1]; StringSDRevision
0x1801440a2  mov     dword ptr [rsp+48h+SecurityDescriptor], 18h; int
0x1801440aa  xor     r9d, r9d; SecurityDescriptorSize
0x1801440ad  lea     r8, [rsp+48h+SecurityDescriptor+8]; SecurityDescriptor
0x1801440b2  lea     rcx, aDAGaS15900AGaA; "D:(A;;GA;;;S-1-5-90-0)(A;;GA;;;AC)(A;;G"...
0x1801440b9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1801440bf  test    eax, eax
0x1801440c1  jz      short loc_1801440EA
0x1801440c3  mov     r9d, 1F0003h; dwDesiredAccess
0x1801440c9  lea     rdx, aManipulationin; "ManipulationInjectorEnableOverlapEvent"
0x1801440d0  xor     r8d, r8d; dwFlags
0x1801440d3  lea     rcx, [rsp+48h+SecurityDescriptor]; lpEventAttributes
0x1801440d8  call    cs:__imp_CreateEventExA
0x1801440de  mov     [rbx+310h], rax
0x1801440e5  test    rax, rax
0x1801440e8  jnz     short loc_18014411F
0x1801440ea  call    cs:__imp_GetLastError
0x1801440f0  mov     rcx, [rsp+48h]; this
0x1801440f5  lea     r8, aOnecoreuapWind_222; "onecoreuap\\windows\\dwm\\manipulationi"...
0x1801440fc  test    eax, eax
0x1801440fe  jz      short loc_18014410E
0x180144100  mov     r9d, eax; char *
0x180144103  mov     edx, 70h ; 'p'; void *
0x180144108  call    ?_FailFast_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_FailFast_Win32(void *,uint,char const *,ulong)
0x18014410e  mov     r9d, 80004005h; char *
0x180144114  mov     edx, 73h ; 's'; void *
0x180144119  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18014411f  add     rsp, 40h
0x180144123  pop     rbx
0x180144124  retn
```
