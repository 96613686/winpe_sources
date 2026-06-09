# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::InitiatializeDataGathering(IStream * *)

- ea: `0x1801193d8`
- end: `0x1801194a9`
- name: `?InitiatializeDataGathering@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEAPEAUIStream@@@Z`
- size: `209`
- prototype: `int(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *__hidden this, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801184c0`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1801193d8`
- `0x180193010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180119403`
- `XmlLite!CreateXmlWriter` at `0x180119403`

## string_xrefs

- `0x18011941f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`

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
0x1801193d8  mov     [rsp+arg_0], rbx
0x1801193dd  mov     [rsp+arg_8], rsi
0x1801193e2  push    rdi; int
0x1801193e3  sub     rsp, 20h
0x1801193e7  lea     rdi, [rcx+8]
0x1801193eb  mov     rsi, rdx
0x1801193ee  mov     rcx, rdi
0x1801193f1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801193f6  xor     r8d, r8d; pMalloc
0x1801193f9  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180119400  mov     rdx, rdi; ppvObject
0x180119403  call    cs:__imp_CreateXmlWriter
0x18011940a  nop     dword ptr [rax+rax+00h]
0x18011940f  mov     ebx, eax
0x180119411  test    eax, eax
0x180119413  jns     short loc_180119432
0x180119415  mov     edx, 67h ; 'g'; void *
0x18011941a  mov     rcx, [rsp+28h]; this
0x18011941f  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180119426  mov     r9d, ebx; char *
0x180119429  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011942e  mov     eax, ebx
0x180119430  jmp     short loc_180119498
0x180119432  mov     rcx, [rdi]
0x180119435  mov     rdx, [rsi]
0x180119438  mov     rax, [rcx]
0x18011943b  mov     rax, [rax+18h]
0x18011943f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119444  mov     ebx, eax
0x180119446  test    eax, eax
0x180119448  jns     short loc_180119451
0x18011944a  mov     edx, 68h ; 'h'
0x18011944f  jmp     short loc_18011941A
0x180119451  mov     rcx, [rdi]
0x180119454  mov     edx, 1
0x180119459  mov     r8d, edx
0x18011945c  mov     rax, [rcx]
0x18011945f  mov     rax, [rax+28h]
0x180119463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119468  mov     ebx, eax
0x18011946a  test    eax, eax
0x18011946c  jns     short loc_180119475
0x18011946e  mov     edx, 69h ; 'i'
0x180119473  jmp     short loc_18011941A
0x180119475  mov     rcx, [rdi]
0x180119478  xor     edx, edx
0x18011947a  mov     rax, [rcx]
0x18011947d  mov     rax, [rax+0D0h]
0x180119484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180119489  mov     ebx, eax
0x18011948b  test    eax, eax
0x18011948d  jns     short loc_180119496
0x18011948f  mov     edx, 6Ah ; 'j'
0x180119494  jmp     short loc_18011941A
0x180119496  xor     eax, eax
0x180119498  mov     rbx, [rsp+28h+arg_0]
0x18011949d  mov     rsi, [rsp+28h+arg_8]
0x1801194a2  add     rsp, 20h
0x1801194a6  pop     rdi
0x1801194a7  retn
```
