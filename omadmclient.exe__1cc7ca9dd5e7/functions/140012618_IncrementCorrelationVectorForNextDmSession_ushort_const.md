# IncrementCorrelationVectorForNextDmSession(ushort const *)

- ea: `0x140012618`
- end: `0x140012b4b`
- name: `?IncrementCorrelationVectorForNextDmSession@@YAJPEBG@Z`
- size: `1331`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14000d860`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x14000b0f4`
- `0x140012530`
- `0x140012618`
- `0x140013068`
- `0x140013090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012680`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001272f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012680`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001272f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012a59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140012a59`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400126f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400127a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400126f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400127a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400126b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001276a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012b1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400126b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001276a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012b1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400128a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012945`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012add`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012821`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012874`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400128a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012945`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012add`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400128bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400128bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400129ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012af1`
- `DMCmnUtils!MBToUnicode` at `0x14001291b`
- `DMCmnUtils!MBToUnicode` at `0x14001291b`
- `DMCmnUtils!UnicodeToMB` at `0x1400127f7`
- `DMCmnUtils!UnicodeToMB` at `0x1400127f7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140012647`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140012647`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall IncrementCorrelationVectorForNextDmSession(const unsigned __int16 *a1)
{
  char IsStateSeparationEnabled; // al
  unsigned int v2; // eax
  __int64 v3; // rdx
  int v4; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  bool v8; // dl
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  void *v11; // rdi
  HANDLE v12; // rax
  char *v13; // rdi
  HANDLE v14; // rax
  struct TraceLoggingCorrelationVector *v15; // rbx
  int v16; // edi
  void *v17; // rsi
  HANDLE v18; // rax
  void *v19; // rbx
  bool v20; // zf
  HANDLE v21; // rax
  char *v22; // rbx
  HANDLE v23; // rax
  unsigned int v24; // eax
  void *v25; // rbx
  HANDLE v26; // rax
  char *v27; // rbx
  HANDLE v28; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  char *Str; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v35; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-B0h] BYREF
  void **p_Str; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v38; // [rsp+60h] [rbp-A0h] BYREF
  char v39; // [rsp+68h] [rbp-98h]
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD lpcbData; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v42; // [rsp+78h] [rbp-88h] BYREF
  struct TraceLoggingCorrelationVector *v43; // [rsp+80h] [rbp-80h]
  WCHAR Data[40]; // [rsp+90h] [rbp-70h] BYREF
  char v45[144]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v46[136]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths + (IsStateSeparationEnabled != 0 ? 8 : 0)),
         0,
         0x20019u,
         &hKey);
  if ( v2 )
  {
    v3 = 208;
LABEL_3:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v3,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v2,
           phkResult);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v4;
  }
  cbData = 78;
  v2 = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, &cbData);
  if ( v2 )
  {
    v3 = 219;
    goto LABEL_3;
  }
  v35 = 0;
  v6 = RegOpenKeyExW(hKey, Data, 0, 0x2001Fu, &v35);
  if ( v6 )
  {
    v7 = 227;
LABEL_11:
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v7,
           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
           (const char *)v6,
           phkResulta);
LABEL_12:
    if ( v35 )
      RegCloseKey(v35);
    goto LABEL_4;
  }
  lpcbData = 258;
  v6 = RegQueryValueExW(v35, L"OmaDmSession", 0, 0, (LPBYTE)v46, &lpcbData);
  if ( v6 )
  {
    v7 = 238;
    goto LABEL_11;
  }
  Str = 0;
  lpMem = 0;
  v42 = 0;
  p_Str = (void **)&Str;
  v38 = 0;
  v39 = 1;
  v4 = UnicodeToMB(v46, 0xFDE9u, (char **)&v38, &v42);
  if ( v39 )
  {
    v8 = (char)p_Str;
    v9 = *p_Str;
    *p_Str = v38;
    if ( v9 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
      (const char *)(unsigned int)v4,
      phkResulta);
    v11 = lpMem;
    lpMem = 0;
    if ( v11 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
    }
    v13 = Str;
    Str = 0;
    if ( v13 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
    }
    goto LABEL_12;
  }
  v15 = TraceLoggingCorrelationVector::Set(Str, v8);
  v43 = v15;
  if ( TraceLoggingCorrelationVector::Increment(v15, v45) )
  {
    v36 = 0;
    p_Str = &lpMem;
    v38 = 0;
    v39 = 1;
    v16 = MBToUnicode(v45, 0xFDE9u, &v38, &v36);
    if ( v39 )
    {
      v17 = *p_Str;
      *p_Str = v38;
      if ( v17 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v17);
      }
    }
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
        (const char *)(unsigned int)v16,
        phkResulta);
