# Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource::InitializeDataGathering(IStream * *)

- ea: `0x180115700`
- end: `0x1801157d1`
- name: `?InitializeDataGathering@MultivariantDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `209`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180113860`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x180115700`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x18011572b`
- `XmlLite!CreateXmlWriter` at `0x18011572b`

## string_xrefs

- `0x180115747`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\multivariantdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource::InitializeDataGathering(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::MultivariantDiagDataSource *this,
        struct IStream **a2)
{
  void **v2; // rdi
  HRESULT XmlWriter; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void **)((char *)this + 8);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease((char *)this + 8);
  XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 182;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\multivariantdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v7);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, *a2);
  if ( XmlWriter < 0 )
  {
    v5 = 183;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v2 + 40LL))(*v2, 1, 1);
  if ( XmlWriter < 0 )
  {
    v5 = 184;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 208LL))(*v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 185;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180115700  mov     [rsp+arg_0], rbx
0x180115705  mov     [rsp+arg_8], rsi
0x18011570a  push    rdi; int
0x18011570b  sub     rsp, 20h
0x18011570f  lea     rdi, [rcx+8]
0x180115713  mov     rsi, rdx
0x180115716  mov     rcx, rdi
0x180115719  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011571e  xor     r8d, r8d; pMalloc
0x180115721  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180115728  mov     rdx, rdi; ppvObject
0x18011572b  call    cs:__imp_CreateXmlWriter
0x180115732  nop     dword ptr [rax+rax+00h]
0x180115737  mov     ebx, eax
0x180115739  test    eax, eax
0x18011573b  jns     short loc_18011575A
0x18011573d  mov     edx, 0B6h; void *
0x180115742  mov     rcx, [rsp+28h]; this
0x180115747  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011574e  mov     r9d, ebx; char *
0x180115751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180115756  mov     eax, ebx
0x180115758  jmp     short loc_1801157C0
0x18011575a  mov     rcx, [rdi]
0x18011575d  mov     rdx, [rsi]
0x180115760  mov     rax, [rcx]
0x180115763  mov     rax, [rax+18h]
0x180115767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011576c  mov     ebx, eax
0x18011576e  test    eax, eax
0x180115770  jns     short loc_180115779
0x180115772  mov     edx, 0B7h
0x180115777  jmp     short loc_180115742
0x180115779  mov     rcx, [rdi]
0x18011577c  mov     edx, 1
0x180115781  mov     r8d, edx
0x180115784  mov     rax, [rcx]
0x180115787  mov     rax, [rax+28h]
0x18011578b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180115790  mov     ebx, eax
0x180115792  test    eax, eax
0x180115794  jns     short loc_18011579D
0x180115796  mov     edx, 0B8h
0x18011579b  jmp     short loc_180115742
0x18011579d  mov     rcx, [rdi]
0x1801157a0  xor     edx, edx
0x1801157a2  mov     rax, [rcx]
0x1801157a5  mov     rax, [rax+0D0h]
0x1801157ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801157b1  mov     ebx, eax
0x1801157b3  test    eax, eax
0x1801157b5  jns     short loc_1801157BE
0x1801157b7  mov     edx, 0B9h
0x1801157bc  jmp     short loc_180115742
0x1801157be  xor     eax, eax
0x1801157c0  mov     rbx, [rsp+28h+arg_0]
0x1801157c5  mov     rsi, [rsp+28h+arg_8]
0x1801157ca  add     rsp, 20h
0x1801157ce  pop     rdi
0x1801157cf  retn
```
