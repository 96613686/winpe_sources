# InputSystemServerConnection::Create(IMessageSession *)

- ea: `0x18003b57c`
- end: `0x18003b6f6`
- name: `?Create@InputSystemServerConnection@@SA?AV?$ComPtr@VInputSystemServerConnection@@@WRL@Microsoft@@PEAUIMessageSession@@@Z`
- size: `378`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012ee0`
- `0x180014530`
- `0x180017e84`
- `0x180024d08`
- `0x180054a20`

## callees

- `0x180012b74`
- `0x18003912c`
- `0x18003b57c`
- `0x18003b6fc`
- `0x18008dcac`
- `0x180095eb0`
- `0x1800a5810`
- `0x1800f0acc`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b5c5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003b5c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b6df`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct ISMBamos_AutoBamos::BamoConnection **__fastcall InputSystemServerConnection::Create(
        struct ISMBamos_AutoBamos::BamoConnection **a1,
        __int64 a2)
{
  const char *v4; // r9
  __int64 (__fastcall *v5)(__int64, PSECURITY_DESCRIPTOR, __int64 *); // rbx
  int v6; // eax
  int v7; // r9d
  int v8; // eax
  struct ISMBamos_AutoBamos::BamoConnection *v9; // rbx
  InputSystem *v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  int v15; // [rsp+20h] [rbp-30h]
  InputSystem *v16; // [rsp+40h] [rbp-10h] BYREF
  int v17; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+38h] BYREF

  *a1 = 0;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;SY)(A;;0x001F0003;;;WD)(A;;0x001F0003;;;AC)(A;;0x001F0003;;;S-1-15-3-1024-1502825166-1963708345-261"
           "6377461-2562897074-4192028372-3968301570-1997628692-1435953622)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\inputsystemserverconnection.cpp",
      v4);
  v19 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, PSECURITY_DESCRIPTOR, __int64 *))(*(_QWORD *)a2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v6 = v5(a2, SecurityDescriptor, &v19);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\inputsystemserverconnection.cpp",
      (const char *)(unsigned int)v6,
      v14);
  Microsoft::WRL::ComPtr<InputSystemInternalServerConnection>::InternalRelease(a1);
  v16 = 0;
  v17 = 1;
  v8 = Microsoft::Bamo::BaseBamoConnection::CreateServer<InputSystemServerConnection>(
         a2,
         v19,
         (unsigned int)&v16,
         v7,
         (__int64)a1);
  if ( v8 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\bamos\\server\\inputsystemserverconnection.cpp",
      (const char *)(unsigned int)v8,
      v15);
  v9 = *a1;
  v16 = (InputSystem *)operator new(0xB8u);
  v10 = InputSystem::InputSystem(v16, *a1);
  v11 = *((_QWORD *)v9 + 31);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  *((_QWORD *)v9 + 31) = v10;
  v12 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return a1;
}

