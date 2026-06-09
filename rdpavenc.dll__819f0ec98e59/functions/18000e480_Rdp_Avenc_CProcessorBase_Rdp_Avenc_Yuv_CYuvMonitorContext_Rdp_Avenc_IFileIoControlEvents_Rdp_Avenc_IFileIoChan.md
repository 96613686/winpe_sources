# Rdp::Avenc::CProcessorBase<Rdp::Avenc::Yuv::CYuvMonitorContext,Rdp::Avenc::IFileIoControlEvents,Rdp::Avenc::IFileIoChannelEvents>::OpenPropertyStore(IPropertyStore * *)

- ea: `0x18000e480`
- end: `0x18000e51e`
- name: `?OpenPropertyStore@?$CProcessorBase@VCYuvMonitorContext@Yuv@Avenc@Rdp@@UIFileIoControlEvents@34@UIFileIoChannelEvents@34@@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e480`
- `0x18000e848`
- `0x18000ec04`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e4b2`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e4b2`

## string_xrefs

- `0x18000e4bd`: `Failed to create property store`
- `0x18000e4cc`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18000e508`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::Yuv::CYuvMonitorContext,Rdp::Avenc::IFileIoControlEvents,Rdp::Avenc::IFileIoChannelEvents>::OpenPropertyStore(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // rcx
  int v7; // [rsp+20h] [rbp-18h]
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)0x80004003LL,
      v7);
  v3 = (__int64 *)(a1 + 24);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    *v3 = 0;
    v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)(a1 + 24));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xA4,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v4,
      (int)"Failed to create property store",
      v8);
  }
  v5 = *v3;
  *a2 = *v3;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x18000e480  mov     [rsp+arg_0], rbx
0x18000e485  push    rdi
0x18000e486  sub     rsp, 30h
0x18000e48a  mov     rdi, rdx
0x18000e48d  mov     rax, [rsp+38h]
0x18000e492  test    rdx, rdx
0x18000e495  jz      short loc_18000E502
0x18000e497  lea     rbx, [rcx+18h]
0x18000e49b  cmp     qword ptr [rbx], 0
0x18000e49f  jnz     short loc_18000E4DD
0x18000e4a1  mov     qword ptr [rbx], 0
0x18000e4a8  mov     rdx, rbx; ppv
0x18000e4ab  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000e4b2  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000e4b8  mov     rcx, [rsp+38h]; this
0x18000e4bd  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x18000e4c4  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000e4c9  mov     r9d, eax; char *
0x18000e4cc  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e4d3  mov     edx, 0A4h; void *
0x18000e4d8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e4dd  mov     rcx, [rbx]
0x18000e4e0  mov     [rdi], rcx
0x18000e4e3  mov     rax, [rcx]
0x18000e4e6  mov     rax, [rax+8]
0x18000e4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ef  xor     eax, eax
0x18000e4f1  jmp     short loc_18000E4F7
0x18000e4f3  mov     eax, [rsp+38h+arg_8]
0x18000e4f7  mov     rbx, [rsp+38h+arg_0]
0x18000e4fc  add     rsp, 30h
0x18000e500  pop     rdi
0x18000e501  retn
0x18000e502  mov     r9d, 80004003h; char *
0x18000e508  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e50f  mov     edx, 99h; void *
0x18000e514  mov     rcx, rax; this
0x18000e517  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
