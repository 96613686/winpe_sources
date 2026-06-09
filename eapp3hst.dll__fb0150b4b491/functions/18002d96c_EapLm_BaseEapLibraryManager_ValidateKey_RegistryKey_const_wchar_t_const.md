# EapLm::BaseEapLibraryManager::ValidateKey(RegistryKey const &,wchar_t const *)

- ea: `0x18002d96c`
- end: `0x18002db29`
- name: `?ValidateKey@BaseEapLibraryManager@EapLm@@IEAA?AW4ResultType@ResultValue@2@AEBVRegistryKey@@PEB_W@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180016ec0`
- `0x1800222e0`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000eb74`
- `0x18000eb94`
- `0x1800123c8`
- `0x1800165a4`
- `0x180016c54`
- `0x18002ab2c`
- `0x18002d96c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da38`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da29`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002da29`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EapLm::BaseEapLibraryManager::ValidateKey(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  unsigned int v5; // ebx
  const WCHAR *v6; // rax
  HANDLE FileW; // rax
  __int64 v8; // rax
  int BinaryArch; // ebx
  __int64 v10; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  _BYTE v14[16]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v15; // [rsp+50h] [rbp-28h]

  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(v14);
  if ( (unsigned int)RegistryKey::QueryValue(v4, a3, v14) != 1 )
  {
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
      goto LABEL_23;
    }
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
    if ( v6 && *v6 && (FileW = CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0x80u, 0), FileW != (HANDLE)-1LL) )
    {
      CloseHandle(FileW);
      v8 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      BinaryArch = File::GetBinaryArch(v8);
      if ( BinaryArch != -1 && BinaryArch == (unsigned int)File::GetBinaryArch(0) )
      {
        v5 = 1;
        goto LABEL_24;
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
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
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_23;
      v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
      v12 = 60;
    }
    WPP_SF_S(*(_QWORD *)(v11 + 16), v12, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, v10);
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids, a3);
  v5 = 0;
LABEL_24:
  std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(v14);
  return v5;
}

```

## disassembly

```asm
0x18002d96c  push    rbx
0x18002d96e  sub     rsp, 70h
0x18002d972  mov     rax, cs:__security_cookie
0x18002d979  xor     rax, rsp
0x18002d97c  mov     [rsp+78h+var_18], rax
0x18002d981  mov     rbx, r8
0x18002d984  mov     r9, rdx
0x18002d987  lea     rcx, [rsp+78h+var_38]
0x18002d98c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
0x18002d991  nop
0x18002d992  lea     r8, [rsp+78h+var_38]
0x18002d997  mov     rdx, rbx
0x18002d99a  mov     rcx, r9
0x18002d99d  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; RegistryKey::QueryValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> &)
0x18002d9a2  cmp     eax, 1
0x18002d9a5  jnz     short loc_18002D9DF
0x18002d9a7  lea     rax, WPP_GLOBAL_Control
0x18002d9ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9b5  cmp     rcx, rax
0x18002d9b8  jz      short loc_18002D9D8
0x18002d9ba  test    byte ptr [rcx+1Ch], 4
0x18002d9be  jz      short loc_18002D9D8
0x18002d9c0  mov     edx, 3Ah ; ':'
0x18002d9c5  mov     r9, rbx
0x18002d9c8  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002d9cf  mov     rcx, [rcx+10h]
0x18002d9d3  call    WPP_SF_S
0x18002d9d8  xor     ebx, ebx
0x18002d9da  jmp     loc_18002DB0A
0x18002d9df  xor     ebx, ebx
0x18002d9e1  cmp     [rsp+78h+var_28], rbx
0x18002d9e6  jbe     loc_18002DAD9
0x18002d9ec  lea     rcx, [rsp+78h+var_38]
0x18002d9f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002d9f6  test    rax, rax
0x18002d9f9  jz      loc_18002DA9B
0x18002d9ff  cmp     [rax], bx
0x18002da02  jz      loc_18002DA9B
0x18002da08  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18002da0d  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002da15  lea     r8d, [rbx+3]; dwShareMode
0x18002da19  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002da1e  xor     r9d, r9d; lpSecurityAttributes
0x18002da21  mov     edx, 80000000h; dwDesiredAccess
0x18002da26  mov     rcx, rax; lpFileName
0x18002da29  call    cs:__imp_CreateFileW
0x18002da2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002da33  jz      short loc_18002DA9B
0x18002da35  mov     rcx, rax; hObject
0x18002da38  call    cs:__imp_CloseHandle
0x18002da3e  lea     rcx, [rsp+78h+var_38]
0x18002da43  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002da48  mov     rcx, rax
0x18002da4b  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18002da50  mov     ebx, eax
0x18002da52  cmp     eax, 0FFFFFFFFh
0x18002da55  jz      short loc_18002DA6C
0x18002da57  xor     ecx, ecx
0x18002da59  call    ?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z; File::GetBinaryArch(wchar_t const *)
0x18002da5e  cmp     ebx, eax
0x18002da60  jnz     short loc_18002DA6C
0x18002da62  mov     ebx, 1
0x18002da67  jmp     loc_18002DB0A
0x18002da6c  lea     rax, WPP_GLOBAL_Control
0x18002da73  mov     r10, cs:WPP_GLOBAL_Control
0x18002da7a  cmp     r10, rax
0x18002da7d  jz      loc_18002DB07
0x18002da83  test    byte ptr [r10+1Ch], 4
0x18002da88  jz      short loc_18002DB07
0x18002da8a  lea     rcx, [rsp+78h+var_38]
0x18002da8f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002da94  mov     edx, 3Bh ; ';'
0x18002da99  jmp     short loc_18002DAC4
0x18002da9b  lea     rax, WPP_GLOBAL_Control
0x18002daa2  mov     r10, cs:WPP_GLOBAL_Control
0x18002daa9  cmp     r10, rax
0x18002daac  jz      short loc_18002DB07
0x18002daae  test    byte ptr [r10+1Ch], 4
0x18002dab3  jz      short loc_18002DB07
0x18002dab5  lea     rcx, [rsp+78h+var_38]
0x18002daba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002dabf  mov     edx, 3Ch ; '<'
0x18002dac4  mov     r9, rax
0x18002dac7  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002dace  mov     rcx, [r10+10h]
0x18002dad2  call    WPP_SF_S
0x18002dad7  jmp     short loc_18002DB07
0x18002dad9  lea     rax, WPP_GLOBAL_Control
0x18002dae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dae7  cmp     rcx, rax
0x18002daea  jz      short loc_18002DB07
0x18002daec  test    byte ptr [rcx+1Ch], 4
0x18002daf0  jz      short loc_18002DB07
0x18002daf2  mov     edx, 3Dh ; '='
0x18002daf7  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002dafe  mov     rcx, [rcx+10h]
0x18002db02  call    WPP_SF_
0x18002db07  or      ebx, 0FFFFFFFFh
0x18002db0a  lea     rcx, [rsp+78h+var_38]
0x18002db0f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18002db14  mov     eax, ebx
0x18002db16  mov     rcx, [rsp+78h+var_18]
0x18002db1b  xor     rcx, rsp; StackCookie
0x18002db1e  call    __security_check_cookie
0x18002db23  add     rsp, 70h
0x18002db27  pop     rbx
0x18002db28  retn
```
