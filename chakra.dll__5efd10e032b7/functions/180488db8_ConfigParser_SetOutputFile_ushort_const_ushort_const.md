# ConfigParser::SetOutputFile(ushort const *,ushort const *)

- ea: `0x180488db8`
- end: `0x18048906f`
- name: `?SetOutputFile@ConfigParser@@QEAAJPEBG0@Z`
- size: `695`
- prototype: `__int64 __fastcall(ConfigParser *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18041fdb0`

## callees

- `0x1803ea24c`
- `0x180488850`
- `0x180488db8`
- `0x1805a9e80`

## import_xrefs

- `msvcrt!_wfsopen` at `0x180489014`
- `msvcrt!_wfsopen` at `0x180489014`
- `msvcrt!wcsrchr` at `0x180488fd5`
- `msvcrt!wcsrchr` at `0x180488fd5`
- `msvcrt!_wcsnicmp` at `0x180488f83`
- `msvcrt!_wcsnicmp` at `0x180488f83`
- `msvcrt!_wsplitpath_s` at `0x180488ef5`
- `msvcrt!_wsplitpath_s` at `0x180488ef5`
- `msvcrt!_itow_s` at `0x180488e6d`
- `msvcrt!_itow_s` at `0x180488e6d`
- `msvcrt!wcsstr` at `0x180488e01`
- `msvcrt!wcsstr` at `0x180488e01`
- `msvcrt!wcsncpy_s` at `0x180488e38`
- `msvcrt!wcsncpy_s` at `0x180488e38`
- `msvcrt!wcscpy_s` at `0x180488ea9`
- `msvcrt!wcscpy_s` at `0x180488ea9`
- `msvcrt!wcscat_s` at `0x180488fc1`
- `msvcrt!wcscat_s` at `0x180488ff3`
- `msvcrt!wcscat_s` at `0x180488fc1`
- `msvcrt!wcscat_s` at `0x180488ff3`
- `msvcrt!_wcsicmp` at `0x180488f0d`
- `msvcrt!_wcsicmp` at `0x180488f29`
- `msvcrt!_wcsicmp` at `0x180488f45`
- `msvcrt!_wcsicmp` at `0x180488f61`
- `msvcrt!_wcsicmp` at `0x180488f0d`
- `msvcrt!_wcsicmp` at `0x180488f29`
- `msvcrt!_wcsicmp` at `0x180488f45`
- `msvcrt!_wcsicmp` at `0x180488f61`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180488fa2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180488fa2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180488e55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180488e55`

## pseudocode

```c
__int64 __fastcall ConfigParser::SetOutputFile(ConfigParser *this, wchar_t *a2, const unsigned __int16 *a3)
{
  wchar_t *v3; // rdi
  wchar_t *v4; // rax
  unsigned int v5; // edx
  rsize_t v6; // rsi
  wchar_t *v7; // r14
  DWORD CurrentProcessId; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  wchar_t *v11; // rcx
  wchar_t *v12; // rax
  FILE *v13; // rbx
  wchar_t String1[264]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+268h] [rbp+160h] BYREF
  wchar_t FullPath[264]; // [rsp+478h] [rbp+370h] BYREF

  v3 = a2;
  v4 = wcsstr(a2, L"{PID}");
  if ( v4 )
  {
    v6 = v4 - v3;
    wcsncpy_s(Destination, 0x104u, v3, v6);
    v7 = &Destination[v6];
    CurrentProcessId = GetCurrentProcessId();
    _itow_s(CurrentProcessId, v7, 260 - v6, 10);
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( v7[v10] );
    v11 = &v7[v10];
    do
      ++v9;
    while ( v11[v9] );
    wcscpy_s(v11, 260 - v6 - v9, &v3[v6 + 5]);
    v3 = Destination;
  }
  PlatformAgnostic::SystemInfo::GetBinaryLocation(FullPath, v5);
  _wsplitpath_s(FullPath, 0, 0, 0, 0, String1, 0x104u, 0, 0);
  if ( !_wcsicmp(String1, L"WWAHost")
    || !_wcsicmp(String1, L"ByteCodeGenerator")
    || !_wcsicmp(String1, L"spartan")
    || !_wcsicmp(String1, L"spartan_edge")
    || !_wcsnicmp(String1, L"MicrosoftEdge", 0xDu) )
  {
    if ( GetEnvironmentVariableW(L"temp", String1, 0x104u) )
    {
      wcscat_s(String1, 0x104u, L"\\");
      v12 = wcsrchr(v3, 0x5Cu);
      if ( !v12 )
        v12 = v3;
      wcscat_s(String1, 0x104u, v12);
    }
    v3 = String1;
  }
  v13 = _wfsopen(v3, L"wt", 32);
  if ( !v13 )
    return 2147500037LL;
  if ( !Output::s_outputFile )
  {
    AutoFILE::Close((AutoFILE *)&Output::s_outputFile);
    Output::s_outputFile = v13;
  }
  return 0;
}

