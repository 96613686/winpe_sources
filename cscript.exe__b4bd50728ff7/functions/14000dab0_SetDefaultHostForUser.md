# SetDefaultHostForUser

- ea: `0x14000dab0`
- end: `0x14000db9e`
- name: `SetDefaultHostForUser`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007c74`

## callees

- `0x14000da0c`
- `0x14000dab0`
- `0x14000dba4`
- `0x1400161d0`

## import_xrefs

- `ADVAPI32!RegCreateKeyA` at `0x14000db3f`
- `ADVAPI32!RegCreateKeyA` at `0x14000db3f`
- `ADVAPI32!RegOpenKeyExA` at `0x14000db28`
- `ADVAPI32!RegOpenKeyExA` at `0x14000db28`
- `ADVAPI32!RegCloseKey` at `0x14000db75`
- `ADVAPI32!RegCloseKey` at `0x14000db75`

## pseudocode

```c
__int64 __fastcall SetDefaultHostForUser(const char *a1, const BYTE *a2)
{
  int v3; // ebx
  __int64 v4; // r8
  LSTATUS KeyA; // eax
  HKEY hKey[2]; // [rsp+30h] [rbp-138h] BYREF
  CHAR SubKey[272]; // [rsp+40h] [rbp-128h] BYREF

  hKey[0] = 0;
  v3 = StringCchPrintfA(SubKey, 0x104u, "SOFTWARE\\Classes\\%s\\%s", a1, "Shell");
  if ( v3 >= 0 )
  {
    if ( !RegOpenKeyExA(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, hKey) )
      goto LABEL_7;
    KeyA = RegCreateKeyA(HKEY_CURRENT_USER, SubKey, hKey);
    v3 = KeyA;
    if ( !KeyA )
      goto LABEL_7;
    if ( KeyA > 0 )
      v3 = (unsigned __int16)KeyA | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_7:
      v3 = RegSetKeyString(hKey[0], byte_140019BD0, v4, a2);
      RegCloseKey(hKey[0]);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000dab0  mov     [rsp+arg_10], rbx
0x14000dab5  push    rdi
0x14000dab6  sub     rsp, 160h
0x14000dabd  mov     rax, cs:__security_cookie
0x14000dac4  xor     rax, rsp
0x14000dac7  mov     [rsp+168h+var_18], rax
0x14000dacf  mov     rdi, rdx
0x14000dad2  mov     [rsp+168h+hKey], 0
0x14000dadb  lea     rax, aShell; "Shell"
0x14000dae2  mov     r9, rcx
0x14000dae5  mov     edx, 104h; unsigned __int64
0x14000daea  mov     [rsp+168h+phkResult], rax
0x14000daef  lea     rcx, [rsp+168h+SubKey]; char *
0x14000daf4  lea     r8, aSoftwareClasse; "SOFTWARE\\Classes\\%s\\%s"
0x14000dafb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000db00  mov     ebx, eax
0x14000db02  test    eax, eax
0x14000db04  js      short loc_14000DB7B
0x14000db06  lea     rax, [rsp+168h+hKey]
0x14000db0b  mov     rbx, 0FFFFFFFF80000001h
0x14000db12  mov     rcx, rbx; hKey
0x14000db15  mov     [rsp+168h+phkResult], rax; phkResult
0x14000db1a  mov     r9d, 20006h; samDesired
0x14000db20  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x14000db25  xor     r8d, r8d; ulOptions
0x14000db28  call    cs:__imp_RegOpenKeyExA
0x14000db2e  test    eax, eax
0x14000db30  jz      short loc_14000DB5A
0x14000db32  lea     r8, [rsp+168h+hKey]; phkResult
0x14000db37  mov     rcx, rbx; hKey
0x14000db3a  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x14000db3f  call    cs:__imp_RegCreateKeyA
0x14000db45  mov     ebx, eax
0x14000db47  test    eax, eax
0x14000db49  jz      short loc_14000DB5A
0x14000db4b  jle     short loc_14000DB56
0x14000db4d  movzx   ebx, ax
0x14000db50  or      ebx, 80070000h
0x14000db56  test    ebx, ebx
0x14000db58  js      short loc_14000DB7B
0x14000db5a  mov     rcx, [rsp+168h+hKey]
0x14000db5f  lea     rdx, byte_140019BD0
0x14000db66  mov     r9, rdi
0x14000db69  call    RegSetKeyString
0x14000db6e  mov     rcx, [rsp+168h+hKey]; hKey
0x14000db73  mov     ebx, eax
0x14000db75  call    cs:__imp_RegCloseKey
0x14000db7b  mov     eax, ebx
0x14000db7d  mov     rcx, [rsp+168h+var_18]
0x14000db85  xor     rcx, rsp; StackCookie
0x14000db88  call    __security_check_cookie
0x14000db8d  mov     rbx, [rsp+168h+arg_10]
0x14000db95  add     rsp, 160h
0x14000db9c  pop     rdi
0x14000db9d  retn
```
