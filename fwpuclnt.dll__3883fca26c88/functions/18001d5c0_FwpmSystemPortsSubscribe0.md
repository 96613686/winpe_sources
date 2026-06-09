# FwpmSystemPortsSubscribe0

- ea: `0x18001d5c0`
- end: `0x18001d7b2`
- name: `FwpmSystemPortsSubscribe0`
- size: `498`
- prototype: `DWORD __stdcall(HANDLE engineHandle, void *reserved, FWPM_SYSTEM_PORTS_CALLBACK0 callback, void *context, HANDLE *sysPortsHandle)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x1800034e0`
- `0x18000438c`
- `0x180004540`
- `0x180004bdc`
- `0x180005fc8`
- `0x180011500`
- `0x180012bd0`
- `0x18001346a`
- `0x18001d5c0`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d6e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d6cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001d6cf`

## string_xrefs

- `0x18001d6c8`: `ntdll.dll`
- `0x18001d5e9`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters\PortKeywords`
- `0x18001d684`: `FwpmSystemPortsSubscribe0`
- `0x18001d69b`: `FwpmSystemPortsSubscribe0`
- `0x18001d708`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters\PortKeywords\`

## pseudocode

```c
DWORD __stdcall FwpmSystemPortsSubscribe0(
        HANDLE engineHandle,
        void *reserved,
        FWPM_SYSTEM_PORTS_CALLBACK0 callback,
        void *context,
        HANDLE *sysPortsHandle)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  const char *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rbx
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  __int64 v15; // r8
  unsigned int v16; // eax
  _QWORD *v18; // rdi
  _OWORD *v19; // [rsp+20h] [rbp-E0h]
  _QWORD *v20; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v22; // [rsp+D0h] [rbp-30h]
  _BYTE v23[398]; // [rsp+D2h] [rbp-2Eh] BYREF

  v21[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords";
  v21[1] = *(_OWORD *)L"urrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords";
  v20 = 0;
  v21[2] = *(_OWORD *)L"ntrolSet\\Services\\MpsSvc\\Parameters\\PortKeywords";
  v22 = aSystemCurrentc_6[64];
  v21[3] = *(_OWORD *)L"\\Services\\MpsSvc\\Parameters\\PortKeywords";
  v21[4] = *(_OWORD *)L"s\\MpsSvc\\Parameters\\PortKeywords";
  v21[5] = *(_OWORD *)L"\\Parameters\\PortKeywords";
  v21[6] = *(_OWORD *)L"ers\\PortKeywords";
  v21[7] = *(_OWORD *)L"Keywords";
  memset_0(v23, 0, 0x186u);
  if ( reserved )
  {
    v9 = 3221225659LL;
    v10 = "FwpmSystemPortsSubscribe0";
  }
  else
  {
    if ( !callback || !sysPortsHandle )
    {
      v11 = WfpReportSysErrorAsWinError(v8, "FwpmSystemPortsSubscribe0", 2150760476LL);
      goto LABEL_11;
    }
    v12 = WfpMemAlloc(0x18u, 0);
    if ( v12 )
    {
LABEL_12:
      WfpMemFree(&v20);
      return WfpErrorToFwpErr(v12);
    }
    ModuleHandleA = GetModuleHandleA("ntdll.dll");
    ProcAddress = GetProcAddress(ModuleHandleA, "RtlGetPersistedStateLocation");
    if ( !ProcAddress
      || (v19 = v21,
          (v16 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, const wchar_t *, _QWORD))ProcAddress)(
                   L"MpssvcParametersPortKeywords",
                   0,
                   L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\",
                   0)) == 0) )
    {
      v18 = v20;
      v12 = WfpRegNotifyCreate(v8, v21, v15, 5, (__int64)v19, (__int64)FwppSystemPortsOnChange, (__int64)v20, v20);
      if ( !v12 )
      {
        v20[1] = callback;
        v18[2] = context;
        *sysPortsHandle = v18;
        return WfpErrorToFwpErr(v12);
      }
      goto LABEL_12;
    }
    v9 = v16;
    v10 = "pFuncGetPersistedStateLocation";
  }
  v11 = WfpReportSysErrorAsNtStatus(v8, v10, v9);
LABEL_11:
  v12 = v11;
  if ( v11 )
    goto LABEL_12;
  return WfpErrorToFwpErr(v12);
}

