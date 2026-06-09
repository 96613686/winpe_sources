# CMDMPushConfiguration::SaveToRegistry(ushort const *,tagVARIANT)

- ea: `0x18002da58`
- end: `0x18002dc0b`
- name: `?SaveToRegistry@CMDMPushConfiguration@@AEAAJPEBGUtagVARIANT@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d998`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000bab4`
- `0x18000c63c`
- `0x18001cc68`
- `0x18002da58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dbc3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002dbc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002db9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dbde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002db67`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002da95`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002da95`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002db32`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18002db32`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::SaveToRegistry(
        CMDMPushConfiguration *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rcx
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rdx
  UINT cbData; // ebx
  OLECHAR *bstrVal; // rdi
  DWORD v13; // esi
  unsigned int v14; // eax
  __int64 v15; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v3 = *((_QWORD *)this + 1);
  memset_0(SubKey, 0, 0x208u);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v5);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &word_1800401D0;
  v8 = StringCchPrintfW(SubKey, 0x104u, L"%sSoftware\\Microsoft\\Enrollments\\%s\\Push", v7, v3);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = 808;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)v8);
    return v8;
  }
  cbData = 8;
  switch ( a3->vt )
  {
    case 8u:
      bstrVal = a3->bstrVal;
      cbData = SysStringByteLen(bstrVal);
      v13 = 1;
      break;
    case 0x13u:
      bstrVal = &a3->uiVal;
      cbData = 4;
      v13 = 4;
      break;
    case 0x15u:
      bstrVal = &a3->uiVal;
      v13 = 11;
      break;
    default:
      v8 = -2147418113;
      v9 = 834;
      goto LABEL_5;
  }
  hKey = 0;
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  if ( v14 )
  {
    v15 = 843;
    goto LABEL_16;
  }
  v14 = RegSetValueExW(hKey, L"Status", 0, v13, (const BYTE *)bstrVal, cbData);
  if ( v14 )
  {
    v15 = 851;
LABEL_16:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v15,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
           (const char *)v14,
           phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002da58  mov     [rsp+arg_8], rbx
0x18002da5d  mov     [rsp+arg_18], rsi
0x18002da62  push    rdi
0x18002da63  sub     rsp, 260h
0x18002da6a  mov     rax, cs:__security_cookie
0x18002da71  xor     rax, rsp
0x18002da74  mov     [rsp+268h+var_18], rax
0x18002da7c  mov     rbx, [rcx+8]
0x18002da80  mov     rdi, r8
0x18002da83  mov     r8d, 208h; Size
0x18002da89  lea     rcx, [rsp+268h+SubKey]; void *
0x18002da8e  xor     edx, edx; Val
0x18002da90  call    memset_0
0x18002da95  call    cs:__imp_RtlIsStateSeparationEnabled
0x18002da9b  lea     rcx, word_1800401D0
0x18002daa2  mov     [rsp+268h+phkResult], rbx; int
0x18002daa7  test    al, al
0x18002daa9  lea     r9, aOsdata; "OSData\\"
0x18002dab0  lea     r8, aSsoftwareMicro; "%sSoftware\\Microsoft\\Enrollments\\%s"...
0x18002dab7  mov     edx, 104h; unsigned __int64
0x18002dabc  cmovz   r9, rcx
0x18002dac0  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18002dac5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002daca  mov     ebx, eax
0x18002dacc  test    eax, eax
0x18002dace  jns     short loc_18002DAF3
0x18002dad0  mov     edx, 328h; void *
0x18002dad5  mov     rcx, [rsp+268h]; this
0x18002dadd  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002dae4  mov     r9d, ebx; char *
0x18002dae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002daec  mov     eax, ebx
0x18002daee  jmp     loc_18002DBE6
0x18002daf3  mov     ebx, 8
0x18002daf8  cmp     [rdi], bx
0x18002dafb  jz      short loc_18002DB2B
0x18002dafd  cmp     word ptr [rdi], 13h
0x18002db01  jz      short loc_18002DB1F
0x18002db03  cmp     word ptr [rdi], 15h
0x18002db07  jz      short loc_18002DB15
0x18002db09  mov     ebx, 8000FFFFh
0x18002db0e  mov     edx, 342h
0x18002db13  jmp     short loc_18002DAD5
0x18002db15  add     rdi, rbx
0x18002db18  mov     esi, 0Bh
0x18002db1d  jmp     short loc_18002DB3F
0x18002db1f  add     rdi, rbx
0x18002db22  mov     ebx, 4
0x18002db27  mov     esi, ebx
0x18002db29  jmp     short loc_18002DB3F
0x18002db2b  mov     rdi, [rdi+8]
0x18002db2f  mov     rcx, rdi; bstr
0x18002db32  call    cs:__imp_SysStringByteLen
0x18002db38  mov     ebx, eax
0x18002db3a  mov     esi, 1
0x18002db3f  lea     rax, [rsp+268h+hKey]
0x18002db44  mov     [rsp+268h+hKey], 0
0x18002db4d  mov     r9d, 0F003Fh; samDesired
0x18002db53  mov     [rsp+268h+phkResult], rax; unsigned int
0x18002db58  xor     r8d, r8d; ulOptions
0x18002db5b  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002db60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002db67  call    cs:__imp_RegOpenKeyExW
0x18002db6d  test    eax, eax
0x18002db6f  jz      short loc_18002DBA8
0x18002db71  mov     edx, 34Bh; void *
0x18002db76  mov     rcx, [rsp+268h]; this
0x18002db7e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x18002db85  mov     r9d, eax; char *
0x18002db88  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002db8d  mov     rcx, [rsp+268h+hKey]; hKey
0x18002db92  mov     ebx, eax
0x18002db94  test    rcx, rcx
0x18002db97  jz      loc_18002DAEC
0x18002db9d  call    cs:__imp_RegCloseKey
0x18002dba3  jmp     loc_18002DAEC
0x18002dba8  mov     rcx, [rsp+268h+hKey]; hKey
0x18002dbad  lea     rdx, aStatus; "Status"
0x18002dbb4  mov     [rsp+268h+cbData], ebx; cbData
0x18002dbb8  mov     r9d, esi; dwType
0x18002dbbb  xor     r8d, r8d; Reserved
0x18002dbbe  mov     [rsp+268h+phkResult], rdi; lpData
0x18002dbc3  call    cs:__imp_RegSetValueExW
0x18002dbc9  test    eax, eax
0x18002dbcb  jz      short loc_18002DBD4
0x18002dbcd  mov     edx, 353h
0x18002dbd2  jmp     short loc_18002DB76
0x18002dbd4  mov     rcx, [rsp+268h+hKey]; hKey
0x18002dbd9  test    rcx, rcx
0x18002dbdc  jz      short loc_18002DBE4
0x18002dbde  call    cs:__imp_RegCloseKey
0x18002dbe4  xor     eax, eax
0x18002dbe6  mov     rcx, [rsp+268h+var_18]
0x18002dbee  xor     rcx, rsp; StackCookie
0x18002dbf1  call    __security_check_cookie
0x18002dbf6  lea     r11, [rsp+268h+var_8]
0x18002dbfe  mov     rbx, [r11+18h]
0x18002dc02  mov     rsi, [r11+28h]
0x18002dc06  mov     rsp, r11
0x18002dc09  pop     rdi
0x18002dc0a  retn
```
