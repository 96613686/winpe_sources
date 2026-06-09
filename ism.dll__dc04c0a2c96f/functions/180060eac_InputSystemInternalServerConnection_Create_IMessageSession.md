# InputSystemInternalServerConnection::Create(IMessageSession *)

- ea: `0x180060eac`
- end: `0x180061044`
- name: `?Create@InputSystemInternalServerConnection@@SA?AV?$ComPtr@VInputSystemInternalServerConnection@@@WRL@Microsoft@@PEAUIMessageSession@@@Z`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060df0`

## callees

- `0x180012b74`
- `0x18003b6fc`
- `0x180060eac`
- `0x18006104c`
- `0x180061168`
- `0x18008dcac`
- `0x180095eb0`
- `0x1800f0acc`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180060ee7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180060ee7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006102d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006102d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct ISMBamos_AutoBamos::BamoConnection **__fastcall InputSystemInternalServerConnection::Create(
        struct ISMBamos_AutoBamos::BamoConnection **a1,
        __int64 a2)
{
  const char *v4; // r9
  __int64 (__fastcall *v5)(__int64, PSECURITY_DESCRIPTOR, __int64 *); // rbx
  int v6; // eax
  int v7; // r9d
  int v8; // eax
  InputSystemInternal *v9; // rax
  InputSystemInternal *v10; // rbx
  struct ISMBamos_AutoBamos::BamoConnection *v11; // rsi
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v15; // [rsp+20h] [rbp-30h]
  int v16; // [rsp+20h] [rbp-30h]
  InputSystemInternal *v17; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v20; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+38h] BYREF

  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;0x001F0003;;;S-1-5-90-0)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\system\\inputsysteminternalserverconnection.cpp",
      v4);
  v20 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, __int64 *))(*(_QWORD *)a2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v6 = v5(a2, SecurityDescriptor, &v20);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\system\\inputsysteminternalserverconnection.cpp",
      (const char *)(unsigned int)v6,
      v15);
  *a1 = 0;
  Microsoft::WRL::ComPtr<InputSystemInternalServerConnection>::InternalRelease(a1);
  v17 = 0;
  v18 = 1;
  v8 = Microsoft::Bamo::BaseBamoConnection::CreateServer<InputSystemInternalServerConnection>(
         a2,
         v20,
         (unsigned int)&v17,
         v7,
         (__int64)a1);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\system\\inputsysteminternalserverconnection.cpp",
      (const char *)(unsigned int)v8,
      v16);
  v17 = (InputSystemInternal *)operator new(0x48u);
  v9 = InputSystemInternal::InputSystemInternal(v17, *a1);
  v10 = v9;
  v11 = *a1;
  if ( *((InputSystemInternal **)*a1 + 31) != v9 )
  {
    if ( v9 )
      (**(void (__fastcall ***)(InputSystemInternal *))v9)(v9);
    v12 = *((_QWORD *)v11 + 31);
    *((_QWORD *)v11 + 31) = v10;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  }
  v13 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return a1;
}

```

## disassembly

