# NGENService::ServiceInstall(void)

- ea: `0x18001b9d0`
- end: `0x18001bc47`
- name: `?ServiceInstall@NGENService@@YAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800084e0`

## callees

- `0x180001e8c`
- `0x180007884`
- `0x180007914`
- `0x180007a04`
- `0x180007b14`
- `0x18001a3a0`
- `0x18001b9d0`
- `0x18001bc48`
- `0x180030568`
- `0x180030d84`
- `0x18003dc30`
- `0x18003e73c`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x18001bb06`
- `KERNEL32!GetEnvironmentVariableW` at `0x18001bb06`
- `KERNEL32!GetModuleFileNameW` at `0x18001ba7a`
- `KERNEL32!GetModuleFileNameW` at `0x18001ba7a`
- `KERNEL32!GetLastError` at `0x18001ba52`
- `KERNEL32!GetLastError` at `0x18001ba84`
- `KERNEL32!GetLastError` at `0x18001bbb6`
- `KERNEL32!GetLastError` at `0x18001ba52`
- `KERNEL32!GetLastError` at `0x18001ba84`
- `KERNEL32!GetLastError` at `0x18001bbb6`

## string_xrefs

- `0x18001baff`: `COMPLUS_DEFAULTVERSION`
- `0x18001bb96`: `SeCreateGlobalPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NGENService::ServiceInstall(NGENService *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rdi
  unsigned __int16 *v3; // rsi
  struct SC_HANDLE__ *v4; // r15
  signed int v5; // eax
  signed int v6; // ebx
  struct SString *v7; // rdx
  bool v8; // r8
  signed int LastError; // eax
  bool v10; // r8
  __int64 v11; // r9
  struct SC_HANDLE__ *v12; // r14
  signed int v13; // eax
  struct SC_HANDLE__ **v14; // rdx
  NGENService *v15; // rcx
  unsigned int v17; // [rsp+28h] [rbp-E0h]
  unsigned int v18; // [rsp+30h] [rbp-D8h]
  unsigned int v19; // [rsp+38h] [rbp-D0h]
  _DWORD v20[2]; // [rsp+78h] [rbp-90h] BYREF
  int v21; // [rsp+80h] [rbp-88h]
  unsigned __int16 *v22; // [rsp+88h] [rbp-80h]
  _DWORD v23[2]; // [rsp+90h] [rbp-78h] BYREF
  int v24; // [rsp+98h] [rbp-70h]
  void *lpMem; // [rsp+A0h] [rbp-68h]
  _DWORD v26[2]; // [rsp+A8h] [rbp-60h] BYREF
  int v27; // [rsp+B0h] [rbp-58h]
  unsigned __int16 *v28; // [rsp+B8h] [rbp-50h]
  const wchar_t *v29; // [rsp+C0h] [rbp-48h] BYREF
  unsigned __int16 near **v30; // [rsp+C8h] [rbp-40h] BYREF
  WCHAR Buffer[104]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR Filename[264]; // [rsp+1A8h] [rbp+A0h] BYREF

  v20[0] = 2;
  v20[1] = 2;
  v21 = 16;
  v2 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  v22 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  v26[0] = 2;
  v26[1] = 2;
  v27 = 16;
  v3 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  v28 = (unsigned __int16 *)&SString::s_EmptyBuffer;
  v23[0] = 2;
  v23[1] = 2;
  v24 = 16;
  lpMem = (void *)&SString::s_EmptyBuffer;
  v4 = CLROpenSCManager((const unsigned __int16 *)2, a2, 0xF003Fu);
  if ( v4 )
  {
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    {
LABEL_6:
      LastError = GetLastError();
      v6 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v6 = LastError;
      goto LABEL_24;
    }
    LOBYTE(v7) = 1;
    if ( (int)NGENService::GenerateServiceName((NGENService *)v23, v7, v8) >= 0 )
    {
      if ( (int)NGENService::GenerateServiceName((NGENService *)v26, 0, v10) >= 0 )
      {
        SString::Append((SString *)v20, Filename);
        memset_0(Buffer, 0, 0xC8u);
        if ( GetEnvironmentVariableW(L"COMPLUS_DEFAULTVERSION", Buffer, 0x64u) )
        {
          SString::Append((SString *)v20, L" ");
          SString::Append((SString *)v20, L"-private");
        }
        SString::ConvertToUnicode((SString *)v20);
        SString::ConvertToUnicode((SString *)v23);
        SString::ConvertToUnicode((SString *)v26);
        v2 = v22;
        v3 = v28;
        v12 = CLRCreateService(v4, v28, (const unsigned __int16 *)lpMem, v11, v17, v18, v19, v22);
        if ( v12 )
        {
          v29 = L"Provides support for optimizing managed assemblies using NGEN technology";
          if ( (unsigned int)CLRChangeServiceConfig2(v12, 1u, &v29)
            && (v30 = &NGENService::PRIVILEGE_NAMES, (unsigned int)CLRChangeServiceConfig2(v12, 6u, &v30)) )
          {
            v6 = 0;
          }
          else
          {
            v13 = GetLastError();
            v6 = (unsigned __int16)v13 | 0x80070000;
            if ( v13 <= 0 )
              v6 = v13;
            if ( v6 < 0 )
              NGENService::ServiceUninstall(v15, v14);
          }
          CLRCloseServiceHandle(v12);
          goto LABEL_24;
        }
        goto LABEL_6;
      }
      v6 = -2147467259;
      v3 = v28;
    }
    else
    {
      v6 = -2147467259;
    }
LABEL_24:
    CLRCloseServiceHandle(v4);
    goto LABEL_25;
  }
  v5 = GetLastError();
  v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 <= 0 )
    v6 = v5;
