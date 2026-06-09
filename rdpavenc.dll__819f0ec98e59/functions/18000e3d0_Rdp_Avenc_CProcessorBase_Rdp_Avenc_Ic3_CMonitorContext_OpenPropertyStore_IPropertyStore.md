# Rdp::Avenc::CProcessorBase<Rdp::Avenc::Ic3::CMonitorContext,>::OpenPropertyStore(IPropertyStore * *)

- ea: `0x18000e3d0`
- end: `0x18000e46e`
- name: `?OpenPropertyStore@?$CProcessorBase@VCMonitorContext@Ic3@Avenc@Rdp@@$$V@Avenc@Rdp@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e3d0`
- `0x18000e848`
- `0x18000ec04`
- `0x180089010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e402`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000e402`

## string_xrefs

- `0x18000e40d`: `Failed to create property store`
- `0x18000e41c`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18000e458`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::CProcessorBase<Rdp::Avenc::Ic3::CMonitorContext,>::OpenPropertyStore(
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
  v3 = (__int64 *)(a1 + 8);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *v3 = 0;
    v4 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)(a1 + 8));
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
0x18000e3d0  mov     [rsp+arg_0], rbx
0x18000e3d5  push    rdi
0x18000e3d6  sub     rsp, 30h
0x18000e3da  mov     rdi, rdx
0x18000e3dd  mov     rax, [rsp+38h]
0x18000e3e2  test    rdx, rdx
0x18000e3e5  jz      short loc_18000E452
0x18000e3e7  lea     rbx, [rcx+8]
0x18000e3eb  cmp     qword ptr [rbx], 0
0x18000e3ef  jnz     short loc_18000E42D
0x18000e3f1  mov     qword ptr [rbx], 0
0x18000e3f8  mov     rdx, rbx; ppv
0x18000e3fb  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000e402  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000e408  mov     rcx, [rsp+38h]; this
0x18000e40d  lea     rdx, aFailedToCreate_10; "Failed to create property store"
0x18000e414  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000e419  mov     r9d, eax; char *
0x18000e41c  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e423  mov     edx, 0A4h; void *
0x18000e428  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000e42d  mov     rcx, [rbx]
0x18000e430  mov     [rdi], rcx
0x18000e433  mov     rax, [rcx]
0x18000e436  mov     rax, [rax+8]
0x18000e43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43f  xor     eax, eax
0x18000e441  jmp     short loc_18000E447
0x18000e443  mov     eax, [rsp+38h+arg_8]
0x18000e447  mov     rbx, [rsp+38h+arg_0]
0x18000e44c  add     rsp, 30h
0x18000e450  pop     rdi
0x18000e451  retn
0x18000e452  mov     r9d, 80004003h; char *
0x18000e458  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18000e45f  mov     edx, 99h; void *
0x18000e464  mov     rcx, rax; this
0x18000e467  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
