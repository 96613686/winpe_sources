# SetDataFile(void)

- ea: `0x180025800`
- end: `0x18002598a`
- name: `?SetDataFile@@YAJXZ`
- size: `394`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18001fa58`

## callees

- `0x1800256b8`
- `0x180025800`
- `0x180025990`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800258c3`
- `msvcrt!_stricmp` at `0x1800258c3`
- `msvcrt!strrchr` at `0x1800258aa`
- `msvcrt!strrchr` at `0x1800258aa`
- `KERNEL32!GetModuleHandleA` at `0x180025853`
- `KERNEL32!GetModuleHandleA` at `0x180025853`
- `KERNEL32!GetModuleFileNameA` at `0x180025866`
- `KERNEL32!GetModuleFileNameA` at `0x180025866`
- `KERNEL32!GetLastError` at `0x180025870`
- `KERNEL32!GetLastError` at `0x180025870`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800258f3`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18002591c`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800258f3`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18002591c`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800258d7`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180025906`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800258d7`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180025906`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18002592a`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180025943`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18002592a`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180025943`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002582a`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180025835`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002582a`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180025835`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180025958`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180025962`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180025958`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180025962`

## string_xrefs

- `0x18002584c`: `metadata.dll`
- `0x1800258bc`: `metadata.dll`
- `0x1800258e8`: `MetaBase.xml`

## pseudocode

