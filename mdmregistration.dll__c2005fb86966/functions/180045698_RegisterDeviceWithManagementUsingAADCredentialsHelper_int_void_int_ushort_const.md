# RegisterDeviceWithManagementUsingAADCredentialsHelper(int,void *,int,ushort const *)

- ea: `0x180045698`
- end: `0x180045ab2`
- name: `?RegisterDeviceWithManagementUsingAADCredentialsHelper@@YAJHPEAXHPEBG@Z`
- size: `1050`
- prototype: `__int64 __fastcall(int, void *, int, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800135b0`
- `0x1800135d0`
- `0x1800135f0`

## callees

- `0x180007e5c`
- `0x18000b0f4`
- `0x18000cc00`
- `0x18002e6f8`
- `0x180041410`
- `0x18004178c`
- `0x1800418cc`
- `0x1800454d0`
- `0x180045530`
- `0x180045698`
- `0x180045ab8`
- `0x180046944`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180045905`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180045905`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800458eb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800458eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180045797`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180045797`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800457e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045a09`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800457e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045a09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800459d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800458cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800459d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800459c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800458b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800459c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045700`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045827`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045a46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004576d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045806`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004576d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045806`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045a29`
- `DMCmnUtils!DmInvalidateAadUserToken` at `0x18004598c`
- `DMCmnUtils!DmInvalidateAadUserToken` at `0x18004598c`
- `DMCmnUtils!DmInvalidateAadDeviceToken` at `0x180045966`
- `DMCmnUtils!DmInvalidateAadDeviceToken` at `0x180045966`
- `dsreg!DsrFreeJoinInfo` at `0x18004597e`
- `dsreg!DsrFreeJoinInfo` at `0x18004597e`
- `dsreg!DsrGetJoinInfo` at `0x18004584b`
- `dsreg!DsrGetJoinInfo` at `0x18004584b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RegisterDeviceWithManagementUsingAADCredentialsHelper(
        int a1,
        void *a2,
        int a3,
        unsigned __int16 *a4)
{
  void *v4; // r12
  int SystemSecurityDescriptor; // eax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // ebx
  int v12; // eax
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v15; // rsi
  DWORD v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned __int64 v25; // r8
  wchar_t *v26; // rbx
  const unsigned __int16 *v27; // rdx
  wchar_t **process_heap_string_nothrow; // rax
  wchar_t *v29; // r15
  void *v30; // r14
  HANDLE ProcessHeap; // rax
  wchar_t *v32; // rax
  wchar_t *v33; // rax
  int v34; // r15d
  unsigned int v35; // r14d
  int v36; // eax
  int v37; // r12d
  CEnrollmentLogger *Logger; // rax
  bool v39; // sf
  HANDLE v40; // rax
  CEnrollmentLogger *v41; // rax
  unsigned int v42; // r8d
  const char *v43; // r9
  unsigned int v44; // r8d
  const char *v45; // r9
  int lpMutexAttributes; // [rsp+28h] [rbp-49h]
  int lpMutexAttributesa; // [rsp+28h] [rbp-49h]
  struct _DSREG_JOIN_INFO *v48; // [rsp+38h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-21h] BYREF
  wchar_t *v52; // [rsp+58h] [rbp-19h] BYREF
  void *v53; // [rsp+60h] [rbp-11h]
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+68h] [rbp-9h] BYREF
  void *v55; // [rsp+80h] [rbp+Fh]
  struct _DSREG_JOIN_INFO **v56; // [rsp+88h] [rbp+17h]
  char v57; // [rsp+90h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]

  v4 = a2;
  hMem = 0;
  SystemSecurityDescriptor = anonymous_namespace_::GetSystemSecurityDescriptor(&hMem);
  v10 = SystemSecurityDescriptor;
  if ( SystemSecurityDescriptor < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)SystemSecurityDescriptor,
      lpMutexAttributes);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return v10;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = hMem;
  hObject = 0;
  v12 = _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
          (int)&hObject,
          v7,
          v8,
          v9,
          &MutexAttributes);
  v10 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\aadhelper\\aadhelper.cpp",
      (const char *)(unsigned int)v12,
      lpMutexAttributesa);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    goto LABEL_3;
  }
  v15 = hObject;
  v16 = WaitForSingleObjectEx(hObject, 0xFFFFFFFF, 0);
  if ( v16 == 258 )
  {
    v20 = 0;
  }
  else
  {
    if ( (v16 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v17, v18, v19);
    v20 = v15;
  }
  v53 = v20;
  v55 = v20;
  LODWORD(lpMem) = 0;
  if ( (int)anonymous_namespace_::IsAlreadyEnrolled(&lpMem) >= 0 && (_DWORD)lpMem )
  {
    if ( v20 && !ReleaseMutex(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v21, v22);
    if ( v15 && !CloseHandle(v15) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
    if ( hMem )
      LocalFree(hMem);
    return 2149056522LL;
  }
  v48 = 0;
  if ( !(unsigned int)DsrGetJoinInfo(0, &v48) )
  {
    v56 = &v48;
    v57 = 1;
    v26 = 0;
    v52 = 0;
    v27 = (const unsigned __int16 *)*((_QWORD *)v48 + 7);
    if ( v27 && *v27 )
    {
      process_heap_string_nothrow = (wchar_t **)wil::make_process_heap_string_nothrow((wil *)&lpMem, v27, v25);
      v29 = 0;
      if ( &v52 != process_heap_string_nothrow )
      {
        v52 = *process_heap_string_nothrow;
        v26 = v52;
        *process_heap_string_nothrow = 0;
        v29 = v26;
      }
      v30 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v30);
      }
      if ( !v29 )
      {
        v35 = 14;
LABEL_40:
        DsrFreeJoinInfo(v48);
        goto LABEL_46;
      }
      v32 = wcsstr(v26, L"https://");
      if ( v32 )
      {
        v33 = wcschr(v32 + 9, 0x2Fu);
        if ( v33 )
          v33[1] = 0;
      }
    }
    v34 = 0;
    do
    {
      v35 = RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(v26, v48, a1, v4, a3, a4);
      if ( v35 != -2145910782 )
        break;
      if ( (unsigned int)++v34 >= 2 )
        break;
      v36 = a1
          ? DmInvalidateAadDeviceToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v26, 0)
          : DmInvalidateAadUserToken(L"de50c81f-5f80-4771-b66b-cebd28ccdfc1", v26, 0);
      v37 = v36;
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(Logger, v37);
      v39 = v37 < 0;
      v4 = a2;
    }
    while ( !v39 );
    v20 = v53;
    v15 = hObject;
    if ( v26 )
    {
      v40 = GetProcessHeap();
      HeapFree(v40, 0, v26);
    }
    goto LABEL_40;
  }
  v35 = -2147024760;
LABEL_46:
  v41 = CEnrollmentLogger::GetLogger();
  CEnrollmentLogger::LogAutoEnrollAttempt(v41, v35, a1);
  if ( v20 && !ReleaseMutex(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v42, v43);
  if ( v15 && !CloseHandle(v15) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
  if ( hMem )
    LocalFree(hMem);
  return v35;
}

```

