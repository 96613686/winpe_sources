# EnumAssemblies(ulong,ushort const *,ulong,ushort *,ulong *,ushort *,ulong *)

- ea: `0x18001bb30`
- end: `0x18001c40d`
- name: `?EnumAssemblies@@YAIKPEBGKPEAGPEAK12@Z`
- size: `2269`
- prototype: `unsigned int __fastcall(unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ab38`
- `0x18001b230`

## callees

- `0x180015950`
- `0x18001b188`
- `0x18001bb30`
- `0x18001cab0`
- `0x18001d960`
- `0x1800227d0`
- `0x18004fc48`
- `0x1801358e8`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x18001c1da`
- `ADVAPI32!RegEnumValueW` at `0x18001c1da`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001c2f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001c2f4`
- `ADVAPI32!RegQueryValueExW` at `0x18001c342`
- `ADVAPI32!RegQueryValueExW` at `0x18001c342`
- `ADVAPI32!RegCloseKey` at `0x18001bebd`
- `ADVAPI32!RegCloseKey` at `0x18001c13f`
- `ADVAPI32!RegCloseKey` at `0x18001bebd`
- `ADVAPI32!RegCloseKey` at `0x18001c13f`
- `KERNEL32!InitializeCriticalSection` at `0x18001bd75`
- `KERNEL32!InitializeCriticalSection` at `0x18001c23f`
- `KERNEL32!InitializeCriticalSection` at `0x18001bd75`
- `KERNEL32!InitializeCriticalSection` at `0x18001c23f`
- `KERNEL32!DeleteCriticalSection` at `0x18001bedc`
- `KERNEL32!DeleteCriticalSection` at `0x18001c15e`
- `KERNEL32!DeleteCriticalSection` at `0x18001bedc`
- `KERNEL32!DeleteCriticalSection` at `0x18001c15e`
- `KERNEL32!LeaveCriticalSection` at `0x18001bbeb`
- `KERNEL32!LeaveCriticalSection` at `0x18001bc75`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd30`
- `KERNEL32!LeaveCriticalSection` at `0x18001be99`
- `KERNEL32!LeaveCriticalSection` at `0x18001bed2`
- `KERNEL32!LeaveCriticalSection` at `0x18001c154`
- `KERNEL32!LeaveCriticalSection` at `0x18001c36b`
- `KERNEL32!LeaveCriticalSection` at `0x18001bbeb`
- `KERNEL32!LeaveCriticalSection` at `0x18001bc75`
- `KERNEL32!LeaveCriticalSection` at `0x18001bd30`
- `KERNEL32!LeaveCriticalSection` at `0x18001be99`
- `KERNEL32!LeaveCriticalSection` at `0x18001bed2`
- `KERNEL32!LeaveCriticalSection` at `0x18001c154`
- `KERNEL32!LeaveCriticalSection` at `0x18001c36b`
- `KERNEL32!GetCurrentThreadId` at `0x18001bc08`
- `KERNEL32!GetCurrentThreadId` at `0x18001bf41`
- `KERNEL32!GetCurrentThreadId` at `0x18001bf8b`
- `KERNEL32!GetCurrentThreadId` at `0x18001bc08`
- `KERNEL32!GetCurrentThreadId` at `0x18001bf41`
- `KERNEL32!GetCurrentThreadId` at `0x18001bf8b`
- `KERNEL32!EnterCriticalSection` at `0x18001bbd5`
- `KERNEL32!EnterCriticalSection` at `0x18001bc02`
- `KERNEL32!EnterCriticalSection` at `0x18001beae`
- `KERNEL32!EnterCriticalSection` at `0x18001bf85`
- `KERNEL32!EnterCriticalSection` at `0x18001c130`
- `KERNEL32!EnterCriticalSection` at `0x18001bbd5`
- `KERNEL32!EnterCriticalSection` at `0x18001bc02`
- `KERNEL32!EnterCriticalSection` at `0x18001beae`
- `KERNEL32!EnterCriticalSection` at `0x18001bf85`
- `KERNEL32!EnterCriticalSection` at `0x18001c130`
- `KERNEL32!GlobalAlloc` at `0x18001bcef`
- `KERNEL32!GlobalAlloc` at `0x18001bcef`
- `KERNEL32!GlobalFree` at `0x18001bef0`
- `KERNEL32!GlobalFree` at `0x18001c16e`
- `KERNEL32!GlobalFree` at `0x18001bef0`
- `KERNEL32!GlobalFree` at `0x18001c16e`

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
0x18001bb30  mov     [rsp-8+arg_0], rbx
0x18001bb35  push    rbp
0x18001bb36  push    rsi
0x18001bb37  push    rdi
0x18001bb38  push    r12
0x18001bb3a  push    r13
0x18001bb3c  push    r14
0x18001bb3e  push    r15
0x18001bb40  lea     rbp, [rsp-80h]
0x18001bb45  sub     rsp, 180h
0x18001bb4c  mov     rax, cs:__security_cookie
0x18001bb53  xor     rax, rsp
0x18001bb56  mov     [rbp+0B0h+var_40], rax
0x18001bb5a  mov     rbx, [rbp+0B0h+arg_20]
0x18001bb61  mov     r15d, ecx
0x18001bb64  mov     r12, [rbp+0B0h+arg_28]
0x18001bb6b  lea     rcx, [rbp+0B0h+var_F8]; this
0x18001bb6f  mov     r14, [rbp+0B0h+arg_30]
0x18001bb76  mov     rsi, r9
0x18001bb79  mov     [rbp+0B0h+lpcchValueName], rbx
0x18001bb7d  mov     rdi, rdx
0x18001bb80  mov     [rbp+0B0h+var_100], r12
0x18001bb84  mov     [rbp+0B0h+var_110], r14
0x18001bb88  mov     [rbp+0B0h+lpValueName], r9
0x18001bb8c  mov     [rsp+1B0h+var_140], r8d
0x18001bb91  mov     [rbp+0B0h+var_128], rdx
0x18001bb95  call    ??0CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(void)
0x18001bb9a  xor     r13d, r13d
0x18001bb9d  test    rdi, rdi
0x18001bba0  jz      loc_18001BE63
0x18001bba6  test    rsi, rsi
0x18001bba9  jz      loc_18001BE63
0x18001bbaf  test    rbx, rbx
0x18001bbb2  jz      loc_18001BE63
0x18001bbb8  test    r12, r12
0x18001bbbb  jnz     loc_18001BCD7
0x18001bbc1  cmp     r15d, 1
0x18001bbc5  ja      loc_18001BE63
0x18001bbcb  lea     rbx, ?g_csEnumLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEnumLock
0x18001bbd2  mov     rcx, rbx; lpCriticalSection
0x18001bbd5  call    cs:__imp_EnterCriticalSection
0x18001bbdb  cmp     cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA, r13; EnumEntityList * g_pEnumAssemblies
0x18001bbe2  jz      loc_18001BCE5
0x18001bbe8  mov     rcx, rbx; lpCriticalSection
0x18001bbeb  call    cs:__imp_LeaveCriticalSection
0x18001bbf1  mov     rdi, cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA; EnumEntityList * g_pEnumAssemblies
0x18001bbf8  lea     rbx, [rdi+3A0h]
0x18001bbff  mov     rcx, rbx; lpCriticalSection
0x18001bc02  call    cs:__imp_EnterCriticalSection
0x18001bc08  call    cs:__imp_GetCurrentThreadId
0x18001bc0e  mov     ecx, r13d
0x18001bc11  cmp     ecx, [rdi+398h]
0x18001bc17  jnb     loc_18001BD12
0x18001bc1d  lea     r8d, [rcx+1]
0x18001bc21  movsxd  rcx, ecx
0x18001bc24  imul    rdx, rcx, 388h
0x18001bc2b  mov     rcx, [rdi]
0x18001bc2e  cmp     [rdx+rcx], eax
0x18001bc31  jnz     loc_18001BCCF
0x18001bc37  test    r8d, r8d
0x18001bc3a  jz      loc_18001BD12
0x18001bc40  mov     rdi, rcx
0x18001bc43  movsxd  rax, r8d
0x18001bc46  imul    rsi, rax, 388h
0x18001bc4d  mov     r13d, [rsi+rcx-384h]
0x18001bc55  mov     ecx, [rsi+rcx-380h]
0x18001bc5c  mov     r12d, [rsi+rdi-378h]
0x18001bc64  mov     [rsp+1B0h+dwIndex], ecx
0x18001bc68  mov     rcx, rbx; lpCriticalSection
0x18001bc6b  mov     [rsp+1B0h+var_148], r13d
0x18001bc70  mov     [rsp+1B0h+var_144], r12d
0x18001bc75  call    cs:__imp_LeaveCriticalSection
0x18001bc7b  add     rdi, 0FFFFFFFFFFFFFD98h
0x18001bc82  add     rdi, rsi
0x18001bc85  mov     esi, [rsp+1B0h+dwIndex]
0x18001bc89  mov     rdx, [rbp+0B0h+var_128]
0x18001bc8d  sub     rdx, rdi
0x18001bc90  movzx   ecx, word ptr [rdi]
0x18001bc93  movzx   eax, word ptr [rdi+rdx]
0x18001bc97  sub     ecx, eax
0x18001bc99  jnz     short loc_18001BCA3
0x18001bc9b  add     rdi, 2
0x18001bc9f  test    eax, eax
0x18001bca1  jnz     short loc_18001BC90
0x18001bca3  mov     edi, [rsp+1B0h+var_140]
0x18001bca7  xor     edx, edx
0x18001bca9  test    ecx, ecx
0x18001bcab  jz      loc_18001BD3B
0x18001bcb1  test    edi, edi
0x18001bcb3  jnz     loc_18001BE63
0x18001bcb9  mov     r13d, edx
0x18001bcbc  mov     [rsp+1B0h+var_148], edx
0x18001bcc0  mov     esi, edx
0x18001bcc2  mov     [rsp+1B0h+dwIndex], edx
0x18001bcc6  mov     [rsp+1B0h+var_144], edx
0x18001bcca  jmp     loc_18001BD55
0x18001bccf  mov     ecx, r8d
0x18001bcd2  jmp     loc_18001BC11
0x18001bcd7  test    r14, r14
0x18001bcda  jnz     loc_18001BBC1
0x18001bce0  jmp     loc_18001BE63
0x18001bce5  mov     edx, 3C8h; dwBytes
0x18001bcea  mov     ecx, 40h ; '@'; uFlags
0x18001bcef  call    cs:__imp_GlobalAlloc
0x18001bcf5  mov     cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA, rax; EnumEntityList * g_pEnumAssemblies
0x18001bcfc  test    rax, rax
0x18001bcff  jz      loc_18001C368
0x18001bd05  mov     rcx, rax; this
0x18001bd08  call    ?Init@EnumEntityList@@QEAAXXZ; EnumEntityList::Init(void)
0x18001bd0d  jmp     loc_18001BBE8
0x18001bd12  xor     esi, esi
0x18001bd14  mov     [rsp+1B0h+var_148], r13d
0x18001bd19  or      r12d, 0FFFFFFFFh
0x18001bd1d  mov     [rsp+1B0h+dwIndex], esi
0x18001bd21  mov     rcx, rbx; lpCriticalSection
0x18001bd24  mov     [rsp+1B0h+var_144], r12d
0x18001bd29  lea     rdi, Default
0x18001bd30  call    cs:__imp_LeaveCriticalSection
0x18001bd36  jmp     loc_18001BC89
0x18001bd3b  cmp     r12d, edi
0x18001bd3e  jz      loc_18001BE59
0x18001bd44  inc     r12d
0x18001bd47  mov     [rsp+1B0h+var_144], r12d
0x18001bd4c  cmp     r12d, edi
0x18001bd4f  jnz     loc_18001BCB1
0x18001bd55  xorps   xmm0, xmm0
0x18001bd58  mov     [rbp+0B0h+var_C0], dx
0x18001bd5c  lea     rax, [rbp+0B0h+var_C0]
0x18001bd60  movdqa  xmmword ptr [rbp+0B0h+hKey], xmm0
0x18001bd65  mov     ebx, 1
0x18001bd6a  mov     [rbp+0B0h+hMem], rax
0x18001bd6e  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x18001bd72  mov     [rbp+0B0h+var_C8], ebx
0x18001bd75  call    cs:__imp_InitializeCriticalSection
0x18001bd7b  xor     r9d, r9d
0x18001bd7e  mov     [rsp+1B0h+var_150], bl
0x18001bd82  mov     ecx, r9d
0x18001bd85  mov     r12b, bl
0x18001bd88  mov     [rsp+1B0h+var_138], ecx
0x18001bd8c  test    r14, r14
0x18001bd8f  jz      short loc_18001BD98
0x18001bd91  mov     ecx, [r14]
0x18001bd94  mov     [rsp+1B0h+var_138], ecx
0x18001bd98  mov     rdi, [rbp+0B0h+lpcchValueName]
0x18001bd9c  lea     r8, aAssemblies_0; "Assemblies"
0x18001bda3  test    bl, r15b
0x18001bda6  lea     rax, aWin32assemblie_0; "Win32Assemblies"
0x18001bdad  cmovz   rax, r8
0x18001bdb1  mov     edx, [rdi]
0x18001bdb3  mov     [rbp+0B0h+var_120], edx
0x18001bdb6  mov     [rbp+0B0h+var_118], rax
0x18001bdba  test    r14, r14
0x18001bdbd  jz      short loc_18001BDC2
0x18001bdbf  mov     [r14], ecx
0x18001bdc2  mov     [rdi], edx
0x18001bdc4  cmp     r13d, 0FFFFFFFFh
0x18001bdc8  jnz     short loc_18001BE47
0x18001bdca  mov     rsi, [rbp+0B0h+var_118]
0x18001bdce  xor     r14d, r14d
0x18001bdd1  mov     rdi, [rbp+0B0h+var_128]
0x18001bdd5  cmp     r13d, 0FFFFFFFFh
0x18001bdd9  mov     ebx, r14d
0x18001bddc  cmovnz  ebx, r13d
0x18001bde0  lea     rax, [rbp+0B0h+hKey]
0x18001bde4  mov     byte ptr [rsp+1B0h+lpType], r14b
0x18001bde9  mov     r9, rdi
0x18001bdec  mov     [rsp+1B0h+lpReserved], rax
0x18001bdf1  mov     r8, rsi
0x18001bdf4  xor     edx, edx
0x18001bdf6  mov     ecx, ebx
0x18001bdf8  call    ?OpenSpecificUsersAdvertisedSubKeyPacked@@YAKW4iaaAppAssignment@@PEBG11AEAVCRegHandle@@_N@Z; OpenSpecificUsersAdvertisedSubKeyPacked(iaaAppAssignment,ushort const *,ushort const *,ushort const *,CRegHandle &,bool)
0x18001bdfd  mov     r15d, eax
0x18001be00  test    eax, eax
0x18001be02  jz      short loc_18001BE0A
0x18001be04  cmp     r13d, 0FFFFFFFFh
0x18001be08  jz      short loc_18001BE3E
0x18001be0a  mov     r14, [rbp+0B0h+var_110]
0x18001be0e  mov     ebx, 1
0x18001be13  mov     esi, [rsp+1B0h+dwIndex]
0x18001be17  mov     r12b, [rsp+1B0h+var_150]
0x18001be1c  mov     rdi, [rbp+0B0h+lpcchValueName]
0x18001be20  cmp     r13d, 2
0x18001be24  jg      loc_18001C402
0x18001be2a  cmp     r15d, 2
0x18001be2e  jnz     loc_18001C19A
0x18001be34  add     r13d, ebx
0x18001be37  mov     [rsp+1B0h+var_148], r13d
0x18001be3c  jmp     short loc_18001BDC4
0x18001be3e  inc     ebx
0x18001be40  cmp     ebx, 3
0x18001be43  jge     short loc_18001BE0A
0x18001be45  jmp     short loc_18001BDE0
0x18001be47  mov     r15d, 2
0x18001be4d  cmp     r13d, 3
0x18001be51  jl      loc_18001BDCA
0x18001be57  jmp     short loc_18001BE20
0x18001be59  cmp     r12d, 0FFFFFFFFh
0x18001be5d  jnz     loc_18001BF5C
0x18001be63  lea     rcx, [rbp+0B0h+var_F8]; this
0x18001be67  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x18001be6c  mov     eax, 57h ; 'W'
0x18001be71  jmp     loc_18001BF0D
0x18001be76  test    rdx, rdx
0x18001be79  lea     rcx, [rax-2]
0x18001be7d  cmovnz  rcx, rax
0x18001be81  mov     [rcx], si
0x18001be84  jnz     short loc_18001BE8E
0x18001be86  mov     [r9-268h], si
0x18001be8e  test    edi, edi
0x18001be90  jnz     loc_18001BF34
0x18001be96  mov     rcx, rbx; lpCriticalSection
0x18001be99  call    cs:__imp_LeaveCriticalSection
0x18001be9f  test    r12b, r12b
0x18001bea2  jnz     short loc_18001BEAA
0x18001bea4  mov     r15d, 8
0x18001beaa  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x18001beae  call    cs:__imp_EnterCriticalSection
0x18001beb4  mov     rcx, [rbp+0B0h+hKey]; hKey
0x18001beb8  test    rcx, rcx
0x18001bebb  jz      short loc_18001BECE
0x18001bebd  call    cs:__imp_RegCloseKey
0x18001bec3  mov     rax, [rbp+0B0h+hMem]
0x18001bec7  mov     [rbp+0B0h+hKey], rsi
0x18001becb  mov     [rax], si
0x18001bece  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x18001bed2  call    cs:__imp_LeaveCriticalSection
0x18001bed8  lea     rcx, [rbp+0B0h+CriticalSection]; lpCriticalSection
0x18001bedc  call    cs:__imp_DeleteCriticalSection
0x18001bee2  mov     ebx, 1
0x18001bee7  cmp     [rbp+0B0h+var_C8], ebx
0x18001beea  jle     short loc_18001BEF6
0x18001beec  mov     rcx, [rbp+0B0h+hMem]; hMem
0x18001bef0  call    cs:__imp_GlobalFree
0x18001bef6  lea     rax, [rbp+0B0h+var_C0]
0x18001befa  mov     [rbp+0B0h+var_C8], ebx
0x18001befd  lea     rcx, [rbp+0B0h+var_F8]; this
0x18001bf01  mov     [rbp+0B0h+hMem], rax
0x18001bf05  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x18001bf0a  mov     eax, r15d
0x18001bf0d  mov     rcx, [rbp+0B0h+var_40]
0x18001bf11  xor     rcx, rsp; StackCookie
0x18001bf14  call    __security_check_cookie
0x18001bf19  mov     rbx, [rsp+1B0h+arg_0]
0x18001bf21  add     rsp, 180h
0x18001bf28  pop     r15
0x18001bf2a  pop     r14
0x18001bf2c  pop     r13
0x18001bf2e  pop     r12
0x18001bf30  pop     rdi
0x18001bf31  pop     rsi
0x18001bf32  pop     rbp
0x18001bf33  retn
0x18001bf34  lea     ecx, [rdi-1]
0x18001bf37  mov     rdi, [r14]
0x18001bf3a  imul    rsi, rcx, 388h
0x18001bf41  call    cs:__imp_GetCurrentThreadId
0x18001bf47  mov     [rsi+rdi], eax
0x18001bf4a  xor     esi, esi
0x18001bf4c  mov     eax, [rsp+1B0h+var_148]
0x18001bf50  mov     [r14+398h], eax
0x18001bf57  jmp     loc_18001BE96
0x18001bf5c  dec     esi
0x18001bf5e  mov     [rsp+1B0h+dwIndex], esi
0x18001bf62  jmp     loc_18001BD55
0x18001bf67  mov     rdi, [rbp+0B0h+lpcchValueName]
0x18001bf6b  test    sil, sil
0x18001bf6e  jnz     loc_18001C30E
0x18001bf74  mov     r14, cs:?g_pEnumAssemblies@@3PEAVEnumEntityList@@EA; EnumEntityList * g_pEnumAssemblies
0x18001bf7b  lea     rbx, [r14+3A0h]
0x18001bf82  mov     rcx, rbx; lpCriticalSection
0x18001bf85  call    cs:__imp_EnterCriticalSection
0x18001bf8b  call    cs:__imp_GetCurrentThreadId
0x18001bf91  mov     r8d, [r14+398h]
0x18001bf98  xor     esi, esi
0x18001bf9a  mov     ecx, esi
0x18001bf9c  cmp     ecx, r8d
0x18001bf9f  jnb     loc_18001C08B
0x18001bfa5  lea     r9d, [rcx+1]
0x18001bfa9  movsxd  rcx, ecx
0x18001bfac  imul    rdx, rcx, 388h
0x18001bfb3  mov     rcx, [r14]
0x18001bfb6  cmp     [rdx+rcx], eax
0x18001bfb9  jnz     loc_18001C083
0x18001bfbf  test    r9d, r9d
0x18001bfc2  jz      loc_18001C08B
0x18001bfc8  mov     edi, esi
0x18001bfca  mov     [rsp+1B0h+var_148], esi
0x18001bfce  mov     rax, [r14]
0x18001bfd1  mov     r11d, 1
0x18001bfd7  mov     ecx, [rsp+1B0h+dwIndex]
0x18001bfdb  mov     r12b, r11b
0x18001bfde  mov     r10, [rbp+0B0h+var_128]
0x18001bfe2  movsxd  r8, r9d
0x18001bfe5  imul    rdx, r8, 388h
0x18001bfec  imul    r9, r8, 388h
0x18001bff3  mov     [rax+rdx-384h], r13d
0x18001bffb  inc     ecx
0x18001bffd  mov     rax, [r14]
0x18001c000  mov     [rax+rdx-380h], ecx
0x18001c007  mov     rax, [r14]
  ... truncated ...
```
