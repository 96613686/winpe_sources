# _DataStoreComServer::GetAttributeDictionarySchema_::_1_::catch$1

- ea: `0x18000e360`
- end: `0x18000e3d6`
- name: `_DataStoreComServer::GetAttributeDictionarySchema_::_1_::catch$1`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007150`
- `0x18000d990`
- `0x18000e360`

## string_xrefs

- `0x18000e38c`: `Error in DataStoreComServer::GetAttributeDictionarySchema() - Caught COM exception...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::GetAttributeDictionarySchema_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::GetAttributeDictionarySchema() - Caught COM exception...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
  }
  *(_DWORD *)(a2 + 96) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x18000e360  mov     [rsp+arg_8], rdx
0x18000e365  push    rbp
0x18000e366  sub     rsp, 20h
0x18000e36a  mov     rbp, rdx
0x18000e36d  lea     rcx, WPP_GLOBAL_Control
0x18000e374  mov     rax, cs:WPP_GLOBAL_Control
0x18000e37b  cmp     rax, rcx
0x18000e37e  jz      short loc_18000E3BB
0x18000e380  cmp     byte ptr [rax+19h], 2
0x18000e384  jb      short loc_18000E3BB
0x18000e386  test    byte ptr [rax+1Ch], 10h
0x18000e38a  jz      short loc_18000E3BB
0x18000e38c  lea     rcx, aErrorInDatasto_4; "Error in DataStoreComServer::GetAttribu"...
0x18000e393  call    WppDbgPrint
0x18000e398  mov     edx, 0Bh
0x18000e39d  lea     r9, aNpsds; "NPSDS"
0x18000e3a4  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3b2  mov     rcx, [rcx+10h]
0x18000e3b6  call    WPP_SF_s
0x18000e3bb  mov     rax, [rbp+20h]
0x18000e3bf  mov     ecx, [rax+8]
0x18000e3c2  mov     [rbp+60h], ecx
0x18000e3c5  mov     rax, 0
0x18000e3cf  add     rsp, 20h
0x18000e3d3  pop     rbp
0x18000e3d4  retn
```
