# NtlmCredIsoInProc::UpdateSharedConfiguration(_NtlmSharedConfiguration *,_NtlmSharedConfiguration *)

- ea: `0x180052c50`
- end: `0x180052c80`
- name: `?UpdateSharedConfiguration@NtlmCredIsoInProc@@UEAAJPEAU_NtlmSharedConfiguration@@0@Z`
- size: `48`
- prototype: `__int64 __fastcall(NtlmCredIsoInProc *__hidden this, struct _NtlmSharedConfiguration *, struct _NtlmSharedConfiguration *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000ed70`

## import_xrefs

- `NtlmShared!MsvpUpdateSharedConfiguration` at `0x180052c5c`
- `NtlmShared!MsvpUpdateSharedConfiguration` at `0x180052c5c`

## string_xrefs

- `0x180052c67`: `NtlmCredIsoInProc::UpdateSharedConfiguration`

## pseudocode

```c
__int64 __fastcall NtlmCredIsoInProc::UpdateSharedConfiguration(
        NtlmCredIsoInProc *this,
        struct _NtlmSharedConfiguration *a2,
        struct _NtlmSharedConfiguration *a3)
{
  unsigned int updated; // ebx

  updated = MsvpUpdateSharedConfiguration(a2, a3);
  NtlmTraceStatusViaWpp_0("NtlmCredIsoInProc::UpdateSharedConfiguration", 490, updated);
  return updated;
}

```

## disassembly

```asm
0x180052c50  push    rbx
0x180052c52  sub     rsp, 20h
0x180052c56  mov     rcx, rdx
0x180052c59  mov     rdx, r8
0x180052c5c  call    cs:__imp_MsvpUpdateSharedConfiguration
0x180052c62  mov     edx, 1EAh
0x180052c67  lea     rcx, aNtlmcredisoinp_11; "NtlmCredIsoInProc::UpdateSharedConfigur"...
0x180052c6e  mov     r8d, eax
0x180052c71  mov     ebx, eax
0x180052c73  call    NtlmTraceStatusViaWpp_0
0x180052c78  mov     eax, ebx
0x180052c7a  add     rsp, 20h
0x180052c7e  pop     rbx
0x180052c7f  retn
```
