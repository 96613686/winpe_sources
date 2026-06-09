# CAppRecorderPlugin::IsAppRecorderEnabled(ulong)

- ea: `0x18002f660`
- end: `0x18002f791`
- name: `?IsAppRecorderEnabled@CAppRecorderPlugin@@AEAAJK@Z`
- size: `305`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f060`

## callees

- `0x1800028b4`
- `0x180006b50`
- `0x180009f00`
- `0x18002f660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002f6ef`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18002f6ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f779`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f779`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f73e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f73e`

## string_xrefs

- `0x18002f72e`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::IsAppRecorderEnabled(CAppRecorderPlugin *this, unsigned int a2)
{
  int v3; // edi
  char *v4; // rbx
  LPCWSTR lpName[2]; // [rsp+40h] [rbp-20h] BYREF
  _WORD v7[8]; // [rsp+50h] [rbp-10h] BYREF
  int pvData; // [rsp+80h] [rbp+20h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+30h] BYREF

  pcbData = 4;
  lpName[0] = v7;
  lpName[1] = v7;
  *((_QWORD *)this + 7) = 0;
  v7[0] = 0;
  pvData = 0;
  v3 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         (__int64)lpName,
         (__int64)L"%d-AppRecorderEnabled",
         a2);
  if ( v3 >= 0 )
  {
    v4 = (char *)OpenEventW(0x100000u, 0, lpName[0]);
    if ( v4 != (char *)-1LL && v4 + 1 != (char *)1 )
      *((_DWORD *)this + 14) = 1;
    if ( !RegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder",
            L"AppRecorderEnabled",
            0x18u,
            0,
            &pvData,
            &pcbData) )
      *((_DWORD *)this + 15) = pvData != 0;
    v3 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
        (unsigned int)v3);
    v4 = 0;
  }
  if ( lpName[0] != v7 )
    operator delete((void *)lpName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (unsigned __int64)(v4 + 1) > 1 )
    CloseHandle(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002f660  mov     [rsp-18h+arg_8], rbx
0x18002f665  push    rbp
0x18002f666  push    rsi
0x18002f667  push    rdi
0x18002f668  mov     rbp, rsp
0x18002f66b  sub     rsp, 60h
0x18002f66f  lea     rax, [rbp+var_10]
0x18002f673  mov     [rbp+arg_10], 4
0x18002f67a  mov     [rbp+lpName], rax
0x18002f67e  mov     rsi, rcx
0x18002f681  lea     rax, [rbp+var_10]
0x18002f685  mov     r8d, edx
0x18002f688  mov     [rbp+var_18], rax
0x18002f68c  lea     rdx, aDApprecorderen; "%d-AppRecorderEnabled"
0x18002f693  xor     eax, eax
0x18002f695  mov     [rcx+38h], rax
0x18002f699  lea     rcx, [rbp+lpName]
0x18002f69d  mov     [rbp+var_10], ax
0x18002f6a1  mov     [rbp+arg_0], eax
0x18002f6a4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002f6a9  mov     edi, eax
0x18002f6ab  test    eax, eax
0x18002f6ad  jns     short loc_18002F6E4
0x18002f6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6b6  lea     rax, WPP_GLOBAL_Control
0x18002f6bd  cmp     rcx, rax
0x18002f6c0  jz      short loc_18002F6E0
0x18002f6c2  test    byte ptr [rcx+1Ch], 1
0x18002f6c6  jz      short loc_18002F6E0
0x18002f6c8  mov     rcx, [rcx+10h]
0x18002f6cc  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f6d3  mov     edx, 20h ; ' '
0x18002f6d8  mov     r9d, edi
0x18002f6db  call    WPP_SF_d
0x18002f6e0  xor     ebx, ebx
0x18002f6e2  jmp     short loc_18002F753
0x18002f6e4  mov     r8, [rbp+lpName]; lpName
0x18002f6e8  xor     edx, edx; bInheritHandle
0x18002f6ea  mov     ecx, 100000h; dwDesiredAccess
0x18002f6ef  call    cs:__imp_OpenEventW
0x18002f6f5  mov     rbx, rax
0x18002f6f8  inc     rax
0x18002f6fb  cmp     rax, 1
0x18002f6ff  jbe     short loc_18002F708
0x18002f701  mov     dword ptr [rsi+38h], 1
0x18002f708  lea     rax, [rbp+arg_10]
0x18002f70c  mov     r9d, 18h; dwFlags
0x18002f712  mov     [rsp+60h+pcbData], rax; pcbData
0x18002f717  lea     r8, aApprecorderena; "AppRecorderEnabled"
0x18002f71e  lea     rax, [rbp+arg_0]
0x18002f722  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002f729  mov     [rsp+60h+pvData], rax; pvData
0x18002f72e  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\Windows E"...
0x18002f735  mov     [rsp+60h+pdwType], 0; pdwType
0x18002f73e  call    cs:__imp_RegGetValueW
0x18002f744  test    eax, eax
0x18002f746  jnz     short loc_18002F751
0x18002f748  cmp     [rbp+arg_0], eax
0x18002f74b  setnz   al
0x18002f74e  mov     [rsi+3Ch], eax
0x18002f751  xor     edi, edi
0x18002f753  mov     rcx, [rbp+lpName]; void *
0x18002f757  lea     rax, [rbp+var_10]
0x18002f75b  cmp     rcx, rax
0x18002f75e  jz      short loc_18002F76C
0x18002f760  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002f767  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f76c  lea     rax, [rbx+1]
0x18002f770  cmp     rax, 1
0x18002f774  jbe     short loc_18002F77F
0x18002f776  mov     rcx, rbx; hObject
0x18002f779  call    cs:__imp_CloseHandle
0x18002f77f  mov     rbx, [rsp+60h+arg_8]
0x18002f787  mov     eax, edi
0x18002f789  add     rsp, 60h
0x18002f78d  pop     rdi
0x18002f78e  pop     rsi
0x18002f78f  pop     rbp
0x18002f790  retn
```
