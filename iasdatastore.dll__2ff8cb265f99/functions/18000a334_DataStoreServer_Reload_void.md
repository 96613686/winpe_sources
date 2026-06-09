# DataStoreServer::Reload(void)

- ea: `0x18000a334`
- end: `0x18000a498`
- name: `?Reload@DataStoreServer@@QEAAJXZ`
- size: `356`
- prototype: `__int64 __fastcall(const WCHAR *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006ee0`

## callees

- `0x1800071ac`
- `0x1800093cc`
- `0x18000a334`
- `0x18000d8f0`
- `0x18000d990`
- `0x180010010`

## string_xrefs

- `0x18000a3b2`: `Load configuration failed:%!hresult! in DataStoreServer::Reload()`
- `0x18000a456`: `Load templates failed:%!hresult! in DataStoreServer::Reload()`

## pseudocode

```c
__int64 __fastcall DataStoreServer::Reload(const WCHAR *this)
{
  _QWORD *v2; // rbx
  __int64 v3; // rcx
  int v4; // esi
  _QWORD *v6; // rbx
  __int64 v7; // rcx
  int v8; // edi

  if ( !IASFileExists(this + 25) )
    goto LABEL_24;
  v2 = this + 1072;
  v3 = *((_QWORD *)this + 268);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *v2 = 0;
  }
  v4 = DataStoreServer::Load(v3, this + 25, this + 1072);
  if ( v4 >= 0 && *v2 )
  {
LABEL_24:
    if ( !IASFileExists(this + 286) )
      return 0;
    v6 = this + 1076;
    v7 = *((_QWORD *)this + 269);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      *v6 = 0;
    }
    v8 = DataStoreServer::Load(v7, this + 286, this + 1076);
    if ( v8 >= 0 && *v6 )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WppDbgPrint("Load templates failed:%!hresult! in DataStoreServer::Reload()");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
      }
      return (unsigned int)v8;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Load configuration failed:%!hresult! in DataStoreServer::Reload()");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids);
    }
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x18000a334  mov     [rsp+arg_0], rbx
0x18000a339  mov     [rsp+arg_8], rsi
0x18000a33e  push    rdi
0x18000a33f  sub     rsp, 30h
0x18000a343  mov     rdi, rcx
0x18000a346  add     rcx, 32h ; '2'
0x18000a34a  call    IASFileExists
0x18000a34f  test    al, al
0x18000a351  jz      loc_18000A3E5
0x18000a357  lea     rbx, [rdi+860h]
0x18000a35e  mov     rcx, [rbx]
0x18000a361  test    rcx, rcx
0x18000a364  jz      short loc_18000A379
0x18000a366  mov     rax, [rcx]
0x18000a369  mov     rax, [rax+10h]
0x18000a36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a372  mov     qword ptr [rbx], 0
0x18000a379  mov     r8, rbx
0x18000a37c  lea     rdx, [rdi+32h]
0x18000a380  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a385  mov     esi, eax
0x18000a387  test    eax, eax
0x18000a389  js      short loc_18000A391
0x18000a38b  cmp     qword ptr [rbx], 0
0x18000a38f  jnz     short loc_18000A3E5
0x18000a391  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a398  lea     rdx, WPP_GLOBAL_Control
0x18000a39f  cmp     rcx, rdx
0x18000a3a2  jz      short loc_18000A3DE
0x18000a3a4  cmp     byte ptr [rcx+19h], 2
0x18000a3a8  jb      short loc_18000A3DE
0x18000a3aa  test    byte ptr [rcx+1Ch], 10h
0x18000a3ae  jz      short loc_18000A3DE
0x18000a3b0  mov     edx, esi
0x18000a3b2  lea     rcx, aLoadConfigurat; "Load configuration failed:%!hresult! in"...
0x18000a3b9  call    WppDbgPrint
0x18000a3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3c5  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a3cc  mov     edx, 42h ; 'B'
0x18000a3d1  mov     [rsp+38h+var_18], esi
0x18000a3d5  mov     rcx, [rcx+10h]
0x18000a3d9  call    WPP_SF_sd
0x18000a3de  mov     eax, esi
0x18000a3e0  jmp     loc_18000A488
0x18000a3e5  lea     rsi, [rdi+23Ch]
0x18000a3ec  mov     rcx, rsi
0x18000a3ef  call    IASFileExists
0x18000a3f4  test    al, al
0x18000a3f6  jz      loc_18000A486
0x18000a3fc  lea     rbx, [rdi+868h]
0x18000a403  mov     rcx, [rbx]
0x18000a406  test    rcx, rcx
0x18000a409  jz      short loc_18000A41E
0x18000a40b  mov     rax, [rcx]
0x18000a40e  mov     rax, [rax+10h]
0x18000a412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a417  mov     qword ptr [rbx], 0
0x18000a41e  mov     r8, rbx
0x18000a421  mov     rdx, rsi
0x18000a424  call    ?Load@DataStoreServer@@AEAAJPEBGAEAV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument2@MSXML2@@$1?_GUID_2933bf95_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; DataStoreServer::Load(ushort const *,_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument2,&__s_GUID const _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60>> &)
0x18000a429  mov     edi, eax
0x18000a42b  test    eax, eax
0x18000a42d  js      short loc_18000A435
0x18000a42f  cmp     qword ptr [rbx], 0
0x18000a433  jnz     short loc_18000A486
0x18000a435  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a43c  lea     rdx, WPP_GLOBAL_Control
0x18000a443  cmp     rcx, rdx
0x18000a446  jz      short loc_18000A482
0x18000a448  cmp     byte ptr [rcx+19h], 2
0x18000a44c  jb      short loc_18000A482
0x18000a44e  test    byte ptr [rcx+1Ch], 10h
0x18000a452  jz      short loc_18000A482
0x18000a454  mov     edx, edi
0x18000a456  lea     rcx, aLoadTemplatesF; "Load templates failed:%!hresult! in Dat"...
0x18000a45d  call    WppDbgPrint
0x18000a462  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a469  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids
0x18000a470  mov     edx, 43h ; 'C'
0x18000a475  mov     [rsp+38h+var_18], edi
0x18000a479  mov     rcx, [rcx+10h]
0x18000a47d  call    WPP_SF_sd
0x18000a482  mov     eax, edi
0x18000a484  jmp     short loc_18000A488
0x18000a486  xor     eax, eax
0x18000a488  mov     rbx, [rsp+38h+arg_0]
0x18000a48d  mov     rsi, [rsp+38h+arg_8]
0x18000a492  add     rsp, 30h
0x18000a496  pop     rdi
0x18000a497  retn
```