LABEL_30:
      if ( v15 )
        operator delete(v15);
      v19 = lpMem;
      v20 = lpMem == 0;
      lpMem = 0;
      if ( !v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v19);
      }
      v22 = Str;
      v20 = Str == 0;
      Str = 0;
      if ( !v20 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      if ( v35 )
        RegCloseKey(v35);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v16;
    }
    v24 = RegSetValueExW(v35, L"OmaDmSession", 0, 1u, (const BYTE *)lpMem, 2 * v36);
    if ( v24 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x109,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmlogger\\loggerutils.cpp",
              (const char *)v24,
              phkResultb);
      goto LABEL_30;
    }
  }
  if ( v15 )
    operator delete(v15);
  v25 = lpMem;
  lpMem = 0;
  if ( v25 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
  v27 = Str;
  Str = 0;
  if ( v27 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v27);
  }
  if ( v35 )
    RegCloseKey(v35);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x140012618  push    rbp
0x14001261a  push    rbx
0x14001261b  push    rsi
0x14001261c  push    rdi
0x14001261d  push    r14
0x14001261f  lea     rbp, [rsp-190h]
0x140012627  sub     rsp, 290h
0x14001262e  mov     rax, cs:__security_cookie
0x140012635  xor     rax, rsp
0x140012638  mov     [rbp+1B0h+var_30], rax
0x14001263f  xor     r14d, r14d
0x140012642  mov     [rsp+2B0h+hKey], r14
0x140012647  call    cs:__imp_RtlIsStateSeparationEnabled
0x14001264e  nop     dword ptr [rax+rax+00h]
0x140012653  neg     al
0x140012655  sbb     rdx, rdx
0x140012658  and     edx, 8
0x14001265b  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x140012662  lea     rax, [rsp+2B0h+hKey]
0x140012667  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x14001266c  mov     r9d, 20019h; samDesired
0x140012672  xor     r8d, r8d; ulOptions
0x140012675  mov     rdx, [rdx+rcx]; lpSubKey
0x140012679  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012680  call    cs:__imp_RegOpenKeyExW
0x140012687  nop     dword ptr [rax+rax+00h]
0x14001268c  test    eax, eax
0x14001268e  jz      short loc_1400126CA
0x140012690  mov     edx, 0D0h; void *
0x140012695  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14001269c  mov     r9d, eax; char *
0x14001269f  mov     rcx, [rbp+1B8h]; this
0x1400126a6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400126ab  mov     ebx, eax
0x1400126ad  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400126b2  test    rcx, rcx
0x1400126b5  jz      short loc_1400126C3
0x1400126b7  call    cs:__imp_RegCloseKey
0x1400126be  nop     dword ptr [rax+rax+00h]
0x1400126c3  mov     eax, ebx
0x1400126c5  jmp     loc_140012B2D
0x1400126ca  mov     [rsp+2B0h+cbData], 4Eh ; 'N'
0x1400126d2  lea     rax, [rsp+2B0h+cbData]
0x1400126d7  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1400126dc  lea     rax, [rbp+1B0h+Data]
0x1400126e0  mov     [rsp+2B0h+phkResult], rax; lpData
0x1400126e5  xor     r9d, r9d; lpType
0x1400126e8  xor     r8d, r8d; lpReserved
0x1400126eb  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1400126f2  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400126f7  call    cs:__imp_RegQueryValueExW
0x1400126fe  nop     dword ptr [rax+rax+00h]
0x140012703  test    eax, eax
0x140012705  jz      short loc_14001270E
0x140012707  mov     edx, 0DBh
0x14001270c  jmp     short loc_140012695
0x14001270e  mov     [rsp+2B0h+var_268], r14
0x140012713  lea     rax, [rsp+2B0h+var_268]
0x140012718  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x14001271d  mov     r9d, 2001Fh; samDesired
0x140012723  xor     r8d, r8d; ulOptions
0x140012726  lea     rdx, [rbp+1B0h+Data]; lpSubKey
0x14001272a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x14001272f  call    cs:__imp_RegOpenKeyExW
0x140012736  nop     dword ptr [rax+rax+00h]
0x14001273b  test    eax, eax
0x14001273d  jz      short loc_14001277B
0x14001273f  mov     edx, 0E3h; void *
0x140012744  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14001274b  mov     r9d, eax; char *
0x14001274e  mov     rcx, [rbp+1B8h]; this
0x140012755  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001275a  mov     ebx, eax
0x14001275c  mov     rcx, [rsp+2B0h+var_268]; hKey
0x140012761  test    rcx, rcx
0x140012764  jz      loc_1400126AD
0x14001276a  call    cs:__imp_RegCloseKey
0x140012771  nop     dword ptr [rax+rax+00h]
0x140012776  jmp     loc_1400126AD
0x14001277b  mov     [rsp+2B0h+var_23C], 102h
0x140012783  lea     rax, [rsp+2B0h+var_23C]
0x140012788  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x14001278d  lea     rax, [rbp+1B0h+var_140]
0x140012791  mov     [rsp+2B0h+phkResult], rax; int
0x140012796  xor     r9d, r9d; lpType
0x140012799  xor     r8d, r8d; lpReserved
0x14001279c  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x1400127a3  mov     rcx, [rsp+2B0h+var_268]; hKey
0x1400127a8  call    cs:__imp_RegQueryValueExW
0x1400127af  nop     dword ptr [rax+rax+00h]
0x1400127b4  test    eax, eax
0x1400127b6  jz      short loc_1400127BF
0x1400127b8  mov     edx, 0EEh
0x1400127bd  jmp     short loc_140012744
0x1400127bf  mov     [rsp+2B0h+Str], r14
0x1400127c4  mov     [rsp+2B0h+lpMem], r14
0x1400127c9  mov     [rsp+2B0h+var_238], r14d
0x1400127ce  lea     rax, [rsp+2B0h+Str]
0x1400127d3  mov     [rsp+2B0h+var_258], rax
0x1400127d8  mov     [rsp+2B0h+var_250], r14
0x1400127dd  mov     [rsp+2B0h+var_248], 1
0x1400127e2  lea     r9, [rsp+2B0h+var_238]
0x1400127e7  lea     r8, [rsp+2B0h+var_250]
0x1400127ec  mov     esi, 0FDE9h
0x1400127f1  mov     edx, esi
0x1400127f3  lea     rcx, [rbp+1B0h+var_140]
0x1400127f7  call    cs:__imp_?UnicodeToMB@@YAJPEBGIPEAPEADPEAK@Z; UnicodeToMB(ushort const *,uint,char * *,ulong *)
0x1400127fe  nop     dword ptr [rax+rax+00h]
0x140012803  mov     ebx, eax
0x140012805  cmp     [rsp+2B0h+var_248], r14b
0x14001280a  jz      short loc_140012841
0x14001280c  mov     rdx, [rsp+2B0h+var_258]
0x140012811  mov     rdi, [rdx]
0x140012814  mov     rcx, [rsp+2B0h+var_250]
0x140012819  mov     [rdx], rcx
0x14001281c  test    rdi, rdi
0x14001281f  jz      short loc_140012841
0x140012821  call    cs:__imp_GetProcessHeap
0x140012828  nop     dword ptr [rax+rax+00h]
0x14001282d  mov     rcx, rax; hHeap
0x140012830  mov     r8, rdi; lpMem
0x140012833  xor     edx, edx; dwFlags
0x140012835  call    cs:__imp_HeapFree
0x14001283c  nop     dword ptr [rax+rax+00h]
0x140012841  test    ebx, ebx
0x140012843  jns     loc_1400128CD
0x140012849  mov     rcx, [rbp+1B8h]; this
0x140012850  mov     r9d, ebx; char *
0x140012853  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14001285a  mov     edx, 0F5h; void *
0x14001285f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012864  nop
0x140012865  mov     rdi, [rsp+2B0h+lpMem]
0x14001286a  mov     [rsp+2B0h+lpMem], r14
0x14001286f  test    rdi, rdi
0x140012872  jz      short loc_140012895
0x140012874  call    cs:__imp_GetProcessHeap
0x14001287b  nop     dword ptr [rax+rax+00h]
0x140012880  mov     rcx, rax; hHeap
0x140012883  mov     r8, rdi; lpMem
0x140012886  xor     edx, edx; dwFlags
0x140012888  call    cs:__imp_HeapFree
0x14001288f  nop     dword ptr [rax+rax+00h]
0x140012894  nop
0x140012895  mov     rdi, [rsp+2B0h+Str]
0x14001289a  mov     [rsp+2B0h+Str], r14
0x14001289f  test    rdi, rdi
0x1400128a2  jz      loc_14001275C
0x1400128a8  call    cs:__imp_GetProcessHeap
0x1400128af  nop     dword ptr [rax+rax+00h]
0x1400128b4  mov     rcx, rax; hHeap
0x1400128b7  mov     r8, rdi; lpMem
0x1400128ba  xor     edx, edx; dwFlags
0x1400128bc  call    cs:__imp_HeapFree
0x1400128c3  nop     dword ptr [rax+rax+00h]
0x1400128c8  jmp     loc_14001275C
0x1400128cd  mov     rcx, [rsp+2B0h+Str]; Str
0x1400128d2  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x1400128d7  mov     rbx, rax
0x1400128da  mov     [rbp+1B0h+var_230], rax
0x1400128de  lea     rdx, [rbp+1B0h+var_1D0]; char *
0x1400128e2  mov     rcx, rax; this
0x1400128e5  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1400128ea  test    al, al
0x1400128ec  jz      loc_140012A8B
0x1400128f2  mov     [rsp+2B0h+var_260], r14d
0x1400128f7  lea     rax, [rsp+2B0h+lpMem]
0x1400128fc  mov     [rsp+2B0h+var_258], rax
0x140012901  mov     [rsp+2B0h+var_250], r14
0x140012906  mov     [rsp+2B0h+var_248], 1
0x14001290b  lea     r9, [rsp+2B0h+var_260]
0x140012910  lea     r8, [rsp+2B0h+var_250]
0x140012915  mov     edx, esi
0x140012917  lea     rcx, [rbp+1B0h+var_1D0]
0x14001291b  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x140012922  nop     dword ptr [rax+rax+00h]
0x140012927  mov     edi, eax
0x140012929  cmp     [rsp+2B0h+var_248], r14b
0x14001292e  jz      short loc_140012965
0x140012930  mov     rdx, [rsp+2B0h+var_258]
0x140012935  mov     rsi, [rdx]
0x140012938  mov     rcx, [rsp+2B0h+var_250]
0x14001293d  mov     [rdx], rcx
0x140012940  test    rsi, rsi
0x140012943  jz      short loc_140012965
0x140012945  call    cs:__imp_GetProcessHeap
0x14001294c  nop     dword ptr [rax+rax+00h]
0x140012951  mov     rcx, rax; hHeap
0x140012954  mov     r8, rsi; lpMem
0x140012957  xor     edx, edx; dwFlags
0x140012959  call    cs:__imp_HeapFree
0x140012960  nop     dword ptr [rax+rax+00h]
0x140012965  test    edi, edi
0x140012967  jns     loc_140012A30
0x14001296d  mov     rcx, [rbp+1B8h]; this
0x140012974  mov     r9d, edi; char *
0x140012977  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x14001297e  mov     edx, 0FFh; void *
0x140012983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012988  nop
0x140012989  test    rbx, rbx
0x14001298c  jz      short loc_14001299C
0x14001298e  mov     edx, 90h
0x140012993  mov     rcx, rbx; Block
0x140012996  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001299b  nop
0x14001299c  mov     rbx, [rsp+2B0h+lpMem]
0x1400129a1  test    rbx, rbx
0x1400129a4  mov     [rsp+2B0h+lpMem], r14
0x1400129a9  jz      short loc_1400129CC
0x1400129ab  call    cs:__imp_GetProcessHeap
0x1400129b2  nop     dword ptr [rax+rax+00h]
0x1400129b7  mov     r8, rbx; lpMem
0x1400129ba  xor     edx, edx; dwFlags
0x1400129bc  mov     rcx, rax; hHeap
0x1400129bf  call    cs:__imp_HeapFree
0x1400129c6  nop     dword ptr [rax+rax+00h]
0x1400129cb  nop
0x1400129cc  mov     rbx, [rsp+2B0h+Str]
0x1400129d1  test    rbx, rbx
0x1400129d4  mov     [rsp+2B0h+Str], r14
0x1400129d9  jz      short loc_1400129FC
0x1400129db  call    cs:__imp_GetProcessHeap
0x1400129e2  nop     dword ptr [rax+rax+00h]
0x1400129e7  mov     r8, rbx; lpMem
0x1400129ea  xor     edx, edx; dwFlags
0x1400129ec  mov     rcx, rax; hHeap
0x1400129ef  call    cs:__imp_HeapFree
0x1400129f6  nop     dword ptr [rax+rax+00h]
0x1400129fb  nop
0x1400129fc  mov     rcx, [rsp+2B0h+var_268]; hKey
0x140012a01  test    rcx, rcx
0x140012a04  jz      short loc_140012A13
0x140012a06  call    cs:__imp_RegCloseKey
0x140012a0d  nop     dword ptr [rax+rax+00h]
0x140012a12  nop
0x140012a13  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140012a18  test    rcx, rcx
0x140012a1b  jz      short loc_140012A29
0x140012a1d  call    cs:__imp_RegCloseKey
0x140012a24  nop     dword ptr [rax+rax+00h]
0x140012a29  mov     eax, edi
0x140012a2b  jmp     loc_140012B2D
0x140012a30  mov     r8, [rsp+2B0h+lpMem]
0x140012a35  mov     eax, [rsp+2B0h+var_260]
0x140012a39  add     eax, eax
0x140012a3b  mov     dword ptr [rsp+2B0h+lpcbData], eax; cbData
0x140012a3f  mov     [rsp+2B0h+phkResult], r8; unsigned int
0x140012a44  mov     r9d, 1; dwType
0x140012a4a  xor     r8d, r8d; Reserved
0x140012a4d  lea     rdx, c_szCvValueNameOmaDmSession; "OmaDmSession"
0x140012a54  mov     rcx, [rsp+2B0h+var_268]; hKey
0x140012a59  call    cs:__imp_RegSetValueExW
0x140012a60  nop     dword ptr [rax+rax+00h]
0x140012a65  test    eax, eax
0x140012a67  jz      short loc_140012A8B
0x140012a69  mov     rcx, [rbp+1B8h]; this
0x140012a70  mov     r9d, eax; char *
0x140012a73  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\dm\\omadm\\omadmlogg"...
0x140012a7a  mov     edx, 109h; void *
0x140012a7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012a84  mov     edi, eax
0x140012a86  jmp     loc_140012989
0x140012a8b  test    rbx, rbx
0x140012a8e  jz      short loc_140012A9E
0x140012a90  mov     edx, 90h
0x140012a95  mov     rcx, rbx; Block
0x140012a98  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140012a9d  nop
0x140012a9e  mov     rbx, [rsp+2B0h+lpMem]
0x140012aa3  mov     [rsp+2B0h+lpMem], r14
0x140012aa8  test    rbx, rbx
0x140012aab  jz      short loc_140012ACE
0x140012aad  call    cs:__imp_GetProcessHeap
0x140012ab4  nop     dword ptr [rax+rax+00h]
0x140012ab9  mov     rcx, rax; hHeap
0x140012abc  mov     r8, rbx; lpMem
0x140012abf  xor     edx, edx; dwFlags
0x140012ac1  call    cs:__imp_HeapFree
0x140012ac8  nop     dword ptr [rax+rax+00h]
0x140012acd  nop
0x140012ace  mov     rbx, [rsp+2B0h+Str]
0x140012ad3  mov     [rsp+2B0h+Str], r14
0x140012ad8  test    rbx, rbx
0x140012adb  jz      short loc_140012AFE
0x140012add  call    cs:__imp_GetProcessHeap
0x140012ae4  nop     dword ptr [rax+rax+00h]
0x140012ae9  mov     rcx, rax; hHeap
0x140012aec  mov     r8, rbx; lpMem
0x140012aef  xor     edx, edx; dwFlags
0x140012af1  call    cs:__imp_HeapFree
0x140012af8  nop     dword ptr [rax+rax+00h]
0x140012afd  nop
0x140012afe  mov     rcx, [rsp+2B0h+var_268]; hKey
0x140012b03  test    rcx, rcx
0x140012b06  jz      short loc_140012B15
0x140012b08  call    cs:__imp_RegCloseKey
0x140012b0f  nop     dword ptr [rax+rax+00h]
0x140012b14  nop
0x140012b15  mov     rcx, [rsp+2B0h+hKey]; hKey
  ... truncated ...
```
