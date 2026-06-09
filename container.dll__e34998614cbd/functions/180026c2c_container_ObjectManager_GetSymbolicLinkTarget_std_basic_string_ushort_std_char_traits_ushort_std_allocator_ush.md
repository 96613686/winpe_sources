# container::ObjectManager::GetSymbolicLinkTarget(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026c2c`
- end: `0x180026ddc`
- name: `?GetSymbolicLinkTarget@ObjectManager@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180027438`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000ca10`
- `0x180026830`
- `0x180026c2c`
- `0x18002754c`

## import_xrefs

- `ntdll!NtOpenSymbolicLinkObject` at `0x180026c8d`
- `ntdll!NtOpenSymbolicLinkObject` at `0x180026c8d`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180026cf8`
- `ntdll!NtQuerySymbolicLinkObject` at `0x180026cf8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026d89`

## string_xrefs

- `0x180026d26`: `QuerySymbolicLinkObject(%ws) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall container::ObjectManager::GetSymbolicLinkTarget(__int64 a1, const char *a2)
{
  const char *v2; // rbx
  NTSTATUS v4; // eax
  ULONG v5; // eax
  WCHAR *v6; // rdi
  unsigned __int64 v7; // rdx
  WCHAR *v8; // rsi
  unsigned int v9; // eax
  unsigned __int64 v10; // rdx
  int v12; // [rsp+20h] [rbp-69h]
  ULONG DataWritten; // [rsp+30h] [rbp-59h] BYREF
  void *SymbolicLinkHandle; // [rsp+38h] [rbp-51h] BYREF
  struct _UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-49h] BYREF
  WCHAR *v16; // [rsp+50h] [rbp-39h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v18[32]; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v2 = a2;
  v16 = (WCHAR *)a1;
  windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, (_DWORD)a2, 64, 0, 0);
  SymbolicLinkHandle = 0;
  v4 = NtOpenSymbolicLinkObject(&SymbolicLinkHandle, 1u, &ObjectAttributes);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
      (const char *)(unsigned int)v4,
      v12);
  v5 = 260;
  DataWritten = 260;
  v16 = 0;
  LinkTarget = 0;
  v6 = 0;
  while ( 1 )
  {
    v8 = (WCHAR *)operator new[](v5);
    v16 = v8;
    if ( v6 )
      operator delete(v6, v7);
    *(_QWORD *)&LinkTarget.Length = 0;
    LinkTarget.MaximumLength = DataWritten;
    LinkTarget.Buffer = v8;
    v9 = NtQuerySymbolicLinkObject(SymbolicLinkHandle, &LinkTarget, &DataWritten);
    v6 = v8;
    if ( v9 != -1073741789 )
      break;
    v5 = DataWritten;
  }
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const char **)v2;
  wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
    retaddr,
    (void *)0x23D,
    (unsigned int)"onecore\\base\\gendrv\\silos\\container\\ob_provider.cpp",
    (const char *)v9,
    (int)"QuerySymbolicLinkObject(%ws) failed",
    v2);
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a1);
  operator delete(v8, v10);
  if ( (char *)SymbolicLinkHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(SymbolicLinkHandle);
  std::wstring::~wstring(v18);
  return a1;
}

```

## disassembly

