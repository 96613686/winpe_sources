# LoadUserModePrinterDriver(ushort *,_PRINTER_DEFAULTSW *,void *,UmpdLoadOptions)

- ea: `0x180045d0c`
- end: `0x1800461cb`
- name: `?LoadUserModePrinterDriver@@YA?AVUmpdPtr@@PEAGPEAU_PRINTER_DEFAULTSW@@PEAXW4UmpdLoadOptions@@@Z`
- size: `1215`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025760`
- `0x180042030`

## callees

- `0x180044b38`
- `0x180044b88`
- `0x180044ea0`
- `0x180045108`
- `0x180045c30`
- `0x180045d0c`
- `0x1800461d4`
- `0x1800462a0`
- `0x180046968`
- `0x180046a04`
- `0x18007ba24`
- `0x180095128`
- `0x180095498`
- `0x18009fbe8`
- `0x1800a34f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045f80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045fb3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045f80`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180045fb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046142`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046142`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045dac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045dac`
- `ntdll!RtlFreeHeap` at `0x180045d96`
- `ntdll!RtlFreeHeap` at `0x180045fa0`
- `ntdll!RtlFreeHeap` at `0x180046101`
- `ntdll!RtlFreeHeap` at `0x180046160`
- `ntdll!RtlFreeHeap` at `0x180046179`
- `ntdll!RtlFreeHeap` at `0x1800461a9`
- `ntdll!RtlFreeHeap` at `0x180045d96`
- `ntdll!RtlFreeHeap` at `0x180045fa0`
- `ntdll!RtlFreeHeap` at `0x180046101`
- `ntdll!RtlFreeHeap` at `0x180046160`
- `ntdll!RtlFreeHeap` at `0x180046179`
- `ntdll!RtlFreeHeap` at `0x1800461a9`
- `ntdll!RtlAllocateHeap` at `0x180045ea3`
- `ntdll!RtlAllocateHeap` at `0x180045ea3`
- `ntdll!RtlEnterCriticalSection` at `0x180045e0e`
- `ntdll!RtlEnterCriticalSection` at `0x180045e0e`
- `ntdll!RtlLeaveCriticalSection` at `0x180045e63`
- `ntdll!RtlLeaveCriticalSection` at `0x180045f2b`
- `ntdll!RtlLeaveCriticalSection` at `0x180045e63`
- `ntdll!RtlLeaveCriticalSection` at `0x180045f2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
UmpdPtr *__fastcall LoadUserModePrinterDriver(
        UmpdPtr *a1,
        unsigned __int16 *a2,
        struct _PRINTER_DEFAULTSW *a3,
        void *a4,
        char a5)
{
  struct _DRIVER_INFO_5W *PrinterDriver; // rax
  struct _DRIVER_INFO_5W *v10; // rsi
  struct _DRIVER_INFO_5W *v11; // r15
  ULONG v12; // edx
  __int64 v13; // rbx
  __int64 v14; // r8
  _QWORD *Heap; // r12
  HMODULE Library; // r13
  unsigned __int64 Driver; // r14
  __int64 v18; // rbx
  const wchar_t **v19; // rbx
  const wchar_t **v20; // rax
  const wchar_t **v21; // rbx
  const wchar_t *v22; // rcx
  int v23; // r8d
  __int64 v24; // r8
  ULONG v25; // edx
  __int64 v27; // [rsp+38h] [rbp-38h] BYREF
  __int64 v28; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t **v29; // [rsp+48h] [rbp-28h]
  struct _DRIVER_INFO_5W *v30; // [rsp+50h] [rbp-20h]
  struct _DRIVER_INFO_5W *v31; // [rsp+58h] [rbp-18h]
  struct _RTL_CRITICAL_SECTION *v32; // [rsp+60h] [rbp-10h]
  _QWORD *v33; // [rsp+68h] [rbp-8h]

  PrinterDriver = (struct _DRIVER_INFO_5W *)MyGetPrinterDriver(a4, 5u);
  v10 = PrinterDriver;
  v31 = PrinterDriver;
  if ( !PrinterDriver || (PrinterDriver->dwDriverAttributes & 1) != 0 )
  {
    *(_QWORD *)a1 = 0;
    UmpdPtr::reset(a1, 0);
    if ( v10 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, v25, v10);
    return a1;
  }
  v11 = DuplicateDriverInfo5W(PrinterDriver);
  v30 = v11;
  if ( !v11 )
  {
    *(_QWORD *)a1 = 0;
    UmpdPtr::reset(a1, 0);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, v12, v10);
    return a1;
  }
  EnterCriticalSection(&semUMPD);
  v32 = &semUMPD;
  FindUserModePrinterDriver(&v27, v10->pDriverPath, v10->dwDriverVersion, 1);
  if ( v27 )
  {
    if ( *(_DWORD *)v27 != -19088744 )
      goto LABEL_44;
    if ( (unsigned int)GdiIsUMPDSandboxingEnabled() )
    {
      UmpdPtr::assert((UmpdPtr *)&v27);
      v13 = *(_QWORD *)(v27 + 64);
      v28 = v13;
      if ( !v13
        || (RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 16)),
            PROXYPORT::LoadDriver((PROXYPORT *)&v28, a2, a3, a4, 0),
            UmpdPtr::assert((UmpdPtr *)&v27),
            *(_QWORD *)(v27 + 72) != v14) )
      {
        UmpdPtr::reset((UmpdPtr *)&v27, 0);
      }
      if ( v13 )
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v13 + 16));
    }
    else if ( (a5 & 1) != 0 )
    {
      UmpdPtr::assert((UmpdPtr *)&v27);
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 44));
    }
    goto LABEL_42;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x398u);
  v33 = Heap;
  if ( Heap )
  {
    Library = 0;
    if ( (unsigned int)GdiIsUMPDSandboxingEnabled() )
    {
      Driver = 0;
      PROXYPORT::PROXYPORT((PROXYPORT *)&v28);
      v18 = v28;
      v29 = (const wchar_t **)v28;
      if ( v28 )
      {
        if ( (a5 & 2) != 0 && (*(_BYTE *)(v28 + 108) & 4) != 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        Driver = PROXYPORT::LoadDriver((PROXYPORT *)&v28, a2, a3, a4, 1);
        if ( !Driver )
        {
          PROXYPORT::Close((PROXYPORT *)&v28);
          v18 = v28;
        }
      }
      if ( v18 )
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v18 + 16));
      v19 = v29;
    }
    else
    {
      if ( (unsigned int)IsAppContainer() )
      {
        v20 = (const wchar_t **)MyGetPrinterDriver(a4, 8u);
        v21 = v20;
        v29 = v20;
        if ( v20 )
        {
          v22 = v20[15];
          if ( v22 )
          {
            if ( !wcscmp_0(v22, L"{084f01fa-e634-4d77-83ee-074817c03581}") )
              Library = LoadLibraryExW(v11->pDriverPath, 0, 8u);
          }
        }
        if ( v21 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
      }
      else
      {
        Library = LoadLibraryExW(v11->pDriverPath, 0, 8u);
      }
      if ( !Library )
        goto LABEL_40;
      v19 = 0;
      Driver = ++g_ulLastUmpdCookie;
    }
    if ( Driver || Library )
    {
      memset_0(Heap, 0, 0x398u);
      *(_DWORD *)Heap = -19088744;
      Heap[7] = Heap + 6;
      Heap[6] = Heap + 6;
      v28 = 0;
      UmpdPtr::reset((UmpdPtr *)&v28, (struct _UMPD *)Heap);
      UmpdPtr::operator=((UmpdPtr *)&v27);
      UmpdPtr::reset((UmpdPtr *)&v28, 0);
      Heap = 0;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_QWORD *)(v27 + 24) = Library;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_QWORD *)(v27 + 16) = v11;
      v11 = 0;
      v30 = 0;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_DWORD *)(v27 + 40) = v23;
      UmpdPtr::assert((UmpdPtr *)&v27);
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 44));
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_DWORD *)(v27 + 36) = 1;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_QWORD *)(v27 + 64) = v19;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_QWORD *)(v27 + 72) = Driver;
      UmpdPtr::assert((UmpdPtr *)&v27);
      *(_QWORD *)(v27 + 8) = v24;
      UmpdPtr::assert((UmpdPtr *)&v27);
      qword_1800FBB00 = (struct _UMPD *)v27;
    }
  }
LABEL_40:
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_42:
  if ( v27 && *(_DWORD *)v27 != -19088744 )
LABEL_44:
    __fastfail(7u);
  *(_QWORD *)a1 = v27;
  UmpdPtr::assert(a1);
  v27 = 0;
  LeaveCriticalSection(&semUMPD);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return a1;
}

```

