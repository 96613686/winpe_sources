# TraceLoggingClient::TraceLoggingClient(void)

- ea: `0x1802f36fc`
- end: `0x1802f3819`
- name: `??0TraceLoggingClient@@QEAA@XZ`
- size: `285`
- prototype: `TraceLoggingClient *__fastcall(TraceLoggingClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1802f257c`

## callees

- `0x1802f36fc`
- `0x1802f3820`
- `0x1805a9e80`

## import_xrefs

- `msvcrt!_wsplitpath_s` at `0x1802f37ab`
- `msvcrt!_wsplitpath_s` at `0x1802f37ab`
- `msvcrt!_wcsicmp` at `0x1802f37d8`
- `msvcrt!_wcsicmp` at `0x1802f37d8`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1802f3761`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1802f3761`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1802f373a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1802f373a`

## pseudocode

```c
TraceLoggingClient *__fastcall TraceLoggingClient::TraceLoggingClient(TraceLoggingClient *this)
{
  unsigned int i; // edi
  WCHAR Filename[264]; // [rsp+50h] [rbp-438h] BYREF
  wchar_t String1[264]; // [rsp+260h] [rbp-228h] BYREF

  *(_BYTE *)this = 1;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  if ( CoCreateGuid((GUID *)((char *)this + 24)) )
    *(_OWORD *)((char *)this + 24) = 0;
  if ( GetModuleFileNameW(0, Filename, 0x104u) && !_wsplitpath_s(Filename, 0, 0, 0, 0, String1, 0x104u, 0, 0) )
  {
    for ( i = 0; i < 8; ++i )
    {
      if ( !_wcsicmp(String1, (const wchar_t *)(&g_ProcessExclusionList)[i]) )
      {
        *(_BYTE *)this = 0;
        break;
      }
    }
  }
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  return this;
}

```

## disassembly

```asm
0x1802f36fc  mov     r11, rsp
0x1802f36ff  mov     [r11+10h], rbx
0x1802f3703  mov     [r11+8], rcx
0x1802f3707  push    rdi
0x1802f3708  sub     rsp, 480h
0x1802f370f  mov     rax, cs:__security_cookie
0x1802f3716  xor     rax, rsp
0x1802f3719  mov     [rsp+488h+var_18], rax
0x1802f3721  mov     byte ptr [rcx], 1
0x1802f3724  mov     rbx, rcx
0x1802f3727  mov     dword ptr [rcx+8], 0
0x1802f372e  mov     qword ptr [rcx+10h], 0
0x1802f3736  lea     rcx, [rcx+18h]; pguid
0x1802f373a  call    cs:__imp_CoCreateGuid
0x1802f3741  nop     dword ptr [rax+rax+00h]
0x1802f3746  test    eax, eax
0x1802f3748  jz      short loc_1802F3752
0x1802f374a  xorps   xmm0, xmm0
0x1802f374d  movdqu  xmmword ptr [rbx+18h], xmm0
0x1802f3752  mov     edi, 104h
0x1802f3757  lea     rdx, [rsp+488h+Filename]; lpFilename
0x1802f375c  mov     r8d, edi; nSize
0x1802f375f  xor     ecx, ecx; hModule
0x1802f3761  call    cs:__imp_GetModuleFileNameW
0x1802f3768  nop     dword ptr [rax+rax+00h]
0x1802f376d  test    eax, eax
0x1802f376f  jz      short loc_1802F37EF
0x1802f3771  mov     [rsp+488h+ExtCount], 0; ExtCount
0x1802f377a  lea     rax, [rsp+488h+String1]
0x1802f3782  mov     [rsp+488h+Ext], 0; Ext
0x1802f378b  lea     rcx, [rsp+488h+Filename]; FullPath
0x1802f3790  mov     [rsp+488h+FilenameCount], rdi; FilenameCount
0x1802f3795  xor     r9d, r9d; Dir
0x1802f3798  mov     [rsp+488h+var_460], rax; Filename
0x1802f379d  xor     r8d, r8d; DriveCount
0x1802f37a0  xor     edx, edx; Drive
0x1802f37a2  mov     [rsp+488h+DirCount], 0; DirCount
0x1802f37ab  call    cs:__imp__wsplitpath_s
0x1802f37b2  nop     dword ptr [rax+rax+00h]
0x1802f37b7  test    eax, eax
0x1802f37b9  jnz     short loc_1802F37EF
0x1802f37bb  xor     edi, edi
0x1802f37bd  cmp     edi, 8
0x1802f37c0  jnb     short loc_1802F37EF
0x1802f37c2  lea     rax, ?g_ProcessExclusionList@@3PAPEAGA; ushort * near * g_ProcessExclusionList
0x1802f37c9  movsxd  rdx, edi
0x1802f37cc  lea     rcx, [rsp+488h+String1]; String1
0x1802f37d4  mov     rdx, [rax+rdx*8]; String2
0x1802f37d8  call    cs:__imp__wcsicmp
0x1802f37df  nop     dword ptr [rax+rax+00h]
0x1802f37e4  test    eax, eax
0x1802f37e6  jz      short loc_1802F37EC
0x1802f37e8  inc     edi
0x1802f37ea  jmp     short loc_1802F37BD
0x1802f37ec  mov     byte ptr [rbx], 0
0x1802f37ef  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1802f37f4  mov     rax, rbx
0x1802f37f7  mov     rcx, [rsp+488h+var_18]
0x1802f37ff  xor     rcx, rsp; StackCookie
0x1802f3802  call    __security_check_cookie
0x1802f3807  mov     rbx, [rsp+488h+arg_8]
0x1802f380f  add     rsp, 480h
0x1802f3816  pop     rdi
0x1802f3817  retn
```
