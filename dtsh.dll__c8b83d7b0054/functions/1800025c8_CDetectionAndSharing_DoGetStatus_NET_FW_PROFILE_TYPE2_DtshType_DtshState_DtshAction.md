# CDetectionAndSharing::DoGetStatus(NET_FW_PROFILE_TYPE2_ *,_DtshType,_DtshState *,_DtshAction *)

- ea: `0x1800025c8`
- end: `0x180002b5d`
- name: `?DoGetStatus@CDetectionAndSharing@@AEAAJPEAW4NET_FW_PROFILE_TYPE2_@@W4_DtshType@@PEAW4_DtshState@@PEAW4_DtshAction@@@Z`
- size: `1429`
- prototype: `__int64 __fastcall(__int64, enum NET_FW_PROFILE_TYPE2_ *, int, _DWORD *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800030d0`
- `0x180003100`

## callees

- `0x1800025a0`
- `0x1800025c8`
- `0x180002e2c`
- `0x180002e90`
- `0x180002f84`
- `0x180003128`
- `0x180003410`
- `0x180003570`
- `0x180005010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180002a90`
- `ADVAPI32!RegQueryValueExW` at `0x180002a90`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a4d`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a4d`
- `ADVAPI32!RegCloseKey` at `0x180002ac6`
- `ADVAPI32!RegCloseKey` at `0x180002ac6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000295d`
- `OLEAUT32!__imp_SysAllocString` at `0x18000295d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029e8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029e8`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::DoGetStatus(
        __int64 a1,
        enum NET_FW_PROFILE_TYPE2_ *a2,
        int a3,
        _DWORD *a4,
        int *a5)
{
  int v5; // r14d
  int FWServiceInfo; // ebx
  int v10; // r13d
  int v11; // r12d
  __int64 v12; // rcx
  unsigned int i; // esi
  unsigned int v14; // r14d
  int v15; // eax
  bool v16; // zf
  enum NET_FW_PROFILE_TYPE2_ *v17; // rdx
  _QWORD *v18; // rsi
  int v19; // r8d
  unsigned int j; // edx
  __int64 v21; // rcx
  unsigned int v22; // ecx
  __int64 v23; // r8
  __int64 v24; // rax
  unsigned __int64 v25; // r9
  _QWORD *v26; // rdx
  int v27; // r10d
  __int64 v28; // rdx
  unsigned int k; // r8d
  __int64 v30; // r9
  __int64 v31; // rcx
  _DWORD *v32; // rcx
  __int64 v33; // rcx
  int v34; // esi
  int v35; // edx
  int v36; // r15d
  unsigned int v37; // r12d
  __int64 v38; // rax
  __int64 v39; // rcx
  OLECHAR *v40; // r13
  unsigned int v41; // eax
  HKEY v42; // rbx
  int v43; // eax
  _WORD v44[2]; // [rsp+30h] [rbp-40h] BYREF
  enum NET_FW_PROFILE_TYPE2_ v45; // [rsp+34h] [rbp-3Ch] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-38h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-34h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-30h] BYREF
  int v49; // [rsp+48h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-24h] BYREF
  int v51; // [rsp+50h] [rbp-20h]
  int v52; // [rsp+54h] [rbp-1Ch]
  int v53; // [rsp+58h] [rbp-18h] BYREF
  int v54; // [rsp+5Ch] [rbp-14h] BYREF
  int v55; // [rsp+60h] [rbp-10h]

  v5 = 0;
  if ( !a4 )
    return 2147942487LL;
  v45 = 0;
  v53 = 0;
  v49 = 0;
  v54 = 0;
  FWServiceInfo = CDetectionAndSharing::GetFWServiceInfo((CDetectionAndSharing *)a1, &v49, &v54);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  FWServiceInfo = CDetectionAndSharing::InitializeServiceStatusArray((CDetectionAndSharing *)a1);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  Type = 0;
  LOWORD(v10) = 0;
  v51 = 0;
  LOWORD(v11) = 0;
  v52 = 0;
  if ( !v49 )
    goto LABEL_33;
  FWServiceInfo = CDetectionAndSharing::GetFwPolicy((CDetectionAndSharing *)a1);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  FWServiceInfo = (*(__int64 (__fastcall **)(_QWORD, enum NET_FW_PROFILE_TYPE2_ *))(**(_QWORD **)(a1 + 72) + 56LL))(
                    *(_QWORD *)(a1 + 72),
                    &v45);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  if ( a2 && *a2 && v45 != *a2 )
  {
    v45 = *a2;
  }
  else
  {
    v12 = *(_QWORD *)(a1 + 72);
    Type = 1;
    FWServiceInfo = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 224LL))(v12, &v53);
    if ( FWServiceInfo < 0 )
      return (unsigned int)FWServiceInfo;
  }
  for ( i = 0; i < 3; ++i )
  {
    v44[0] = 0;
    LOWORD(hKey) = 0;
    v14 = dword_180007130[i] & v45;
    if ( v14 )
    {
      FWServiceInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *))(**(_QWORD **)(a1 + 72) + 64LL))(
                        *(_QWORD *)(a1 + 72),
                        v14,
                        v44);
      if ( FWServiceInfo < 0 )
        return (unsigned int)FWServiceInfo;
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HKEY *))(**(_QWORD **)(a1 + 72) + 96LL))(
              *(_QWORD *)(a1 + 72),
              v14,
              &hKey);
      v5 = 0;
      FWServiceInfo = v15;
      if ( v15 < 0 )
        return (unsigned int)FWServiceInfo;
      v16 = (_WORD)v10 == 0xFFFF;
      v10 = 0xFFFF;
      if ( !v16 )
        v10 = v44[0];
      v51 = v10;
      if ( (_WORD)v11 == 0xFFFF )
        v11 = 0xFFFF;
      else
        v11 = (unsigned __int16)hKey;
      v52 = v11;
    }
    else
    {
      v5 = 0;
    }
  }
  if ( (_WORD)v10 == 0xFFFF && !(_WORD)v11 )
  {
    if ( a2 && *a2 )
      v17 = a2;
    else
      v17 = 0;
    FWServiceInfo = CDetectionAndSharing::GetFwGroupsStatus((CDetectionAndSharing *)a1, v17);
    if ( FWServiceInfo < 0 )
      return (unsigned int)FWServiceInfo;
    v55 = 0;
    v18 = (_QWORD *)(a1 + 88);
  }
  else
  {
LABEL_33:
    v55 = IsThirdPartyFwRunning();
    if ( !v49 || (_WORD)v10 != 0xFFFF || (v19 = 0, (_WORD)v11 != 0xFFFF) )
      v19 = 1;
    v18 = (_QWORD *)(a1 + 88);
    for ( j = 0; (unsigned __int64)j < *v18; *(_DWORD *)(32 * v21 + *(_QWORD *)(a1 + 80) + 28) = v19 )
    {
      v21 = j;
      if ( (unsigned __int64)j >= *(_QWORD *)(a1 + 88) )
        goto LABEL_107;
      ++j;
    }
  }
  FWServiceInfo = CDetectionAndSharing::GetWindowsServicesStatus((CDetectionAndSharing *)a1);
  if ( FWServiceInfo < 0 )
    return (unsigned int)FWServiceInfo;
  v22 = 0;
  if ( *v18 )
  {
    while ( (unsigned __int64)v22 < *(_QWORD *)(a1 + 88) )
    {
      v23 = *(_QWORD *)(a1 + 80);
      v24 = 32LL * v22;
      if ( *(_DWORD *)(v24 + v23 + 28) && *(_DWORD *)(v24 + v23 + 24) )
      {
        v25 = *(int *)(v24 + v23 + 16);
        v26 = (_QWORD *)(a1 + 112);
        if ( v25 >= *(_QWORD *)(a1 + 120) )
          goto LABEL_107;
        ++*(_DWORD *)(*v26 + 8 * v25 + 4);
      }
      else
      {
        v26 = (_QWORD *)(a1 + 112);
      }
      if ( (unsigned __int64)++v22 >= *v18 )
        goto LABEL_51;
    }
    goto LABEL_107;
  }
  v26 = (_QWORD *)(a1 + 112);
