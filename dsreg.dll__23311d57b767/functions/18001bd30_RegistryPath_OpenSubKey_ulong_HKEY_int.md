# RegistryPath::OpenSubKey(ulong,HKEY__ * *,int)

- ea: `0x18001bd30`
- end: `0x18001be08`
- name: `?OpenSubKey@RegistryPath@@QEBAKKPEAPEAUHKEY__@@H@Z`
- size: `216`
- prototype: `unsigned int(RegistryPath *__hidden this, unsigned int, HKEY *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180095dfc`
- `0x180096528`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18001bd30`
- `0x180043e54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bd74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdfa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001bdfa`

## string_xrefs

- `0x18001bd98`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18001bd91`: `RegistryPath::OpenSubKey`
- `0x18001bdb3`: `RegistryPath::OpenSubKey`
- `0x18001bddc`: `RegistryPath::OpenSubKey`
- `0x18001bdcb`: `RegOpenKeyExW`
- `0x18001bde6`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`
- `0x18001bdba`: `%s: Registry key "%s" does not exist.`

## pseudocode

```c
__int64 __fastcall RegistryPath::OpenSubKey(RegistryPath *this, REGSAM a2, HKEY *a3, int a4)
{
  HKEY v6; // rcx
  HKEY *phkResult; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx

  *a3 = 0;
  v6 = (HKEY)*((_QWORD *)this + 4);
  phkResult = a3;
  if ( v6 )
  {
    a3 = *(HKEY **)this;
    if ( *(_QWORD *)this )
    {
      if ( *(_WORD *)a3 )
      {
        v8 = RegOpenKeyExW(v6, (LPCWSTR)a3 + *((_QWORD *)this + 3), 0, a2, phkResult);
        v9 = v8;
        if ( a4 || v8 != 2 )
        {
          if ( !v8 )
            return v9;
          Logger::WriteRegistryFailureEvent(v8, L"RegOpenKeyExW", *(const unsigned __int16 **)this);
          Logger::TraceError(
            L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
            L"RegistryPath::OpenSubKey",
            *(_QWORD *)this,
            v9);
        }
        else
        {
          Logger::TraceVerbose(
            (wchar_t *)L"%s: Registry key \"%s\" does not exist.",
            L"RegistryPath::OpenSubKey",
            *(_QWORD *)this);
        }
        if ( *phkResult )
        {
          RegCloseKey(*phkResult);
          *phkResult = 0;
        }
        return v9;
      }
    }
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::OpenSubKey",
    a3,
    a2);
  return 87;
}

```

## disassembly

```asm
0x18001bd30  push    rbx
0x18001bd32  push    rbp
0x18001bd33  push    rsi
0x18001bd34  push    rdi
0x18001bd35  push    r14
0x18001bd37  sub     rsp, 30h
0x18001bd3b  xor     r14d, r14d
0x18001bd3e  mov     rdi, rcx
0x18001bd41  mov     [r8], r14
0x18001bd44  mov     ebp, r9d
0x18001bd47  mov     rcx, [rcx+20h]; hKey
0x18001bd4b  mov     rsi, r8
0x18001bd4e  mov     r9d, edx; samDesired
0x18001bd51  test    rcx, rcx
0x18001bd54  jz      short loc_18001BD91
0x18001bd56  mov     r8, [rdi]
0x18001bd59  test    r8, r8
0x18001bd5c  jz      short loc_18001BD91
0x18001bd5e  cmp     [r8], r14w
0x18001bd62  jz      short loc_18001BD91
0x18001bd64  mov     rax, [rdi+18h]
0x18001bd68  mov     [rsp+58h+phkResult], rsi; phkResult
0x18001bd6d  lea     rdx, [r8+rax*2]; lpSubKey
0x18001bd71  xor     r8d, r8d; ulOptions
0x18001bd74  call    cs:__imp_RegOpenKeyExW
0x18001bd7a  mov     ebx, eax
0x18001bd7c  test    ebp, ebp
0x18001bd7e  jz      short loc_18001BDAB
0x18001bd80  test    ebx, ebx
0x18001bd82  jnz     short loc_18001BDC8
0x18001bd84  mov     eax, ebx
0x18001bd86  add     rsp, 30h
0x18001bd8a  pop     r14
0x18001bd8c  pop     rdi
0x18001bd8d  pop     rsi
0x18001bd8e  pop     rbp
0x18001bd8f  pop     rbx
0x18001bd90  retn
0x18001bd91  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bd98  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18001bd9f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bda4  mov     eax, 57h ; 'W'
0x18001bda9  jmp     short loc_18001BD86
0x18001bdab  cmp     ebx, 2
0x18001bdae  jnz     short loc_18001BD80
0x18001bdb0  mov     r8, [rdi]
0x18001bdb3  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bdba  lea     rcx, aSRegistryKeySD; "%s: Registry key \"%s\" does not exist."
0x18001bdc1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001bdc6  jmp     short loc_18001BDF2
0x18001bdc8  mov     r8, [rdi]; unsigned __int16 *
0x18001bdcb  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001bdd2  mov     ecx, ebx; unsigned int
0x18001bdd4  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18001bdd9  mov     r8, [rdi]
0x18001bddc  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18001bde3  mov     r9d, ebx
0x18001bde6  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x18001bded  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001bdf2  mov     rcx, [rsi]; hKey
0x18001bdf5  test    rcx, rcx
0x18001bdf8  jz      short loc_18001BD84
0x18001bdfa  call    cs:__imp_RegCloseKey
0x18001be00  mov     [rsi], r14
0x18001be03  jmp     loc_18001BD84
```
