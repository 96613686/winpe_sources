# _DataStoreComServer::GetAttributeDictionary_::_1_::catch$1

- ea: `0x18000e2e4`
- end: `0x18000e35a`
- name: `_DataStoreComServer::GetAttributeDictionary_::_1_::catch$1`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007150`
- `0x18000d990`
- `0x18000e2e4`

## string_xrefs

- `0x18000e310`: `Error in DataStoreComServer::GetAttributeDictionary() - Caught COM exception...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::GetAttributeDictionary_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::GetAttributeDictionary() - Caught COM exception...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
  }
  *(_DWORD *)(a2 + 96) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x18000e2e4  mov     [rsp+arg_8], rdx
0x18000e2e9  push    rbp
0x18000e2ea  sub     rsp, 20h
0x18000e2ee  mov     rbp, rdx
0x18000e2f1  lea     rcx, WPP_GLOBAL_Control
0x18000e2f8  mov     rax, cs:WPP_GLOBAL_Control
0x18000e2ff  cmp     rax, rcx
0x18000e302  jz      short loc_18000E33F
0x18000e304  cmp     byte ptr [rax+19h], 2
0x18000e308  jb      short loc_18000E33F
0x18000e30a  test    byte ptr [rax+1Ch], 10h
0x18000e30e  jz      short loc_18000E33F
0x18000e310  lea     rcx, aErrorInDatasto_3; "Error in DataStoreComServer::GetAttribu"...
0x18000e317  call    WppDbgPrint
0x18000e31c  mov     edx, 0Dh
0x18000e321  lea     r9, aNpsds; "NPSDS"
0x18000e328  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e32f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e336  mov     rcx, [rcx+10h]
0x18000e33a  call    WPP_SF_s
0x18000e33f  mov     rax, [rbp+20h]
0x18000e343  mov     ecx, [rax+8]
0x18000e346  mov     [rbp+60h], ecx
0x18000e349  mov     rax, 0
0x18000e353  add     rsp, 20h
0x18000e357  pop     rbp
0x18000e358  retn
```