LABEL_51:
  v27 = a3;
  if ( a3 == 4 )
  {
    if ( *(_QWORD *)(a1 + 120) <= 4u )
      goto LABEL_107;
    v28 = *(_QWORD *)(a1 + 112);
    for ( k = 0; k < 4; ++k )
    {
      v30 = k;
      if ( (unsigned __int64)k >= *(_QWORD *)(a1 + 120) )
        goto LABEL_107;
      v31 = *(_QWORD *)(a1 + 112);
      *(_DWORD *)(v28 + 32) += *(_DWORD *)(v31 + 8 * v30);
      *(_DWORD *)(v28 + 36) += *(_DWORD *)(v31 + 8 * v30 + 4);
    }
    v26 = (_QWORD *)(a1 + 112);
  }
  else if ( a3 == 3 )
  {
    if ( v26[1] <= 3u )
      goto LABEL_107;
    v32 = (_DWORD *)*v26;
    v32[6] = *(_DWORD *)*v26 + *(_DWORD *)(*v26 + 8LL);
    v32[7] = v32[3] + v32[1];
  }
  if ( (unsigned __int64)a3 >= v26[1] )
LABEL_107:
    ATL::AtlThrowImpl(-2147024809);
  v33 = *v26;
  v34 = 0;
  v35 = *(_DWORD *)(*v26 + 8LL * a3 + 4);
  if ( v35 )
  {
    LOBYTE(v34) = *(_DWORD *)(v33 + 8LL * a3) != v35;
    ++v34;
  }
  v36 = 0;
  *(_DWORD *)Data = 0;
  v37 = 0;
  v44[0] = 0;
  FWServiceInfo = 0;
  LODWORD(hKey) = v45;
  do
  {
    if ( (unsigned __int64)v37 >= *(_QWORD *)(a1 + 88) )
      goto LABEL_81;
    v38 = *(_QWORD *)(a1 + 80);
    v39 = 32LL * v37;
    if ( v27 != *(_DWORD *)(v39 + v38 + 16) )
      goto LABEL_78;
    v40 = SysAllocString(*(const OLECHAR **)(v39 + v38 + 8));
    if ( !v40 )
      return (unsigned int)-2147024882;
    v41 = (unsigned int)hKey;
    cbData = 1;
    while ( (dword_180007130[v36] & v41) == 0 )
    {
LABEL_73:
      if ( (unsigned int)++v36 >= 3 )
        goto LABEL_76;
    }
    FWServiceInfo = (*(__int64 (__fastcall **)(_QWORD, _QWORD, OLECHAR *, _WORD *))(**(_QWORD **)(a1 + 72) + 168LL))(
                      *(_QWORD *)(a1 + 72),
                      dword_180007130[v36] & v41,
                      v40,
                      v44);
    if ( cbData )
    {
      *(_DWORD *)Data = v44[0];
      cbData = 0;
LABEL_72:
      v41 = (unsigned int)hKey;
      goto LABEL_73;
    }
    if ( *(_WORD *)Data == v44[0] )
      goto LABEL_72;
    v5 = 1;
LABEL_76:
    SysFreeString(v40);
    v36 = 0;
    if ( v5 )
    {
      if ( FWServiceInfo < 0 )
        return (unsigned int)FWServiceInfo;
LABEL_81:
      if ( Type )
      {
        if ( v5 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Dtsh",
                  0,
                  0x20019u,
                  &hKey) )
          {
            v42 = hKey;
            *(_DWORD *)Data = 0;
            Type = 0;
            cbData = 4;
            if ( !RegQueryValueExW(hKey, L"GlobalDtshStateOnConflict", 0, &Type, Data, &cbData) && Type == 4 )
              v34 = *(_DWORD *)Data != 0;
            if ( v42 )
              RegCloseKey(v42);
          }
        }
      }
      if ( v49 && (_WORD)v51 == 0xFFFF )
      {
        v43 = 0;
        if ( (_WORD)v52 == 0xFFFF )
          v43 = 2;
      }
      else
      {
        v43 = 1;
      }
      if ( v53 == 1 )
        v43 = 4;
      if ( v54 )
        v43 = 3;
      if ( v55 )
        v43 = 5;
      if ( a5 )
        *a5 = v43;
      *a4 = v34;
      if ( a2 )
        *a2 = v45;
      return 0;
    }
    v27 = a3;
