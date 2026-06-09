# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::InitiatializeDataGathering(IStream * *)

- ea: `0x180117c40`
- end: `0x180117d0a`
- name: `?InitiatializeDataGathering@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `202`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180116dc0`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x180117c40`
- `0x180191010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180117c6b`
- `XmlLite!CreateXmlWriter` at `0x180117c6b`

## string_xrefs

- `0x180117c81`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::InitiatializeDataGathering(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this,
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
    v5 = 103;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
      (const char *)(unsigned int)XmlWriter,
      v7);
    return (unsigned int)XmlWriter;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, *a2);
  if ( XmlWriter < 0 )
  {
    v5 = 104;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)*v2 + 40LL))(*v2, 1, 1);
  if ( XmlWriter < 0 )
  {
    v5 = 105;
    goto LABEL_3;
  }
  XmlWriter = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v2 + 208LL))(*v2, 0);
  if ( XmlWriter < 0 )
  {
    v5 = 106;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180117c40  mov     [rsp+arg_0], rbx
0x180117c45  mov     [rsp+arg_8], rsi
0x180117c4a  push    rdi; int
0x180117c4b  sub     rsp, 20h
0x180117c4f  lea     rdi, [rcx+8]
0x180117c53  mov     rsi, rdx
0x180117c56  mov     rcx, rdi
0x180117c59  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180117c5e  xor     r8d, r8d; pMalloc
0x180117c61  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180117c68  mov     rdx, rdi; ppvObject
0x180117c6b  call    cs:__imp_CreateXmlWriter
0x180117c71  mov     ebx, eax
0x180117c73  test    eax, eax
0x180117c75  jns     short loc_180117C94
0x180117c77  mov     edx, 67h ; 'g'; void *
0x180117c7c  mov     rcx, [rsp+28h]; this
0x180117c81  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180117c88  mov     r9d, ebx; char *
0x180117c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180117c90  mov     eax, ebx
0x180117c92  jmp     short loc_180117CFA
0x180117c94  mov     rcx, [rdi]
0x180117c97  mov     rdx, [rsi]
0x180117c9a  mov     rax, [rcx]
0x180117c9d  mov     rax, [rax+18h]
0x180117ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117ca6  mov     ebx, eax
0x180117ca8  test    eax, eax
0x180117caa  jns     short loc_180117CB3
0x180117cac  mov     edx, 68h ; 'h'
0x180117cb1  jmp     short loc_180117C7C
0x180117cb3  mov     rcx, [rdi]
0x180117cb6  mov     edx, 1
0x180117cbb  mov     r8d, edx
0x180117cbe  mov     rax, [rcx]
0x180117cc1  mov     rax, [rax+28h]
0x180117cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117cca  mov     ebx, eax
0x180117ccc  test    eax, eax
0x180117cce  jns     short loc_180117CD7
0x180117cd0  mov     edx, 69h ; 'i'
0x180117cd5  jmp     short loc_180117C7C
0x180117cd7  mov     rcx, [rdi]
0x180117cda  xor     edx, edx
0x180117cdc  mov     rax, [rcx]
0x180117cdf  mov     rax, [rax+0D0h]
0x180117ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117ceb  mov     ebx, eax
0x180117ced  test    eax, eax
0x180117cef  jns     short loc_180117CF8
0x180117cf1  mov     edx, 6Ah ; 'j'
0x180117cf6  jmp     short loc_180117C7C
0x180117cf8  xor     eax, eax
0x180117cfa  mov     rbx, [rsp+28h+arg_0]
0x180117cff  mov     rsi, [rsp+28h+arg_8]
0x180117d04  add     rsp, 20h
0x180117d08  pop     rdi
0x180117d09  retn
```
