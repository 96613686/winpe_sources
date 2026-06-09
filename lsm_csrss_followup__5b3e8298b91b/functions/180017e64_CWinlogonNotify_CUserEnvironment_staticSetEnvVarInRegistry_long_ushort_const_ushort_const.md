# CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry(long,ushort const *,ushort const *)

- ea: `0x180017e64`
- end: `0x180017fd3`
- name: `?staticSetEnvVarInRegistry@CUserEnvironment@CWinlogonNotify@@CAJJPEBG0@Z`
- size: `367`
- prototype: `static int(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017a50`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x180017e64`
- `0x180018200`
- `0x18002bb60`
- `0x18004b460`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017f9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017ee1`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180017ee1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017f25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017f25`

## string_xrefs

- `0x180017fbc`: `CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry`
- `0x180017fa9`: `RegEnv.CreateUserKey failed: 0x%x in %s`
- `0x180017fb2`: `RegEnv.WriteRegString failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry(
        unsigned int a1,
        const unsigned __int16 *a2,
        const BYTE *a3)
{
  __int64 v5; // rdi
  int v6; // eax
  int Key; // ebx
  unsigned int v8; // r9d
  bool v9; // sf
  LSTATUS v10; // eax
  const char *v12; // rdx
  unsigned int *lpData; // [rsp+20h] [rbp-79h]
  struct _SECURITY_ATTRIBUTES *cbData; // [rsp+28h] [rbp-71h]
  unsigned int v15; // [rsp+30h] [rbp-69h]
  HKEY phkResult; // [rsp+40h] [rbp-59h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-51h] BYREF
  int v18; // [rsp+58h] [rbp-41h]
  HKEY hKey; // [rsp+60h] [rbp-39h]
  int v20; // [rsp+68h] [rbp-31h]
  int v21; // [rsp+6Ch] [rbp-2Dh]
  unsigned __int16 v22[40]; // [rsp+70h] [rbp-29h] BYREF

  v17[0] = &CRegistry::`vftable';
  v17[1] = 0;
  v18 = 0;
  hKey = 0;
  v5 = -1;
  v20 = -1;
  v21 = -1;
  v6 = StringCchPrintfW(v22, 0x21u, L"Volatile Environment\\%lu", a1);
  Key = v6;
  if ( v6 < 0 )
  {
    _DbgPrintMessage(
      8,
      "StringCbPrintf failed: 0x%x in %s",
      (unsigned int)v6,
      "CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry");
    goto LABEL_11;
  }
  phkResult = 0;
  Key = RegOpenCurrentUser(0x20006u, &phkResult);
  if ( !Key )
  {
    Key = CRegistry::CreateKey((CRegistry *)v17, phkResult, v22, v8, lpData, cbData, v15);
    RegCloseKey(phkResult);
  }
  v9 = Key < 0;
  if ( Key > 0 )
  {
    Key = (unsigned __int16)Key | 0x80070000;
    v9 = Key < 0;
  }
  if ( v9 )
  {
    v12 = "RegEnv.CreateUserKey failed: 0x%x in %s";
LABEL_15:
    _DbgPrintMessage(8, v12, (unsigned int)Key, "CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry");
    goto LABEL_11;
  }
  do
    ++v5;
  while ( *(_WORD *)&a3[2 * v5] );
  v10 = RegSetValueExW(hKey, a2, 0, 1u, a3, 2 * v5 + 2);
  Key = v10;
  if ( v10 > 0 )
    Key = (unsigned __int16)v10 | 0x80070000;
  if ( Key < 0 )
  {
    v12 = "RegEnv.WriteRegString failed: 0x%x in %s";
    goto LABEL_15;
  }
LABEL_11:
  CRegistry::~CRegistry((CRegistry *)v17);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180017e64  mov     [rsp-8+arg_18], rbx
0x180017e69  push    rbp
0x180017e6a  push    rsi
0x180017e6b  push    rdi
0x180017e6c  push    r14
0x180017e6e  push    r15
0x180017e70  lea     rbp, [rsp-37h]
0x180017e75  sub     rsp, 0D0h
0x180017e7c  mov     rax, cs:__security_cookie
0x180017e83  xor     rax, rsp
0x180017e86  mov     [rbp+57h+var_30], rax
0x180017e8a  mov     rsi, r8
0x180017e8d  mov     r14, rdx
0x180017e90  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180017e97  mov     [rbp+57h+var_A8], rax
0x180017e9b  xor     r15d, r15d
0x180017e9e  mov     [rbp+57h+var_A0], r15
0x180017ea2  mov     [rbp+57h+var_98], r15d
0x180017ea6  mov     [rbp+57h+hKey], r15
0x180017eaa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017eae  mov     [rbp+57h+var_88], edi
0x180017eb1  mov     [rbp+57h+var_84], edi
0x180017eb4  mov     r9d, ecx
0x180017eb7  lea     r8, aVolatileEnviro; "Volatile Environment\\%lu"
0x180017ebe  lea     edx, [rdi+22h]; unsigned __int64
0x180017ec1  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x180017ec5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017eca  mov     ebx, eax
0x180017ecc  test    eax, eax
0x180017ece  js      loc_180017F7B
0x180017ed4  mov     [rbp+57h+phkResult], r15
0x180017ed8  lea     rdx, [rbp+57h+phkResult]; phkResult
0x180017edc  mov     ecx, 20006h; samDesired
0x180017ee1  call    cs:__imp_RegOpenCurrentUser
0x180017ee7  mov     ebx, eax
0x180017ee9  test    eax, eax
0x180017eeb  jz      loc_180017F87
0x180017ef1  test    ebx, ebx
0x180017ef3  jg      short loc_180017F63
0x180017ef5  js      loc_180017FA9
0x180017efb  inc     rdi
0x180017efe  cmp     [rsi+rdi*2], r15w
0x180017f03  jnz     short loc_180017EFB
0x180017f05  lea     eax, ds:2[rdi*2]
0x180017f0c  mov     dword ptr [rsp+0F0h+cbData], eax; cbData
0x180017f10  mov     [rsp+0F0h+lpData], rsi; lpData
0x180017f15  mov     r9d, 1; dwType
0x180017f1b  xor     r8d, r8d; Reserved
0x180017f1e  mov     rdx, r14; lpValueName
0x180017f21  mov     rcx, [rbp+57h+hKey]; hKey
0x180017f25  call    cs:__imp_RegSetValueExW
0x180017f2b  mov     ebx, eax
0x180017f2d  test    eax, eax
0x180017f2f  jg      short loc_180017F70
0x180017f31  test    ebx, ebx
0x180017f33  js      short loc_180017FB2
0x180017f35  lea     rcx, [rbp+57h+var_A8]; this
0x180017f39  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x180017f3e  mov     eax, ebx
0x180017f40  mov     rcx, [rbp+57h+var_30]
0x180017f44  xor     rcx, rsp; StackCookie
0x180017f47  call    __security_check_cookie
0x180017f4c  mov     rbx, [rsp+0F0h+arg_18]
0x180017f54  add     rsp, 0D0h
0x180017f5b  pop     r15
0x180017f5d  pop     r14
0x180017f5f  pop     rdi
0x180017f60  pop     rsi
0x180017f61  pop     rbp
0x180017f62  retn
0x180017f63  movzx   ebx, bx
0x180017f66  or      ebx, 80070000h
0x180017f6c  test    ebx, ebx
0x180017f6e  jmp     short loc_180017EF5
0x180017f70  movzx   ebx, ax
0x180017f73  or      ebx, 80070000h
0x180017f79  jmp     short loc_180017F31
0x180017f7b  mov     r8d, eax
0x180017f7e  lea     rdx, aStringcbprintf_0; "StringCbPrintf failed: 0x%x in %s"
0x180017f85  jmp     short loc_180017FBC
0x180017f87  lea     r8, [rbp+57h+var_80]; unsigned __int16 *
0x180017f8b  mov     rdx, [rbp+57h+phkResult]; HKEY
0x180017f8f  lea     rcx, [rbp+57h+var_A8]; this
0x180017f93  call    ?CreateKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGKPEAKPEAU_SECURITY_ATTRIBUTES@@K@Z; CRegistry::CreateKey(HKEY__ *,ushort const *,ulong,ulong *,_SECURITY_ATTRIBUTES *,ulong)
0x180017f98  mov     ebx, eax
0x180017f9a  mov     rcx, [rbp+57h+phkResult]; hKey
0x180017f9e  call    cs:__imp_RegCloseKey
0x180017fa4  jmp     loc_180017EF1
0x180017fa9  lea     rdx, aRegenvCreateus; "RegEnv.CreateUserKey failed: 0x%x in %s"
0x180017fb0  jmp     short loc_180017FB9
0x180017fb2  lea     rdx, aRegenvWritereg; "RegEnv.WriteRegString failed: 0x%x in %"...
0x180017fb9  mov     r8d, ebx
0x180017fbc  lea     r9, aCwinlogonnotif_16; "CWinlogonNotify::CUserEnvironment::stat"...
0x180017fc3  mov     ecx, 8; int
0x180017fc8  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017fcd  jmp     loc_180017F35
```
