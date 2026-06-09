# Rdp::Stack::Graphics::CMonitorConfigChannel::Stop(void)

- ea: `0x18001682c`
- end: `0x18001686f`
- name: `?Stop@CMonitorConfigChannel@Graphics@Stack@Rdp@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000cbc0`

## callees

- `0x18000cf28`
- `0x18001682c`
- `0x18002a010`

## string_xrefs

- `0x180016856`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x18001684a`: `Failed to close monitor config Dvc`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::Stop(Rdp::Stack::Graphics::CMonitorConfigChannel *this)
{
  __int64 v1; // rcx
  unsigned int v2; // eax
  const char *v3; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = *((_QWORD *)this + 14);
  if ( v1 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 32LL))(v1);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)v2,
      (int)"Failed to close monitor config Dvc",
      v3);
  }
}

```

## disassembly

```asm
0x18001682c  sub     rsp, 38h
0x180016830  mov     rcx, [rcx+70h]
0x180016834  test    rcx, rcx
0x180016837  jz      short loc_18001686A
0x180016839  mov     rax, [rcx]
0x18001683c  mov     rax, [rax+20h]
0x180016840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016845  mov     rcx, [rsp+38h]; this
0x18001684a  lea     rdx, aFailedToCloseM; "Failed to close monitor config Dvc"
0x180016851  mov     qword ptr [rsp+38h+var_18], rdx; int
0x180016856  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001685d  mov     edx, 58h ; 'X'; void *
0x180016862  mov     r9d, eax; char *
0x180016865  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001686a  add     rsp, 38h
0x18001686e  retn
```
