# _DataStoreServer::Load_::_1_::catch$41

- ea: `0x18000e971`
- end: `0x18000e9ef`
- name: `_DataStoreServer::Load_::_1_::catch$41`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800071ac`
- `0x18000d990`
- `0x18000e971`

## string_xrefs

- `0x18000e9b0`: `IXMLDOMDocument2::load failed %!hresult!`

## pseudocode

```c
__int64 __fastcall DataStoreServer::Load_::_1_::catch_41(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 288) = *(_DWORD *)(*(_QWORD *)(a2 + 192) + 8LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("IXMLDOMDocument2::load failed %!hresult!");
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e971  mov     [rsp+arg_8], rdx
0x18000e976  push    rbx
0x18000e977  push    rbp
0x18000e978  sub     rsp, 38h
0x18000e97c  mov     rbp, rdx
0x18000e97f  mov     rax, [rbp+0C0h]
0x18000e986  mov     ebx, [rax+8]
0x18000e989  mov     [rbp+120h], ebx
0x18000e98f  lea     rcx, WPP_GLOBAL_Control
0x18000e996  mov     rax, cs:WPP_GLOBAL_Control
0x18000e99d  cmp     rax, rcx
0x18000e9a0  jz      short loc_18000E9DD
0x18000e9a2  cmp     byte ptr [rax+19h], 2
0x18000e9a6  jb      short loc_18000E9DD
0x18000e9a8  test    byte ptr [rax+1Ch], 10h
0x18000e9ac  jz      short loc_18000E9DD
0x18000e9ae  mov     edx, ebx
0x18000e9b0  lea     rcx, aIxmldomdocumen; "IXMLDOMDocument2::load failed %!hresult"...
0x18000e9b7  call    WppDbgPrint
0x18000e9bc  mov     edx, 38h ; '8'
0x18000e9c1  mov     [rsp+48h+var_28], ebx
0x18000e9c5  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000e9cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9d3  mov     rcx, [rcx+10h]
0x18000e9d7  call    WPP_SF_sd
0x18000e9dc  nop
0x18000e9dd  mov     rax, 0
0x18000e9e7  add     rsp, 38h
0x18000e9eb  pop     rbp
0x18000e9ec  pop     rbx
0x18000e9ed  retn
```
