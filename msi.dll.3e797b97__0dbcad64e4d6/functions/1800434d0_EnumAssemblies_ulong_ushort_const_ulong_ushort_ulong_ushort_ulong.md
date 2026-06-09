# EnumAssemblies(ulong,ushort const *,ulong,ushort *,ulong *,ushort *,ulong *)

- ea: `0x1800434d0`
- end: `0x180043e54`
- name: `?EnumAssemblies@@YAIKPEBGKPEAGPEAK12@Z`
- size: `2436`
- prototype: `unsigned int __fastcall(unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180041d34`
- `0x180042b60`

## callees

- `0x180011280`
- `0x18003c030`
- `0x180042414`
- `0x1800434d0`
- `0x180044960`
- `0x1800459c0`
- `0x180048588`
- `0x18013aa84`
- `0x180265240`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180043c03`
- `ADVAPI32!RegEnumValueW` at `0x180043c03`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180043d29`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180043d29`
- `ADVAPI32!RegQueryValueExW` at `0x180043d7d`
- `ADVAPI32!RegQueryValueExW` at `0x180043d7d`
- `ADVAPI32!RegCloseKey` at `0x180043899`
- `ADVAPI32!RegCloseKey` at `0x180043b50`
- `ADVAPI32!RegCloseKey` at `0x180043899`
- `ADVAPI32!RegCloseKey` at `0x180043b50`
- `KERNEL32!InitializeCriticalSection` at `0x18004373f`
- `KERNEL32!InitializeCriticalSection` at `0x180043c6e`
- `KERNEL32!InitializeCriticalSection` at `0x18004373f`
- `KERNEL32!InitializeCriticalSection` at `0x180043c6e`
- `KERNEL32!DeleteCriticalSection` at `0x1800438c4`
- `KERNEL32!DeleteCriticalSection` at `0x180043b7b`
- `KERNEL32!DeleteCriticalSection` at `0x1800438c4`
- `KERNEL32!DeleteCriticalSection` at `0x180043b7b`
- `KERNEL32!LeaveCriticalSection` at `0x180043591`
- `KERNEL32!LeaveCriticalSection` at `0x18004362d`
- `KERNEL32!LeaveCriticalSection` at `0x1800436f4`
- `KERNEL32!LeaveCriticalSection` at `0x180043869`
- `KERNEL32!LeaveCriticalSection` at `0x1800438b4`
- `KERNEL32!LeaveCriticalSection` at `0x180043b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180043dac`
- `KERNEL32!LeaveCriticalSection` at `0x180043591`
- `KERNEL32!LeaveCriticalSection` at `0x18004362d`
- `KERNEL32!LeaveCriticalSection` at `0x1800436f4`
- `KERNEL32!LeaveCriticalSection` at `0x180043869`
- `KERNEL32!LeaveCriticalSection` at `0x1800438b4`
- `KERNEL32!LeaveCriticalSection` at `0x180043b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180043dac`
- `KERNEL32!GetCurrentThreadId` at `0x1800435ba`
- `KERNEL32!GetCurrentThreadId` at `0x180043936`
- `KERNEL32!GetCurrentThreadId` at `0x18004398c`
- `KERNEL32!GetCurrentThreadId` at `0x1800435ba`
- `KERNEL32!GetCurrentThreadId` at `0x180043936`
- `KERNEL32!GetCurrentThreadId` at `0x18004398c`
- `KERNEL32!EnterCriticalSection` at `0x180043575`
- `KERNEL32!EnterCriticalSection` at `0x1800435ae`
- `KERNEL32!EnterCriticalSection` at `0x180043884`
- `KERNEL32!EnterCriticalSection` at `0x180043980`
- `KERNEL32!EnterCriticalSection` at `0x180043b3b`
- `KERNEL32!EnterCriticalSection` at `0x180043575`
- `KERNEL32!EnterCriticalSection` at `0x1800435ae`
- `KERNEL32!EnterCriticalSection` at `0x180043884`
- `KERNEL32!EnterCriticalSection` at `0x180043980`
- `KERNEL32!EnterCriticalSection` at `0x180043b3b`
- `KERNEL32!GlobalAlloc` at `0x1800436ad`
- `KERNEL32!GlobalAlloc` at `0x1800436ad`
- `KERNEL32!GlobalFree` at `0x1800438de`
- `KERNEL32!GlobalFree` at `0x180043b91`
- `KERNEL32!GlobalFree` at `0x1800438de`
- `KERNEL32!GlobalFree` at `0x180043b91`

## pseudocode

```c
__int64 __fastcall EnumAssemblies(
        unsigned int a1,
        char *a2,
        int a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 *lpData,
        unsigned int *a7)
{
  unsigned int *lpcbData; // r14
  int v11; // r13d
  _DWORD *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int i; // ecx
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rsi
  int v21; // r12d
  const wchar_t *v22; // rdi
  DWORD v23; // esi
  char *v24; // rdx
  int v25; // eax
  int v26; // ecx
  HGLOBAL v27; // rax
  unsigned int v28; // ecx
  char v29; // r12
  unsigned int *lpcbMaxValueNameLen; // rdi
  const wchar_t *v31; // rax
  unsigned int v32; // edx
  int v33; // ebx
  unsigned int v34; // r15d
  _WORD *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdi
  _DWORD *v39; // r14
  struct _RTL_CRITICAL_SECTION *v40; // rbx
  DWORD v41; // eax
  unsigned int v42; // r8d
  unsigned int j; // ecx
  int v44; // r9d
  int v45; // edi
  char v46; // r12
  const unsigned __int16 *v47; // r10
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // r9
  _WORD *v52; // rax
  int k; // edx
  int v54; // edi
  int v55; // eax
  bool v56; // si
  int v57; // ebx
  int v58; // r8d
  __int64 v59; // rcx
  __int64 v60; // rdx
  char v61; // [rsp+60h] [rbp-A0h]
  DWORD dwIndex; // [rsp+64h] [rbp-9Ch]
  int v63; // [rsp+68h] [rbp-98h]
  unsigned int v64; // [rsp+68h] [rbp-98h]
  int v65; // [rsp+6Ch] [rbp-94h]
  bool v67; // [rsp+74h] [rbp-8Ch]
  unsigned int v68; // [rsp+78h] [rbp-88h]
  unsigned int v70; // [rsp+90h] [rbp-70h]
  WCHAR *v71; // [rsp+98h] [rbp-68h]
  LPVOID v73[3]; // [rsp+B8h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION hKey; // [rsp+D0h] [rbp-30h] BYREF
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+F8h] [rbp-8h] BYREF
  struct _RTL_CRITICAL_SECTION v76; // [rsp+120h] [rbp+20h] BYREF
  struct _RTL_CRITICAL_SECTION v77; // [rsp+148h] [rbp+48h] BYREF

  lpcbData = a7;
  CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall((CForbidTokenChangesDuringCall *)v73);
  v11 = 0;
  if ( !a2 || !a4 || !a5 || lpData && !a7 || a1 > 1 )
    goto LABEL_48;
  EnterCriticalSection(&g_csEnumLock);
  if ( !g_pEnumAssemblies )
  {
    v27 = GlobalAlloc(0x40u, 0x3C8u);
    g_pEnumAssemblies = v27;
    if ( !v27 )
    {
      LeaveCriticalSection(&g_csEnumLock);
      CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(v73);
      return 14;
    }
    EnumEntityList::Init((EnumEntityList *)v27);
  }
  LeaveCriticalSection(&g_csEnumLock);
  v12 = g_pEnumAssemblies;
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pEnumAssemblies + 928);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pEnumAssemblies + 928));
  CurrentThreadId = GetCurrentThreadId();
  for ( i = 0; i < v12[230]; i = v16 )
  {
    v16 = i + 1;
    v17 = 904LL * (int)i;
    v18 = *(_QWORD *)v12;
    if ( *(_DWORD *)(v17 + *(_QWORD *)v12) == CurrentThreadId )
    {
      if ( v16 )
      {
        v19 = *(_QWORD *)v12;
        v20 = 904LL * (int)v16;
        v11 = *(_DWORD *)(v20 + v18 - 900);
        v21 = *(_DWORD *)(v20 + v18 - 888);
        dwIndex = *(_DWORD *)(v20 + v18 - 896);
        v63 = v11;
        v65 = v21;
        LeaveCriticalSection(v13);
        v22 = (const wchar_t *)(v20 + v19 - 616);
        v23 = dwIndex;
        goto LABEL_12;
      }
      break;
    }
  }
  v23 = 0;
  v63 = 0;
  v21 = -1;
  dwIndex = 0;
  v65 = -1;
  v22 = &Default;
  LeaveCriticalSection(v13);