```

## disassembly

```asm
0x18001d5c0  push    rbp
0x18001d5c2  push    rbx
0x18001d5c3  push    rsi
0x18001d5c4  push    rdi
0x18001d5c5  push    r14
0x18001d5c7  push    r15
0x18001d5c9  lea     rbp, [rsp-178h]
0x18001d5d1  sub     rsp, 278h
0x18001d5d8  mov     rax, cs:__security_cookie
0x18001d5df  xor     rax, rsp
0x18001d5e2  mov     [rbp+1A0h+var_40], rax
0x18001d5e9  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18001d5f0  lea     rcx, [rbp+1A0h+var_1CE]; void *
0x18001d5f4  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+10h; "urrentControlSet\\Services\\MpsSvc\\Par"...
0x18001d5fb  mov     rsi, r8
0x18001d5fe  movzx   eax, word ptr cs:aSystemCurrentc_6+80h; ""
0x18001d605  mov     rbx, rdx
0x18001d608  mov     r14, [rbp+1A0h+sysPortsHandle]
0x18001d60f  xor     edx, edx; Val
0x18001d611  movups  [rsp+2A0h+var_250], xmm0
0x18001d616  mov     r8d, 186h; Size
0x18001d61c  mov     r15, r9
0x18001d61f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+20h; "ntrolSet\\Services\\MpsSvc\\Parameters"...
0x18001d626  movups  [rsp+2A0h+var_240], xmm1
0x18001d62b  mov     [rsp+2A0h+var_260], 0
0x18001d634  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+30h; "\\Services\\MpsSvc\\Parameters\\PortKey"...
0x18001d63b  movups  [rsp+2A0h+var_230], xmm0
0x18001d640  mov     [rbp+1A0h+var_1D0], ax
0x18001d644  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+40h; "s\\MpsSvc\\Parameters\\PortKeywords"
0x18001d64b  movups  [rbp+1A0h+var_220], xmm1
0x18001d64f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+50h; "\\Parameters\\PortKeywords"
0x18001d656  movups  [rbp+1A0h+var_210], xmm0
0x18001d65a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_6+60h; "ers\\PortKeywords"
0x18001d661  movups  [rbp+1A0h+var_200], xmm1
0x18001d665  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_6+70h; "Keywords"
0x18001d66c  movups  [rbp+1A0h+var_1F0], xmm0
0x18001d670  movups  [rbp+1A0h+var_1E0], xmm1
0x18001d674  call    memset_0
0x18001d679  test    rbx, rbx
0x18001d67c  jz      short loc_18001D690
0x18001d67e  mov     r8d, 0C00000BBh
0x18001d684  lea     rdx, aFwpmsystemport_2; "FwpmSystemPortsSubscribe0"
0x18001d68b  jmp     loc_18001D733
0x18001d690  test    rsi, rsi
0x18001d693  jnz     short loc_18001D6AC
0x18001d695  mov     r8d, 8032001Ch
0x18001d69b  lea     rdx, aFwpmsystemport_2; "FwpmSystemPortsSubscribe0"
0x18001d6a2  call    WfpReportSysErrorAsWinError
0x18001d6a7  jmp     loc_18001D738
0x18001d6ac  test    r14, r14
0x18001d6af  jz      short loc_18001D695
0x18001d6b1  xor     edx, edx; dwFlags
0x18001d6b3  lea     r8, [rsp+2A0h+var_260]
0x18001d6b8  lea     ecx, [rdx+18h]; dwBytes
0x18001d6bb  call    WfpMemAlloc
0x18001d6c0  mov     rbx, rax
0x18001d6c3  test    rax, rax
0x18001d6c6  jnz     short loc_18001D740
0x18001d6c8  lea     rcx, ModuleName; "ntdll.dll"
0x18001d6cf  call    cs:__imp_GetModuleHandleA
0x18001d6d6  nop     dword ptr [rax+rax+00h]
0x18001d6db  mov     rcx, rax; hModule
0x18001d6de  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x18001d6e5  call    cs:__imp_GetProcAddress
0x18001d6ec  nop     dword ptr [rax+rax+00h]
0x18001d6f1  test    rax, rax
0x18001d6f4  jz      short loc_18001D772
0x18001d6f6  mov     [rsp+2A0h+var_270], rbx
0x18001d6fb  lea     rcx, [rsp+2A0h+var_250]
0x18001d700  mov     dword ptr [rsp+2A0h+var_278], 208h
0x18001d708  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18001d70f  mov     [rsp+2A0h+var_280], rcx
0x18001d714  xor     r9d, r9d
0x18001d717  lea     rcx, aMpssvcparamete; "MpssvcParametersPortKeywords"
0x18001d71e  xor     edx, edx
0x18001d720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d725  test    eax, eax
0x18001d727  jz      short loc_18001D772
0x18001d729  mov     r8d, eax
0x18001d72c  lea     rdx, aPfuncgetpersis; "pFuncGetPersistedStateLocation"
0x18001d733  call    WfpReportSysErrorAsNtStatus
0x18001d738  mov     rbx, rax
0x18001d73b  test    rax, rax
0x18001d73e  jz      short loc_18001D74A
0x18001d740  lea     rcx, [rsp+2A0h+var_260]
0x18001d745  call    WfpMemFree
0x18001d74a  mov     rcx, rbx
0x18001d74d  call    WfpErrorToFwpErr
0x18001d752  mov     rcx, [rbp+1A0h+var_40]
0x18001d759  xor     rcx, rsp; StackCookie
0x18001d75c  call    __security_check_cookie
0x18001d761  add     rsp, 278h
0x18001d768  pop     r15
0x18001d76a  pop     r14
0x18001d76c  pop     rdi
0x18001d76d  pop     rsi
0x18001d76e  pop     rbx
0x18001d76f  pop     rbp
0x18001d770  retn
0x18001d772  mov     rdi, [rsp+2A0h+var_260]
0x18001d777  lea     rax, FwppSystemPortsOnChange
0x18001d77e  mov     [rsp+2A0h+var_268], rdi
0x18001d783  lea     rdx, [rsp+2A0h+var_250]
0x18001d788  mov     [rsp+2A0h+var_270], rdi
0x18001d78d  mov     r9d, 5
0x18001d793  mov     [rsp+2A0h+var_278], rax
0x18001d798  call    WfpRegNotifyCreate
0x18001d79d  mov     rbx, rax
0x18001d7a0  test    rax, rax
0x18001d7a3  jnz     short loc_18001D740
0x18001d7a5  mov     [rdi+8], rsi
0x18001d7a9  mov     [rdi+10h], r15
0x18001d7ad  mov     [r14], rdi
0x18001d7b0  jmp     short loc_18001D74A
```
