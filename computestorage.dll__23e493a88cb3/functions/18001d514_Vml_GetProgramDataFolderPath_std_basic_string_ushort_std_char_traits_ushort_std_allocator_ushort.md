# Vml::GetProgramDataFolderPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001d514`
- end: `0x18001d5e9`
- name: `?GetProgramDataFolderPath@Vml@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001cd00`

## callees

- `0x180008fac`
- `0x180009a38`
- `0x1800136f8`
- `0x180013cb4`
- `0x18001b920`
- `0x18001d514`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001d535`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001d57c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001d535`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18001d57c`

## string_xrefs

- `0x18001d5c9`: `onecore\vm\common\vml\VmEnvironment.h`
- `0x18001d5d8`: `onecore\vm\common\vml\VmEnvironment.h`
- `0x18001d52e`: `ProgramData`
- `0x18001d575`: `ProgramData`

## pseudocode

```c
__int64 __fastcall Vml::GetProgramDataFolderPath(__int64 a1)
{
  DWORD EnvironmentVariableW; // eax
  const char *v3; // r9
  DWORD v4; // ebx
  WCHAR *v5; // rdx
  const char *v6; // r9
  const char *v7; // r9
  __int64 result; // rax
  LPWSTR lpBuffer[6]; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  EnvironmentVariableW = GetEnvironmentVariableW(L"ProgramData", 0, 0);
  try
  {
    v4 = EnvironmentVariableW;
    if ( !EnvironmentVariableW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\vm\\common\\vml\\VmEnvironment.h",
        v3);
    std::wstring::wstring(lpBuffer, EnvironmentVariableW);
    v5 = (WCHAR *)lpBuffer;
    if ( lpBuffer[3] > (LPWSTR)7 )
      v5 = lpBuffer[0];
    if ( !GetEnvironmentVariableW(L"ProgramData", v5, v4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\vm\\common\\vml\\VmEnvironment.h",
        v6);
    std::wstring::resize(lpBuffer);
    std::wstring::operator=(a1, lpBuffer);
    std::wstring::~wstring((char **)lpBuffer);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x82,
                           (unsigned int)"onecore\\vm\\common\\vml\\VmPath.h",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001d514  mov     [rsp+arg_8], rbx
0x18001d519  push    rdi
0x18001d51a  sub     rsp, 50h
0x18001d51e  mov     rdi, rcx
0x18001d521  mov     [rsp+58h+var_38], 0
0x18001d529  xor     r8d, r8d; nSize
0x18001d52c  xor     edx, edx; lpBuffer
0x18001d52e  lea     rcx, Name; "ProgramData"
0x18001d535  call    cs:__imp_GetEnvironmentVariableW
0x18001d53c  nop     dword ptr [rax+rax+00h]
0x18001d541  mov     ebx, eax
0x18001d543  mov     rcx, [rsp+58h]; this
0x18001d548  test    eax, eax
0x18001d54a  jz      short loc_18001D5C9
0x18001d54c  mov     rdx, rbx
0x18001d54f  lea     rcx, [rsp+58h+lpBuffer]
0x18001d554  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18001d559  mov     [rsp+58h+var_38], 1
0x18001d561  lea     rdx, [rsp+58h+lpBuffer]
0x18001d566  cmp     [rsp+58h+var_18], 7
0x18001d56c  cmova   rdx, [rsp+58h+lpBuffer]; lpBuffer
0x18001d572  mov     r8d, ebx; nSize
0x18001d575  lea     rcx, Name; "ProgramData"
0x18001d57c  call    cs:__imp_GetEnvironmentVariableW
0x18001d583  nop     dword ptr [rax+rax+00h]
0x18001d588  mov     rcx, [rsp+58h]; this
0x18001d58d  test    eax, eax
0x18001d58f  jz      short loc_18001D5D8
0x18001d591  mov     edx, eax
0x18001d593  lea     rcx, [rsp+58h+lpBuffer]; Src
0x18001d598  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001d59d  lea     rdx, [rsp+58h+lpBuffer]
0x18001d5a2  mov     rcx, rdi
0x18001d5a5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d5aa  nop
0x18001d5ab  lea     rcx, [rsp+58h+lpBuffer]
0x18001d5b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001d5b5  xor     eax, eax
0x18001d5b7  jmp     short loc_18001D5BD
0x18001d5b9  mov     eax, [rsp+58h+var_38]
0x18001d5bd  mov     rbx, [rsp+58h+arg_8]
0x18001d5c2  add     rsp, 50h
0x18001d5c6  pop     rdi
0x18001d5c7  retn
0x18001d5c9  lea     r8, aOnecoreVmCommo_1; "onecore\\vm\\common\\vml\\VmEnvironment"...
0x18001d5d0  lea     edx, [rax+32h]; void *
0x18001d5d3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001d5d8  lea     r8, aOnecoreVmCommo_1; "onecore\\vm\\common\\vml\\VmEnvironment"...
0x18001d5df  lea     edx, [rax+36h]; void *
0x18001d5e2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
