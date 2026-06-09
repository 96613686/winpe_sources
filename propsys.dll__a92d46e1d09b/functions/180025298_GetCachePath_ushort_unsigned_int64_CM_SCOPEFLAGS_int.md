# GetCachePath(ushort *,unsigned __int64,CM_SCOPEFLAGS,int)

- ea: `0x180025298`
- end: `0x1800253fa`
- name: `?GetCachePath@@YAHPEAG_KW4CM_SCOPEFLAGS@@H@Z`
- size: `354`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020bdc`
- `0x180024ac4`
- `0x18004f204`
- `0x1800632b0`
- `0x1800a73bc`

## callees

- `0x180025298`
- `0x18002568c`
- `0x180025978`
- `0x18005d548`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025308`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025308`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800252da`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002533c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800252da`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18002533c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800252f4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800253c4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800253e8`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800252f4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800253c4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800253e8`

## string_xrefs

- `0x18002534a`: `Microsoft\Windows\Caches`
- `0x1800252d3`: `ProgramData`

## pseudocode

```c
_BOOL8 __fastcall GetCachePath(unsigned __int16 *a1, __int64 a2, char a3, int a4)
{
  HANDLE CurrentProcess; // rax
  bool *v7; // r8
  struct _SECURITY_ATTRIBUTES *v8; // rdx
  _BOOL8 result; // rax
  int Directory; // eax
  _BYTE v11[16]; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  *a1 = 0;
  if ( (a3 & 1) == 0 )
  {
    if ( !GetEnvironmentVariableW(L"ProgramData", Buffer, 0x104u)
      && (int)GetBasicProfileFolderPath(4, 0, Buffer, 260) < 0 )
    {
      return 0;
    }
    goto LABEL_8;
  }
  v11[0] = 0;
  CurrentProcess = GetCurrentProcess();
  if ( (int)CallerIdentity::IsProcessAppContainer(CurrentProcess, v11, v7) >= 0 && v11[0] )
  {
    result = (int)GetBasicProfileFolderPath(8, 0, Buffer, 260) >= 0;
    goto LABEL_16;
  }
  if ( !GetEnvironmentVariableW(L"LOCALAPPDATA", Buffer, 0x104u)
    && (int)GetBasicProfileFolderPath(6, 0, Buffer, 260) < 0 )
  {
    result = 0;
LABEL_16:
    if ( !result )
      return result;
  }
LABEL_8:
  if ( (int)StringCchPrintfW(a1, 0x104u, L"%s\\%s", Buffer, L"Microsoft\\Windows\\Caches") < 0 )
    return 0;
  if ( a4 )
  {
    Directory = _CreateDirectory(a1, v8);
    if ( Directory )
    {
      if ( Directory != 183 )
        return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180025298  mov     [rsp+arg_8], rsi
0x18002529d  push    rdi
0x18002529e  sub     rsp, 260h
0x1800252a5  mov     rax, cs:__security_cookie
0x1800252ac  xor     rax, rsp
0x1800252af  mov     [rsp+268h+var_18], rax
0x1800252b7  xor     eax, eax
0x1800252b9  mov     esi, r9d
0x1800252bc  mov     [rcx], ax
0x1800252bf  mov     rdi, rcx
0x1800252c2  test    r8b, 1
0x1800252c6  jnz     short loc_180025304
0x1800252c8  mov     r8d, 104h; nSize
0x1800252ce  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x1800252d3  lea     rcx, aProgramdata; "ProgramData"
0x1800252da  call    cs:__imp_GetEnvironmentVariableW
0x1800252e0  test    eax, eax
0x1800252e2  jnz     short loc_18002534A
0x1800252e4  mov     r9d, 104h
0x1800252ea  lea     r8, [rsp+268h+Buffer]
0x1800252ef  xor     edx, edx
0x1800252f1  lea     ecx, [rax+4]
0x1800252f4  call    cs:__imp_GetBasicProfileFolderPath
0x1800252fa  test    eax, eax
0x1800252fc  js      loc_1800253B0
0x180025302  jmp     short loc_18002534A
0x180025304  mov     [rsp+268h+var_238], al
0x180025308  call    cs:__imp_GetCurrentProcess
0x18002530e  mov     rcx, rax; ProcessHandle
0x180025311  lea     rdx, [rsp+268h+var_238]; void *
0x180025316  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18002531b  test    eax, eax
0x18002531d  js      short loc_18002532A
0x18002531f  cmp     [rsp+268h+var_238], 0
0x180025324  jnz     loc_1800253B4
0x18002532a  mov     r8d, 104h; nSize
0x180025330  lea     rdx, [rsp+268h+Buffer]; lpBuffer
0x180025335  lea     rcx, aLocalappdata; "LOCALAPPDATA"
0x18002533c  call    cs:__imp_GetEnvironmentVariableW
0x180025342  test    eax, eax
0x180025344  jz      loc_1800253D8
0x18002534a  lea     rax, aMicrosoftWindo; "Microsoft\\Windows\\Caches"
0x180025351  mov     edx, 104h; unsigned __int64
0x180025356  lea     r9, [rsp+268h+Buffer]
0x18002535b  mov     [rsp+268h+var_248], rax
0x180025360  lea     r8, aSS; "%s\\%s"
0x180025367  mov     rcx, rdi; unsigned __int16 *
0x18002536a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002536f  test    eax, eax
0x180025371  js      short loc_1800253B0
0x180025373  test    esi, esi
0x180025375  jnz     short loc_18002539D
0x180025377  mov     eax, 1
0x18002537c  mov     rcx, [rsp+268h+var_18]
0x180025384  xor     rcx, rsp; StackCookie
0x180025387  call    __security_check_cookie
0x18002538c  mov     rsi, [rsp+268h+arg_8]
0x180025394  add     rsp, 260h
0x18002539b  pop     rdi
0x18002539c  retn
0x18002539d  mov     rcx, rdi; unsigned __int16 *
0x1800253a0  call    ?_CreateDirectory@@YAHPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; _CreateDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x1800253a5  test    eax, eax
0x1800253a7  jz      short loc_180025377
0x1800253a9  cmp     eax, 0B7h
0x1800253ae  jz      short loc_180025377
0x1800253b0  xor     eax, eax
0x1800253b2  jmp     short loc_18002537C
0x1800253b4  xor     edx, edx
0x1800253b6  lea     r8, [rsp+268h+Buffer]
0x1800253bb  mov     r9d, 104h
0x1800253c1  lea     ecx, [rdx+8]
0x1800253c4  call    cs:__imp_GetBasicProfileFolderPath
0x1800253ca  not     eax
0x1800253cc  shr     eax, 1Fh
0x1800253cf  test    eax, eax
0x1800253d1  jz      short loc_18002537C
0x1800253d3  jmp     loc_18002534A
0x1800253d8  xor     edx, edx
0x1800253da  lea     r8, [rsp+268h+Buffer]
0x1800253df  mov     r9d, 104h
0x1800253e5  lea     ecx, [rdx+6]
0x1800253e8  call    cs:__imp_GetBasicProfileFolderPath
0x1800253ee  test    eax, eax
0x1800253f0  jns     loc_18002534A
0x1800253f6  xor     eax, eax
0x1800253f8  jmp     short loc_1800253CF
```
