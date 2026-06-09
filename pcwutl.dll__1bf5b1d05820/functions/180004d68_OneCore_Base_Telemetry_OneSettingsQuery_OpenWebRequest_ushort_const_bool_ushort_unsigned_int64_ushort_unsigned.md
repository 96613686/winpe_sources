# OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)

- ea: `0x180004d68`
- end: `0x180004eeb`
- name: `?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z`
- size: `387`
- prototype: `__int64 __usercall@<rax>(void **this@<rcx>, const unsigned __int16 *@<rdx>, bool@<r8b>, unsigned __int16 *@<r9>, unsigned __int64, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180003388`

## callees

- `0x180002cc4`
- `0x180004d68`
- `0x180007170`
- `0x180007b54`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004dd5`
- `KERNEL32!GetLastError` at `0x180004dd5`
- `WINHTTP!WinHttpOpen` at `0x180004dc7`
- `WINHTTP!WinHttpOpen` at `0x180004dc7`
- `WINHTTP!WinHttpConnect` at `0x180004e03`
- `WINHTTP!WinHttpConnect` at `0x180004e03`
- `WINHTTP!WinHttpSetOption` at `0x180004e41`
- `WINHTTP!WinHttpSetOption` at `0x180004e41`
- `WINHTTP!WinHttpOpenRequest` at `0x180004eb3`
- `WINHTTP!WinHttpOpenRequest` at `0x180004eb3`

## string_xrefs

- `0x180004df6`: `settings-win.data.microsoft.com`

## pseudocode

```c
signed int __fastcall OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
        void **this,
        const unsigned __int16 *a2,
        char a3,
        unsigned __int16 *a4,
        unsigned __int64 a5,
        unsigned __int16 *a6)
{
  void *v9; // rax
  signed int result; // eax
  void *v11; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v12; // rcx
  const unsigned __int16 *v13; // r8
  void *v14; // rcx
  unsigned int v15; // r8d
  void *v16; // rax
  LPCWSTR *ppwszAcceptTypes; // [rsp+28h] [rbp-450h]
  int Buffer[4]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR pwszObjectName[512]; // [rsp+50h] [rbp-428h] BYREF

  memset_0(pwszObjectName, 0, sizeof(pwszObjectName));
  *a4 = 0;
  *a6 = 0;
  v9 = WinHttpOpen(L"OneSettingsQuery", 0, 0, 0, 0);
  *this = v9;
  if ( !v9
    || (v11 = WinHttpConnect(v9, L"settings-win.data.microsoft.com", 0x1BBu, 0), (this[1] = v11) == 0)
    || (OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(
          v12,
          this,
          v13,
          a3,
          a4,
          (unsigned __int64)ppwszAcceptTypes,
          a6),
        v14 = *this,
        Buffer[0] = 2048,
        !WinHttpSetOption(v14, 0x54u, Buffer, 4u)) )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringCchPrintfW(pwszObjectName, 0x200u, L"settings/v2.0/%ls/%ls", this + 5, this + 70);
  if ( result >= 0 )
  {
    result = OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(
               (OneCore::Base::Telemetry::OneSettingsQuery *)this,
               pwszObjectName,
               v15);
    if ( result >= 0 )
    {
      v16 = WinHttpOpenRequest(this[1], L"GET", pwszObjectName, 0, 0, 0, 0x800000u);
      this[2] = v16;
      if ( v16 )
        return 0;
      goto LABEL_2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004d68  mov     [rsp+arg_8], rbx
0x180004d6d  push    rbp
0x180004d6e  push    rsi
0x180004d6f  push    rdi
0x180004d70  sub     rsp, 460h
0x180004d77  mov     rax, cs:__security_cookie
0x180004d7e  xor     rax, rsp
0x180004d81  mov     [rsp+478h+var_28], rax
0x180004d89  mov     rsi, [rsp+478h+arg_28]
0x180004d91  mov     bpl, r8b
0x180004d94  mov     rbx, rcx
0x180004d97  mov     r8d, 400h; Size
0x180004d9d  lea     rcx, [rsp+478h+pwszObjectName]; void *
0x180004da2  xor     edx, edx; Val
0x180004da4  mov     rdi, r9
0x180004da7  call    memset_0
0x180004dac  xor     eax, eax
0x180004dae  lea     rcx, pszAgentW; "OneSettingsQuery"
0x180004db5  mov     [rdi], ax
0x180004db8  xor     r9d, r9d; pszProxyBypassW
0x180004dbb  xor     r8d, r8d; pszProxyW
0x180004dbe  mov     [rsi], ax
0x180004dc1  xor     edx, edx; dwAccessType
0x180004dc3  mov     [rsp+478h+dwFlags], eax; dwFlags
0x180004dc7  call    cs:__imp_WinHttpOpen
0x180004dcd  mov     [rbx], rax
0x180004dd0  test    rax, rax
0x180004dd3  jnz     short loc_180004DF0
0x180004dd5  call    cs:__imp_GetLastError
0x180004ddb  test    eax, eax
0x180004ddd  jle     loc_180004EC8
0x180004de3  movzx   eax, ax
0x180004de6  or      eax, 80070000h
0x180004deb  jmp     loc_180004EC8
0x180004df0  mov     r8d, 1BBh; nServerPort
0x180004df6  lea     rdx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x180004dfd  xor     r9d, r9d; dwReserved
0x180004e00  mov     rcx, rax; hSession
0x180004e03  call    cs:__imp_WinHttpConnect
0x180004e09  mov     [rbx+8], rax
0x180004e0d  test    rax, rax
0x180004e10  jz      short loc_180004DD5
0x180004e12  mov     qword ptr [rsp+478h+var_448], rsi; unsigned __int16 *
0x180004e17  mov     r9b, bpl; bool
0x180004e1a  mov     rdx, rbx; void **
0x180004e1d  mov     qword ptr [rsp+478h+dwFlags], rdi; unsigned __int16 *
0x180004e22  call    ?SetUserProxyInfoAndGetCredentials@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEAPEAXPEBG_NPEAG_K34@Z; OneCore::Base::Telemetry::OneSettingsQuery::SetUserProxyInfoAndGetCredentials(void * &,ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180004e27  mov     rcx, [rbx]; hInternet
0x180004e2a  lea     r8, [rsp+478h+Buffer]; lpBuffer
0x180004e2f  mov     r9d, 4; dwBufferLength
0x180004e35  mov     [rsp+478h+Buffer], 800h
0x180004e3d  lea     edx, [r9+50h]; dwOption
0x180004e41  call    cs:__imp_WinHttpSetOption
0x180004e47  test    eax, eax
0x180004e49  jz      short loc_180004DD5
0x180004e4b  lea     rax, [rbx+230h]
0x180004e52  mov     edx, 200h; unsigned __int64
0x180004e57  lea     r9, [rbx+28h]
0x180004e5b  mov     qword ptr [rsp+478h+dwFlags], rax
0x180004e60  lea     r8, aSettingsV20LsL; "settings/v2.0/%ls/%ls"
0x180004e67  lea     rcx, [rsp+478h+pwszObjectName]; unsigned __int16 *
0x180004e6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004e71  test    eax, eax
0x180004e73  js      short loc_180004EC8
0x180004e75  lea     rdx, [rsp+478h+pwszObjectName]; unsigned __int16 *
0x180004e7a  mov     rcx, rbx; this
0x180004e7d  call    ?AppendQueryString@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::AppendQueryString(ushort *,ulong)
0x180004e82  test    eax, eax
0x180004e84  js      short loc_180004EC8
0x180004e86  mov     rcx, [rbx+8]; hConnect
0x180004e8a  lea     r8, [rsp+478h+pwszObjectName]; pwszObjectName
0x180004e8f  mov     [rsp+478h+var_448], 800000h; dwFlags
0x180004e97  lea     rdx, pwszVerb; "GET"
0x180004e9e  mov     [rsp+478h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180004ea7  xor     r9d, r9d; pwszVersion
0x180004eaa  mov     qword ptr [rsp+478h+dwFlags], 0; pwszReferrer
0x180004eb3  call    cs:__imp_WinHttpOpenRequest
0x180004eb9  mov     [rbx+10h], rax
0x180004ebd  test    rax, rax
0x180004ec0  jz      loc_180004DD5
0x180004ec6  xor     eax, eax
0x180004ec8  mov     rcx, [rsp+478h+var_28]
0x180004ed0  xor     rcx, rsp; StackCookie
0x180004ed3  call    __security_check_cookie
0x180004ed8  mov     rbx, [rsp+478h+arg_8]
0x180004ee0  add     rsp, 460h
0x180004ee7  pop     rdi
0x180004ee8  pop     rsi
0x180004ee9  pop     rbp
0x180004eea  retn
```
