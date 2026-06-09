# CModule::DllMainInt(HINSTANCE__ *,ulong,void *)

- ea: `0x18001f5f4`
- end: `0x18001faa9`
- name: `?DllMainInt@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `1205`
- prototype: `int(CModule *__hidden this, HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001f5e0`

## callees

- `0x18000c6b0`
- `0x18001f060`
- `0x18001f5f4`
- `0x18001fae8`
- `0x18001fb9c`
- `0x18001fc10`
- `0x18001fd2c`
- `0x18001fe20`
- `0x18001fe60`
- `0x18001fe84`
- `0x180076f20`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001f9e0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fa00`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fa20`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001f9e0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fa00`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18001fa20`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f773`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18001f773`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f7d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f841`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f7d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001f841`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f7a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f7a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f8d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f987`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f8d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f987`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f95d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f99c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f795`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f8c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f95d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f979`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f99c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa4e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f96e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f9ad`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001fa5f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f96e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001f9ad`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001fa5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001f684`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001f684`

## string_xrefs

- `0x18001f90c`: `RtlUnsubscribeWnfNotificationWaitForCompletion`

## pseudocode

```c
__int64 __fastcall CModule::DllMainInt(CModule *this, HINSTANCE a2, int a3, void *a4)
{
  unsigned int v6; // esi
  __int64 v8; // rcx
  int i; // eax
  unsigned int v10; // ebx
  WCHAR *v11; // r14
  UINT v12; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  HANDLE v18; // rax
  WCHAR *v19; // rdi
  unsigned int v20; // ebp
  DWORD ModuleFileNameW; // eax
  DWORD v22; // ecx
  bool v23; // zf
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // r14
  DWORD v27; // ebx
  DWORD v28; // eax
  DWORD v29; // ecx
  void *v30; // rbx
  HANDLE ProcessHeap; // rax
  char **v32; // rax
  CModule *v33; // rcx
  HANDLE v34; // rax
  WCHAR *v35; // rax
  HANDLE v36; // rax
  HANDLE v37; // rax
  WCHAR *v38; // rax
  signed int v39; // eax
  CModule *v40; // rcx
  bool v41; // r9
  signed int v42; // eax
  CModule *v43; // rcx
  bool v44; // r9
  signed int v45; // eax
  CModule *v46; // rcx
  bool v47; // r9
  HANDLE v48; // rax
  WCHAR *v49; // rax
  GUID v50; // [rsp+20h] [rbp-58h] BYREF

  v6 = 1;
  if ( !a3 )
  {
    TraceLoggingUnregister_EtwEventUnregister(off_180108330);
    if ( g_pDebugPrivate )
    {
      v50 = DXGI_DEBUG_DXGI;
      (*(void (__fastcall **)(struct IDXGIDebugPrivate *, GUID *, bool))(*(_QWORD *)g_pDebugPrivate + 80LL))(
        g_pDebugPrivate,
        &v50,
        a4 != 0);
    }
    McGenEventUnregister_EtwEventUnregister();
    CDXGIMutexInSeparateThread::DestroyMutex((CDXGIMutexInSeparateThread *)&qword_180109AB0);
    CDXGIMutexInSeparateThread::DestroyMutex((CDXGIMutexInSeparateThread *)&qword_180109AF8);
    v30 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v30);
    }
    Size = 0;
    v32 = &g_CompatStringCache;
    if ( (unsigned __int64)qword_180109990 > 0xF )
      v32 = (char **)g_CompatStringCache;
    *(_BYTE *)v32 = 0;
    StereoModuleData::DeInit((StereoModuleData *)&stru_180109A28);
    if ( qword_180109A48 )
    {
      v39 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      if ( v39 < 0 )
        CModule::RecordJournalImpl(v40, v39, "RtlUnsubscribeWnfNotificationWaitForCompletion", v41);
      qword_180109A48 = 0;
    }
    if ( *(&xmmword_180109A10 + 1) )
    {
      v42 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      if ( v42 < 0 )
        CModule::RecordJournalImpl(v43, v42, "RtlUnsubscribeWnfNotificationWaitForCompletion", v44);
      *(&xmmword_180109A10 + 1) = 0;
    }
    if ( stru_180109A50 )
    {
      v45 = RtlUnsubscribeWnfNotificationWaitForCompletion();
      if ( v45 < 0 )
        CModule::RecordJournalImpl(v46, v45, "RtlUnsubscribeWnfNotificationWaitForCompletion", v47);
      stru_180109A50 = 0;
    }
    AdapterEnumModuleData::DeInit((AdapterEnumModuleData *)&byte_180109A60);
    CModule::ClearAllDetours(v33);
    return v6;
  }
  if ( a3 != 1 )
    return v6;
  byte_180109B40 = 0;
  hWnd = 0;
  qword_1801099F8 = 0;
  hHandle = 0;
  memset_0(&g_aNULLs, 0, 0x88u);
  DisableThreadLibraryCalls(a2);
  if ( (int)CTelemetryHelper::Register((CTelemetryHelper *)&g_Telemetry) >= 0 )
    byte_180108368 = 1;
  McGenEventRegister_EtwEventRegister();
  v18 = GetProcessHeap();
  v19 = (WCHAR *)HeapAlloc(v18, 0, 0x208u);
  if ( v19 )
  {
    v20 = 260;
    while ( 1 )
    {
      if ( v20 >= 2 )
      {
        ModuleFileNameW = GetModuleFileNameW(0, v19, v20 - 2);
        v22 = ModuleFileNameW;
        LODWORD(qword_180109B70) = ModuleFileNameW;
        if ( ModuleFileNameW != v20 - 2 )
          break;
      }
      v20 += 260;
      v37 = GetProcessHeap();
      v38 = (WCHAR *)HeapReAlloc(v37, 0, v19, 2LL * v20);
      if ( !v38 )
      {
LABEL_45:
        v36 = GetProcessHeap();
        HeapFree(v36, 0, v19);
        return 0;
      }
      v19 = v38;
    }
    if ( ModuleFileNameW )
    {
      do
      {
        if ( v19[v22] == 92 )
          break;
        v23 = v22-- == 1;
        LODWORD(qword_180109B70) = v22;
      }
      while ( !v23 );
    }
    v24 = v22 + 1;
    LODWORD(qword_180109B70) = v24;
    v19[v24] = 0;
    v25 = qword_180109B70 + 1;
    LODWORD(qword_180109B70) = qword_180109B70 + 1;
    while ( 1 )
    {
      if ( v20 - v25 >= 2 )
      {
        v26 = v25;
        v27 = v20 - v25 - 2;
        v28 = GetModuleFileNameW(a2, &v19[v25], v27);
        v29 = v28;
        HIDWORD(qword_180109B70) = v28;
        if ( v28 != v27 )
          break;
      }
      v20 += 260;
      v48 = GetProcessHeap();
      v49 = (WCHAR *)HeapReAlloc(v48, 0, v19, 2LL * v20);
      if ( !v49 )
        goto LABEL_45;
      v19 = v49;
      v25 = qword_180109B70;
    }
    if ( v28 )
    {
      do
      {
        if ( v19[v26 + v29] == 92 )
          break;
        v23 = v29-- == 1;
        HIDWORD(qword_180109B70) = v29;
      }
      while ( !v23 );
    }
    v8 = v29 + 1;
    HIDWORD(qword_180109B70) = v8;
    v19[v26 + v8] = 0;
    for ( i = ++HIDWORD(qword_180109B70); ; i = HIDWORD(qword_180109B70) )
    {
      v10 = v20 - i - qword_180109B70;
      if ( v10 >= 2 )
      {
        v11 = &v19[(unsigned int)(qword_180109B70 + i)];
        v12 = v10 - 2;
        SystemDirectoryW = GetSystemDirectoryW(v11, v12);
        LODWORD(qword_180109B78) = SystemDirectoryW;
        if ( SystemDirectoryW < v12 )
          break;
      }
      v20 += 260;
      v34 = GetProcessHeap();
      v35 = (WCHAR *)HeapReAlloc(v34, 0, v19, 2LL * v20);
      if ( !v35 )
        goto LABEL_45;
      v19 = v35;
    }
    if ( v11[SystemDirectoryW] || SystemDirectoryW <= 1 )
    {
      *v11 = 0;
      LODWORD(qword_180109B78) = 1;
      v16 = 1;
    }
    else
    {
      v14 = SystemDirectoryW - 1;
      LODWORD(qword_180109B78) = SystemDirectoryW - 1;
      if ( v11[v14] != 92 )
      {
        LODWORD(qword_180109B78) = SystemDirectoryW;
        v11[SystemDirectoryW] = 92;
        LODWORD(v14) = qword_180109B78;
      }
      v15 = (unsigned int)(v14 + 1);
      LODWORD(qword_180109B78) = v15;
      v11[v15] = 0;
      LODWORD(qword_180109B78) = qword_180109B78 + 1;
      v16 = qword_180109B78;
    }
    lpMem = v19;
    xmmword_180109B60 = &v19[(unsigned int)qword_180109B70];
    v17 = HIDWORD(qword_180109B70);
    *(&xmmword_180109B60 + 1) = &v19[(unsigned int)qword_180109B70 + (unsigned __int64)HIDWORD(qword_180109B70)];
    if ( (unsigned int)qword_180109B70 >= HIDWORD(qword_180109B70) )
      v17 = qword_180109B70;
    if ( v17 < v16 )
      v17 = v16;
    HIDWORD(qword_180109B78) = v17;
    if ( ATL::CAtlBaseModule::m_bInitFailed )
      return 0;
    return v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18001f5f4  push    rbx
0x18001f5f6  push    rbp
0x18001f5f7  push    rsi
0x18001f5f8  push    rdi
0x18001f5f9  push    r12
0x18001f5fb  push    r13
0x18001f5fd  push    r14
0x18001f5ff  push    r15
0x18001f601  sub     rsp, 38h
0x18001f605  mov     rbx, r9
0x18001f608  mov     r15, rdx
0x18001f60b  mov     eax, r8d
0x18001f60e  mov     esi, 1
0x18001f613  xor     r12d, r12d
0x18001f616  test    r8d, r8d
0x18001f619  jz      loc_18001F87F
0x18001f61f  cmp     eax, esi
0x18001f621  jz      loc_18001F740
0x18001f627  cmp     r8d, esi
0x18001f62a  jz      loc_18001F72B
0x18001f630  mov     eax, esi
0x18001f632  add     rsp, 38h
0x18001f636  pop     r15
0x18001f638  pop     r14
0x18001f63a  pop     r13
0x18001f63c  pop     r12
0x18001f63e  pop     rdi
0x18001f63f  pop     rsi
0x18001f640  pop     rbp
0x18001f641  pop     rbx
0x18001f642  retn
0x18001f643  add     ecx, esi
0x18001f645  mov     dword ptr cs:qword_180109B70+4, ecx
0x18001f64b  add     rcx, r14
0x18001f64e  mov     [rdi+rcx*2], r12w
0x18001f653  mov     eax, dword ptr cs:qword_180109B70+4
0x18001f659  add     eax, esi
0x18001f65b  mov     dword ptr cs:qword_180109B70+4, eax
0x18001f661  mov     ebx, ebp
0x18001f663  sub     ebx, eax
0x18001f665  mov     ecx, dword ptr cs:qword_180109B70
0x18001f66b  sub     ebx, ecx
0x18001f66d  cmp     ebx, 2
0x18001f670  jb      loc_18001F952
0x18001f676  add     eax, ecx
0x18001f678  lea     r14, [rdi+rax*2]
0x18001f67c  add     ebx, 0FFFFFFFEh
0x18001f67f  mov     edx, ebx; uSize
0x18001f681  mov     rcx, r14; lpBuffer
0x18001f684  call    cs:__imp_GetSystemDirectoryW
0x18001f68a  mov     edx, eax
0x18001f68c  mov     dword ptr cs:qword_180109B78, edx
0x18001f692  cmp     eax, ebx
0x18001f694  jnb     loc_18001F952
0x18001f69a  cmp     [r14+rdx*2], r12w
0x18001f69f  jnz     loc_18001F9CE
0x18001f6a5  cmp     edx, esi
0x18001f6a7  jbe     loc_18001F9CE
0x18001f6ad  lea     ecx, [rdx-1]
0x18001f6b0  mov     dword ptr cs:qword_180109B78, ecx
0x18001f6b6  cmp     [r14+rcx*2], r13w
0x18001f6bb  jz      short loc_18001F6CE
0x18001f6bd  mov     dword ptr cs:qword_180109B78, edx
0x18001f6c3  mov     [r14+rdx*2], r13w
0x18001f6c8  mov     ecx, dword ptr cs:qword_180109B78
0x18001f6ce  add     ecx, esi
0x18001f6d0  mov     dword ptr cs:qword_180109B78, ecx
0x18001f6d6  mov     [r14+rcx*2], r12w
0x18001f6db  mov     eax, dword ptr cs:qword_180109B78
0x18001f6e1  add     eax, esi
0x18001f6e3  mov     dword ptr cs:qword_180109B78, eax
0x18001f6e9  mov     r8d, eax
0x18001f6ec  mov     cs:lpMem, rdi
0x18001f6f3  mov     ecx, dword ptr cs:qword_180109B70
0x18001f6f9  lea     rax, [rdi+rcx*2]
0x18001f6fd  mov     qword ptr cs:xmmword_180109B60, rax
0x18001f704  mov     edx, dword ptr cs:qword_180109B70+4
0x18001f70a  lea     rax, [rcx+rdx]
0x18001f70e  lea     rax, [rdi+rax*2]
0x18001f712  mov     qword ptr cs:xmmword_180109B60+8, rax
0x18001f719  cmp     ecx, edx
0x18001f71b  cmovnb  edx, ecx
0x18001f71e  cmp     edx, r8d
0x18001f721  cmovb   edx, r8d
0x18001f725  mov     dword ptr cs:qword_180109B78+4, edx
0x18001f72b  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, r12b; bool ATL::CAtlBaseModule::m_bInitFailed
0x18001f732  jz      loc_18001F630
0x18001f738  mov     esi, r12d
0x18001f73b  jmp     loc_18001F630
0x18001f740  mov     cs:byte_180109B40, r12b
0x18001f747  mov     cs:hWnd, r12
0x18001f74e  mov     cs:qword_1801099F8, r12
0x18001f755  mov     cs:hHandle, r12
0x18001f75c  xor     edx, edx; Val
0x18001f75e  mov     r8d, 88h; Size
0x18001f764  lea     rcx, ?g_aNULLs@@3PAPEAXA; void *
0x18001f76b  call    memset_0
0x18001f770  mov     rcx, r15; hLibModule
0x18001f773  call    cs:__imp_DisableThreadLibraryCalls
0x18001f779  lea     rcx, ?g_Telemetry@@3VCDXGITelemetryHelper@@A; this
0x18001f780  call    ?Register@CTelemetryHelper@@UEAAJXZ; CTelemetryHelper::Register(void)
0x18001f785  test    eax, eax
0x18001f787  js      short loc_18001F790
0x18001f789  mov     cs:byte_180108368, sil
0x18001f790  call    McGenEventRegister_EtwEventRegister
0x18001f795  call    cs:__imp_GetProcessHeap
0x18001f79b  mov     rcx, rax; hHeap
0x18001f79e  xor     edx, edx; dwFlags
0x18001f7a0  mov     r8d, 208h; dwBytes
0x18001f7a6  call    cs:__imp_HeapAlloc
0x18001f7ac  mov     rdi, rax
0x18001f7af  test    rax, rax
0x18001f7b2  jz      loc_18001F98D
0x18001f7b8  mov     r14d, 104h
0x18001f7be  mov     ebp, r14d
0x18001f7c1  cmp     ebp, 2
0x18001f7c4  jb      loc_18001F994
0x18001f7ca  lea     ebx, [rbp-2]
0x18001f7cd  mov     r8d, ebx; nSize
0x18001f7d0  mov     rdx, rdi; lpFilename
0x18001f7d3  xor     ecx, ecx; hModule
0x18001f7d5  call    cs:__imp_GetModuleFileNameW
0x18001f7db  mov     ecx, eax
0x18001f7dd  mov     dword ptr cs:qword_180109B70, eax
0x18001f7e3  cmp     eax, ebx
0x18001f7e5  jz      loc_18001F994
0x18001f7eb  mov     r13d, 5Ch ; '\'
0x18001f7f1  test    eax, eax
0x18001f7f3  jz      short loc_18001F809
0x18001f7f5  mov     eax, ecx
0x18001f7f7  cmp     [rdi+rax*2], r13w
0x18001f7fc  jz      short loc_18001F809
0x18001f7fe  add     ecx, 0FFFFFFFFh
0x18001f801  mov     dword ptr cs:qword_180109B70, ecx
0x18001f807  jnz     short loc_18001F7F5
0x18001f809  add     ecx, esi
0x18001f80b  mov     dword ptr cs:qword_180109B70, ecx
0x18001f811  mov     [rdi+rcx*2], r12w
0x18001f816  mov     eax, dword ptr cs:qword_180109B70
0x18001f81c  add     eax, esi
0x18001f81e  mov     dword ptr cs:qword_180109B70, eax
0x18001f824  mov     ebx, ebp
0x18001f826  sub     ebx, eax
0x18001f828  cmp     ebx, 2
0x18001f82b  jb      loc_18001FA46
0x18001f831  mov     r14d, eax
0x18001f834  add     ebx, 0FFFFFFFEh
0x18001f837  lea     rdx, [rdi+r14*2]; lpFilename
0x18001f83b  mov     r8d, ebx; nSize
0x18001f83e  mov     rcx, r15; hModule
0x18001f841  call    cs:__imp_GetModuleFileNameW
0x18001f847  mov     ecx, eax
0x18001f849  mov     dword ptr cs:qword_180109B70+4, eax
0x18001f84f  cmp     eax, ebx
0x18001f851  jz      loc_18001FA40
0x18001f857  test    eax, eax
0x18001f859  jz      loc_18001F643
0x18001f85f  mov     eax, ecx
0x18001f861  add     rax, r14
0x18001f864  cmp     [rdi+rax*2], r13w
0x18001f869  jz      loc_18001F643
0x18001f86f  add     ecx, 0FFFFFFFFh
0x18001f872  mov     dword ptr cs:qword_180109B70+4, ecx
0x18001f878  jnz     short loc_18001F85F
0x18001f87a  jmp     loc_18001F643
0x18001f87f  mov     rcx, cs:off_180108330
0x18001f886  call    TraceLoggingUnregister_EtwEventUnregister
0x18001f88b  mov     rcx, cs:?g_pDebugPrivate@@3PEAUIDXGIDebugPrivate@@EA; IDXGIDebugPrivate * g_pDebugPrivate
0x18001f892  test    rcx, rcx
0x18001f895  jnz     loc_18001FA7C
0x18001f89b  call    McGenEventUnregister_EtwEventUnregister
0x18001f8a0  lea     rcx, qword_180109AB0; this
0x18001f8a7  call    ?DestroyMutex@CDXGIMutexInSeparateThread@@QEAAXXZ; CDXGIMutexInSeparateThread::DestroyMutex(void)
0x18001f8ac  lea     rcx, qword_180109AF8; this
0x18001f8b3  call    ?DestroyMutex@CDXGIMutexInSeparateThread@@QEAAXXZ; CDXGIMutexInSeparateThread::DestroyMutex(void)
0x18001f8b8  mov     rbx, cs:lpMem
0x18001f8bf  test    rbx, rbx
0x18001f8c2  jz      short loc_18001F8D8
0x18001f8c4  call    cs:__imp_GetProcessHeap
0x18001f8ca  mov     r8, rbx; lpMem
0x18001f8cd  xor     edx, edx; dwFlags
0x18001f8cf  mov     rcx, rax; hHeap
0x18001f8d2  call    cs:__imp_HeapFree
0x18001f8d8  mov     cs:Size, r12
0x18001f8df  lea     rax, ?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x18001f8e6  cmp     cs:qword_180109990, 0Fh
0x18001f8ee  cmova   rax, cs:?g_CompatStringCache@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_CompatStringCache
0x18001f8f6  mov     [rax], r12b
0x18001f8f9  lea     rcx, stru_180109A28; this
0x18001f900  call    ?DeInit@StereoModuleData@@QEAAXXZ; StereoModuleData::DeInit(void)
0x18001f905  mov     rcx, cs:qword_180109A48
0x18001f90c  lea     rbx, aRtlunsubscribe_0; "RtlUnsubscribeWnfNotificationWaitForCom"...
0x18001f913  test    rcx, rcx
0x18001f916  jnz     loc_18001F9E0
0x18001f91c  mov     rcx, qword ptr cs:xmmword_180109A10+8
0x18001f923  test    rcx, rcx
0x18001f926  jnz     loc_18001FA00
0x18001f92c  mov     rcx, qword ptr cs:stru_180109A50.Data
0x18001f933  test    rcx, rcx
0x18001f936  jnz     loc_18001FA20
0x18001f93c  lea     rcx, byte_180109A60; this
0x18001f943  call    ?DeInit@AdapterEnumModuleData@@QEAAXXZ; AdapterEnumModuleData::DeInit(void)
0x18001f948  call    ?ClearAllDetours@CModule@@QEAAJXZ; CModule::ClearAllDetours(void)
0x18001f94d  jmp     loc_18001F630
0x18001f952  add     ebp, 104h
0x18001f958  mov     ebx, ebp
0x18001f95a  add     rbx, rbx
0x18001f95d  call    cs:__imp_GetProcessHeap
0x18001f963  mov     rcx, rax; hHeap
0x18001f966  mov     r9, rbx; dwBytes
0x18001f969  mov     r8, rdi; lpMem
0x18001f96c  xor     edx, edx; dwFlags
0x18001f96e  call    cs:__imp_HeapReAlloc
0x18001f974  test    rax, rax
0x18001f977  jnz     short loc_18001F9C0
0x18001f979  call    cs:__imp_GetProcessHeap
0x18001f97f  mov     rcx, rax; hHeap
0x18001f982  mov     r8, rdi; lpMem
0x18001f985  xor     edx, edx; dwFlags
0x18001f987  call    cs:__imp_HeapFree
0x18001f98d  xor     eax, eax
0x18001f98f  jmp     loc_18001F632
0x18001f994  add     ebp, r14d
0x18001f997  mov     ebx, ebp
0x18001f999  add     rbx, rbx
0x18001f99c  call    cs:__imp_GetProcessHeap
0x18001f9a2  mov     rcx, rax; hHeap
0x18001f9a5  mov     r9, rbx; dwBytes
0x18001f9a8  mov     r8, rdi; lpMem
0x18001f9ab  xor     edx, edx; dwFlags
0x18001f9ad  call    cs:__imp_HeapReAlloc
0x18001f9b3  test    rax, rax
0x18001f9b6  jz      short loc_18001F979
0x18001f9b8  mov     rdi, rax
0x18001f9bb  jmp     loc_18001F7C1
0x18001f9c0  mov     rdi, rax
0x18001f9c3  mov     eax, dword ptr cs:qword_180109B70+4
0x18001f9c9  jmp     loc_18001F661
0x18001f9ce  mov     [r14], r12w
0x18001f9d2  mov     dword ptr cs:qword_180109B78, esi
0x18001f9d8  mov     r8d, esi
0x18001f9db  jmp     loc_18001F6EC
0x18001f9e0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001f9e6  test    eax, eax
0x18001f9e8  jns     short loc_18001F9F4
0x18001f9ea  mov     r8, rbx; char *
0x18001f9ed  mov     edx, eax; unsigned int
0x18001f9ef  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001f9f4  mov     cs:qword_180109A48, r12
0x18001f9fb  jmp     loc_18001F91C
0x18001fa00  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fa06  test    eax, eax
0x18001fa08  jns     short loc_18001FA14
0x18001fa0a  mov     r8, rbx; char *
0x18001fa0d  mov     edx, eax; unsigned int
0x18001fa0f  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fa14  mov     qword ptr cs:xmmword_180109A10+8, r12
0x18001fa1b  jmp     loc_18001F92C
0x18001fa20  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18001fa26  test    eax, eax
0x18001fa28  jns     short loc_18001FA34
0x18001fa2a  mov     r8, rbx; char *
0x18001fa2d  mov     edx, eax; unsigned int
0x18001fa2f  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001fa34  mov     qword ptr cs:stru_180109A50.Data, r12
0x18001fa3b  jmp     loc_18001F93C
0x18001fa40  mov     r14d, 104h
0x18001fa46  add     ebp, r14d
0x18001fa49  mov     ebx, ebp
0x18001fa4b  add     rbx, rbx
0x18001fa4e  call    cs:__imp_GetProcessHeap
0x18001fa54  mov     rcx, rax; hHeap
0x18001fa57  mov     r9, rbx; dwBytes
0x18001fa5a  mov     r8, rdi; lpMem
0x18001fa5d  xor     edx, edx; dwFlags
0x18001fa5f  call    cs:__imp_HeapReAlloc
0x18001fa65  test    rax, rax
0x18001fa68  jz      loc_18001F979
0x18001fa6e  mov     rdi, rax
0x18001fa71  mov     eax, dword ptr cs:qword_180109B70
0x18001fa77  jmp     loc_18001F824
0x18001fa7c  movups  xmm0, xmmword ptr cs:DXGI_DEBUG_DXGI.Data1
0x18001fa83  movdqu  [rsp+78h+var_58], xmm0
0x18001fa89  mov     rax, [rcx]
0x18001fa8c  mov     r8d, r12d
0x18001fa8f  test    rbx, rbx
0x18001fa92  setnz   r8b
0x18001fa96  lea     rdx, [rsp+78h+var_58]
0x18001fa9b  mov     rax, [rax+50h]
0x18001fa9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faa4  jmp     loc_18001F89B
```
