# FwIOReadPortUseIndications

- ea: `0x180006090`
- end: `0x180006322`
- name: `FwIOReadPortUseIndications`
- size: `658`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001b80`
- `0x1800047e0`
- `0x180006090`
- `0x180014268`
- `0x18001e1d0`
- `0x18001eb54`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800061bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800061bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800061dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800061cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800062b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800062a2`

## string_xrefs

- `0x1800060b7`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters\PortKeywords\RPC-EPMap`
- `0x1800061d6`: `GetPersistedRegistryLocationW`
- `0x1800061c6`: `kernelbase.dll`
- `0x18000615e`: `FwIOReadPortUseIndications`
- `0x18000616c`: `FwIOReadPortUseIndications`
- `0x180006286`: `FwIOReadPortUseIndications`
- `0x1800062f8`: `FwIOReadPortUseIndications`

## pseudocode

```c
__int64 __fastcall FwIOReadPortUseIndications(int a1, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // ebx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // r9d
  int v14; // eax
  unsigned int v15; // eax
  signed int v16; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v18; // rax
  int v19; // edx
  int v20; // r8d
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int128 v25; // [rsp+70h] [rbp-90h]
  __int128 v26; // [rsp+80h] [rbp-80h]
  __int128 v27; // [rsp+90h] [rbp-70h]
  __int128 v28; // [rsp+A0h] [rbp-60h]
  __int128 v29; // [rsp+B0h] [rbp-50h]
  __int128 v30; // [rsp+C0h] [rbp-40h]
  _BYTE v31[22]; // [rsp+D0h] [rbp-30h]
  _BYTE v32[378]; // [rsp+E6h] [rbp-1Ah] BYREF

  *(_OWORD *)v23 = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v5 = a1;
  v25 = *(_OWORD *)L"ntrolSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v22[0] = 0;
  v24 = *(_OWORD *)L"urrentControlSet\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v21 = 0;
  v27 = *(_OWORD *)L"s\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v26 = *(_OWORD *)L"\\Services\\MpsSvc\\Parameters\\PortKeywords\\RPC-EPMap";
  v29 = *(_OWORD *)L"ers\\PortKeywords\\RPC-EPMap";
  v28 = *(_OWORD *)L"\\Parameters\\PortKeywords\\RPC-EPMap";
  *(_OWORD *)v31 = *(_OWORD *)L"\\RPC-EPMap";
  *(_QWORD *)&v31[14] = *(_QWORD *)L"Map";
  v30 = *(_OWORD *)L"Keywords\\RPC-EPMap";
  memset_0(v32, 0, 0x172u);
  if ( (unsigned int)v5 > 8 || !a2 || !a3 || (unsigned int)_o_wcscpy_s(v23, 260, (&wszKeywordRegNames)[v5]) )
  {
    v6 = 2147942487LL;
    v7 = -2147024809;
    goto LABEL_3;
  }
  ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "GetPersistedRegistryLocationW");
  if ( !ProcAddress
    || ((v16 = ((__int64 (__fastcall *)(unsigned __int16 * near *, unsigned __int16 * near *, unsigned __int16 *, __int64, _QWORD))ProcAddress)(
                 (&wszKeywordRegMapIds)[v5],
                 (&wszKeywordRegNames)[v5],
                 v23,
                 520,
                 0),
         v12 = 2147942400LL,
         v16 <= 0)
      ? (v11 = (unsigned int)v16)
      : (v11 = (unsigned __int16)v16 | 0x80070000),
        (v11 & 0x80000000) == 0LL) )
  {
    v14 = FwRegQueryBinary((HKEY)v11, v23, (const unsigned __int16 *)v12, v13, a2, v22, &v21);
    v7 = v14;
    if ( v14 < 0 )
    {
      v6 = (unsigned int)v14;
    }
    else
    {
      if ( v21 )
      {
        v15 = v22[0];
      }
      else
      {
        ProcessHeap = GetProcessHeap();
        v18 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, 4u);
        *a2 = v18;
        if ( !v18 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_ssL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v19,
              v20,
              (unsigned int)"FwIOReadPortUseIndications",
              (__int64)"FwAlloc",
              8);
          v7 = -2147024888;
          return (unsigned int)FwReportReturnError("FwIOReadPortUseIndications", v7);
        }
        v15 = 0;
        v22[0] = 0;
      }
      if ( (v15 & 3) == 0 )
      {
        *a3 = v15 >> 2;
        return v7;
      }
      v7 = -2147024883;
      v6 = 2147942413LL;
    }
