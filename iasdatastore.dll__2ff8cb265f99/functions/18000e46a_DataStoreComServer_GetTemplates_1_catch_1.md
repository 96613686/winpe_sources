# _DataStoreComServer::GetTemplates_::_1_::catch$1

- ea: `0x18000e46a`
- end: `0x18000e4e2`
- name: `_DataStoreComServer::GetTemplates_::_1_::catch$1`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800071ac`
- `0x18000d990`
- `0x18000e46a`

## string_xrefs

- `0x18000e4a3`: `Error in DataStoreComServer::GetTemplates() - Caught COM exception (%!hresult!)...`

## pseudocode

```c
__int64 __fastcall DataStoreComServer::GetTemplates_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 96) = *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("Error in DataStoreComServer::GetTemplates() - Caught COM exception (%!hresult!)...");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e46a  mov     [rsp+arg_8], rdx
0x18000e46f  push    rbx
0x18000e470  push    rbp
0x18000e471  sub     rsp, 38h
0x18000e475  mov     rbp, rdx
0x18000e478  mov     rax, [rbp+30h]
0x18000e47c  mov     ebx, [rax+8]
0x18000e47f  mov     [rbp+60h], ebx
0x18000e482  lea     rcx, WPP_GLOBAL_Control
0x18000e489  mov     rax, cs:WPP_GLOBAL_Control
0x18000e490  cmp     rax, rcx
0x18000e493  jz      short loc_18000E4D0
0x18000e495  cmp     byte ptr [rax+19h], 2
0x18000e499  jb      short loc_18000E4D0
0x18000e49b  test    byte ptr [rax+1Ch], 10h
0x18000e49f  jz      short loc_18000E4D0
0x18000e4a1  mov     edx, ebx
0x18000e4a3  lea     rcx, aErrorInDatasto_5; "Error in DataStoreComServer::GetTemplat"...
0x18000e4aa  call    WppDbgPrint
0x18000e4af  mov     edx, 13h
0x18000e4b4  mov     [rsp+48h+var_28], ebx
0x18000e4b8  lea     r8, WPP_1fdf44c3c99737e7cc94960c70475a5a_Traceguids
0x18000e4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4c6  mov     rcx, [rcx+10h]
0x18000e4ca  call    WPP_SF_sd
0x18000e4cf  nop
0x18000e4d0  mov     rax, 0
0x18000e4da  add     rsp, 38h
0x18000e4de  pop     rbp
0x18000e4df  pop     rbx
0x18000e4e0  retn
```
