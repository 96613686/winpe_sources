# Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Ic3::CIc3Processor,>::OpenPropertyStore(IPropertyStore * *)

- ea: `0x180044670`
- end: `0x18004470e`
- name: `?OpenPropertyStore@?$CMonitorContextBase@VCIc3Processor@Ic3@Avenc@Rdp@@$$V@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e848`
- `0x18000ec04`
- `0x180044670`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800446a2`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800446a2`

## string_xrefs

- `0x1800446ad`: `Failed to create property store`
- `0x1800446bc`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/MonitorContextBase.h`
- `0x1800446f8`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/MonitorContextBase.h`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Ic3::CIc3Processor,>::OpenPropertyStore(
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
      (void *)0x92,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/MonitorContextBase.h",
      (const char *)0x80004003LL,
      v7);
  v3 = (__int64 *)(a1 + 16);
  if ( !*(_QWORD *)(a1 + 16) )
  {
    *v3 = 0;
    v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)(a1 + 16));
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/MonitorContextBase.h",
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
0x180044670  mov     [rsp+arg_0], rbx
0x180044675  push    rdi
0x180044676  sub     rsp, 30h
0x18004467a  mov     rdi, rdx
0x18004467d  mov     rax, [rsp+38h]
0x180044682  test    rdx, rdx
0x180044685  jz      short loc_1800446F2
0x180044687  lea     rbx, [rcx+10h]
0x18004468b  cmp     qword ptr [rbx], 0
0x18004468f  jnz     short loc_1800446CD
0x180044691  mov     qword ptr [rbx], 0
0x180044698  mov     rdx, rbx; ppv
0x18004469b  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800446a2  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800446a8  mov     rcx, [rsp+38h]; this
0x1800446ad  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x1800446b4  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800446b9  mov     r9d, eax; char *
0x1800446bc  lea     r8, aOnecoreuapTerm_27; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800446c3  mov     edx, 9Dh; void *
0x1800446c8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800446cd  mov     rcx, [rbx]
0x1800446d0  mov     [rdi], rcx
0x1800446d3  mov     rax, [rcx]
0x1800446d6  mov     rax, [rax+8]
0x1800446da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446df  xor     eax, eax
0x1800446e1  jmp     short loc_1800446E7
0x1800446e3  mov     eax, [rsp+38h+arg_8]
0x1800446e7  mov     rbx, [rsp+38h+arg_0]
0x1800446ec  add     rsp, 30h
0x1800446f0  pop     rdi
0x1800446f1  retn
0x1800446f2  mov     r9d, 80004003h; char *
0x1800446f8  lea     r8, aOnecoreuapTerm_27; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800446ff  mov     edx, 92h; void *
0x180044704  mov     rcx, rax; this
0x180044707  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
