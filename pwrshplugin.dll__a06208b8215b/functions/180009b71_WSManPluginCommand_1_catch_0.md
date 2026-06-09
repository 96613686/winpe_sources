# _WSManPluginCommand_::_1_::catch$0

- ea: `0x180009b71`
- end: `0x180009bd1`
- name: `_WSManPluginCommand_::_1_::catch$0`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040d0`
- `0x180009b71`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009bac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bac`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009b9b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009b9b`

## pseudocode

```c
__int64 __fastcall WSManPluginCommand_::_1_::catch_0(__int64 a1, __int64 a2)
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
  ReportOperationComplete(*(WSMAN_PLUGIN_REQUEST **)(a2 + 112), v3);
  return 0;
}

```

## disassembly

```asm
0x180009b71  mov     [rsp+arg_8], rdx
0x180009b76  push    rbx
0x180009b77  push    rbp
0x180009b78  push    rdi
0x180009b79  sub     rsp, 30h
0x180009b7d  mov     rbp, rdx
0x180009b80  mov     edi, 44Dh
0x180009b85  mov     rbx, [rbp+30h]
0x180009b89  test    rbx, rbx
0x180009b8c  jz      short loc_180009BB2
0x180009b8e  mov     edi, [rbx]
0x180009b90  cmp     qword ptr [rbx+8], 0
0x180009b95  jz      short loc_180009BA9
0x180009b97  mov     rcx, [rbx+8]
0x180009b9b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009ba1  mov     qword ptr [rbx+8], 0
0x180009ba9  mov     rcx, rbx
0x180009bac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009bb2  mov     edx, edi; errorCode
0x180009bb4  mov     rcx, [rbp+70h]; requestDetails
0x180009bb8  call    ?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z; ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)
0x180009bbd  nop
0x180009bbe  mov     rax, 0
0x180009bc8  add     rsp, 30h
0x180009bcc  pop     rdi
0x180009bcd  pop     rbp
0x180009bce  pop     rbx
0x180009bcf  retn
```
