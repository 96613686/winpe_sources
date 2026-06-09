# Installersp_Start(_PCA_INSTALLER *,_PCA_SERVICE *,unsigned __int64,ushort const *,void *,ulong,char const *)

- ea: `0x180003af4`
- end: `0x180004228`
- name: `?Installersp_Start@@YAKPEAU_PCA_INSTALLER@@PEAU_PCA_SERVICE@@_KPEBGPEAXKPEBD@Z`
- size: `1844`
- prototype: `unsigned int __usercall@<eax>(struct _PCA_INSTALLER *lpParameter@<rcx>, struct _PCA_SERVICE *@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, void *, unsigned int, const char *)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800219d0`
- `0x1800ad670`
- `0x1800ad6e0`

## callees

- `0x180003af4`
- `0x180004230`
- `0x1800044a4`
- `0x180004634`
- `0x1800055b8`
- `0x180005820`
- `0x180006464`
- `0x18000cb00`
- `0x180012920`
- `0x1800133c0`
- `0x180013fac`
- `0x18001b320`
- `0x1800212b0`
- `0x180026150`
- `0x180026374`
- `0x180026858`
- `0x180035760`
- `0x18004bf24`
- `0x18007a9cf`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x180003fb0`
- `ntdll!RtlReAllocateHeap` at `0x180003fb0`
- `ntdll!RtlAllocateHeap` at `0x180003f90`
- `ntdll!RtlAllocateHeap` at `0x180003f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004118`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004106`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180004106`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800040a6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800040a6`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x180003c5c`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x180003c5c`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x180004208`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x180004208`

## string_xrefs

- `0x180003b7f`: `Installersp_Start`
- `0x180003bd7`: `Installersp_Start`
- `0x180003d1b`: `Installer,Elevated non-installer`
- `0x180003d22`: `Installers`
- `0x18000403a`: `Installers`
- `0x180004088`: `Installers`
- `0x1800041c1`: `Installers`
- `0x1800040b6`: `Failed to open process token [%d]`
- `0x18000411e`: `Failed to create data collection thread [%d]`
- `0x180003c68`: `Failed to read installer process data [%d]`
- `0x180003bb2`: `Failed to copy root path [%d]`
- `0x180003b72`: `Failed to find installer type [%d]`
- `0x180003d80`: `Failed to create arpkeys list [%d]`
- `0x180003dd1`: `Failed to create arpkeys list [%d]`
- `0x180003df5`: `Failed to create process list [%d]`
- `0x180003d53`: `Failed to create files list [%d]`
- `0x180003da7`: `Failed to create files list [%d]`
- `0x180003c1b`: `Failed to get user temp path [%d]`
- `0x18000402f`: `Installersp_Start: Tracing ProcessId: %d, RegistryTracerCount: %d, FileTracerCount: %d`
- `0x180003e7f`: `Failed to activate Installer layer [%d]`
- `0x180003e6a`: `Installer`
- `0x180003e28`: `Failed to initialize installer attribute list [%d]`
- `0x1800041ae`: `Chain activated as installer,%s,ActiveCount,%d`

## pseudocode