```asm
0x180060eac  mov     [rsp-18h+arg_8], rbx
0x180060eb1  mov     [rsp-18h+arg_0], rcx
0x180060eb6  push    rbp
0x180060eb7  push    rsi
0x180060eb8  push    rdi
0x180060eb9  mov     rbp, rsp
0x180060ebc  sub     rsp, 50h
0x180060ec0  mov     rsi, rdx
0x180060ec3  mov     rdi, rcx
0x180060ec6  mov     [rbp+var_20], 0
0x180060ecd  mov     [rbp+SecurityDescriptor], 0
0x180060ed5  xor     r9d, r9d; SecurityDescriptorSize
0x180060ed8  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180060edc  lea     edx, [r9+1]; StringSDRevision
0x180060ee0  lea     rcx, aDA0x001f0003S1; "D:(A;;0x001F0003;;;S-1-5-90-0)"
0x180060ee7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180060eed  mov     rcx, [rbp+18h]; this
0x180060ef1  test    eax, eax
0x180060ef3  jnz     short loc_180060F05
0x180060ef5  lea     r8, aOnecoreuapWind_210; "onecoreuap\\windows\\moderncore\\inputv"...
0x180060efc  lea     edx, [rax+1Dh]; void *
0x180060eff  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180060f05  mov     [rbp+arg_10], 0
0x180060f0d  mov     rax, [rsi]
0x180060f10  mov     rbx, [rax+40h]
0x180060f14  lea     rcx, [rbp+arg_10]
0x180060f18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060f1d  lea     r8, [rbp+arg_10]
0x180060f21  mov     rdx, [rbp+SecurityDescriptor]
0x180060f25  mov     rcx, rsi
0x180060f28  mov     rax, rbx
0x180060f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060f30  mov     rcx, [rbp+18h]; this
0x180060f34  test    eax, eax
0x180060f36  jns     short loc_180060F4D
0x180060f38  mov     r9d, eax; char *
0x180060f3b  lea     r8, aOnecoreuapWind_210; "onecoreuap\\windows\\moderncore\\inputv"...
0x180060f42  mov     edx, 22h ; '"'; void *
0x180060f47  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180060f4d  mov     qword ptr [rdi], 0
0x180060f54  mov     [rbp+var_20], 1
0x180060f5b  mov     rcx, rdi
0x180060f5e  call    ?InternalRelease@?$ComPtr@VInputSystemInternalServerConnection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<InputSystemInternalServerConnection>::InternalRelease(void)
0x180060f63  mov     [rbp+var_10], 0
0x180060f6b  mov     [rbp+var_8], 1
0x180060f72  mov     eax, [rbp+var_4]
0x180060f75  mov     [rbp+var_4], eax
0x180060f78  mov     qword ptr [rsp+50h+var_30], rdi; int
0x180060f7d  lea     r8, [rbp+var_10]
0x180060f81  mov     rdx, [rbp+arg_10]
0x180060f85  mov     rcx, rsi
0x180060f88  call    ??$CreateServer@VInputSystemInternalServerConnection@@@BaseBamoConnection@Bamo@Microsoft@@SAJPEAUIMessageSession@@PEAUIMessagePort@@UMsgScopeID@@PEBGPEAPEAVInputSystemInternalServerConnection@@@Z; Microsoft::Bamo::BaseBamoConnection::CreateServer<InputSystemInternalServerConnection>(IMessageSession *,IMessagePort *,MsgScopeID,ushort const *,InputSystemInternalServerConnection * *)
0x180060f8d  mov     rcx, [rbp+18h]; this
0x180060f91  test    eax, eax
0x180060f93  jns     short loc_180060FAA
0x180060f95  mov     r9d, eax; char *
0x180060f98  lea     r8, aOnecoreuapWind_210; "onecoreuap\\windows\\moderncore\\inputv"...
0x180060f9f  mov     edx, 2Bh ; '+'; void *
0x180060fa4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180060faa  mov     ecx, 48h ; 'H'; Size
0x180060faf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180060fb4  mov     [rbp+var_10], rax
0x180060fb8  mov     rdx, [rdi]; struct ISMBamos_AutoBamos::BamoConnection *
0x180060fbb  mov     rcx, rax; this
0x180060fbe  call    ??0InputSystemInternal@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@@Z; InputSystemInternal::InputSystemInternal(ISMBamos_AutoBamos::BamoConnection *)
0x180060fc3  mov     rbx, rax
0x180060fc6  mov     rsi, [rdi]
0x180060fc9  cmp     [rsi+0F8h], rax
0x180060fd0  jz      short loc_180061006
0x180060fd2  test    rax, rax
0x180060fd5  jz      short loc_180060FE6
0x180060fd7  mov     rcx, [rax]
0x180060fda  mov     rax, [rcx]
0x180060fdd  mov     rcx, rbx
0x180060fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060fe5  nop
0x180060fe6  mov     rcx, [rsi+0F8h]
0x180060fed  mov     [rsi+0F8h], rbx
0x180060ff4  test    rcx, rcx
0x180060ff7  jz      short loc_180061006
0x180060ff9  mov     rax, [rcx]
0x180060ffc  mov     rax, [rax+8]
0x180061000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061005  nop
0x180061006  mov     rcx, [rbp+arg_10]
0x18006100a  test    rcx, rcx
0x18006100d  jz      short loc_180061024
0x18006100f  mov     [rbp+arg_10], 0
0x180061017  mov     rax, [rcx]
0x18006101a  mov     rax, [rax+10h]
0x18006101e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061023  nop
0x180061024  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180061028  test    rcx, rcx
0x18006102b  jz      short loc_180061033
0x18006102d  call    cs:__imp_LocalFree
0x180061033  mov     rax, rdi
0x180061036  mov     rbx, [rsp+50h+arg_8]
0x18006103b  add     rsp, 50h
0x18006103f  pop     rdi
0x180061040  pop     rsi
0x180061041  pop     rbp
0x180061042  retn
```
