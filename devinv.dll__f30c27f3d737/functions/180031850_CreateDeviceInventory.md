# CreateDeviceInventory

- ea: `0x180031850`
- end: `0x180031cbf`
- name: `CreateDeviceInventory`
- size: `1135`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180027f40`
- `0x18002a500`

## callees

- `0x1800066f0`
- `0x180006d02`
- `0x180007014`
- `0x18002dd44`
- `0x180031850`
- `0x180039b88`
- `0x18003d8c0`
- `0x18006041c`
- `0x180066c10`
- `0x18007a4ac`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c88`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180031912`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003196a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800319b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800319dd`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x180031912`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003196a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800319b8`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800319dd`

## string_xrefs

- `0x18003186a`: `Entered CreateDeviceInventory`
- `0x18003187a`: `CreateDeviceInventory`
- `0x180031a23`: `Devinv already running`
- `0x180031b08`: `[0x%08x] CDevInventory::CreateDevInventoryToCache failed`

## pseudocode

```c
__int64 __fastcall CreateDeviceInventory(unsigned int a1, __int64 a2)
{
  _DWORD *v4; // rdi
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  LPWSTR CommandLineW; // rax
  FILE *v9; // rax
  LPWSTR v10; // rbx
  FILE *v11; // rax
  FILE *v12; // rax
  LPWSTR v13; // rax
  LPWSTR v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  int v18; // ebx
  int DevInventoryToCache; // eax
  struct TelCacheProvider *v20; // rcx
  FILE *v21; // rax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  __int64 v28; // [rsp+20h] [rbp-48h]
  __int64 v29; // [rsp+30h] [rbp-38h]
  HANDLE hObject; // [rsp+80h] [rbp+18h] BYREF

  hObject = 0;
  v4 = 0;
  AslLogCallPrintf(3, "CreateDeviceInventory", 348, "Entered CreateDeviceInventory");
  if ( EnableDevInvStdErrLog )
  {
    v5 = o___acrt_iob_func_0(2u);
    fprintf(v5, "Info: %s, %u: ", "CreateDeviceInventory", 348);
    v6 = o___acrt_iob_func_0(2u);
    fprintf(v6, "Entered CreateDeviceInventory");
    v7 = o___acrt_iob_func_0(2u);
    fprintf(v7, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x4000000, "Entered CreateDeviceInventory");
  if ( (a1 & 0x21FEFFD) != 0 )
  {
    CommandLineW = GetCommandLineW();
    AslLogCallPrintf(
      2,
      "CreateDeviceInventory",
      355,
      "DEVINV legacy flags being used. Flags: %X, Cmd: %ws, [%#x]",
      a1,
      CommandLineW,
      -2147024809);
    if ( EnableDevInvStdErrLog )
    {
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "Error: %s, %u: ", "CreateDeviceInventory", 355);
      v10 = GetCommandLineW();
      v11 = o___acrt_iob_func_0(2u);
      LODWORD(v28) = -2147024809;
      fprintf(v11, "DEVINV legacy flags being used. Flags: %X, Cmd: %ws, [%#x]", a1, v10, v28);
      v12 = o___acrt_iob_func_0(2u);
      fprintf(v12, "\n");
    }
    if ( g_DeviceMapLogFunction )
    {
      v13 = GetCommandLineW();
      LODWORD(v28) = -2147024809;
      TraceMessageCallback(0x2000000, "DEVINV legacy flags being used. Flags: %X, Cmd: %ws, [%#x]", a1, v13, v28);
    }
    v14 = GetCommandLineW();
    LODWORD(v29) = -2147024809;
    LODWORD(v28) = a1;
    AslLogCallPrintf(
      1,
      "CreateDeviceInventory",
      355,
      "DEVINV legacy flags being used. Flags: %X, Cmd: %ws, [%#x]",
      v28,
      v14,
      v29);
  }
  if ( IsDevInvAlreadyRunning(&hObject) )
  {
    AslLogCallPrintf(3, "CreateDeviceInventory", 360, "Devinv already running");
    if ( EnableDevInvStdErrLog )
    {
      v15 = o___acrt_iob_func_0(2u);
      fprintf(v15, "Info: %s, %u: ", "CreateDeviceInventory", 360);
      v16 = o___acrt_iob_func_0(2u);
      fprintf(v16, "Devinv already running");
      v17 = o___acrt_iob_func_0(2u);
      fprintf(v17, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x4000000, "Devinv already running");
  }
  v18 = DeviceMapInitializeTelemetryAndCache(0);
  if ( v18 >= 0 )
  {
    EnableDevInvStdErrLog = (a1 >> 21) & 1;
    v4 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
      v4[3] = a1;
      *(_QWORD *)v4 = &CDevInventory::`vftable';
      *((_QWORD *)v4 + 2) = a2;
      DevInventoryToCache = CDevInventory::CreateDevInventoryToCache((CDevInventory *)v4);
      v18 = DevInventoryToCache;
      if ( DevInventoryToCache >= 0 )
      {
        if ( a1 == 0x1000000 && qword_180157118 )
          SetLastInventoryScanTime(v20);
        v18 = 0;
      }
      else
      {
        AslLogCallPrintf(
          2,
          "CreateDeviceInventory",
          386,
          "[0x%08x] CDevInventory::CreateDevInventoryToCache failed",
          DevInventoryToCache);
        if ( EnableDevInvStdErrLog )
        {
          v21 = o___acrt_iob_func_0(2u);
          fprintf(v21, "Error: %s, %u: ", "CreateDeviceInventory", 386);
          v22 = o___acrt_iob_func_0(2u);
          fprintf(v22, "[0x%08x] CDevInventory::CreateDevInventoryToCache failed", v18);
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "[0x%08x] CDevInventory::CreateDevInventoryToCache failed", v18);
        AslLogCallPrintf(
          1,
          "CreateDeviceInventory",
          386,
          "[0x%08x] CDevInventory::CreateDevInventoryToCache failed",
          v18);
      }
    }
    else
    {
      v18 = -2147024882;
      AslLogCallPrintf(2, "CreateDeviceInventory", 375, "System Out of memory [%#x]", -2147024882);
      if ( EnableDevInvStdErrLog )
      {
        v24 = o___acrt_iob_func_0(2u);
        fprintf(v24, "Error: %s, %u: ", "CreateDeviceInventory", 375);
        v25 = o___acrt_iob_func_0(2u);
        fprintf(v25, "System Out of memory [%#x]", -2147024882);
        v26 = o___acrt_iob_func_0(2u);
        fprintf(v26, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "System Out of memory [%#x]", 2147942414LL);
      AslLogCallPrintf(1, "CreateDeviceInventory", 375, "System Out of memory [%#x]", -2147024882);
      v4 = 0;
    }
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( v4 )
    (**(void (__fastcall ***)(void *, __int64))v4)(v4, 1);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180031850  mov     rax, rsp
0x180031853  mov     [rax+8], rbx
0x180031857  mov     [rax+10h], rbp
0x18003185b  push    rsi
0x18003185c  push    rdi
0x18003185d  push    r12
0x18003185f  push    r14
0x180031861  push    r15
0x180031863  sub     rsp, 40h
0x180031867  xor     r14d, r14d
0x18003186a  lea     rbx, aEnteredCreated_0; "Entered CreateDeviceInventory"
0x180031871  mov     rbp, rdx
0x180031874  mov     [rax+18h], r14
0x180031878  mov     esi, ecx
0x18003187a  lea     r15, aCreatedevicein_2; "CreateDeviceInventory"
0x180031881  mov     r9, rbx
0x180031884  mov     r8d, 15Ch
0x18003188a  lea     ecx, [r14+3]
0x18003188e  mov     rdx, r15
0x180031891  mov     edi, r14d
0x180031894  call    AslLogCallPrintf
0x180031899  cmp     cs:EnableDevInvStdErrLog, r14d
0x1800318a0  lea     r12d, [r14+2]
0x1800318a4  jz      short loc_1800318F0
0x1800318a6  mov     ecx, r12d; Ix
0x1800318a9  call    _o___acrt_iob_func_0
0x1800318ae  mov     rcx, rax; Stream
0x1800318b1  lea     rdx, aInfoSU; "Info: %s, %u: "
0x1800318b8  mov     r9d, 15Ch
0x1800318be  mov     r8, r15
0x1800318c1  call    fprintf
0x1800318c6  mov     ecx, r12d; Ix
0x1800318c9  call    _o___acrt_iob_func_0
0x1800318ce  mov     rcx, rax; Stream
0x1800318d1  mov     rdx, rbx; Format
0x1800318d4  call    fprintf
0x1800318d9  mov     ecx, r12d; Ix
0x1800318dc  call    _o___acrt_iob_func_0
0x1800318e1  mov     rcx, rax; Stream
0x1800318e4  lea     rdx, asc_18011EAD8; "\n"
0x1800318eb  call    fprintf
0x1800318f0  cmp     cs:g_DeviceMapLogFunction, r14
0x1800318f7  jz      short loc_180031906
0x1800318f9  mov     rdx, rbx
0x1800318fc  mov     ecx, 4000000h
0x180031901  call    TraceMessageCallback
0x180031906  test    esi, 21FEFFDh
0x18003190c  jz      loc_180031A0E
0x180031912  call    cs:__imp_GetCommandLineW
0x180031918  mov     dword ptr [rsp+68h+var_38], 80070057h
0x180031920  lea     r9, aDevinvLegacyFl; "DEVINV legacy flags being used. Flags: "...
0x180031927  mov     [rsp+68h+var_40], rax
0x18003192c  mov     r8d, 163h
0x180031932  mov     rdx, r15
0x180031935  mov     dword ptr [rsp+68h+var_48], esi
0x180031939  mov     ecx, r12d
0x18003193c  call    AslLogCallPrintf
0x180031941  cmp     cs:EnableDevInvStdErrLog, r14d
0x180031948  jz      short loc_1800319AF
0x18003194a  mov     ecx, r12d; Ix
0x18003194d  call    _o___acrt_iob_func_0
0x180031952  mov     rcx, rax; Stream
0x180031955  lea     rdx, Format; "Error: %s, %u: "
0x18003195c  mov     r9d, 163h
0x180031962  mov     r8, r15
0x180031965  call    fprintf
0x18003196a  call    cs:__imp_GetCommandLineW
0x180031970  mov     ecx, r12d; Ix
0x180031973  mov     rbx, rax
0x180031976  call    _o___acrt_iob_func_0
0x18003197b  mov     r9, rbx
0x18003197e  mov     dword ptr [rsp+68h+var_48], 80070057h
0x180031986  mov     r8d, esi
0x180031989  lea     rdx, aDevinvLegacyFl; "DEVINV legacy flags being used. Flags: "...
0x180031990  mov     rcx, rax; Stream
0x180031993  call    fprintf
0x180031998  mov     ecx, r12d; Ix
0x18003199b  call    _o___acrt_iob_func_0
0x1800319a0  mov     rcx, rax; Stream
0x1800319a3  lea     rdx, asc_18011EAD8; "\n"
0x1800319aa  call    fprintf
0x1800319af  cmp     cs:g_DeviceMapLogFunction, r14
0x1800319b6  jz      short loc_1800319DD
0x1800319b8  call    cs:__imp_GetCommandLineW
0x1800319be  mov     r8d, esi
0x1800319c1  mov     dword ptr [rsp+68h+var_48], 80070057h
0x1800319c9  mov     r9, rax
0x1800319cc  lea     rdx, aDevinvLegacyFl; "DEVINV legacy flags being used. Flags: "...
0x1800319d3  mov     ecx, 2000000h
0x1800319d8  call    TraceMessageCallback
0x1800319dd  call    cs:__imp_GetCommandLineW
0x1800319e3  mov     dword ptr [rsp+68h+var_38], 80070057h
0x1800319eb  lea     r9, aDevinvLegacyFl; "DEVINV legacy flags being used. Flags: "...
0x1800319f2  mov     [rsp+68h+var_40], rax
0x1800319f7  mov     r8d, 163h
0x1800319fd  mov     rdx, r15
0x180031a00  mov     dword ptr [rsp+68h+var_48], esi
0x180031a04  mov     ecx, 1
0x180031a09  call    AslLogCallPrintf
0x180031a0e  lea     rcx, [rsp+68h+hObject]; void **
0x180031a16  call    ?IsDevInvAlreadyRunning@@YA_NAEAPEAX@Z; IsDevInvAlreadyRunning(void * &)
0x180031a1b  test    al, al
0x180031a1d  jz      loc_180031AA9
0x180031a23  lea     rbx, aDevinvAlreadyR; "Devinv already running"
0x180031a2a  mov     r8d, 168h
0x180031a30  mov     r9, rbx
0x180031a33  mov     rdx, r15
0x180031a36  mov     ecx, 3
0x180031a3b  call    AslLogCallPrintf
0x180031a40  cmp     cs:EnableDevInvStdErrLog, r14d
0x180031a47  jz      short loc_180031A93
0x180031a49  mov     ecx, r12d; Ix
0x180031a4c  call    _o___acrt_iob_func_0
0x180031a51  mov     rcx, rax; Stream
0x180031a54  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180031a5b  mov     r9d, 168h
0x180031a61  mov     r8, r15
0x180031a64  call    fprintf
0x180031a69  mov     ecx, r12d; Ix
0x180031a6c  call    _o___acrt_iob_func_0
0x180031a71  mov     rcx, rax; Stream
0x180031a74  mov     rdx, rbx; Format
0x180031a77  call    fprintf
0x180031a7c  mov     ecx, r12d; Ix
0x180031a7f  call    _o___acrt_iob_func_0
0x180031a84  mov     rcx, rax; Stream
0x180031a87  lea     rdx, asc_18011EAD8; "\n"
0x180031a8e  call    fprintf
0x180031a93  cmp     cs:g_DeviceMapLogFunction, r14
0x180031a9a  jz      short loc_180031AA9
0x180031a9c  mov     rdx, rbx
0x180031a9f  mov     ecx, 4000000h
0x180031aa4  call    TraceMessageCallback
0x180031aa9  xor     ecx, ecx
0x180031aab  call    DeviceMapInitializeTelemetryAndCache
0x180031ab0  mov     ebx, eax
0x180031ab2  test    eax, eax
0x180031ab4  js      loc_180031C7B
0x180031aba  mov     eax, esi
0x180031abc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180031ac3  shr     eax, 15h
0x180031ac6  mov     ecx, 18h; unsigned __int64
0x180031acb  and     eax, 1
0x180031ace  mov     cs:EnableDevInvStdErrLog, eax
0x180031ad4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031ad9  mov     rdi, rax
0x180031adc  test    rax, rax
0x180031adf  jz      loc_180031BCF
0x180031ae5  lea     rax, ??_7CDevInventory@@6B@; const CDevInventory::`vftable'
0x180031aec  mov     [rdi+0Ch], esi
0x180031aef  mov     rcx, rdi; this
0x180031af2  mov     [rdi], rax
0x180031af5  mov     [rdi+10h], rbp
0x180031af9  call    ?CreateDevInventoryToCache@CDevInventory@@QEAAJXZ; CDevInventory::CreateDevInventoryToCache(void)
0x180031afe  mov     ebx, eax
0x180031b00  test    eax, eax
0x180031b02  jns     loc_180031BB1
0x180031b08  lea     rsi, a0x08xCdevinven; "[0x%08x] CDevInventory::CreateDevInvent"...
0x180031b0f  mov     dword ptr [rsp+68h+var_48], eax
0x180031b13  mov     ebp, 182h
0x180031b18  mov     r9, rsi
0x180031b1b  mov     r8d, ebp
0x180031b1e  mov     rdx, r15
0x180031b21  mov     ecx, r12d
0x180031b24  call    AslLogCallPrintf
0x180031b29  cmp     cs:EnableDevInvStdErrLog, r14d
0x180031b30  jz      short loc_180031B7C
0x180031b32  mov     ecx, r12d; Ix
0x180031b35  call    _o___acrt_iob_func_0
0x180031b3a  mov     rcx, rax; Stream
0x180031b3d  lea     rdx, Format; "Error: %s, %u: "
0x180031b44  mov     r9d, ebp
0x180031b47  mov     r8, r15
0x180031b4a  call    fprintf
0x180031b4f  mov     ecx, r12d; Ix
0x180031b52  call    _o___acrt_iob_func_0
0x180031b57  mov     rcx, rax; Stream
0x180031b5a  mov     r8d, ebx
0x180031b5d  mov     rdx, rsi; Format
0x180031b60  call    fprintf
0x180031b65  mov     ecx, r12d; Ix
0x180031b68  call    _o___acrt_iob_func_0
0x180031b6d  mov     rcx, rax; Stream
0x180031b70  lea     rdx, asc_18011EAD8; "\n"
0x180031b77  call    fprintf
0x180031b7c  cmp     cs:g_DeviceMapLogFunction, r14
0x180031b83  jz      short loc_180031B95
0x180031b85  mov     r8d, ebx
0x180031b88  mov     rdx, rsi
0x180031b8b  mov     ecx, 2000000h
0x180031b90  call    TraceMessageCallback
0x180031b95  mov     r9, rsi
0x180031b98  mov     dword ptr [rsp+68h+var_48], ebx
0x180031b9c  mov     r8, rbp
0x180031b9f  mov     rdx, r15
0x180031ba2  mov     ecx, 1
0x180031ba7  call    AslLogCallPrintf
0x180031bac  jmp     loc_180031C7B
0x180031bb1  cmp     esi, 1000000h
0x180031bb7  jnz     short loc_180031BC7
0x180031bb9  cmp     cs:qword_180157118, r14
0x180031bc0  jz      short loc_180031BC7
0x180031bc2  call    ?SetLastInventoryScanTime@@YAXAEAVTelCacheProvider@@@Z; SetLastInventoryScanTime(TelCacheProvider &)
0x180031bc7  mov     ebx, r14d
0x180031bca  jmp     loc_180031C7B
0x180031bcf  lea     rdi, aSystemOutOfMem; "System Out of memory [%#x]"
0x180031bd6  mov     esi, 177h
0x180031bdb  mov     ebx, 8007000Eh
0x180031be0  mov     r9, rdi
0x180031be3  mov     r8d, esi
0x180031be6  mov     dword ptr [rsp+68h+var_48], ebx
0x180031bea  mov     rdx, r15
0x180031bed  mov     ecx, r12d
0x180031bf0  call    AslLogCallPrintf
0x180031bf5  cmp     cs:EnableDevInvStdErrLog, r14d
0x180031bfc  jz      short loc_180031C48
0x180031bfe  mov     ecx, r12d; Ix
0x180031c01  call    _o___acrt_iob_func_0
0x180031c06  mov     rcx, rax; Stream
0x180031c09  lea     rdx, Format; "Error: %s, %u: "
0x180031c10  mov     r9d, esi
0x180031c13  mov     r8, r15
0x180031c16  call    fprintf
0x180031c1b  mov     ecx, r12d; Ix
0x180031c1e  call    _o___acrt_iob_func_0
0x180031c23  mov     rcx, rax; Stream
0x180031c26  mov     r8d, ebx
0x180031c29  mov     rdx, rdi; Format
0x180031c2c  call    fprintf
0x180031c31  mov     ecx, r12d; Ix
0x180031c34  call    _o___acrt_iob_func_0
0x180031c39  mov     rcx, rax; Stream
0x180031c3c  lea     rdx, asc_18011EAD8; "\n"
0x180031c43  call    fprintf
0x180031c48  cmp     cs:g_DeviceMapLogFunction, r14
0x180031c4f  jz      short loc_180031C61
0x180031c51  mov     r8d, ebx
0x180031c54  mov     rdx, rdi
0x180031c57  mov     ecx, 2000000h
0x180031c5c  call    TraceMessageCallback
0x180031c61  mov     r9, rdi
0x180031c64  mov     dword ptr [rsp+68h+var_48], ebx
0x180031c68  mov     r8, rsi
0x180031c6b  mov     rdx, r15
0x180031c6e  mov     ecx, 1
0x180031c73  call    AslLogCallPrintf
0x180031c78  mov     rdi, r14
0x180031c7b  mov     rcx, [rsp+68h+hObject]; hObject
0x180031c83  test    rcx, rcx
0x180031c86  jz      short loc_180031C8E
0x180031c88  call    cs:__imp_CloseHandle
0x180031c8e  test    rdi, rdi
0x180031c91  jz      short loc_180031CA6
0x180031c93  mov     rax, [rdi]
0x180031c96  mov     edx, 1
0x180031c9b  mov     rcx, rdi
0x180031c9e  mov     rax, [rax]
0x180031ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ca6  mov     rbp, [rsp+68h+arg_8]
0x180031cab  mov     eax, ebx
0x180031cad  mov     rbx, [rsp+68h+arg_0]
0x180031cb2  add     rsp, 40h
0x180031cb6  pop     r15
0x180031cb8  pop     r14
0x180031cba  pop     r12
0x180031cbc  pop     rdi
0x180031cbd  pop     rsi
0x180031cbe  retn
```