## disassembly

```asm
0x180045d0c  mov     rax, rsp
0x180045d0f  mov     [rax+8], rbx
0x180045d13  mov     [rax+20h], r9
0x180045d17  mov     [rax+18h], r8
0x180045d1b  mov     [rax+10h], rdx
0x180045d1f  push    rbp
0x180045d20  push    rsi
0x180045d21  push    rdi
0x180045d22  push    r12
0x180045d24  push    r13
0x180045d26  push    r14
0x180045d28  push    r15
0x180045d2a  mov     rbp, rsp
0x180045d2d  sub     rsp, 70h
0x180045d31  mov     r14, r9
0x180045d34  mov     r12, r8
0x180045d37  mov     r13, rdx
0x180045d3a  mov     rdi, rcx
0x180045d3d  mov     edx, 5; unsigned int
0x180045d42  mov     rcx, r9; void *
0x180045d45  call    ?MyGetPrinterDriver@@YAPEAXPEAXK@Z; MyGetPrinterDriver(void *,ulong)
0x180045d4a  mov     rsi, rax
0x180045d4d  mov     [rbp+var_18], rax
0x180045d51  test    rax, rax
0x180045d54  jz      loc_180046182
0x180045d5a  test    byte ptr [rax+30h], 1
0x180045d5e  jnz     loc_180046182
0x180045d64  mov     rcx, rax; struct _DRIVER_INFO_5W *
0x180045d67  call    ?DuplicateDriverInfo5W@@YAPEAU_DRIVER_INFO_5W@@PEAU1@@Z; DuplicateDriverInfo5W(_DRIVER_INFO_5W *)
0x180045d6c  mov     r15, rax
0x180045d6f  mov     [rbp+var_20], rax
0x180045d73  test    rax, rax
0x180045d76  jnz     short loc_180045DA2
0x180045d78  mov     [rdi], rax
0x180045d7b  xor     edx, edx; struct _UMPD *
0x180045d7d  mov     rcx, rdi; this
0x180045d80  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180045d85  nop
0x180045d86  mov     rcx, gs:60h
0x180045d8f  mov     r8, rsi; P
0x180045d92  mov     rcx, [rcx+30h]; HeapHandle
0x180045d96  call    cs:__imp_RtlFreeHeap
0x180045d9c  nop
0x180045d9d  jmp     loc_1800461B0
0x180045da2  lea     rbx, semUMPD
0x180045da9  mov     rcx, rbx; lpCriticalSection
0x180045dac  call    cs:__imp_EnterCriticalSection
0x180045db2  mov     [rbp+var_10], rbx
0x180045db6  mov     r9d, 1
0x180045dbc  mov     r8d, [rsi+38h]
0x180045dc0  mov     rdx, [rsi+18h]
0x180045dc4  lea     rcx, [rbp+var_38]
0x180045dc8  call    ?FindUserModePrinterDriver@@YA?AVUmpdPtr@@PEBGKH@Z; FindUserModePrinterDriver(ushort const *,ulong,int)
0x180045dcd  nop
0x180045dce  mov     rax, [rbp+var_38]
0x180045dd2  test    rax, rax
0x180045dd5  jz      loc_180045E8E
0x180045ddb  cmp     dword ptr [rax], 0FEDCBA98h
0x180045de1  jnz     loc_180046120
0x180045de7  call    GdiIsUMPDSandboxingEnabled
0x180045dec  test    eax, eax
0x180045dee  jz      short loc_180045E6E
0x180045df0  lea     rcx, [rbp+var_38]; this
0x180045df4  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180045df9  mov     rdx, [rbp+var_38]
0x180045dfd  mov     rbx, [rdx+40h]
0x180045e01  mov     [rbp+var_30], rbx
0x180045e05  test    rbx, rbx
0x180045e08  jz      short loc_180045E15
0x180045e0a  lea     rcx, [rbx+10h]; CriticalSection
0x180045e0e  call    cs:__imp_RtlEnterCriticalSection
0x180045e14  nop
0x180045e15  test    rbx, rbx
0x180045e18  jz      short loc_180045E4A
0x180045e1a  mov     [rsp+70h+var_50], 0; int
0x180045e22  mov     r9, r14; void *
0x180045e25  mov     r8, r12; struct _PRINTER_DEFAULTSW *
0x180045e28  mov     rdx, r13; unsigned __int16 *
0x180045e2b  lea     rcx, [rbp+var_30]; this
0x180045e2f  call    ?LoadDriver@PROXYPORT@@QEAA_KPEAGPEAU_PRINTER_DEFAULTSW@@PEAXH@Z; PROXYPORT::LoadDriver(ushort *,_PRINTER_DEFAULTSW *,void *,int)
0x180045e34  mov     r8, rax
0x180045e37  lea     rcx, [rbp+var_38]; this
0x180045e3b  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180045e40  mov     rdx, [rbp+var_38]
0x180045e44  cmp     [rdx+48h], r8
0x180045e48  jz      short loc_180045E56
0x180045e4a  xor     edx, edx; struct _UMPD *
0x180045e4c  lea     rcx, [rbp+var_38]; this
0x180045e50  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180045e55  nop
0x180045e56  test    rbx, rbx
0x180045e59  jz      loc_180046108
0x180045e5f  lea     rcx, [rbx+10h]; CriticalSection
0x180045e63  call    cs:__imp_RtlLeaveCriticalSection
0x180045e69  jmp     loc_180046108
0x180045e6e  test    [rbp+arg_20], 1
0x180045e72  jz      loc_18004610F
0x180045e78  lea     rcx, [rbp+var_38]; this
0x180045e7c  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180045e81  mov     rdx, [rbp+var_38]
0x180045e85  lock inc dword ptr [rdx+2Ch]
0x180045e89  jmp     loc_18004610F
0x180045e8e  mov     rcx, gs:60h
0x180045e97  xor     edx, edx; Flags
0x180045e99  mov     r8d, 398h; Size
0x180045e9f  mov     rcx, [rcx+30h]; HeapHandle
0x180045ea3  call    cs:__imp_RtlAllocateHeap
0x180045ea9  mov     r12, rax
0x180045eac  mov     [rbp+var_8], rax
0x180045eb0  test    rax, rax
0x180045eb3  jz      loc_1800460EA
0x180045eb9  xor     r13d, r13d
0x180045ebc  call    GdiIsUMPDSandboxingEnabled
0x180045ec1  test    eax, eax
0x180045ec3  jz      short loc_180045F3B
0x180045ec5  xor     r14d, r14d
0x180045ec8  lea     rcx, [rbp+var_30]; this
0x180045ecc  call    ??0PROXYPORT@@QEAA@_K@Z; PROXYPORT::PROXYPORT(unsigned __int64)
0x180045ed1  nop
0x180045ed2  mov     rbx, [rbp+var_30]
0x180045ed6  mov     [rbp+var_28], rbx
0x180045eda  test    rbx, rbx
0x180045edd  jz      short loc_180045F22
0x180045edf  test    [rbp+arg_20], 2
0x180045ee3  jz      short loc_180045EF0
0x180045ee5  test    byte ptr [rbx+6Ch], 4
0x180045ee9  jz      short loc_180045EF0
0x180045eeb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180045ef0  mov     [rsp+70h+var_50], 1; int
0x180045ef8  mov     r9, [rbp+arg_18]; void *
0x180045efc  mov     r8, [rbp+arg_10]; struct _PRINTER_DEFAULTSW *
0x180045f00  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180045f04  lea     rcx, [rbp+var_30]; this
0x180045f08  call    ?LoadDriver@PROXYPORT@@QEAA_KPEAGPEAU_PRINTER_DEFAULTSW@@PEAXH@Z; PROXYPORT::LoadDriver(ushort *,_PRINTER_DEFAULTSW *,void *,int)
0x180045f0d  mov     r14, rax
0x180045f10  test    rax, rax
0x180045f13  jnz     short loc_180045F22
0x180045f15  lea     rcx, [rbp+var_30]; this
0x180045f19  call    ?Close@PROXYPORT@@QEAAXXZ; PROXYPORT::Close(void)
0x180045f1e  mov     rbx, [rbp+var_30]
0x180045f22  test    rbx, rbx
0x180045f25  jz      short loc_180045F32
0x180045f27  lea     rcx, [rbx+10h]; CriticalSection
0x180045f2b  call    cs:__imp_RtlLeaveCriticalSection
0x180045f31  nop
0x180045f32  mov     rbx, [rbp+var_28]
0x180045f36  jmp     loc_180045FD8
0x180045f3b  call    ?IsAppContainer@@YAHXZ; IsAppContainer(void)
0x180045f40  test    eax, eax
0x180045f42  jz      short loc_180045FA9
0x180045f44  mov     edx, 8; unsigned int
0x180045f49  mov     rcx, r14; void *
0x180045f4c  call    ?MyGetPrinterDriver@@YAPEAXPEAXK@Z; MyGetPrinterDriver(void *,ulong)
0x180045f51  mov     rbx, rax
0x180045f54  mov     [rbp+var_28], rax
0x180045f58  test    rax, rax
0x180045f5b  jz      short loc_180045F89
0x180045f5d  mov     rcx, [rax+78h]; String1
0x180045f61  test    rcx, rcx
0x180045f64  jz      short loc_180045F89
0x180045f66  lea     rdx, a084f01faE6344d; "{084f01fa-e634-4d77-83ee-074817c03581}"
0x180045f6d  call    wcscmp_0
0x180045f72  test    eax, eax
0x180045f74  jnz     short loc_180045F89
0x180045f76  xor     edx, edx; hFile
0x180045f78  lea     r8d, [rax+8]; dwFlags
0x180045f7c  mov     rcx, [r15+18h]; lpLibFileName
0x180045f80  call    cs:__imp_LoadLibraryExW
0x180045f86  mov     r13, rax
0x180045f89  test    rbx, rbx
0x180045f8c  jz      short loc_180045FA7
0x180045f8e  mov     rcx, gs:60h
0x180045f97  mov     r8, rbx; P
0x180045f9a  xor     edx, edx; Flags
0x180045f9c  mov     rcx, [rcx+30h]; HeapHandle
0x180045fa0  call    cs:__imp_RtlFreeHeap
0x180045fa6  nop
0x180045fa7  jmp     short loc_180045FBC
0x180045fa9  xor     edx, edx; hFile
0x180045fab  lea     r8d, [rdx+8]; dwFlags
0x180045faf  mov     rcx, [r15+18h]; lpLibFileName
0x180045fb3  call    cs:__imp_LoadLibraryExW
0x180045fb9  mov     r13, rax
0x180045fbc  test    r13, r13
0x180045fbf  jz      loc_1800460EA
0x180045fc5  xor     ebx, ebx
0x180045fc7  mov     r14, cs:?g_ulLastUmpdCookie@@3_KA; unsigned __int64 g_ulLastUmpdCookie
0x180045fce  inc     r14
0x180045fd1  mov     cs:?g_ulLastUmpdCookie@@3_KA, r14; unsigned __int64 g_ulLastUmpdCookie
0x180045fd8  test    r14, r14
0x180045fdb  jnz     short loc_180045FE6
0x180045fdd  test    r13, r13
0x180045fe0  jz      loc_1800460EA
0x180045fe6  xor     edx, edx; Val
0x180045fe8  mov     r8d, 398h; Size
0x180045fee  mov     rcx, r12; void *
0x180045ff1  call    memset_0
0x180045ff6  mov     dword ptr [r12], 0FEDCBA98h
0x180045ffe  lea     rax, [r12+30h]
0x180046003  mov     [rax+8], rax
0x180046007  mov     [rax], rax
0x18004600a  mov     [rbp+var_30], 0
0x180046012  mov     rdx, r12; struct _UMPD *
0x180046015  lea     rcx, [rbp+var_30]; this
0x180046019  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18004601e  lea     rdx, [rbp+var_30]
0x180046022  lea     rcx, [rbp+var_38]; this
0x180046026  call    ??4UmpdPtr@@QEAAAEAV0@$$QEAV0@@Z; UmpdPtr::operator=(UmpdPtr &&)
0x18004602b  xor     edx, edx; struct _UMPD *
0x18004602d  lea     rcx, [rbp+var_30]; this
0x180046031  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180046036  xor     r12d, r12d
0x180046039  lea     rcx, [rbp+var_38]; this
0x18004603d  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180046042  mov     rdx, [rbp+var_38]
0x180046046  mov     [rdx+18h], r13
0x18004604a  lea     rcx, [rbp+var_38]; this
0x18004604e  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180046053  mov     rdx, [rbp+var_38]
0x180046057  mov     [rdx+10h], r15
0x18004605b  xor     r15d, r15d
0x18004605e  mov     [rbp+var_20], r15
0x180046062  mov     r8d, [rsi+38h]
0x180046066  lea     rcx, [rbp+var_38]; this
0x18004606a  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18004606f  mov     rdx, [rbp+var_38]
0x180046073  mov     [rdx+28h], r8d
0x180046077  lea     rcx, [rbp+var_38]; this
0x18004607b  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180046080  mov     rdx, [rbp+var_38]
0x180046084  lock inc dword ptr [rdx+2Ch]
0x180046088  lea     rcx, [rbp+var_38]; this
0x18004608c  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180046091  mov     rdx, [rbp+var_38]
0x180046095  mov     dword ptr [rdx+24h], 1
0x18004609c  lea     rcx, [rbp+var_38]; this
0x1800460a0  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800460a5  mov     rdx, [rbp+var_38]
0x1800460a9  mov     [rdx+40h], rbx
0x1800460ad  lea     rcx, [rbp+var_38]; this
0x1800460b1  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800460b6  mov     rdx, [rbp+var_38]
0x1800460ba  mov     [rdx+48h], r14
0x1800460be  mov     r8, cs:qword_1800FBB00
0x1800460c5  lea     rcx, [rbp+var_38]; this
0x1800460c9  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800460ce  mov     rdx, [rbp+var_38]
0x1800460d2  mov     [rdx+8], r8
0x1800460d6  lea     rcx, [rbp+var_38]; this
0x1800460da  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800460df  mov     rdx, [rbp+var_38]
0x1800460e3  mov     cs:qword_1800FBB00, rdx
0x1800460ea  test    r12, r12
0x1800460ed  jz      short loc_180046108
0x1800460ef  mov     rcx, gs:60h
0x1800460f8  mov     r8, r12; P
0x1800460fb  xor     edx, edx; Flags
0x1800460fd  mov     rcx, [rcx+30h]; HeapHandle
0x180046101  call    cs:__imp_RtlFreeHeap
0x180046107  nop
0x180046108  lea     rbx, semUMPD
0x18004610f  mov     rax, [rbp+var_38]
0x180046113  test    rax, rax
0x180046116  jz      short loc_180046127
0x180046118  cmp     dword ptr [rax], 0FEDCBA98h
0x18004611e  jz      short loc_180046127
0x180046120  mov     ecx, 7
0x180046125  int     29h; Win8: RtlFailFast(ecx)
0x180046127  mov     rax, [rbp+var_38]
0x18004612b  mov     [rdi], rax
0x18004612e  mov     rcx, rdi; this
0x180046131  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180046136  nop
0x180046137  mov     [rbp+var_38], 0
0x18004613f  mov     rcx, rbx; lpCriticalSection
0x180046142  call    cs:__imp_LeaveCriticalSection
0x180046148  nop
0x180046149  test    r15, r15
0x18004614c  jz      short loc_180046167
0x18004614e  mov     rcx, gs:60h
0x180046157  mov     r8, r15; P
0x18004615a  xor     edx, edx; Flags
0x18004615c  mov     rcx, [rcx+30h]; HeapHandle
0x180046160  call    cs:__imp_RtlFreeHeap
0x180046166  nop
0x180046167  mov     rcx, gs:60h
0x180046170  mov     r8, rsi; P
0x180046173  xor     edx, edx; Flags
0x180046175  mov     rcx, [rcx+30h]; HeapHandle
0x180046179  call    cs:__imp_RtlFreeHeap
0x18004617f  nop
0x180046180  jmp     short loc_1800461B0
0x180046182  mov     qword ptr [rdi], 0
0x180046189  xor     edx, edx; struct _UMPD *
0x18004618b  mov     rcx, rdi; this
0x18004618e  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180046193  nop
0x180046194  test    rsi, rsi
0x180046197  jz      short loc_1800461B0
0x180046199  mov     rcx, gs:60h
  ... truncated ...
```
