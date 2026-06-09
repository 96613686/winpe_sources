# _Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__

- ea: `0x140029f40`
- end: `0x140029f85`
- name: `_Windows::WCP::Implementation::Rtl::GetSystemSecurity_::_5_::_dynamic_atexit_destructor_for__g_SystemSecurity__`
- size: `69`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140029f40`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140029f64`
- `ntdll!RtlFreeHeap` at `0x140029f64`

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
0x140029f40  sub     rsp, 28h
0x140029f44  cmp     qword ptr cs:P, 0
0x140029f4c  jz      short loc_140029F80
0x140029f4e  mov     rcx, gs:60h
0x140029f57  xor     edx, edx; Flags
0x140029f59  mov     r8, qword ptr cs:P; P
0x140029f60  mov     rcx, [rcx+30h]; HeapHandle
0x140029f64  call    cs:__imp_RtlFreeHeap
0x140029f6a  mov     qword ptr cs:P, 0
0x140029f75  mov     qword ptr cs:P+8, 0
0x140029f80  add     rsp, 28h
0x140029f84  retn
```