LABEL_12:
  v24 = (char *)(a2 - (char *)v22);
  do
  {
    v25 = *(unsigned __int16 *)&v24[(_QWORD)v22];
    v26 = *v22 - v25;
    if ( v26 )
      break;
    ++v22;
  }
  while ( v25 );
  if ( !v26 )
  {
    if ( v21 == a3 )
    {
      if ( v21 != -1 )
      {
        dwIndex = --v23;
        goto LABEL_26;
      }
LABEL_48:
      CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(v73);
      return 87;
    }
    v65 = v21 + 1;
    if ( v21 + 1 == a3 )
      goto LABEL_26;
  }
  if ( a3 )
    goto LABEL_48;
  v11 = 0;
  v63 = 0;
  v23 = 0;
  dwIndex = 0;
  v65 = 0;
LABEL_26:
  LOWORD(hKey.SpinCount) = 0;
  *(_OWORD *)&hKey.DebugInfo = 0;
  hKey.OwningThread = &hKey.SpinCount;
  LODWORD(hKey.LockSemaphore) = 1;
  InitializeCriticalSection(&CriticalSection);
  v61 = 1;
  v28 = 0;
  v29 = 1;
  v68 = 0;
  if ( a7 )
  {
    v28 = *a7;
    v68 = *a7;
  }
  lpcbMaxValueNameLen = a5;
  v31 = L"Win32Assemblies";
  if ( (a1 & 1) == 0 )
    v31 = L"Assemblies";
  v32 = *a5;
  v70 = *a5;
  v71 = (WCHAR *)v31;
  while ( 2 )
  {
    if ( lpcbData )
      *lpcbData = v28;
    *lpcbMaxValueNameLen = v32;
    while ( 1 )
    {
      if ( v11 == -1 || (v34 = 2, v11 < 3) )
      {
        v33 = 0;
        if ( v11 != -1 )
          v33 = v11;
        do
        {
          v34 = OpenSpecificUsersAdvertisedSubKeyPacked(v33, 0, v71, (const WCHAR *)a2, &hKey, 0);
          if ( !v34 )
            break;
          if ( v11 != -1 )
            break;
          ++v33;
        }
        while ( v33 < 3 );
        lpcbData = a7;
        v23 = dwIndex;
        v29 = v61;
        lpcbMaxValueNameLen = a5;
      }
      if ( v11 > 2 )
      {
        v34 = 259;
        goto LABEL_113;
      }
      if ( v34 != 2 )
        break;
      v63 = ++v11;
    }
    if ( v34 )
      goto LABEL_112;
    if ( lpcbData )
      *lpcbData *= 2;
    v34 = RegEnumValueW((HKEY)hKey.DebugInfo, v23, a4, lpcbMaxValueNameLen, 0, 0, (LPBYTE)lpData, lpcbData);
    if ( v34 == 234 )
      RegQueryInfoKeyW((HKEY)hKey.DebugInfo, 0, 0, 0, 0, 0, 0, 0, lpcbMaxValueNameLen, lpcbData, 0, 0);
    if ( lpcbData )
      *lpcbData >>= 1;
    if ( v34 )
    {
      if ( v34 == 259 )
      {
        ++v11;
        dwIndex = 0;
        v63 = v11;
        v23 = 0;
      }
      else
      {
        v29 = 0;
      }
      goto LABEL_111;
    }
    v57 = 0;
    v56 = *a4 == 0;
    v67 = v56;
    if ( v11 )
    {
      while ( !v56 )
      {
        LODWORD(v76.LockSemaphore) = 1;
        *(_OWORD *)&v76.DebugInfo = 0;
        v76.OwningThread = &v76.SpinCount;
        LOWORD(v76.SpinCount) = 0;
        InitializeCriticalSection(&v77);
        if ( v57 == -1 || (v55 = 2, v57 < 3) )
        {
          v54 = 0;
          if ( v57 != -1 )
            v54 = v57;
          do
          {
            v55 = OpenSpecificUsersAdvertisedSubKeyPacked(v54, 0, v71, (const WCHAR *)a2, &v76, 0);
            if ( !v55 )
              break;
            if ( v57 != -1 )
              break;
            ++v54;
          }
          while ( v54 < 3 );
          lpcbData = a7;
          v11 = v63;
          v56 = v67;
          v29 = v61;
        }
        if ( v57 > 2 || v55 )
        {
          EnterCriticalSection(&v77);
          if ( v76.DebugInfo )
          {
            RegCloseKey((HKEY)v76.DebugInfo);
            v76.DebugInfo = 0;
            *(_WORD *)v76.OwningThread = 0;
          }
          LeaveCriticalSection(&v77);
          DeleteCriticalSection(&v77);
          if ( SLODWORD(v76.LockSemaphore) > 1 )
            GlobalFree(v76.OwningThread);
        }
        else
        {
          if ( !RegQueryValueExW((HKEY)v76.DebugInfo, a4, 0, 0, 0, 0) )
            v56 = 1;
          v67 = v56;
          CRegHandle::~CRegHandle((CRegHandle *)&v76);
        }
        if ( ++v57 >= (unsigned int)v11 )
        {
          lpcbMaxValueNameLen = a5;
          goto LABEL_63;
        }
      }
      lpcbMaxValueNameLen = a5;
LABEL_117:
      v23 = ++dwIndex;
LABEL_111:
      v28 = v68;
      v32 = v70;
      v61 = v29;
      if ( v29 )
        continue;
LABEL_112:
      if ( v34 == 259 )
      {
LABEL_113:
        if ( a3 )
          EnumEntityList::RemoveThreadInfo((EnumEntityList *)g_pEnumAssemblies);
        else
          v34 = 1607;
        goto LABEL_57;
      }
    }
    else
    {
LABEL_63:
      if ( v56 )
        goto LABEL_117;
    }
    break;
  }
  v39 = g_pEnumAssemblies;
  v40 = (struct _RTL_CRITICAL_SECTION *)((char *)g_pEnumAssemblies + 928);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pEnumAssemblies + 928));
  v41 = GetCurrentThreadId();
  v42 = v39[230];
  for ( j = 0; j < v42; ++j )
  {
    v44 = j + 1;
    if ( *(_DWORD *)(904LL * (int)j + *(_QWORD *)v39) == v41 )
    {
      if ( j != -1 )
      {
        v45 = 0;
        v64 = 0;
        goto LABEL_69;
      }
      break;
    }
  }
  v45 = v42 + 1;
  v64 = v42 + 1;
  if ( v42 + 1 > v39[2] )
  {
    for ( k = 1; k <= v42; ++k )
    {
      if ( !*(_DWORD *)(904LL * k + *(_QWORD *)v39 - 904) )
      {
        v45 = k;
        v64 = v39[230];
        goto LABEL_80;
      }
    }
    if ( !(unsigned __int8)CAPITempBuffer<EnumEntity,1>::SetSize(v39, v42 + 10) )
    {
      v46 = 0;
      goto LABEL_55;
    }
    v58 = v39[230];
    while ( v58 < v39[2] )
    {
      v59 = *(_QWORD *)v39;
      v60 = 904LL * v58++;
      *(_QWORD *)(v60 + v59) = 0;
      *(_QWORD *)(v60 + v59 + 8) = 0;
      *(_DWORD *)(v60 + v59 + 16) = 0;
      *(_BYTE *)(v60 + v59 + 20) = 0;
      *(_DWORD *)(v60 + v59 + 24) = 0;
      *(_DWORD *)(v60 + v59 + 896) = 0;
      *(_BYTE *)(v60 + v59 + 28) = 0;
      *(_WORD *)(v60 + v59 + 288) = 0;
      *(_WORD *)(v60 + v59 + 808) = 0;
      *(_QWORD *)(v60 + v59 + 888) = 0;
    }
  }
