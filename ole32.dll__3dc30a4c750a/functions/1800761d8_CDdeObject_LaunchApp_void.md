# CDdeObject::LaunchApp(void)

- ea: `0x1800761d8`
- end: `0x180076462`
- name: `?LaunchApp@CDdeObject@@AEAAHXZ`
- size: `650`
- prototype: `int __fastcall(CDdeObject *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800748e0`
- `0x180078860`

## callees

- `0x18001248c`
- `0x18001b810`
- `0x180052390`
- `0x180053014`
- `0x180075c40`
- `0x1800761d8`
- `0x1800778c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076408`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800763e1`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800763e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007641e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076413`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007641e`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18007628d`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18007628d`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x1800762b0`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x1800762b0`
- `USER32!WaitForInputIdle` at `0x1800763f7`
- `USER32!WaitForInputIdle` at `0x1800763f7`

## pseudocode

```c
__int64 __fastcall CDdeObject::LaunchApp(CDdeObject *this)
{
  unsigned __int16 m_aExeName; // cx
  const wchar_t *v3; // rax
  const wchar_t *v4; // rax
  unsigned int v5; // edi
  DWORD v6; // eax
  int v7; // r8d
  _PROCESS_INFORMATION procInfo; // [rsp+50h] [rbp-B0h] BYREF
  _STARTUPINFOW startInfo; // [rsp+70h] [rbp-90h] BYREF
  wchar_t cmdline[280]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t exeName[536]; // [rsp+310h] [rbp+210h] BYREF

  memset(&procInfo, 0, sizeof(procInfo));
  memset_0(exeName, 0, 0x42Au);
  memset_0(&startInfo, 0, sizeof(startInfo));
  m_aExeName = this->m_aExeName;
  startInfo.cb = 104;
  startInfo.wShowWindow = 1;
  startInfo.dwFlags = 1;
  this->m_fDidLaunchApp = 0;
  if ( !m_aExeName )
    return 0;
  v3 = wAtomName(m_aExeName);
  if ( SearchPathW(0, v3, 0, 0x215u, exeName, 0) - 1 > 0x214 )
    GlobalGetAtomNameW(this->m_aExeName, exeName, 533);
  if ( StringCchCopyW(cmdline, 0x111u, EMB_STR) < 0 )
    return 0;
  if ( this->m_ulObjType == 1 )
  {
    v4 = wAtomName(this->m_aTopic);
    if ( !v4 || StringCchCatW(cmdline, 0x111u, v4) < 0 )
      return 0;
  }
  if ( *(_QWORD *)&this->m_clsid.Data1 == *(_QWORD *)&CLSID_ExcelWorksheet.Data1
    && *(_QWORD *)this->m_clsid.Data4 == *(_QWORD *)CLSID_ExcelWorksheet.Data4
    || *(_QWORD *)&this->m_clsid.Data1 == *(_QWORD *)&CLSID_ExcelMacrosheet.Data1
    && *(_QWORD *)this->m_clsid.Data4 == *(_QWORD *)CLSID_ExcelMacrosheet.Data4
    || *(_QWORD *)&this->m_clsid.Data1 == *(_QWORD *)&CLSID_ExcelChart.Data1
    && *(_QWORD *)this->m_clsid.Data4 == *(_QWORD *)CLSID_ExcelChart.Data4
    || *(_QWORD *)&this->m_clsid.Data1 == *(_QWORD *)&CLSID_PBrush.Data1
    && *(_QWORD *)this->m_clsid.Data4 == *(_QWORD *)CLSID_PBrush.Data4 )
  {
    startInfo.wShowWindow = 7;
  }
  if ( StringCchCatW(exeName, 0x215u, cmdline) < 0 )
    return 0;
  v5 = CreateProcessW(0, exeName, 0, 0, 0, 0, 0, 0, &startInfo, &procInfo);
  if ( v5 )
  {
    v6 = WaitForInputIdle(procInfo.hProcess, 0x7530u);
    if ( v6 )
    {
      if ( v6 != 258 )
        GetLastError();
    }
    CloseHandle(procInfo.hProcess);
    CloseHandle(procInfo.hThread);
    CDdeObject::DeclareVisibility(this, 0, v7);
    this->m_fDidLaunchApp = 1;
  }
  return v5;
}