```c
__int64 SetDataFile(void)
{
  HMODULE ModuleHandleA; // rax
  signed int LastError; // eax
  signed int v2; // ebx
  char *v3; // rax
  _BYTE *v4; // rbx
  const CHAR *StrA; // rax
  const CHAR *v6; // rax
  _BYTE v8[128]; // [rsp+20h] [rbp-E0h] BYREF
  CHAR v9[128]; // [rsp+A0h] [rbp-60h] BYREF
  CHAR Filename[272]; // [rsp+120h] [rbp+20h] BYREF

  STRAU::STRAU((STRAU *)v9);
  STRAU::STRAU((STRAU *)v8);
  memset_0(Filename, 0, 0x105u);
  ModuleHandleA = GetModuleHandleA("metadata.dll");
  if ( GetModuleFileNameA(ModuleHandleA, Filename, 0x104u) )
  {
    if ( !Filename[259] && (v3 = strrchr(Filename, 92)) != 0 && (v4 = v3 + 1, !_stricmp(v3 + 1, "metadata.dll")) )
    {
      *v4 = 0;
      if ( STRAU::Copy((STRAU *)v9, Filename)
        && STRAU::Append((STRAU *)v9, "MetaBase.xml")
        && STRAU::Copy((STRAU *)v8, Filename)
        && STRAU::Append((STRAU *)v8, "MetaBack") )
      {
        StrA = STRAU::QueryStrA((STRAU *)v9);
        v2 = SetGlobalDataFileValues(StrA);
        if ( v2 >= 0 )
        {
          v6 = STRAU::QueryStrA((STRAU *)v8);
          v2 = SetBackupPath(v6);
        }
      }
      else
      {
        v2 = -2147024882;
      }
    }
    else
    {
      v2 = -2147467259;
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
  }
  STRAU::~STRAU((STRAU *)v8);
  STRAU::~STRAU((STRAU *)v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180025800  mov     [rsp-8+arg_0], rbx
0x180025805  push    rbp
0x180025806  lea     rbp, [rsp-140h]
0x18002580e  sub     rsp, 240h
0x180025815  mov     rax, cs:__security_cookie
0x18002581c  xor     rax, rsp
0x18002581f  mov     [rbp+140h+var_10], rax
0x180025826  lea     rcx, [rbp+140h+var_1A0]
0x18002582a  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180025830  lea     rcx, [rsp+240h+var_220]
0x180025835  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18002583b  xor     edx, edx; Val
0x18002583d  lea     rcx, [rbp+140h+Filename]; void *
0x180025841  mov     r8d, 105h; Size
0x180025847  call    memset_0
0x18002584c  lea     rcx, ModuleName; "metadata.dll"
0x180025853  call    cs:__imp_GetModuleHandleA
0x180025859  mov     r8d, 104h; nSize
0x18002585f  lea     rdx, [rbp+140h+Filename]; lpFilename
0x180025863  mov     rcx, rax; hModule
0x180025866  call    cs:__imp_GetModuleFileNameA
0x18002586c  test    eax, eax
0x18002586e  jnz     short loc_18002588E
0x180025870  call    cs:__imp_GetLastError
0x180025876  mov     ebx, eax
0x180025878  test    eax, eax
0x18002587a  jle     loc_180025953
0x180025880  movzx   ebx, ax
0x180025883  or      ebx, 80070000h
0x180025889  jmp     loc_180025953
0x18002588e  cmp     [rbp+140h+var_1D], 0
0x180025895  jz      short loc_1800258A1
0x180025897  mov     ebx, 80004005h
0x18002589c  jmp     loc_180025953
0x1800258a1  mov     edx, 5Ch ; '\'; Ch
0x1800258a6  lea     rcx, [rbp+140h+Filename]; Str
0x1800258aa  call    cs:__imp_strrchr
0x1800258b0  test    rax, rax
0x1800258b3  jz      short loc_180025897
0x1800258b5  lea     rbx, [rax+1]
0x1800258b9  mov     rcx, rbx; String1
0x1800258bc  lea     rdx, ModuleName; "metadata.dll"
0x1800258c3  call    cs:__imp__stricmp
0x1800258c9  test    eax, eax
0x1800258cb  jnz     short loc_180025897
0x1800258cd  lea     rdx, [rbp+140h+Filename]
0x1800258d1  mov     [rbx], al
0x1800258d3  lea     rcx, [rbp+140h+var_1A0]
0x1800258d7  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x1800258dd  test    eax, eax
0x1800258df  jnz     short loc_1800258E8
0x1800258e1  mov     ebx, 8007000Eh
0x1800258e6  jmp     short loc_180025953
0x1800258e8  lea     rdx, aMetabaseXml_0; "MetaBase.xml"
0x1800258ef  lea     rcx, [rbp+140h+var_1A0]
0x1800258f3  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x1800258f9  test    eax, eax
0x1800258fb  jz      short loc_1800258E1
0x1800258fd  lea     rdx, [rbp+140h+Filename]
0x180025901  lea     rcx, [rsp+240h+var_220]
0x180025906  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18002590c  test    eax, eax
0x18002590e  jz      short loc_1800258E1
0x180025910  lea     rdx, aMetaback; "MetaBack"
0x180025917  lea     rcx, [rsp+240h+var_220]
0x18002591c  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x180025922  test    eax, eax
0x180025924  jz      short loc_1800258E1
0x180025926  lea     rcx, [rbp+140h+var_1A0]
0x18002592a  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180025930  mov     rcx, rax; lpFileName
0x180025933  call    ?SetGlobalDataFileValues@@YAJPEAD@Z; SetGlobalDataFileValues(char *)
0x180025938  mov     ebx, eax
0x18002593a  test    eax, eax
0x18002593c  js      short loc_180025953
0x18002593e  lea     rcx, [rsp+240h+var_220]
0x180025943  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180025949  mov     rcx, rax; lpPathName
0x18002594c  call    ?SetBackupPath@@YAJPEAD@Z; SetBackupPath(char *)
0x180025951  mov     ebx, eax
0x180025953  lea     rcx, [rsp+240h+var_220]
0x180025958  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x18002595e  lea     rcx, [rbp+140h+var_1A0]
0x180025962  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180025968  mov     eax, ebx
0x18002596a  mov     rcx, [rbp+140h+var_10]
0x180025971  xor     rcx, rsp; StackCookie
0x180025974  call    __security_check_cookie
0x180025979  mov     rbx, [rsp+240h+arg_0]
0x180025981  add     rsp, 240h
0x180025988  pop     rbp
0x180025989  retn
```
