# EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)

- ea: `0x18001c0fc`
- end: `0x18001c2b9`
- name: `?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800113a0`

## callees

- `0x180002a90`
- `0x180009dc4`
- `0x180009f70`
- `0x180010aa8`
- `0x1800118e8`
- `0x180011908`
- `0x18001c0fc`
- `0x18002f2e4`
- `0x18003044c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c1c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c1b9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001c1b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18001c0fc  push    rbx
0x18001c0fe  sub     rsp, 70h
0x18001c102  mov     rax, cs:__security_cookie
0x18001c109  xor     rax, rsp
0x18001c10c  mov     [rsp+78h+var_18], rax
0x18001c111  mov     rbx, r8
0x18001c114  mov     r9, rdx
0x18001c117  lea     rcx, [rsp+78h+var_38]
0x18001c11c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18001c121  nop
0x18001c122  lea     r8, [rsp+78h+var_38]
0x18001c127  mov     rdx, rbx
0x18001c12a  mov     rcx, r9
0x18001c12d  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18001c132  cmp     eax, 1
0x18001c135  jnz     short loc_18001C16F
0x18001c137  lea     rax, WPP_GLOBAL_Control
0x18001c13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c145  cmp     rcx, rax
0x18001c148  jz      short loc_18001C168
0x18001c14a  test    byte ptr [rcx+1Ch], 4
0x18001c14e  jz      short loc_18001C168
0x18001c150  mov     edx, 3Ah ; ':'
0x18001c155  mov     r9, rbx
0x18001c158  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c15f  mov     rcx, [rcx+10h]
0x18001c163  call    WPP_SF_S
0x18001c168  xor     ebx, ebx
0x18001c16a  jmp     loc_18001C29A
0x18001c16f  xor     ebx, ebx
0x18001c171  cmp     [rsp+78h+var_28], rbx
0x18001c176  jbe     loc_18001C269
0x18001c17c  lea     rcx, [rsp+78h+var_38]
0x18001c181  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c186  test    rax, rax
0x18001c189  jz      loc_18001C22B
0x18001c18f  cmp     [rax], bx
0x18001c192  jz      loc_18001C22B
0x18001c198  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18001c19d  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001c1a5  lea     r8d, [rbx+3]; dwShareMode
0x18001c1a9  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001c1ae  xor     r9d, r9d; lpSecurityAttributes
0x18001c1b1  mov     edx, 80000000h; dwDesiredAccess
0x18001c1b6  mov     rcx, rax; lpFileName
0x18001c1b9  call    cs:__imp_CreateFileW
0x18001c1bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c1c3  jz      short loc_18001C22B
0x18001c1c5  mov     rcx, rax; hObject
0x18001c1c8  call    cs:__imp_CloseHandle
0x18001c1ce  lea     rcx, [rsp+78h+var_38]
0x18001c1d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c1d8  mov     rcx, rax
0x18001c1db  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18001c1e0  mov     ebx, eax
0x18001c1e2  cmp     eax, 0FFFFFFFFh
0x18001c1e5  jz      short loc_18001C1FC
0x18001c1e7  xor     ecx, ecx
0x18001c1e9  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18001c1ee  cmp     ebx, eax
0x18001c1f0  jnz     short loc_18001C1FC
0x18001c1f2  mov     ebx, 1
0x18001c1f7  jmp     loc_18001C29A
0x18001c1fc  lea     rax, WPP_GLOBAL_Control
0x18001c203  mov     r10, cs:WPP_GLOBAL_Control
0x18001c20a  cmp     r10, rax
0x18001c20d  jz      loc_18001C297
0x18001c213  test    byte ptr [r10+1Ch], 4
0x18001c218  jz      short loc_18001C297
0x18001c21a  lea     rcx, [rsp+78h+var_38]
0x18001c21f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c224  mov     edx, 3Bh ; ';'
0x18001c229  jmp     short loc_18001C254
0x18001c22b  lea     rax, WPP_GLOBAL_Control
0x18001c232  mov     r10, cs:WPP_GLOBAL_Control
0x18001c239  cmp     r10, rax
0x18001c23c  jz      short loc_18001C297
0x18001c23e  test    byte ptr [r10+1Ch], 4
0x18001c243  jz      short loc_18001C297
0x18001c245  lea     rcx, [rsp+78h+var_38]
0x18001c24a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c24f  mov     edx, 3Ch ; '<'
0x18001c254  mov     r9, rax
0x18001c257  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c25e  mov     rcx, [r10+10h]
0x18001c262  call    WPP_SF_S
0x18001c267  jmp     short loc_18001C297
0x18001c269  lea     rax, WPP_GLOBAL_Control
0x18001c270  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c277  cmp     rcx, rax
0x18001c27a  jz      short loc_18001C297
0x18001c27c  test    byte ptr [rcx+1Ch], 4
0x18001c280  jz      short loc_18001C297
0x18001c282  mov     edx, 3Dh ; '='
0x18001c287  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c28e  mov     rcx, [rcx+10h]
0x18001c292  call    WPP_SF_
0x18001c297  or      ebx, 0FFFFFFFFh
0x18001c29a  lea     rcx, [rsp+78h+var_38]
0x18001c29f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18001c2a4  mov     eax, ebx
0x18001c2a6  mov     rcx, [rsp+78h+var_18]
0x18001c2ab  xor     rcx, rsp; StackCookie
0x18001c2ae  call    __security_check_cookie
0x18001c2b3  add     rsp, 70h
0x18001c2b7  pop     rbx
0x18001c2b8  retn
```
