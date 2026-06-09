# PerfDiagDm::ResolverUIBase::LaunchEventViewer(int)

- ea: `0x1800be4d4`
- end: `0x1800be6ad`
- name: `?LaunchEventViewer@ResolverUIBase@PerfDiagDm@@IEAAJH@Z`
- size: `473`
- prototype: `__int64 __fastcall(PerfDiagDm::ResolverUIBase *__hidden this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800bf304`

## callees

- `0x180043030`
- `0x180081d2c`
- `0x1800be4d4`
- `0x1800bf224`
- `0x1800cf032`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be67e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800be67e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be569`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800be569`
- `SHELL32!ShellExecuteExW` at `0x1800be65d`
- `SHELL32!ShellExecuteExW` at `0x1800be65d`

## pseudocode

```c
int __fastcall PerfDiagDm::ResolverUIBase::LaunchEventViewer(PerfDiagDm::ResolverUIBase *this, unsigned int a2)
{
  int result; // eax
  UINT SystemDirectoryW; // eax
  size_t v5; // r9
  size_t v6; // r9
  size_t v7; // r9
  int v8; // ebx
  SHELLEXECUTEINFOW pExecInfo; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 v10[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v11[280]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v13[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  *(_OWORD *)v10 = *(_OWORD *)L"eventvwr.exe";
  *(_OWORD *)&v10[5] = *(_OWORD *)L"vwr.exe";
  memset_0(v13, 0, 0x20Au);
  result = StringCbPrintfW(
             v13,
             0x105u,
             L" /c:Microsoft-Windows-Diagnostics-Performance/Operational /f:*[System[(EventID=%d)]]",
             a2);
  if ( result >= 0 )
  {
    memset_0(Buffer, 0, 0x20Au);
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    if ( SystemDirectoryW - 1 > 0x102 )
    {
      return -2147467259;
    }
    else
    {
      if ( Buffer[SystemDirectoryW - 1] != 92 )
        Buffer[SystemDirectoryW] = 92;
      memset_0(v11, 0, 0x224u);
      result = StringCchCopyW(v11, 0x112u, L"\"");
      if ( result >= 0 )
      {
        result = StringCchCatW(v11, 0x112u, Buffer, v5);
        if ( result >= 0 )
        {
          result = StringCchCatW(v11, 0x112u, v10, v6);
          if ( result >= 0 )
          {
            result = StringCchCatW(v11, 0x112u, L"\"", v7);
            if ( result >= 0 )
            {
              memset_0(&pExecInfo, 0, sizeof(pExecInfo));
              pExecInfo.cbSize = 112;
              pExecInfo.lpFile = v11;
              pExecInfo.hwnd = 0;
              pExecInfo.lpParameters = v13;
              pExecInfo.lpDirectory = 0;
              pExecInfo.nShow = 1;
              if ( !ShellExecuteExW(&pExecInfo) || (v8 = 0, SLODWORD(pExecInfo.hInstApp) < 32) )
                v8 = 1;
              if ( pExecInfo.hProcess )
                CloseHandle(pExecInfo.hProcess);
              return v8;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800be4d4  mov     [rsp-8+arg_0], rbx
0x1800be4d9  push    rbp
0x1800be4da  lea     rbp, [rsp-610h]
0x1800be4e2  sub     rsp, 710h
0x1800be4e9  mov     rax, cs:__security_cookie
0x1800be4f0  xor     rax, rsp
0x1800be4f3  mov     [rbp+610h+var_10], rax
0x1800be4fa  movups  xmm0, xmmword ptr cs:aEventvwrExe; "eventvwr.exe"
0x1800be501  mov     ebx, edx
0x1800be503  xor     edx, edx; Val
0x1800be505  movups  xmm1, xmmword ptr cs:aEventvwrExe+0Ah; "vwr.exe"
0x1800be50c  mov     r8d, 20Ah; Size
0x1800be512  lea     rcx, [rbp+610h+var_220]; void *
0x1800be519  movups  xmmword ptr [rbp+610h+var_680], xmm0
0x1800be51d  movups  xmmword ptr [rbp+610h+var_680+0Ah], xmm1
0x1800be521  call    memset_0
0x1800be526  mov     r9d, ebx
0x1800be529  lea     r8, aCMicrosoftWind; " /c:Microsoft-Windows-Diagnostics-Perfo"...
0x1800be530  mov     edx, 105h; unsigned __int64
0x1800be535  lea     rcx, [rbp+610h+var_220]; unsigned __int16 *
0x1800be53c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800be541  test    eax, eax
0x1800be543  js      loc_1800BE68D
0x1800be549  xor     edx, edx; Val
0x1800be54b  lea     rcx, [rbp+610h+Buffer]; void *
0x1800be552  mov     r8d, 20Ah; Size
0x1800be558  call    memset_0
0x1800be55d  mov     edx, 104h; uSize
0x1800be562  lea     rcx, [rbp+610h+Buffer]; lpBuffer
0x1800be569  call    cs:__imp_GetSystemDirectoryW
0x1800be56f  lea     ecx, [rax-1]
0x1800be572  cmp     ecx, 102h
0x1800be578  ja      loc_1800BE688
0x1800be57e  lea     edx, [rax-1]
0x1800be581  mov     ecx, 5Ch ; '\'
0x1800be586  cmp     [rbp+rdx*2+610h+Buffer], cx
0x1800be58e  jz      short loc_1800BE59A
0x1800be590  mov     eax, eax
0x1800be592  mov     [rbp+rax*2+610h+Buffer], cx
0x1800be59a  xor     edx, edx; Val
0x1800be59c  lea     rcx, [rbp+610h+var_660]; void *
0x1800be5a0  mov     r8d, 224h; Size
0x1800be5a6  call    memset_0
0x1800be5ab  mov     ebx, 112h
0x1800be5b0  lea     r8, asc_1800E87D8; "\""
0x1800be5b7  mov     edx, ebx; unsigned __int64
0x1800be5b9  lea     rcx, [rbp+610h+var_660]; unsigned __int16 *
0x1800be5bd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800be5c2  test    eax, eax
0x1800be5c4  js      loc_1800BE68D
0x1800be5ca  lea     r8, [rbp+610h+Buffer]; unsigned __int16 *
0x1800be5d1  mov     edx, ebx; unsigned __int64
0x1800be5d3  lea     rcx, [rbp+610h+var_660]; unsigned __int16 *
0x1800be5d7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800be5dc  test    eax, eax
0x1800be5de  js      loc_1800BE68D
0x1800be5e4  lea     r8, [rbp+610h+var_680]; unsigned __int16 *
0x1800be5e8  mov     edx, ebx; unsigned __int64
0x1800be5ea  lea     rcx, [rbp+610h+var_660]; unsigned __int16 *
0x1800be5ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800be5f3  test    eax, eax
0x1800be5f5  js      loc_1800BE68D
0x1800be5fb  lea     r8, asc_1800E87D8; "\""
0x1800be602  mov     edx, ebx; unsigned __int64
0x1800be604  lea     rcx, [rbp+610h+var_660]; unsigned __int16 *
0x1800be608  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800be60d  test    eax, eax
0x1800be60f  js      short loc_1800BE68D
0x1800be611  mov     ebx, 70h ; 'p'
0x1800be616  lea     rcx, [rsp+710h+pExecInfo]; void *
0x1800be61b  mov     r8d, ebx; Size
0x1800be61e  xor     edx, edx; Val
0x1800be620  call    memset_0
0x1800be625  lea     rax, [rbp+610h+var_660]
0x1800be629  mov     [rsp+710h+pExecInfo.cbSize], ebx
0x1800be62d  mov     [rsp+710h+pExecInfo.lpFile], rax
0x1800be632  lea     rcx, [rsp+710h+pExecInfo]; pExecInfo
0x1800be637  lea     rax, [rbp+610h+var_220]
0x1800be63e  mov     [rsp+710h+pExecInfo.hwnd], 0
0x1800be647  mov     [rsp+710h+pExecInfo.lpParameters], rax
0x1800be64c  mov     [rsp+710h+pExecInfo.lpDirectory], 0
0x1800be655  mov     [rsp+710h+pExecInfo.nShow], 1
0x1800be65d  call    cs:__imp_ShellExecuteExW
0x1800be663  test    eax, eax
0x1800be665  jz      short loc_1800BE670
0x1800be667  xor     ebx, ebx
0x1800be669  cmp     dword ptr [rsp+710h+pExecInfo.hInstApp], 20h ; ' '
0x1800be66e  jge     short loc_1800BE675
0x1800be670  mov     ebx, 1
0x1800be675  mov     rcx, [rbp+610h+pExecInfo.hProcess]; hObject
0x1800be679  test    rcx, rcx
0x1800be67c  jz      short loc_1800BE684
0x1800be67e  call    cs:__imp_CloseHandle
0x1800be684  mov     eax, ebx
0x1800be686  jmp     short loc_1800BE68D
0x1800be688  mov     eax, 80004005h
0x1800be68d  mov     rcx, [rbp+610h+var_10]
0x1800be694  xor     rcx, rsp; StackCookie
0x1800be697  call    __security_check_cookie
0x1800be69c  mov     rbx, [rsp+710h+arg_0]
0x1800be6a4  add     rsp, 710h
0x1800be6ab  pop     rbp
0x1800be6ac  retn
```
