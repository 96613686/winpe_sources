# DialupConnection::HrEnsureCmStringsLoaded(void)

- ea: `0x18002c4e8`
- end: `0x18002c740`
- name: `?HrEnsureCmStringsLoaded@DialupConnection@@AEAAJXZ`
- size: `600`
- prototype: `__int64 __fastcall(DialupConnection *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18002b7d0`

## callees

- `0x180001710`
- `0x180003d5c`
- `0x180004340`
- `0x180004d80`
- `0x18000538c`
- `0x1800084fc`
- `0x18002c4e8`
- `0x18002c960`
- `0x18002cf50`
- `0x18002cf80`
- `0x180034d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18002c5af`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18002c5af`
- `KERNEL32!EnterCriticalSection` at `0x18002c522`
- `KERNEL32!EnterCriticalSection` at `0x18002c522`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DialupConnection::HrEnsureCmStringsLoaded(DialupConnection *this)
{
  int CmpFileLocation; // edi
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  const unsigned __int16 *v4; // rdi
  const unsigned __int16 *v5; // rax
  char *v6; // rax
  char *v7; // rax
  char *v8; // rax
  char *v9; // rax
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dir[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t Drive[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v15[264]; // [rsp+690h] [rbp+590h] BYREF
  unsigned __int16 v16[264]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v17[264]; // [rsp+AB0h] [rbp+9B0h] BYREF
  wchar_t FullPath[264]; // [rsp+CC0h] [rbp+BC0h] BYREF
  wchar_t Ext[264]; // [rsp+ED0h] [rbp+DD0h] BYREF

  CmpFileLocation = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 320);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 8);
  v11 = v3;
  if ( !*((_DWORD *)this + 122) )
  {
    v4 = RasConnectionBase::PszwEntryName((DialupConnection *)((char *)this + 104));
    v5 = RasConnectionBase::PszwPbkFile((DialupConnection *)((char *)this + 104));
    CmpFileLocation = DialupConnection::HrGetCmpFileLocation((struct _RTL_CRITICAL_SECTION *)this, v5, v4, FullPath);
    if ( CmpFileLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids,
          (unsigned int)CmpFileLocation);
    }
    else
    {
      _wsplitpath_s(FullPath, Drive, 0x104u, Dir, 0x104u, Filename, 0x104u, Ext, 0x104u);
      StringCchPrintfW(v15, 0x104u, L"%s%s%s\\%s%s", Drive, Dir, Filename, Filename, L".cms");
      StringCchPrintfW(v16, 0x104u, L"%s%s%s\\", Drive, Dir, Filename);
      StringCchPrintfW(v17, 0x104u, L"%s%s", Drive, Dir);
      v6 = (char *)std::_WChar_traits<unsigned short>::length(v15);
      std::wstring::_Assign<unsigned short>((char **)this + 45, v15, v6);
      v7 = (char *)std::_WChar_traits<unsigned short>::length(v16);
      std::wstring::_Assign<unsigned short>((char **)this + 49, v16, v7);
      v8 = (char *)std::_WChar_traits<unsigned short>::length(v17);
      std::wstring::_Assign<unsigned short>((char **)this + 57, v17, v8);
      v9 = (char *)std::_WChar_traits<unsigned short>::length(Filename);
      std::wstring::_Assign<unsigned short>((char **)this + 53, Filename, v9);
      *((_DWORD *)this + 122) = 1;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v11);
  return (unsigned int)CmpFileLocation;
}

```

## disassembly

