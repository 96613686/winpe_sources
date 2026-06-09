# _WSManPluginShell_::_1_::catch$0

- ea: `0x180009cf8`
- end: `0x180009d64`
- name: `_WSManPluginShell_::_1_::catch$0`
- size: `108`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040d0`
- `0x180009cf8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009d33`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009d33`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d22`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009d22`
- `OLE32!CoUninitialize` at `0x180009d3f`
- `OLE32!CoUninitialize` at `0x180009d3f`

## pseudocode

```c
__int64 __fastcall WSManPluginShell_::_1_::catch_0(__int64 a1, __int64 a2)
{
  DWORD v3; // edi
  void *v4; // rbx

  v3 = 1101;
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
  if ( *(_BYTE *)(a2 + 112) )
    CoUninitialize();
  ReportOperationComplete(*(WSMAN_PLUGIN_REQUEST **)(a2 + 120), v3);
  return 0;
}

```

## disassembly

```asm
0x180009cf8  mov     [rsp+arg_8], rdx
0x180009cfd  push    rbx
0x180009cfe  push    rbp
0x180009cff  push    rdi
0x180009d00  sub     rsp, 30h
0x180009d04  mov     rbp, rdx
0x180009d07  mov     edi, 44Dh
0x180009d0c  mov     rbx, [rbp+30h]
0x180009d10  test    rbx, rbx
0x180009d13  jz      short loc_180009D39
0x180009d15  mov     edi, [rbx]
0x180009d17  cmp     qword ptr [rbx+8], 0
0x180009d1c  jz      short loc_180009D30
0x180009d1e  mov     rcx, [rbx+8]
0x180009d22  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009d28  mov     qword ptr [rbx+8], 0
0x180009d30  mov     rcx, rbx
0x180009d33  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009d39  cmp     byte ptr [rbp+70h], 0
0x180009d3d  jz      short loc_180009D45
0x180009d3f  call    cs:__imp_CoUninitialize
0x180009d45  mov     edx, edi; errorCode
0x180009d47  mov     rcx, [rbp+78h]; requestDetails
0x180009d4b  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180009d50  nop
0x180009d51  mov     rax, 0
0x180009d5b  add     rsp, 30h
0x180009d5f  pop     rdi
0x180009d60  pop     rbp
0x180009d61  pop     rbx
0x180009d62  retn
```
