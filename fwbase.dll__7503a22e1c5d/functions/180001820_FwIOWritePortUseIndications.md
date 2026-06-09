# FwIOWritePortUseIndications

- ea: `0x180001820`
- end: `0x1800019e9`
- name: `FwIOWritePortUseIndications`
- size: `457`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001820`
- `0x180001a58`
- `0x1800047e0`
- `0x18001e1d0`
- `0x18001eb54`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800018f6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800018f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000191b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000191b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000190b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000190b`

## string_xrefs

- `0x180001847`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters\PortKeywords\RPC-EPMap`
- `0x180001914`: `GetPersistedRegistryLocationW`
- `0x180001904`: `kernelbase.dll`
- `0x1800019af`: `FwIOWritePortUseIndications`
- `0x1800019c4`: `FwIOWritePortUseIndications`
- `0x1800019d2`: `FwIOWritePortUseIndications`

## pseudocode

```c
__int64 __fastcall FwIOWritePortUseIndications(int a1, unsigned __int8 *a2, int a3)
{
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // r8
  unsigned int v10; // ebx
  signed int v12; // eax
  unsigned __int16 v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v14; // [rsp+40h] [rbp-C0h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  __int128 v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h]
  __int128 v18; // [rsp+80h] [rbp-80h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  _BYTE v21[22]; // [rsp+B0h] [rbp-50h]
  _BYTE v22[378]; // [rsp+C6h] [rbp-3Ah] BYREF

  *(_OWORD *)v13 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v5 = a1;
  v15 = *(_OWORD *)L"ntrolSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v14 = *(_OWORD *)L"urrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v17 = *(_OWORD *)L"s\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v16 = *(_OWORD *)L"\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v19 = *(_OWORD *)L"ers\\PortKeywords\\RPC-EPMap";
  v18 = *(_OWORD *)L"\\Parameters\\PortKeywords\\RPC-EPMap";
  *(_OWORD *)v21 = *(_OWORD *)L"\\RPC-EPMap";
  *(_QWORD *)&v21[14] = *(_QWORD *)L"Map";
  v20 = *(_OWORD *)L"Keywords\\RPC-EPMap";
  memset_0(v22, 0, 0x172u);
  if ( (unsigned int)v5 > 8 || (unsigned int)_o_wcscpy_s(v13, 260, (&wszKeywordRegNames)[v5]) )
  {
    v10 = -2147024809;
    goto LABEL_13;
  }
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "GetPersistedRegistryLocationW");
  if ( !ProcAddress
    || ((v12 = ((__int64 (__fastcall *)(unsigned __int16 * near *, unsigned __int16 * near *, unsigned __int16 *, __int64, _QWORD))ProcAddress)(
                 (&wszKeywordRegMapIds)[v5],
                 (&wszKeywordRegNames)[v5],
                 v13,
                 520,
                 0),
         v9 = 2147942400LL,
         v12 <= 0)
      ? (v8 = (unsigned int)v12)
      : (v8 = (unsigned __int16)v12 | 0x80070000),
        (v8 & 0x80000000) == 0LL) )
  {
    v10 = FwRegSetBinary((HKEY)v8, v13, (const unsigned __int16 *)v9, a2, 4 * a3);
    if ( (v10 & 0x80000000) == 0 )
      return v10;
LABEL_13:
    FwReportReturnError("FwIOWritePortUseIndications", v10);
    return (unsigned int)FwReportReturnError("FwIOWritePortUseIndications", v10);
  }
  v10 = 0;
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  FwReportReturnError("FwIOWritePortUseIndications", (unsigned int)v12);
  return v10;
}

