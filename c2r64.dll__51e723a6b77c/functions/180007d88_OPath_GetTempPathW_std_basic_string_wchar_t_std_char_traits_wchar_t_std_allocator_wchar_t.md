# OPath::GetTempPathW(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180007d88`
- end: `0x180007e3b`
- name: `?GetTempPathW@OPath@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180004660`
- `0x180019848`

## callees

- `0x180006074`
- `0x180007700`
- `0x180007d88`
- `0x180007ffc`
- `0x18003e690`
- `0x1800409e0`
- `0x18004a3dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007e0a`
- `KERNEL32!GetLastError` at `0x180007e0a`
- `KERNEL32!GetTempPathW` at `0x180007dd2`
- `KERNEL32!GetTempPathW` at `0x180007dd2`

## string_xrefs

- `0x180007e10`: `Cannot get temp path`

## pseudocode

```c
__int64 __fastcall OPath::GetTempPathW(__int64 a1)
{
  WCHAR *v2; // rbx
  DWORD v3; // eax
  DWORD TempPathW; // eax
  DWORD LastError; // eax
  _BYTE pExceptionObject[912]; // [rsp+20h] [rbp-3A8h] BYREF

  std::wstring::resize(a1, 260, 0);
  v2 = (WCHAR *)std::wstring::operator[](a1, 0);
  v3 = OcfxDwordFromSize_t(*(_QWORD *)(a1 + 24));
  TempPathW = GetTempPathW(v3, v2);
  if ( !TempPathW )
  {
    LastError = GetLastError();
    OException::OException(pExceptionObject, 15, LastError, L"Cannot get temp path");
    throw (OException *)pExceptionObject;
  }
  return std::wstring::resize(a1, TempPathW, 0);
}

```

## disassembly

```asm
0x180007d88  mov     [rsp+arg_8], rbx
0x180007d8d  push    rdi
0x180007d8e  sub     rsp, 3C0h
0x180007d95  mov     rax, cs:__security_cookie
0x180007d9c  xor     rax, rsp
0x180007d9f  mov     [rsp+3C8h+var_18], rax
0x180007da7  xor     r8d, r8d
0x180007daa  mov     edx, 104h
0x180007daf  mov     rdi, rcx
0x180007db2  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180007db7  xor     edx, edx
0x180007db9  mov     rcx, rdi
0x180007dbc  call    ??A?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEA_W_K@Z; std::wstring::operator[](unsigned __int64)
0x180007dc1  mov     rcx, [rdi+18h]; unsigned __int64
0x180007dc5  mov     rbx, rax
0x180007dc8  call    ?OcfxDwordFromSize_t@@YAK_K@Z; OcfxDwordFromSize_t(unsigned __int64)
0x180007dcd  mov     rdx, rbx; lpBuffer
0x180007dd0  mov     ecx, eax; nBufferLength
0x180007dd2  call    cs:__imp_GetTempPathW
0x180007dd8  mov     edx, eax
0x180007dda  test    eax, eax
0x180007ddc  jz      short loc_180007E0A
0x180007dde  xor     r8d, r8d
0x180007de1  mov     rcx, rdi
0x180007de4  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180007de9  mov     rcx, [rsp+3C8h+var_18]
0x180007df1  xor     rcx, rsp; StackCookie
0x180007df4  call    __security_check_cookie
0x180007df9  mov     rbx, [rsp+3C8h+arg_8]
0x180007e01  add     rsp, 3C0h
0x180007e08  pop     rdi
0x180007e09  retn
0x180007e0a  call    cs:__imp_GetLastError
0x180007e10  lea     r9, aCannotGetTempP; "Cannot get temp path"
0x180007e17  mov     edx, 0Fh
0x180007e1c  mov     r8d, eax
0x180007e1f  lea     rcx, [rsp+3C8h+pExceptionObject]
0x180007e24  call    ??$?0$0BF@@OException@@QEAA@W4exceptionType@et@@IAEAY0BF@$$CB_W@Z; OException::OException(et::exceptionType,uint,wchar_t const (&)[21])
0x180007e29  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180007e30  lea     rcx, [rsp+3C8h+pExceptionObject]; pExceptionObject
0x180007e35  call    _CxxThrowException
```
