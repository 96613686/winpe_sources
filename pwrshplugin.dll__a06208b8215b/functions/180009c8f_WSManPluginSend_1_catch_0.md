# _WSManPluginSend_::_1_::catch$0

- ea: `0x180009c8f`
- end: `0x180009cf2`
- name: `_WSManPluginSend_::_1_::catch$0`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040d0`
- `0x180009c8f`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009cca`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009cca`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009cb9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009cb9`

## pseudocode

```c
__int64 __fastcall WSManPluginSend_::_1_::catch_0(__int64 a1, __int64 a2)
{
  DWORD v3; // edi
  void *v4; // rbx

  v3 = -2141977623;
  v4 = *(void **)(a2 + 64);
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
  ReportOperationComplete(*(WSMAN_PLUGIN_REQUEST **)(a2 + 128), v3);
  return 0;
}

```

## disassembly

```asm
0x180009c8f  mov     [rsp+arg_8], rdx
0x180009c94  push    rbx
0x180009c95  push    rbp
0x180009c96  push    rdi
0x180009c97  sub     rsp, 40h
0x180009c9b  mov     rbp, rdx
0x180009c9e  mov     edi, 805403E9h
0x180009ca3  mov     rbx, [rbp+40h]
0x180009ca7  test    rbx, rbx
0x180009caa  jz      short loc_180009CD0
0x180009cac  mov     edi, [rbx]
0x180009cae  cmp     qword ptr [rbx+8], 0
0x180009cb3  jz      short loc_180009CC7
0x180009cb5  mov     rcx, [rbx+8]
0x180009cb9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009cbf  mov     qword ptr [rbx+8], 0
0x180009cc7  mov     rcx, rbx
0x180009cca  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009cd0  mov     edx, edi; errorCode
0x180009cd2  mov     rcx, [rbp+80h]; requestDetails
0x180009cd9  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180009cde  nop
0x180009cdf  mov     rax, 0
0x180009ce9  add     rsp, 40h
0x180009ced  pop     rdi
0x180009cee  pop     rbp
0x180009cef  pop     rbx
0x180009cf0  retn
```
