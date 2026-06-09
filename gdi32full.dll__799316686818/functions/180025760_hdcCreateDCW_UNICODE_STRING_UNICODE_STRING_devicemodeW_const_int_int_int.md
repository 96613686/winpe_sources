# hdcCreateDCW(_UNICODE_STRING *,_UNICODE_STRING *,_devicemodeW const *,int,int,int)

- ea: `0x180025760`
- end: `0x180025eee`
- name: `?hdcCreateDCW@@YAPEAUHDC__@@PEAU_UNICODE_STRING@@0PEBU_devicemodeW@@HHH@Z`
- size: `1934`
- prototype: `HDC(struct _UNICODE_STRING *, struct _UNICODE_STRING *, const struct _devicemodeW *, int, int, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800255c4`

## callees

- `0x180025760`
- `0x180032a24`
- `0x180033d30`
- `0x180041ae0`
- `0x180041b00`
- `0x1800449c8`
- `0x180044b18`
- `0x180044b38`
- `0x180044b88`
- `0x180044ba8`
- `0x180044d48`
- `0x180045c08`
- `0x180045c30`
- `0x180045d0c`
- `0x1800564bc`
- `0x18005bf98`
- `0x180060710`
- `0x18006a730`
- `0x1800710c4`
- `0x1800740d0`
- `0x18007ac50`
- `0x18007ba24`
- `0x1800849c0`
- `0x1800886e8`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `GDI32!bDeleteLDC` at `0x180025a36`
- `GDI32!bDeleteLDC` at `0x180025a36`
- `GDI32!ExtEscape` at `0x180025d1d`
- `GDI32!ExtEscape` at `0x180025d1d`
- `GDI32!GdiGetEntry` at `0x180025da5`
- `GDI32!GdiGetEntry` at `0x180025da5`
- `GDI32!fpClosePrinter` at `0x180025a14`
- `GDI32!gW32PID` at `0x180025ddc`
- `GDI32!gCookie` at `0x180025df0`
- `GDI32!gMaxGdiHandleCount` at `0x180025d83`
- `ntdll!RtlFreeHeap` at `0x180025a56`
- `ntdll!RtlFreeHeap` at `0x180025a56`
- `ntdll!RtlAllocateHeap` at `0x180025ba3`
- `ntdll!RtlAllocateHeap` at `0x180025c21`
- `ntdll!RtlAllocateHeap` at `0x180025c81`
- `ntdll!RtlAllocateHeap` at `0x180025e72`
- `ntdll!RtlAllocateHeap` at `0x180025ba3`
- `ntdll!RtlAllocateHeap` at `0x180025c21`
- `ntdll!RtlAllocateHeap` at `0x180025c81`
- `ntdll!RtlAllocateHeap` at `0x180025e72`
- `ntdll!RtlDecodePointer` at `0x180025824`
- `ntdll!RtlDecodePointer` at `0x1800258bc`
- `ntdll!RtlDecodePointer` at `0x180025a1e`
- `ntdll!RtlDecodePointer` at `0x180025b5a`
- `ntdll!RtlDecodePointer` at `0x180025bd0`
- `ntdll!RtlDecodePointer` at `0x180025824`
- `ntdll!RtlDecodePointer` at `0x1800258bc`
- `ntdll!RtlDecodePointer` at `0x180025a1e`
- `ntdll!RtlDecodePointer` at `0x180025b5a`
- `ntdll!RtlDecodePointer` at `0x180025bd0`
- `win32u!NtGdiDeleteObjectApp` at `0x1800259aa`
- `win32u!NtGdiDeleteObjectApp` at `0x1800259aa`
- `win32u!NtGdiOpenDCW` at `0x180025aeb`
- `win32u!NtGdiOpenDCW` at `0x180025aeb`

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
0x180025760  push    rbp
0x180025762  push    rbx
0x180025763  push    rsi
0x180025764  push    rdi
0x180025765  push    r12
0x180025767  push    r13
0x180025769  push    r14
0x18002576b  push    r15
0x18002576d  lea     rbp, [rsp-1F8h]
0x180025775  sub     rsp, 2F8h
0x18002577c  mov     rax, cs:__security_cookie
0x180025783  xor     rax, rsp
0x180025786  mov     [rbp+230h+var_50], rax
0x18002578d  mov     r12d, r9d
0x180025790  mov     rdi, r8
0x180025793  mov     [rsp+330h+var_2C8], rdx
0x180025798  mov     r15, rcx
0x18002579b  mov     r13d, [rbp+230h+arg_28]
0x1800257a2  xor     ebx, ebx
0x1800257a4  mov     r14d, ebx
0x1800257a7  mov     [rbp+230h+P], rbx
0x1800257ab  mov     [rsp+330h+var_2D8], rbx
0x1800257b0  mov     [rsp+330h+var_2E0], rbx
0x1800257b5  xor     edx, edx; struct _UMPD *
0x1800257b7  lea     rcx, [rsp+330h+var_2E0]; this
0x1800257bc  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x1800257c1  nop
0x1800257c2  mov     [rsp+330h+var_2B8], rbx
0x1800257c7  xorps   xmm0, xmm0
0x1800257ca  xor     eax, eax
0x1800257cc  movups  [rbp+230h+var_280], xmm0
0x1800257d0  mov     [rbp+230h+var_270], rax
0x1800257d4  mov     [rbp+230h+var_290], rbx
0x1800257d8  mov     dword ptr [rsp+330h+InData], ebx
0x1800257dc  test    r12d, r12d
0x1800257df  jnz     loc_18002592F
0x1800257e5  test    r15, r15
0x1800257e8  jnz     short loc_1800257F1
0x1800257ea  mov     esi, ebx
0x1800257ec  jmp     loc_180025A5D
0x1800257f1  cmp     cs:ghSpooler, rbx
0x1800257f8  jnz     short loc_180025807
0x1800257fa  call    bLoadSpooler
0x1800257ff  test    eax, eax
0x180025801  jz      loc_18002592F
0x180025807  mov     qword ptr [rbp+230h+var_280+8], rdi
0x18002580b  mov     dword ptr [rbp+230h+var_270], 8
0x180025812  lea     rax, aRaw_0; "RAW"
0x180025819  mov     qword ptr [rbp+230h+var_280], rax
0x18002581d  mov     rcx, cs:fpOpenPrinterW; Pointer
0x180025824  call    cs:__imp_RtlDecodePointer
0x18002582a  lea     r8, [rbp+230h+var_280]
0x18002582e  lea     rdx, [rsp+330h+var_2D8]
0x180025833  mov     rcx, [r15+8]
0x180025837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002583c  mov     r9, [rsp+330h+var_2D8]
0x180025841  test    r9, r9
0x180025844  jz      loc_18002592F
0x18002584a  mov     rsi, rbx
0x18002584d  mov     ebx, [rbp+230h+arg_20]
0x180025853  mov     eax, ebx
0x180025855  neg     eax
0x180025857  sbb     ecx, ecx
0x180025859  not     ecx
0x18002585b  and     ecx, 2
0x18002585e  mov     [rsp+330h+cjOutput], ecx
0x180025862  lea     r8, [rbp+230h+var_280]
0x180025866  mov     rdx, [r15+8]
0x18002586a  lea     rcx, [rsp+330h+var_2C0]
0x18002586f  call    ?LoadUserModePrinterDriver@@YA?AVUmpdPtr@@PEAGPEAU_PRINTER_DEFAULTSW@@PEAXW4UmpdLoadOptions@@@Z; LoadUserModePrinterDriver(ushort *,_PRINTER_DEFAULTSW *,void *,UmpdLoadOptions)
0x180025874  mov     rdx, rax
0x180025877  lea     rcx, [rsp+330h+var_2E0]; this
0x18002587c  call    ??4UmpdPtr@@QEAAAEAV0@$$QEAV0@@Z; UmpdPtr::operator=(UmpdPtr &&)
0x180025881  xor     edx, edx; struct _UMPD *
0x180025883  lea     rcx, [rsp+330h+var_2C0]; this
0x180025888  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x18002588d  lea     rcx, [rsp+330h+var_2E0]
0x180025892  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x180025897  test    al, al
0x180025899  jz      loc_18002594E
0x18002589f  test    rdi, rdi
0x1800258a2  jnz     short loc_1800258B5
0x1800258a4  lea     r8, [rbp+230h+P]
0x1800258a8  mov     rcx, [rsp+330h+var_2D8]
0x1800258ad  call    pdmwGetDefaultDevMode
0x1800258b2  mov     rdi, rax
0x1800258b5  mov     rcx, cs:fpDocumentEvent; Pointer
0x1800258bc  call    cs:__imp_RtlDecodePointer
0x1800258c2  test    rax, rax
0x1800258c5  jz      short loc_18002592F
0x1800258c7  mov     [rbp+230h+var_294], esi
0x1800258ca  mov     qword ptr [rbp+230h+var_2B0], rsi
0x1800258ce  mov     rcx, [r15+8]
0x1800258d2  mov     qword ptr [rbp+230h+var_2B0+8], rcx
0x1800258d6  mov     [rbp+230h+var_2A0], rdi
0x1800258da  mov     [rbp+230h+var_298], ebx
0x1800258dd  lea     rax, [rsp+330h+var_2B8]
0x1800258e2  mov     [rsp+330h+var_2F8], rax; void *
0x1800258e7  mov     [rsp+330h+var_300], 8; unsigned int
0x1800258ef  lea     rax, [rbp+230h+var_2B0]
0x1800258f3  mov     [rsp+330h+lpOutData], rax; void *
0x1800258f8  mov     [rsp+330h+cjOutput], 20h ; ' '; unsigned int
0x180025900  mov     ebx, 1
0x180025905  mov     r9d, ebx; int
0x180025908  xor     r8d, r8d; HDC
0x18002590b  mov     rdx, [rsp+330h+var_2D8]; void *
0x180025910  lea     rcx, [rsp+330h+var_2E0]; this
0x180025915  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x18002591a  cmp     eax, 0FFFFFFFFh
0x18002591d  jz      short loc_18002594E
0x18002591f  mov     dword ptr [rsp+330h+InData], ebx
0x180025923  mov     rax, [rsp+330h+var_2B8]
0x180025928  test    rax, rax
0x18002592b  cmovnz  rdi, rax
0x18002592f  lea     rcx, [rsp+330h+var_2E0]
0x180025934  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x180025939  mov     rbx, [rsp+330h+var_2E0]
0x18002593e  test    al, al
0x180025940  jnz     loc_180025A8F
0x180025946  xor     r8d, r8d
0x180025949  jmp     loc_180025A9D
0x18002594e  mov     rbx, [rsp+330h+var_2E0]
0x180025953  mov     rax, [rsp+330h+var_2D8]
0x180025958  test    rax, rax
0x18002595b  jz      short loc_1800259A2
0x18002595d  cmp     dword ptr [rsp+330h+InData], 0
0x180025962  jz      short loc_1800259A2
0x180025964  mov     [rsp+330h+var_2F8], 0; void *
0x18002596d  mov     [rsp+330h+var_300], 0; unsigned int
0x180025975  lea     rcx, [rsp+330h+var_2B8]
0x18002597a  mov     [rsp+330h+lpOutData], rcx; void *
0x18002597f  mov     [rsp+330h+cjOutput], 8; unsigned int
0x180025987  mov     r9d, 2; int
0x18002598d  xor     r8d, r8d; HDC
0x180025990  mov     rdx, rax; void *
0x180025993  lea     rcx, [rsp+330h+var_2E0]; this
0x180025998  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x18002599d  mov     rax, [rsp+330h+var_2D8]
0x1800259a2  test    rsi, rsi
0x1800259a5  jz      short loc_1800259B5
0x1800259a7  mov     rcx, rsi
0x1800259aa  call    cs:__imp_NtGdiDeleteObjectApp
0x1800259b0  mov     rax, [rsp+330h+var_2D8]
0x1800259b5  test    rax, rax
0x1800259b8  jz      short loc_180025A2E
0x1800259ba  lea     rcx, [rsp+330h+var_2E0]
0x1800259bf  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x1800259c4  test    al, al
0x1800259c6  jz      short loc_180025A14
0x1800259c8  lea     rdx, semUMPD
0x1800259cf  lea     rcx, [rsp+330h+var_2C8]
0x1800259d4  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800259d9  nop
0x1800259da  lea     rcx, [rsp+330h+var_2E0]; this
0x1800259df  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x1800259e4  lock inc dword ptr [rbx+2Ch]
0x1800259e8  test    r14, r14
0x1800259eb  jz      short loc_1800259F5
0x1800259ed  mov     rcx, r14; struct _LDC *
0x1800259f0  call    ?LdcSetUmpd@@YAXPEAU_LDC@@PEAU_UMPD@@@Z; LdcSetUmpd(_LDC *,_UMPD *)
0x1800259f5  mov     r8, [rsp+330h+var_2D8]; void *
0x1800259fa  mov     edx, 1; int
0x1800259ff  lea     rcx, [rsp+330h+var_2E0]; this
0x180025a04  call    ?UnloadUserModePrinterDriver@@YAHAEAVUmpdPtr@@HPEAX@Z; UnloadUserModePrinterDriver(UmpdPtr &,int,void *)
0x180025a09  nop
0x180025a0a  lea     rcx, [rsp+330h+var_2C8]
0x180025a0f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180025a14  mov     rcx, cs:__imp_fpClosePrinter
0x180025a1b  mov     rcx, [rcx]; Pointer
0x180025a1e  call    cs:__imp_RtlDecodePointer
0x180025a24  mov     rcx, [rsp+330h+var_2D8]
0x180025a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025a2e  test    r14, r14
0x180025a31  jz      short loc_180025A3C
0x180025a33  mov     rcx, r14
0x180025a36  call    cs:__imp_bDeleteLDC
0x180025a3c  xor     esi, esi
0x180025a3e  mov     r8, [rbp+230h+P]; P
0x180025a42  test    r8, r8
0x180025a45  jz      short loc_180025A5D
0x180025a47  mov     rcx, gs:60h
0x180025a50  xor     edx, edx; Flags
0x180025a52  mov     rcx, [rcx+30h]; HeapHandle
0x180025a56  call    cs:__imp_RtlFreeHeap
0x180025a5c  nop
0x180025a5d  xor     edx, edx; struct _UMPD *
0x180025a5f  lea     rcx, [rsp+330h+var_2E0]; this
0x180025a64  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180025a69  mov     rax, rsi
0x180025a6c  mov     rcx, [rbp+230h+var_50]
0x180025a73  xor     rcx, rsp; StackCookie
0x180025a76  call    __security_check_cookie
0x180025a7b  add     rsp, 2F8h
0x180025a82  pop     r15
0x180025a84  pop     r14
0x180025a86  pop     r13
0x180025a88  pop     r12
0x180025a8a  pop     rdi
0x180025a8b  pop     rsi
0x180025a8c  pop     rbx
0x180025a8d  pop     rbp
0x180025a8e  retn
0x180025a8f  lea     rcx, [rsp+330h+var_2E0]; this
0x180025a94  call    ?assert@UmpdPtr@@AEAAXXZ; UmpdPtr::assert(void)
0x180025a99  mov     r8, [rbx+10h]
0x180025a9d  lea     rcx, [rsp+330h+var_2E0]
0x180025aa2  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x180025aa7  neg     al
0x180025aa9  sbb     rdx, rdx
0x180025aac  and     rdx, [rsp+330h+var_2D8]
0x180025ab1  mov     eax, [rbp+230h+arg_20]
0x180025ab7  neg     eax
0x180025ab9  sbb     r9d, r9d
0x180025abc  and     r9d, 2
0x180025ac0  lea     rax, [rbp+230h+var_290]
0x180025ac4  mov     [rsp+330h+var_2F0], rax
0x180025ac9  mov     [rsp+330h+var_2F8], r8
0x180025ace  mov     qword ptr [rsp+330h+var_300], rdx
0x180025ad3  mov     dword ptr [rsp+330h+lpOutData], r13d
0x180025ad8  mov     [rsp+330h+cjOutput], r12d
0x180025add  mov     r13, [rsp+330h+var_2C8]
0x180025ae2  mov     r8, r13
0x180025ae5  mov     rdx, rdi
0x180025ae8  mov     rcx, r15
0x180025aeb  call    cs:__imp_NtGdiOpenDCW
0x180025af1  mov     rsi, rax
0x180025af4  test    rax, rax
0x180025af7  jz      loc_180025953
0x180025afd  mov     ecx, esi
0x180025aff  and     ecx, 7F0000h
0x180025b05  cmp     ecx, 10000h
0x180025b0b  jz      loc_180025A3E
0x180025b11  cmp     [rsp+330h+var_2D8], 0
0x180025b17  jz      loc_180025A3E
0x180025b1d  mov     [rsp+330h+var_2C0], 0
0x180025b25  mov     edx, 1
0x180025b2a  mov     rcx, rax
0x180025b2d  call    pldcCreate
0x180025b32  mov     r14, rax
0x180025b35  test    rax, rax
0x180025b38  jz      loc_180025953
0x180025b3e  test    rdi, rdi
0x180025b41  jz      loc_180025CA7
0x180025b47  movzx   r12d, word ptr [rdi+46h]
0x180025b4c  movzx   ecx, word ptr [rdi+44h]
0x180025b50  add     r12d, ecx
0x180025b53  mov     rcx, cs:fpIsValidDevmodeW; Pointer
0x180025b5a  call    cs:__imp_RtlDecodePointer
0x180025b60  mov     r15d, r12d
0x180025b63  mov     edx, r12d
0x180025b66  mov     rcx, rdi
0x180025b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b6e  test    eax, eax
0x180025b70  jz      loc_180025953
0x180025b76  cmp     word ptr [rdi+44h], 5Eh ; '^'
0x180025b7b  jb      short loc_180025BC9
0x180025b7d  test    dword ptr [rdi+48h], 800h
0x180025b84  jz      short loc_180025BC9
0x180025b86  mov     eax, 1
0x180025b8b  cmp     [rdi+5Ch], ax
0x180025b8f  jnz     short loc_180025BC9
0x180025b91  mov     rcx, gs:60h
0x180025b9a  mov     r8d, r15d; Size
0x180025b9d  xor     edx, edx; Flags
0x180025b9f  mov     rcx, [rcx+30h]; HeapHandle
0x180025ba3  call    cs:__imp_RtlAllocateHeap
0x180025ba9  mov     [r14+70h], rax
0x180025bad  test    rax, rax
0x180025bb0  jz      loc_180025953
0x180025bb6  mov     r8d, r15d; Size
0x180025bb9  mov     rdx, rdi; Src
0x180025bbc  mov     rcx, rax; void *
0x180025bbf  call    memcpy_0
0x180025bc4  jmp     loc_180025CA7
0x180025bc9  mov     rcx, cs:fpDocumentPropertiesW; Pointer
0x180025bd0  call    cs:__imp_RtlDecodePointer
0x180025bd6  mov     r13, rax
0x180025bd9  mov     dword ptr [rsp+330h+lpOutData], 0
0x180025be1  mov     qword ptr [rsp+330h+cjOutput], 0
0x180025bea  xor     r9d, r9d
0x180025bed  mov     r8, rdi
0x180025bf0  mov     rdx, [rsp+330h+var_2D8]
0x180025bf5  xor     ecx, ecx
0x180025bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bfc  test    eax, eax
0x180025bfe  js      short loc_180025C6F
0x180025c00  movzx   ecx, word ptr [rdi+44h]
0x180025c04  cmp     eax, ecx
0x180025c06  jl      short loc_180025C6F
0x180025c08  cmp     eax, r12d
0x180025c0b  cmova   r12d, eax
0x180025c0f  mov     rcx, gs:60h
0x180025c18  mov     r8d, r12d; Size
0x180025c1b  xor     edx, edx; Flags
0x180025c1d  mov     rcx, [rcx+30h]; HeapHandle
0x180025c21  call    cs:__imp_RtlAllocateHeap
0x180025c27  mov     [r14+70h], rax
0x180025c2b  test    rax, rax
0x180025c2e  jz      loc_180025953
0x180025c34  mov     r8d, r12d; Size
  ... truncated ...
```