```asm
0x18002c4e8  push    rbp
0x18002c4ea  push    rbx
0x18002c4eb  push    rsi
0x18002c4ec  push    rdi
0x18002c4ed  lea     rbp, [rsp-0FF8h]
0x18002c4f5  mov     eax, 10F8h
0x18002c4fa  call    _alloca_probe
0x18002c4ff  sub     rsp, rax
0x18002c502  mov     rax, cs:__security_cookie
0x18002c509  xor     rax, rsp
0x18002c50c  mov     [rbp+1010h+var_30], rax
0x18002c513  mov     rsi, rcx
0x18002c516  xor     edi, edi
0x18002c518  lea     rbx, [rcx+140h]
0x18002c51f  mov     rcx, rbx; lpCriticalSection
0x18002c522  call    cs:__imp_EnterCriticalSection
0x18002c528  mov     [rsp+1110h+var_10C0], rbx
0x18002c52d  cmp     [rsi+1E8h], edi
0x18002c533  jnz     loc_18002C719
0x18002c539  lea     rcx, [rsi+68h]; this
0x18002c53d  call    ?PszwEntryName@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwEntryName(void)
0x18002c542  mov     rdi, rax
0x18002c545  lea     rcx, [rsi+68h]; this
0x18002c549  call    ?PszwPbkFile@RasConnectionBase@@IEAAPEBGXZ; RasConnectionBase::PszwPbkFile(void)
0x18002c54e  lea     r9, [rbp+1010h+FullPath]; unsigned __int16 *
0x18002c555  mov     r8, rdi; unsigned __int16 *
0x18002c558  mov     rdx, rax; unsigned __int16 *
0x18002c55b  mov     rcx, rsi; this
0x18002c55e  call    ?HrGetCmpFileLocation@DialupConnection@@AEAAJPEBG0PEAG@Z; DialupConnection::HrGetCmpFileLocation(ushort const *,ushort const *,ushort *)
0x18002c563  mov     edi, eax
0x18002c565  test    eax, eax
0x18002c567  js      loc_18002C6E7
0x18002c56d  mov     ebx, 104h
0x18002c572  mov     [rsp+1110h+ExtCount], rbx; ExtCount
0x18002c577  lea     rax, [rbp+1010h+var_240]
0x18002c57e  mov     [rsp+1110h+Ext], rax; Ext
0x18002c583  mov     [rsp+1110h+FilenameCount], rbx; FilenameCount
0x18002c588  lea     rax, [rsp+1110h+var_10B0]
0x18002c58d  mov     [rsp+1110h+Filename], rax; Filename
0x18002c592  mov     [rsp+1110h+DirCount], rbx; DirCount
0x18002c597  lea     r9, [rbp+1010h+Dir]; Dir
0x18002c59e  mov     r8d, ebx; DriveCount
0x18002c5a1  lea     rdx, [rbp+1010h+Drive]; Drive
0x18002c5a8  lea     rcx, [rbp+1010h+FullPath]; FullPath
0x18002c5af  call    cs:__imp__wsplitpath_s
0x18002c5b5  lea     rax, aCms; ".cms"
0x18002c5bc  mov     [rsp+1110h+Ext], rax
0x18002c5c1  lea     rax, [rsp+1110h+var_10B0]
0x18002c5c6  mov     [rsp+1110h+FilenameCount], rax
0x18002c5cb  lea     rax, [rsp+1110h+var_10B0]
0x18002c5d0  mov     [rsp+1110h+Filename], rax
0x18002c5d5  lea     rax, [rbp+1010h+Dir]
0x18002c5dc  mov     [rsp+1110h+DirCount], rax
0x18002c5e1  lea     r9, [rbp+1010h+Drive]
0x18002c5e8  lea     r8, aSSSSS; "%s%s%s\\%s%s"
0x18002c5ef  mov     edx, ebx; unsigned __int64
0x18002c5f1  lea     rcx, [rbp+1010h+var_A80]; unsigned __int16 *
0x18002c5f8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c5fd  lea     rax, [rsp+1110h+var_10B0]
0x18002c602  mov     [rsp+1110h+Filename], rax
0x18002c607  lea     rax, [rbp+1010h+Dir]
0x18002c60e  mov     [rsp+1110h+DirCount], rax
0x18002c613  lea     r9, [rbp+1010h+Drive]
0x18002c61a  lea     r8, aSSS; "%s%s%s\\"
0x18002c621  mov     edx, ebx; unsigned __int64
0x18002c623  lea     rcx, [rbp+1010h+var_870]; unsigned __int16 *
0x18002c62a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c62f  lea     rax, [rbp+1010h+Dir]
0x18002c636  mov     [rsp+1110h+DirCount], rax
0x18002c63b  lea     r9, [rbp+1010h+Drive]
0x18002c642  lea     r8, aSS_0; "%s%s"
0x18002c649  mov     edx, ebx; unsigned __int64
0x18002c64b  lea     rcx, [rbp+1010h+var_660]; unsigned __int16 *
0x18002c652  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002c657  lea     rcx, [rbp+1010h+var_A80]
0x18002c65e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002c663  mov     r8, rax
0x18002c666  lea     rcx, [rsi+168h]
0x18002c66d  lea     rdx, [rbp+1010h+var_A80]
0x18002c674  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002c679  lea     rcx, [rbp+1010h+var_870]
0x18002c680  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002c685  mov     r8, rax
0x18002c688  lea     rcx, [rsi+188h]
0x18002c68f  lea     rdx, [rbp+1010h+var_870]
0x18002c696  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002c69b  lea     rcx, [rbp+1010h+var_660]
0x18002c6a2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002c6a7  mov     r8, rax
0x18002c6aa  lea     rcx, [rsi+1C8h]
0x18002c6b1  lea     rdx, [rbp+1010h+var_660]
0x18002c6b8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002c6bd  lea     rcx, [rsp+1110h+var_10B0]
0x18002c6c2  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002c6c7  mov     r8, rax
0x18002c6ca  lea     rcx, [rsi+1A8h]
0x18002c6d1  lea     rdx, [rsp+1110h+var_10B0]
0x18002c6d6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18002c6db  mov     dword ptr [rsi+1E8h], 1
0x18002c6e5  jmp     short loc_18002C719
0x18002c6e7  lea     rax, WPP_GLOBAL_Control
0x18002c6ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6f5  cmp     rcx, rax
0x18002c6f8  jz      short loc_18002C719
0x18002c6fa  test    byte ptr [rcx+1Ch], 1
0x18002c6fe  jz      short loc_18002C719
0x18002c700  mov     edx, 26h ; '&'
0x18002c705  mov     r9d, edi
0x18002c708  lea     r8, WPP_72e8a2b6c4a334b644d76a8a8dce3e8a_Traceguids
0x18002c70f  mov     rcx, [rcx+10h]
0x18002c713  call    WPP_SF_d
0x18002c718  nop
0x18002c719  lea     rcx, [rsp+1110h+var_10C0]
0x18002c71e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002c723  mov     eax, edi
0x18002c725  mov     rcx, [rbp+1010h+var_30]
0x18002c72c  xor     rcx, rsp; StackCookie
0x18002c72f  call    __security_check_cookie
0x18002c734  add     rsp, 10F8h
0x18002c73b  pop     rdi
0x18002c73c  pop     rsi
0x18002c73d  pop     rbx
0x18002c73e  pop     rbp
0x18002c73f  retn
```
