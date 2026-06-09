# LoadDsGroup

- ea: `0x180090fd8`
- end: `0x1800914b7`
- name: `LoadDsGroup`
- size: `1247`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009da0`
- `0x1800d641c`

## callees

- `0x180034270`
- `0x180090fd8`
- `0x1800914c0`
- `0x18009182c`
- `0x180091b9c`
- `0x1800bf5f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091419`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009102d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009102d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091097`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091004`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091097`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090ff7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180090ff7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180091016`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180091071`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180091016`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180091071`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18009146f`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18009146f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800912e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180091348`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18009138f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800913be`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800912e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180091348`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18009138f`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800913be`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18009145a`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18009145a`

## string_xrefs

- `0x1800912c9`: `msPKI-Cert-Template-OID`

## pseudocode

```c
void LoadDsGroup()
{
  LONG v0; // ebx
  _QWORD *DsOIDInfoCache; // rsi
  int v2; // ebx
  unsigned int v3; // edx
  __int64 v4; // r9
  _QWORD *v5; // r10
  unsigned int i; // r8d
  __int64 v7; // rax
  int v8; // r10d
  const char *v9; // r8
  DWORD v10; // r11d
  __int64 v11; // rcx
  DWORD dwLowDateTime; // edx
  LANGID UserDefaultUILanguage; // r13
  int v14; // r12d
  DWORD v15; // r15d
  unsigned int j; // eax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rbx
  const char *v20; // r14
  unsigned int v21; // ebx
  __int64 v22; // rax
  const char *v23; // rdx
  int v24; // ecx
  int v25; // ecx
  const CHAR *v26; // rbp
  unsigned int v27; // ebx
  __int64 v28; // rax
  const char *v29; // rcx
  int v30; // edi
  DWORD v31; // r9d
  __int64 v32; // rdi
  DWORD v33; // ebx
  const char *v34; // rdi
  int v35; // eax
  const char *v36; // rcx
  int v37; // ebp
  __int16 v38; // di
  DWORD v39; // r9d
  __int64 v40; // [rsp+30h] [rbp-78h]
  int v41; // [rsp+38h] [rbp-70h]
  const unsigned __int16 *v42; // [rsp+40h] [rbp-68h]
  int v43; // [rsp+48h] [rbp-60h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-58h] BYREF
  FILETIME FileTime2; // [rsp+B0h] [rbp+8h] BYREF
  DWORD v46; // [rsp+B8h] [rbp+10h]
  DWORD v47; // [rsp+C0h] [rbp+18h]
  unsigned int v48; // [rsp+C8h] [rbp+20h]

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  EnterCriticalSection(&stru_18015CC80);
  v0 = CompareFileTime(&FileTime1, &SystemTimeAsFileTime);
  if ( v0 > 0 )
  {
    FileTime2 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 576000000000LL);
    if ( CompareFileTime(&FileTime1, &FileTime2) > 0 )
      v0 = -1;
  }
  LeaveCriticalSection(&stru_18015CC80);
  if ( v0 > 0 )
    return;
  DsOIDInfoCache = (_QWORD *)I_CryptGetDsOIDInfoCache();
  if ( !DsOIDInfoCache && GetLastError() != 2 )
    return;
  EnterCriticalSection(&stru_18015CC80);
  v2 = dword_18015CC60;
  if ( dword_18015CC60 )
  {
    if ( !(unsigned int)AddDsOIDInfo(Src, (unsigned int)dword_18015CC60, &dword_18015CC70) )
      goto LABEL_11;
    v3 = dword_18015CC60;
    v4 = 0;
    v5 = Src;
    for ( i = v2; i < v3; v4 = (unsigned int)(v4 + 1) )
    {
      v7 = i++;
      v5[v4] = v5[v7];
    }
    dword_18015CC60 = v3 - v2;
  }
  if ( !DsOIDInfoCache )
    goto LABEL_10;
  v8 = 0;
  v9 = (const char *)&byte_180136197;
  v10 = 0;
  v42 = &byte_180136197;
  v11 = 0;
  v41 = 0;
  dwLowDateTime = 0;
  v46 = 0;
  UserDefaultUILanguage = 0;
  v43 = 0;
  v14 = 0;
  v47 = 0;
  v15 = 0;
  v40 = 0;
  FileTime2.dwLowDateTime = 0;
  for ( j = 0; ; j = v48 + 1 )
  {
    v48 = j;
    if ( j >= *(_DWORD *)DsOIDInfoCache )
      break;
    v17 = j;
    v18 = DsOIDInfoCache[1];
    v19 = 2 * v17;
    v20 = *(const char **)(v18 + 8 * v19 + 8);
    if ( v20 )
    {
      v21 = *(_DWORD *)(v18 + 8 * v19);
      if ( v21 <= 0x7FFFFFFF )
      {
        v22 = v21;
        v23 = v20;
        if ( v21 )
        {
          while ( *v23 )
          {
            ++v23;
            if ( !--v22 )
              goto LABEL_24;
          }
          v24 = v21 - v22;
        }
        else
        {
LABEL_24:
          v24 = 0;
        }
        if ( !v22 )
          goto LABEL_43;
        v25 = v24 + 1;
        v26 = &v20[v25];
        if ( !v26 )
          goto LABEL_43;
        v27 = v21 - v25;
        if ( v27 > 0x7FFFFFFF )
          goto LABEL_43;
        v28 = v27;
        v29 = &v20[v25];
        if ( v27 )
        {
          while ( *v29 )
          {
            ++v29;
            if ( !--v28 )
              goto LABEL_32;
          }
          v30 = v27 - v28;
        }
        else
        {
LABEL_32:
          v30 = 0;
        }
        if ( !v28 )
          goto LABEL_43;
        if ( strcmp(v20, v9) )
        {
          v31 = v15;
          if ( !v15 )
          {
            v14 = v43;
            v31 = v47;
          }
          if ( !(unsigned int)CreateAndAddDsOIDInfo(v8, v10, v14, v31, v40, FileTime2.dwLowDateTime) )
            goto LABEL_11;
          v42 = (const unsigned __int16 *)v20;
          v41 = 0;
          v14 = 0;
          v46 = 0;
          v15 = 0;
          v43 = 0;
          v47 = 0;
          v40 = 0;
          FileTime2.dwLowDateTime = 0;
        }
        v32 = (unsigned int)(v30 + 1);
        v33 = v27 - v32;
        v34 = &v26[v32];
        if ( CompareStringA(0x409u, 1u, v26, -1, "msPKI-Cert-Template-OID", -1) == 2 )
        {
          v8 = (int)v34;
          v41 = (int)v34;
          v10 = v33;
          v46 = v33;
LABEL_42:
          v9 = (const char *)v42;
LABEL_43:
          v11 = v40;
          dwLowDateTime = FileTime2.dwLowDateTime;
          continue;
        }
        if ( CompareStringA(0x409u, 1u, v26, -1, "displayName", -1) == 2 )
        {
          v43 = (int)v34;
          v47 = v33;
LABEL_48:
          v10 = v46;
          v8 = v41;
          goto LABEL_42;
        }
        if ( CompareStringA(0x409u, 1u, v26, -1, "msPKI-OIDLocalizedName", -1) == 2 )
        {
          if ( !v15 )
          {
            v36 = v34;
            while ( v33 )
            {
              --v33;
              v37 = (_DWORD)v34 + 1;
              if ( *v34 == 44 )
              {
                *v34 = 0;
                if ( !v33 )
                  goto LABEL_48;
                v38 = strtoul(v36, 0, 10);
                if ( !v38 )
                  goto LABEL_48;
                if ( !UserDefaultUILanguage )
                {
                  UserDefaultUILanguage = GetUserDefaultUILanguage();
                  if ( !UserDefaultUILanguage )
                    UserDefaultUILanguage = GetSystemDefaultUILanguage();
                }
                v8 = v41;
                v10 = v46;
                v11 = v40;
                dwLowDateTime = FileTime2.dwLowDateTime;
                v9 = (const char *)v42;
                if ( v38 == UserDefaultUILanguage )
                {
                  v15 = v33;
                  v14 = v37;
                }
                goto LABEL_44;
              }
              ++v34;
            }
          }
          goto LABEL_48;
        }
        v35 = CompareStringA(0x409u, 1u, v26, -1, "flags", -1);
        v8 = v41;
        v10 = v46;
        v9 = (const char *)v42;
        if ( v35 != 2 )
          goto LABEL_43;
        v11 = (__int64)v34;
        FileTime2.dwLowDateTime = v33;
        v40 = (__int64)v34;
        dwLowDateTime = v33;
      }
    }
LABEL_44:
    ;
  }
  v39 = v15;
  if ( !v15 )
  {
    v14 = v43;
    v39 = v47;
  }
  if ( (unsigned int)CreateAndAddDsOIDInfo(v8, v10, v14, v39, v11, dwLowDateTime) )
LABEL_10:
    FileTime1 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 288000000000LL);
LABEL_11:
  LeaveCriticalSection(&stru_18015CC80);
  if ( DsOIDInfoCache )
    ICM_Free(DsOIDInfoCache);
}

```

