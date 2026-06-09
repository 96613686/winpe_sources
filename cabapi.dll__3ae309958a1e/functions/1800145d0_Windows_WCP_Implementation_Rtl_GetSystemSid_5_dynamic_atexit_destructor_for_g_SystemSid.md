# _Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__

- ea: `0x1800145d0`
- end: `0x18001460a`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__`
- size: `58`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800145d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800145f4`
- `ntdll!RtlFreeHeap` at `0x1800145f4`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::GetSystemSid_::_5_::_dynamic_atexit_destructor_for__g_SystemSid__()
{
  if ( Sid )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Sid);
    Sid = 0;
  }
}

```

## disassembly

```asm
0x1800145d0  sub     rsp, 28h
0x1800145d4  cmp     cs:Sid, 0
0x1800145dc  jz      short loc_180014605
0x1800145de  mov     rcx, gs:60h
0x1800145e7  xor     edx, edx; Flags
0x1800145e9  mov     r8, cs:Sid; P
0x1800145f0  mov     rcx, [rcx+30h]; HeapHandle
0x1800145f4  call    cs:__imp_RtlFreeHeap
0x1800145fa  mov     cs:Sid, 0
0x180014605  add     rsp, 28h
0x180014609  retn
```