```

## disassembly

```asm
0x180488db8  mov     rax, rsp
0x180488dbb  mov     [rax+18h], r8
0x180488dbf  mov     [rax+10h], rdx
0x180488dc3  mov     [rax+8], rcx
0x180488dc7  push    rbp
0x180488dc8  push    rbx
0x180488dc9  push    rsi
0x180488dca  push    rdi
0x180488dcb  push    r12
0x180488dcd  push    r14
0x180488dcf  push    r15
0x180488dd1  lea     rbp, [rax-5C8h]
0x180488dd8  sub     rsp, 690h
0x180488ddf  mov     rax, cs:__security_cookie
0x180488de6  xor     rax, rsp
0x180488de9  mov     [rbp+5C0h+var_40], rax
0x180488df0  mov     rdi, [rbp+5C0h+Str]
0x180488df7  lea     rdx, aPid; "{PID}"
0x180488dfe  mov     rcx, rdi; Str
0x180488e01  call    cs:__imp_wcsstr
0x180488e08  nop     dword ptr [rax+rax+00h]
0x180488e0d  xor     r15d, r15d
0x180488e10  mov     r12d, 104h
0x180488e16  mov     rsi, rax
0x180488e19  test    rax, rax
0x180488e1c  jz      loc_180488EBC
0x180488e22  sub     rsi, rdi
0x180488e25  lea     rcx, [rbp+5C0h+Destination]; Destination
0x180488e2c  sar     rsi, 1
0x180488e2f  mov     r8, rdi; Source
0x180488e32  mov     r9, rsi; MaxCount
0x180488e35  mov     edx, r12d; SizeInWords
0x180488e38  call    cs:__imp_wcsncpy_s
0x180488e3f  nop     dword ptr [rax+rax+00h]
0x180488e44  lea     r14, [rbp+5C0h+Destination]
0x180488e4b  mov     ebx, r12d
0x180488e4e  lea     r14, [r14+rsi*2]
0x180488e52  sub     rbx, rsi
0x180488e55  call    cs:__imp_GetCurrentProcessId
0x180488e5c  nop     dword ptr [rax+rax+00h]
0x180488e61  lea     r9d, [r15+0Ah]; Radix
0x180488e65  mov     r8, rbx; BufferCount
0x180488e68  mov     ecx, eax; Value
0x180488e6a  mov     rdx, r14; Buffer
0x180488e6d  call    cs:__imp__itow_s
0x180488e74  nop     dword ptr [rax+rax+00h]
0x180488e79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180488e7d  mov     rcx, rax
0x180488e80  inc     rcx
0x180488e83  cmp     [r14+rcx*2], r15w
0x180488e88  jnz     short loc_180488E80
0x180488e8a  lea     rcx, [r14+rcx*2]; Destination
0x180488e8e  inc     rax
0x180488e91  cmp     [rcx+rax*2], r15w
0x180488e96  jnz     short loc_180488E8E
0x180488e98  mov     rdx, r12
0x180488e9b  lea     r8, [rdi+0Ah]
0x180488e9f  sub     rdx, rsi
0x180488ea2  lea     r8, [r8+rsi*2]; Source
0x180488ea6  sub     rdx, rax; SizeInWords
0x180488ea9  call    cs:__imp_wcscpy_s
0x180488eb0  nop     dword ptr [rax+rax+00h]
0x180488eb5  lea     rdi, [rbp+5C0h+Destination]
0x180488ebc  lea     rcx, [rbp+5C0h+FullPath]; unsigned __int16 *
0x180488ec3  call    ?GetBinaryLocation@SystemInfo@PlatformAgnostic@@SA_NPEAGI@Z; PlatformAgnostic::SystemInfo::GetBinaryLocation(ushort *,uint)
0x180488ec8  mov     [rsp+40h], r15; ExtCount
0x180488ecd  lea     rax, [rsp+6C0h+String1]
0x180488ed2  mov     [rsp+6C0h+Ext], r15; Ext
0x180488ed7  lea     rcx, [rbp+5C0h+FullPath]; FullPath
0x180488ede  mov     [rsp+6C0h+FilenameCount], r12; FilenameCount
0x180488ee3  xor     r9d, r9d; Dir
0x180488ee6  mov     [rsp+6C0h+Filename], rax; Filename
0x180488eeb  xor     r8d, r8d; DriveCount
0x180488eee  xor     edx, edx; Drive
0x180488ef0  mov     [rsp+6C0h+DirCount], r15; DirCount
0x180488ef5  call    cs:__imp__wsplitpath_s
0x180488efc  nop     dword ptr [rax+rax+00h]
0x180488f01  lea     rdx, aWwahost; "WWAHost"
0x180488f08  lea     rcx, [rsp+6C0h+String1]; String1
0x180488f0d  call    cs:__imp__wcsicmp
0x180488f14  nop     dword ptr [rax+rax+00h]
0x180488f19  test    eax, eax
0x180488f1b  jz      short loc_180488F93
0x180488f1d  lea     rdx, aBytecodegenera; "ByteCodeGenerator"
0x180488f24  lea     rcx, [rsp+6C0h+String1]; String1
0x180488f29  call    cs:__imp__wcsicmp
0x180488f30  nop     dword ptr [rax+rax+00h]
0x180488f35  test    eax, eax
0x180488f37  jz      short loc_180488F93
0x180488f39  lea     rdx, aSpartan; "spartan"
0x180488f40  lea     rcx, [rsp+6C0h+String1]; String1
0x180488f45  call    cs:__imp__wcsicmp
0x180488f4c  nop     dword ptr [rax+rax+00h]
0x180488f51  test    eax, eax
0x180488f53  jz      short loc_180488F93
0x180488f55  lea     rdx, aSpartanEdge; "spartan_edge"
0x180488f5c  lea     rcx, [rsp+6C0h+String1]; String1
0x180488f61  call    cs:__imp__wcsicmp
0x180488f68  nop     dword ptr [rax+rax+00h]
0x180488f6d  test    eax, eax
0x180488f6f  jz      short loc_180488F93
0x180488f71  mov     r8d, 0Dh; MaxCount
0x180488f77  lea     rdx, aMicrosoftedge; "MicrosoftEdge"
0x180488f7e  lea     rcx, [rsp+6C0h+String1]; String1
0x180488f83  call    cs:__imp__wcsnicmp
0x180488f8a  nop     dword ptr [rax+rax+00h]
0x180488f8f  test    eax, eax
0x180488f91  jnz     short loc_180489004
0x180488f93  mov     r8d, r12d; nSize
0x180488f96  lea     rdx, [rsp+6C0h+String1]; lpBuffer
0x180488f9b  lea     rcx, aTemp; "temp"
0x180488fa2  call    cs:__imp_GetEnvironmentVariableW
0x180488fa9  nop     dword ptr [rax+rax+00h]
0x180488fae  test    eax, eax
0x180488fb0  jz      short loc_180488FFF
0x180488fb2  lea     r8, SubBlock; "\\"
0x180488fb9  mov     rdx, r12; SizeInWords
0x180488fbc  lea     rcx, [rsp+6C0h+String1]; Destination
0x180488fc1  call    cs:__imp_wcscat_s
0x180488fc8  nop     dword ptr [rax+rax+00h]
0x180488fcd  mov     edx, 5Ch ; '\'; Ch
0x180488fd2  mov     rcx, rdi; Str
0x180488fd5  call    cs:__imp_wcsrchr
0x180488fdc  nop     dword ptr [rax+rax+00h]
0x180488fe1  mov     rdx, r12; SizeInWords
0x180488fe4  lea     rcx, [rsp+6C0h+String1]; Destination
0x180488fe9  test    rax, rax
0x180488fec  cmovz   rax, rdi
0x180488ff0  mov     r8, rax; Source
0x180488ff3  call    cs:__imp_wcscat_s
0x180488ffa  nop     dword ptr [rax+rax+00h]
0x180488fff  lea     rdi, [rsp+6C0h+String1]
0x180489004  mov     r8d, 20h ; ' '; ShFlag
0x18048900a  lea     rdx, aWt; "wt"
0x180489011  mov     rcx, rdi; FileName
0x180489014  call    cs:__imp__wfsopen
0x18048901b  nop     dword ptr [rax+rax+00h]
0x180489020  mov     rbx, rax
0x180489023  test    rax, rax
0x180489026  jz      short loc_180489048
0x180489028  cmp     cs:?s_outputFile@Output@@0VAutoFILE@@A, r15; AutoFILE Output::s_outputFile
0x18048902f  jnz     short loc_180489044
0x180489031  lea     rcx, ?s_outputFile@Output@@0VAutoFILE@@A; this
0x180489038  call    ?Close@AutoFILE@@QEAAXXZ; AutoFILE::Close(void)
0x18048903d  mov     cs:?s_outputFile@Output@@0VAutoFILE@@A, rbx; AutoFILE Output::s_outputFile
0x180489044  xor     eax, eax
0x180489046  jmp     short loc_18048904D
0x180489048  mov     eax, 80004005h
0x18048904d  mov     rcx, [rbp+5C0h+var_40]
0x180489054  xor     rcx, rsp; StackCookie
0x180489057  call    __security_check_cookie
0x18048905c  add     rsp, 690h
0x180489063  pop     r15
0x180489065  pop     r14
0x180489067  pop     r12
0x180489069  pop     rdi
0x18048906a  pop     rsi
0x18048906b  pop     rbx
0x18048906c  pop     rbp
0x18048906d  retn
```
