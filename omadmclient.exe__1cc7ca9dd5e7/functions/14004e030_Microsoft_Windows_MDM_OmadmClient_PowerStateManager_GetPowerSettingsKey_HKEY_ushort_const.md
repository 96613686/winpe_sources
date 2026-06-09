# Microsoft::Windows::MDM::OmadmClient::PowerStateManager::GetPowerSettingsKey(HKEY__ * *,ushort const *)

- ea: `0x14004e030`
- end: `0x14004e148`
- name: `?GetPowerSettingsKey@PowerStateManager@OmadmClient@MDM@Windows@Microsoft@@AEAAJPEAPEAUHKEY__@@PEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::PowerStateManager *__hidden this, HKEY *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004df2c`
- `0x14004e2a4`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000b0f4`
- `0x14000bf50`
- `0x14004e030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004e0e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14004e0e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e107`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14004e107`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::PowerStateManager::GetPowerSettingsKey(
        Microsoft::Windows::MDM::OmadmClient::PowerStateManager *this,
        HKEY *a2,
        const unsigned __int16 *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  LSTATUS v8; // eax
  int phkResult; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  if ( !a3 || !a2 )
    return 2147942487LL;
  memset_0(SubKey, 0, 0x208u);
  v5 = StringCchPrintfW(SubKey, 0x104u, qword_140085148, a3);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\powerstatemanager.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    return v6;
  }
  hKey = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  *a2 = hKey;
  return 0;
}

```

## disassembly

```asm
0x14004e030  mov     [rsp+arg_0], rbx
0x14004e035  push    rdi
0x14004e036  sub     rsp, 260h
0x14004e03d  mov     rax, cs:__security_cookie
0x14004e044  xor     rax, rsp
0x14004e047  mov     [rsp+268h+var_18], rax
0x14004e04f  mov     rbx, r8
0x14004e052  mov     rdi, rdx
0x14004e055  test    r8, r8
0x14004e058  jz      loc_14004E121
0x14004e05e  test    rdx, rdx
0x14004e061  jz      loc_14004E121
0x14004e067  xor     edx, edx; Val
0x14004e069  lea     rcx, [rsp+268h+SubKey]; void *
0x14004e06e  mov     r8d, 208h; Size
0x14004e074  call    memset_0
0x14004e079  mov     r8, cs:qword_140085148; unsigned __int16 *
0x14004e080  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x14004e085  mov     r9, rbx
0x14004e088  mov     edx, 104h; unsigned __int64
0x14004e08d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14004e092  mov     ebx, eax
0x14004e094  test    eax, eax
0x14004e096  jns     short loc_14004E0B8
0x14004e098  mov     rcx, [rsp+268h]; this
0x14004e0a0  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004e0a7  mov     r9d, eax; char *
0x14004e0aa  mov     edx, 169h; void *
0x14004e0af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004e0b4  mov     eax, ebx
0x14004e0b6  jmp     short loc_14004E126
0x14004e0b8  lea     rax, [rsp+268h+hKey]
0x14004e0bd  mov     [rsp+268h+hKey], 0
0x14004e0c6  mov     r9d, 0F003Fh; samDesired
0x14004e0cc  mov     qword ptr [rsp+268h+phkResult], rax; phkResult
0x14004e0d1  xor     r8d, r8d; ulOptions
0x14004e0d4  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x14004e0d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14004e0e0  call    cs:__imp_RegOpenKeyExW
0x14004e0e7  nop     dword ptr [rax+rax+00h]
0x14004e0ec  mov     ebx, eax
0x14004e0ee  test    eax, eax
0x14004e0f0  jz      short loc_14004E115
0x14004e0f2  jle     short loc_14004E0FD
0x14004e0f4  movzx   ebx, ax
0x14004e0f7  or      ebx, 80070000h
0x14004e0fd  mov     rcx, [rsp+268h+hKey]; hKey
0x14004e102  test    rcx, rcx
0x14004e105  jz      short loc_14004E0B4
0x14004e107  call    cs:__imp_RegCloseKey
0x14004e10e  nop     dword ptr [rax+rax+00h]
0x14004e113  jmp     short loc_14004E0B4
0x14004e115  mov     rax, [rsp+268h+hKey]
0x14004e11a  mov     [rdi], rax
0x14004e11d  xor     eax, eax
0x14004e11f  jmp     short loc_14004E126
0x14004e121  mov     eax, 80070057h
0x14004e126  mov     rcx, [rsp+268h+var_18]
0x14004e12e  xor     rcx, rsp; StackCookie
0x14004e131  call    __security_check_cookie
0x14004e136  mov     rbx, [rsp+268h+arg_0]
0x14004e13e  add     rsp, 260h
0x14004e145  pop     rdi
0x14004e146  retn
```
