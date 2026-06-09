# hdcCreateDCW(_UNICODE_STRING *,_UNICODE_STRING *,_devicemodeW const *,int,int,int)

- ea: `0x18002e6f0`
- end: `0x18002eed9`
- name: `?hdcCreateDCW@@YAPEAUHDC__@@PEAU_UNICODE_STRING@@0PEBU_devicemodeW@@HHH@Z`
- size: `2025`
- prototype: `HDC(struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _devicemodeW *, int, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002e514`

## callees

- `0x18002e6f0`
- `0x18003888c`
- `0x180039d00`
- `0x18003e758`
- `0x18003e8c0`
- `0x18003e8e0`
- `0x18003e930`
- `0x18003e950`
- `0x18003eb04`
- `0x18003fa60`
- `0x18003fa88`
- `0x18003fb74`
- `0x1800410a4`
- `0x1800413f0`
- `0x18005b500`
- `0x180060820`
- `0x180064f9c`
- `0x18006ef00`
- `0x1800756cc`
- `0x180078938`
- `0x18007f800`
- `0x180080604`
- `0x180089ba4`
- `0x18008dc14`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `GDI32!bDeleteLDC` at `0x18002e9de`
- `GDI32!bDeleteLDC` at `0x18002e9de`
- `GDI32!ExtEscape` at `0x18002ecf6`
- `GDI32!ExtEscape` at `0x18002ecf6`
- `GDI32!GdiGetEntry` at `0x18002ed84`
- `GDI32!GdiGetEntry` at `0x18002ed84`
- `GDI32!fpClosePrinter` at `0x18002e9b6`
- `GDI32!gW32PID` at `0x18002edc1`
- `GDI32!gCookie` at `0x18002edd5`
- `GDI32!gMaxGdiHandleCount` at `0x18002ed62`
- `ntdll!RtlFreeHeap` at `0x18002ea04`
- `ntdll!RtlFreeHeap` at `0x18002ea04`
- `ntdll!RtlAllocateHeap` at `0x18002eb64`
- `ntdll!RtlAllocateHeap` at `0x18002ebee`
- `ntdll!RtlAllocateHeap` at `0x18002ec54`
- `ntdll!RtlAllocateHeap` at `0x18002ee57`
- `ntdll!RtlAllocateHeap` at `0x18002eb64`
- `ntdll!RtlAllocateHeap` at `0x18002ebee`
- `ntdll!RtlAllocateHeap` at `0x18002ec54`
- `ntdll!RtlAllocateHeap` at `0x18002ee57`
- `ntdll!RtlDecodePointer` at `0x18002e7b4`
- `ntdll!RtlDecodePointer` at `0x18002e852`
- `ntdll!RtlDecodePointer` at `0x18002e9c0`
- `ntdll!RtlDecodePointer` at `0x18002eb15`
- `ntdll!RtlDecodePointer` at `0x18002eb97`
- `ntdll!RtlDecodePointer` at `0x18002e7b4`
- `ntdll!RtlDecodePointer` at `0x18002e852`
- `ntdll!RtlDecodePointer` at `0x18002e9c0`
- `ntdll!RtlDecodePointer` at `0x18002eb15`
- `ntdll!RtlDecodePointer` at `0x18002eb97`
- `win32u!NtGdiDeleteObjectApp` at `0x18002e946`
- `win32u!NtGdiDeleteObjectApp` at `0x18002e946`
- `win32u!NtGdiOpenDCW` at `0x18002eaa0`
- `win32u!NtGdiOpenDCW` at `0x18002eaa0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HDC __fastcall hdcCreateDCW(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        const struct _devicemodeW *DefaultDevMode,
        int a4,
        int a5,
        int a6)
{
  __int64 v9; // r14
  HDC v10; // rsi
  void (__fastcall *v11)(PWSTR, void **, __int128 *); // rax
  __int64 v12; // rdx
  char v13; // al
  __int64 v14; // rbx
  void *v15; // rax
  struct _UMPD *v16; // rdx
  void (__fastcall *v17)(void *); // rax
  char v19; // al
  struct _UNICODE_STRING *v20; // r13
  __int64 v21; // r8
  __int64 v22; // rax
  unsigned int v23; // r12d
  unsigned int (__fastcall *v24)(const struct _devicemodeW *, _QWORD); // rax
  size_t v25; // r15
  PVOID Heap; // rax
  PVOID v27; // r13
  int v28; // eax
  PVOID v29; // rax
  void *v30; // rcx
  PVOID v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 ColorSpaceByName; // rbx
  __int64 Length; // rbx
  PVOID v37; // rax
  void *v38; // rdx
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  void *v40; // [rsp+58h] [rbp-A8h] BYREF
  CHAR InData[8]; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING *v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+70h] [rbp-90h] BYREF
  const struct _devicemodeW *v44; // [rsp+78h] [rbp-88h] BYREF
  __int128 v45; // [rsp+80h] [rbp-80h] BYREF
  const struct _devicemodeW *v46; // [rsp+90h] [rbp-70h]
  int v47; // [rsp+98h] [rbp-68h]
  int v48; // [rsp+9Ch] [rbp-64h]
  __int64 v49; // [rsp+A0h] [rbp-60h] BYREF
  PVOID P; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v51; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+C0h] [rbp-40h]
  _BYTE v53[528]; // [rsp+D0h] [rbp-30h] BYREF

  v42 = a2;
  v9 = 0;
  P = 0;
  v40 = 0;
  v39 = 0;
  UmpdPtr::reset((UmpdPtr *)&v39, 0);
  v44 = 0;
  v51 = 0;
  v52 = 0;
  v49 = 0;
  *(_DWORD *)InData = 0;
  if ( !a4 )
  {
    if ( !a1 )
    {
      v10 = 0;
      goto LABEL_33;
    }
    if ( ghSpooler || (unsigned int)bLoadSpooler() )
    {
      *((_QWORD *)&v51 + 1) = DefaultDevMode;
      LODWORD(v52) = 8;
      *(_QWORD *)&v51 = L"RAW";
      v11 = (void (__fastcall *)(PWSTR, void **, __int128 *))RtlDecodePointer(fpOpenPrinterW);
      v11(a1->Buffer, &v40, &v51);
      if ( v40 )
      {
        v10 = 0;
        LoadUserModePrinterDriver(&v43, a1->Buffer, &v51);
        UmpdPtr::operator=((UmpdPtr *)&v39);
        UmpdPtr::reset((UmpdPtr *)&v43, 0);
        if ( !(unsigned __int8)UmpdPtr::operator bool(&v39) )
          goto LABEL_16;
        if ( !DefaultDevMode )
          DefaultDevMode = (const struct _devicemodeW *)pdmwGetDefaultDevMode(v40, v12, &P);
        if ( RtlDecodePointer(fpDocumentEvent) )
        {
          v48 = 0;
          *(_QWORD *)&v45 = 0;
          *((_QWORD *)&v45 + 1) = a1->Buffer;
          v46 = DefaultDevMode;
          v47 = a5;
          if ( (unsigned int)DocumentEventEx((struct UmpdPtr *)&v39, v40, 0, 1, 0x20u, &v45, 8u, &v44) != -1 )
          {
            *(_DWORD *)InData = 1;
            if ( v44 )
              DefaultDevMode = v44;
            goto LABEL_14;
          }
LABEL_16:
          v14 = v39;
          goto LABEL_17;
        }
      }
    }
  }
LABEL_14:
  v13 = UmpdPtr::operator bool(&v39);
  v14 = v39;
  if ( v13 )
    UmpdPtr::assert((UmpdPtr *)&v39);
  v19 = UmpdPtr::operator bool(&v39);
  v20 = v42;
  v22 = NtGdiOpenDCW(
          a1,
          DefaultDevMode,
          v42,
          a5 != 0 ? 2 : 0,
          a4,
          a6,
          (unsigned __int64)v40 & -(__int64)(v19 != 0),
          v21,
          &v49);
  v10 = (HDC)v22;
  if ( !v22 )
    goto LABEL_17;
  if ( (v22 & 0x7F0000) != 0x10000 && v40 )
  {
    v43 = 0;
    v9 = pldcCreate(v22, 1);
    if ( !v9 )
      goto LABEL_17;
    if ( !DefaultDevMode )
      goto LABEL_57;
    v23 = DefaultDevMode->dmSize + DefaultDevMode->dmDriverExtra;
    v24 = (unsigned int (__fastcall *)(const struct _devicemodeW *, _QWORD))RtlDecodePointer(fpIsValidDevmodeW);
    v25 = v23;
    if ( !v24(DefaultDevMode, v23) )
      goto LABEL_17;
    if ( DefaultDevMode->dmSize >= 0x5Eu && (DefaultDevMode->dmFields & 0x800) != 0 && DefaultDevMode->dmColor == 1 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      *(_QWORD *)(v9 + 112) = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, DefaultDevMode, v23);
        goto LABEL_57;
      }
LABEL_17:
      v15 = v40;
      if ( v40 && *(_DWORD *)InData )
      {
        DocumentEventEx((struct UmpdPtr *)&v39, v40, 0, 2, 8u, &v44, 0, 0);
        v15 = v40;
      }
      if ( v10 )
      {
        NtGdiDeleteObjectApp(v10);
        v15 = v40;
      }
      if ( v15 )
      {
        if ( (unsigned __int8)UmpdPtr::operator bool(&v39) )
        {
          wil::EnterCriticalSection(&v42, &semUMPD);
          UmpdPtr::assert((UmpdPtr *)&v39);
          _InterlockedIncrement((volatile signed __int32 *)(v14 + 44));
          if ( v9 )
            LdcSetUmpd((struct _LDC *)v9, v16);
          UnloadUserModePrinterDriver((struct UmpdPtr *)&v39, 1, v40);
          wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v42);
        }
        v17 = (void (__fastcall *)(void *))RtlDecodePointer(fpClosePrinter);
        v17(v40);
      }
      if ( v9 )
        bDeleteLDC(v9);
      v10 = 0;
      goto LABEL_31;
    }
    v27 = RtlDecodePointer(fpDocumentPropertiesW);
    v28 = ((__int64 (__fastcall *)(_QWORD, void *, const struct _devicemodeW *, _QWORD, _QWORD, _DWORD))v27)(
            0,
            v40,
            DefaultDevMode,
            0,
            0,
            0);
    if ( v28 < 0 || v28 < DefaultDevMode->dmSize )
    {
      v31 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      *(_QWORD *)(v9 + 112) = v31;
      if ( !v31 )
        goto LABEL_17;
      v30 = v31;
    }
    else
    {
      if ( v28 > v23 )
        v23 = v28;
      v29 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
      *(_QWORD *)(v9 + 112) = v29;
      if ( !v29 )
        goto LABEL_17;
      memset_0(v29, 0, v23);
      if ( ((unsigned int (__fastcall *)(_QWORD, void *, const struct _devicemodeW *, _QWORD, const struct _devicemodeW *, int))v27)(
             0,
             v40,
             DefaultDevMode,
             *(_QWORD *)(v9 + 112),
             DefaultDevMode,
             10) == 1 )
      {
LABEL_56:
        v20 = v42;
LABEL_57:
        *(_QWORD *)(v9 + 48) = v40;
        LdcSetUmpd((struct _LDC *)v9, (struct UmpdPtr *)&v39);
        *(_QWORD *)(v9 + 80) = v49;
        if ( (unsigned __int8)UmpdPtr::operator bool(&v39) )
        {
          UmpdPtr::assert((UmpdPtr *)&v39);
          if ( (*(_BYTE *)(v14 + 32) & 4) == 0 )
          {
            UmpdPtr::assert((UmpdPtr *)&v39);
            if ( (*(_BYTE *)(v14 + 32) & 2) == 0 )
            {
              *(_DWORD *)InData = 2049;
              if ( ExtEscape(v10, 8, 4, InData, 0, 0) )
              {
                UmpdPtr::assert((UmpdPtr *)&v39);
                *(_DWORD *)(v14 + 32) |= 2u;
              }
              else
              {
                UmpdPtr::assert((UmpdPtr *)&v39);
                *(_DWORD *)(v14 + 32) |= 4u;
              }
            }
          }
        }
        if ( a5 )
          *(_DWORD *)(v9 + 8) |= 0x1000000u;
        IcmInitLocalDC(v10);
        if ( (unsigned int)GetDefaultDestinationProfile(v10, v53, &v43) )
        {
          v32 = HANDLE_TO_INDEX(v10);
          if ( v32 < gMaxGdiHandleCount )
          {
            v45 = 0;
            v46 = 0;
            if ( (int)GdiGetEntry(v32, &v45) >= 0
              && BYTE14(v45) == 1
              && WORD6(v45) == WORD1(v10)
              && (DWORD2(v45) & 0xFFFFFFFE) == gW32PID )
            {
              if ( v46 )
              {
                v33 = __ROR8__(v46, 64 - (gCookie & 0x3Fu));
                if ( v33 != gCookie )
                {
                  v34 = *(_QWORD *)((v33 ^ gCookie) + 0x108);
                  if ( v34 )
                  {
                    ColorSpaceByName = IcmGetOrCreateColorSpaceByName(v10, v53, *(unsigned int *)(v34 + 96), v43);
                    if ( ColorSpaceByName )
                    {
                      SetICMProfileInternalW(v10, 0);
                      IcmReleaseColorSpace(0, ColorSpaceByName, 0);
                    }
                  }
                }
              }
            }
          }
        }
        if ( v20 )
        {
          Length = v20->Length;
          v37 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Length + 2);
          *(_QWORD *)(v9 + 24) = v37;
          if ( v37 )
            memcpy_0(v37, v20->Buffer, Length + 2);
        }
        LdcGetUmpd(&v42, v9);
        UmpdPtr::operator=((UmpdPtr *)&v39);
        UmpdPtr::reset((UmpdPtr *)&v42, 0);
        DocumentEventEx((struct UmpdPtr *)&v39, v40, v10, (_DWORD)v38 + 2, 8u, &v44, (unsigned int)v38, v38);
        goto LABEL_31;
      }
      v30 = *(void **)(v9 + 112);
    }
    memcpy_0(v30, DefaultDevMode, v25);
    goto LABEL_56;
  }
LABEL_31:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
LABEL_33:
  UmpdPtr::reset((UmpdPtr *)&v39, 0);
  return v10;
}

```

