# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(ushort const *,ulong *)

- ea: `0x18012ac74`
- end: `0x18012ad52`
- name: `?GetEnrollmentType@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGPEAK@Z`
- size: `222`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012b39c`
- `0x18012e790`
- `0x18012f3b4`

## callees

- `0x1800e7de8`
- `0x180105294`
- `0x18012a388`
- `0x18012ac74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012acc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012acc2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ad06`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18012ad06`

## string_xrefs

- `0x18012ad25`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentType(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  const WCHAR *v5; // rax
  unsigned int ValueW; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  v13 = HIDWORD(this);
  *a3 = 63;
  pcbData = 4;
  hkey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath();
  ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x20019u, &hkey);
  if ( ValueW )
  {
    v7 = 193;
  }
  else
  {
    ValueW = RegGetValueW(hkey, a2, L"EnrollmentType", 0x10u, 0, a3, &pcbData);
    if ( ValueW == 2 || !ValueW )
    {
      v8 = 0;
      goto LABEL_8;
    }
    v7 = 206;
  }
  v8 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v7,
         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
         (const char *)ValueW,
         phkResult);
LABEL_8:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v8;
}

```

## disassembly

```asm
0x18012ac74  mov     rax, rsp
0x18012ac77  mov     [rax+10h], rbx
0x18012ac7b  mov     [rax+8], rcx
0x18012ac7f  push    rdi
0x18012ac80  sub     rsp, 40h
0x18012ac84  mov     rbx, r8
0x18012ac87  mov     dword ptr [r8], 3Fh ; '?'
0x18012ac8e  mov     rdi, rdx
0x18012ac91  mov     dword ptr [rax+8], 4
0x18012ac98  mov     qword ptr [rax+18h], 0
0x18012aca0  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x18012aca5  lea     rcx, [rsp+48h+hkey]
0x18012acaa  mov     r9d, 20019h; samDesired
0x18012acb0  mov     [rsp+48h+phkResult], rcx; phkResult
0x18012acb5  xor     r8d, r8d; ulOptions
0x18012acb8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18012acbf  mov     rdx, rax; lpSubKey
0x18012acc2  call    cs:__imp_RegOpenKeyExW
0x18012acc9  nop     dword ptr [rax+rax+00h]
0x18012acce  test    eax, eax
0x18012acd0  jz      short loc_18012ACD9
0x18012acd2  mov     edx, 0C1h
0x18012acd7  jmp     short loc_18012AD20
0x18012acd9  mov     rcx, [rsp+48h+hkey]; hkey
0x18012acde  lea     rax, [rsp+48h+arg_0]
0x18012ace3  mov     [rsp+48h+pcbData], rax; pcbData
0x18012ace8  lea     r8, aEnrollmenttype; "EnrollmentType"
0x18012acef  mov     [rsp+48h+pvData], rbx; pvData
0x18012acf4  mov     r9d, 10h; dwFlags
0x18012acfa  mov     rdx, rdi; lpSubKey
0x18012acfd  mov     [rsp+48h+phkResult], 0; unsigned int
0x18012ad06  call    cs:__imp_RegGetValueW
0x18012ad0d  nop     dword ptr [rax+rax+00h]
0x18012ad12  cmp     eax, 2
0x18012ad15  jz      short loc_18012AD38
0x18012ad17  test    eax, eax
0x18012ad19  jz      short loc_18012AD38
0x18012ad1b  mov     edx, 0CEh; void *
0x18012ad20  mov     rcx, [rsp+48h]; this
0x18012ad25  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012ad2c  mov     r9d, eax; char *
0x18012ad2f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18012ad34  mov     ebx, eax
0x18012ad36  jmp     short loc_18012AD3A
0x18012ad38  xor     ebx, ebx
0x18012ad3a  lea     rcx, [rsp+48h+hkey]
0x18012ad3f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18012ad44  mov     eax, ebx
0x18012ad46  mov     rbx, [rsp+48h+arg_8]
0x18012ad4b  add     rsp, 40h
0x18012ad4f  pop     rdi
0x18012ad50  retn
```
