# RegistryVerb::RuntimeClassInitialize(ushort const *,HKEY__ *)

- ea: `0x1800c2e3c`
- end: `0x1800c2f6d`
- name: `?RuntimeClassInitialize@RegistryVerb@@QEAAJPEBGPEAUHKEY__@@@Z`
- size: `305`
- prototype: `HRESULT __fastcall(RegistryVerb *this, const wchar_t *id, HKEY__ *verbsKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c05e4`

## callees

- `0x1800185ec`
- `0x180051168`
- `0x180055f30`
- `0x1800560c4`
- `0x1800c0a60`
- `0x1800c240c`
- `0x1800c2e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800c2e5a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x1800c2e5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ef4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2f15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2f58`

## string_xrefs

- `0x1800c2e7d`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`
- `0x1800c2edb`: `com\ole32\oleregistrationenumeration\oleregistrationenumeration.cpp`

## pseudocode

```c
__int64 __fastcall RegistryVerb::RuntimeClassInitialize(RegistryVerb *this, const wchar_t *id, HKEY__ *verbsKey)
{
  unsigned int v6; // r8d
  HRESULT v7; // eax
  HRESULT StringValue; // ebx
  unsigned int v10; // edx
  HSTRING__ *m_ptr; // rdi
  HSTRING__ *v12; // rcx
  void *retaddr; // [rsp+48h] [rbp+0h]
  wil::last_error_context dwFlags; // [rsp+50h] [rbp+8h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > defaultValueOfVerbKey; // [rsp+68h] [rbp+20h] BYREF

  this->m_id = wcstol(id, 0, 10);
  v7 = RegistryKey::StaticOpen(verbsKey, id, v6, (HKEY__ **)&this->m_verbKey._hkey);
  StringValue = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x414u,
      "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
      v7);
    return (unsigned int)StringValue;
  }
  defaultValueOfVerbKey.m_ptr = 0;
  dwFlags.m_dismissed = 0;
  StringValue = RegistryKey::ReadStringValueWorker<0,HSTRING__ *>(
                  &this->m_verbKey,
                  &value,
                  2u,
                  &defaultValueOfVerbKey.m_ptr,
                  (bool *)&dwFlags);
  if ( StringValue < 0 )
  {
    v10 = 1047;
    goto LABEL_6;
  }
  m_ptr = this->m_name.m_ptr;
  if ( m_ptr )
  {
    wil::last_error_context::last_error_context(&dwFlags);
    WindowsDeleteString(m_ptr);
    wil::last_error_context::~last_error_context(&dwFlags);
  }
  v12 = defaultValueOfVerbKey.m_ptr;
  this->m_name.m_ptr = 0;
  StringValue = ParseVerbValue(v12, &this->m_name.m_ptr, &this->m_flags, &this->m_attributes);
  if ( StringValue < 0 )
  {
    v10 = 1048;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "com\\ole32\\oleregistrationenumeration\\oleregistrationenumeration.cpp",
      StringValue);
    if ( defaultValueOfVerbKey.m_ptr )
      WindowsDeleteString(defaultValueOfVerbKey.m_ptr);
    return (unsigned int)StringValue;
  }
  if ( defaultValueOfVerbKey.m_ptr )
    WindowsDeleteString(defaultValueOfVerbKey.m_ptr);
  return 0;
}