```

## disassembly

```asm
0x18003b57c  mov     [rsp-18h+arg_8], rbx
0x18003b581  mov     [rsp-18h+arg_0], rcx
0x18003b586  push    rbp
0x18003b587  push    rsi
0x18003b588  push    rdi
0x18003b589  mov     rbp, rsp
0x18003b58c  sub     rsp, 50h
0x18003b590  mov     rsi, rdx
0x18003b593  mov     rdi, rcx
0x18003b596  mov     [rbp+var_20], 0
0x18003b59d  mov     qword ptr [rcx], 0
0x18003b5a4  mov     [rbp+var_20], 1
0x18003b5ab  mov     [rbp+SecurityDescriptor], 0
0x18003b5b3  xor     r9d, r9d; SecurityDescriptorSize
0x18003b5b6  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18003b5ba  lea     edx, [r9+1]; StringSDRevision
0x18003b5be  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)(A;;0x001F0003;;;WD)(A;;0"...
0x18003b5c5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003b5cb  mov     rcx, [rbp+18h]; this
0x18003b5cf  test    eax, eax
0x18003b5d1  jnz     short loc_18003B5E3
0x18003b5d3  lea     r8, aOnecoreuapWind_120; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b5da  lea     edx, [rax+26h]; void *
0x18003b5dd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003b5e3  mov     [rbp+arg_10], 0
0x18003b5eb  mov     rax, [rsi]
0x18003b5ee  mov     rbx, [rax+40h]
0x18003b5f2  lea     rcx, [rbp+arg_10]
0x18003b5f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b5fb  lea     r8, [rbp+arg_10]
0x18003b5ff  mov     rdx, [rbp+SecurityDescriptor]
0x18003b603  mov     rcx, rsi
0x18003b606  mov     rax, rbx
0x18003b609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b60e  mov     rcx, [rbp+18h]; this
0x18003b612  test    eax, eax
0x18003b614  jns     short loc_18003B62B
0x18003b616  mov     r9d, eax; char *
0x18003b619  lea     r8, aOnecoreuapWind_120; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b620  mov     edx, 2Bh ; '+'; void *
0x18003b625  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003b62b  mov     rcx, rdi
0x18003b62e  call    ?InternalRelease@?$ComPtr@VInputSystemInternalServerConnection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<InputSystemInternalServerConnection>::InternalRelease(void)
0x18003b633  mov     [rbp+var_10], 0
0x18003b63b  mov     [rbp+var_8], 1
0x18003b642  mov     eax, [rbp+var_4]
0x18003b645  mov     [rbp+var_4], eax
0x18003b648  mov     qword ptr [rsp+50h+var_30], rdi; int
0x18003b64d  lea     r8, [rbp+var_10]
0x18003b651  mov     rdx, [rbp+arg_10]
0x18003b655  mov     rcx, rsi
0x18003b658  call    ??$CreateServer@VInputSystemServerConnection@@@BaseBamoConnection@Bamo@Microsoft@@SAJPEAUIMessageSession@@PEAUIMessagePort@@UMsgScopeID@@PEBGPEAPEAVInputSystemServerConnection@@@Z; Microsoft::Bamo::BaseBamoConnection::CreateServer<InputSystemServerConnection>(IMessageSession *,IMessagePort *,MsgScopeID,ushort const *,InputSystemServerConnection * *)
0x18003b65d  mov     rcx, [rbp+18h]; this
0x18003b661  test    eax, eax
0x18003b663  jns     short loc_18003B67A
0x18003b665  mov     r9d, eax; char *
0x18003b668  lea     r8, aOnecoreuapWind_120; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b66f  mov     edx, 32h ; '2'; void *
0x18003b674  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003b67a  mov     rbx, [rdi]
0x18003b67d  mov     ecx, 0B8h; Size
0x18003b682  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003b687  mov     [rbp+var_10], rax
0x18003b68b  mov     rdx, [rdi]; struct ISMBamos_AutoBamos::BamoConnection *
0x18003b68e  mov     rcx, rax; this
0x18003b691  call    ??0InputSystem@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@@Z; InputSystem::InputSystem(ISMBamos_AutoBamos::BamoConnection *)
0x18003b696  mov     rsi, rax
0x18003b699  mov     rcx, [rbx+0F8h]
0x18003b6a0  test    rcx, rcx
0x18003b6a3  jz      short loc_18003B6B1
0x18003b6a5  mov     rdx, [rcx]
0x18003b6a8  mov     rax, [rdx+8]
0x18003b6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6b1  mov     [rbx+0F8h], rsi
0x18003b6b8  mov     rcx, [rbp+arg_10]
0x18003b6bc  test    rcx, rcx
0x18003b6bf  jz      short loc_18003B6D6
0x18003b6c1  mov     [rbp+arg_10], 0
0x18003b6c9  mov     rax, [rcx]
0x18003b6cc  mov     rax, [rax+10h]
0x18003b6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6d5  nop
0x18003b6d6  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18003b6da  test    rcx, rcx
0x18003b6dd  jz      short loc_18003B6E5
0x18003b6df  call    cs:__imp_LocalFree
0x18003b6e5  mov     rax, rdi
0x18003b6e8  mov     rbx, [rsp+50h+arg_8]
0x18003b6ed  add     rsp, 50h
0x18003b6f1  pop     rdi
0x18003b6f2  pop     rsi
0x18003b6f3  pop     rbp
0x18003b6f4  retn
```
