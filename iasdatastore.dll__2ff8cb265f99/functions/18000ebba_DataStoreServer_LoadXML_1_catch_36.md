# _DataStoreServer::LoadXML_::_1_::catch$36

- ea: `0x18000ebba`
- end: `0x18000ec38`
- name: `_DataStoreServer::LoadXML_::_1_::catch$36`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800071ac`
- `0x18000d990`
- `0x18000ebba`

## string_xrefs

- `0x18000ebf9`: `IXMLDOMDocument2::loadXML failed %!hresult!`

## pseudocode

```c
__int64 __fastcall DataStoreServer::LoadXML_::_1_::catch_36(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 240) = *(_DWORD *)(*(_QWORD *)(a2 + 200) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("IXMLDOMDocument2::loadXML failed %!hresult!");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ebba  mov     [rsp+arg_8], rdx
0x18000ebbf  push    rbx
0x18000ebc0  push    rbp
0x18000ebc1  sub     rsp, 38h
0x18000ebc5  mov     rbp, rdx
0x18000ebc8  mov     rax, [rbp+0C8h]
0x18000ebcf  mov     ebx, [rax+8]
0x18000ebd2  mov     [rbp+0F0h], ebx
0x18000ebd8  lea     rcx, WPP_GLOBAL_Control
0x18000ebdf  mov     rax, cs:WPP_GLOBAL_Control
0x18000ebe6  cmp     rax, rcx
0x18000ebe9  jz      short loc_18000EC26
0x18000ebeb  cmp     byte ptr [rax+19h], 2
0x18000ebef  jb      short loc_18000EC26
0x18000ebf1  test    byte ptr [rax+1Ch], 10h
0x18000ebf5  jz      short loc_18000EC26
0x18000ebf7  mov     edx, ebx
0x18000ebf9  lea     rcx, aIxmldomdocumen_1; "IXMLDOMDocument2::loadXML failed %!hres"...
0x18000ec00  call    WppDbgPrint
0x18000ec05  mov     edx, 3Bh ; ';'
0x18000ec0a  mov     [rsp+48h+var_28], ebx
0x18000ec0e  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000ec15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec1c  mov     rcx, [rcx+10h]
0x18000ec20  call    WPP_SF_sd
0x18000ec25  nop
0x18000ec26  mov     rax, 0
0x18000ec30  add     rsp, 38h
0x18000ec34  pop     rbp
0x18000ec35  pop     rbx
0x18000ec36  retn
```
