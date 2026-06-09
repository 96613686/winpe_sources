# CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry(long,ushort const *,ushort const *)

- ea: `0x18000bda8`
- end: `0x18000bf31`
- name: `?staticSetEnvVarInRegistry@CUserEnvironment@CWinlogonNotify@@CAJJPEBG0@Z`
- size: `393`
- prototype: `static int(int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b978`

## callees

- `0x1800077a0`
- `0x18000bcc8`
- `0x18000bda8`
- `0x18000c17c`
- `0x18002dc08`
- `0x18004e850`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bef6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bef6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000be25`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000be25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000be6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000be6f`

## string_xrefs

- `0x18000bf1a`: `CWinlogonNotify::CUserEnvironment::staticSetEnvVarInRegistry`
- `0x18000bf07`: `RegEnv.CreateUserKey failed: 0x%x in %s`
- `0x18000bf10`: `RegEnv.WriteRegString failed: 0x%x in %s`

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
0x18000bda8  mov     [rsp-8+arg_18], rbx
0x18000bdad  push    rbp
0x18000bdae  push    rsi
0x18000bdaf  push    rdi
0x18000bdb0  push    r14
0x18000bdb2  push    r15
0x18000bdb4  lea     rbp, [rsp-37h]
0x18000bdb9  sub     rsp, 0D0h
0x18000bdc0  mov     rax, cs:__security_cookie
0x18000bdc7  xor     rax, rsp
0x18000bdca  mov     [rbp+57h+var_30], rax
0x18000bdce  mov     rsi, r8
0x18000bdd1  mov     r14, rdx
0x18000bdd4  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18000bddb  mov     [rbp+57h+var_A8], rax
0x18000bddf  xor     r15d, r15d
0x18000bde2  mov     [rbp+57h+var_A0], r15
0x18000bde6  mov     [rbp+57h+var_98], r15d
0x18000bdea  mov     [rbp+57h+hKey], r15
0x18000bdee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000bdf2  mov     [rbp+57h+var_88], edi
0x18000bdf5  mov     [rbp+57h+var_84], edi
0x18000bdf8  mov     r9d, ecx
0x18000bdfb  lea     r8, aVolatileEnviro; "Volatile Environment\\%lu"
0x18000be02  lea     edx, [rdi+22h]; unsigned __int64
0x18000be05  lea     rcx, [rbp+57h+var_80]; unsigned __int16 *
0x18000be09  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000be0e  mov     ebx, eax
0x18000be10  test    eax, eax
0x18000be12  js      loc_18000BED3
0x18000be18  mov     [rbp+57h+phkResult], r15
0x18000be1c  lea     rdx, [rbp+57h+phkResult]; phkResult
0x18000be20  mov     ecx, 20006h; samDesired
0x18000be25  call    cs:__imp_RegOpenCurrentUser
0x18000be2c  nop     dword ptr [rax+rax+00h]
0x18000be31  mov     ebx, eax
0x18000be33  test    eax, eax
0x18000be35  jz      loc_18000BEDF
0x18000be3b  test    ebx, ebx
0x18000be3d  jg      short loc_18000BEB8
0x18000be3f  js      loc_18000BF07
0x18000be45  inc     rdi
0x18000be48  cmp     [rsi+rdi*2], r15w
0x18000be4d  jnz     short loc_18000BE45
0x18000be4f  lea     eax, ds:2[rdi*2]
0x18000be56  mov     dword ptr [rsp+0F0h+cbData], eax; cbData
0x18000be5a  mov     [rsp+0F0h+lpData], rsi; lpData
0x18000be5f  mov     r9d, 1; dwType
0x18000be65  xor     r8d, r8d; Reserved
0x18000be68  mov     rdx, r14; lpValueName
0x18000be6b  mov     rcx, [rbp+57h+hKey]; hKey
0x18000be6f  call    cs:__imp_RegSetValueExW
0x18000be76  nop     dword ptr [rax+rax+00h]
0x18000be7b  mov     ebx, eax
0x18000be7d  test    eax, eax
0x18000be7f  jg      short loc_18000BEC8
0x18000be81  test    ebx, ebx
0x18000be83  js      loc_18000BF10
0x18000be89  lea     rcx, [rbp+57h+var_A8]; this
0x18000be8d  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18000be92  mov     eax, ebx
0x18000be94  mov     rcx, [rbp+57h+var_30]
0x18000be98  xor     rcx, rsp; StackCookie
0x18000be9b  call    __security_check_cookie
0x18000bea0  mov     rbx, [rsp+0F0h+arg_18]
0x18000bea8  add     rsp, 0D0h
0x18000beaf  pop     r15
0x18000beb1  pop     r14
0x18000beb3  pop     rdi
0x18000beb4  pop     rsi
0x18000beb5  pop     rbp
0x18000beb6  retn
0x18000beb8  movzx   ebx, bx
0x18000bebb  or      ebx, 80070000h
0x18000bec1  test    ebx, ebx
0x18000bec3  jmp     loc_18000BE3F
0x18000bec8  movzx   ebx, ax
0x18000becb  or      ebx, 80070000h
0x18000bed1  jmp     short loc_18000BE81
0x18000bed3  mov     r8d, eax
0x18000bed6  lea     rdx, aStringcbprintf_0; "StringCbPrintf failed: 0x%x in %s"
0x18000bedd  jmp     short loc_18000BF1A
0x18000bedf  lea     r8, [rbp+57h+var_80]; unsigned __int16 *
0x18000bee3  mov     rdx, [rbp+57h+phkResult]; HKEY
0x18000bee7  lea     rcx, [rbp+57h+var_A8]; this
0x18000beeb  call    ?CreateKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGKPEAKPEAU_SECURITY_ATTRIBUTES@@K@Z; CRegistry::CreateKey(HKEY__ *,ushort const *,ulong,ulong *,_SECURITY_ATTRIBUTES *,ulong)
0x18000bef0  mov     ebx, eax
0x18000bef2  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000bef6  call    cs:__imp_RegCloseKey
0x18000befd  nop     dword ptr [rax+rax+00h]
0x18000bf02  jmp     loc_18000BE3B
0x18000bf07  lea     rdx, aRegenvCreateus; "RegEnv.CreateUserKey failed: 0x%x in %s"
0x18000bf0e  jmp     short loc_18000BF17
0x18000bf10  lea     rdx, aRegenvWritereg; "RegEnv.WriteRegString failed: 0x%x in %"...
0x18000bf17  mov     r8d, ebx
0x18000bf1a  lea     r9, aCwinlogonnotif_16; "CWinlogonNotify::CUserEnvironment::stat"...
0x18000bf21  mov     ecx, 8; int
0x18000bf26  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18000bf2b  jmp     loc_18000BE89
```
