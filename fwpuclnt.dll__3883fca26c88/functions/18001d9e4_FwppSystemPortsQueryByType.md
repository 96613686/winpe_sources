# FwppSystemPortsQueryByType

- ea: `0x18001d9e4`
- end: `0x18001dc6e`
- name: `FwppSystemPortsQueryByType`
- size: `650`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x18001d83c`

## callees

- `0x18000438c`
- `0x180007e38`
- `0x18000b6a0`
- `0x18000e374`
- `0x180011500`
- `0x180011de0`
- `0x180012bd0`
- `0x18001346a`
- `0x18001d9e4`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001dac7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001dac7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001db0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001daf8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18001daf8`

## string_xrefs

- `0x18001daf1`: `ntdll.dll`
- `0x18001da0b`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters\PortKeywords\RPC-EPMap`
- `0x18001dc3e`: `FwppSystemPortsQueryByType`

## pseudocode

```c
__int64 __fastcall FwppSystemPortsQueryByType(int a1, unsigned int *a2, _QWORD *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  unsigned int v11; // eax
  __int64 v12; // rcx
  __int64 Value; // rax
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 i; // r8
  SIZE_T dwBytes; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[22]; // [rsp+E0h] [rbp-20h]
  _BYTE v25[378]; // [rsp+F6h] [rbp-Ah] BYREF

  v23[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v5 = a1;
  v23[2] = *(_OWORD *)L"ntrolSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v23[1] = *(_OWORD *)L"urrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v22 = 0;
  v23[4] = *(_OWORD *)L"s\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v21 = 0;
  v23[3] = *(_OWORD *)L"\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v23[6] = *(_OWORD *)L"ers\\PortKeywords\\RPC-EPMap";
  v23[5] = *(_OWORD *)L"\\Parameters\\PortKeywords\\RPC-EPMap";
  *(_OWORD *)v24 = *(_OWORD *)L"\\RPC-EPMap";
  *(_QWORD *)&v24[14] = *(_QWORD *)L"Map";
  v23[7] = *(_OWORD *)L"Keywords\\RPC-EPMap";
  memset_0(v25, 0, 0x172u);
  if ( (unsigned int)_o_wcscpy_s(v23, 260, FWPP_KEYWORD_REG_KEYS[v5]) )
  {
    v7 = WfpReportSysErrorAsHResult(v6, "wcscpy_s", 2147942487LL);
LABEL_3:
    v8 = v7;
    goto LABEL_17;
  }
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  ProcAddress = GetProcAddress(ModuleHandleA, "RtlGetPersistedStateLocation");
  if ( ProcAddress )
  {
    v20 = 0;
    v11 = ((__int64 (__fastcall *)(wchar_t *, _QWORD, wchar_t *, _QWORD, _OWORD *, int))ProcAddress)(
            FWPP_KEYWORD_MAP_IDS[v5],
            0,
            FWPP_KEYWORD_REG_KEYS[v5],
            0,
            v23,
            520);
    if ( v11 )
    {
      v7 = WfpReportSysErrorAsNtStatus(v12, "pFuncGetPersistedStateLocation", v11);
      goto LABEL_3;
    }
  }
  LODWORD(dwBytes) = 4096;
  Value = BfeRegQueryValue(HKEY_LOCAL_MACHINE, dwBytes, 1, v20, (__int64)&v21 + 4, (__int64)&v22, (__int64)&v21);
  v8 = Value;
  if ( Value )
  {
    WfpReportError(Value, "BfeRegQueryBinary");
  }
  else if ( (_DWORD)v21 && HIDWORD(v21) && (v21 & 0x300000000LL) == 0 )
  {
    v15 = HIDWORD(v21) >> 2;
    v8 = WfpMemAllocArray(HIDWORD(v21) >> 2, v14, 0, a3);
    if ( !v8 )
    {
      v16 = v22;
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
        *(_WORD *)(*a3 + 2 * i) = *(_WORD *)(v16 + 4 * i);
      *a2 = v15;
    }
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
LABEL_17:
  WfpMemFree(&v22);
  if ( v8 )
    WfpReportError(v8, "FwppSystemPortsQueryByType");
  return v8;
}

```

## disassembly

```asm
0x18001d9e4  push    rbp
0x18001d9e6  push    rbx
0x18001d9e7  push    rsi
0x18001d9e8  push    rdi
0x18001d9e9  push    r14
0x18001d9eb  lea     rbp, [rsp-180h]
0x18001d9f3  sub     rsp, 280h
0x18001d9fa  mov     rax, cs:__security_cookie
0x18001da01  xor     rax, rsp
0x18001da04  mov     [rbp+1A0h+var_30], rax
0x18001da0b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18001da12  mov     rsi, r8
0x18001da15  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_5+10h; "urrentControlSet\\Services\\MpsSvc\\Par"...
0x18001da1c  mov     r14, rdx
0x18001da1f  mov     rax, qword ptr cs:aSystemCurrentc_5+8Eh; "Map"
0x18001da26  xor     edx, edx; Val
0x18001da28  movups  [rsp+2A0h+var_240], xmm0
0x18001da2d  mov     r8d, 172h; Size
0x18001da33  movsxd  rbx, ecx
0x18001da36  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_5+20h; "ntrolSet\\Services\\MpsSvc\\Parameters"...
0x18001da3d  lea     rcx, [rbp+1A0h+var_1AA]; void *
0x18001da41  movups  [rbp+1A0h+var_220], xmm0
0x18001da45  mov     dword ptr [rsp+2A0h+var_250+4], 0
0x18001da4d  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_5+40h; "s\\MpsSvc\\Parameters\\PortKeywords\\RP"...
0x18001da54  movups  [rsp+2A0h+var_230], xmm1
0x18001da59  mov     [rsp+2A0h+var_248], 0
0x18001da62  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_5+30h; "\\Services\\MpsSvc\\Parameters\\PortKey"...
0x18001da69  movups  [rbp+1A0h+var_200], xmm0
0x18001da6d  mov     dword ptr [rsp+2A0h+var_250], 0
0x18001da75  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_5+60h; "ers\\PortKeywords\\RPC-EPMap"
0x18001da7c  movups  [rbp+1A0h+var_210], xmm1
0x18001da80  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_5+50h; "\\Parameters\\PortKeywords\\RPC-EPMap"
0x18001da87  movups  [rbp+1A0h+var_1E0], xmm0
0x18001da8b  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_5+80h; "\\RPC-EPMap"
0x18001da92  movups  [rbp+1A0h+var_1F0], xmm1
0x18001da96  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_5+70h; "Keywords\\RPC-EPMap"
0x18001da9d  movups  xmmword ptr [rbp+1A0h+var_1C0], xmm0
0x18001daa1  mov     qword ptr [rbp+1A0h+var_1C0+0Eh], rax
0x18001daa5  movups  [rbp+1A0h+var_1D0], xmm1
0x18001daa9  call    memset_0
0x18001daae  lea     rdi, __ImageBase
0x18001dab5  mov     edx, 104h
0x18001daba  mov     r8, ds:rva FWPP_KEYWORD_REG_KEYS[rdi+rbx*8]
0x18001dac2  lea     rcx, [rsp+2A0h+var_240]
0x18001dac7  call    cs:__imp__o_wcscpy_s
0x18001dace  nop     dword ptr [rax+rax+00h]
0x18001dad3  test    eax, eax
0x18001dad5  jz      short loc_18001DAF1
0x18001dad7  mov     r8d, 80070057h
0x18001dadd  lea     rdx, aWcscpyS; "wcscpy_s"
0x18001dae4  call    WfpReportSysErrorAsHResult
0x18001dae9  mov     rbx, rax
0x18001daec  jmp     loc_18001DC2F
0x18001daf1  lea     rcx, ModuleName; "ntdll.dll"
0x18001daf8  call    cs:__imp_GetModuleHandleA
0x18001daff  nop     dword ptr [rax+rax+00h]
0x18001db04  mov     rcx, rax; hModule
0x18001db07  lea     rdx, ProcName; "RtlGetPersistedStateLocation"
0x18001db0e  call    cs:__imp_GetProcAddress
0x18001db15  nop     dword ptr [rax+rax+00h]
0x18001db1a  test    rax, rax
0x18001db1d  jz      short loc_18001DB69
0x18001db1f  mov     r8, ds:rva FWPP_KEYWORD_REG_KEYS[rdi+rbx*8]
0x18001db27  lea     rcx, [rsp+2A0h+var_240]
0x18001db2c  mov     [rsp+2A0h+var_270], 0
0x18001db35  xor     r9d, r9d
0x18001db38  mov     [rsp+2A0h+var_278], 208h
0x18001db40  xor     edx, edx
0x18001db42  mov     [rsp+2A0h+dwBytes], rcx
0x18001db47  mov     rcx, ds:rva FWPP_KEYWORD_MAP_IDS[rdi+rbx*8]
0x18001db4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db54  test    eax, eax
0x18001db56  jz      short loc_18001DB69
0x18001db58  mov     r8d, eax
0x18001db5b  lea     rdx, aPfuncgetpersis; "pFuncGetPersistedStateLocation"
0x18001db62  call    WfpReportSysErrorAsNtStatus
0x18001db67  jmp     short loc_18001DAE9
0x18001db69  lea     rax, [rsp+2A0h+var_250]
0x18001db6e  mov     r9d, 3
0x18001db74  mov     [rsp+2A0h+var_258], rax; __int64
0x18001db79  lea     r8, aCollection; "Collection"
0x18001db80  lea     rax, [rsp+2A0h+var_248]
0x18001db85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001db8c  mov     [rsp+2A0h+var_260], rax; __int64
0x18001db91  lea     rdx, [rsp+2A0h+var_240]
0x18001db96  lea     rax, [rsp+2A0h+var_250+4]
0x18001db9b  mov     [rsp+2A0h+var_268], rax; __int64
0x18001dba0  mov     [rsp+2A0h+var_278], 1; int
0x18001dba8  mov     dword ptr [rsp+2A0h+dwBytes], 1000h; dwBytes
0x18001dbb0  call    BfeRegQueryValue
0x18001dbb5  mov     rbx, rax
0x18001dbb8  test    rax, rax
0x18001dbbb  jz      short loc_18001DBCE
0x18001dbbd  lea     rdx, aBferegquerybin; "BfeRegQueryBinary"
0x18001dbc4  mov     rcx, rax
0x18001dbc7  call    WfpReportError
0x18001dbcc  jmp     short loc_18001DC2F
0x18001dbce  cmp     dword ptr [rsp+2A0h+var_250], 0
0x18001dbd3  jz      short loc_18001DC21
0x18001dbd5  mov     edi, dword ptr [rsp+2A0h+var_250+4]
0x18001dbd9  test    edi, edi
0x18001dbdb  jz      short loc_18001DC21
0x18001dbdd  test    dil, 3
0x18001dbe1  jnz     short loc_18001DC21
0x18001dbe3  shr     edi, 2
0x18001dbe6  mov     r9, rsi
0x18001dbe9  mov     ecx, edi
0x18001dbeb  xor     r8d, r8d
0x18001dbee  call    WfpMemAllocArray
0x18001dbf3  mov     rbx, rax
0x18001dbf6  test    rax, rax
0x18001dbf9  jnz     short loc_18001DC2F
0x18001dbfb  mov     r9, [rsp+2A0h+var_248]
0x18001dc00  xor     r8d, r8d
0x18001dc03  test    edi, edi
0x18001dc05  jz      short loc_18001DC1C
0x18001dc07  movzx   eax, word ptr [r9+r8*4]
0x18001dc0c  mov     rcx, [rsi]
0x18001dc0f  mov     [rcx+r8*2], ax
0x18001dc14  inc     r8d
0x18001dc17  cmp     r8d, edi
0x18001dc1a  jb      short loc_18001DC07
0x18001dc1c  mov     [r14], edi
0x18001dc1f  jmp     short loc_18001DC2F
0x18001dc21  mov     dword ptr [r14], 0
0x18001dc28  mov     qword ptr [rsi], 0
0x18001dc2f  lea     rcx, [rsp+2A0h+var_248]
0x18001dc34  call    WfpMemFree
0x18001dc39  test    rbx, rbx
0x18001dc3c  jz      short loc_18001DC4D
0x18001dc3e  lea     rdx, aFwppsystemport; "FwppSystemPortsQueryByType"
0x18001dc45  mov     rcx, rbx
0x18001dc48  call    WfpReportError
0x18001dc4d  mov     rax, rbx
0x18001dc50  mov     rcx, [rbp+1A0h+var_30]
0x18001dc57  xor     rcx, rsp; StackCookie
0x18001dc5a  call    __security_check_cookie
0x18001dc5f  add     rsp, 280h
0x18001dc66  pop     r14
0x18001dc68  pop     rdi
0x18001dc69  pop     rsi
0x18001dc6a  pop     rbx
0x18001dc6b  pop     rbp
0x18001dc6c  retn
```
