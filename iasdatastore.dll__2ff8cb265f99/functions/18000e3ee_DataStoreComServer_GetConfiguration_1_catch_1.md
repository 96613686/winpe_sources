# _DataStoreComServer::GetConfiguration_::_1_::catch$1

- ea: `0x18000e3ee`
- end: `0x18000e464`
- name: `_DataStoreComServer::GetConfiguration_::_1_::catch$1`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007150`
- `0x18000d990`
- `0x18000e3ee`

## string_xrefs

- `0x18000e41a`: `Error in DataStoreComServer::GetConfiguration() - Caught COM exception...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::GetConfiguration_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::GetConfiguration() - Caught COM exception...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids, "NPSDS");
  }
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL);
  return 0;
}

```

## disassembly

```asm
0x18000e3ee  mov     [rsp+arg_8], rdx
0x18000e3f3  push    rbp
0x18000e3f4  sub     rsp, 20h
0x18000e3f8  mov     rbp, rdx
0x18000e3fb  lea     rcx, WPP_GLOBAL_Control
0x18000e402  mov     rax, cs:WPP_GLOBAL_Control
0x18000e409  cmp     rax, rcx
0x18000e40c  jz      short loc_18000E449
0x18000e40e  cmp     byte ptr [rax+19h], 2
0x18000e412  jb      short loc_18000E449
0x18000e414  test    byte ptr [rax+1Ch], 10h
0x18000e418  jz      short loc_18000E449
0x18000e41a  lea     rcx, aErrorInDatasto_2; "Error in DataStoreComServer::GetConfigu"...
0x18000e421  call    WppDbgPrint
0x18000e426  mov     edx, 0Fh
0x18000e42b  lea     r9, aNpsds; "NPSDS"
0x18000e432  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e439  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e440  mov     rcx, [rcx+10h]
0x18000e444  call    WPP_SF_s
0x18000e449  mov     rax, [rbp+20h]
0x18000e44d  mov     ecx, [rax+8]
0x18000e450  mov     [rbp+50h], ecx
0x18000e453  mov     rax, 0
0x18000e45d  add     rsp, 20h
0x18000e461  pop     rbp
0x18000e462  retn
```
