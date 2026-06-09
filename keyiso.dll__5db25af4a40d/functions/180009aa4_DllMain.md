# DllMain

- ea: `0x180009aa4`
- end: `0x180009c17`
- name: `DllMain`
- size: `371`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c674`

## callees

- `0x180004470`
- `0x180009aa4`
- `0x18000b45c`
- `0x18000b584`
- `0x18000ba90`
- `0x18000c1b8`
- `0x180016de8`
- `0x180016e54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009b67`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009b7b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180009b7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009b9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009b9d`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180009ac4`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x180009ac4`

## string_xrefs

- `0x180009b3e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\keyiso.cxx`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v4; // edx
  int v5; // r8d
  __int64 v7; // r8
  __int64 v8; // r8

  g_hInstance = (__int64)hinstDLL;
  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      UninitializeCNG();
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v8, hinstDLL);
      WppCleanupUm();
    }
    return 1;
  }
  LdrDisableThreadCalloutsForDll(hinstDLL);
  DllMainCRTStartupForGS2((__int64)hinstDLL, 1);
  qword_180025CB8 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CNGTraceControlGuid;
  qword_180025CB0 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  v4 = InitializeCNG();
  if ( v4 >= 0 )
  {
    InitializeSRWLock(&g_ngcFuncLoadLock);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      GetModuleFileNameW(0, &Filename, 0x100u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v7, hinstDLL);
    }
    return 1;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      v5,
      (unsigned int)"ntStatus",
      v4,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\keyiso.cxx",
      26);
  SetLastError(0x54Fu);
  return 0;
}

```

## disassembly

```asm
0x180009aa4  mov     [rsp+arg_0], rbx
0x180009aa9  push    rdi
0x180009aaa  sub     rsp, 40h
0x180009aae  mov     cs:g_hInstance, rcx
0x180009ab5  mov     rbx, r8
0x180009ab8  mov     rdi, rcx
0x180009abb  cmp     edx, 1
0x180009abe  jnz     loc_180009BCF
0x180009ac4  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x180009aca  mov     r8, rbx
0x180009acd  mov     edx, 1
0x180009ad2  mov     rcx, rdi
0x180009ad5  call    _DllMainCRTStartupForGS2
0x180009ada  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x180009ae1  mov     cs:qword_180025CB8, 1
0x180009aec  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180009af3  xor     ebx, ebx
0x180009af5  lea     rax, WPP_MAIN_CB
0x180009afc  mov     cs:qword_180025CB0, rbx
0x180009b03  mov     cs:WPP_GLOBAL_Control, rax
0x180009b0a  mov     cs:WPP_MAIN_CB, rbx
0x180009b11  call    WppInitUm
0x180009b16  call    InitializeCNG
0x180009b1b  mov     edx, eax
0x180009b1d  test    eax, eax
0x180009b1f  jns     short loc_180009B74
0x180009b21  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b28  lea     rax, WPP_GLOBAL_Control
0x180009b2f  cmp     rcx, rax
0x180009b32  jz      short loc_180009B62
0x180009b34  test    byte ptr [rcx+1Ch], 1
0x180009b38  jz      short loc_180009B62
0x180009b3a  mov     rcx, [rcx+10h]
0x180009b3e  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009b45  mov     [rsp+48h+var_18], 11Ah
0x180009b4d  lea     r9, aNtstatus; "ntStatus"
0x180009b54  mov     [rsp+48h+var_20], rax
0x180009b59  mov     [rsp+48h+var_28], edx
0x180009b5d  call    WPP_SF_sDsd
0x180009b62  mov     ecx, 54Fh; dwErrCode
0x180009b67  call    cs:__imp_SetLastError
0x180009b6d  xor     eax, eax
0x180009b6f  jmp     loc_180009C0C
0x180009b74  lea     rcx, ?g_ngcFuncLoadLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180009b7b  call    cs:__imp_InitializeSRWLock
0x180009b81  mov     rax, cs:WPP_GLOBAL_Control
0x180009b88  test    byte ptr [rax+1Ch], 20h
0x180009b8c  jz      short loc_180009C07
0x180009b8e  mov     r8d, 100h; nSize
0x180009b94  lea     rdx, Filename; lpFilename
0x180009b9b  xor     ecx, ecx; hModule
0x180009b9d  call    cs:__imp_GetModuleFileNameW
0x180009ba3  mov     rcx, cs:WPP_GLOBAL_Control
0x180009baa  lea     rax, WPP_GLOBAL_Control
0x180009bb1  cmp     rcx, rax
0x180009bb4  jz      short loc_180009C07
0x180009bb6  test    byte ptr [rcx+1Ch], 20h
0x180009bba  jz      short loc_180009C07
0x180009bbc  mov     rcx, [rcx+10h]
0x180009bc0  mov     edx, 0Ah
0x180009bc5  mov     r9, rdi
0x180009bc8  call    WPP_SF_qS
0x180009bcd  jmp     short loc_180009C07
0x180009bcf  test    edx, edx
0x180009bd1  jnz     short loc_180009C07
0x180009bd3  call    UninitializeCNG
0x180009bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bdf  test    byte ptr [rcx+1Ch], 20h
0x180009be3  jz      short loc_180009C02
0x180009be5  lea     rax, WPP_GLOBAL_Control
0x180009bec  cmp     rcx, rax
0x180009bef  jz      short loc_180009C02
0x180009bf1  mov     rcx, [rcx+10h]
0x180009bf5  mov     edx, 0Bh
0x180009bfa  mov     r9, rdi
0x180009bfd  call    WPP_SF_qS
0x180009c02  call    WppCleanupUm
0x180009c07  mov     eax, 1
0x180009c0c  mov     rbx, [rsp+48h+arg_0]
0x180009c11  add     rsp, 40h
0x180009c15  pop     rdi
0x180009c16  retn
```
