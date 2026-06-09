# TelpReadEnterpriseGovSetting

- ea: `0x1800cdf18`
- end: `0x1800ce06f`
- name: `TelpReadEnterpriseGovSetting`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800cd82c`

## callees

- `0x18000ec54`
- `0x1800cdf18`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdfa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800cdfa2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cdf8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cdf8d`
- `ntdll!NtQueryLicenseValue` at `0x1800cdfd5`
- `ntdll!NtQueryLicenseValue` at `0x1800cdfd5`

## string_xrefs

- `0x1800cdf50`: `ntdll.dll`
- `0x1800cdf2a`: `Reserved.PlatformSigned`
- `0x1800cdf98`: `NtQuerySecurityPolicy`

## pseudocode

```c
__int64 __fastcall TelpReadEnterpriseGovSetting(_DWORD *a1, int *a2)
{
  FARPROC ProcAddress; // rbx
  HMODULE ModuleHandleW; // rax
  int v6; // eax
  unsigned int v7; // ebx
  _DWORD v9[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v10[2]; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v11[2]; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v12[3]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  int v14; // [rsp+A0h] [rbp+20h] BYREF
  int v15; // [rsp+B0h] [rbp+30h] BYREF
  int v16; // [rsp+B8h] [rbp+38h] BYREF

  *a1 = 1;
  v12[1] = L"Reserved.PlatformSigned";
  v16 = 0;
  v11[1] = L"CodeIntegrity.Telemetry";
  v9[1] = 4;
  v10[1] = L"OptInLevel";
  v15 = 0;
  ProcAddress = 0;
  v12[0] = 3145774;
  v11[0] = 3145774;
  v10[0] = 1441812;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW )
    ProcAddress = GetProcAddress(ModuleHandleW, "NtQuerySecurityPolicy");
  v14 = 0;
  v9[0] = 4;
  NtQueryLicenseValue(asc_1800FE208, 0, &v14, 4, v9);
  if ( (unsigned int)(v14 - 171) <= 1 && ProcAddress )
  {
    v6 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *, _QWORD *, int *))ProcAddress)(v12, v11, v10, &v15);
    v7 = v6 | 0x10000000;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43F,
        (unsigned int)"onecore\\base\\telemetry\\permission\\lib\\telemetrypermission.cpp",
        (const char *)v7,
        (int)&v16);
    }
    else if ( v15 == 1 && (unsigned int)v16 <= 3 )
    {
      *a2 = v16;
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    v7 = 0;
    *a1 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800cdf18  mov     [rsp-18h+arg_8], rbx
0x1800cdf1d  push    rbp
0x1800cdf1e  push    rsi
0x1800cdf1f  push    rdi
0x1800cdf20  mov     rbp, rsp
0x1800cdf23  sub     rsp, 80h
0x1800cdf2a  lea     rax, aReservedPlatfo; "Reserved.PlatformSigned"
0x1800cdf31  mov     dword ptr [rcx], 1
0x1800cdf37  mov     [rbp+var_10], rax
0x1800cdf3b  mov     rsi, rcx
0x1800cdf3e  lea     rax, aCodeintegrityT; "CodeIntegrity.Telemetry"
0x1800cdf45  mov     [rbp+arg_18], 0
0x1800cdf4c  mov     [rbp+var_20], rax
0x1800cdf50  lea     rcx, LibFileName; "ntdll.dll"
0x1800cdf57  lea     rax, aOptinlevel; "OptInLevel"
0x1800cdf5e  mov     [rbp+var_3C], 4
0x1800cdf65  mov     [rbp+var_30], rax
0x1800cdf69  mov     rdi, rdx
0x1800cdf6c  mov     [rbp+arg_10], 0
0x1800cdf73  xor     ebx, ebx
0x1800cdf75  mov     [rbp+var_18], 30002Eh
0x1800cdf7d  mov     [rbp+var_28], 30002Eh
0x1800cdf85  mov     [rbp+var_38], 160014h
0x1800cdf8d  call    cs:__imp_GetModuleHandleW
0x1800cdf93  test    rax, rax
0x1800cdf96  jz      short loc_1800CDFAB
0x1800cdf98  lea     rdx, aNtquerysecurit; "NtQuerySecurityPolicy"
0x1800cdf9f  mov     rcx, rax; hModule
0x1800cdfa2  call    cs:__imp_GetProcAddress
0x1800cdfa8  mov     rbx, rax
0x1800cdfab  lea     rax, [rbp+var_40]
0x1800cdfaf  mov     [rbp+arg_0], 0
0x1800cdfb6  mov     r9d, 4
0x1800cdfbc  mov     qword ptr [rsp+80h+var_60], rax
0x1800cdfc1  lea     r8, [rbp+arg_0]
0x1800cdfc5  mov     [rbp+var_40], 4
0x1800cdfcc  xor     edx, edx
0x1800cdfce  lea     rcx, asc_1800FE208; "$&"
0x1800cdfd5  call    cs:__imp_NtQueryLicenseValue
0x1800cdfdb  mov     ecx, [rbp+arg_0]
0x1800cdfde  add     ecx, 0FFFFFF55h
0x1800cdfe4  cmp     ecx, 1
0x1800cdfe7  ja      short loc_1800CE056
0x1800cdfe9  test    rbx, rbx
0x1800cdfec  jz      short loc_1800CE056
0x1800cdfee  lea     rax, [rbp+var_3C]
0x1800cdff2  mov     [rsp+80h+var_58], rax
0x1800cdff7  lea     r9, [rbp+arg_10]
0x1800cdffb  lea     rax, [rbp+arg_18]
0x1800cdfff  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800ce004  lea     r8, [rbp+var_38]
0x1800ce008  mov     rax, rbx
0x1800ce00b  lea     rdx, [rbp+var_28]
0x1800ce00f  lea     rcx, [rbp+var_18]
0x1800ce013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ce018  mov     ebx, eax
0x1800ce01a  or      ebx, 10000000h
0x1800ce020  jl      short loc_1800CE03C
0x1800ce022  cmp     [rbp+arg_10], 1
0x1800ce026  jnz     short loc_1800CE034
0x1800ce028  mov     eax, [rbp+arg_18]
0x1800ce02b  cmp     eax, 3
0x1800ce02e  ja      short loc_1800CE034
0x1800ce030  mov     [rdi], eax
0x1800ce032  jmp     short loc_1800CE05A
0x1800ce034  mov     dword ptr [rdi], 0
0x1800ce03a  jmp     short loc_1800CE05A
0x1800ce03c  mov     rcx, [rbp+18h]; this
0x1800ce040  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\permission\\l"...
0x1800ce047  mov     r9d, ebx; char *
0x1800ce04a  mov     edx, 43Fh; void *
0x1800ce04f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce054  jmp     short loc_1800CE05A
0x1800ce056  xor     ebx, ebx
0x1800ce058  mov     [rsi], ebx
0x1800ce05a  mov     eax, ebx
0x1800ce05c  mov     rbx, [rsp+80h+arg_8]
0x1800ce064  add     rsp, 80h
0x1800ce06b  pop     rdi
0x1800ce06c  pop     rsi
0x1800ce06d  pop     rbp
0x1800ce06e  retn
```
