# _DataStoreComServer::SetConfiguration_::_1_::catch$1

- ea: `0x18000e566`
- end: `0x18000e5dc`
- name: `_DataStoreComServer::SetConfiguration_::_1_::catch$1`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007150`
- `0x18000d990`
- `0x18000e566`

## string_xrefs

- `0x18000e592`: `Error in DataStoreComServer::SetConfiguration() - Caught COM exception...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::SetConfiguration_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::SetConfiguration() - Caught COM exception...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
  }
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x18000e566  mov     [rsp+arg_8], rdx
0x18000e56b  push    rbp
0x18000e56c  sub     rsp, 20h
0x18000e570  mov     rbp, rdx
0x18000e573  lea     rcx, WPP_GLOBAL_Control
0x18000e57a  mov     rax, cs:WPP_GLOBAL_Control
0x18000e581  cmp     rax, rcx
0x18000e584  jz      short loc_18000E5C1
0x18000e586  cmp     byte ptr [rax+19h], 2
0x18000e58a  jb      short loc_18000E5C1
0x18000e58c  test    byte ptr [rax+1Ch], 10h
0x18000e590  jz      short loc_18000E5C1
0x18000e592  lea     rcx, aErrorInDatasto_1; "Error in DataStoreComServer::SetConfigu"...
0x18000e599  call    WppDbgPrint
0x18000e59e  mov     edx, 11h
0x18000e5a3  lea     r9, aNpsds; "NPSDS"
0x18000e5aa  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e5b8  mov     rcx, [rcx+10h]
0x18000e5bc  call    WPP_SF_s
0x18000e5c1  mov     rax, [rbp+20h]
0x18000e5c5  mov     ecx, [rax+8]
0x18000e5c8  mov     [rbp+50h], ecx
0x18000e5cb  mov     rax, 0
0x18000e5d5  add     rsp, 20h
0x18000e5d9  pop     rbp
0x18000e5da  retn
```
