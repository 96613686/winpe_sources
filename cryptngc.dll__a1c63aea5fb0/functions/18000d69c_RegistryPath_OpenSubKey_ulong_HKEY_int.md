# RegistryPath::OpenSubKey(ulong,HKEY__ * *,int)

- ea: `0x18000d69c`
- end: `0x18000d75f`
- name: `?OpenSubKey@RegistryPath@@QEBAKKPEAPEAUHKEY__@@H@Z`
- size: `195`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, unsigned int, HKEY *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002cf08`

## callees

- `0x18000c190`
- `0x18000d69c`
- `0x180026f88`
- `0x180027448`
- `0x18002cb00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d6e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d6e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d726`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d726`

## string_xrefs

- `0x18000d73e`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x18000d708`: `RegistryPath::OpenSubKey`
- `0x18000d737`: `RegistryPath::OpenSubKey`
- `0x18000d6f7`: `RegOpenKeyExW`
- `0x18000d712`: `%s: Failed to open registry key "%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegistryPath::OpenSubKey(HKEY *this, __int64 a2, HKEY *a3)
{
  const WCHAR *v5; // rax
  PHKEY phkResult; // r8
  LSTATUS v7; // eax
  unsigned int v8; // esi

  *a3 = 0;
  if ( !this[4] || (unsigned int)IsEmptyString((const unsigned __int16 *)*this) )
  {
    Logger::TraceError(
      L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
      L"RegistryPath::OpenSubKey");
    return 87;
  }
  else
  {
    v5 = RegistryPath::SubPath((RegistryPath *)this);
    v7 = RegOpenKeyExW(this[4], v5, 0, 1u, phkResult);
    v8 = v7;
    if ( v7 )
    {
      Logger::WriteRegistryFailureEvent(v7, L"RegOpenKeyExW", (const unsigned __int16 *)*this);
      Logger::TraceError(
        L"%s: Failed to open registry key \"%s\". Error code: 0x%08x.",
        L"RegistryPath::OpenSubKey",
        *this,
        v8);
      if ( *a3 )
      {
        RegCloseKey(*a3);
        *a3 = 0;
      }
    }
    return v8;
  }
}

```

## disassembly

```asm
0x18000d69c  mov     [rsp+arg_0], rbx
0x18000d6a1  mov     [rsp+arg_8], rsi
0x18000d6a6  push    rdi
0x18000d6a7  sub     rsp, 30h
0x18000d6ab  mov     qword ptr [r8], 0
0x18000d6b2  mov     rdi, r8
0x18000d6b5  cmp     qword ptr [rcx+20h], 0
0x18000d6ba  mov     rbx, rcx
0x18000d6bd  jz      short loc_18000D737
0x18000d6bf  mov     rcx, [rcx]; unsigned __int16 *
0x18000d6c2  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000d6c7  test    eax, eax
0x18000d6c9  jnz     short loc_18000D737
0x18000d6cb  mov     rcx, rbx; this
0x18000d6ce  call    ?SubPath@RegistryPath@@QEBAPEBGXZ; RegistryPath::SubPath(void)
0x18000d6d3  mov     rcx, [rbx+20h]; hKey
0x18000d6d7  mov     rdx, rax; lpSubKey
0x18000d6da  mov     [rsp+38h+phkResult], r8; phkResult
0x18000d6df  mov     r9d, 1; samDesired
0x18000d6e5  xor     r8d, r8d; ulOptions
0x18000d6e8  call    cs:__imp_RegOpenKeyExW
0x18000d6ee  mov     esi, eax
0x18000d6f0  test    eax, eax
0x18000d6f2  jz      short loc_18000D733
0x18000d6f4  mov     r8, [rbx]; unsigned __int16 *
0x18000d6f7  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18000d6fe  mov     ecx, eax; unsigned int
0x18000d700  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x18000d705  mov     r8, [rbx]
0x18000d708  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18000d70f  mov     r9d, esi
0x18000d712  lea     rcx, aSFailedToOpenR; "%s: Failed to open registry key \"%s\"."...
0x18000d719  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d71e  mov     rcx, [rdi]; hKey
0x18000d721  test    rcx, rcx
0x18000d724  jz      short loc_18000D733
0x18000d726  call    cs:__imp_RegCloseKey
0x18000d72c  mov     qword ptr [rdi], 0
0x18000d733  mov     eax, esi
0x18000d735  jmp     short loc_18000D74F
0x18000d737  lea     rdx, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18000d73e  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x18000d745  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000d74a  mov     eax, 57h ; 'W'
0x18000d74f  mov     rbx, [rsp+38h+arg_0]
0x18000d754  mov     rsi, [rsp+38h+arg_8]
0x18000d759  add     rsp, 30h
0x18000d75d  pop     rdi
0x18000d75e  retn
```
