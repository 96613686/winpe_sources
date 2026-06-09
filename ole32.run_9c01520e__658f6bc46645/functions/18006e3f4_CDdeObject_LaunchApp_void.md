# CDdeObject::LaunchApp(void)

- ea: `0x18006e3f4`
- end: `0x18006e69e`
- name: `?LaunchApp@CDdeObject@@AEAAHXZ`
- size: `682`
- prototype: `int __fastcall(CDdeObject *this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006c6a0`
- `0x180071250`

## callees

- `0x18000fc2c`
- `0x18001a630`
- `0x180046460`
- `0x180047484`
- `0x18006ddc0`
- `0x18006e3f4`
- `0x18007009c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18006e615`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18006e615`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006e653`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18006e4a9`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18006e4a9`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18006e4d2`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18006e4d2`
- `USER32!WaitForInputIdle` at `0x18006e631`
- `USER32!WaitForInputIdle` at `0x18006e631`

## pseudocode

```c
__int64 __fastcall CDdeObject::LaunchApp(CDdeObject *this)
{
  unsigned __int16 m_aExeName; // cx
  const wchar_t *v3; // rax
  const wchar_t *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int v9; // edi
  int v10; // r8d
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
  v5 = *(_QWORD *)&this->m_clsid.Data1 - *(_QWORD *)&CLSID_ExcelWorksheet.Data1;
  if ( !v5 )
    v5 = *(_QWORD *)this->m_clsid.Data4 - *(_QWORD *)CLSID_ExcelWorksheet.Data4;
  if ( !v5 )
    goto LABEL_20;
  v6 = *(_QWORD *)&this->m_clsid.Data1 - *(_QWORD *)&CLSID_ExcelMacrosheet.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)this->m_clsid.Data4 - *(_QWORD *)CLSID_ExcelMacrosheet.Data4;
  if ( !v6 )
    goto LABEL_20;
  v7 = *(_QWORD *)&this->m_clsid.Data1 - *(_QWORD *)&CLSID_ExcelChart.Data1;
  if ( !v7 )
    v7 = *(_QWORD *)this->m_clsid.Data4 - *(_QWORD *)CLSID_ExcelChart.Data4;
  if ( !v7 )
    goto LABEL_20;
  v8 = *(_QWORD *)&this->m_clsid.Data1 - *(_QWORD *)&CLSID_PBrush.Data1;
  if ( !v8 )
    v8 = *(_QWORD *)this->m_clsid.Data4 - *(_QWORD *)CLSID_PBrush.Data4;
  if ( !v8 )
LABEL_20:
    startInfo.wShowWindow = 7;
  if ( StringCchCatW(exeName, 0x215u, cmdline) < 0 )
    return 0;
  v9 = CreateProcessW(0, exeName, 0, 0, 0, 0, 0, 0, &startInfo, &procInfo);
  if ( v9 )
  {
    WaitForInputIdle(procInfo.hProcess, 0x7530u);
    CloseHandle(procInfo.hProcess);
    CloseHandle(procInfo.hThread);
    CDdeObject::DeclareVisibility(this, 0, v10);
    this->m_fDidLaunchApp = 1;
  }
  return v9;
}

```

## disassembly

