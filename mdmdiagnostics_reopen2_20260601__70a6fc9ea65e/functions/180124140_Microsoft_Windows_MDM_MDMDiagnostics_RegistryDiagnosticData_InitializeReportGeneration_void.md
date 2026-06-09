# Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData::InitializeReportGeneration(void)

- ea: `0x180124140`
- end: `0x180124228`
- name: `?InitializeReportGeneration@RegistryDiagnosticData@MDMDiagnostics@MDM@Windows@Microsoft@@UEAAJXZ`
- size: `232`
- prototype: `int(Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180124140`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18012416b`
- `XmlLite!CreateXmlWriter` at `0x18012416b`

## string_xrefs

- `0x180124187`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\registrydiagnosticdata.cpp`
- `0x1801241fd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\registrytoxml\registrydiagnosticdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData::InitializeReportGeneration(
        Microsoft::Windows::MDM::MDMDiagnostics::RegistryDiagnosticData *this)
{
  void **v1; // rbx
  HRESULT XmlWriter; // edi
  __int64 v4; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void **)((char *)this + 48);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 48);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, v1, 0);
  if ( XmlWriter < 0 )
  {
    v4 = 55;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\registrydiagnosticdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v8);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v1 + 24LL))(*v1, *((_QWORD *)this + 5));
  if ( XmlWriter < 0 )
  {
    v4 = 56;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v1 + 40LL))(*v1, 1, 1);
  if ( XmlWriter < 0 )
  {
    v4 = 57;
    goto LABEL_3;
  }
  v6 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v1 + 208LL))(*v1, 0);
  v7 = v6;
  if ( v6 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\registrytoxml\\registrydiagnosticdata.cpp",
    (const char *)(unsigned int)v6,
    v8);
  return v7;
}

```

## disassembly

```asm
0x180124140  mov     [rsp+arg_0], rbx
0x180124145  mov     [rsp+arg_8], rsi
0x18012414a  push    rdi; int
0x18012414b  sub     rsp, 20h
0x18012414f  lea     rbx, [rcx+30h]
0x180124153  mov     rsi, rcx
0x180124156  mov     rcx, rbx
0x180124159  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012415e  xor     r8d, r8d; pMalloc
0x180124161  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180124168  mov     rdx, rbx; ppvObject
0x18012416b  call    cs:__imp_CreateXmlWriter
0x180124172  nop     dword ptr [rax+rax+00h]
0x180124177  mov     edi, eax
0x180124179  test    eax, eax
0x18012417b  jns     short loc_18012419A
0x18012417d  mov     edx, 37h ; '7'; void *
0x180124182  mov     rcx, [rsp+28h]; this
0x180124187  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012418e  mov     r9d, edi; char *
0x180124191  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124196  mov     eax, edi
0x180124198  jmp     short loc_180124217
0x18012419a  mov     rcx, [rbx]
0x18012419d  mov     rdx, [rsi+28h]
0x1801241a1  mov     rax, [rcx]
0x1801241a4  mov     rax, [rax+18h]
0x1801241a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801241ad  mov     edi, eax
0x1801241af  test    eax, eax
0x1801241b1  jns     short loc_1801241BA
0x1801241b3  mov     edx, 38h ; '8'
0x1801241b8  jmp     short loc_180124182
0x1801241ba  mov     rcx, [rbx]
0x1801241bd  mov     edx, 1
0x1801241c2  mov     r8d, edx
0x1801241c5  mov     rax, [rcx]
0x1801241c8  mov     rax, [rax+28h]
0x1801241cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801241d1  mov     edi, eax
0x1801241d3  test    eax, eax
0x1801241d5  jns     short loc_1801241DE
0x1801241d7  mov     edx, 39h ; '9'
0x1801241dc  jmp     short loc_180124182
0x1801241de  mov     rcx, [rbx]
0x1801241e1  xor     edx, edx
0x1801241e3  mov     rax, [rcx]
0x1801241e6  mov     rax, [rax+0D0h]
0x1801241ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801241f2  mov     ebx, eax
0x1801241f4  test    eax, eax
0x1801241f6  jns     short loc_180124215
0x1801241f8  mov     rcx, [rsp+28h]; this
0x1801241fd  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180124204  mov     r9d, eax; char *
0x180124207  mov     edx, 3Ah ; ':'; void *
0x18012420c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180124211  mov     eax, ebx
0x180124213  jmp     short loc_180124217
0x180124215  xor     eax, eax
0x180124217  mov     rbx, [rsp+28h+arg_0]
0x18012421c  mov     rsi, [rsp+28h+arg_8]
0x180124221  add     rsp, 20h
0x180124225  pop     rdi
0x180124226  retn
```
