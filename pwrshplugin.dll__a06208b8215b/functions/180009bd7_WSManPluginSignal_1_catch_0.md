# _WSManPluginSignal_::_1_::catch$0

- ea: `0x180009bd7`
- end: `0x180009c37`
- name: `_WSManPluginSignal_::_1_::catch$0`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040d0`
- `0x180009bd7`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009c12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009c12`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c01`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c01`

## pseudocode

```c
__int64 __fastcall WSManPluginSignal_::_1_::catch_0(__int64 a1, __int64 a2)
{
  DWORD v3; // edi
  void *v4; // rbx

  v3 = -2141977623;
  v4 = *(void **)(a2 + 48);
  if ( v4 )
  {
    v3 = *(_DWORD *)v4;
    if ( *((_QWORD *)v4 + 1) )
    {
      operator delete[](*((void **)v4 + 1));
      *((_QWORD *)v4 + 1) = 0;
    }
    operator delete(v4);
  }
  ReportOperationComplete(*(WSMAN_PLUGIN_REQUEST **)(a2 + 112), v3);
  return 0;
}

```

## disassembly

```asm
0x180009bd7  mov     [rsp+arg_8], rdx
0x180009bdc  push    rbx
0x180009bdd  push    rbp
0x180009bde  push    rdi
0x180009bdf  sub     rsp, 30h
0x180009be3  mov     rbp, rdx
0x180009be6  mov     edi, 805403E9h
0x180009beb  mov     rbx, [rbp+30h]
0x180009bef  test    rbx, rbx
0x180009bf2  jz      short loc_180009C18
0x180009bf4  mov     edi, [rbx]
0x180009bf6  cmp     qword ptr [rbx+8], 0
0x180009bfb  jz      short loc_180009C0F
0x180009bfd  mov     rcx, [rbx+8]
0x180009c01  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009c07  mov     qword ptr [rbx+8], 0
0x180009c0f  mov     rcx, rbx
0x180009c12  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009c18  mov     edx, edi; errorCode
0x180009c1a  mov     rcx, [rbp+70h]; requestDetails
0x180009c1e  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180009c23  nop
0x180009c24  mov     rax, 0
0x180009c2e  add     rsp, 30h
0x180009c32  pop     rdi
0x180009c33  pop     rbp
0x180009c34  pop     rbx
0x180009c35  retn
```
