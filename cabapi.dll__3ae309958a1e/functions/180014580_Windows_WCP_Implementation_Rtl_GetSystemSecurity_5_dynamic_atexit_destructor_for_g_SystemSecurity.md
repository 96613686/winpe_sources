# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__

- ea: `0x180014580`
- end: `0x1800145c5`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__`
- size: `69`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014580`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800145a4`
- `ntdll!RtlFreeHeap` at `0x1800145a4`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__()
{
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    *(_OWORD *)&P = 0u;
  }
}

```

## disassembly

```asm
0x180014580  sub     rsp, 28h
0x180014584  cmp     qword ptr cs:P, 0
0x18001458c  jz      short loc_1800145C0
0x18001458e  mov     rcx, gs:60h
0x180014597  xor     edx, edx; Flags
0x180014599  mov     r8, qword ptr cs:P; P
0x1800145a0  mov     rcx, [rcx+30h]; HeapHandle
0x1800145a4  call    cs:__imp_RtlFreeHeap
0x1800145aa  mov     qword ptr cs:P, 0
0x1800145b5  mov     qword ptr cs:P+8, 0
0x1800145c0  add     rsp, 28h
0x1800145c4  retn
```
