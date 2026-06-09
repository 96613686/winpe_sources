# EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)

- ea: `0x18001cb34`
- end: `0x18001ccfe`
- name: `?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180011ae0`

## callees

- `0x180002af0`
- `0x18000a21c`
- `0x18000a3e4`
- `0x180011218`
- `0x18001204c`
- `0x18001206c`
- `0x18001cb34`
- `0x18003043c`
- `0x18003165c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cc06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cbf1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001cbf1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapLm::BaseEapLibraryManager::ValidateKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  const WCHAR *v6; // rax
  HANDLE FileW; // rax
  const WCHAR *v8; // rax
  int BinaryArch; // ebx
  __int64 v10; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  _BYTE v14[16]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-28h]

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
    v14,
    a2,
    a3,
    a2);
  if ( (unsigned int)RegistryKey::QueryValue(v4, a3, v14) != 1 )
  {
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
      }
      goto LABEL_23;
    }
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
    if ( v6 && *v6 && (FileW = CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0x80u, 0), FileW != (HANDLE)-1LL) )
    {
      CloseHandle(FileW);
      v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      BinaryArch = File::GetBinaryArch(v8);
      if ( BinaryArch != -1 && BinaryArch == (unsigned int)File::GetBinaryArch(0) )
      {
        v5 = 1;
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_23:
        v5 = -1;
        goto LABEL_24;
      }
      v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      v12 = 59;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (EapHost::Peer::Host *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_23;
      }
      v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      v12 = 60;
    }
    WPP_SF_S(*(_QWORD *)(v11 + 16), v12, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v10);
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, a3);
  }
  v5 = 0;
LABEL_24:
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v14);
  return v5;
}

```

## disassembly

```asm
0x18001cb34  push    rbx
0x18001cb36  sub     rsp, 70h
0x18001cb3a  mov     rax, cs:__security_cookie
0x18001cb41  xor     rax, rsp
0x18001cb44  mov     [rsp+78h+var_18], rax
0x18001cb49  mov     rbx, r8
0x18001cb4c  mov     r9, rdx
0x18001cb4f  lea     rcx, [rsp+78h+var_38]
0x18001cb54  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001cb59  nop
0x18001cb5a  lea     r8, [rsp+78h+var_38]
0x18001cb5f  mov     rdx, rbx
0x18001cb62  mov     rcx, r9
0x18001cb65  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001cb6a  cmp     eax, 1
0x18001cb6d  jnz     short loc_18001CBA7
0x18001cb6f  lea     rax, WPP_GLOBAL_Control
0x18001cb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb7d  cmp     rcx, rax
0x18001cb80  jz      short loc_18001CBA0
0x18001cb82  test    byte ptr [rcx+1Ch], 4
0x18001cb86  jz      short loc_18001CBA0
0x18001cb88  mov     edx, 3Ah ; ':'
0x18001cb8d  mov     r9, rbx
0x18001cb90  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001cb97  mov     rcx, [rcx+10h]
0x18001cb9b  call    WPP_SF_S
0x18001cba0  xor     ebx, ebx
0x18001cba2  jmp     loc_18001CCDE
0x18001cba7  xor     ebx, ebx
0x18001cba9  cmp     [rsp+78h+var_28], rbx
0x18001cbae  jbe     loc_18001CCAD
0x18001cbb4  lea     rcx, [rsp+78h+var_38]
0x18001cbb9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cbbe  test    rax, rax
0x18001cbc1  jz      loc_18001CC6F
0x18001cbc7  cmp     [rax], bx
0x18001cbca  jz      loc_18001CC6F
0x18001cbd0  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18001cbd5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001cbdd  lea     r8d, [rbx+3]; dwShareMode
0x18001cbe1  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001cbe6  xor     r9d, r9d; lpSecurityAttributes
0x18001cbe9  mov     edx, 80000000h; dwDesiredAccess
0x18001cbee  mov     rcx, rax; lpFileName
0x18001cbf1  call    cs:__imp_CreateFileW
0x18001cbf8  nop     dword ptr [rax+rax+00h]
0x18001cbfd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cc01  jz      short loc_18001CC6F
0x18001cc03  mov     rcx, rax; hObject
0x18001cc06  call    cs:__imp_CloseHandle
0x18001cc0d  nop     dword ptr [rax+rax+00h]
0x18001cc12  lea     rcx, [rsp+78h+var_38]
0x18001cc17  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cc1c  mov     rcx, rax
0x18001cc1f  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18001cc24  mov     ebx, eax
0x18001cc26  cmp     eax, 0FFFFFFFFh
0x18001cc29  jz      short loc_18001CC40
0x18001cc2b  xor     ecx, ecx
0x18001cc2d  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18001cc32  cmp     ebx, eax
0x18001cc34  jnz     short loc_18001CC40
0x18001cc36  mov     ebx, 1
0x18001cc3b  jmp     loc_18001CCDE
0x18001cc40  lea     rax, WPP_GLOBAL_Control
0x18001cc47  mov     r10, cs:WPP_GLOBAL_Control
0x18001cc4e  cmp     r10, rax
0x18001cc51  jz      loc_18001CCDB
0x18001cc57  test    byte ptr [r10+1Ch], 4
0x18001cc5c  jz      short loc_18001CCDB
0x18001cc5e  lea     rcx, [rsp+78h+var_38]
0x18001cc63  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cc68  mov     edx, 3Bh ; ';'
0x18001cc6d  jmp     short loc_18001CC98
0x18001cc6f  lea     rax, WPP_GLOBAL_Control
0x18001cc76  mov     r10, cs:WPP_GLOBAL_Control
0x18001cc7d  cmp     r10, rax
0x18001cc80  jz      short loc_18001CCDB
0x18001cc82  test    byte ptr [r10+1Ch], 4
0x18001cc87  jz      short loc_18001CCDB
0x18001cc89  lea     rcx, [rsp+78h+var_38]
0x18001cc8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001cc93  mov     edx, 3Ch ; '<'
0x18001cc98  mov     r9, rax
0x18001cc9b  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001cca2  mov     rcx, [r10+10h]
0x18001cca6  call    WPP_SF_S
0x18001ccab  jmp     short loc_18001CCDB
0x18001ccad  lea     rax, WPP_GLOBAL_Control
0x18001ccb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccbb  cmp     rcx, rax
0x18001ccbe  jz      short loc_18001CCDB
0x18001ccc0  test    byte ptr [rcx+1Ch], 4
0x18001ccc4  jz      short loc_18001CCDB
0x18001ccc6  mov     edx, 3Dh ; '='
0x18001cccb  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001ccd2  mov     rcx, [rcx+10h]
0x18001ccd6  call    WPP_SF_
0x18001ccdb  or      ebx, 0FFFFFFFFh
0x18001ccde  lea     rcx, [rsp+78h+var_38]
0x18001cce3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001cce8  mov     eax, ebx
0x18001ccea  mov     rcx, [rsp+78h+var_18]
0x18001ccef  xor     rcx, rsp; StackCookie
0x18001ccf2  call    __security_check_cookie
0x18001ccf7  add     rsp, 70h
0x18001ccfb  pop     rbx
0x18001ccfc  retn
```