```

## disassembly

```asm
0x180001820  push    rbp
0x180001822  push    rbx
0x180001823  push    rsi
0x180001824  push    rdi
0x180001825  push    r14
0x180001827  lea     rbp, [rsp-150h]
0x18000182f  sub     rsp, 250h
0x180001836  mov     rax, cs:__security_cookie
0x18000183d  xor     rax, rsp
0x180001840  mov     [rbp+170h+var_30], rax
0x180001847  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18000184e  mov     esi, r8d
0x180001851  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+10h; "urrentControlSet\\Services\\MpsSvc\\Par"...
0x180001858  mov     rdi, rdx
0x18000185b  mov     rax, qword ptr cs:aSystemCurrentc_7+8Eh; "Map"
0x180001862  xor     edx, edx; Val
0x180001864  movups  xmmword ptr [rsp+270h+var_240], xmm0
0x180001869  mov     r8d, 172h; Size
0x18000186f  movsxd  rbx, ecx
0x180001872  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+20h; "ntrolSet\\Services\\MpsSvc\\Parameters"...
0x180001879  lea     rcx, [rbp+170h+var_1AA]; void *
0x18000187d  movups  [rsp+270h+var_220], xmm0
0x180001882  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+40h; "s\\MpsSvc\\Parameters\\PortKeywords\\RP"...
0x180001889  movups  [rsp+270h+var_230], xmm1
0x18000188e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+30h; "\\Services\\MpsSvc\\Parameters\\PortKey"...
0x180001895  movups  [rsp+270h+var_200], xmm0
0x18000189a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+60h; "ers\\PortKeywords\\RPC-EPMap"
0x1800018a1  movups  [rsp+270h+var_210], xmm1
0x1800018a6  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+50h; "\\Parameters\\PortKeywords\\RPC-EPMap"
0x1800018ad  movups  [rbp+170h+var_1E0], xmm0
0x1800018b1  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+80h; "\\RPC-EPMap"
0x1800018b8  movups  [rbp+170h+var_1F0], xmm1
0x1800018bc  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+70h; "Keywords\\RPC-EPMap"
0x1800018c3  movups  xmmword ptr [rbp+170h+var_1C0], xmm0
0x1800018c7  mov     qword ptr [rbp+170h+var_1C0+0Eh], rax
0x1800018cb  movups  [rbp+170h+var_1D0], xmm1
0x1800018cf  call    memset_0
0x1800018d4  cmp     ebx, 8
0x1800018d7  ja      loc_1800019BD
0x1800018dd  lea     r14, __ImageBase
0x1800018e4  mov     edx, 104h
0x1800018e9  mov     r8, ds:rva ?wszKeywordRegNames@@3PAPEAGA[r14+rbx*8]; ushort * near * wszKeywordRegNames ...
0x1800018f1  lea     rcx, [rsp+270h+var_240]
0x1800018f6  call    cs:__imp__o_wcscpy_s
0x1800018fc  test    eax, eax
0x1800018fe  jnz     loc_1800019BD
0x180001904  lea     rcx, ModuleName; "kernelbase.dll"
0x18000190b  call    cs:__imp_GetModuleHandleW
0x180001911  mov     rcx, rax; hModule
0x180001914  lea     rdx, ProcName; "GetPersistedRegistryLocationW"
0x18000191b  call    cs:__imp_GetProcAddress
0x180001921  test    rax, rax
0x180001924  jnz     short loc_180001963
0x180001926  lea     eax, ds:0[rsi*4]
0x18000192d  mov     r9, rdi; unsigned __int8 *
0x180001930  lea     rdx, [rsp+270h+var_240]; unsigned __int16 *
0x180001935  mov     [rsp+270h+var_250], eax; unsigned int
0x180001939  call    ?FwRegSetBinary@@YAJPEAUHKEY__@@PEBG1PEAEK@Z; FwRegSetBinary(HKEY__ *,ushort const *,ushort const *,uchar *,ulong)
0x18000193e  mov     ebx, eax
0x180001940  test    eax, eax
0x180001942  js      short loc_1800019C2
0x180001944  mov     eax, ebx
0x180001946  mov     rcx, [rbp+170h+var_30]
0x18000194d  xor     rcx, rsp; StackCookie
0x180001950  call    __security_check_cookie
0x180001955  add     rsp, 250h
0x18000195c  pop     r14
0x18000195e  pop     rdi
0x18000195f  pop     rsi
0x180001960  pop     rbx
0x180001961  pop     rbp
0x180001962  retn
0x180001963  mov     rdx, ds:rva ?wszKeywordRegNames@@3PAPEAGA[r14+rbx*8]; ushort * near * wszKeywordRegNames ...
0x18000196b  lea     r8, [rsp+270h+var_240]
0x180001970  mov     rcx, ds:rva ?wszKeywordRegMapIds@@3PAPEAGA[r14+rbx*8]; ushort * near * wszKeywordRegMapIds ...
0x180001978  mov     r9d, 208h
0x18000197e  mov     qword ptr [rsp+270h+var_250], 0
0x180001987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000198c  movzx   edx, ax
0x18000198f  mov     r8d, 80070000h
0x180001995  test    eax, eax
0x180001997  jle     short loc_1800019E5
0x180001999  mov     ecx, edx
0x18000199b  or      ecx, r8d
0x18000199e  test    ecx, ecx
0x1800019a0  jns     short loc_180001926
0x1800019a2  xor     ebx, ebx
0x1800019a4  test    eax, eax
0x1800019a6  jle     short loc_1800019AD
0x1800019a8  mov     eax, edx
0x1800019aa  or      eax, r8d
0x1800019ad  mov     edx, eax
0x1800019af  lea     rcx, aFwiowriteportu_0; "FwIOWritePortUseIndications"
0x1800019b6  call    FwReportReturnError
0x1800019bb  jmp     short loc_180001944
0x1800019bd  mov     ebx, 80070057h
0x1800019c2  mov     edx, ebx
0x1800019c4  lea     rcx, aFwiowriteportu_0; "FwIOWritePortUseIndications"
0x1800019cb  call    FwReportReturnError
0x1800019d0  mov     edx, ebx
0x1800019d2  lea     rcx, aFwiowriteportu_0; "FwIOWritePortUseIndications"
0x1800019d9  call    FwReportReturnError
0x1800019de  mov     ebx, eax
0x1800019e0  jmp     loc_180001944
0x1800019e5  mov     ecx, eax
0x1800019e7  jmp     short loc_18000199E
```
