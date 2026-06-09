# DeleteKeyAndSubKeys(HKEY__ *,char const *)

- ea: `0x180066874`
- end: `0x180066973`
- name: `?DeleteKeyAndSubKeys@@YAHPEAUHKEY__@@PEBD@Z`
- size: `255`
- prototype: `__int64 __fastcall(HKEY, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180066874`
- `0x18006c168`
- `0x18006c248`
- `0x18006c2e4`

## callees

- `0x180066874`
- `0x180075c90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180066933`
- `ADVAPI32!RegCloseKey` at `0x180066933`
- `ADVAPI32!RegDeleteKeyA` at `0x18006693f`
- `ADVAPI32!RegDeleteKeyA` at `0x18006693f`
- `ADVAPI32!RegEnumKeyExA` at `0x18006690f`
- `ADVAPI32!RegEnumKeyExA` at `0x18006690f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800668c2`
- `ADVAPI32!RegOpenKeyExA` at `0x1800668c2`

## pseudocode

```c
_BOOL8 __fastcall DeleteKeyAndSubKeys(HKEY a1, const char *a2)
{
  DWORD v5; // ebx
  DWORD cchName; // [rsp+40h] [rbp-138h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-130h] BYREF
  CHAR Name[272]; // [rsp+50h] [rbp-128h] BYREF

  hKey = 0;
  cchName = 0;
  if ( RegOpenKeyExA(a1, a2, 0, 0xF003Fu, &hKey) )
    return 0;
  v5 = 0;
  do
  {
    cchName = 260;
    if ( RegEnumKeyExA(hKey, v5, Name, &cchName, 0, 0, 0, 0) )
      break;
    ++v5;
  }
  while ( (unsigned int)DeleteKeyAndSubKeys(hKey, Name) );
  RegCloseKey(hKey);
  return RegDeleteKeyA(a1, a2) == 0;
}

```

## disassembly

```asm
0x180066874  mov     [rsp+arg_10], rbx
0x180066879  mov     [rsp+arg_18], rsi
0x18006687e  push    rdi
0x18006687f  sub     rsp, 170h
0x180066886  mov     rax, cs:__security_cookie
0x18006688d  xor     rax, rsp
0x180066890  mov     [rsp+178h+var_18], rax
0x180066898  lea     rax, [rsp+178h+hKey]
0x18006689d  mov     [rsp+178h+hKey], 0
0x1800668a6  mov     r9d, 0F003Fh; samDesired
0x1800668ac  mov     [rsp+178h+phkResult], rax; phkResult
0x1800668b1  xor     r8d, r8d; ulOptions
0x1800668b4  mov     [rsp+178h+cchName], 0
0x1800668bc  mov     rsi, rdx
0x1800668bf  mov     rdi, rcx
0x1800668c2  call    cs:__imp_RegOpenKeyExA
0x1800668c8  test    eax, eax
0x1800668ca  jz      short loc_1800668D0
0x1800668cc  xor     eax, eax
0x1800668ce  jmp     short loc_18006694E
0x1800668d0  xor     ebx, ebx
0x1800668d2  mov     rcx, [rsp+178h+hKey]; hKey
0x1800668d7  lea     r9, [rsp+178h+cchName]; lpcchName
0x1800668dc  mov     [rsp+178h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800668e5  lea     r8, [rsp+178h+Name]; lpName
0x1800668ea  mov     [rsp+178h+lpcchClass], 0; lpcchClass
0x1800668f3  mov     edx, ebx; dwIndex
0x1800668f5  mov     [rsp+178h+lpClass], 0; lpClass
0x1800668fe  mov     [rsp+178h+phkResult], 0; lpReserved
0x180066907  mov     [rsp+178h+cchName], 104h
0x18006690f  call    cs:__imp_RegEnumKeyExA
0x180066915  test    eax, eax
0x180066917  jnz     short loc_18006692E
0x180066919  mov     rcx, [rsp+178h+hKey]; HKEY
0x18006691e  lea     rdx, [rsp+178h+Name]; char *
0x180066923  inc     ebx
0x180066925  call    ?DeleteKeyAndSubKeys@@YAHPEAUHKEY__@@PEBD@Z; DeleteKeyAndSubKeys(HKEY__ *,char const *)
0x18006692a  test    eax, eax
0x18006692c  jnz     short loc_1800668D2
0x18006692e  mov     rcx, [rsp+178h+hKey]; hKey
0x180066933  call    cs:__imp_RegCloseKey
0x180066939  mov     rdx, rsi; lpSubKey
0x18006693c  mov     rcx, rdi; hKey
0x18006693f  call    cs:__imp_RegDeleteKeyA
0x180066945  xor     ecx, ecx
0x180066947  test    eax, eax
0x180066949  setz    cl
0x18006694c  mov     eax, ecx
0x18006694e  mov     rcx, [rsp+178h+var_18]
0x180066956  xor     rcx, rsp; StackCookie
0x180066959  call    __security_check_cookie
0x18006695e  lea     r11, [rsp+178h+var_8]
0x180066966  mov     rbx, [r11+20h]
0x18006696a  mov     rsi, [r11+28h]
0x18006696e  mov     rsp, r11
0x180066971  pop     rdi
0x180066972  retn
```