LABEL_80:
  v44 = v45;
LABEL_69:
  v46 = 1;
  v47 = (const unsigned __int16 *)a2;
  v48 = 904LL * v44;
  *(_DWORD *)(*(_QWORD *)v39 + v48 - 900) = v11;
  *(_DWORD *)(*(_QWORD *)v39 + v48 - 896) = dwIndex + 1;
  *(_DWORD *)(*(_QWORD *)v39 + v48 - 892) = 0;
  *(_DWORD *)(*(_QWORD *)v39 + v48 - 888) = v65;
  v49 = 2147483646;
  *(_DWORD *)(*(_QWORD *)v39 + v48 - 880) = 0;
  *(_BYTE *)(*(_QWORD *)v39 + v48 - 884) = 0;
  *(_BYTE *)(*(_QWORD *)v39 + v48 - 876) = 0;
  v50 = 260;
  v51 = *(_QWORD *)v39 + v48;
  v52 = (_WORD *)(v51 - 616);
  do
  {
    if ( !v49 )
      break;
    if ( !*v47 )
      break;
    *v52++ = *v47++;
    --v49;
    --v50;
  }
  while ( v50 );
  v36 = v52 - 1;
  if ( v50 )
    v36 = v52;
  *v36 = 0;
  if ( !v50 )
    *(_WORD *)(v51 - 616) = 0;
  if ( v45 )
  {
    v37 = (unsigned int)(v45 - 1);
    v38 = *(_QWORD *)v39;
    *(_DWORD *)(904 * v37 + v38) = GetCurrentThreadId();
    v39[230] = v64;
  }