```

## disassembly

```asm
0x1800761d8  mov     [rsp-8+arg_8], rbx
0x1800761dd  mov     [rsp-8+arg_10], rsi
0x1800761e2  push    rbp
0x1800761e3  push    rdi
0x1800761e4  push    r15
0x1800761e6  lea     rbp, [rsp-650h]
0x1800761ee  sub     rsp, 750h
0x1800761f5  mov     rax, cs:__security_cookie
0x1800761fc  xor     rax, rsp
0x1800761ff  mov     [rbp+660h+var_20], rax
0x180076206  mov     rbx, this
0x180076209  xorps   xmm0, xmm0
0x18007620c  xor     eax, eax
0x18007620e  lea     this, [rbp+660h+exeName]; void *
0x180076215  xor     edx, edx; Val
0x180076217  mov     qword ptr [rsp+760h+procInfo.dwProcessId], rax
0x18007621c  mov     r8d, 42Ah; Size
0x180076222  movups  xmmword ptr [rsp+760h+procInfo.hProcess], xmm0
0x180076227  call    memset_0
0x18007622c  mov     edi, 68h ; 'h'
0x180076231  lea     this, [rsp+760h+startInfo]; void *
0x180076236  mov     r8d, edi; Size
0x180076239  xor     edx, edx; Val
0x18007623b  call    memset_0
0x180076240  movzx   ecx, word ptr [rbx+92h]; atom
0x180076247  lea     r15d, [rdi-67h]
0x18007624b  xor     esi, esi
0x18007624d  mov     [rsp+760h+startInfo.cb], edi
0x180076251  mov     [rbp+660h+startInfo.wShowWindow], r15w
0x180076256  mov     [rbp+660h+startInfo.dwFlags], r15d
0x18007625a  mov     [rbx+0F0h], esi
0x180076260  test    cx, cx
0x180076263  jz      loc_180076439
0x180076269  call    ?wAtomName@@YAPEAGG@Z; wAtomName(ushort)
0x18007626e  mov     rdx, rax; lpFileName
0x180076271  mov     [rsp+760h+lpFilePart], rsi; lpFilePart
0x180076276  lea     rax, [rbp+660h+exeName]
0x18007627d  mov     r9d, 215h; nBufferLength
0x180076283  xor     r8d, r8d; lpExtension
0x180076286  mov     [rsp+760h+lpBuffer], rax; lpBuffer
0x18007628b  xor     ecx, ecx; lpPath
0x18007628d  call    cs:__imp_SearchPathW
0x180076293  dec     eax
0x180076295  cmp     eax, 214h
0x18007629a  jbe     short loc_1800762B6
0x18007629c  movzx   ecx, word ptr [rbx+92h]; nAtom
0x1800762a3  lea     rdx, [rbp+660h+exeName]; lpBuffer
0x1800762aa  mov     r8d, 215h; nSize
0x1800762b0  call    cs:__imp_GlobalGetAtomNameW
0x1800762b6  mov     edi, 111h
0x1800762bb  lea     r8, EMB_STR; pszSrc
0x1800762c2  mov     edx, edi; cchDest
0x1800762c4  lea     this, [rbp+660h+cmdline]; pszDest
0x1800762c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800762cd  test    eax, eax
0x1800762cf  js      loc_180076439
0x1800762d5  cmp     [rbx+7Ch], r15d
0x1800762d9  jnz     short loc_180076306
0x1800762db  movzx   ecx, word ptr [rbx+94h]; atom
0x1800762e2  call    ?wAtomName@@YAPEAGG@Z; wAtomName(ushort)
0x1800762e7  test    rax, rax
0x1800762ea  jz      loc_180076439
0x1800762f0  mov     r8, rax; pszSrc
0x1800762f3  lea     this, [rbp+660h+cmdline]; pszDest
0x1800762f7  mov     edx, edi; cchDest
0x1800762f9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800762fe  test    eax, eax
0x180076300  js      loc_180076439
0x180076306  mov     rax, [rbx+80h]
0x18007630d  cmp     rax, qword ptr cs:CLSID_ExcelWorksheet.Data1
0x180076314  jnz     short loc_180076326
0x180076316  mov     rax, [rbx+88h]
0x18007631d  cmp     rax, qword ptr cs:CLSID_ExcelWorksheet.Data4
0x180076324  jz      short loc_180076386
0x180076326  mov     rax, [rbx+80h]
0x18007632d  cmp     rax, qword ptr cs:CLSID_ExcelMacrosheet.Data1
0x180076334  jnz     short loc_180076346
0x180076336  mov     rax, [rbx+88h]
0x18007633d  cmp     rax, qword ptr cs:CLSID_ExcelMacrosheet.Data4
0x180076344  jz      short loc_180076386
0x180076346  mov     rax, [rbx+80h]
0x18007634d  cmp     rax, qword ptr cs:CLSID_ExcelChart.Data1
0x180076354  jnz     short loc_180076366
0x180076356  mov     rax, [rbx+88h]
0x18007635d  cmp     rax, qword ptr cs:CLSID_ExcelChart.Data4
0x180076364  jz      short loc_180076386
0x180076366  mov     rax, [rbx+80h]
0x18007636d  cmp     rax, qword ptr cs:CLSID_PBrush.Data1
0x180076374  jnz     short loc_18007638F
0x180076376  mov     rax, [rbx+88h]
0x18007637d  cmp     rax, qword ptr cs:CLSID_PBrush.Data4
0x180076384  jnz     short loc_18007638F
0x180076386  mov     eax, 7
0x18007638b  mov     [rbp+660h+startInfo.wShowWindow], ax
0x18007638f  lea     r8, [rbp+660h+cmdline]; pszSrc
0x180076393  mov     edx, 215h; cchDest
0x180076398  lea     this, [rbp+660h+exeName]; pszDest
0x18007639f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800763a4  test    eax, eax
0x1800763a6  js      loc_180076439
0x1800763ac  lea     rax, [rsp+760h+procInfo]
0x1800763b1  xor     r9d, r9d; lpThreadAttributes
0x1800763b4  mov     [rsp+760h+lpProcessInformation], rax; lpProcessInformation
0x1800763b9  lea     rdx, [rbp+660h+exeName]; lpCommandLine
0x1800763c0  lea     rax, [rsp+760h+startInfo]
0x1800763c5  xor     r8d, r8d; lpProcessAttributes
0x1800763c8  mov     [rsp+760h+lpStartupInfo], rax; lpStartupInfo
0x1800763cd  xor     ecx, ecx; lpApplicationName
0x1800763cf  mov     [rsp+760h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x1800763d4  mov     [rsp+760h+lpEnvironment], rsi; lpEnvironment
0x1800763d9  mov     dword ptr [rsp+760h+lpFilePart], esi; dwCreationFlags
0x1800763dd  mov     dword ptr [rsp+760h+lpBuffer], esi; bInheritHandles
0x1800763e1  call    cs:__imp_CreateProcessW
0x1800763e7  mov     edi, eax
0x1800763e9  test    eax, eax
0x1800763eb  jz      short loc_180076435
0x1800763ed  mov     this, [rsp+760h+procInfo.hProcess]; hProcess
0x1800763f2  mov     edx, 7530h; dwMilliseconds
0x1800763f7  call    cs:__imp_WaitForInputIdle
0x1800763fd  test    eax, eax
0x1800763ff  jz      short loc_18007640E
0x180076401  cmp     eax, 102h
0x180076406  jz      short loc_18007640E
0x180076408  call    cs:__imp_GetLastError
0x18007640e  mov     this, [rsp+760h+procInfo.hProcess]; hObject
0x180076413  call    cs:__imp_CloseHandle
0x180076419  mov     this, [rsp+760h+procInfo.hThread]; hObject
0x18007641e  call    cs:__imp_CloseHandle
0x180076424  xor     edx, edx; f
0x180076426  mov     this, rbx; this
0x180076429  call    ?DeclareVisibility@CDdeObject@@AEAAJHH@Z; CDdeObject::DeclareVisibility(int,int)
0x18007642e  mov     [rbx+0F0h], r15d
0x180076435  mov     eax, edi
0x180076437  jmp     short loc_18007643B
0x180076439  xor     eax, eax
0x18007643b  mov     this, [rbp+660h+var_20]
0x180076442  xor     this, rsp; StackCookie
0x180076445  call    __security_check_cookie
0x18007644a  lea     r11, [rsp+760h+var_10]
0x180076452  mov     rbx, [r11+28h]
0x180076456  mov     rsi, [r11+30h]
0x18007645a  mov     rsp, r11
0x18007645d  pop     r15
0x18007645f  pop     rdi
0x180076460  pop     rbp
0x180076461  retn
```
