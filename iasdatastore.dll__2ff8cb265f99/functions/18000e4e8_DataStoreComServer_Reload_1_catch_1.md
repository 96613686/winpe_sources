# _DataStoreComServer::Reload_::_1_::catch$1

- ea: `0x18000e4e8`
- end: `0x18000e560`
- name: `_DataStoreComServer::Reload_::_1_::catch$1`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800071ac`
- `0x18000d990`
- `0x18000e4e8`

## string_xrefs

- `0x18000e521`: `Error in DataStoreComServer::Reload() - Caught COM exception (%!hresult!)...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::Reload_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 80) = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::Reload() - Caught COM exception (%!hresult!)...");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e4e8  mov     [rsp+arg_8], rdx
0x18000e4ed  push    rbx
0x18000e4ee  push    rbp
0x18000e4ef  sub     rsp, 38h
0x18000e4f3  mov     rbp, rdx
0x18000e4f6  mov     rax, [rbp+30h]
0x18000e4fa  mov     ebx, [rax+8]
0x18000e4fd  mov     [rbp+50h], ebx
0x18000e500  lea     rcx, WPP_GLOBAL_Control
0x18000e507  mov     rax, cs:WPP_GLOBAL_Control
0x18000e50e  cmp     rax, rcx
0x18000e511  jz      short loc_18000E54E
0x18000e513  cmp     byte ptr [rax+19h], 2
0x18000e517  jb      short loc_18000E54E
0x18000e519  test    byte ptr [rax+1Ch], 10h
0x18000e51d  jz      short loc_18000E54E
0x18000e51f  mov     edx, ebx
0x18000e521  lea     rcx, aErrorInDatasto_0; "Error in DataStoreComServer::Reload() -"...
0x18000e528  call    WppDbgPrint
0x18000e52d  mov     edx, 17h
0x18000e532  mov     [rsp+48h+var_28], ebx
0x18000e536  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e544  mov     rcx, [rcx+10h]
0x18000e548  call    WPP_SF_sd
0x18000e54d  nop
0x18000e54e  mov     rax, 0
0x18000e558  add     rsp, 38h
0x18000e55c  pop     rbp
0x18000e55d  pop     rbx
0x18000e55e  retn
```