## disassembly

```asm
0x18002e6f0  push    rbp
0x18002e6f2  push    rbx
0x18002e6f3  push    rsi
0x18002e6f4  push    rdi
0x18002e6f5  push    r12
0x18002e6f7  push    r13
0x18002e6f9  push    r14
0x18002e6fb  push    r15
0x18002e6fd  lea     rbp, [rsp-1F8h]
0x18002e705  sub     rsp, 2F8h
0x18002e70c  mov     rax, cs:__security_cookie
0x18002e713  xor     rax, rsp
0x18002e716  mov     [rbp+230h+var_50], rax
0x18002e71d  mov     r12d, r9d
0x18002e720  mov     rdi, r8
0x18002e723  mov     [rsp+330h+var_2C8], rdx
0x18002e728  mov     r15, rcx
0x18002e72b  mov     r13d, [rbp+230h+arg_28]
0x18002e732  xor     ebx, ebx
0x18002e734  mov     r14d, ebx
0x18002e737  mov     [rbp+230h+P], rbx
0x18002e73b  mov     [rsp+330h+var_2D8], rbx
0x18002e740  mov     [rsp+330h+var_2E0], rbx
0x18002e745  xor     edx, edx; struct _UMPD *
0x18002e747  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e74c  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18002e751  nop
0x18002e752  mov     [rsp+330h+var_2B8], rbx
0x18002e757  xorps   xmm0, xmm0
0x18002e75a  xor     eax, eax
0x18002e75c  movups  [rbp+230h+var_280], xmm0
0x18002e760  mov     [rbp+230h+var_270], rax
0x18002e764  mov     [rbp+230h+var_290], rbx
0x18002e768  mov     dword ptr [rsp+330h+InData], ebx
0x18002e76c  test    r12d, r12d
0x18002e76f  jnz     loc_18002E8CB
0x18002e775  test    r15, r15
0x18002e778  jnz     short loc_18002E781
0x18002e77a  mov     esi, ebx
0x18002e77c  jmp     loc_18002EA11
0x18002e781  cmp     cs:ghSpooler, rbx
0x18002e788  jnz     short loc_18002E797
0x18002e78a  call    bLoadSpooler
0x18002e78f  test    eax, eax
0x18002e791  jz      loc_18002E8CB
0x18002e797  mov     qword ptr [rbp+230h+var_280+8], rdi
0x18002e79b  mov     dword ptr [rbp+230h+var_270], 8
0x18002e7a2  lea     rax, aRaw_0; "RAW"
0x18002e7a9  mov     qword ptr [rbp+230h+var_280], rax
0x18002e7ad  mov     rcx, cs:fpOpenPrinterW; Pointer
0x18002e7b4  call    cs:__imp_RtlDecodePointer
0x18002e7bb  nop     dword ptr [rax+rax+00h]
0x18002e7c0  lea     r8, [rbp+230h+var_280]
0x18002e7c4  lea     rdx, [rsp+330h+var_2D8]
0x18002e7c9  mov     rcx, [r15+8]
0x18002e7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7d2  mov     r9, [rsp+330h+var_2D8]
0x18002e7d7  test    r9, r9
0x18002e7da  jz      loc_18002E8CB
0x18002e7e0  mov     rsi, rbx
0x18002e7e3  mov     ebx, [rbp+230h+arg_20]
0x18002e7e9  mov     eax, ebx
0x18002e7eb  neg     eax
0x18002e7ed  sbb     ecx, ecx
0x18002e7ef  not     ecx
0x18002e7f1  and     ecx, 2
0x18002e7f4  mov     [rsp+330h+cjOutput], ecx
0x18002e7f8  lea     r8, [rbp+230h+var_280]
0x18002e7fc  mov     rdx, [r15+8]
0x18002e800  lea     rcx, [rsp+330h+var_2C0]
0x18002e805  call    ?LoadUserModePrinterDriver@@YA?AVUmpdPtr@@PEAGPEAU_PRINTER_DEFAULTSW@@PEAXW4UmpdLoadOptions@@@Z; LoadUserModePrinterDriver(ushort *,_PRINTER_DEFAULTSW *,void *,UmpdLoadOptions)
0x18002e80a  mov     rdx, rax
0x18002e80d  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e812  call    ??4UmpdPtr@@QEAAAEAV0@$$QEAV0@@Z; UmpdPtr::operator=(UmpdPtr &&)
0x18002e817  xor     edx, edx; struct _UMPD *
0x18002e819  lea     rcx, [rsp+330h+var_2C0]; this
0x18002e81e  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18002e823  lea     rcx, [rsp+330h+var_2E0]
0x18002e828  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x18002e82d  test    al, al
0x18002e82f  jz      loc_18002E8EA
0x18002e835  test    rdi, rdi
0x18002e838  jnz     short loc_18002E84B
0x18002e83a  lea     r8, [rbp+230h+P]
0x18002e83e  mov     rcx, [rsp+330h+var_2D8]
0x18002e843  call    pdmwGetDefaultDevMode
0x18002e848  mov     rdi, rax
0x18002e84b  mov     rcx, cs:fpDocumentEvent; Pointer
0x18002e852  call    cs:__imp_RtlDecodePointer
0x18002e859  nop     dword ptr [rax+rax+00h]
0x18002e85e  test    rax, rax
0x18002e861  jz      short loc_18002E8CB
0x18002e863  mov     [rbp+230h+var_294], esi
0x18002e866  mov     qword ptr [rbp+230h+var_2B0], rsi
0x18002e86a  mov     rcx, [r15+8]
0x18002e86e  mov     qword ptr [rbp+230h+var_2B0+8], rcx
0x18002e872  mov     [rbp+230h+var_2A0], rdi
0x18002e876  mov     [rbp+230h+var_298], ebx
0x18002e879  lea     rax, [rsp+330h+var_2B8]
0x18002e87e  mov     [rsp+330h+var_2F8], rax; void *
0x18002e883  mov     [rsp+330h+var_300], 8; unsigned int
0x18002e88b  lea     rax, [rbp+230h+var_2B0]
0x18002e88f  mov     [rsp+330h+lpOutData], rax; void *
0x18002e894  mov     [rsp+330h+cjOutput], 20h ; ' '; unsigned int
0x18002e89c  mov     ebx, 1
0x18002e8a1  mov     r9d, ebx; int
0x18002e8a4  xor     r8d, r8d; HDC
0x18002e8a7  mov     rdx, [rsp+330h+var_2D8]; void *
0x18002e8ac  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e8b1  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x18002e8b6  cmp     eax, 0FFFFFFFFh
0x18002e8b9  jz      short loc_18002E8EA
0x18002e8bb  mov     dword ptr [rsp+330h+InData], ebx
0x18002e8bf  mov     rax, [rsp+330h+var_2B8]
0x18002e8c4  test    rax, rax
0x18002e8c7  cmovnz  rdi, rax
0x18002e8cb  lea     rcx, [rsp+330h+var_2E0]
0x18002e8d0  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x18002e8d5  mov     rbx, [rsp+330h+var_2E0]
0x18002e8da  test    al, al
0x18002e8dc  jnz     loc_18002EA44
0x18002e8e2  xor     r8d, r8d
0x18002e8e5  jmp     loc_18002EA52
0x18002e8ea  mov     rbx, [rsp+330h+var_2E0]
0x18002e8ef  mov     rax, [rsp+330h+var_2D8]
0x18002e8f4  test    rax, rax
0x18002e8f7  jz      short loc_18002E93E
0x18002e8f9  cmp     dword ptr [rsp+330h+InData], 0
0x18002e8fe  jz      short loc_18002E93E
0x18002e900  mov     [rsp+330h+var_2F8], 0; void *
0x18002e909  mov     [rsp+330h+var_300], 0; unsigned int
0x18002e911  lea     rcx, [rsp+330h+var_2B8]
0x18002e916  mov     [rsp+330h+lpOutData], rcx; void *
0x18002e91b  mov     [rsp+330h+cjOutput], 8; unsigned int
0x18002e923  mov     r9d, 2; int
0x18002e929  xor     r8d, r8d; HDC
0x18002e92c  mov     rdx, rax; void *
0x18002e92f  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e934  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x18002e939  mov     rax, [rsp+330h+var_2D8]
0x18002e93e  test    rsi, rsi
0x18002e941  jz      short loc_18002E957
0x18002e943  mov     rcx, rsi
0x18002e946  call    cs:__imp_NtGdiDeleteObjectApp
0x18002e94d  nop     dword ptr [rax+rax+00h]
0x18002e952  mov     rax, [rsp+330h+var_2D8]
0x18002e957  test    rax, rax
0x18002e95a  jz      short loc_18002E9D6
0x18002e95c  lea     rcx, [rsp+330h+var_2E0]
0x18002e961  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x18002e966  test    al, al
0x18002e968  jz      short loc_18002E9B6
0x18002e96a  lea     rdx, semUMPD
0x18002e971  lea     rcx, [rsp+330h+var_2C8]
0x18002e976  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18002e97b  nop
0x18002e97c  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e981  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18002e986  lock inc dword ptr [rbx+2Ch]
0x18002e98a  test    r14, r14
0x18002e98d  jz      short loc_18002E997
0x18002e98f  mov     rcx, r14; struct _LDC *
0x18002e992  call    ?LdcSetUmpd@@YAXPEAU_LDC@@PEAU_UMPD@@@Z; LdcSetUmpd(_LDC *,_UMPD *)
0x18002e997  mov     r8, [rsp+330h+var_2D8]; void *
0x18002e99c  mov     edx, 1; int
0x18002e9a1  lea     rcx, [rsp+330h+var_2E0]; this
0x18002e9a6  call    ?UnloadUserModePrinterDriver@@YAHAEAVUmpdPtr@@HPEAX@Z; UnloadUserModePrinterDriver(UmpdPtr &,int,void *)
0x18002e9ab  nop
0x18002e9ac  lea     rcx, [rsp+330h+var_2C8]
0x18002e9b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002e9b6  mov     rcx, cs:__imp_fpClosePrinter
0x18002e9bd  mov     rcx, [rcx]; Pointer
0x18002e9c0  call    cs:__imp_RtlDecodePointer
0x18002e9c7  nop     dword ptr [rax+rax+00h]
0x18002e9cc  mov     rcx, [rsp+330h+var_2D8]
0x18002e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9d6  test    r14, r14
0x18002e9d9  jz      short loc_18002E9EA
0x18002e9db  mov     rcx, r14
0x18002e9de  call    cs:__imp_bDeleteLDC
0x18002e9e5  nop     dword ptr [rax+rax+00h]
0x18002e9ea  xor     esi, esi
0x18002e9ec  mov     r8, [rbp+230h+P]; P
0x18002e9f0  test    r8, r8
0x18002e9f3  jz      short loc_18002EA11
0x18002e9f5  mov     rcx, gs:60h
0x18002e9fe  xor     edx, edx; Flags
0x18002ea00  mov     rcx, [rcx+30h]; HeapHandle
0x18002ea04  call    cs:__imp_RtlFreeHeap
0x18002ea0b  nop     dword ptr [rax+rax+00h]
0x18002ea10  nop
0x18002ea11  xor     edx, edx; struct _UMPD *
0x18002ea13  lea     rcx, [rsp+330h+var_2E0]; this
0x18002ea18  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18002ea1d  mov     rax, rsi
0x18002ea20  mov     rcx, [rbp+230h+var_50]
0x18002ea27  xor     rcx, rsp; StackCookie
0x18002ea2a  call    __security_check_cookie
0x18002ea2f  add     rsp, 2F8h
0x18002ea36  pop     r15
0x18002ea38  pop     r14
0x18002ea3a  pop     r13
0x18002ea3c  pop     r12
0x18002ea3e  pop     rdi
0x18002ea3f  pop     rsi
0x18002ea40  pop     rbx
0x18002ea41  pop     rbp
0x18002ea42  retn
0x18002ea44  lea     rcx, [rsp+330h+var_2E0]; this
0x18002ea49  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x18002ea4e  mov     r8, [rbx+10h]
0x18002ea52  lea     rcx, [rsp+330h+var_2E0]
0x18002ea57  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x18002ea5c  neg     al
0x18002ea5e  sbb     rdx, rdx
0x18002ea61  and     rdx, [rsp+330h+var_2D8]
0x18002ea66  mov     eax, [rbp+230h+arg_20]
0x18002ea6c  neg     eax
0x18002ea6e  sbb     r9d, r9d
0x18002ea71  and     r9d, 2
0x18002ea75  lea     rax, [rbp+230h+var_290]
0x18002ea79  mov     [rsp+330h+var_2F0], rax
0x18002ea7e  mov     [rsp+330h+var_2F8], r8
0x18002ea83  mov     qword ptr [rsp+330h+var_300], rdx
0x18002ea88  mov     dword ptr [rsp+330h+lpOutData], r13d
0x18002ea8d  mov     [rsp+330h+cjOutput], r12d
0x18002ea92  mov     r13, [rsp+330h+var_2C8]
0x18002ea97  mov     r8, r13
0x18002ea9a  mov     rdx, rdi
0x18002ea9d  mov     rcx, r15
0x18002eaa0  call    cs:__imp_NtGdiOpenDCW
0x18002eaa7  nop     dword ptr [rax+rax+00h]
0x18002eaac  mov     rsi, rax
0x18002eaaf  test    rax, rax
0x18002eab2  jz      loc_18002E8EF
0x18002eab8  mov     ecx, esi
0x18002eaba  and     ecx, 7F0000h
0x18002eac0  cmp     ecx, 10000h
0x18002eac6  jz      loc_18002E9EC
0x18002eacc  cmp     [rsp+330h+var_2D8], 0
0x18002ead2  jz      loc_18002E9EC
0x18002ead8  mov     [rsp+330h+var_2C0], 0
0x18002eae0  mov     edx, 1
0x18002eae5  mov     rcx, rax
0x18002eae8  call    pldcCreate
0x18002eaed  mov     r14, rax
0x18002eaf0  test    rax, rax
0x18002eaf3  jz      loc_18002E8EF
0x18002eaf9  test    rdi, rdi
0x18002eafc  jz      loc_18002EC80
0x18002eb02  movzx   r12d, word ptr [rdi+46h]
0x18002eb07  movzx   ecx, word ptr [rdi+44h]
0x18002eb0b  add     r12d, ecx
0x18002eb0e  mov     rcx, cs:fpIsValidDevmodeW; Pointer
0x18002eb15  call    cs:__imp_RtlDecodePointer
0x18002eb1c  nop     dword ptr [rax+rax+00h]
0x18002eb21  mov     r15d, r12d
0x18002eb24  mov     edx, r12d
0x18002eb27  mov     rcx, rdi
0x18002eb2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb2f  test    eax, eax
0x18002eb31  jz      loc_18002E8EF
0x18002eb37  cmp     word ptr [rdi+44h], 5Eh ; '^'
0x18002eb3c  jb      short loc_18002EB90
0x18002eb3e  test    dword ptr [rdi+48h], 800h
0x18002eb45  jz      short loc_18002EB90
0x18002eb47  mov     eax, 1
0x18002eb4c  cmp     [rdi+5Ch], ax
0x18002eb50  jnz     short loc_18002EB90
0x18002eb52  mov     rcx, gs:60h
0x18002eb5b  mov     r8d, r15d; Size
0x18002eb5e  xor     edx, edx; Flags
0x18002eb60  mov     rcx, [rcx+30h]; HeapHandle
0x18002eb64  call    cs:__imp_RtlAllocateHeap
0x18002eb6b  nop     dword ptr [rax+rax+00h]
0x18002eb70  mov     [r14+70h], rax
0x18002eb74  test    rax, rax
0x18002eb77  jz      loc_18002E8EF
0x18002eb7d  mov     r8d, r15d; Size
0x18002eb80  mov     rdx, rdi; Src
0x18002eb83  mov     rcx, rax; void *
0x18002eb86  call    memcpy_0
0x18002eb8b  jmp     loc_18002EC80
0x18002eb90  mov     rcx, cs:fpDocumentPropertiesW; Pointer
0x18002eb97  call    cs:__imp_RtlDecodePointer
0x18002eb9e  nop     dword ptr [rax+rax+00h]
0x18002eba3  mov     r13, rax
0x18002eba6  mov     dword ptr [rsp+330h+lpOutData], 0
0x18002ebae  mov     qword ptr [rsp+330h+cjOutput], 0
0x18002ebb7  xor     r9d, r9d
0x18002ebba  mov     r8, rdi
0x18002ebbd  mov     rdx, [rsp+330h+var_2D8]
0x18002ebc2  xor     ecx, ecx
0x18002ebc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ebc9  test    eax, eax
0x18002ebcb  js      short loc_18002EC42
0x18002ebcd  movzx   ecx, word ptr [rdi+44h]
0x18002ebd1  cmp     eax, ecx
0x18002ebd3  jl      short loc_18002EC42
0x18002ebd5  cmp     eax, r12d
  ... truncated ...
```