```asm
0x18006e3f4  mov     [rsp-8+arg_8], rbx
0x18006e3f9  mov     [rsp-8+arg_10], rsi
0x18006e3fe  push    rbp
0x18006e3ff  push    rdi
0x18006e400  push    r15
0x18006e402  lea     rbp, [rsp-650h]
0x18006e40a  sub     rsp, 750h
0x18006e411  mov     rax, cs:__security_cookie
0x18006e418  xor     rax, rsp
0x18006e41b  mov     [rbp+660h+var_20], rax
0x18006e422  mov     rbx, this
0x18006e425  xorps   xmm0, xmm0
0x18006e428  xor     eax, eax
0x18006e42a  lea     this, [rbp+660h+exeName]; void *
0x18006e431  xor     edx, edx; Val
0x18006e433  mov     qword ptr [rsp+760h+procInfo.dwProcessId], rax
0x18006e438  mov     r8d, 42Ah; Size
0x18006e43e  movups  xmmword ptr [rsp+760h+procInfo.hProcess], xmm0
0x18006e443  call    memset_0
0x18006e448  mov     edi, 68h ; 'h'
0x18006e44d  lea     this, [rsp+760h+startInfo]; void *
0x18006e452  mov     r8d, edi; Size
0x18006e455  xor     edx, edx; Val
0x18006e457  call    memset_0
0x18006e45c  movzx   ecx, word ptr [rbx+92h]; atom
0x18006e463  lea     r15d, [rdi-67h]
0x18006e467  xor     esi, esi
0x18006e469  mov     [rsp+760h+startInfo.cb], edi
0x18006e46d  mov     [rbp+660h+startInfo.wShowWindow], r15w
0x18006e472  mov     [rbp+660h+startInfo.dwFlags], r15d
0x18006e476  mov     [rbx+0F0h], esi
0x18006e47c  test    cx, cx
0x18006e47f  jz      loc_18006E674
0x18006e485  call    ?wAtomName@@YAPEAGG@Z; wAtomName(ushort)
0x18006e48a  mov     rdx, rax; lpFileName
0x18006e48d  mov     [rsp+760h+lpFilePart], rsi; lpFilePart
0x18006e492  lea     rax, [rbp+660h+exeName]
0x18006e499  mov     r9d, 215h; nBufferLength
0x18006e49f  xor     r8d, r8d; lpExtension
0x18006e4a2  mov     [rsp+760h+lpBuffer], rax; lpBuffer
0x18006e4a7  xor     ecx, ecx; lpPath
0x18006e4a9  call    cs:__imp_SearchPathW
0x18006e4b0  nop     dword ptr [rax+rax+00h]
0x18006e4b5  dec     eax
0x18006e4b7  cmp     eax, 214h
0x18006e4bc  jbe     short loc_18006E4DE
0x18006e4be  movzx   ecx, word ptr [rbx+92h]; nAtom
0x18006e4c5  lea     rdx, [rbp+660h+exeName]; lpBuffer
0x18006e4cc  mov     r8d, 215h; nSize
0x18006e4d2  call    cs:__imp_GlobalGetAtomNameW
0x18006e4d9  nop     dword ptr [rax+rax+00h]
0x18006e4de  mov     edi, 111h
0x18006e4e3  lea     r8, EMB_STR; pszSrc
0x18006e4ea  mov     edx, edi; cchDest
0x18006e4ec  lea     this, [rbp+660h+cmdline]; pszDest
0x18006e4f0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006e4f5  test    eax, eax
0x18006e4f7  js      loc_18006E674
0x18006e4fd  cmp     [rbx+7Ch], r15d
0x18006e501  jnz     short loc_18006E52E
0x18006e503  movzx   ecx, word ptr [rbx+94h]; atom
0x18006e50a  call    ?wAtomName@@YAPEAGG@Z; wAtomName(ushort)
0x18006e50f  test    rax, rax
0x18006e512  jz      loc_18006E674
0x18006e518  mov     r8, rax; pszSrc
0x18006e51b  lea     this, [rbp+660h+cmdline]; pszDest
0x18006e51f  mov     edx, edi; cchDest
0x18006e521  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006e526  test    eax, eax
0x18006e528  js      loc_18006E674
0x18006e52e  mov     rax, [rbx+80h]
0x18006e535  sub     rax, qword ptr cs:CLSID_ExcelWorksheet.Data1
0x18006e53c  jnz     short loc_18006E54C
0x18006e53e  mov     rax, [rbx+88h]
0x18006e545  sub     rax, qword ptr cs:CLSID_ExcelWorksheet.Data4
0x18006e54c  test    rax, rax
0x18006e54f  jz      short loc_18006E5BA
0x18006e551  mov     rax, [rbx+80h]
0x18006e558  sub     rax, qword ptr cs:CLSID_ExcelMacrosheet.Data1
0x18006e55f  jnz     short loc_18006E56F
0x18006e561  mov     rax, [rbx+88h]
0x18006e568  sub     rax, qword ptr cs:CLSID_ExcelMacrosheet.Data4
0x18006e56f  test    rax, rax
0x18006e572  jz      short loc_18006E5BA
0x18006e574  mov     rax, [rbx+80h]
0x18006e57b  sub     rax, qword ptr cs:CLSID_ExcelChart.Data1
0x18006e582  jnz     short loc_18006E592
0x18006e584  mov     rax, [rbx+88h]
0x18006e58b  sub     rax, qword ptr cs:CLSID_ExcelChart.Data4
0x18006e592  test    rax, rax
0x18006e595  jz      short loc_18006E5BA
0x18006e597  mov     rax, [rbx+80h]
0x18006e59e  sub     rax, qword ptr cs:CLSID_PBrush.Data1
0x18006e5a5  jnz     short loc_18006E5B5
0x18006e5a7  mov     rax, [rbx+88h]
0x18006e5ae  sub     rax, qword ptr cs:CLSID_PBrush.Data4
0x18006e5b5  test    rax, rax
0x18006e5b8  jnz     short loc_18006E5C3
0x18006e5ba  mov     eax, 7
0x18006e5bf  mov     [rbp+660h+startInfo.wShowWindow], ax
0x18006e5c3  lea     r8, [rbp+660h+cmdline]; pszSrc
0x18006e5c7  mov     edx, 215h; cchDest
0x18006e5cc  lea     this, [rbp+660h+exeName]; pszDest
0x18006e5d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006e5d8  test    eax, eax
0x18006e5da  js      loc_18006E674
0x18006e5e0  lea     rax, [rsp+760h+procInfo]
0x18006e5e5  xor     r9d, r9d; lpThreadAttributes
0x18006e5e8  mov     [rsp+760h+lpProcessInformation], rax; lpProcessInformation
0x18006e5ed  lea     rdx, [rbp+660h+exeName]; lpCommandLine
0x18006e5f4  lea     rax, [rsp+760h+startInfo]
0x18006e5f9  xor     r8d, r8d; lpProcessAttributes
0x18006e5fc  mov     [rsp+760h+lpStartupInfo], rax; lpStartupInfo
0x18006e601  xor     ecx, ecx; lpApplicationName
0x18006e603  mov     [rsp+760h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18006e608  mov     [rsp+760h+lpEnvironment], rsi; lpEnvironment
0x18006e60d  mov     dword ptr [rsp+760h+lpFilePart], esi; dwCreationFlags
0x18006e611  mov     dword ptr [rsp+760h+lpBuffer], esi; bInheritHandles
0x18006e615  call    cs:__imp_CreateProcessW
0x18006e61c  nop     dword ptr [rax+rax+00h]
0x18006e621  mov     edi, eax
0x18006e623  test    eax, eax
0x18006e625  jz      short loc_18006E670
0x18006e627  mov     this, [rsp+760h+procInfo.hProcess]; hProcess
0x18006e62c  mov     edx, 7530h; dwMilliseconds
0x18006e631  call    cs:__imp_WaitForInputIdle
0x18006e638  nop     dword ptr [rax+rax+00h]
0x18006e63d  mov     this, [rsp+760h+procInfo.hProcess]; hObject
0x18006e642  call    cs:__imp_CloseHandle
0x18006e649  nop     dword ptr [rax+rax+00h]
0x18006e64e  mov     this, [rsp+760h+procInfo.hThread]; hObject
0x18006e653  call    cs:__imp_CloseHandle
0x18006e65a  nop     dword ptr [rax+rax+00h]
0x18006e65f  xor     edx, edx; f
0x18006e661  mov     this, rbx; this
0x18006e664  call    ?DeclareVisibility@CDdeObject@@AEAAJHH@Z; CDdeObject::DeclareVisibility(int,int)
0x18006e669  mov     [rbx+0F0h], r15d
0x18006e670  mov     eax, edi
0x18006e672  jmp     short loc_18006E676
0x18006e674  xor     eax, eax
0x18006e676  mov     this, [rbp+660h+var_20]
0x18006e67d  xor     this, rsp; StackCookie
0x18006e680  call    __security_check_cookie
0x18006e685  lea     r11, [rsp+760h+var_10]
0x18006e68d  mov     rbx, [r11+28h]
0x18006e691  mov     rsi, [r11+30h]
0x18006e695  mov     rsp, r11
0x18006e698  pop     r15
0x18006e69a  pop     rdi
0x18006e69b  pop     rbp
0x18006e69c  retn
```