LABEL_78:
    ++v37;
  }
  while ( FWServiceInfo >= 0 );
  return (unsigned int)FWServiceInfo;
}

```

## disassembly

```asm
0x1800025c8  mov     rax, rsp
0x1800025cb  mov     [rax+8], rbx
0x1800025cf  mov     [rax+20h], r9
0x1800025d3  mov     [rax+18h], r8d
0x1800025d7  mov     [rax+10h], rdx
0x1800025db  push    rbp
0x1800025dc  push    rsi
0x1800025dd  push    rdi
0x1800025de  push    r12
0x1800025e0  push    r13
0x1800025e2  push    r14
0x1800025e4  push    r15
0x1800025e6  mov     rbp, rsp
0x1800025e9  sub     rsp, 70h
0x1800025ed  xor     r14d, r14d
0x1800025f0  mov     r15, rdx
0x1800025f3  mov     rdi, rcx
0x1800025f6  test    r9, r9
0x1800025f9  jnz     short loc_180002605
0x1800025fb  mov     eax, 80070057h
0x180002600  jmp     loc_180002B3A
0x180002605  lea     r8, [rbp+var_14]; int *
0x180002609  mov     [rbp+var_3C], r14d
0x18000260d  lea     rdx, [rbp+var_28]; int *
0x180002611  mov     [rbp+var_18], r14d
0x180002615  mov     [rbp+var_28], r14d
0x180002619  mov     [rbp+var_14], r14d
0x18000261d  call    ?GetFWServiceInfo@CDetectionAndSharing@@AEAAJPEAH0@Z; CDetectionAndSharing::GetFWServiceInfo(int *,int *)
0x180002622  mov     ebx, eax
0x180002624  test    eax, eax
0x180002626  js      loc_180002B38
0x18000262c  mov     rcx, rdi; this
0x18000262f  call    ?InitializeServiceStatusArray@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::InitializeServiceStatusArray(void)
0x180002634  mov     ebx, eax
0x180002636  test    eax, eax
0x180002638  js      loc_180002B38
0x18000263e  or      esi, 0FFFFFFFFh
0x180002641  mov     [rbp+Type], r14d
0x180002645  mov     r13d, r14d
0x180002648  mov     [rbp+var_20], r14d
0x18000264c  mov     r12d, r14d
0x18000264f  mov     [rbp+var_1C], r14d
0x180002653  mov     ebx, 1
0x180002658  cmp     [rbp+var_28], r14d
0x18000265c  jz      loc_1800027C5
0x180002662  mov     rcx, rdi; this
0x180002665  call    ?GetFwPolicy@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::GetFwPolicy(void)
0x18000266a  mov     ebx, eax
0x18000266c  test    eax, eax
0x18000266e  js      loc_180002B38
0x180002674  mov     rcx, [rdi+48h]
0x180002678  lea     rdx, [rbp+var_3C]
0x18000267c  mov     rax, [rcx]
0x18000267f  mov     rax, [rax+38h]
0x180002683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002688  mov     ebx, eax
0x18000268a  test    eax, eax
0x18000268c  js      loc_180002B38
0x180002692  test    r15, r15
0x180002695  jz      short loc_1800026A8
0x180002697  mov     eax, [r15]
0x18000269a  test    eax, eax
0x18000269c  jz      short loc_1800026A8
0x18000269e  cmp     [rbp+var_3C], eax
0x1800026a1  jz      short loc_1800026A8
0x1800026a3  mov     [rbp+var_3C], eax
0x1800026a6  jmp     short loc_1800026D0
0x1800026a8  mov     rcx, [rdi+48h]
0x1800026ac  lea     rdx, [rbp+var_18]
0x1800026b0  mov     [rbp+Type], 1
0x1800026b7  mov     rax, [rcx]
0x1800026ba  mov     rax, [rax+0E0h]
0x1800026c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026c6  mov     ebx, eax
0x1800026c8  test    eax, eax
0x1800026ca  js      loc_180002B38
0x1800026d0  mov     esi, r14d
0x1800026d3  lea     rcx, cs:180000000h
0x1800026da  mov     ebx, 1
0x1800026df  mov     [rbp+var_40], r14w
0x1800026e4  mov     word ptr [rbp+hKey], r14w
0x1800026e9  mov     r14d, [rbp+var_3C]
0x1800026ed  movsxd  rax, esi
0x1800026f0  and     r14d, ds:rva dword_180007130[rcx+rax*4]
0x1800026f8  jz      short loc_180002778
0x1800026fa  mov     rcx, [rdi+48h]
0x1800026fe  lea     r8, [rbp+var_40]
0x180002702  mov     edx, r14d
0x180002705  mov     rax, [rcx]
0x180002708  mov     rax, [rax+40h]
0x18000270c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002711  mov     ebx, eax
0x180002713  test    eax, eax
0x180002715  js      loc_180002B38
0x18000271b  mov     rcx, [rdi+48h]
0x18000271f  lea     r8, [rbp+hKey]
0x180002723  mov     edx, r14d
0x180002726  mov     rax, [rcx]
0x180002729  mov     rax, [rax+60h]
0x18000272d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002732  xor     r14d, r14d
0x180002735  mov     ebx, eax
0x180002737  test    eax, eax
0x180002739  js      loc_180002B38
0x18000273f  or      eax, 0FFFFFFFFh
0x180002742  cmp     r13w, ax
0x180002746  movzx   r13d, ax
0x18000274a  jz      short loc_180002751
0x18000274c  movzx   r13d, [rbp+var_40]
0x180002751  mov     [rbp+var_20], r13d
0x180002755  mov     ebx, 1
0x18000275a  lea     rcx, cs:180000000h
0x180002761  cmp     r12w, ax
0x180002765  jnz     short loc_180002771
0x180002767  movzx   r12d, ax
0x18000276b  mov     [rbp+var_1C], r12d
0x18000276f  jmp     short loc_18000277E
0x180002771  movzx   r12d, word ptr [rbp+hKey]
0x180002776  jmp     short loc_18000276B
0x180002778  xor     r14d, r14d
0x18000277b  or      eax, 0FFFFFFFFh
0x18000277e  add     esi, ebx
0x180002780  cmp     esi, 3
0x180002783  jb      loc_1800026DF
0x180002789  cmp     ax, r13w
0x18000278d  jnz     short loc_1800027C2
0x18000278f  cmp     r14w, r12w
0x180002793  jnz     short loc_1800027C2
0x180002795  test    r15, r15
0x180002798  jz      short loc_1800027A4
0x18000279a  cmp     [r15], r14d
0x18000279d  jz      short loc_1800027A4
0x18000279f  mov     rdx, r15
0x1800027a2  jmp     short loc_1800027A6
0x1800027a4  xor     edx, edx; enum NET_FW_PROFILE_TYPE2_ *
0x1800027a6  mov     rcx, rdi; this
0x1800027a9  call    ?GetFwGroupsStatus@CDetectionAndSharing@@AEAAJPEAW4NET_FW_PROFILE_TYPE2_@@@Z; CDetectionAndSharing::GetFwGroupsStatus(NET_FW_PROFILE_TYPE2_ *)
0x1800027ae  mov     ebx, eax
0x1800027b0  test    eax, eax
0x1800027b2  js      loc_180002B38
0x1800027b8  mov     [rbp+var_10], r14d
0x1800027bc  lea     rsi, [rdi+58h]
0x1800027c0  jmp     short loc_180002813
0x1800027c2  or      esi, 0FFFFFFFFh
0x1800027c5  call    ?IsThirdPartyFwRunning@@YAHXZ; IsThirdPartyFwRunning(void)
0x1800027ca  mov     [rbp+var_10], eax
0x1800027cd  cmp     [rbp+var_28], r14d
0x1800027d1  jz      short loc_1800027E2
0x1800027d3  cmp     si, r13w
0x1800027d7  jnz     short loc_1800027E2
0x1800027d9  mov     r8d, r14d
0x1800027dc  cmp     si, r12w
0x1800027e0  jz      short loc_1800027E5
0x1800027e2  mov     r8d, ebx
0x1800027e5  lea     rsi, [rdi+58h]
0x1800027e9  mov     edx, r14d
0x1800027ec  cmp     [rsi], r14
0x1800027ef  jbe     short loc_180002813
0x1800027f1  mov     ecx, edx
0x1800027f3  cmp     rcx, [rdi+58h]
0x1800027f7  jnb     loc_180002B52
0x1800027fd  mov     rax, [rdi+50h]
0x180002801  add     edx, ebx
0x180002803  shl     rcx, 5
0x180002807  mov     [rcx+rax+1Ch], r8d
0x18000280c  mov     eax, edx
0x18000280e  cmp     rax, [rsi]
0x180002811  jb      short loc_1800027F1
0x180002813  mov     rcx, rdi; this
0x180002816  call    ?GetWindowsServicesStatus@CDetectionAndSharing@@AEAAJXZ; CDetectionAndSharing::GetWindowsServicesStatus(void)
0x18000281b  mov     ebx, eax
0x18000281d  test    eax, eax
0x18000281f  js      loc_180002B38
0x180002825  mov     ecx, r14d
0x180002828  mov     r11d, 1
0x18000282e  cmp     [rsi], r14
0x180002831  jbe     short loc_180002882
0x180002833  mov     eax, ecx
0x180002835  cmp     rax, [rdi+58h]
0x180002839  jnb     loc_180002B52
0x18000283f  mov     r8, [rdi+50h]
0x180002843  shl     rax, 5
0x180002847  cmp     [rax+r8+1Ch], r14d
0x18000284c  jz      short loc_180002872
0x18000284e  cmp     [rax+r8+18h], r14d
0x180002853  jz      short loc_180002872
0x180002855  movsxd  r9, dword ptr [rax+r8+10h]
0x18000285a  lea     rdx, [rdi+70h]
0x18000285e  cmp     r9, [rdx+8]
0x180002862  jnb     loc_180002B52
0x180002868  mov     rax, [rdx]
0x18000286b  add     [rax+r9*8+4], r11d
0x180002870  jmp     short loc_180002876
0x180002872  lea     rdx, [rdi+70h]
0x180002876  add     ecx, r11d
0x180002879  mov     eax, ecx
0x18000287b  cmp     rax, [rsi]
0x18000287e  jb      short loc_180002833
0x180002880  jmp     short loc_180002886
0x180002882  lea     rdx, [rdi+70h]
0x180002886  movsxd  r10, [rbp+arg_10]
0x18000288a  mov     r13d, 4
0x180002890  cmp     r10d, r13d
0x180002893  jnz     short loc_1800028D4
0x180002895  cmp     [rdi+78h], r13
0x180002899  jbe     loc_180002B52
0x18000289f  mov     rdx, [rdi+70h]
0x1800028a3  mov     r8d, r14d
0x1800028a6  mov     r9d, r8d
0x1800028a9  cmp     r9, [rdi+78h]
0x1800028ad  jnb     loc_180002B52
0x1800028b3  mov     rcx, [rdi+70h]
0x1800028b7  add     r8d, r11d
0x1800028ba  mov     eax, [rcx+r9*8]
0x1800028be  add     [rdx+20h], eax
0x1800028c1  mov     eax, [rcx+r9*8+4]
0x1800028c6  add     [rdx+24h], eax
0x1800028c9  cmp     r8d, r13d
0x1800028cc  jb      short loc_1800028A6
0x1800028ce  lea     rdx, [rdi+70h]
0x1800028d2  jmp     short loc_1800028FC
0x1800028d4  mov     eax, 3
0x1800028d9  cmp     r10d, eax
0x1800028dc  jnz     short loc_1800028FC
0x1800028de  cmp     [rdx+8], rax
0x1800028e2  jbe     loc_180002B52
0x1800028e8  mov     rcx, [rdx]
0x1800028eb  mov     eax, [rcx+8]
0x1800028ee  add     eax, [rcx]
0x1800028f0  mov     [rcx+18h], eax
0x1800028f3  mov     eax, [rcx+4]
0x1800028f6  add     eax, [rcx+0Ch]
0x1800028f9  mov     [rcx+1Ch], eax
0x1800028fc  cmp     r10, [rdx+8]
0x180002900  jnb     loc_180002B52
0x180002906  mov     rcx, [rdx]
0x180002909  mov     esi, r14d
0x18000290c  mov     edx, [rcx+r10*8+4]
0x180002911  test    edx, edx
0x180002913  jz      short loc_180002920
0x180002915  cmp     [rcx+r10*8], edx
0x180002919  setnz   sil
0x18000291d  add     esi, r11d
0x180002920  mov     eax, [rbp+var_3C]
0x180002923  xor     r15d, r15d
0x180002926  mov     dword ptr [rbp+Data], r15d
0x18000292a  mov     r12d, r15d
0x18000292d  mov     [rbp+var_40], r15w
0x180002932  mov     ebx, r14d
0x180002935  mov     dword ptr [rbp+hKey], eax
0x180002938  mov     ecx, r12d
0x18000293b  cmp     rcx, [rdi+58h]
0x18000293f  jnb     loc_180002A16
0x180002945  mov     rax, [rdi+50h]
0x180002949  shl     rcx, 5
0x18000294d  cmp     r10d, [rcx+rax+10h]
0x180002952  jnz     loc_1800029FE
0x180002958  mov     rcx, [rcx+rax+8]; psz
0x18000295d  call    cs:__imp_SysAllocString
0x180002963  mov     r13, rax
0x180002966  test    rax, rax
0x180002969  jz      loc_180002AAC
0x18000296f  mov     eax, dword ptr [rbp+hKey]
0x180002972  lea     r8, cs:180000000h
0x180002979  mov     [rbp+cbData], 1
0x180002980  movsxd  rcx, r15d
0x180002983  mov     edx, eax
0x180002985  and     edx, ds:rva dword_180007130[r8+rcx*4]
0x18000298d  jz      short loc_1800029D4
0x18000298f  mov     rcx, [rdi+48h]
0x180002993  lea     r9, [rbp+var_40]
0x180002997  mov     r8, r13
0x18000299a  mov     rax, [rcx]
0x18000299d  mov     rax, [rax+0A8h]
0x1800029a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a9  cmp     [rbp+cbData], 0
0x1800029ad  mov     ebx, eax
0x1800029af  jz      short loc_1800029C1
0x1800029b1  movzx   eax, [rbp+var_40]
0x1800029b5  mov     dword ptr [rbp+Data], eax
0x1800029b8  mov     [rbp+cbData], 0
0x1800029bf  jmp     short loc_1800029CA
0x1800029c1  mov     eax, dword ptr [rbp+Data]
0x1800029c4  cmp     ax, [rbp+var_40]
0x1800029c8  jnz     short loc_1800029DF
0x1800029ca  mov     eax, dword ptr [rbp+hKey]
0x1800029cd  lea     r8, cs:180000000h
0x1800029d4  inc     r15d
0x1800029d7  cmp     r15d, 3
0x1800029db  jb      short loc_180002980
0x1800029dd  jmp     short loc_1800029E5
0x1800029df  mov     r14d, 1
0x1800029e5  mov     rcx, r13; bstrString
0x1800029e8  call    cs:__imp_SysFreeString
0x1800029ee  xor     r15d, r15d
0x1800029f1  test    r14d, r14d
0x1800029f4  jnz     short loc_180002A0E
0x1800029f6  mov     r10d, [rbp+arg_10]
0x1800029fa  lea     r11d, [r15+1]
0x1800029fe  add     r12d, r11d
  ... truncated ...
```
