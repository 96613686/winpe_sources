# LaunchHelpPane(ushort const *)

- ea: `0x18000d760`
- end: `0x18000d8e7`
- name: `?LaunchHelpPane@@YAJPEBG@Z`
- size: `391`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x18000dfe4`

## callees

- `0x180003d50`
- `0x180007ee4`
- `0x18000d760`
- `0x18000eb28`
- `0x18001f652`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d872`
- `KERNEL32!GetLastError` at `0x18000d872`
- `KERNEL32!CloseHandle` at `0x18000d8ca`
- `KERNEL32!CloseHandle` at `0x18000d8ca`
- `ole32!CoTaskMemAlloc` at `0x18000d801`
- `ole32!CoTaskMemAlloc` at `0x18000d801`
- `ole32!CoTaskMemFree` at `0x18000d8b0`
- `ole32!CoTaskMemFree` at `0x18000d8b0`
- `SHELL32!ShellExecuteExW` at `0x18000d868`
- `SHELL32!ShellExecuteExW` at `0x18000d868`

## string_xrefs

- `0x18000d81c`: `ndfapi.dll,NdfRunDllHelpTopic %s`
- `0x18000d82e`: `%windir%\system32\rundll32.exe`

## pseudocode

```c
__int64 __fastcall LaunchHelpPane(const unsigned __int16 *a1)
{
  const unsigned __int16 *v2; // rax
  __int64 v3; // rcx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdi
  unsigned int v6; // eax
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rsi
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  int v12; // r8d
  signed int LastError; // eax
  unsigned int v14; // eax
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-98h] BYREF

  if ( !a1 || !*a1 )
    return 2147942487LL;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v2 = a1;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v4 = (0x7FFFFFFF - v3) & ((unsigned __int128)-(__int128)(unsigned __int64)v3 >> 64);
  if ( v3 )
  {
    v5 = v4 + 50;
    if ( v4 + 50 < v4 )
    {
LABEL_21:
      v10 = -2147024362;
      goto LABEL_22;
    }
  }
  else
  {
    __int2c();
    v5 = 50;
  }
  v6 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v5);
  if ( v6 + 1 < v6 )
    goto LABEL_21;
  v7 = 2LL * (v6 + 1);
  if ( v7 > 0xFFFFFFFF )
    goto LABEL_21;
  v8 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v7);
  v9 = v8;
  if ( v8 )
  {
    StringCchPrintfW(v8, v5, L"ndfapi.dll,NdfRunDllHelpTopic %s", a1);
    pExecInfo.cbSize = 112;
    pExecInfo.lpFile = L"%windir%\\system32\\rundll32.exe";
    pExecInfo.fMask = 1600;
    pExecInfo.lpVerb = L"open";
    pExecInfo.nShow = 1;
    pExecInfo.lpParameters = v9;
    if ( !ShellExecuteExW(&pExecInfo) )
      goto LABEL_14;
    v14 = NetDiagClientWaitForObjects(v11, &pExecInfo.hProcess, v12, 0xFFFFFFFF);
    if ( v14 )
    {
      if ( v14 != 258 )
      {
LABEL_14:
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_20;
      }
      v10 = -2147024638;
    }
    else
    {
      v10 = 0;
    }
LABEL_20:
    CoTaskMemFree(v9);
    goto LABEL_22;
  }
  v10 = -2147024882;
LABEL_22:
  if ( pExecInfo.hProcess )
    CloseHandle(pExecInfo.hProcess);
  return v10;
}

```

## disassembly