LABEL_55:
  LeaveCriticalSection(v40);
  if ( !v46 )
    v34 = 8;
LABEL_57:
  EnterCriticalSection(&CriticalSection);
  if ( hKey.DebugInfo )
  {
    RegCloseKey((HKEY)hKey.DebugInfo);
    hKey.DebugInfo = 0;
    *(_WORD *)hKey.OwningThread = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  DeleteCriticalSection(&CriticalSection);
  if ( SLODWORD(hKey.LockSemaphore) > 1 )
    GlobalFree(hKey.OwningThread);
  LODWORD(hKey.LockSemaphore) = 1;
  hKey.OwningThread = &hKey.SpinCount;
  CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(v73);
  return v34;
}

```

## disassembly

```asm
0x1800434d0  mov     [rsp-8+arg_0], rbx
0x1800434d5  push    rbp
0x1800434d6  push    rsi
0x1800434d7  push    rdi
0x1800434d8  push    r12
0x1800434da  push    r13
0x1800434dc  push    r14
0x1800434de  push    r15
0x1800434e0  lea     rbp, [rsp-80h]
0x1800434e5  sub     rsp, 180h
0x1800434ec  mov     rax, cs:__security_cookie
0x1800434f3  xor     rax, rsp
0x1800434f6  mov     [rbp+0B0h+var_40], rax
0x1800434fa  mov     rbx, [rbp+0B0h+arg_20]
0x180043501  mov     r15d, ecx
0x180043504  mov     r12, [rbp+0B0h+arg_28]
0x18004350b  lea     rcx, [rbp+0B0h+var_F8]; this
0x18004350f  mov     r14, [rbp+0B0h+arg_30]
0x180043516  mov     rsi, r9
0x180043519  mov     [rbp+0B0h+lpcchValueName], rbx
0x18004351d  mov     rdi, rdx
0x180043520  mov     [rbp+0B0h+var_100], r12
0x180043524  mov     [rbp+0B0h+var_110], r14
0x180043528  mov     [rbp+0B0h+lpValueName], r9
0x18004352c  mov     [rsp+1B0h+var_140], r8d
0x180043531  mov     [rbp+0B0h+var_128], rdx
0x180043535  call    ??0CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(void)
0x18004353a  xor     r13d, r13d
0x18004353d  test    rdi, rdi
0x180043540  jz      loc_180043833
0x180043546  test    rsi, rsi
0x180043549  jz      loc_180043833
0x18004354f  test    rbx, rbx
0x180043552  jz      loc_180043833
0x180043558  test    r12, r12
0x18004355b  jnz     loc_180043695
0x180043561  cmp     r15d, 1
0x180043565  ja      loc_180043833
0x18004356b  lea     rbx, ?g_csEnumLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEnumLock
0x180043572  mov     rcx, rbx; lpCriticalSection
0x180043575  call    cs:__imp_EnterCriticalSection
0x18004357c  nop     dword ptr [rax+rax+00h]
0x180043581  cmp     cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA, r13; EnumEntityList * g_pEnumAssemblies
0x180043588  jz      loc_1800436A3
0x18004358e  mov     rcx, rbx; lpCriticalSection
0x180043591  call    cs:__imp_LeaveCriticalSection
0x180043598  nop     dword ptr [rax+rax+00h]
0x18004359d  mov     rdi, cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA; EnumEntityList * g_pEnumAssemblies
0x1800435a4  lea     rbx, [rdi+3A0h]
0x1800435ab  mov     rcx, rbx; lpCriticalSection
0x1800435ae  call    cs:__imp_EnterCriticalSection
0x1800435b5  nop     dword ptr [rax+rax+00h]
0x1800435ba  call    cs:__imp_GetCurrentThreadId
0x1800435c1  nop     dword ptr [rax+rax+00h]
0x1800435c6  mov     ecx, r13d
0x1800435c9  cmp     ecx, [rdi+398h]
0x1800435cf  jnb     loc_1800436D6
0x1800435d5  lea     r8d, [rcx+1]
0x1800435d9  movsxd  rcx, ecx
0x1800435dc  imul    rdx, rcx, 388h
0x1800435e3  mov     rcx, [rdi]
0x1800435e6  cmp     [rdx+rcx], eax
0x1800435e9  jnz     loc_18004368D
0x1800435ef  test    r8d, r8d
0x1800435f2  jz      loc_1800436D6
0x1800435f8  mov     rdi, rcx
0x1800435fb  movsxd  rax, r8d
0x1800435fe  imul    rsi, rax, 388h
0x180043605  mov     r13d, [rsi+rcx-384h]
0x18004360d  mov     ecx, [rsi+rcx-380h]
0x180043614  mov     r12d, [rsi+rdi-378h]
0x18004361c  mov     [rsp+1B0h+dwIndex], ecx
0x180043620  mov     rcx, rbx; lpCriticalSection
0x180043623  mov     [rsp+1B0h+var_148], r13d
0x180043628  mov     [rsp+1B0h+var_144], r12d
0x18004362d  call    cs:__imp_LeaveCriticalSection
0x180043634  nop     dword ptr [rax+rax+00h]
0x180043639  add     rdi, 0FFFFFFFFFFFFFD98h
0x180043640  add     rdi, rsi
0x180043643  mov     esi, [rsp+1B0h+dwIndex]
0x180043647  mov     rdx, [rbp+0B0h+var_128]
0x18004364b  sub     rdx, rdi
0x18004364e  movzx   ecx, word ptr [rdi]
0x180043651  movzx   eax, word ptr [rdi+rdx]
0x180043655  sub     ecx, eax
0x180043657  jnz     short loc_180043661
0x180043659  add     rdi, 2
0x18004365d  test    eax, eax
0x18004365f  jnz     short loc_18004364E
0x180043661  mov     edi, [rsp+1B0h+var_140]
0x180043665  xor     edx, edx
0x180043667  test    ecx, ecx
0x180043669  jz      loc_180043705
0x18004366f  test    edi, edi
0x180043671  jnz     loc_180043833
0x180043677  mov     r13d, edx
0x18004367a  mov     [rsp+1B0h+var_148], edx
0x18004367e  mov     esi, edx
0x180043680  mov     [rsp+1B0h+dwIndex], edx
0x180043684  mov     [rsp+1B0h+var_144], edx
0x180043688  jmp     loc_18004371F
0x18004368d  mov     ecx, r8d
0x180043690  jmp     loc_1800435C9
0x180043695  test    r14, r14
0x180043698  jnz     loc_180043561
0x18004369e  jmp     loc_180043833
0x1800436a3  mov     edx, 3C8h; dwBytes
0x1800436a8  mov     ecx, 40h ; '@'; uFlags
0x1800436ad  call    cs:__imp_GlobalAlloc
0x1800436b4  nop     dword ptr [rax+rax+00h]
0x1800436b9  mov     cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA, rax; EnumEntityList * g_pEnumAssemblies
0x1800436c0  test    rax, rax
0x1800436c3  jz      loc_180043DA9
0x1800436c9  mov     rcx, rax; this
0x1800436cc  call    ?Init@EnumEntityList@@QEAAXXZ; EnumEntityList::Init(void)
0x1800436d1  jmp     loc_18004358E
0x1800436d6  xor     esi, esi
0x1800436d8  mov     [rsp+1B0h+var_148], r13d
0x1800436dd  or      r12d, 0FFFFFFFFh
0x1800436e1  mov     [rsp+1B0h+dwIndex], esi
0x1800436e5  mov     rcx, rbx; lpCriticalSection
0x1800436e8  mov     [rsp+1B0h+var_144], r12d
0x1800436ed  lea     rdi, Default
0x1800436f4  call    cs:__imp_LeaveCriticalSection
0x1800436fb  nop     dword ptr [rax+rax+00h]
0x180043700  jmp     loc_180043647
0x180043705  cmp     r12d, edi
0x180043708  jz      loc_180043829
0x18004370e  inc     r12d
0x180043711  mov     [rsp+1B0h+var_144], r12d
0x180043716  cmp     r12d, edi
0x180043719  jnz     loc_18004366F
0x18004371f  xorps   xmm0, xmm0
0x180043722  mov     [rbp+0B0h+var_C0], dx
0x180043726  lea     rax, [rbp+0B0h+var_C0]
0x18004372a  movdqa  xmmword ptr [rbp+0B0h+hKey], xmm0
0x18004372f  mov     ebx, 1
0x180043734  mov     [rbp+0B0h+hMem], rax
0x180043738  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x18004373c  mov     [rbp+0B0h+var_C8], ebx
0x18004373f  call    cs:__imp_InitializeCriticalSection
0x180043746  nop     dword ptr [rax+rax+00h]
0x18004374b  xor     r9d, r9d
0x18004374e  mov     [rsp+1B0h+var_150], bl
0x180043752  mov     ecx, r9d
0x180043755  mov     r12b, bl
0x180043758  mov     [rsp+1B0h+var_138], ecx
0x18004375c  test    r14, r14
0x18004375f  jz      short loc_180043768
0x180043761  mov     ecx, [r14]
0x180043764  mov     [rsp+1B0h+var_138], ecx
0x180043768  mov     rdi, [rbp+0B0h+lpcchValueName]
0x18004376c  lea     r8, aAssemblies_0; "Assemblies"
0x180043773  test    bl, r15b
0x180043776  lea     rax, aWin32assemblie_0; "Win32Assemblies"
0x18004377d  cmovz   rax, r8
0x180043781  mov     edx, [rdi]
0x180043783  mov     [rbp+0B0h+var_120], edx
0x180043786  mov     [rbp+0B0h+var_118], rax
0x18004378a  test    r14, r14
0x18004378d  jz      short loc_180043792
0x18004378f  mov     [r14], ecx
0x180043792  mov     [rdi], edx
0x180043794  cmp     r13d, 0FFFFFFFFh
0x180043798  jnz     short loc_180043817
0x18004379a  mov     rsi, [rbp+0B0h+var_118]
0x18004379e  xor     r14d, r14d
0x1800437a1  mov     rdi, [rbp+0B0h+var_128]
0x1800437a5  cmp     r13d, 0FFFFFFFFh
0x1800437a9  mov     ebx, r14d
0x1800437ac  cmovnz  ebx, r13d
0x1800437b0  lea     rax, [rbp+0B0h+hKey]
0x1800437b4  mov     byte ptr [rsp+1B0h+lpType], r14b
0x1800437b9  mov     r9, rdi
0x1800437bc  mov     [rsp+1B0h+lpReserved], rax
0x1800437c1  mov     r8, rsi
0x1800437c4  xor     edx, edx
0x1800437c6  mov     ecx, ebx
0x1800437c8  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x1800437cd  mov     r15d, eax
0x1800437d0  test    eax, eax
0x1800437d2  jz      short loc_1800437DA
0x1800437d4  cmp     r13d, 0FFFFFFFFh
0x1800437d8  jz      short loc_18004380E
0x1800437da  mov     r14, [rbp+0B0h+var_110]
0x1800437de  mov     ebx, 1
0x1800437e3  mov     esi, [rsp+1B0h+dwIndex]
0x1800437e7  mov     r12b, [rsp+1B0h+var_150]
0x1800437ec  mov     rdi, [rbp+0B0h+lpcchValueName]
0x1800437f0  cmp     r13d, 2
0x1800437f4  jg      loc_180043E49
0x1800437fa  cmp     r15d, 2
0x1800437fe  jnz     loc_180043BC3
0x180043804  add     r13d, ebx
0x180043807  mov     [rsp+1B0h+var_148], r13d
0x18004380c  jmp     short loc_180043794
0x18004380e  inc     ebx
0x180043810  cmp     ebx, 3
0x180043813  jge     short loc_1800437DA
0x180043815  jmp     short loc_1800437B0
0x180043817  mov     r15d, 2
0x18004381d  cmp     r13d, 3
0x180043821  jl      loc_18004379A
0x180043827  jmp     short loc_1800437F0
0x180043829  cmp     r12d, 0FFFFFFFFh
0x18004382d  jnz     loc_180043957
0x180043833  lea     rcx, [rbp+0B0h+var_F8]; this
0x180043837  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x18004383c  mov     eax, 57h ; 'W'
0x180043841  jmp     loc_180043901
0x180043846  test    rdx, rdx
0x180043849  lea     rcx, [rax-2]
0x18004384d  cmovnz  rcx, rax
0x180043851  mov     [rcx], si
0x180043854  jnz     short loc_18004385E
0x180043856  mov     [r9-268h], si
0x18004385e  test    edi, edi
0x180043860  jnz     loc_180043929
0x180043866  mov     rcx, rbx; lpCriticalSection
0x180043869  call    cs:__imp_LeaveCriticalSection
0x180043870  nop     dword ptr [rax+rax+00h]
0x180043875  test    r12b, r12b
0x180043878  jnz     short loc_180043880
0x18004387a  mov     r15d, 8
0x180043880  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x180043884  call    cs:__imp_EnterCriticalSection
0x18004388b  nop     dword ptr [rax+rax+00h]
0x180043890  mov     rcx, [rbp+0B0h+hKey]; hKey
0x180043894  test    rcx, rcx
0x180043897  jz      short loc_1800438B0
0x180043899  call    cs:__imp_RegCloseKey
0x1800438a0  nop     dword ptr [rax+rax+00h]
0x1800438a5  mov     rax, [rbp+0B0h+hMem]
0x1800438a9  mov     [rbp+0B0h+hKey], rsi
0x1800438ad  mov     [rax], si
0x1800438b0  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x1800438b4  call    cs:__imp_LeaveCriticalSection
0x1800438bb  nop     dword ptr [rax+rax+00h]
0x1800438c0  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x1800438c4  call    cs:__imp_DeleteCriticalSection
0x1800438cb  nop     dword ptr [rax+rax+00h]
0x1800438d0  mov     ebx, 1
0x1800438d5  cmp     [rbp+0B0h+var_C8], ebx
0x1800438d8  jle     short loc_1800438EA
0x1800438da  mov     rcx, [rbp+0B0h+hMem]; hMem
0x1800438de  call    cs:__imp_GlobalFree
0x1800438e5  nop     dword ptr [rax+rax+00h]
0x1800438ea  lea     rax, [rbp+0B0h+var_C0]
0x1800438ee  mov     [rbp+0B0h+var_C8], ebx
0x1800438f1  lea     rcx, [rbp+0B0h+var_F8]; this
0x1800438f5  mov     [rbp+0B0h+hMem], rax
0x1800438f9  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x1800438fe  mov     eax, r15d
0x180043901  mov     rcx, [rbp+0B0h+var_40]
0x180043905  xor     rcx, rsp; StackCookie
0x180043908  call    __security_check_cookie
0x18004390d  mov     rbx, [rsp+1B0h+arg_0]
0x180043915  add     rsp, 180h
0x18004391c  pop     r15
0x18004391e  pop     r14
0x180043920  pop     r13
0x180043922  pop     r12
0x180043924  pop     rdi
0x180043925  pop     rsi
0x180043926  pop     rbp
0x180043927  retn
0x180043929  lea     ecx, [rdi-1]
0x18004392c  mov     rdi, [r14]
0x18004392f  imul    rsi, rcx, 388h
0x180043936  call    cs:__imp_GetCurrentThreadId
0x18004393d  nop     dword ptr [rax+rax+00h]
0x180043942  mov     [rsi+rdi], eax
0x180043945  xor     esi, esi
0x180043947  mov     eax, [rsp+1B0h+var_148]
0x18004394b  mov     [r14+398h], eax
0x180043952  jmp     loc_180043866
0x180043957  dec     esi
0x180043959  mov     [rsp+1B0h+dwIndex], esi
0x18004395d  jmp     loc_18004371F
0x180043962  mov     rdi, [rbp+0B0h+lpcchValueName]
0x180043966  test    sil, sil
0x180043969  jnz     loc_180043D49
0x18004396f  mov     r14, cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA; EnumEntityList * g_pEnumAssemblies
0x180043976  lea     rbx, [r14+3A0h]
0x18004397d  mov     rcx, rbx; lpCriticalSection
0x180043980  call    cs:__imp_EnterCriticalSection
0x180043987  nop     dword ptr [rax+rax+00h]
0x18004398c  call    cs:__imp_GetCurrentThreadId
0x180043993  nop     dword ptr [rax+rax+00h]
0x180043998  mov     r8d, [r14+398h]
0x18004399f  xor     esi, esi
0x1800439a1  mov     ecx, esi
0x1800439a3  cmp     ecx, r8d
0x1800439a6  jnb     loc_180043A92
0x1800439ac  lea     r9d, [rcx+1]
0x1800439b0  movsxd  rcx, ecx
0x1800439b3  imul    rdx, rcx, 388h
0x1800439ba  mov     rcx, [r14]
0x1800439bd  cmp     [rdx+rcx], eax
0x1800439c0  jnz     loc_180043A8A
  ... truncated ...
```