```asm
0x180026c2c  mov     [rsp-8+arg_10], rbx
0x180026c31  mov     [rsp-8+arg_18], rsi
0x180026c36  push    rbp
0x180026c37  push    rdi
0x180026c38  push    r14
0x180026c3a  lea     rbp, [rsp-47h]
0x180026c3f  sub     rsp, 0D0h
0x180026c46  mov     rax, cs:__security_cookie
0x180026c4d  xor     rax, rsp
0x180026c50  mov     [rbp+57h+var_20], rax
0x180026c54  mov     rbx, rdx
0x180026c57  mov     r14, rcx
0x180026c5a  mov     [rbp+57h+var_90], rcx
0x180026c5e  mov     qword ptr [rsp+0E0h+var_C0], 0; int
0x180026c67  xor     r9d, r9d
0x180026c6a  lea     r8d, [r9+40h]
0x180026c6e  lea     rcx, [rbp+57h+ObjectAttributes]
0x180026c72  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x180026c77  nop
0x180026c78  mov     [rbp+57h+SymbolicLinkHandle], 0
0x180026c80  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180026c84  mov     edx, 1; DesiredAccess
0x180026c89  lea     rcx, [rbp+57h+SymbolicLinkHandle]; SymbolicLinkHandle
0x180026c8d  call    cs:__imp_NtOpenSymbolicLinkObject
0x180026c94  nop     dword ptr [rax+rax+00h]
0x180026c99  mov     rcx, [rbp+5Fh]; this
0x180026c9d  test    eax, eax
0x180026c9f  js      loc_180026DC7
0x180026ca5  mov     eax, 104h
0x180026caa  mov     [rbp+57h+DataWritten], eax
0x180026cad  mov     [rbp+57h+var_90], 0
0x180026cb5  xorps   xmm0, xmm0
0x180026cb8  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x180026cbc  xor     edi, edi
0x180026cbe  mov     ecx, eax; unsigned __int64
0x180026cc0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180026cc5  mov     rsi, rax
0x180026cc8  mov     [rbp+57h+var_90], rax
0x180026ccc  test    rdi, rdi
0x180026ccf  jz      short loc_180026CD9
0x180026cd1  mov     rcx, rdi; void *
0x180026cd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026cd9  xorps   xmm0, xmm0
0x180026cdc  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x180026ce0  movzx   eax, word ptr [rbp+57h+DataWritten]
0x180026ce4  mov     [rbp+57h+LinkTarget.MaximumLength], ax
0x180026ce8  mov     [rbp+57h+LinkTarget.Buffer], rsi
0x180026cec  lea     r8, [rbp+57h+DataWritten]; DataWritten
0x180026cf0  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x180026cf4  mov     rcx, [rbp+57h+SymbolicLinkHandle]; SymLinkObjHandle
0x180026cf8  call    cs:__imp_NtQuerySymbolicLinkObject
0x180026cff  nop     dword ptr [rax+rax+00h]
0x180026d04  mov     rdi, rsi
0x180026d07  cmp     eax, 0C0000023h
0x180026d0c  jnz     short loc_180026D13
0x180026d0e  mov     eax, [rbp+57h+DataWritten]
0x180026d11  jmp     short loc_180026CBE
0x180026d13  cmp     qword ptr [rbx+18h], 7
0x180026d18  jbe     short loc_180026D1D
0x180026d1a  mov     rbx, [rbx]
0x180026d1d  mov     rcx, [rbp+5Fh]; this
0x180026d21  mov     [rsp+0E0h+var_B8], rbx; char *
0x180026d26  lea     rdx, aQuerysymbolicl; "QuerySymbolicLinkObject(%ws) failed"
0x180026d2d  mov     qword ptr [rsp+0E0h+var_C0], rdx; int
0x180026d32  mov     r9d, eax; char *
0x180026d35  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026d3c  mov     edx, 23Dh; void *
0x180026d41  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180026d46  xorps   xmm0, xmm0
0x180026d49  movups  xmmword ptr [r14], xmm0
0x180026d4d  mov     qword ptr [r14+10h], 0
0x180026d55  mov     qword ptr [r14+18h], 0
0x180026d5d  movzx   r8d, [rbp+57h+LinkTarget.Length]
0x180026d62  shr     r8, 1
0x180026d65  mov     rdx, [rbp+57h+LinkTarget.Buffer]
0x180026d69  mov     rcx, r14
0x180026d6c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180026d71  nop
0x180026d72  mov     rcx, rsi; void *
0x180026d75  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026d7a  nop
0x180026d7b  mov     rcx, [rbp+57h+SymbolicLinkHandle]; hObject
0x180026d7f  lea     rdx, [rcx-1]
0x180026d83  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180026d87  ja      short loc_180026D96
0x180026d89  call    cs:__imp_CloseHandle
0x180026d90  nop     dword ptr [rax+rax+00h]
0x180026d95  nop
0x180026d96  lea     rcx, [rbp+57h+var_40]
0x180026d9a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026d9f  mov     rax, r14
0x180026da2  mov     rcx, [rbp+57h+var_20]
0x180026da6  xor     rcx, rsp; StackCookie
0x180026da9  call    __security_check_cookie
0x180026dae  lea     r11, [rsp+0E0h+var_10]
0x180026db6  mov     rbx, [r11+30h]
0x180026dba  mov     rsi, [r11+38h]
0x180026dbe  mov     rsp, r11
0x180026dc1  pop     r14
0x180026dc3  pop     rdi
0x180026dc4  pop     rbp
0x180026dc5  retn
0x180026dc7  mov     r9d, eax; char *
0x180026dca  lea     r8, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\container"...
0x180026dd1  mov     edx, 224h; void *
0x180026dd6  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
