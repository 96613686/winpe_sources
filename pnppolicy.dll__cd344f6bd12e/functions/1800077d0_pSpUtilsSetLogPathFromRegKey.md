# pSpUtilsSetLogPathFromRegKey

- ea: `0x1800077d0`
- end: `0x18000795f`
- name: `pSpUtilsSetLogPathFromRegKey`
- size: `399`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000729c`
- `0x180007458`

## callees

- `0x180001728`
- `0x180006100`
- `0x180006e28`
- `0x180007548`
- `0x18000762c`
- `0x1800077d0`
- `0x180007cd0`
- `0x1800084ac`
- `0x18000a1a0`

## import_xrefs

- `ntdll!NtClose` at `0x180007887`
- `ntdll!NtClose` at `0x180007898`
- `ntdll!NtClose` at `0x180007887`
- `ntdll!NtClose` at `0x180007898`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007874`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000786a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000786a`

## string_xrefs

- `0x180007838`: `LogPath`

## pseudocode

```c
_BOOL8 pSpUtilsSetLogPathFromRegKey()
{
  DWORD OverrideValue; // ebx
  DWORD v1; // eax
  __int64 v3; // rdi
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE v5; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v6; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Dst[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Src[264]; // [rsp+260h] [rbp+160h] BYREF

  LODWORD(v6) = 520;
  Handle = 0;
  v5 = 0;
  OverrideValue = pSpUtilsOpenSetupKey(&Handle, &v5);
  if ( OverrideValue )
    goto LABEL_9;
  OverrideValue = pSpUtilsQueryOverrideValue(Handle, v5, L"LogPath", (__int64)Src, (__int64)&v6);
  if ( !OverrideValue )
  {
    v1 = ExpandEnvironmentStringsW(Src, Dst, 0x104u);
    if ( v1 )
    {
      if ( v1 > 0x104 )
      {
        OverrideValue = 122;
        goto LABEL_5;
      }
      v3 = -1;
      do
        ++v3;
      while ( Dst[v3] );
      if ( (unsigned int)pSetupConcatenatePaths(Dst, L"setupapi.dev.log", 260) )
      {
        OverrideValue = pSetupMakeSurePathExists(Dst);
        if ( OverrideValue )
          goto LABEL_5;
        if ( 2 * (unsigned __int64)(unsigned int)v3 >= 0x208 )
          _report_rangecheckfailure();
        Dst[(unsigned int)v3] = 0;
        if ( (unsigned int)pSpUtilsSetTextLogPath(Dst) )
        {
          if ( (unsigned int)pSpUtilsLogSetPath(Dst) )
            goto LABEL_5;
        }
      }
    }
    OverrideValue = GetLastError();
  }
LABEL_5:
  if ( Handle )
    NtClose((HANDLE)(unsigned int)Handle);
  if ( v5 )
    NtClose((HANDLE)(unsigned int)v5);
LABEL_9:
  SetLastError(OverrideValue);
  return OverrideValue == 0;
}

```

## disassembly

```asm
0x1800077d0  push    rbp
0x1800077d2  push    rbx
0x1800077d3  push    rdi
0x1800077d4  push    r15
0x1800077d6  lea     rbp, [rsp-388h]
0x1800077de  sub     rsp, 488h
0x1800077e5  mov     rax, cs:__security_cookie
0x1800077ec  xor     rax, rsp
0x1800077ef  mov     [rbp+3A0h+var_30], rax
0x1800077f6  xor     r15d, r15d
0x1800077f9  mov     dword ptr [rsp+4A0h+var_460], 208h
0x180007801  lea     rdx, [rsp+4A0h+var_468]
0x180007806  mov     [rsp+4A0h+Handle], r15
0x18000780b  lea     rcx, [rsp+4A0h+Handle]
0x180007810  mov     [rsp+4A0h+var_468], r15
0x180007815  call    pSpUtilsOpenSetupKey
0x18000781a  mov     ebx, eax
0x18000781c  test    eax, eax
0x18000781e  jnz     short loc_18000789E
0x180007820  mov     rdx, [rsp+4A0h+var_468]; HANDLE
0x180007825  lea     rax, [rsp+4A0h+var_460]
0x18000782a  mov     rcx, [rsp+4A0h+Handle]; KeyHandle
0x18000782f  lea     r9d, [r15+1]
0x180007833  mov     [rsp+4A0h+var_478], rax; __int64
0x180007838  lea     r8, aLogpath; "LogPath"
0x18000783f  lea     rax, [rbp+3A0h+Src]
0x180007846  mov     [rsp+4A0h+var_480], rax; __int64
0x18000784b  call    pSpUtilsQueryOverrideValue
0x180007850  mov     ebx, eax
0x180007852  test    eax, eax
0x180007854  jnz     short loc_18000787C
0x180007856  mov     ebx, 104h
0x18000785b  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x180007860  mov     r8d, ebx; nSize
0x180007863  lea     rcx, [rbp+3A0h+Src]; lpSrc
0x18000786a  call    cs:__imp_ExpandEnvironmentStringsW
0x180007870  test    eax, eax
0x180007872  jnz     short loc_1800078CA
0x180007874  call    cs:__imp_GetLastError
0x18000787a  mov     ebx, eax
0x18000787c  cmp     [rsp+4A0h+Handle], r15
0x180007881  jz      short loc_18000788D
0x180007883  mov     ecx, dword ptr [rsp+4A0h+Handle]; Handle
0x180007887  call    cs:__imp_NtClose
0x18000788d  cmp     [rsp+4A0h+var_468], r15
0x180007892  jz      short loc_18000789E
0x180007894  mov     ecx, dword ptr [rsp+4A0h+var_468]; Handle
0x180007898  call    cs:__imp_NtClose
0x18000789e  mov     ecx, ebx; dwErrCode
0x1800078a0  call    cs:__imp_SetLastError
0x1800078a6  test    ebx, ebx
0x1800078a8  mov     eax, r15d
0x1800078ab  setz    al
0x1800078ae  mov     rcx, [rbp+3A0h+var_30]
0x1800078b5  xor     rcx, rsp; StackCookie
0x1800078b8  call    __security_check_cookie
0x1800078bd  add     rsp, 488h
0x1800078c4  pop     r15
0x1800078c6  pop     rdi
0x1800078c7  pop     rbx
0x1800078c8  pop     rbp
0x1800078c9  retn
0x1800078ca  cmp     eax, ebx
0x1800078cc  jbe     short loc_1800078D5
0x1800078ce  mov     ebx, 7Ah ; 'z'
0x1800078d3  jmp     short loc_18000787C
0x1800078d5  lea     rax, [rsp+4A0h+Dst]
0x1800078da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800078de  inc     rdi
0x1800078e1  cmp     [rax+rdi*2], r15w
0x1800078e6  jnz     short loc_1800078DE
0x1800078e8  mov     r8d, ebx
0x1800078eb  lea     rdx, aSetupapiDevLog; "setupapi.dev.log"
0x1800078f2  lea     rcx, [rsp+4A0h+Dst]
0x1800078f7  call    pSetupConcatenatePaths
0x1800078fc  test    eax, eax
0x1800078fe  jz      loc_180007874
0x180007904  lea     rcx, [rsp+4A0h+Dst]
0x180007909  call    pSetupMakeSurePathExists
0x18000790e  mov     ebx, eax
0x180007910  test    eax, eax
0x180007912  jnz     loc_18000787C
0x180007918  mov     eax, edi
0x18000791a  lea     rcx, [rax+rax]
0x18000791e  cmp     rcx, 208h
0x180007925  jnb     short loc_180007959
0x180007927  mov     [rsp+rcx+4A0h+Dst], r15w
0x18000792d  lea     edx, [rbx+1]
0x180007930  lea     rcx, [rsp+4A0h+Dst]; pszSrc
0x180007935  call    _pSpUtilsSetTextLogPath
0x18000793a  test    eax, eax
0x18000793c  jz      loc_180007874
0x180007942  lea     rcx, [rsp+4A0h+Dst]; pszSrc
0x180007947  call    _pSpUtilsLogSetPath
0x18000794c  test    eax, eax
0x18000794e  jnz     loc_18000787C
0x180007954  jmp     loc_180007874
0x180007959  call    __report_rangecheckfailure
```