```

## disassembly

```asm
0x1800c2e3c  mov     [rsp+arg_8], rbx
0x1800c2e41  push    rbp
0x1800c2e42  push    rsi
0x1800c2e43  push    rdi
0x1800c2e44  sub     rsp, 30h
0x1800c2e48  mov     rbx, id
0x1800c2e4b  mov     rdi, verbsKey
0x1800c2e4e  xor     edx, edx; EndPtr
0x1800c2e50  mov     rsi, this
0x1800c2e53  mov     this, rbx; String
0x1800c2e56  lea     r8d, [id+0Ah]; Radix
0x1800c2e5a  call    cs:__imp_wcstol
0x1800c2e60  lea     r9, [rsi+18h]; hkeyAncestor
0x1800c2e64  mov     id, rbx; pszSubKeyPath
0x1800c2e67  mov     this, rdi; hkeyAncestor
0x1800c2e6a  mov     [rsi+10h], eax
0x1800c2e6d  call    ?StaticOpen@RegistryKey@@CAJPEAUHKEY__@@PEBGKPEAPEAU2@@Z; RegistryKey::StaticOpen(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x1800c2e72  mov     ebx, eax
0x1800c2e74  test    eax, eax
0x1800c2e76  jns     short loc_1800C2E98
0x1800c2e78  mov     this, [rsp+48h]; callerReturnAddress
0x1800c2e7d  lea     verbsKey, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c2e84  mov     r9d, eax; hr
0x1800c2e87  mov     edx, 414h; lineNumber
0x1800c2e8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2e91  mov     eax, ebx
0x1800c2e93  jmp     loc_1800C2F60
0x1800c2e98  lea     rax, [rsp+48h+arg_0]
0x1800c2e9d  mov     [rsp+48h+defaultValueOfVerbKey.m_ptr], 0
0x1800c2ea6  lea     r9, [rsp+48h+defaultValueOfVerbKey]; valueName
0x1800c2eab  mov     [rsp+48h+dwFlags], rax; dwFlags
0x1800c2eb0  mov     r8d, 2; isExpandable
0x1800c2eb6  mov     [rsp+48h+arg_0.m_dismissed], 0
0x1800c2ebb  lea     id, value; value
0x1800c2ec2  lea     this, [rsi+18h]; this
0x1800c2ec6  call    ??$ReadStringValueWorker@$0A@PEAUHSTRING__@@@RegistryKey@@AEBAJPEBGKPEAPEAUHSTRING__@@PEA_N@Z; RegistryKey::ReadStringValueWorker<0,HSTRING__ *>(ushort const *,ulong,HSTRING__ * *,bool *)
0x1800c2ecb  mov     ebx, eax
0x1800c2ecd  test    eax, eax
0x1800c2ecf  jns     short loc_1800C2EFC
0x1800c2ed1  mov     edx, 417h; lineNumber
0x1800c2ed6  mov     this, [rsp+48h]; callerReturnAddress
0x1800c2edb  lea     verbsKey, aComOle32Olereg; "com\\ole32\\oleregistrationenumeration"...
0x1800c2ee2  mov     r9d, ebx; hr
0x1800c2ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2eea  mov     this, [rsp+48h+defaultValueOfVerbKey.m_ptr]; string
0x1800c2eef  test    this, this
0x1800c2ef2  jz      short loc_1800C2E91
0x1800c2ef4  call    cs:__imp_WindowsDeleteString
0x1800c2efa  jmp     short loc_1800C2E91
0x1800c2efc  lea     rbx, [rsi+20h]
0x1800c2f00  mov     rdi, [rbx]
0x1800c2f03  test    rdi, rdi
0x1800c2f06  jz      short loc_1800C2F25
0x1800c2f08  lea     this, [rsp+48h+arg_0]; this
0x1800c2f0d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800c2f12  mov     this, rdi; string
0x1800c2f15  call    cs:__imp_WindowsDeleteString
0x1800c2f1b  lea     this, [rsp+48h+arg_0]; this
0x1800c2f20  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800c2f25  mov     this, [rsp+48h+defaultValueOfVerbKey.m_ptr]; value
0x1800c2f2a  lea     r9, [rsi+2Ch]; attributes
0x1800c2f2e  lea     verbsKey, [rsi+28h]; flags
0x1800c2f32  mov     qword ptr [rbx], 0
0x1800c2f39  mov     id, rbx; name
0x1800c2f3c  call    ?ParseVerbValue@@YAJPEAUHSTRING__@@PEAPEAU1@PEAK2@Z; ParseVerbValue(HSTRING__ *,HSTRING__ * *,ulong *,ulong *)
0x1800c2f41  mov     ebx, eax
0x1800c2f43  test    eax, eax
0x1800c2f45  jns     short loc_1800C2F4E
0x1800c2f47  mov     edx, 418h
0x1800c2f4c  jmp     short loc_1800C2ED6
0x1800c2f4e  mov     this, [rsp+48h+defaultValueOfVerbKey.m_ptr]; string
0x1800c2f53  test    this, this
0x1800c2f56  jz      short loc_1800C2F5E
0x1800c2f58  call    cs:__imp_WindowsDeleteString
0x1800c2f5e  xor     eax, eax
0x1800c2f60  mov     rbx, [rsp+48h+arg_8]
0x1800c2f65  add     rsp, 30h
0x1800c2f69  pop     rdi
0x1800c2f6a  pop     rsi
0x1800c2f6b  pop     rbp
0x1800c2f6c  retn
```