## disassembly

```asm
0x180090fd8  push    rbx
0x180090fda  push    rbp
0x180090fdb  push    rsi
0x180090fdc  push    rdi
0x180090fdd  push    r12
0x180090fdf  push    r13
0x180090fe1  push    r14
0x180090fe3  push    r15
0x180090fe5  sub     rsp, 68h
0x180090fe9  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180090fee  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180090ff7  call    cs:__imp_GetSystemTimeAsFileTime
0x180090ffd  lea     rcx, stru_18015CC80; lpCriticalSection
0x180091004  call    cs:__imp_EnterCriticalSection
0x18009100a  lea     rdx, [rsp+0A8h+SystemTimeAsFileTime]; lpFileTime2
0x18009100f  lea     rcx, FileTime1; lpFileTime1
0x180091016  call    cs:__imp_CompareFileTime
0x18009101c  or      r14d, 0FFFFFFFFh
0x180091020  mov     ebx, eax
0x180091022  test    eax, eax
0x180091024  jg      short loc_180091048
0x180091026  lea     rcx, stru_18015CC80; lpCriticalSection
0x18009102d  call    cs:__imp_LeaveCriticalSection
0x180091033  test    ebx, ebx
0x180091035  jle     short loc_18009107F
0x180091037  add     rsp, 68h
0x18009103b  pop     r15
0x18009103d  pop     r14
0x18009103f  pop     r13
0x180091041  pop     r12
0x180091043  pop     rdi
0x180091044  pop     rsi
0x180091045  pop     rbp
0x180091046  pop     rbx
0x180091047  retn
0x180091048  mov     rdx, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x18009104d  lea     rcx, FileTime1; lpFileTime1
0x180091054  mov     rax, 861C468000h
0x18009105e  add     rdx, rax
0x180091061  mov     qword ptr [rsp+0A8h+FileTime2.dwLowDateTime], rdx
0x180091069  lea     rdx, [rsp+0A8h+FileTime2]; lpFileTime2
0x180091071  call    cs:__imp_CompareFileTime
0x180091077  test    eax, eax
0x180091079  cmovg   ebx, r14d
0x18009107d  jmp     short loc_180091026
0x18009107f  call    I_CryptGetDsOIDInfoCache
0x180091084  mov     rsi, rax
0x180091087  test    rax, rax
0x18009108a  jz      loc_180091419
0x180091090  lea     rcx, stru_18015CC80; lpCriticalSection
0x180091097  call    cs:__imp_EnterCriticalSection
0x18009109d  mov     ebx, cs:dword_18015CC60
0x1800910a3  test    ebx, ebx
0x1800910a5  jnz     short loc_1800910E9
0x1800910a7  test    rsi, rsi
0x1800910aa  jnz     loc_18009113C
0x1800910b0  mov     rdx, 430E234000h
0x1800910ba  add     rdx, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800910bf  mov     qword ptr cs:FileTime1.dwLowDateTime, rdx
0x1800910c6  lea     rcx, stru_18015CC80; lpCriticalSection
0x1800910cd  call    cs:__imp_LeaveCriticalSection
0x1800910d3  test    rsi, rsi
0x1800910d6  jz      loc_180091037
0x1800910dc  mov     rcx, rsi; pv
0x1800910df  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x1800910e4  jmp     loc_180091037
0x1800910e9  mov     rcx, cs:Src
0x1800910f0  lea     r8, dword_18015CC70
0x1800910f7  mov     edx, ebx
0x1800910f9  call    AddDsOIDInfo
0x1800910fe  test    eax, eax
0x180091100  jz      short loc_1800910C6
0x180091102  mov     edx, cs:dword_18015CC60
0x180091108  xor     r9d, r9d
0x18009110b  mov     r10, cs:Src
0x180091112  mov     r8d, ebx
0x180091115  cmp     ebx, edx
0x180091117  jnb     short loc_18009112F
0x180091119  mov     eax, r8d
0x18009111c  inc     r8d
0x18009111f  mov     rax, [r10+rax*8]
0x180091123  mov     [r10+r9*8], rax
0x180091127  inc     r9d
0x18009112a  cmp     r8d, edx
0x18009112d  jb      short loc_180091119
0x18009112f  sub     edx, ebx
0x180091131  mov     cs:dword_18015CC60, edx
0x180091137  jmp     loc_1800910A7
0x18009113c  xor     r10d, r10d
0x18009113f  lea     r8, byte_180136197
0x180091146  xor     r11d, r11d
0x180091149  mov     [rsp+0A8h+var_68], r8
0x18009114e  xor     ecx, ecx
0x180091150  mov     [rsp+0A8h+var_70], r10
0x180091155  xor     edx, edx
0x180091157  mov     [rsp+0A8h+arg_8], r11d
0x18009115f  xor     r13d, r13d
0x180091162  mov     [rsp+0A8h+var_60], r10
0x180091167  xor     r12d, r12d
0x18009116a  mov     [rsp+0A8h+arg_10], r10d
0x180091172  xor     r15d, r15d
0x180091175  mov     [rsp+0A8h+var_78], rcx
0x18009117a  mov     [rsp+0A8h+FileTime2.dwLowDateTime], edx
0x180091181  xor     eax, eax
0x180091183  mov     [rsp+0A8h+arg_18], eax
0x18009118a  cmp     eax, [rsi]
0x18009118c  jnb     loc_18009147E
0x180091192  mov     ebx, eax
0x180091194  mov     rax, [rsi+8]
0x180091198  add     rbx, rbx
0x18009119b  mov     r14, [rax+rbx*8+8]
0x1800911a0  test    r14, r14
0x1800911a3  jz      loc_180091314
0x1800911a9  mov     ebx, [rax+rbx*8]
0x1800911ac  cmp     ebx, 7FFFFFFFh
0x1800911b2  ja      loc_180091314
0x1800911b8  mov     eax, ebx
0x1800911ba  mov     rdx, r14
0x1800911bd  mov     ecx, ebx
0x1800911bf  test    ebx, ebx
0x1800911c1  jz      short loc_1800911D1
0x1800911c3  cmp     byte ptr [rdx], 0
0x1800911c6  jz      short loc_1800911D5
0x1800911c8  inc     rdx
0x1800911cb  sub     rax, 1
0x1800911cf  jnz     short loc_1800911C3
0x1800911d1  xor     ecx, ecx
0x1800911d3  jmp     short loc_1800911D8
0x1800911d5  sub     rcx, rax
0x1800911d8  test    rax, rax
0x1800911db  jz      loc_180091308
0x1800911e1  inc     ecx
0x1800911e3  mov     ebp, ecx
0x1800911e5  add     rbp, r14
0x1800911e8  jz      loc_180091308
0x1800911ee  sub     ebx, ecx
0x1800911f0  cmp     ebx, 7FFFFFFFh
0x1800911f6  ja      loc_180091308
0x1800911fc  mov     eax, ebx
0x1800911fe  mov     rcx, rbp
0x180091201  mov     edi, ebx
0x180091203  test    ebx, ebx
0x180091205  jz      short loc_180091215
0x180091207  cmp     byte ptr [rcx], 0
0x18009120a  jz      short loc_180091219
0x18009120c  inc     rcx
0x18009120f  sub     rax, 1
0x180091213  jnz     short loc_180091207
0x180091215  xor     edi, edi
0x180091217  jmp     short loc_18009121C
0x180091219  sub     rdi, rax
0x18009121c  test    rax, rax
0x18009121f  jz      loc_180091308
0x180091225  mov     rax, r14
0x180091228  sub     r8, r14
0x18009122b  movzx   edx, byte ptr [rax]
0x18009122e  movzx   ecx, byte ptr [rax+r8]
0x180091233  sub     edx, ecx
0x180091235  jnz     short loc_18009123E
0x180091237  inc     rax
0x18009123a  test    ecx, ecx
0x18009123c  jnz     short loc_18009122B
0x18009123e  test    edx, edx
0x180091240  jz      loc_180091322
0x180091246  mov     eax, [rsp+0A8h+FileTime2.dwLowDateTime]
0x18009124d  test    r15d, r15d
0x180091250  mov     [rsp+0A8h+cchCount2], eax
0x180091254  mov     r9d, r15d
0x180091257  cmovz   r12, [rsp+0A8h+var_60]
0x18009125d  mov     edx, r11d
0x180091260  mov     rax, [rsp+0A8h+var_78]
0x180091265  mov     r8, r12
0x180091268  cmovz   r9d, [rsp+0A8h+arg_10]
0x180091271  mov     rcx, r10
0x180091274  mov     [rsp+0A8h+lpString2], rax
0x180091279  call    CreateAndAddDsOIDInfo
0x18009127e  test    eax, eax
0x180091280  jz      loc_1800910C6
0x180091286  mov     [rsp+0A8h+var_68], r14
0x18009128b  xor     r14d, r14d
0x18009128e  mov     [rsp+0A8h+var_70], r14
0x180091293  mov     r12d, r14d
0x180091296  mov     [rsp+0A8h+arg_8], r14d
0x18009129e  mov     r15d, r14d
0x1800912a1  mov     [rsp+0A8h+var_60], r14
0x1800912a6  mov     [rsp+0A8h+arg_10], r14d
0x1800912ae  mov     [rsp+0A8h+var_78], r14
0x1800912b3  mov     [rsp+0A8h+FileTime2.dwLowDateTime], r14d
0x1800912bb  or      ecx, 0FFFFFFFFh
0x1800912be  lea     eax, [rdi+1]
0x1800912c1  mov     edi, eax
0x1800912c3  sub     ebx, eax
0x1800912c5  mov     [rsp+0A8h+cchCount2], ecx; cchCount2
0x1800912c9  lea     rax, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x1800912d0  mov     r9d, ecx; cchCount1
0x1800912d3  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1800912d8  lea     edx, [rcx+2]; dwCmpFlags
0x1800912db  mov     r8, rbp; lpString1
0x1800912de  mov     ecx, 409h; Locale
0x1800912e3  add     rdi, rbp
0x1800912e6  call    cs:__imp_CompareStringA
0x1800912ec  cmp     eax, 2
0x1800912ef  jnz     short loc_180091327
0x1800912f1  mov     r10, rdi
0x1800912f4  mov     [rsp+0A8h+var_70], rdi
0x1800912f9  mov     r11d, ebx
0x1800912fc  mov     [rsp+0A8h+arg_8], ebx
0x180091303  mov     r8, [rsp+0A8h+var_68]
0x180091308  mov     rcx, [rsp+0A8h+var_78]
0x18009130d  mov     edx, [rsp+0A8h+FileTime2.dwLowDateTime]
0x180091314  mov     eax, [rsp+0A8h+arg_18]
0x18009131b  inc     eax
0x18009131d  jmp     loc_180091183
0x180091322  xor     r14d, r14d
0x180091325  jmp     short loc_1800912BB
0x180091327  or      ecx, 0FFFFFFFFh
0x18009132a  lea     rax, aDisplayname_0; "displayName"
0x180091331  mov     [rsp+0A8h+cchCount2], ecx; cchCount2
0x180091335  mov     r9d, ecx; cchCount1
0x180091338  mov     r8, rbp; lpString1
0x18009133b  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180091340  lea     edx, [rcx+2]; dwCmpFlags
0x180091343  mov     ecx, 409h; Locale
0x180091348  call    cs:__imp_CompareStringA
0x18009134e  cmp     eax, 2
0x180091351  jnz     short loc_18009136E
0x180091353  mov     [rsp+0A8h+var_60], rdi
0x180091358  mov     [rsp+0A8h+arg_10], ebx
0x18009135f  mov     r11d, [rsp+0A8h+arg_8]
0x180091367  mov     r10, [rsp+0A8h+var_70]
0x18009136c  jmp     short loc_180091303
0x18009136e  or      ecx, 0FFFFFFFFh
0x180091371  lea     rax, aMspkiOidlocali; "msPKI-OIDLocalizedName"
0x180091378  mov     [rsp+0A8h+cchCount2], ecx; cchCount2
0x18009137c  mov     r9d, ecx; cchCount1
0x18009137f  mov     r8, rbp; lpString1
0x180091382  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180091387  lea     edx, [rcx+2]; dwCmpFlags
0x18009138a  mov     ecx, 409h; Locale
0x18009138f  call    cs:__imp_CompareStringA
0x180091395  cmp     eax, 2
0x180091398  jz      short loc_1800913F5
0x18009139a  or      r14d, 0FFFFFFFFh
0x18009139e  lea     rax, aFlags_0; "flags"
0x1800913a5  mov     [rsp+0A8h+cchCount2], r14d; cchCount2
0x1800913aa  mov     r9d, r14d; cchCount1
0x1800913ad  mov     r8, rbp; lpString1
0x1800913b0  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1800913b5  mov     ecx, 409h; Locale
0x1800913ba  lea     edx, [r14+2]; dwCmpFlags
0x1800913be  call    cs:__imp_CompareStringA
0x1800913c4  mov     r10, [rsp+0A8h+var_70]
0x1800913c9  mov     r11d, [rsp+0A8h+arg_8]
0x1800913d1  mov     r8, [rsp+0A8h+var_68]
0x1800913d6  cmp     eax, 2
0x1800913d9  jnz     loc_180091308
0x1800913df  mov     rcx, rdi
0x1800913e2  mov     [rsp+0A8h+FileTime2.dwLowDateTime], ebx
0x1800913e9  mov     [rsp+0A8h+var_78], rcx
0x1800913ee  mov     edx, ebx
0x1800913f0  jmp     loc_180091314
0x1800913f5  test    r15d, r15d
0x1800913f8  jnz     loc_18009135F
0x1800913fe  mov     rcx, rdi; String
0x180091401  test    ebx, ebx
0x180091403  jz      loc_18009135F
0x180091409  dec     ebx
0x18009140b  lea     rbp, [rdi+1]
0x18009140f  cmp     byte ptr [rdi], 2Ch ; ','
0x180091412  jz      short loc_18009142D
0x180091414  mov     rdi, rbp
0x180091417  jmp     short loc_180091401
0x180091419  call    cs:__imp_GetLastError
0x18009141f  cmp     eax, 2
0x180091422  jnz     loc_180091037
0x180091428  jmp     loc_180091090
0x18009142d  mov     [rdi], r14b
0x180091430  test    ebx, ebx
0x180091432  jz      loc_18009135F
0x180091438  xor     edx, edx; EndPtr
0x18009143a  lea     r8d, [rdx+0Ah]; Radix
0x18009143e  call    strtoul
0x180091443  xor     ecx, ecx
0x180091445  mov     edi, eax
0x180091447  cmp     cx, ax
0x18009144a  jz      loc_18009135F
0x180091450  cmp     cx, r13w
0x180091454  jnz     loc_18011C1E6
0x18009145a  call    cs:__imp_GetUserDefaultUILanguage
0x180091460  xor     ecx, ecx
0x180091462  movzx   r13d, ax
0x180091466  cmp     cx, ax
0x180091469  jnz     loc_18011C1E6
0x18009146f  call    cs:__imp_GetSystemDefaultUILanguage
0x180091475  movzx   r13d, ax
0x180091479  jmp     loc_18011C1E6
0x18009147e  mov     [rsp+0A8h+cchCount2], edx
0x180091482  test    r15d, r15d
0x180091485  mov     r9d, r15d
0x180091488  mov     [rsp+0A8h+lpString2], rcx
  ... truncated ...
```
