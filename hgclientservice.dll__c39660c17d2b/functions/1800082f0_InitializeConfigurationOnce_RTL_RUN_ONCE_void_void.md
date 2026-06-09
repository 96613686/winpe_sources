# InitializeConfigurationOnce(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800082f0`
- end: `0x1800083e0`
- name: `?InitializeConfigurationOnce@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, HKEY **Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001770`
- `0x180001794`
- `0x1800082f0`
- `0x180008760`
- `0x1800087a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000838c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000838c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000836e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000836e`

## string_xrefs

- `0x1800083b6`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`
- `0x1800083cd`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall InitializeConfigurationOnce(PINIT_ONCE InitOnce, PVOID Parameter, HKEY **Context)
{
  HKEY *v4; // rbx
  HKEY *v5; // rcx
  HKEY *v6; // rax
  unsigned int v7; // eax
  wil *v8; // rcx
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  HKEY *v14; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v15[4]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    if ( InitOnce && Context )
    {
      v4 = (HKEY *)operator new(0x10u);
      v14 = v4;
      v5 = (HKEY *)off_180020090;
      *v4 = (HKEY)&Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vftable';
      v6 = v4 + 1;
      v4[1] = 0;
      if ( !*v5 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
          (const char *)0x80070057LL,
          phkResult);
      *v6 = 0;
      v7 = RegOpenKeyExW(*v5, L"SOFTWARE\\Microsoft\\HgsClient", 0, 3u, v6);
      v8 = retaddr;
      if ( v7 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x45,
          (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
          (const char *)v7,
          phkResulta);
      *Context = v4;
      result = 1;
    }
    else
    {
      SetLastError(0x57u);
      result = 0;
    }
  }
  catch ( ... )
  {
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 0x20) != 0 )
    {
      LODWORD(v14) = wil::ResultFromCaughtException(v8);
      v15[2] = &v14;
      v15[3] = 4;
      McGenEventWrite_EventWriteTransfer(v10, "\v", v11, 2, v15);
    }
    SetLastError(0x24Du);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800082f0  mov     [rsp+arg_0], rbx
0x1800082f5  push    rdi
0x1800082f6  sub     rsp, 60h
0x1800082fa  mov     rax, cs:__security_cookie
0x180008301  xor     rax, rsp
0x180008304  mov     [rsp+68h+var_10], rax
0x180008309  mov     rdi, r8
0x18000830c  test    rcx, rcx
0x18000830f  jz      short loc_180008387
0x180008311  test    r8, r8
0x180008314  jz      short loc_180008387
0x180008316  mov     ecx, 10h; Size
0x18000831b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008320  mov     rbx, rax
0x180008323  mov     [rsp+68h+var_38], rax
0x180008328  mov     rcx, cs:off_180020090
0x18000832f  lea     rax, ??_7HgRegistryConfiguration@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vftable'
0x180008336  mov     [rbx], rax
0x180008339  lea     rax, [rbx+8]
0x18000833d  mov     qword ptr [rax], 0
0x180008344  mov     r10, [rsp+68h]
0x180008349  cmp     qword ptr [rcx], 0
0x18000834d  jz      short loc_1800083B0
0x18000834f  mov     qword ptr [rax], 0
0x180008356  mov     qword ptr [rsp+68h+phkResult], rax; unsigned int
0x18000835b  mov     r9d, 3; samDesired
0x180008361  xor     r8d, r8d; ulOptions
0x180008364  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\HgsClient"
0x18000836b  mov     rcx, [rcx]; hKey
0x18000836e  call    cs:__imp_RegOpenKeyExW
0x180008374  mov     rcx, [rsp+68h]; this
0x180008379  test    eax, eax
0x18000837b  jnz     short loc_1800083CA
0x18000837d  mov     [rdi], rbx
0x180008380  mov     eax, 1
0x180008385  jmp     short loc_180008398
0x180008387  mov     ecx, 57h ; 'W'; dwErrCode
0x18000838c  call    cs:__imp_SetLastError
0x180008392  xor     eax, eax
0x180008394  jmp     short loc_180008398
0x180008396  xor     eax, eax
0x180008398  mov     rcx, [rsp+68h+var_10]
0x18000839d  xor     rcx, rsp; StackCookie
0x1800083a0  call    __security_check_cookie
0x1800083a5  mov     rbx, [rsp+68h+arg_0]
0x1800083aa  add     rsp, 60h
0x1800083ae  pop     rdi
0x1800083af  retn
0x1800083b0  mov     r9d, 80070057h; char *
0x1800083b6  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x1800083bd  mov     edx, 3Fh ; '?'; void *
0x1800083c2  mov     rcx, r10; this
0x1800083c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800083ca  mov     r9d, eax; char *
0x1800083cd  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x1800083d4  mov     edx, 45h ; 'E'; void *
0x1800083d9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
