# LoadUserModePrinterDriver(ushort *,_PRINTER_DEFAULTSW *,void *,UmpdLoadOptions)

- ea: `0x18003fb74`
- end: `0x18004008c`
- name: `?LoadUserModePrinterDriver@@YA?AVUmpdPtr@@PEAGPEAU_PRINTER_DEFAULTSW@@PEAXW4UmpdLoadOptions@@@Z`
- size: `1304`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e6f0`
- `0x18003bd20`

## callees

- `0x18003e8e0`
- `0x18003e930`
- `0x18003ec70`
- `0x18003ef14`
- `0x18003fa88`
- `0x18003fb74`
- `0x180040094`
- `0x18004017c`
- `0x180040898`
- `0x180040950`
- `0x180080604`
- `0x18009affc`
- `0x18009b3c8`
- `0x1800a2b64`
- `0x1800a68b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fe10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fe4f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fe10`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fe4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ffea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ffea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fc1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003fc1a`
- `ntdll!RtlFreeHeap` at `0x18003fbfe`
- `ntdll!RtlFreeHeap` at `0x18003fe36`
- `ntdll!RtlFreeHeap` at `0x18003ffa3`
- `ntdll!RtlFreeHeap` at `0x18004000e`
- `ntdll!RtlFreeHeap` at `0x18004002d`
- `ntdll!RtlFreeHeap` at `0x180040063`
- `ntdll!RtlFreeHeap` at `0x18003fbfe`
- `ntdll!RtlFreeHeap` at `0x18003fe36`
- `ntdll!RtlFreeHeap` at `0x18003ffa3`
- `ntdll!RtlFreeHeap` at `0x18004000e`
- `ntdll!RtlFreeHeap` at `0x18004002d`
- `ntdll!RtlFreeHeap` at `0x180040063`
- `ntdll!RtlAllocateHeap` at `0x18003fd27`
- `ntdll!RtlAllocateHeap` at `0x18003fd27`
- `ntdll!RtlEnterCriticalSection` at `0x18003fc86`
- `ntdll!RtlEnterCriticalSection` at `0x18003fc86`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fce1`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fdb5`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fce1`
- `ntdll!RtlLeaveCriticalSection` at `0x18003fdb5`

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
      qword_1800FEBE0 = (struct _UMPD *)v27;
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
0x18003fb74  mov     rax, rsp
0x18003fb77  mov     [rax+8], rbx
0x18003fb7b  mov     [rax+20h], r9
0x18003fb7f  mov     [rax+18h], r8
0x18003fb83  mov     [rax+10h], rdx
0x18003fb87  push    rbp
0x18003fb88  push    rsi
0x18003fb89  push    rdi
0x18003fb8a  push    r12
0x18003fb8c  push    r13
0x18003fb8e  push    r14
0x18003fb90  push    r15
0x18003fb92  mov     rbp, rsp
0x18003fb95  sub     rsp, 70h
0x18003fb99  mov     r14, r9
0x18003fb9c  mov     r12, r8
0x18003fb9f  mov     r13, rdx
0x18003fba2  mov     rdi, rcx
0x18003fba5  mov     edx, 5; unsigned int
0x18003fbaa  mov     rcx, r9; void *
0x18003fbad  call    ?MyGetPrinterDriver@@YAPEAXPEAXK@Z; MyGetPrinterDriver(void *,ulong)
0x18003fbb2  mov     rsi, rax
0x18003fbb5  mov     [rbp+var_18], rax
0x18003fbb9  test    rax, rax
0x18003fbbc  jz      loc_18004003C
0x18003fbc2  test    byte ptr [rax+30h], 1
0x18003fbc6  jnz     loc_18004003C
0x18003fbcc  mov     rcx, rax; struct _DRIVER_INFO_5W *
0x18003fbcf  call    ?DuplicateDriverInfo5W@@YAPEAU_DRIVER_INFO_5W@@PEAU1@@Z; DuplicateDriverInfo5W(_DRIVER_INFO_5W *)
0x18003fbd4  mov     r15, rax
0x18003fbd7  mov     [rbp+var_20], rax
0x18003fbdb  test    rax, rax
0x18003fbde  jnz     short loc_18003FC10
0x18003fbe0  mov     [rdi], rax
0x18003fbe3  xor     edx, edx; struct _UMPD *
0x18003fbe5  mov     rcx, rdi; this
0x18003fbe8  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18003fbed  nop
0x18003fbee  mov     rcx, gs:60h
0x18003fbf7  mov     r8, rsi; P
0x18003fbfa  mov     rcx, [rcx+30h]; HeapHandle
0x18003fbfe  call    cs:__imp_RtlFreeHeap
0x18003fc05  nop     dword ptr [rax+rax+00h]
0x18003fc0a  nop
0x18003fc0b  jmp     loc_180040070
0x18003fc10  lea     rbx, semUMPD
0x18003fc17  mov     rcx, rbx; lpCriticalSection
0x18003fc1a  call    cs:__imp_EnterCriticalSection
0x18003fc21  nop     dword ptr [rax+rax+00h]
0x18003fc26  mov     [rbp+var_10], rbx
0x18003fc2a  mov     r9d, 1
0x18003fc30  mov     r8d, [rsi+38h]
0x18003fc34  mov     rdx, [rsi+18h]
0x18003fc38  lea     rcx, [rbp+var_38]
0x18003fc3c  call    ?FindUserModePrinterDriver@@YA?AVUmpdPtr@@PEBGKH@Z; FindUserModePrinterDriver(ushort const *,ulong,int)
0x18003fc41  nop
0x18003fc42  mov     rax, [rbp+var_38]
0x18003fc46  test    rax, rax
0x18003fc49  jz      loc_18003FD12
0x18003fc4f  cmp     dword ptr [rax], 0FEDCBA98h
0x18003fc55  jnz     loc_18003FFC8
0x18003fc5b  call    GdiIsUMPDSandboxingEnabled
0x18003fc60  test    eax, eax
0x18003fc62  jz      loc_18003FCF2
0x18003fc68  lea     rcx, [rbp+var_38]; this
0x18003fc6c  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003fc71  mov     rdx, [rbp+var_38]
0x18003fc75  mov     rbx, [rdx+40h]
0x18003fc79  mov     [rbp+var_30], rbx
0x18003fc7d  test    rbx, rbx
0x18003fc80  jz      short loc_18003FC93
0x18003fc82  lea     rcx, [rbx+10h]; CriticalSection
0x18003fc86  call    cs:__imp_RtlEnterCriticalSection
0x18003fc8d  nop     dword ptr [rax+rax+00h]
0x18003fc92  nop
0x18003fc93  test    rbx, rbx
0x18003fc96  jz      short loc_18003FCC8
0x18003fc98  mov     [rsp+70h+var_50], 0; int
0x18003fca0  mov     r9, r14; void *
0x18003fca3  mov     r8, r12; struct _PRINTER_DEFAULTSW *
0x18003fca6  mov     rdx, r13; unsigned __int16 *
0x18003fca9  lea     rcx, [rbp+var_30]; this
0x18003fcad  call    ?LoadDriver@PROXYPORT@@QEAA_KPEAGPEAU_PRINTER_DEFAULTSW@@PEAXH@Z; PROXYPORT::LoadDriver(ushort *,_PRINTER_DEFAULTSW *,void *,int)
0x18003fcb2  mov     r8, rax
0x18003fcb5  lea     rcx, [rbp+var_38]; this
0x18003fcb9  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003fcbe  mov     rdx, [rbp+var_38]
0x18003fcc2  cmp     [rdx+48h], r8
0x18003fcc6  jz      short loc_18003FCD4
0x18003fcc8  xor     edx, edx; struct _UMPD *
0x18003fcca  lea     rcx, [rbp+var_38]; this
0x18003fcce  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18003fcd3  nop
0x18003fcd4  test    rbx, rbx
0x18003fcd7  jz      loc_18003FFB0
0x18003fcdd  lea     rcx, [rbx+10h]; CriticalSection
0x18003fce1  call    cs:__imp_RtlLeaveCriticalSection
0x18003fce8  nop     dword ptr [rax+rax+00h]
0x18003fced  jmp     loc_18003FFB0
0x18003fcf2  test    [rbp+arg_20], 1
0x18003fcf6  jz      loc_18003FFB7
0x18003fcfc  lea     rcx, [rbp+var_38]; this
0x18003fd00  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003fd05  mov     rdx, [rbp+var_38]
0x18003fd09  lock inc dword ptr [rdx+2Ch]
0x18003fd0d  jmp     loc_18003FFB7
0x18003fd12  mov     rcx, gs:60h
0x18003fd1b  xor     edx, edx; Flags
0x18003fd1d  mov     r8d, 398h; Size
0x18003fd23  mov     rcx, [rcx+30h]; HeapHandle
0x18003fd27  call    cs:__imp_RtlAllocateHeap
0x18003fd2e  nop     dword ptr [rax+rax+00h]
0x18003fd33  mov     r12, rax
0x18003fd36  mov     [rbp+var_8], rax
0x18003fd3a  test    rax, rax
0x18003fd3d  jz      loc_18003FF8C
0x18003fd43  xor     r13d, r13d
0x18003fd46  call    GdiIsUMPDSandboxingEnabled
0x18003fd4b  test    eax, eax
0x18003fd4d  jz      short loc_18003FDCB
0x18003fd4f  xor     r14d, r14d
0x18003fd52  lea     rcx, [rbp+var_30]; this
0x18003fd56  call    ??0PROXYPORT@@QEAA@_K@Z; PROXYPORT::PROXYPORT(unsigned __int64)
0x18003fd5b  nop
0x18003fd5c  mov     rbx, [rbp+var_30]
0x18003fd60  mov     [rbp+var_28], rbx
0x18003fd64  test    rbx, rbx
0x18003fd67  jz      short loc_18003FDAC
0x18003fd69  test    [rbp+arg_20], 2
0x18003fd6d  jz      short loc_18003FD7A
0x18003fd6f  test    byte ptr [rbx+6Ch], 4
0x18003fd73  jz      short loc_18003FD7A
0x18003fd75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fd7a  mov     [rsp+70h+var_50], 1; int
0x18003fd82  mov     r9, [rbp+arg_18]; void *
0x18003fd86  mov     r8, [rbp+arg_10]; struct _PRINTER_DEFAULTSW *
0x18003fd8a  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18003fd8e  lea     rcx, [rbp+var_30]; this
0x18003fd92  call    ?LoadDriver@PROXYPORT@@QEAA_KPEAGPEAU_PRINTER_DEFAULTSW@@PEAXH@Z; PROXYPORT::LoadDriver(ushort *,_PRINTER_DEFAULTSW *,void *,int)
0x18003fd97  mov     r14, rax
0x18003fd9a  test    rax, rax
0x18003fd9d  jnz     short loc_18003FDAC
0x18003fd9f  lea     rcx, [rbp+var_30]; this
0x18003fda3  call    ?Close@PROXYPORT@@QEAAXXZ; PROXYPORT::Close(void)
0x18003fda8  mov     rbx, [rbp+var_30]
0x18003fdac  test    rbx, rbx
0x18003fdaf  jz      short loc_18003FDC2
0x18003fdb1  lea     rcx, [rbx+10h]; CriticalSection
0x18003fdb5  call    cs:__imp_RtlLeaveCriticalSection
0x18003fdbc  nop     dword ptr [rax+rax+00h]
0x18003fdc1  nop
0x18003fdc2  mov     rbx, [rbp+var_28]
0x18003fdc6  jmp     loc_18003FE7A
0x18003fdcb  call    ?IsAppContainer@@YAHXZ; IsAppContainer(void)
0x18003fdd0  test    eax, eax
0x18003fdd2  jz      short loc_18003FE45
0x18003fdd4  mov     edx, 8; unsigned int
0x18003fdd9  mov     rcx, r14; void *
0x18003fddc  call    ?MyGetPrinterDriver@@YAPEAXPEAXK@Z; MyGetPrinterDriver(void *,ulong)
0x18003fde1  mov     rbx, rax
0x18003fde4  mov     [rbp+var_28], rax
0x18003fde8  test    rax, rax
0x18003fdeb  jz      short loc_18003FE1F
0x18003fded  mov     rcx, [rax+78h]; String1
0x18003fdf1  test    rcx, rcx
0x18003fdf4  jz      short loc_18003FE1F
0x18003fdf6  lea     rdx, a084f01faE6344d; "{084f01fa-e634-4d77-83ee-074817c03581}"
0x18003fdfd  call    wcscmp_0
0x18003fe02  test    eax, eax
0x18003fe04  jnz     short loc_18003FE1F
0x18003fe06  xor     edx, edx; hFile
0x18003fe08  lea     r8d, [rax+8]; dwFlags
0x18003fe0c  mov     rcx, [r15+18h]; lpLibFileName
0x18003fe10  call    cs:__imp_LoadLibraryExW
0x18003fe17  nop     dword ptr [rax+rax+00h]
0x18003fe1c  mov     r13, rax
0x18003fe1f  test    rbx, rbx
0x18003fe22  jz      short loc_18003FE43
0x18003fe24  mov     rcx, gs:60h
0x18003fe2d  mov     r8, rbx; P
0x18003fe30  xor     edx, edx; Flags
0x18003fe32  mov     rcx, [rcx+30h]; HeapHandle
0x18003fe36  call    cs:__imp_RtlFreeHeap
0x18003fe3d  nop     dword ptr [rax+rax+00h]
0x18003fe42  nop
0x18003fe43  jmp     short loc_18003FE5E
0x18003fe45  xor     edx, edx; hFile
0x18003fe47  lea     r8d, [rdx+8]; dwFlags
0x18003fe4b  mov     rcx, [r15+18h]; lpLibFileName
0x18003fe4f  call    cs:__imp_LoadLibraryExW
0x18003fe56  nop     dword ptr [rax+rax+00h]
0x18003fe5b  mov     r13, rax
0x18003fe5e  test    r13, r13
0x18003fe61  jz      loc_18003FF8C
0x18003fe67  xor     ebx, ebx
0x18003fe69  mov     r14, cs:?g_ulLastUmpdCookie@@3_KA; unsigned __int64 g_ulLastUmpdCookie
0x18003fe70  inc     r14
0x18003fe73  mov     cs:?g_ulLastUmpdCookie@@3_KA, r14; unsigned __int64 g_ulLastUmpdCookie
0x18003fe7a  test    r14, r14
0x18003fe7d  jnz     short loc_18003FE88
0x18003fe7f  test    r13, r13
0x18003fe82  jz      loc_18003FF8C
0x18003fe88  xor     edx, edx; Val
0x18003fe8a  mov     r8d, 398h; Size
0x18003fe90  mov     rcx, r12; void *
0x18003fe93  call    memset_0
0x18003fe98  mov     dword ptr [r12], 0FEDCBA98h
0x18003fea0  lea     rax, [r12+30h]
0x18003fea5  mov     [rax+8], rax
0x18003fea9  mov     [rax], rax
0x18003feac  mov     [rbp+var_30], 0
0x18003feb4  mov     rdx, r12; struct _UMPD *
0x18003feb7  lea     rcx, [rbp+var_30]; this
0x18003febb  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18003fec0  lea     rdx, [rbp+var_30]
0x18003fec4  lea     rcx, [rbp+var_38]; this
0x18003fec8  call    ??4UmpdPtr@@QEAAAEAV0@$$QEAV0@@Z; UmpdPtr::operator=(UmpdPtr &&)
0x18003fecd  xor     edx, edx; struct _UMPD *
0x18003fecf  lea     rcx, [rbp+var_30]; this
0x18003fed3  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18003fed8  xor     r12d, r12d
0x18003fedb  lea     rcx, [rbp+var_38]; this
0x18003fedf  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003fee4  mov     rdx, [rbp+var_38]
0x18003fee8  mov     [rdx+18h], r13
0x18003feec  lea     rcx, [rbp+var_38]; this
0x18003fef0  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003fef5  mov     rdx, [rbp+var_38]
0x18003fef9  mov     [rdx+10h], r15
0x18003fefd  xor     r15d, r15d
0x18003ff00  mov     [rbp+var_20], r15
0x18003ff04  mov     r8d, [rsi+38h]
0x18003ff08  lea     rcx, [rbp+var_38]; this
0x18003ff0c  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff11  mov     rdx, [rbp+var_38]
0x18003ff15  mov     [rdx+28h], r8d
0x18003ff19  lea     rcx, [rbp+var_38]; this
0x18003ff1d  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff22  mov     rdx, [rbp+var_38]
0x18003ff26  lock inc dword ptr [rdx+2Ch]
0x18003ff2a  lea     rcx, [rbp+var_38]; this
0x18003ff2e  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff33  mov     rdx, [rbp+var_38]
0x18003ff37  mov     dword ptr [rdx+24h], 1
0x18003ff3e  lea     rcx, [rbp+var_38]; this
0x18003ff42  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff47  mov     rdx, [rbp+var_38]
0x18003ff4b  mov     [rdx+40h], rbx
0x18003ff4f  lea     rcx, [rbp+var_38]; this
0x18003ff53  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff58  mov     rdx, [rbp+var_38]
0x18003ff5c  mov     [rdx+48h], r14
0x18003ff60  mov     r8, cs:qword_1800FEBE0
0x18003ff67  lea     rcx, [rbp+var_38]; this
0x18003ff6b  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff70  mov     rdx, [rbp+var_38]
0x18003ff74  mov     [rdx+8], r8
0x18003ff78  lea     rcx, [rbp+var_38]; this
0x18003ff7c  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ff81  mov     rdx, [rbp+var_38]
0x18003ff85  mov     cs:qword_1800FEBE0, rdx
0x18003ff8c  test    r12, r12
0x18003ff8f  jz      short loc_18003FFB0
0x18003ff91  mov     rcx, gs:60h
0x18003ff9a  mov     r8, r12; P
0x18003ff9d  xor     edx, edx; Flags
0x18003ff9f  mov     rcx, [rcx+30h]; HeapHandle
0x18003ffa3  call    cs:__imp_RtlFreeHeap
0x18003ffaa  nop     dword ptr [rax+rax+00h]
0x18003ffaf  nop
0x18003ffb0  lea     rbx, semUMPD
0x18003ffb7  mov     rax, [rbp+var_38]
0x18003ffbb  test    rax, rax
0x18003ffbe  jz      short loc_18003FFCF
0x18003ffc0  cmp     dword ptr [rax], 0FEDCBA98h
0x18003ffc6  jz      short loc_18003FFCF
0x18003ffc8  mov     ecx, 7
0x18003ffcd  int     29h; Win8: RtlFailFast(ecx)
0x18003ffcf  mov     rax, [rbp+var_38]
0x18003ffd3  mov     [rdi], rax
0x18003ffd6  mov     rcx, rdi; this
0x18003ffd9  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18003ffde  nop
0x18003ffdf  mov     [rbp+var_38], 0
0x18003ffe7  mov     rcx, rbx; lpCriticalSection
0x18003ffea  call    cs:__imp_LeaveCriticalSection
0x18003fff1  nop     dword ptr [rax+rax+00h]
0x18003fff6  nop
0x18003fff7  test    r15, r15
0x18003fffa  jz      short loc_18004001B
0x18003fffc  mov     rcx, gs:60h
0x180040005  mov     r8, r15; P
0x180040008  xor     edx, edx; Flags
0x18004000a  mov     rcx, [rcx+30h]; HeapHandle
0x18004000e  call    cs:__imp_RtlFreeHeap
0x180040015  nop     dword ptr [rax+rax+00h]
0x18004001a  nop
0x18004001b  mov     rcx, gs:60h
0x180040024  mov     r8, rsi; P
0x180040027  xor     edx, edx; Flags
  ... truncated ...
```