```c
__int64 __fastcall Installersp_Start(
        struct _PCA_INSTALLER *lpParameter,
        struct _PCA_SERVICE *a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4,
        HANDLE ProcessHandle,
        unsigned int a6,
        const char *a7)
{
  struct _PCA_CHAIN *v9; // rax
  const struct _PCA_CHAIN_DATA *v10; // r14
  void *v11; // r13
  unsigned int InstallerType; // ebx
  size_t *v13; // r8
  const char *v14; // r9
  int v15; // r8d
  unsigned int IsOrphan; // eax
  __int64 v17; // rdx
  _WORD *v18; // rbx
  int ProcessTempPath; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  struct _PCA_CHAIN *v23; // rax
  void *v24; // rdx
  void *v25; // rdx
  void *v26; // rdx
  void *v27; // rdx
  unsigned int v28; // r12d
  ULONGLONG v29; // r15
  __int64 v30; // rdi
  __int64 v31; // r10
  ULONGLONG v32; // rdi
  size_t v33; // r14
  PVOID v34; // rax
  PVOID Heap; // rbx
  unsigned __int64 v36; // r14
  int v37; // ebx
  int v38; // edi
  struct _PCA_CHAIN *v39; // rax
  DWORD LastError; // eax
  HANDLE Thread; // rax
  void (*v42)(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, void *); // r8
  DWORD v43; // eax
  unsigned __int32 v44; // eax
  void *v45; // rdi
  int v46; // ebx
  struct _PCA_CHAIN *v47; // rax
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-68h]
  int dwCreationFlagsa; // [rsp+20h] [rbp-68h]
  int dwCreationFlagsb; // [rsp+20h] [rbp-68h]
  int dwCreationFlagsc; // [rsp+20h] [rbp-68h]
  int dwCreationFlagsd; // [rsp+20h] [rbp-68h]
  ULONGLONG Size; // [rsp+40h] [rbp-48h] BYREF
  ULONGLONG pullResult[8]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v56; // [rsp+90h] [rbp+8h] BYREF
  void *v57; // [rsp+98h] [rbp+10h]
  unsigned __int64 v58; // [rsp+A0h] [rbp+18h]

  v58 = a3;
  v57 = a2;
  v56 = 0;
  v9 = PcapChainFromHandle(a3);
  if ( *((_DWORD *)lpParameter + 355) )
    goto LABEL_78;
  v10 = (struct _PCA_CHAIN *)((char *)v9 + 24);
  if ( ((*((_DWORD *)v9 + 6) - 1) & 0xFFFFFFFD) != 0 )
    goto LABEL_78;
  v11 = ProcessHandle;
  InstallerType = Installersp_FindInstallerType(
                    (struct _PCA_INSTALLER *)((char *)lpParameter + 1428),
                    v10,
                    ProcessHandle,
                    a4);
  if ( InstallerType )
  {
    v14 = "Failed to find installer type [%d]";
    v15 = 1929;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"Installersp_Start", v15, (_DWORD)v14);
    goto LABEL_79;
  }
  if ( StringCopyWorkerW((STRSAFE_LPWSTR)lpParameter + 180, 0x104u, v13, a4, *(size_t *)dwCreationFlags) < 0 )
  {
    InstallerType = 122;
    v14 = "Failed to copy root path [%d]";
    v15 = 1941;
    goto LABEL_5;
  }
  IsOrphan = PcaUtilityIsOrphan((int *)lpParameter + 354, a4);
  if ( (IsOrphan & 0xFFFFFFFD) != 0 )
  {
    dwCreationFlagsa = IsOrphan;
    AslLogCallPrintf(
      1,
      (unsigned int)"Installersp_Start",
      1952,
      (unsigned int)"Failed to determine if file is an orphan [%d]");
  }
  v18 = (_WORD *)((char *)lpParameter + 880);
  ProcessTempPath = PcaUtilityGetProcessTempPath((unsigned __int16 *)lpParameter + 440, v17, v11);
  if ( ProcessTempPath )
  {
    dwCreationFlagsa = ProcessTempPath;
    AslLogCallPrintf(1, (unsigned int)"Installersp_Start", 1967, (unsigned int)"Failed to get user temp path [%d]");
    *v18 = 0;
  }
  v20 = -1;
  do
    ++v20;
  while ( v18[v20] );
  *((_QWORD *)lpParameter + 175) = v20;
  InstallerType = BaseReadAppCompatDataForProcess(v11, &v56, 0);
  if ( InstallerType )
  {
    v14 = "Failed to read installer process data [%d]";
    v15 = 1981;
    goto LABEL_5;
  }
  v21 = v56;
  *((_DWORD *)lpParameter + 370) = *(_DWORD *)(v56 + 4436);
  *((_DWORD *)lpParameter + 369) = *(_DWORD *)(v21 + 4440);
  *((_DWORD *)lpParameter + 368) = *(_DWORD *)(v21 + 4428);
  *((_DWORD *)lpParameter + 371) = *(_DWORD *)(v21 + 4444);
  if ( *((_DWORD *)v10 + 1179) || (v22 = 0, *(_DWORD *)(v21 + 4444)) )
    v22 = 1;
  *((_DWORD *)lpParameter + 358) = v22;
  *((_WORD *)lpParameter + 744) = *(_WORD *)(v21 + 532);
  if ( *(_DWORD *)v10 == 3
    || *((_DWORD *)lpParameter + 354)
    || (_DWORD)v22
    || *((_DWORD *)lpParameter + 359)
    || *((_DWORD *)lpParameter + 357) )
  {
    InstallerType = RtlStringArray::Initialize(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 8),
                      (void *)v22,
                      0,
                      0x10u,
                      dwCreationFlagsa);
    if ( InstallerType )
    {
      v14 = "Failed to create files list [%d]";
      v15 = 2018;
      goto LABEL_5;
    }
    InstallerType = RtlStringArray::Initialize(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 64),
                      v24,
                      0,
                      4u,
                      dwCreationFlagsb);
    if ( InstallerType )
    {
      v14 = "Failed to create arpkeys list [%d]";
      v15 = 2024;
      goto LABEL_5;
    }
    InstallerType = RtlStringArray::Initialize(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 120),
                      v25,
                      0,
                      0x10u,
                      dwCreationFlagsc);
    if ( InstallerType )
    {
      v14 = "Failed to create files list [%d]";
      v15 = 2030;
      goto LABEL_5;
    }
    InstallerType = RtlStringArray::Initialize(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 176),
                      v26,
                      0,
                      4u,
                      dwCreationFlagsd);
    if ( InstallerType )
    {
      v14 = "Failed to create arpkeys list [%d]";
      v15 = 2036;
      goto LABEL_5;
    }
    InstallerType = RtlArray<_PCA_INSTALLER_PROCESS_DATA>::Initialize((char *)lpParameter + 280);
    if ( InstallerType )
    {
      v14 = "Failed to create process list [%d]";
      v15 = 2042;
      goto LABEL_5;
    }
    InstallerType = RtlNameValueArray::Initialize(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 232),
                      v27,
                      0x40u,
                      0x400u);
    if ( InstallerType )
    {
      v14 = "Failed to initialize installer attribute list [%d]";
      v15 = 2048;
      goto LABEL_5;
    }
    InstallerType = RtlNameValueArray::AppendTimeStamp(
                      (struct _PCA_INSTALLER *)((char *)lpParameter + 232),
                      L"StartTime");
    if ( InstallerType )
    {
      v14 = "Failed to add timestamp [%d]";
      v15 = 2054;
      goto LABEL_5;
    }
    if ( !*((_DWORD *)lpParameter + 359) )
    {
      InstallerType = PcaUtilityActivateLayer(v11, L"Installer");
      if ( InstallerType )
      {
        v14 = "Failed to activate Installer layer [%d]";
        v15 = 2075;
        goto LABEL_5;
      }
      *((_DWORD *)lpParameter + 353) = 1;
    }
    v28 = a6;
    if ( *((_DWORD *)lpParameter + 359) == 1 )
    {
      if ( !dword_180159A60 )
      {
        InstallerType = PcaFileTracerStart(g_LoggerGlobal);
        if ( InstallerType )
        {
          v14 = "Failed to start the file tracer [%d]";
          v15 = 2092;
          goto LABEL_5;
        }
        *((_DWORD *)lpParameter + 352) = 1;
      }
      ++dword_180159A60;
      v29 = ullMultiplier;
      if ( ullMultiplier >= *(&ullMultiplier + 1) )
      {
        if ( ullMultiplier + 1 <= *(&ullMultiplier + 1) )
        {
          InstallerType = -1073741811;
LABEL_68:
          AslLogCallPrintf(
            1,
            (unsigned int)"Installersp_Start",
            2108,
            (unsigned int)"Unable to insert new process for logging");
          goto LABEL_79;
        }
        v30 = xmmword_180159AB8 - 1;
        if ( (unsigned __int64)xmmword_180159AB8 + ullMultiplier < ullMultiplier + 1
          || (Size = 0, ULongLongMult(*(&ullMultiplier + 1), (ULONGLONG)*(&::Heap + 1), pullResult) < 0)
          || (v32 = v31 & ~v30, ULongLongMult(v32, (ULONGLONG)*(&::Heap + 1), &Size) < 0) )
        {
          InstallerType = -1073741675;
          goto LABEL_68;
        }
        v33 = Size;
        if ( *((_QWORD *)&xmmword_180159AB8 + 1) )
        {
          Heap = RtlReAllocateHeap(::Heap, 0, *((PVOID *)&xmmword_180159AB8 + 1), Size);
        }
        else
        {
          v34 = RtlAllocateHeap(::Heap, 0, Size);
          Heap = v34;
          if ( v34 )
            memset_0(v34, 0, v33);
        }
        if ( !Heap )
        {
          InstallerType = -1073741801;
          goto LABEL_68;
        }
        *((_QWORD *)&xmmword_180159AB8 + 1) = Heap;
        *(&ullMultiplier + 1) = v32;
      }
      Size = 0;
      if ( ULongLongMult((ULONGLONG)*(&::Heap + 1), v29, &Size) < 0
        || *((_QWORD *)&xmmword_180159AB8 + 1) + Size < *((_QWORD *)&xmmword_180159AB8 + 1) )
      {
        InstallerType = -1073741675;
        goto LABEL_68;
      }
      *(_DWORD *)(*((_QWORD *)&xmmword_180159AB8 + 1) + Size) = v28;
      ++ullMultiplier;
      PcaTracePrintf(
        "Installers",
        0,
        0,
        "Installersp_Start: Tracing ProcessId: %d, RegistryTracerCount: %d, FileTracerCount: %d",
        v28,
        dword_180159A64,
        dword_180159A60);
    }
    v36 = v58;
    v37 = *((_DWORD *)lpParameter + 352);
    v38 = *((_DWORD *)lpParameter + 353);
    v39 = PcapChainFromHandle(v58);
    PcaTracePrintf("Installers", *((_DWORD *)v39 + 4), v28, "Tracer,ShimTracer,%d,FileTracer,%d", v38, v37);
    if ( !OpenProcessToken(v11, 0xEu, (PHANDLE)lpParameter + 44) )
    {
      LastError = GetLastError();
      v14 = "Failed to open process token [%d]";
      v15 = 2132;
      InstallerType = LastError;
      goto LABEL_5;
    }
    Thread = CreateThread(0, 0, Installersp_ThreadProc, lpParameter, 0, 0);
    *((_QWORD *)lpParameter + 42) = Thread;
    if ( !Thread )
    {
      v43 = GetLastError();
      v14 = "Failed to create data collection thread [%d]";
      v15 = 2150;
      InstallerType = v43;
      goto LABEL_5;
    }
    v44 = _InterlockedIncrement((volatile signed __int32 *)&g_InstallerGlobal);
    if ( v44 == 1 )
    {
      v45 = v57;
      if ( PcaArpMonitorDiff((LPCRITICAL_SECTION)qword_180159258, 0xFFFFFFFF, v42, v57) )
        AslLogCallPrintf(1, (unsigned int)"Installersp_Start", 2165, (unsigned int)"Failed to diff arp key [%d]");
    }
    else
    {
      if ( v44 > 1 )
        PcaMarkEvent(3, 0);
      v45 = v57;
    }
    v46 = g_InstallerGlobal;
    v47 = PcapChainFromHandle(v36);
    PcaTracePrintf("Installers", *((_DWORD *)v47 + 4), v28, "Chain activated as installer,%s,ActiveCount,%d", a7, v46);
    *((_DWORD *)lpParameter + 355) = 1;
    Installersp_SendEvent(lpParameter, v45, 15, v36, v28, v11);
    goto LABEL_78;
  }
  v23 = PcapChainFromHandle(v58);
  PcaTracePrintf("Installers", *((_DWORD *)v23 + 4), a6, "Installer,Elevated non-installer");
LABEL_78:
  InstallerType = 0;
LABEL_79:
  if ( v56 )
    BaseFreeAppCompatDataForProcess(v56);
  return InstallerType;
}

```

