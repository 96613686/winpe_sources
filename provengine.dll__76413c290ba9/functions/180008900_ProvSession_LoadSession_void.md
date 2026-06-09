# ProvSession::LoadSession(void)

- ea: `0x180008900`
- end: `0x180008a7e`
- name: `?LoadSession@ProvSession@@UEAAJXZ`
- size: `382`
- prototype: `int __fastcall(ProvSession *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800010c8`
- `0x180008900`
- `0x180008a84`
- `0x1800092dc`
- `0x1800098dc`
- `0x180009900`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008a3a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008a3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008969`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008969`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000895e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000895e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ProvSession::LoadSession(ProvSession *this)
{
  HKEY v2; // rsi
  DWORD LastError; // ebx
  bool IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  int result; // eax
  signed int SessionRegistry; // ebx
  __int64 v9; // rdx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-68h]
  BYTE Data[4]; // [rsp+30h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-54h] BYREF
  _BYTE v15[32]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_18004E242, 0, 0, 2, v15);
  v2 = (HKEY)*((_QWORD *)this + 11);
  if ( v2 )
  {
    LastError = GetLastError();
    RegCloseKey(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 11) = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v5 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Sessions";
  if ( !IsStateSeparationEnabled )
    v5 = L"SOFTWARE\\Microsoft\\Provisioning\\Sessions";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0xFu, (PHKEY)this + 11);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x70,
             (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
             (const char *)v6,
             phkResult);
  SessionRegistry = ProvSession::LoadSessionRegistry(this);
  if ( SessionRegistry < 0 )
  {
    v9 = 114;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provsession.cpp",
      (const char *)(unsigned int)SessionRegistry,
      phkResult);
    return SessionRegistry;
  }
  v10 = (HKEY)*((_QWORD *)this + 12);
  *(_DWORD *)Data = 0;
  cbData = 4;
  v11 = RegQueryValueExW(v10, L"StateValue", 0, 0, Data, &cbData);
  SessionRegistry = v11;
  if ( v11 > 0 )
    SessionRegistry = (unsigned __int16)v11 | 0x80070000;
  if ( SessionRegistry < 0 )
  {
    v9 = 117;
    goto LABEL_11;
  }
  *((_DWORD *)this + 5) = *(_DWORD *)Data;
  result = 0;
  *((_BYTE *)this + 112) = 1;
  return result;
}

```

## disassembly

```asm
0x180008900  push    rbx
0x180008902  push    rsi
0x180008903  push    rdi
0x180008904  push    r14
0x180008906  sub     rsp, 68h
0x18000890a  mov     rax, cs:__security_cookie
0x180008911  xor     rax, rsp
0x180008914  mov     [rsp+88h+var_30], rax
0x180008919  mov     eax, cs:dword_18005A000
0x18000891f  mov     rdi, rcx
0x180008922  cmp     eax, 4
0x180008925  jbe     short loc_180008952
0x180008927  lea     rax, [rsp+88h+var_50]
0x18000892c  xor     r9d, r9d
0x18000892f  mov     [rsp+88h+lpcbData], rax
0x180008934  lea     rdx, word_18004E242
0x18000893b  xor     r8d, r8d
0x18000893e  mov     dword ptr [rsp+88h+phkResult], 2
0x180008946  lea     rcx, dword_18005A000
0x18000894d  call    _tlgWriteTransfer_EventWriteTransfer
0x180008952  lea     r14, [rdi+58h]
0x180008956  mov     rsi, [r14]
0x180008959  test    rsi, rsi
0x18000895c  jz      short loc_180008977
0x18000895e  call    cs:__imp_GetLastError
0x180008964  mov     rcx, rsi; hKey
0x180008967  mov     ebx, eax
0x180008969  call    cs:__imp_RegCloseKey
0x18000896f  mov     ecx, ebx; dwErrCode
0x180008971  call    cs:__imp_SetLastError
0x180008977  mov     qword ptr [r14], 0
0x18000897e  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180008983  test    al, al
0x180008985  mov     [rsp+88h+phkResult], r14; int
0x18000898a  lea     rcx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\Provisioning\\Sess"...
0x180008991  mov     r9d, 0Fh; samDesired
0x180008997  lea     rdx, aOsdataSoftware_12; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x18000899e  cmovz   rdx, rcx; lpSubKey
0x1800089a2  xor     r8d, r8d; ulOptions
0x1800089a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800089ac  call    cs:__imp_RegOpenKeyExW
0x1800089b2  test    eax, eax
0x1800089b4  jz      short loc_1800089D7
0x1800089b6  mov     rcx, [rsp+88h]; this
0x1800089be  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800089c5  mov     r9d, eax; char *
0x1800089c8  mov     edx, 70h ; 'p'; void *
0x1800089cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800089d2  jmp     loc_180008A67
0x1800089d7  mov     rcx, rdi; this
0x1800089da  call    ?LoadSessionRegistry@ProvSession@@AEAAJXZ; ProvSession::LoadSessionRegistry(void)
0x1800089df  mov     ebx, eax
0x1800089e1  test    eax, eax
0x1800089e3  jns     short loc_180008A05
0x1800089e5  mov     edx, 72h ; 'r'; void *
0x1800089ea  mov     rcx, [rsp+88h]; this
0x1800089f2  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800089f9  mov     r9d, ebx; char *
0x1800089fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a01  mov     eax, ebx
0x180008a03  jmp     short loc_180008A67
0x180008a05  mov     rcx, [rdi+60h]; hKey
0x180008a09  lea     rax, [rsp+88h+cbData]
0x180008a0e  mov     [rsp+88h+lpcbData], rax; lpcbData
0x180008a13  lea     rdx, ValueName; "StateValue"
0x180008a1a  lea     rax, [rsp+88h+Data]
0x180008a1f  mov     dword ptr [rsp+88h+Data], 0
0x180008a27  xor     r9d, r9d; lpType
0x180008a2a  mov     [rsp+88h+phkResult], rax; lpData
0x180008a2f  xor     r8d, r8d; lpReserved
0x180008a32  mov     [rsp+88h+cbData], 4
0x180008a3a  call    cs:__imp_RegQueryValueExW
0x180008a40  mov     ebx, eax
0x180008a42  test    eax, eax
0x180008a44  jle     short loc_180008A4F
0x180008a46  movzx   ebx, ax
0x180008a49  or      ebx, 80070000h
0x180008a4f  test    ebx, ebx
0x180008a51  jns     short loc_180008A5A
0x180008a53  mov     edx, 75h ; 'u'
0x180008a58  jmp     short loc_1800089EA
0x180008a5a  mov     eax, dword ptr [rsp+88h+Data]
0x180008a5e  mov     [rdi+14h], eax
0x180008a61  xor     eax, eax
0x180008a63  mov     byte ptr [rdi+70h], 1
0x180008a67  mov     rcx, [rsp+88h+var_30]
0x180008a6c  xor     rcx, rsp; StackCookie
0x180008a6f  call    __security_check_cookie
0x180008a74  add     rsp, 68h
0x180008a78  pop     r14
0x180008a7a  pop     rdi
0x180008a7b  pop     rsi
0x180008a7c  pop     rbx
0x180008a7d  retn
```