## disassembly

```asm
0x180045698  mov     rax, rsp
0x18004569b  mov     [rax+8], rbx
0x18004569f  mov     [rax+20h], r9
0x1800456a3  mov     [rax+18h], r8d
0x1800456a7  mov     [rax+10h], rdx
0x1800456ab  push    rbp
0x1800456ac  push    rsi
0x1800456ad  push    rdi
0x1800456ae  push    r12
0x1800456b0  push    r13
0x1800456b2  push    r14
0x1800456b4  push    r15
0x1800456b6  lea     rbp, [rax-5Fh]
0x1800456ba  sub     rsp, 90h
0x1800456c1  mov     r12, rdx
0x1800456c4  mov     r13d, ecx
0x1800456c7  mov     [rbp+57h+hMem], 0
0x1800456cf  lea     rcx, [rbp+57h+hMem]; SecurityDescriptor
0x1800456d3  call    _anonymous_namespace___GetSystemSecurityDescriptor
0x1800456d8  mov     ebx, eax
0x1800456da  test    eax, eax
0x1800456dc  jns     short loc_180045713
0x1800456de  mov     rcx, [rbp+5Fh]; this
0x1800456e2  mov     r9d, eax; char *
0x1800456e5  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800456ec  mov     edx, 1D9h; void *
0x1800456f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800456f6  nop
0x1800456f7  mov     rcx, [rbp+57h+hMem]; hMem
0x1800456fb  test    rcx, rcx
0x1800456fe  jz      short loc_18004570C
0x180045700  call    cs:__imp_LocalFree
0x180045707  nop     dword ptr [rax+rax+00h]
0x18004570c  mov     eax, ebx
0x18004570e  jmp     loc_180045A55
0x180045713  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x18004571b  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], 0
0x180045723  mov     rax, [rbp+57h+hMem]
0x180045727  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x18004572b  mov     [rbp+57h+hObject], 0
0x180045733  lea     rax, [rbp+57h+MutexAttributes]
0x180045737  mov     qword ptr [rsp+0C0h+lpMutexAttributes], rax; int
0x18004573c  lea     rcx, [rbp+57h+hObject]; int
0x180045740  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180045745  mov     ebx, eax
0x180045747  test    eax, eax
0x180045749  jns     short loc_18004578A
0x18004574b  mov     rcx, [rbp+5Fh]; this
0x18004574f  mov     r9d, eax; char *
0x180045752  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045759  mov     edx, 1E0h; void *
0x18004575e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045763  nop
0x180045764  mov     rcx, [rbp+57h+hObject]; hObject
0x180045768  test    rcx, rcx
0x18004576b  jz      short loc_1800456F7
0x18004576d  call    cs:__imp_CloseHandle
0x180045774  nop     dword ptr [rax+rax+00h]
0x180045779  mov     rcx, [rbp+5Fh]; this
0x18004577d  test    eax, eax
0x18004577f  jz      loc_180045A7C
0x180045785  jmp     loc_1800456F7
0x18004578a  mov     rsi, [rbp+57h+hObject]
0x18004578e  xor     r8d, r8d; bAlertable
0x180045791  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180045794  mov     rcx, rsi; hHandle
0x180045797  call    cs:__imp_WaitForSingleObjectEx
0x18004579e  nop     dword ptr [rax+rax+00h]
0x1800457a3  cmp     eax, 102h
0x1800457a8  jz      short loc_1800457BA
0x1800457aa  test    eax, 0FFFFFF7Fh
0x1800457af  jnz     loc_180045A87
0x1800457b5  mov     rdi, rsi
0x1800457b8  jmp     short loc_1800457BC
0x1800457ba  xor     edi, edi
0x1800457bc  mov     [rbp+57h+var_68], rdi
0x1800457c0  mov     [rbp+57h+var_48], rdi
0x1800457c4  mov     dword ptr [rbp+57h+lpMem], 0
0x1800457cb  lea     rcx, [rbp+57h+lpMem]
0x1800457cf  call    _anonymous_namespace___IsAlreadyEnrolled
0x1800457d4  test    eax, eax
0x1800457d6  js      short loc_18004583D
0x1800457d8  cmp     dword ptr [rbp+57h+lpMem], 0
0x1800457dc  jz      short loc_18004583D
0x1800457de  test    rdi, rdi
0x1800457e1  jz      short loc_1800457FE
0x1800457e3  mov     rcx, rdi; hMutex
0x1800457e6  call    cs:__imp_ReleaseMutex
0x1800457ed  nop     dword ptr [rax+rax+00h]
0x1800457f2  mov     rcx, [rbp+5Fh]; this
0x1800457f6  test    eax, eax
0x1800457f8  jz      loc_180045A91
0x1800457fe  test    rsi, rsi
0x180045801  jz      short loc_18004581E
0x180045803  mov     rcx, rsi; hObject
0x180045806  call    cs:__imp_CloseHandle
0x18004580d  nop     dword ptr [rax+rax+00h]
0x180045812  mov     rcx, [rbp+5Fh]; this
0x180045816  test    eax, eax
0x180045818  jz      loc_180045A9C
0x18004581e  mov     rcx, [rbp+57h+hMem]; hMem
0x180045822  test    rcx, rcx
0x180045825  jz      short loc_180045833
0x180045827  call    cs:__imp_LocalFree
0x18004582e  nop     dword ptr [rax+rax+00h]
0x180045833  mov     eax, 8018000Ah
0x180045838  jmp     loc_180045A55
0x18004583d  mov     [rbp+57h+var_90], 0
0x180045845  lea     rdx, [rbp+57h+var_90]
0x180045849  xor     ecx, ecx
0x18004584b  call    cs:__imp_DsrGetJoinInfo
0x180045852  nop     dword ptr [rax+rax+00h]
0x180045857  test    eax, eax
0x180045859  jnz     loc_1800459E7
0x18004585f  lea     rax, [rbp+57h+var_90]
0x180045863  mov     [rbp+57h+var_40], rax
0x180045867  mov     [rbp+57h+var_38], 1
0x18004586b  xor     ebx, ebx
0x18004586d  mov     [rbp+57h+var_70], rbx
0x180045871  mov     rax, [rbp+57h+var_90]
0x180045875  mov     rdx, [rax+38h]; unsigned __int16 *
0x180045879  test    rdx, rdx
0x18004587c  jz      loc_18004591C
0x180045882  xor     eax, eax
0x180045884  cmp     ax, [rdx]
0x180045887  jz      loc_18004591C
0x18004588d  lea     rcx, [rbp+57h+lpMem]; this
0x180045891  call    ?make_process_heap_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_process_heap_string_nothrow(ushort const *,unsigned __int64)
0x180045896  xor     r15d, r15d
0x180045899  lea     rcx, [rbp+57h+var_70]
0x18004589d  cmp     rcx, rax
0x1800458a0  jz      short loc_1800458AF
0x1800458a2  mov     rbx, [rax]
0x1800458a5  mov     [rbp+57h+var_70], rbx
0x1800458a9  mov     [rax], r15
0x1800458ac  mov     r15, rbx
0x1800458af  mov     r14, [rbp+57h+lpMem]
0x1800458b3  test    r14, r14
0x1800458b6  jz      short loc_1800458D8
0x1800458b8  call    cs:__imp_GetProcessHeap
0x1800458bf  nop     dword ptr [rax+rax+00h]
0x1800458c4  mov     rcx, rax; hHeap
0x1800458c7  mov     r8, r14; lpMem
0x1800458ca  xor     edx, edx; dwFlags
0x1800458cc  call    cs:__imp_HeapFree
0x1800458d3  nop     dword ptr [rax+rax+00h]
0x1800458d8  test    r15, r15
0x1800458db  jz      loc_180045974
0x1800458e1  lea     rdx, aHttps; "https://"
0x1800458e8  mov     rcx, rbx; Str
0x1800458eb  call    cs:__imp_wcsstr
0x1800458f2  nop     dword ptr [rax+rax+00h]
0x1800458f7  test    rax, rax
0x1800458fa  jz      short loc_18004591C
0x1800458fc  mov     edx, 2Fh ; '/'; Ch
0x180045901  lea     rcx, [rax+12h]; Str
0x180045905  call    cs:__imp_wcschr
0x18004590c  nop     dword ptr [rax+rax+00h]
0x180045911  test    rax, rax
0x180045914  jz      short loc_18004591C
0x180045916  xor     ecx, ecx
0x180045918  mov     [rax+2], cx
0x18004591c  xor     r15d, r15d
0x18004591f  mov     rsi, [rbp+57h+arg_18]
0x180045923  mov     edi, [rbp+57h+arg_10]
0x180045926  mov     qword ptr [rsp+0C0h+lpMutexAttributes+8], rsi; unsigned __int16 *
0x18004592b  mov     [rsp+0C0h+lpMutexAttributes], edi; int
0x18004592f  mov     r9, r12; void *
0x180045932  mov     r8d, r13d; int
0x180045935  mov     rdx, [rbp+57h+var_90]; struct _DSREG_JOIN_INFO *
0x180045939  mov     rcx, rbx; unsigned __int16 *
0x18004593c  call    ?RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal@@YAJPEBGPEAU_DSREG_JOIN_INFO@@HPEAXH0@Z; RegisterDeviceWithManagementUsingAADCredentialsHelper_Internal(ushort const *,_DSREG_JOIN_INFO *,int,void *,int,ushort const *)
0x180045941  mov     r14d, eax
0x180045944  cmp     eax, 80180002h
0x180045949  jnz     short loc_1800459B8
0x18004594b  inc     r15d
0x18004594e  cmp     r15d, 2
0x180045952  jnb     short loc_1800459B8
0x180045954  xor     r8d, r8d
0x180045957  mov     rdx, rbx
0x18004595a  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180045961  test    r13d, r13d
0x180045964  jz      short loc_18004598C
0x180045966  call    cs:__imp_?DmInvalidateAadDeviceToken@@YAJPEBG00@Z; DmInvalidateAadDeviceToken(ushort const *,ushort const *,ushort const *)
0x18004596d  nop     dword ptr [rax+rax+00h]
0x180045972  jmp     short loc_180045998
0x180045974  mov     r14d, 0Eh
0x18004597a  mov     rcx, [rbp+57h+var_90]
0x18004597e  call    cs:__imp_DsrFreeJoinInfo
0x180045985  nop     dword ptr [rax+rax+00h]
0x18004598a  jmp     short loc_1800459ED
0x18004598c  call    cs:__imp_?DmInvalidateAadUserToken@@YAJPEBG00@Z; DmInvalidateAadUserToken(ushort const *,ushort const *,ushort const *)
0x180045993  nop     dword ptr [rax+rax+00h]
0x180045998  mov     r12d, eax
0x18004599b  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800459a0  mov     edx, r12d; int
0x1800459a3  mov     rcx, rax; this
0x1800459a6  call    ?LogAutoEnrollAttemptRetryOnFailure@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogAutoEnrollAttemptRetryOnFailure(long)
0x1800459ab  test    r12d, r12d
0x1800459ae  mov     r12, [rbp+57h+arg_8]
0x1800459b2  jns     loc_180045926
0x1800459b8  test    rbx, rbx
0x1800459bb  mov     rdi, [rbp+57h+var_68]
0x1800459bf  mov     rsi, [rbp+57h+hObject]
0x1800459c3  jz      short loc_18004597A
0x1800459c5  call    cs:__imp_GetProcessHeap
0x1800459cc  nop     dword ptr [rax+rax+00h]
0x1800459d1  mov     rcx, rax; hHeap
0x1800459d4  mov     r8, rbx; lpMem
0x1800459d7  xor     edx, edx; dwFlags
0x1800459d9  call    cs:__imp_HeapFree
0x1800459e0  nop     dword ptr [rax+rax+00h]
0x1800459e5  jmp     short loc_18004597A
0x1800459e7  mov     r14d, 80070088h
0x1800459ed  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x1800459f2  mov     r8d, r13d; int
0x1800459f5  mov     edx, r14d; int
0x1800459f8  mov     rcx, rax; this
0x1800459fb  call    ?LogAutoEnrollAttempt@CEnrollmentLogger@@QEAAXJH@Z; CEnrollmentLogger::LogAutoEnrollAttempt(long,int)
0x180045a00  nop
0x180045a01  test    rdi, rdi
0x180045a04  jz      short loc_180045A21
0x180045a06  mov     rcx, rdi; hMutex
0x180045a09  call    cs:__imp_ReleaseMutex
0x180045a10  nop     dword ptr [rax+rax+00h]
0x180045a15  mov     rcx, [rbp+5Fh]; this
0x180045a19  test    eax, eax
0x180045a1b  jz      loc_180045AA7
0x180045a21  test    rsi, rsi
0x180045a24  jz      short loc_180045A3D
0x180045a26  mov     rcx, rsi; hObject
0x180045a29  call    cs:__imp_CloseHandle
0x180045a30  nop     dword ptr [rax+rax+00h]
0x180045a35  mov     rcx, [rbp+5Fh]; this
0x180045a39  test    eax, eax
0x180045a3b  jz      short loc_180045A71
0x180045a3d  mov     rcx, [rbp+57h+hMem]; hMem
0x180045a41  test    rcx, rcx
0x180045a44  jz      short loc_180045A52
0x180045a46  call    cs:__imp_LocalFree
0x180045a4d  nop     dword ptr [rax+rax+00h]
0x180045a52  mov     eax, r14d
0x180045a55  mov     rbx, [rsp+0C0h+arg_0]
0x180045a5d  add     rsp, 90h
0x180045a64  pop     r15
0x180045a66  pop     r14
0x180045a68  pop     r13
0x180045a6a  pop     r12
0x180045a6c  pop     rdi
0x180045a6d  pop     rsi
0x180045a6e  pop     rbp
0x180045a6f  retn
0x180045a71  mov     edx, 0A0Bh; void *
0x180045a76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180045a7c  mov     edx, 0A0Bh; void *
0x180045a81  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180045a87  mov     rcx, [rbp+5Fh]; this
0x180045a8b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180045a91  mov     edx, 0A15h; void *
0x180045a96  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180045a9c  mov     edx, 0A0Bh; void *
0x180045aa1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180045aa7  mov     edx, 0A15h; void *
0x180045aac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