```asm
0x18000d760  push    rbx
0x18000d762  push    rbp
0x18000d763  push    rsi
0x18000d764  push    rdi
0x18000d765  push    r14
0x18000d767  sub     rsp, 90h
0x18000d76e  xor     ebp, ebp
0x18000d770  mov     rbx, rcx
0x18000d773  test    rcx, rcx
0x18000d776  jz      loc_18000D8D4
0x18000d77c  cmp     bp, [rcx]
0x18000d77f  jz      loc_18000D8D4
0x18000d785  xor     edx, edx; Val
0x18000d787  lea     r8d, [rbp+70h]; Size
0x18000d78b  lea     rcx, [rsp+0B8h+pExecInfo]; void *
0x18000d790  call    memset_0
0x18000d795  mov     r8d, 7FFFFFFFh
0x18000d79b  mov     rax, rbx
0x18000d79e  mov     ecx, r8d
0x18000d7a1  cmp     [rax], bp
0x18000d7a4  jz      short loc_18000D7B0
0x18000d7a6  add     rax, 2
0x18000d7aa  sub     rcx, 1
0x18000d7ae  jnz     short loc_18000D7A1
0x18000d7b0  sub     r8, rcx
0x18000d7b3  mov     rax, rcx
0x18000d7b6  neg     rax
0x18000d7b9  sbb     rdx, rdx
0x18000d7bc  and     rdx, r8
0x18000d7bf  test    rcx, rcx
0x18000d7c2  jnz     short loc_18000D7CB
0x18000d7c4  int     2Ch; Windows NT - assertion failure
0x18000d7c6  lea     edi, [rcx+32h]
0x18000d7c9  jmp     short loc_18000D7D8
0x18000d7cb  lea     rdi, [rdx+32h]
0x18000d7cf  cmp     rdi, rdx
0x18000d7d2  jb      loc_18000D8B8
0x18000d7d8  mov     rcx, rdi
0x18000d7db  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d7e0  lea     ecx, [rax+1]
0x18000d7e3  cmp     ecx, eax
0x18000d7e5  jb      loc_18000D8B8
0x18000d7eb  mov     eax, ecx
0x18000d7ed  mov     r14d, 0FFFFFFFFh
0x18000d7f3  add     rax, rax
0x18000d7f6  cmp     rax, r14
0x18000d7f9  ja      loc_18000D8B8
0x18000d7ff  mov     ecx, eax; cb
0x18000d801  call    cs:__imp_CoTaskMemAlloc
0x18000d807  mov     rsi, rax
0x18000d80a  test    rax, rax
0x18000d80d  jnz     short loc_18000D819
0x18000d80f  mov     ebx, 8007000Eh
0x18000d814  jmp     loc_18000D8BD
0x18000d819  mov     r9, rbx
0x18000d81c  lea     r8, aNdfapiDllNdfru; "ndfapi.dll,NdfRunDllHelpTopic %s"
0x18000d823  mov     rdx, rdi; unsigned __int64
0x18000d826  mov     rcx, rsi; unsigned __int16 *
0x18000d829  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000d82e  lea     rax, aWindirSystem32; "%windir%\\system32\\rundll32.exe"
0x18000d835  mov     [rsp+0B8h+pExecInfo.cbSize], 70h ; 'p'
0x18000d83d  mov     [rsp+0B8h+pExecInfo.lpFile], rax
0x18000d842  lea     rcx, [rsp+0B8h+pExecInfo]; pExecInfo
0x18000d847  lea     rax, aOpen; "open"
0x18000d84e  mov     [rsp+0B8h+pExecInfo.fMask], 640h
0x18000d856  mov     [rsp+0B8h+pExecInfo.lpVerb], rax
0x18000d85b  mov     [rsp+0B8h+pExecInfo.nShow], 1
0x18000d863  mov     [rsp+0B8h+pExecInfo.lpParameters], rsi
0x18000d868  call    cs:__imp_ShellExecuteExW
0x18000d86e  test    eax, eax
0x18000d870  jnz     short loc_18000D889
0x18000d872  call    cs:__imp_GetLastError
0x18000d878  mov     ebx, eax
0x18000d87a  test    eax, eax
0x18000d87c  jle     short loc_18000D8AD
0x18000d87e  movzx   ebx, ax
0x18000d881  or      ebx, 80070000h
0x18000d887  jmp     short loc_18000D8AD
0x18000d889  mov     r9d, r14d; unsigned int
0x18000d88c  lea     rdx, [rsp+0B8h+pExecInfo.hProcess]; void **
0x18000d894  call    ?NetDiagClientWaitForObjects@@YAKKPEBQEAXHK@Z; NetDiagClientWaitForObjects(ulong,void * const *,int,ulong)
0x18000d899  test    eax, eax
0x18000d89b  jz      short loc_18000D8AB
0x18000d89d  cmp     eax, 102h
0x18000d8a2  jnz     short loc_18000D872
0x18000d8a4  mov     ebx, 80070102h
0x18000d8a9  jmp     short loc_18000D8AD
0x18000d8ab  mov     ebx, ebp
0x18000d8ad  mov     rcx, rsi; pv
0x18000d8b0  call    cs:__imp_CoTaskMemFree
0x18000d8b6  jmp     short loc_18000D8BD
0x18000d8b8  mov     ebx, 80070216h
0x18000d8bd  mov     rcx, [rsp+0B8h+pExecInfo.hProcess]; hObject
0x18000d8c5  test    rcx, rcx
0x18000d8c8  jz      short loc_18000D8D0
0x18000d8ca  call    cs:__imp_CloseHandle
0x18000d8d0  mov     eax, ebx
0x18000d8d2  jmp     short loc_18000D8D9
0x18000d8d4  mov     eax, 80070057h
0x18000d8d9  add     rsp, 90h
0x18000d8e0  pop     r14
0x18000d8e2  pop     rdi
0x18000d8e3  pop     rsi
0x18000d8e4  pop     rbp
0x18000d8e5  pop     rbx
0x18000d8e6  retn
```