LABEL_3:
    FwReportReturnError("FwIOReadPortUseIndications", v6);
    return (unsigned int)FwReportReturnError("FwIOReadPortUseIndications", v7);
  }
  v7 = 0;
  if ( v16 > 0 )
    v16 = (unsigned __int16)v16 | 0x80070000;
  FwReportReturnError("FwIOReadPortUseIndications", (unsigned int)v16);
  return v7;
}

```

## disassembly

```asm
0x180006090  push    rbp
0x180006092  push    rbx
0x180006093  push    rsi
0x180006094  push    rdi
0x180006095  push    r15
0x180006097  lea     rbp, [rsp-170h]
0x18000609f  sub     rsp, 270h
0x1800060a6  mov     rax, cs:__security_cookie
0x1800060ad  xor     rax, rsp
0x1800060b0  mov     [rbp+190h+var_30], rax
0x1800060b7  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x1800060be  mov     rsi, r8
0x1800060c1  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+10h; "urrentControlSet\\Services\\MpsSvc\\Par"...
0x1800060c8  mov     rdi, rdx
0x1800060cb  mov     rax, qword ptr cs:aSystemCurrentc_7+8Eh; "Map"
0x1800060d2  xor     edx, edx; Val
0x1800060d4  movups  xmmword ptr [rsp+290h+var_240], xmm0
0x1800060d9  mov     r8d, 172h; Size
0x1800060df  movsxd  rbx, ecx
0x1800060e2  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+20h; "ntrolSet\\Services\\MpsSvc\\Parameters"...
0x1800060e9  lea     rcx, [rbp+190h+var_1AA]; void *
0x1800060ed  movups  [rsp+290h+var_220], xmm0
0x1800060f2  mov     [rsp+290h+var_24C], 0
0x1800060fa  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+40h; "s\\MpsSvc\\Parameters\\PortKeywords\\RP"...
0x180006101  movups  [rsp+290h+var_230], xmm1
0x180006106  mov     [rsp+290h+var_250], 0
0x18000610e  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+30h; "\\Services\\MpsSvc\\Parameters\\PortKey"...
0x180006115  movups  [rbp+190h+var_200], xmm0
0x180006119  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+60h; "ers\\PortKeywords\\RPC-EPMap"
0x180006120  movups  [rbp+190h+var_210], xmm1
0x180006124  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+50h; "\\Parameters\\PortKeywords\\RPC-EPMap"
0x18000612b  movups  [rbp+190h+var_1E0], xmm0
0x18000612f  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_7+80h; "\\RPC-EPMap"
0x180006136  movups  [rbp+190h+var_1F0], xmm1
0x18000613a  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_7+70h; "Keywords\\RPC-EPMap"
0x180006141  movups  xmmword ptr [rbp+190h+var_1C0], xmm0
0x180006145  mov     qword ptr [rbp+190h+var_1C0+0Eh], rax
0x180006149  movups  [rbp+190h+var_1D0], xmm1
0x18000614d  call    memset_0
0x180006152  cmp     ebx, 8
0x180006155  jbe     short loc_180006199
0x180006157  mov     edx, 80070057h
0x18000615c  mov     ebx, edx
0x18000615e  lea     rcx, aFwioreadportus_0; "FwIOReadPortUseIndications"
0x180006165  call    FwReportReturnError
0x18000616a  mov     edx, ebx
0x18000616c  lea     rcx, aFwioreadportus_0; "FwIOReadPortUseIndications"
0x180006173  call    FwReportReturnError
0x180006178  mov     ebx, eax
0x18000617a  mov     eax, ebx
0x18000617c  mov     rcx, [rbp+190h+var_30]
0x180006183  xor     rcx, rsp; StackCookie
0x180006186  call    __security_check_cookie
0x18000618b  add     rsp, 270h
0x180006192  pop     r15
0x180006194  pop     rdi
0x180006195  pop     rsi
0x180006196  pop     rbx
0x180006197  pop     rbp
0x180006198  retn
0x180006199  test    rdi, rdi
0x18000619c  jz      short loc_180006157
0x18000619e  test    rsi, rsi
0x1800061a1  jz      short loc_180006157
0x1800061a3  lea     r15, __ImageBase
0x1800061aa  mov     edx, 104h
0x1800061af  mov     r8, ds:rva ?wszKeywordRegNames@@3PAPEAGA[r15+rbx*8]; ushort * near * wszKeywordRegNames ...
0x1800061b7  lea     rcx, [rsp+290h+var_240]
0x1800061bc  call    cs:__imp__o_wcscpy_s
0x1800061c2  test    eax, eax
0x1800061c4  jnz     short loc_180006157
0x1800061c6  lea     rcx, ModuleName; "kernelbase.dll"
0x1800061cd  call    cs:__imp_GetModuleHandleW
0x1800061d3  mov     rcx, rax; hModule
0x1800061d6  lea     rdx, ProcName; "GetPersistedRegistryLocationW"
0x1800061dd  call    cs:__imp_GetProcAddress
0x1800061e3  test    rax, rax
0x1800061e6  jnz     short loc_180006236
0x1800061e8  lea     rax, [rsp+290h+var_250]
0x1800061ed  mov     [rsp+290h+var_260], rax; int *
0x1800061f2  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x1800061f7  lea     rax, [rsp+290h+var_24C]
0x1800061fc  mov     [rsp+290h+var_268], rax; unsigned int *
0x180006201  mov     [rsp+290h+var_270], rdi; unsigned __int8 **
0x180006206  call    ?FwRegQueryBinary@@YAJPEAUHKEY__@@PEBG1KPEAPEAEPEAKPEAH@Z; FwRegQueryBinary(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *,int *)
0x18000620b  mov     ebx, eax
0x18000620d  test    eax, eax
0x18000620f  js      loc_180006297
0x180006215  cmp     [rsp+290h+var_250], 0
0x18000621a  jz      loc_1800062A2
0x180006220  mov     eax, [rsp+290h+var_24C]
0x180006224  test    al, 3
0x180006226  jnz     loc_180006316
0x18000622c  shr     eax, 2
0x18000622f  mov     [rsi], eax
0x180006231  jmp     loc_18000617A
0x180006236  mov     rdx, ds:rva ?wszKeywordRegNames@@3PAPEAGA[r15+rbx*8]; ushort * near * wszKeywordRegNames ...
0x18000623e  lea     r8, [rsp+290h+var_240]
0x180006243  mov     rcx, ds:rva ?wszKeywordRegMapIds@@3PAPEAGA[r15+rbx*8]; ushort * near * wszKeywordRegMapIds ...
0x18000624b  mov     r9d, 208h
0x180006251  mov     [rsp+290h+var_270], 0
0x18000625a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625f  movzx   edx, ax
0x180006262  mov     r8d, 80070000h
0x180006268  test    eax, eax
0x18000626a  jle     short loc_18000629E
0x18000626c  mov     ecx, edx
0x18000626e  or      ecx, r8d
0x180006271  test    ecx, ecx
0x180006273  jns     loc_1800061E8
0x180006279  xor     ebx, ebx
0x18000627b  test    eax, eax
0x18000627d  jle     short loc_180006284
0x18000627f  mov     eax, edx
0x180006281  or      eax, r8d
0x180006284  mov     edx, eax
0x180006286  lea     rcx, aFwioreadportus_0; "FwIOReadPortUseIndications"
0x18000628d  call    FwReportReturnError
0x180006292  jmp     loc_18000617A
0x180006297  mov     edx, eax
0x180006299  jmp     loc_18000615E
0x18000629e  mov     ecx, eax
0x1800062a0  jmp     short loc_180006271
0x1800062a2  call    cs:__imp_GetProcessHeap
0x1800062a8  mov     edx, 8; dwFlags
0x1800062ad  mov     rcx, rax; hHeap
0x1800062b0  lea     r8d, [rdx-4]; dwBytes
0x1800062b4  call    cs:__imp_HeapAlloc
0x1800062ba  mov     [rdi], rax
0x1800062bd  test    rax, rax
0x1800062c0  jnz     short loc_18000630B
0x1800062c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062c9  lea     rax, WPP_GLOBAL_Control
0x1800062d0  cmp     rcx, rax
0x1800062d3  jz      short loc_1800062DB
0x1800062d5  test    byte ptr [rcx+1Ch], 1
0x1800062d9  jnz     short loc_1800062E5
0x1800062db  mov     ebx, 80070008h
0x1800062e0  jmp     loc_18000616A
0x1800062e5  mov     rcx, [rcx+10h]
0x1800062e9  lea     rax, aFwalloc_0; "FwAlloc"
0x1800062f0  mov     dword ptr [rsp+290h+var_268], 8
0x1800062f8  lea     r9, aFwioreadportus_0; "FwIOReadPortUseIndications"
0x1800062ff  mov     [rsp+290h+var_270], rax
0x180006304  call    WPP_SF_ssL
0x180006309  jmp     short loc_1800062DB
0x18000630b  xor     eax, eax
0x18000630d  mov     [rsp+290h+var_24C], eax
0x180006311  jmp     loc_180006224
0x180006316  mov     ebx, 8007000Dh
0x18000631b  mov     edx, ebx
0x18000631d  jmp     loc_18000615E
```
