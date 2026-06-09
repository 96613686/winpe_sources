# OpenPhysicalStoreCallback(void const *,ulong,ushort const *,_CERT_PHYSICAL_STORE_INFO *,void *,void *)

- ea: `0x180046eb0`
- end: `0x1800473b1`
- name: `?OpenPhysicalStoreCallback@@YAHPEBXKPEBGPEAU_CERT_PHYSICAL_STORE_INFO@@PEAX3@Z`
- size: `1281`
- prototype: `__int64 __fastcall(const void *, DWORD, const unsigned __int16 *, struct _CERT_PHYSICAL_STORE_INFO *, void *, _QWORD *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18001a0d0`
- `0x180034270`
- `0x1800466a0`
- `0x180046eb0`
- `0x180047f10`
- `0x18005b130`
- `0x18005cfc0`
- `0x18006dbc4`
- `0x18006ee70`
- `0x1800863d0`
- `0x1800ae420`
- `0x1800bec20`
- `0x1800bf564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800471a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004709c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004718d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004709c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004718d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004700a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047076`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004700a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047076`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180046fc0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047060`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047094`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047094`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047020`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047020`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180047206`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180047206`

## pseudocode

```c
__int64 __fastcall OpenPhysicalStoreCallback(
        const void *a1,
        DWORD a2,
        const unsigned __int16 *a3,
        struct _CERT_PHYSICAL_STORE_INFO *a4,
        void *a5,
        _QWORD *a6)
{
  bool v6; // zf
  unsigned int v9; // edi
  const WCHAR *v10; // r8
  __int64 v11; // rcx
  DWORD dwOpenFlags; // ebx
  volatile signed __int32 *v13; // r12
  signed int v14; // ebx
  CHAR *pvPara; // r15
  unsigned __int64 pszOpenStoreProvider; // rsi
  DWORD dwFlags; // r15d
  __int64 v18; // rsi
  __int64 i; // rcx
  int v20; // ebx
  _DWORD *v21; // rax
  _DWORD *v22; // rbx
  DWORD v23; // r15d
  __int64 v24; // rcx
  HLOCAL v25; // rsi
  DWORD v26; // ebx
  __int64 v28; // rax
  __int64 v29; // rax
  DWORD v30; // ecx
  DWORD LastError; // eax
  int v32; // r15d
  void *v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  DWORD pvData; // [rsp+30h] [rbp-69h] BYREF
  DWORD pcbData; // [rsp+34h] [rbp-65h] BYREF
  __int64 v39; // [rsp+38h] [rbp-61h]
  LPVOID pv; // [rsp+40h] [rbp-59h]
  LPCCH lpMultiByteStr; // [rsp+48h] [rbp-51h]
  HLOCAL hMem[2]; // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+60h] [rbp-39h]
  __int128 v44; // [rsp+68h] [rbp-31h] BYREF
  __int128 v45; // [rsp+78h] [rbp-21h] BYREF
  __int128 v46; // [rsp+88h] [rbp-11h]
  __int64 v47; // [rsp+98h] [rbp-1h]

  v6 = (a4->dwFlags & 2) == 0;
  v44 = 0;
  pcbData = a2;
  v9 = 1;
  if ( v6 )
  {
    v10 = (const WCHAR *)a6[3];
    if ( v10 )
    {
      if ( CompareStringW(0x409u, 1u, v10, -1, a3, -1) != 2 )
        return v9;
      a2 = pcbData;
    }
    v11 = a6[1];
    if ( !v11 || (a4->dwFlags & 4) == 0 )
    {
      dwOpenFlags = a4->dwOpenFlags;
      v13 = 0;
      hMem[0] = 0;
      v14 = dwOpenFlags | 0x20000000;
      if ( (a2 & 0x20000000) == 0 )
        v14 = a4->dwOpenFlags;
      pcbData = a2 & 1;
      if ( (a2 & 1) == 0 )
      {
        v14 |= 0x20u;
        if ( (v14 & 0x9D5) != 0 )
          goto LABEL_49;
      }
      pvPara = (CHAR *)a4->OpenParameters.pbData;
      pszOpenStoreProvider = (unsigned __int64)a4->pszOpenStoreProvider;
      lpMultiByteStr = pvPara;
      if ( !v11 && !a6[2] )
      {
LABEL_9:
        if ( a6[4] && GetSystemProviderFlags((PCNZCH)pszOpenStoreProvider) )
        {
          if ( v14 < 0 )
            goto LABEL_49;
          v35 = a6[4];
          v14 |= 0x80000000;
          *((_QWORD *)&v44 + 1) = pvPara;
          pvPara = (CHAR *)&v44;
          *(_QWORD *)&v44 = v35;
        }
        v13 = (volatile signed __int32 *)CertOpenStore(
                                           (LPCSTR)pszOpenStoreProvider,
                                           a4->dwOpenEncodingType,
                                           0,
                                           v14 | (_DWORD)a6[5] & 0xCFC0u,
                                           pvPara);
        if ( !v13 )
        {
          LastError = GetLastError();
          if ( ((v14 & 0x10000000) == 0 || LastError != 5) && LastError != 2 && LastError != 127 && LastError != 31 )
            goto LABEL_51;
          if ( !a6[3] || !pcbData )
            goto LABEL_30;
          CertAddStoreToCollection((HCERTSTORE)*a6, 0, 0, 0);
LABEL_29:
          *((_DWORD *)a6 + 11) = 1;
LABEL_30:
          v25 = hMem[0];
          if ( hMem[0] )
          {
            v26 = GetLastError();
            LocalFree(v25);
            SetLastError(v26);
          }
          if ( v13 )
            CertCloseStore((HCERTSTORE)v13, 0);
          return v9;
        }
        dwFlags = a4->dwFlags;
        if ( (dwFlags & 1) == 0 && (v14 & 0x1000) != 0 )
        {
          if ( a6[3] )
          {
            pvData = 0;
            pcbData = 4;
            if ( CertGetStoreProperty((HCERTSTORE)v13, 0xEu, &pvData, &pcbData) )
            {
              if ( (pvData & 1) != 0 )
                dwFlags |= 1u;
            }
          }
        }
        v18 = *a6;
        pvData = a4->dwPriority;
        EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
        if ( *(_DWORD *)v18 != 3 )
        {
          if ( *(_DWORD *)v18 != 1 || *(_DWORD *)(v18 + 20) != 2 )
            goto LABEL_91;
          for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
          {
            if ( *(_QWORD *)(v18 + 8 * i + 64) )
              goto LABEL_91;
          }
          if ( *(_QWORD *)(v18 + 88) )
          {
LABEL_91:
            v20 = 0;
LABEL_22:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
            if ( v20 )
            {
              v21 = LocalAlloc(0x40u, 0x30u);
              v22 = v21;
              if ( !v21 )
              {
                v30 = -2147024882;
                goto LABEL_50;
              }
              v21[2] = dwFlags;
              v23 = pvData;
              v21[3] = pvData;
              v21[1] = 1;
              *((_QWORD *)v21 + 2) = v18;
              _InterlockedAdd(v13 + 1, 1u);
              if ( (v13[4] & 4) != 0 )
                _InterlockedAdd(v13 + 26, 1u);
              *((_QWORD *)v21 + 3) = v13;
              EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
              v24 = *(_QWORD *)(v18 + 88);
              if ( v24 )
              {
                if ( v23 <= *(_DWORD *)(v24 + 12) )
                {
                  if ( *(_QWORD *)(v24 + 32) )
                  {
                    do
                    {
                      v28 = *(_QWORD *)(v24 + 32);
                      if ( v23 > *(_DWORD *)(v28 + 12) )
                        break;
                      v24 = *(_QWORD *)(v24 + 32);
                    }
                    while ( *(_QWORD *)(v28 + 32) );
                  }
                  *((_QWORD *)v22 + 5) = v24;
                  *((_QWORD *)v22 + 4) = *(_QWORD *)(v24 + 32);
                  v29 = *(_QWORD *)(v24 + 32);
                  if ( v29 )
                    *(_QWORD *)(v29 + 40) = v22;
                  *(_QWORD *)(v24 + 32) = v22;
                  goto LABEL_28;
                }
                *((_QWORD *)v22 + 4) = v24;
                *(_QWORD *)(v24 + 40) = v22;
              }
              *(_QWORD *)(v18 + 88) = v22;
LABEL_28:
              LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
              goto LABEL_29;
            }
LABEL_49:
            v30 = -2147024809;
LABEL_50:
            SetLastError(v30);
LABEL_51:
            v9 = 0;
            goto LABEL_30;
          }
          *(_DWORD *)v18 = 3;
        }
        v20 = 1;
        goto LABEL_22;
      }
      v39 = 0;
      pv = pvPara;
      pvData = GetSystemProviderFlags((PCNZCH)pszOpenStoreProvider);
      if ( !pvData )
      {
        if ( (a4->dwFlags & 8) == 0 )
        {
LABEL_73:
          if ( !pvPara )
            goto LABEL_51;
          goto LABEL_9;
        }
        v34 = a6[1];
        v32 = pvData & 2;
LABEL_69:
        if ( !v34 && !v39
          || (*(_QWORD *)&v45 = v34,
              hMem[1] = &v45,
              *((_QWORD *)&v45 + 1) = v39,
              hMem[0] = (HLOCAL)3,
              *(_QWORD *)&v46 = pv,
              hMem[0] = FormatSystemNamePath(1u, (struct _SYSTEM_NAME_GROUP *const)hMem),
              lpMultiByteStr = (LPCCH)hMem[0],
              !v32) )
        {
          if ( (pvData & 2) == 0 )
          {
LABEL_72:
            pvPara = (CHAR *)lpMultiByteStr;
            goto LABEL_73;
          }
LABEL_81:
          ICM_Free(pv);
          if ( !pszOpenStoreProvider )
          {
            v30 = -2147418113;
            goto LABEL_50;
          }
          goto LABEL_72;
        }
        v36 = pszOpenStoreProvider;
        if ( pszOpenStoreProvider > 0xFFFF )
        {
          if ( *(_BYTE *)pszOpenStoreProvider != 35 )
          {
LABEL_101:
            pszOpenStoreProvider = 0;
            if ( v36 == 12 )
              pszOpenStoreProvider = 13;
            goto LABEL_81;
          }
          v36 = o_atol_0((const char *)(pszOpenStoreProvider + 1));
        }
        if ( v36 == 9 )
        {
          pszOpenStoreProvider = 10;
          goto LABEL_81;
        }
        goto LABEL_101;
      }
      v47 = 0;
      v45 = 0;
      v46 = 0;
      if ( v14 < 0 )
        goto LABEL_49;
      v32 = pvData & 2;
      if ( (pvData & 2) != 0 )
      {
        v33 = (void *)MkWStr(lpMultiByteStr);
        pv = v33;
        if ( !v33 )
          goto LABEL_51;
      }
      else
      {
        v33 = pv;
      }
      v43 = 0;
      ParseSystemStorePara(v33, v14, ((pvData & 4) != 0) + 1, (struct _SYSTEM_NAME_INFO *)&v45);
      if ( *((_QWORD *)&v46 + 1) || !*((_QWORD *)&v45 + 1) || (v43 = a6[1], !a6[2]) )
      {
LABEL_68:
        FreeSystemNameInfo((struct _SYSTEM_NAME_INFO *)&v45);
        v34 = v43;
        goto LABEL_69;
      }
      if ( (v14 & 0xFF0000) == 0x40000 )
      {
        v14 = v14 & 0xFF00FFFF | 0x50000;
      }
      else
      {
        if ( (v14 & 0xFF0000) != 0x10000 )
          goto LABEL_68;
        v14 = v14 & 0xFF00FFFF | 0x60000;
      }
      v39 = a6[2];
      goto LABEL_68;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180046eb0  mov     [rsp-8+arg_0], rbx
0x180046eb5  push    rbp
0x180046eb6  push    rsi
0x180046eb7  push    rdi
0x180046eb8  push    r12
0x180046eba  push    r13
0x180046ebc  push    r14
0x180046ebe  push    r15
0x180046ec0  lea     rbp, [rsp-17h]
0x180046ec5  sub     rsp, 0B0h
0x180046ecc  mov     rax, cs:__security_cookie
0x180046ed3  xor     rax, rsp
0x180046ed6  mov     [rbp+47h+var_40], rax
0x180046eda  test    byte ptr [r9+28h], 2
0x180046edf  xorps   xmm0, xmm0
0x180046ee2  mov     r14, [rbp+47h+arg_28]
0x180046ee6  mov     r13, r9
0x180046ee9  movups  [rbp+47h+var_78], xmm0
0x180046eed  mov     rax, r8
0x180046ef0  mov     [rbp+47h+pcbData], edx
0x180046ef3  mov     edi, 1
0x180046ef8  jnz     loc_1800470B1
0x180046efe  mov     r8, [r14+18h]; lpString1
0x180046f02  test    r8, r8
0x180046f05  jnz     loc_1800471F1
0x180046f0b  mov     rcx, [r14+8]
0x180046f0f  test    rcx, rcx
0x180046f12  jnz     loc_180047169
0x180046f18  mov     ebx, [r13+14h]
0x180046f1c  xor     r12d, r12d
0x180046f1f  mov     r8d, 20000000h
0x180046f25  mov     [rbp+47h+hMem], r12
0x180046f29  or      ebx, r8d
0x180046f2c  test    r8d, edx
0x180046f2f  cmovz   ebx, [r13+14h]
0x180046f34  and     edx, edi
0x180046f36  mov     [rbp+47h+pcbData], edx
0x180046f39  jz      loc_180047179
0x180046f3f  mov     r15, [r13+20h]
0x180046f43  mov     rsi, [r13+8]
0x180046f47  mov     [rbp+47h+lpMultiByteStr], r15
0x180046f4b  test    rcx, rcx
0x180046f4e  jnz     loc_18004721D
0x180046f54  cmp     [r14+10h], r12
0x180046f58  jnz     loc_18004721D
0x180046f5e  cmp     [r14+20h], r12
0x180046f62  jnz     loc_18004734B
0x180046f68  mov     r9d, [r14+28h]
0x180046f6c  xor     r8d, r8d; hCryptProv
0x180046f6f  mov     edx, [r13+10h]; dwEncodingType
0x180046f73  and     r9d, 0CFC0h
0x180046f7a  or      r9d, ebx; dwFlags
0x180046f7d  mov     [rsp+0E0h+pvPara], r15; pvPara
0x180046f82  mov     rcx, rsi; lpszStoreProvider
0x180046f85  call    CertOpenStore
0x180046f8a  mov     r12, rax
0x180046f8d  test    rax, rax
0x180046f90  jz      loc_1800471A7
0x180046f96  mov     r15d, [r13+28h]
0x180046f9a  test    dil, r15b
0x180046f9d  setz    cl
0x180046fa0  bt      ebx, 0Ch
0x180046fa4  setb    al
0x180046fa7  test    al, cl
0x180046fa9  jnz     loc_180047121
0x180046faf  mov     eax, [r13+2Ch]
0x180046fb3  mov     rsi, [r14]
0x180046fb6  mov     [rbp+47h+pvData], eax
0x180046fb9  lea     r13, [rsi+18h]
0x180046fbd  mov     rcx, r13; lpCriticalSection
0x180046fc0  call    cs:__imp_EnterCriticalSection
0x180046fc6  cmp     dword ptr [rsi], 3
0x180046fc9  jz      short loc_180047005
0x180046fcb  cmp     [rsi], edi
0x180046fcd  jnz     loc_1800473A1
0x180046fd3  cmp     dword ptr [rsi+14h], 2
0x180046fd7  jnz     loc_1800473A1
0x180046fdd  xor     ecx, ecx
0x180046fdf  cmp     ecx, 3
0x180046fe2  jnb     short loc_180046FF4
0x180046fe4  cmp     qword ptr [rsi+rcx*8+40h], 0
0x180046fea  jnz     loc_1800473A1
0x180046ff0  add     ecx, edi
0x180046ff2  jmp     short loc_180046FDF
0x180046ff4  cmp     qword ptr [rsi+58h], 0
0x180046ff9  jnz     loc_1800473A1
0x180046fff  mov     dword ptr [rsi], 3
0x180047005  mov     ebx, edi
0x180047007  mov     rcx, r13; lpCriticalSection
0x18004700a  call    cs:__imp_LeaveCriticalSection
0x180047010  test    ebx, ebx
0x180047012  jz      loc_180047188
0x180047018  mov     edx, 30h ; '0'; uBytes
0x18004701d  lea     ecx, [rdx+10h]; uFlags
0x180047020  call    cs:__imp_LocalAlloc
0x180047026  mov     rbx, rax
0x180047029  test    rax, rax
0x18004702c  jz      loc_1800471EA
0x180047032  mov     [rax+8], r15d
0x180047036  mov     r15d, [rbp+47h+pvData]
0x18004703a  mov     [rax+0Ch], r15d
0x18004703e  mov     [rax+4], edi
0x180047041  mov     [rax+10h], rsi
0x180047045  lock add [r12+4], edi
0x18004704b  test    byte ptr [r12+10h], 4
0x180047051  jz      short loc_180047059
0x180047053  lock add [r12+68h], edi
0x180047059  mov     rcx, r13; lpCriticalSection
0x18004705c  mov     [rax+18h], r12
0x180047060  call    cs:__imp_EnterCriticalSection
0x180047066  mov     rcx, [rsi+58h]
0x18004706a  test    rcx, rcx
0x18004706d  jnz     short loc_1800470DA
0x18004706f  mov     [rsi+58h], rbx
0x180047073  mov     rcx, r13; lpCriticalSection
0x180047076  call    cs:__imp_LeaveCriticalSection
0x18004707c  mov     [r14+2Ch], edi
0x180047080  mov     rsi, [rbp+47h+hMem]
0x180047084  test    rsi, rsi
0x180047087  jz      short loc_1800470A2
0x180047089  call    cs:__imp_GetLastError
0x18004708f  mov     rcx, rsi; hMem
0x180047092  mov     ebx, eax
0x180047094  call    cs:__imp_LocalFree
0x18004709a  mov     ecx, ebx; dwErrCode
0x18004709c  call    cs:__imp_SetLastError
0x1800470a2  test    r12, r12
0x1800470a5  jz      short loc_1800470B1
0x1800470a7  xor     edx, edx; dwFlags
0x1800470a9  mov     rcx, r12; hCertStore
0x1800470ac  call    CertCloseStore
0x1800470b1  mov     eax, edi
0x1800470b3  mov     rcx, [rbp+47h+var_40]
0x1800470b7  xor     rcx, rsp; StackCookie
0x1800470ba  call    __security_check_cookie
0x1800470bf  mov     rbx, [rsp+0E0h+arg_0]
0x1800470c7  add     rsp, 0B0h
0x1800470ce  pop     r15
0x1800470d0  pop     r14
0x1800470d2  pop     r13
0x1800470d4  pop     r12
0x1800470d6  pop     rdi
0x1800470d7  pop     rsi
0x1800470d8  pop     rbp
0x1800470d9  retn
0x1800470da  cmp     r15d, [rcx+0Ch]
0x1800470de  ja      loc_18004719A
0x1800470e4  cmp     qword ptr [rcx+20h], 0
0x1800470e9  jz      short loc_1800470FF
0x1800470eb  mov     rax, [rcx+20h]
0x1800470ef  cmp     r15d, [rax+0Ch]
0x1800470f3  ja      short loc_1800470FF
0x1800470f5  cmp     qword ptr [rax+20h], 0
0x1800470fa  mov     rcx, rax
0x1800470fd  jnz     short loc_1800470EB
0x1800470ff  mov     [rbx+28h], rcx
0x180047103  mov     rax, [rcx+20h]
0x180047107  mov     [rbx+20h], rax
0x18004710b  mov     rax, [rcx+20h]
0x18004710f  test    rax, rax
0x180047112  jnz     loc_1800473A8
0x180047118  mov     [rcx+20h], rbx
0x18004711c  jmp     loc_180047073
0x180047121  cmp     qword ptr [r14+18h], 0
0x180047126  jz      loc_180046FAF
0x18004712c  lea     r9, [rbp+47h+pcbData]; pcbData
0x180047130  mov     [rbp+47h+pvData], 0
0x180047137  lea     r8, [rbp+47h+pvData]; pvData
0x18004713b  mov     [rbp+47h+pcbData], 4
0x180047142  mov     edx, 0Eh; dwPropId
0x180047147  mov     rcx, r12; hCertStore
0x18004714a  call    CertGetStoreProperty
0x18004714f  test    eax, eax
0x180047151  jz      loc_180046FAF
0x180047157  test    byte ptr [rbp+47h+pvData], dil
0x18004715b  jz      loc_180046FAF
0x180047161  or      r15d, edi
0x180047164  jmp     loc_180046FAF
0x180047169  test    byte ptr [r13+28h], 4
0x18004716e  jnz     loc_1800470B1
0x180047174  jmp     loc_180046F18
0x180047179  or      ebx, 20h
0x18004717c  test    ebx, 9D5h
0x180047182  jz      loc_180046F3F
0x180047188  mov     ecx, 80070057h; dwErrCode
0x18004718d  call    cs:__imp_SetLastError
0x180047193  xor     edi, edi
0x180047195  jmp     loc_180047080
0x18004719a  mov     [rbx+20h], rcx
0x18004719e  mov     [rcx+28h], rbx
0x1800471a2  jmp     loc_18004706F
0x1800471a7  call    cs:__imp_GetLastError
0x1800471ad  bt      ebx, 1Ch
0x1800471b1  jb      loc_18004737C
0x1800471b7  cmp     eax, 2
0x1800471ba  jnz     loc_18004738A
0x1800471c0  cmp     qword ptr [r14+18h], 0
0x1800471c5  jz      loc_180047080
0x1800471cb  cmp     [rbp+47h+pcbData], 0
0x1800471cf  jz      loc_180047080
0x1800471d5  mov     rcx, [r14]; hCollectionStore
0x1800471d8  xor     r9d, r9d; dwPriority
0x1800471db  xor     r8d, r8d; dwUpdateFlags
0x1800471de  xor     edx, edx; hSiblingStore
0x1800471e0  call    CertAddStoreToCollection
0x1800471e5  jmp     loc_18004707C
0x1800471ea  mov     ecx, 8007000Eh
0x1800471ef  jmp     short loc_18004718D
0x1800471f1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800471f5  mov     edx, edi; dwCmpFlags
0x1800471f7  mov     [rsp+0E0h+cchCount2], r9d; cchCount2
0x1800471fc  mov     ecx, 409h; Locale
0x180047201  mov     [rsp+0E0h+pvPara], rax; lpString2
0x180047206  call    cs:__imp_CompareStringW
0x18004720c  cmp     eax, 2
0x18004720f  jnz     loc_1800470B1
0x180047215  mov     edx, [rbp+47h+pcbData]
0x180047218  jmp     loc_180046F0B
0x18004721d  mov     rcx, rsi; lpString2
0x180047220  mov     [rbp+47h+var_A8], r12
0x180047224  mov     [rbp+47h+pv], r15
0x180047228  call    ?GetSystemProviderFlags@@YAKPEBD@Z; GetSystemProviderFlags(char const *)
0x18004722d  mov     [rbp+47h+pvData], eax
0x180047230  mov     ecx, eax
0x180047232  test    eax, eax
0x180047234  jz      loc_18004731F
0x18004723a  xor     eax, eax
0x18004723c  xorps   xmm0, xmm0
0x18004723f  mov     [rbp+47h+var_48], rax
0x180047243  movups  [rbp+47h+var_68], xmm0
0x180047247  movups  [rbp+47h+var_58], xmm0
0x18004724b  test    ebx, ebx
0x18004724d  js      loc_180047188
0x180047253  mov     r15d, ecx
0x180047256  and     r15d, 2
0x18004725a  jnz     loc_1800472E1
0x180047260  mov     rax, [rbp+47h+pv]
0x180047264  xor     ecx, ecx
0x180047266  lea     r9, [rbp+47h+var_68]; struct _SYSTEM_NAME_INFO *
0x18004726a  mov     [rbp+47h+var_80], rcx
0x18004726e  mov     edx, ebx; unsigned int
0x180047270  mov     ecx, [rbp+47h+pvData]
0x180047273  and     cl, 4
0x180047276  neg     cl
0x180047278  mov     rcx, rax; void *
0x18004727b  sbb     r8d, r8d
0x18004727e  neg     r8d
0x180047281  add     r8d, edi; unsigned int
0x180047284  call    ?ParseSystemStorePara@@YAHPEBXKKPEAU_SYSTEM_NAME_INFO@@@Z; ParseSystemStorePara(void const *,ulong,ulong,_SYSTEM_NAME_INFO *)
0x180047289  cmp     qword ptr [rbp+47h+var_58+8], r12
0x18004728d  jnz     short loc_1800472A6
0x18004728f  cmp     qword ptr [rbp+47h+var_68+8], r12
0x180047293  jz      short loc_1800472A6
0x180047295  mov     rcx, [r14+8]
0x180047299  mov     [rbp+47h+var_80], rcx
0x18004729d  mov     rcx, [r14+10h]
0x1800472a1  test    rcx, rcx
0x1800472a4  jnz     short loc_1800472FC
0x1800472a6  lea     rcx, [rbp+47h+var_68]; struct _SYSTEM_NAME_INFO *
0x1800472aa  call    ?FreeSystemNameInfo@@YAXPEAU_SYSTEM_NAME_INFO@@@Z; FreeSystemNameInfo(_SYSTEM_NAME_INFO *)
0x1800472af  mov     rax, [rbp+47h+var_80]
0x1800472b3  mov     rcx, [rbp+47h+var_A8]
0x1800472b7  test    rax, rax
0x1800472ba  jnz     loc_180117FFC
0x1800472c0  test    rcx, rcx
0x1800472c3  jnz     loc_180117FFC
0x1800472c9  test    byte ptr [rbp+47h+pvData], 2
0x1800472cd  jnz     short loc_180047333
0x1800472cf  mov     r15, [rbp+47h+lpMultiByteStr]
0x1800472d3  test    r15, r15
0x1800472d6  jnz     loc_180046F5E
0x1800472dc  jmp     loc_180047193
0x1800472e1  mov     rcx, [rbp+47h+lpMultiByteStr]; lpMultiByteStr
0x1800472e5  call    MkWStr
0x1800472ea  mov     [rbp+47h+pv], rax
0x1800472ee  test    rax, rax
0x1800472f1  jz      loc_180047193
0x1800472f7  jmp     loc_180047264
0x1800472fc  mov     eax, ebx
0x1800472fe  and     eax, 0FF0000h
0x180047303  cmp     eax, 40000h
0x180047308  jnz     loc_180117FDC
0x18004730e  and     ebx, 0FF05FFFFh
0x180047314  or      ebx, 50000h
0x18004731a  jmp     loc_180117FF3
0x18004731f  test    byte ptr [r13+28h], 8
0x180047324  jz      short loc_1800472D3
0x180047326  mov     rax, [r14+8]
0x18004732a  mov     r15d, ecx
0x18004732d  and     r15d, 2
0x180047331  jmp     short loc_1800472B3
0x180047333  mov     rcx, [rbp+47h+pv]; pv
0x180047337  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x18004733c  test    rsi, rsi
0x18004733f  jnz     short loc_1800472CF
0x180047341  mov     ecx, 8000FFFFh
0x180047346  jmp     loc_18004718D
0x18004734b  mov     rcx, rsi; lpString2
0x18004734e  call    ?GetSystemProviderFlags@@YAKPEBD@Z; GetSystemProviderFlags(char const *)
0x180047353  test    eax, eax
  ... truncated ...
```