## disassembly

```asm
0x180003af4  mov     rax, rsp
0x180003af7  mov     [rax+20h], rbx
0x180003afb  mov     [rax+18h], r8
0x180003aff  mov     [rax+10h], rdx
0x180003b03  push    rbp
0x180003b04  push    rsi
0x180003b05  push    rdi
0x180003b06  push    r12
0x180003b08  push    r13
0x180003b0a  push    r14
0x180003b0c  push    r15
0x180003b0e  sub     rsp, 50h
0x180003b12  mov     rsi, rcx
0x180003b15  xor     r15d, r15d
0x180003b18  mov     rcx, r8; unsigned __int64
0x180003b1b  mov     [rax+8], r15
0x180003b1f  mov     rdi, r9
0x180003b22  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180003b27  cmp     [rsi+58Ch], r15d
0x180003b2e  jnz     loc_1800041F8
0x180003b34  lea     r14, [rax+18h]
0x180003b38  mov     eax, [r14]
0x180003b3b  dec     eax
0x180003b3d  test    eax, 0FFFFFFFDh
0x180003b42  jnz     loc_1800041F8
0x180003b48  mov     r13, [rsp+88h+ProcessHandle]
0x180003b50  lea     r12, [rsi+594h]
0x180003b57  mov     r8, r13; void *
0x180003b5a  mov     rcx, r12; enum PCA_INSTALLER_TYPE *
0x180003b5d  mov     r9, rdi; unsigned __int16 *
0x180003b60  mov     rdx, r14; struct _PCA_CHAIN_DATA *
0x180003b63  call    ?Installersp_FindInstallerType@@YAKPEAW4PCA_INSTALLER_TYPE@@PEBU_PCA_CHAIN_DATA@@PEAXPEBG@Z; Installersp_FindInstallerType(PCA_INSTALLER_TYPE *,_PCA_CHAIN_DATA const *,void *,ushort const *)
0x180003b68  mov     ebx, eax
0x180003b6a  test    eax, eax
0x180003b6c  jz      short loc_180003B95
0x180003b6e  mov     [rsp+88h+dwCreationFlags], eax
0x180003b72  lea     r9, aFailedToFindIn; "Failed to find installer type [%d]"
0x180003b79  mov     r8d, 789h
0x180003b7f  lea     rdx, aInstallerspSta_0; "Installersp_Start"
0x180003b86  mov     ecx, 1
0x180003b8b  call    AslLogCallPrintf
0x180003b90  jmp     loc_1800041FB
0x180003b95  lea     rcx, [rsi+168h]; pszDest
0x180003b9c  mov     r9, rdi; pszSrc
0x180003b9f  mov     edx, 104h; cchDest
0x180003ba4  call    StringCopyWorkerW
0x180003ba9  test    eax, eax
0x180003bab  jns     short loc_180003BC5
0x180003bad  mov     ebx, 7Ah ; 'z'
0x180003bb2  lea     r9, aFailedToCopyRo; "Failed to copy root path [%d]"
0x180003bb9  mov     [rsp+88h+dwCreationFlags], ebx
0x180003bbd  mov     r8d, 795h
0x180003bc3  jmp     short loc_180003B7F
0x180003bc5  lea     r15, [rsi+588h]
0x180003bcc  mov     rdx, rdi; unsigned __int16 *
0x180003bcf  mov     rcx, r15; int *
0x180003bd2  call    ?PcaUtilityIsOrphan@@YAKPEAHPEBG@Z; PcaUtilityIsOrphan(int *,ushort const *)
0x180003bd7  lea     rbp, aInstallerspSta_0; "Installersp_Start"
0x180003bde  test    eax, 0FFFFFFFDh
0x180003be3  jz      short loc_180003C03
0x180003be5  lea     r9, aFailedToDeterm_1; "Failed to determine if file is an orpha"...
0x180003bec  mov     [rsp+88h+dwCreationFlags], eax
0x180003bf0  mov     r8d, 7A0h
0x180003bf6  mov     rdx, rbp
0x180003bf9  mov     ecx, 1
0x180003bfe  call    AslLogCallPrintf
0x180003c03  lea     rbx, [rsi+370h]
0x180003c0a  mov     r8, r13; void *
0x180003c0d  mov     rcx, rbx; unsigned __int16 *
0x180003c10  call    ?PcaUtilityGetProcessTempPath@@YAKPEAGIPEAX@Z; PcaUtilityGetProcessTempPath(ushort *,uint,void *)
0x180003c15  xor     edi, edi
0x180003c17  test    eax, eax
0x180003c19  jz      short loc_180003C3A
0x180003c1b  lea     r9, aFailedToGetUse_2; "Failed to get user temp path [%d]"
0x180003c22  mov     [rsp+88h+dwCreationFlags], eax; int
0x180003c26  mov     r8d, 7AFh
0x180003c2c  lea     ecx, [rdi+1]
0x180003c2f  mov     rdx, rbp
0x180003c32  call    AslLogCallPrintf
0x180003c37  mov     [rbx], di
0x180003c3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003c3e  inc     rax
0x180003c41  cmp     [rbx+rax*2], di
0x180003c45  jnz     short loc_180003C3E
0x180003c47  xor     r8d, r8d
0x180003c4a  mov     [rsi+578h], rax
0x180003c51  lea     rdx, [rsp+88h+arg_0]
0x180003c59  mov     rcx, r13
0x180003c5c  call    cs:__imp_BaseReadAppCompatDataForProcess
0x180003c62  mov     ebx, eax
0x180003c64  test    eax, eax
0x180003c66  jz      short loc_180003C81
0x180003c68  lea     r9, aFailedToReadIn; "Failed to read installer process data ["...
0x180003c6f  mov     r8d, 7BDh
0x180003c75  mov     [rsp+88h+dwCreationFlags], eax
0x180003c79  mov     rdx, rbp
0x180003c7c  jmp     loc_180003B86
0x180003c81  mov     rcx, [rsp+88h+arg_0]
0x180003c89  mov     eax, [rcx+1154h]
0x180003c8f  mov     [rsi+5C8h], eax
0x180003c95  mov     eax, [rcx+1158h]
0x180003c9b  mov     [rsi+5C4h], eax
0x180003ca1  mov     eax, [rcx+114Ch]
0x180003ca7  mov     [rsi+5C0h], eax
0x180003cad  mov     eax, [rcx+115Ch]
0x180003cb3  mov     [rsi+5CCh], eax
0x180003cb9  cmp     [r14+126Ch], edi
0x180003cc0  jnz     short loc_180003CCC
0x180003cc2  mov     edx, edi
0x180003cc4  cmp     [rcx+115Ch], edi
0x180003cca  jz      short loc_180003CD1
0x180003ccc  mov     edx, 1; void *
0x180003cd1  mov     [rsi+598h], edx
0x180003cd7  movzx   eax, word ptr [rcx+214h]
0x180003cde  mov     [rsi+5D0h], ax
0x180003ce5  cmp     dword ptr [r14], 3
0x180003ce9  jz      short loc_180003D36
0x180003ceb  cmp     [r15], edi
0x180003cee  jnz     short loc_180003D36
0x180003cf0  xor     r15d, r15d
0x180003cf3  test    edx, edx
0x180003cf5  jnz     short loc_180003D39
0x180003cf7  cmp     [rsi+59Ch], r15d
0x180003cfe  jnz     short loc_180003D39
0x180003d00  cmp     [r12], r15d
0x180003d04  jnz     short loc_180003D39
0x180003d06  mov     rcx, [rsp+88h+arg_10]; unsigned __int64
0x180003d0e  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x180003d13  mov     r8d, [rsp+88h+arg_28]; unsigned int
0x180003d1b  lea     r9, aInstallerEleva; "Installer,Elevated non-installer"
0x180003d22  lea     rcx, aInstallers; "Installers"
0x180003d29  mov     edx, [rax+10h]; unsigned int
0x180003d2c  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x180003d31  jmp     loc_1800041F8
0x180003d36  xor     r15d, r15d
0x180003d39  mov     edi, 10h
0x180003d3e  lea     rcx, [rsi+8]; this
0x180003d42  mov     r9d, edi; unsigned __int64
0x180003d45  xor     r8d, r8d; unsigned __int64
0x180003d48  call    ?Initialize@RtlStringArray@@QEAAJPEAX_K1H@Z; RtlStringArray::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180003d4d  mov     ebx, eax
0x180003d4f  test    eax, eax
0x180003d51  jz      short loc_180003D65
0x180003d53  lea     r9, aFailedToCreate_1; "Failed to create files list [%d]"
0x180003d5a  mov     r8d, 7E2h
0x180003d60  jmp     loc_180003C75
0x180003d65  mov     r14d, 4
0x180003d6b  lea     rcx, [rsi+40h]; this
0x180003d6f  mov     r9d, r14d; unsigned __int64
0x180003d72  xor     r8d, r8d; unsigned __int64
0x180003d75  call    ?Initialize@RtlStringArray@@QEAAJPEAX_K1H@Z; RtlStringArray::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180003d7a  mov     ebx, eax
0x180003d7c  test    eax, eax
0x180003d7e  jz      short loc_180003D92
0x180003d80  lea     r9, aFailedToCreate_77; "Failed to create arpkeys list [%d]"
0x180003d87  mov     r8d, 7E8h
0x180003d8d  jmp     loc_180003C75
0x180003d92  lea     rcx, [rsi+78h]; this
0x180003d96  mov     r9, rdi; unsigned __int64
0x180003d99  xor     r8d, r8d; unsigned __int64
0x180003d9c  call    ?Initialize@RtlStringArray@@QEAAJPEAX_K1H@Z; RtlStringArray::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180003da1  mov     ebx, eax
0x180003da3  test    eax, eax
0x180003da5  jz      short loc_180003DB9
0x180003da7  lea     r9, aFailedToCreate_1; "Failed to create files list [%d]"
0x180003dae  mov     r8d, 7EEh
0x180003db4  jmp     loc_180003C75
0x180003db9  lea     rcx, [rsi+0B0h]; this
0x180003dc0  mov     r9, r14; unsigned __int64
0x180003dc3  xor     r8d, r8d; unsigned __int64
0x180003dc6  call    ?Initialize@RtlStringArray@@QEAAJPEAX_K1H@Z; RtlStringArray::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180003dcb  mov     ebx, eax
0x180003dcd  test    eax, eax
0x180003dcf  jz      short loc_180003DE3
0x180003dd1  lea     r9, aFailedToCreate_77; "Failed to create arpkeys list [%d]"
0x180003dd8  mov     r8d, 7F4h
0x180003dde  jmp     loc_180003C75
0x180003de3  lea     rcx, [rsi+118h]
0x180003dea  call    ?Initialize@?$RtlArray@U_PCA_INSTALLER_PROCESS_DATA@@@@QEAAJPEAX_K1H@Z; RtlArray<_PCA_INSTALLER_PROCESS_DATA>::Initialize(void *,unsigned __int64,unsigned __int64,int)
0x180003def  mov     ebx, eax
0x180003df1  test    eax, eax
0x180003df3  jz      short loc_180003E07
0x180003df5  lea     r9, aFailedToCreate_8; "Failed to create process list [%d]"
0x180003dfc  mov     r8d, 7FAh
0x180003e02  jmp     loc_180003C75
0x180003e07  lea     rdi, [rsi+0E8h]
0x180003e0e  mov     r9d, 400h; unsigned __int64
0x180003e14  mov     rcx, rdi; this
0x180003e17  mov     r8d, 40h ; '@'; unsigned __int64
0x180003e1d  call    ?Initialize@RtlNameValueArray@@QEAAJPEAX_K1@Z; RtlNameValueArray::Initialize(void *,unsigned __int64,unsigned __int64)
0x180003e22  mov     ebx, eax
0x180003e24  test    eax, eax
0x180003e26  jz      short loc_180003E3A
0x180003e28  lea     r9, aFailedToInitia_24; "Failed to initialize installer attribut"...
0x180003e2f  mov     r8d, 800h
0x180003e35  jmp     loc_180003C75
0x180003e3a  lea     rdx, aStarttime; "StartTime"
0x180003e41  mov     rcx, rdi; this
0x180003e44  call    ?AppendTimeStamp@RtlNameValueArray@@QEAAJPEBG@Z; RtlNameValueArray::AppendTimeStamp(ushort const *)
0x180003e49  mov     ebx, eax
0x180003e4b  test    eax, eax
0x180003e4d  jz      short loc_180003E61
0x180003e4f  lea     r9, aFailedToAddTim; "Failed to add timestamp [%d]"
0x180003e56  mov     r8d, 806h
0x180003e5c  jmp     loc_180003C75
0x180003e61  cmp     [rsi+59Ch], r15d
0x180003e68  jnz     short loc_180003E9B
0x180003e6a  lea     rdx, aInstaller; "Installer"
0x180003e71  mov     rcx, r13; hProcess
0x180003e74  call    ?PcaUtilityActivateLayer@@YAKPEAXPEBG@Z; PcaUtilityActivateLayer(void *,ushort const *)
0x180003e79  mov     ebx, eax
0x180003e7b  test    eax, eax
0x180003e7d  jz      short loc_180003E91
0x180003e7f  lea     r9, aFailedToActiva; "Failed to activate Installer layer [%d]"
0x180003e86  mov     r8d, 81Bh
0x180003e8c  jmp     loc_180003C75
0x180003e91  mov     dword ptr [rsi+584h], 1
0x180003e9b  cmp     dword ptr [rsi+59Ch], 1
0x180003ea2  mov     r12d, [rsp+88h+arg_28]
0x180003eaa  jnz     loc_18000405A
0x180003eb0  cmp     cs:dword_180159A60, r15d
0x180003eb7  jnz     short loc_180003EE7
0x180003eb9  mov     rcx, cs:?g_LoggerGlobal@@3U_PCA_LOGGER_GLOBAL@@A; struct _PCA_FILE_TRACER *
0x180003ec0  call    ?PcaFileTracerStart@@YAK_K@Z; PcaFileTracerStart(unsigned __int64)
0x180003ec5  mov     ebx, eax
0x180003ec7  test    eax, eax
0x180003ec9  jz      short loc_180003EDD
0x180003ecb  lea     r9, aFailedToStartT; "Failed to start the file tracer [%d]"
0x180003ed2  mov     r8d, 82Ch
0x180003ed8  jmp     loc_180003C75
0x180003edd  mov     dword ptr [rsi+580h], 1
0x180003ee7  inc     cs:dword_180159A60
0x180003eed  mov     r15, qword ptr cs:ullMultiplier
0x180003ef4  mov     r9, qword ptr cs:ullMultiplier+8
0x180003efb  cmp     r15, r9
0x180003efe  jb      loc_180003FDE
0x180003f04  lea     rcx, [r15+1]
0x180003f08  cmp     rcx, r9
0x180003f0b  ja      short loc_180003F17
0x180003f0d  mov     ebx, 0C000000Dh
0x180003f12  jmp     loc_180003FC3
0x180003f17  mov     rdi, qword ptr cs:xmmword_180159AB8
0x180003f1e  dec     rdi
0x180003f21  lea     r10, [rdi+rcx]
0x180003f25  cmp     r10, rcx
0x180003f28  jnb     short loc_180003F34
0x180003f2a  mov     ebx, 0C0000095h
0x180003f2f  jmp     loc_180003FC3
0x180003f34  mov     rdx, qword ptr cs:Heap+8; ullMultiplier
0x180003f3b  lea     r8, [rsp+88h+pullResult]; pullResult
0x180003f40  mov     rcx, r9; ullMultiplicand
0x180003f43  mov     [rsp+88h+Size], 0
0x180003f4c  call    ULongLongMult
0x180003f51  test    eax, eax
0x180003f53  js      short loc_180003F2A
0x180003f55  mov     rdx, qword ptr cs:Heap+8; ullMultiplier
0x180003f5c  lea     r8, [rsp+88h+Size]; pullResult
0x180003f61  not     rdi
0x180003f64  and     rdi, r10
0x180003f67  mov     rcx, rdi; ullMultiplicand
0x180003f6a  call    ULongLongMult
0x180003f6f  test    eax, eax
0x180003f71  js      short loc_180003F2A
0x180003f73  mov     r8, qword ptr cs:xmmword_180159AB8+8; Ptr
0x180003f7a  xor     edx, edx; Flags
0x180003f7c  mov     r14, [rsp+88h+Size]
0x180003f81  mov     rcx, qword ptr cs:Heap; Heap
0x180003f88  test    r8, r8
0x180003f8b  jnz     short loc_180003FAD
0x180003f8d  mov     r8, r14; Size
0x180003f90  call    cs:__imp_RtlAllocateHeap
0x180003f96  mov     rbx, rax
0x180003f99  test    rax, rax
0x180003f9c  jz      short loc_180003FB9
0x180003f9e  mov     r8, r14; Size
0x180003fa1  xor     edx, edx; Val
0x180003fa3  mov     rcx, rax; void *
0x180003fa6  call    memset_0
0x180003fab  jmp     short loc_180003FB9
0x180003fad  mov     r9, r14; Size
0x180003fb0  call    cs:__imp_RtlReAllocateHeap
0x180003fb6  mov     rbx, rax
0x180003fb9  test    rbx, rbx
0x180003fbc  jnz     short loc_180003FD0
0x180003fbe  mov     ebx, 0C0000017h
0x180003fc3  xor     r15d, r15d
0x180003fc6  test    ebx, ebx
0x180003fc8  jnz     loc_1800040CF
0x180003fce  jmp     short loc_180004029
0x180003fd0  mov     qword ptr cs:xmmword_180159AB8+8, rbx
0x180003fd7  mov     qword ptr cs:ullMultiplier+8, rdi
0x180003fde  mov     rcx, qword ptr cs:Heap+8; ullMultiplicand
0x180003fe5  lea     r8, [rsp+88h+Size]; pullResult
0x180003fea  mov     rdx, r15; ullMultiplier
0x180003fed  mov     [rsp+88h+Size], 0
0x180003ff6  call    ULongLongMult
0x180003ffb  xor     r15d, r15d
0x180003ffe  test    eax, eax
0x180004000  js      loc_1800040CA
0x180004006  mov     rdx, [rsp+88h+Size]
  ... truncated ...
```
