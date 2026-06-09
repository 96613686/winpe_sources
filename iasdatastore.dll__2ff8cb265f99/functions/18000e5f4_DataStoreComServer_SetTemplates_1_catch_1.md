# _DataStoreComServer::SetTemplates_::_1_::catch$1

- ea: `0x18000e5f4`
- end: `0x18000e66c`
- name: `_DataStoreComServer::SetTemplates_::_1_::catch$1`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800071ac`
- `0x18000d990`
- `0x18000e5f4`

## string_xrefs

- `0x18000e62d`: `Error in DataStoreComServer::SetTemplates() - Caught COM exception (%!hresult!)...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::SetTemplates_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::SetTemplates() - Caught COM exception (%!hresult!)...");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e5f4  mov     [rsp+arg_8], rdx
0x18000e5f9  push    rbx
0x18000e5fa  push    rbp
0x18000e5fb  sub     rsp, 38h
0x18000e5ff  mov     rbp, rdx
0x18000e602  mov     rax, [rbp+30h]
0x18000e606  mov     ebx, [rax+8]
0x18000e609  mov     [rbp+70h], ebx
0x18000e60c  lea     rcx, WPP_GLOBAL_Control
0x18000e613  mov     rax, cs:WPP_GLOBAL_Control
0x18000e61a  cmp     rax, rcx
0x18000e61d  jz      short loc_18000E65A
0x18000e61f  cmp     byte ptr [rax+19h], 2
0x18000e623  jb      short loc_18000E65A
0x18000e625  test    byte ptr [rax+1Ch], 10h
0x18000e629  jz      short loc_18000E65A
0x18000e62b  mov     edx, ebx
0x18000e62d  lea     rcx, aErrorInDatasto; "Error in DataStoreComServer::SetTemplat"...
0x18000e634  call    WppDbgPrint
0x18000e639  mov     edx, 15h
0x18000e63e  mov     [rsp+48h+var_28], ebx
0x18000e642  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e649  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e650  mov     rcx, [rcx+10h]
0x18000e654  call    WPP_SF_sd
0x18000e659  nop
0x18000e65a  mov     rax, 0
0x18000e664  add     rsp, 38h
0x18000e668  pop     rbp
0x18000e669  pop     rbx
0x18000e66a  retn
```