LABEL_25:
  if ( (v24 & 8) != 0 )
    operator delete(lpMem);
  if ( (v27 & 8) != 0 )
    operator delete(v3);
  if ( (v21 & 8) != 0 )
    operator delete(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b9d0  mov     rax, rsp
0x18001b9d3  mov     [rax+8], rbx
0x18001b9d7  mov     [rax+10h], rsi
0x18001b9db  mov     [rax+18h], rdi
0x18001b9df  push    rbp
0x18001b9e0  push    r14
0x18001b9e2  push    r15
0x18001b9e4  lea     rbp, [rax-2D8h]
0x18001b9eb  sub     rsp, 3C0h
0x18001b9f2  mov     rax, cs:__security_cookie
0x18001b9f9  xor     rax, rsp
0x18001b9fc  mov     [rbp+2D0h+var_20], rax
0x18001ba03  mov     ecx, 2; unsigned __int16 *
0x18001ba08  mov     [rsp+3D0h+var_360], ecx
0x18001ba0c  mov     [rsp+3D0h+var_35C], ecx
0x18001ba10  lea     eax, [rcx+0Eh]
0x18001ba13  mov     [rsp+3D0h+var_358], eax
0x18001ba17  lea     rdi, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18001ba1e  mov     [rbp+2D0h+var_350], rdi
0x18001ba22  mov     [rbp+2D0h+var_330], ecx
0x18001ba25  mov     [rbp+2D0h+var_32C], ecx
0x18001ba28  mov     [rbp+2D0h+var_328], eax
0x18001ba2b  mov     rsi, rdi
0x18001ba2e  mov     [rbp+2D0h+var_320], rdi
0x18001ba32  mov     [rbp+2D0h+var_348], ecx
0x18001ba35  mov     [rbp+2D0h+var_344], ecx
0x18001ba38  mov     [rbp+2D0h+var_340], eax
0x18001ba3b  mov     [rbp+2D0h+lpMem], rdi
0x18001ba3f  mov     r8d, 0F003Fh; unsigned int
0x18001ba45  call    ?CLROpenSCManager@@YAPEAUSC_HANDLE__@@PEBG0K@Z; CLROpenSCManager(ushort const *,ushort const *,ulong)
0x18001ba4a  mov     r15, rax
0x18001ba4d  test    rax, rax
0x18001ba50  jnz     short loc_18001BA6B
0x18001ba52  call    cs:__imp_GetLastError
0x18001ba58  movzx   ebx, ax
0x18001ba5b  or      ebx, 80070000h
0x18001ba61  test    eax, eax
0x18001ba63  cmovle  ebx, eax
0x18001ba66  jmp     loc_18001BBE8
0x18001ba6b  mov     r8d, 104h; nSize
0x18001ba71  lea     rdx, [rbp+2D0h+Filename]; lpFilename
0x18001ba78  xor     ecx, ecx; hModule
0x18001ba7a  call    cs:__imp_GetModuleFileNameW
0x18001ba80  test    eax, eax
0x18001ba82  jnz     short loc_18001BA9D
0x18001ba84  call    cs:__imp_GetLastError
0x18001ba8a  movzx   ebx, ax
0x18001ba8d  or      ebx, 80070000h
0x18001ba93  test    eax, eax
0x18001ba95  cmovle  ebx, eax
0x18001ba98  jmp     loc_18001BBDF
0x18001ba9d  mov     dl, 1; struct SString *
0x18001ba9f  lea     rcx, [rbp+2D0h+var_348]; this
0x18001baa3  call    ?GenerateServiceName@NGENService@@YAJAEAVSString@@_N@Z; NGENService::GenerateServiceName(SString &,bool)
0x18001baa8  test    eax, eax
0x18001baaa  jns     short loc_18001BAB6
0x18001baac  mov     ebx, 80004005h
0x18001bab1  jmp     loc_18001BBDF
0x18001bab6  xor     edx, edx; struct SString *
0x18001bab8  lea     rcx, [rbp+2D0h+var_330]; this
0x18001babc  call    ?GenerateServiceName@NGENService@@YAJAEAVSString@@_N@Z; NGENService::GenerateServiceName(SString &,bool)
0x18001bac1  test    eax, eax
0x18001bac3  jns     short loc_18001BAD3
0x18001bac5  mov     ebx, 80004005h
0x18001baca  mov     rsi, [rbp+2D0h+var_320]
0x18001bace  jmp     loc_18001BBDF
0x18001bad3  lea     rdx, [rbp+2D0h+Filename]; unsigned __int16 *
0x18001bada  lea     rcx, [rsp+3D0h+var_360]; this
0x18001badf  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001bae4  xor     edx, edx; Val
0x18001bae6  mov     r8d, 0C8h; Size
0x18001baec  lea     rcx, [rbp+2D0h+Buffer]; void *
0x18001baf0  call    memset_0
0x18001baf5  mov     r8d, 64h ; 'd'; nSize
0x18001bafb  lea     rdx, [rbp+2D0h+Buffer]; lpBuffer
0x18001baff  lea     rcx, Name; "COMPLUS_DEFAULTVERSION"
0x18001bb06  call    cs:__imp_GetEnvironmentVariableW
0x18001bb0c  test    eax, eax
0x18001bb0e  jz      short loc_18001BB32
0x18001bb10  lea     rdx, asc_180055D68; " "
0x18001bb17  lea     rcx, [rsp+3D0h+var_360]; this
0x18001bb1c  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001bb21  lea     rdx, aPrivate; "-private"
0x18001bb28  lea     rcx, [rsp+3D0h+var_360]; this
0x18001bb2d  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001bb32  lea     rcx, [rsp+3D0h+var_360]; this
0x18001bb37  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001bb3c  lea     rcx, [rbp+2D0h+var_348]; this
0x18001bb40  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001bb45  lea     rcx, [rbp+2D0h+var_330]; this
0x18001bb49  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001bb4e  mov     rdi, [rbp+2D0h+var_350]
0x18001bb52  mov     [rsp+3D0h+var_398], rdi; unsigned __int16 *
0x18001bb57  mov     r8, [rbp+2D0h+lpMem]; unsigned __int16 *
0x18001bb5b  mov     rsi, [rbp+2D0h+var_320]
0x18001bb5f  mov     rdx, rsi; unsigned __int16 *
0x18001bb62  mov     rcx, r15; struct SC_HANDLE__ *
0x18001bb65  call    ?CLRCreateService@@YAPEAUSC_HANDLE__@@PEAU1@PEBG1KKKK11PEAK111@Z; CLRCreateService(SC_HANDLE__ *,ushort const *,ushort const *,ulong,ulong,ulong,ulong,ushort const *,ushort const *,ulong *,ushort const *,ushort const *,ushort const *)
0x18001bb6a  mov     r14, rax
0x18001bb6d  test    rax, rax
0x18001bb70  jz      loc_18001BA84
0x18001bb76  lea     rax, aProvidesSuppor; "Provides support for optimizing managed"...
0x18001bb7d  mov     [rbp+2D0h+var_318], rax
0x18001bb81  lea     r8, [rbp+2D0h+var_318]; void *
0x18001bb85  mov     edx, 1; unsigned int
0x18001bb8a  mov     rcx, r14; struct SC_HANDLE__ *
0x18001bb8d  call    ?CLRChangeServiceConfig2@@YAHPEAUSC_HANDLE__@@KPEAX@Z; CLRChangeServiceConfig2(SC_HANDLE__ *,ulong,void *)
0x18001bb92  test    eax, eax
0x18001bb94  jz      short loc_18001BBB6
0x18001bb96  lea     rax, ?PRIVILEGE_NAMES@NGENService@@3PAGA; "SeCreateGlobalPrivilege"
0x18001bb9d  mov     [rbp+2D0h+var_310], rax
0x18001bba1  lea     r8, [rbp+2D0h+var_310]; void *
0x18001bba5  mov     edx, 6; unsigned int
0x18001bbaa  mov     rcx, r14; struct SC_HANDLE__ *
0x18001bbad  call    ?CLRChangeServiceConfig2@@YAHPEAUSC_HANDLE__@@KPEAX@Z; CLRChangeServiceConfig2(SC_HANDLE__ *,ulong,void *)
0x18001bbb2  test    eax, eax
0x18001bbb4  jnz     short loc_18001BBD5
0x18001bbb6  call    cs:__imp_GetLastError
0x18001bbbc  movzx   ebx, ax
0x18001bbbf  or      ebx, 80070000h
0x18001bbc5  test    eax, eax
0x18001bbc7  cmovle  ebx, eax
0x18001bbca  test    ebx, ebx
0x18001bbcc  jns     short loc_18001BBD7
0x18001bbce  call    ?ServiceUninstall@NGENService@@YAJXZ; NGENService::ServiceUninstall(void)
0x18001bbd3  jmp     short loc_18001BBD7
0x18001bbd5  xor     ebx, ebx
0x18001bbd7  mov     rcx, r14; struct SC_HANDLE__ *
0x18001bbda  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001bbdf  mov     rcx, r15; struct SC_HANDLE__ *
0x18001bbe2  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001bbe7  nop
0x18001bbe8  mov     r14b, 8
0x18001bbeb  test    byte ptr [rbp+2D0h+var_340], r14b
0x18001bbef  jz      short loc_18001BBFB
0x18001bbf1  mov     rcx, [rbp+2D0h+lpMem]; lpMem
0x18001bbf5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bbfa  nop
0x18001bbfb  test    byte ptr [rbp+2D0h+var_328], r14b
0x18001bbff  jz      short loc_18001BC0A
0x18001bc01  mov     rcx, rsi; lpMem
0x18001bc04  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bc09  nop
0x18001bc0a  test    byte ptr [rsp+3D0h+var_358], r14b
0x18001bc0f  jz      short loc_18001BC19
0x18001bc11  mov     rcx, rdi; lpMem
0x18001bc14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bc19  mov     eax, ebx
0x18001bc1b  mov     rcx, [rbp+2D0h+var_20]
0x18001bc22  xor     rcx, rsp; StackCookie
0x18001bc25  call    __security_check_cookie
0x18001bc2a  lea     r11, [rsp+3D0h+var_10]
0x18001bc32  mov     rbx, [r11+20h]
0x18001bc36  mov     rsi, [r11+28h]
0x18001bc3a  mov     rdi, [r11+30h]
0x18001bc3e  mov     rsp, r11
0x18001bc41  pop     r15
0x18001bc43  pop     r14
0x18001bc45  pop     rbp
0x18001bc46  retn
```
