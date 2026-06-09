# CScmPatternTbl::InitTbl(void)

- ea: `0x180059380`
- end: `0x18005971d`
- name: `?InitTbl@CScmPatternTbl@@QEAAJXZ`
- size: `925`
- prototype: `HRESULT __fastcall(CScmPatternTbl *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180059a98`

## callees

- `0x18000e924`
- `0x18000fc2c`
- `0x18001a630`
- `0x18003a394`
- `0x180046460`
- `0x180046c08`
- `0x180047484`
- `0x180059380`
- `0x180059904`
- `0x1800c8934`
- `0x1800ce967`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005964c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005964c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800593d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005961d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800593d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005961d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059458`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005955c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059458`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005955c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059517`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059517`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800596b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800596d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800596b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800596d6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800594e7`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800594e7`

## string_xrefs

- `0x180059485`: `Clsid\`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CScmPatternTbl::InitTbl(CScmPatternTbl *this)
{
  unsigned __int8 *v2; // rax
  unsigned int *v3; // rbx
  DWORD i; // r12d
  DWORD v6; // r15d
  unsigned int v7; // edx
  unsigned __int64 v8; // rax
  int v9; // r9d
  unsigned int v10; // ecx
  unsigned int v11; // r8d
  unsigned int v12; // ecx
  unsigned int *v13; // rdi
  unsigned int v14; // eax
  unsigned int v15; // r13d
  unsigned int *v16; // rax
  unsigned int *v17; // r14
  _QWORD *v18; // rax
  SPatternEntry *v19; // rdi
  unsigned int ulCb; // eax
  HKEY__ *hkClsid; // [rsp+48h] [rbp-C0h] BYREF
  HKEY__ *hkFileType; // [rsp+50h] [rbp-B8h] BYREF
  HKEY cbTemp; // [rsp+58h] [rbp-B0h] OVERLAPPED BYREF
  int cbValue[2]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE clsid[25]; // [rsp+68h] [rbp-A0h] OVERLAPPED BYREF
  wchar_t szBuf[40]; // [rsp+90h] [rbp-78h] BYREF
  wchar_t szClsid[80]; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t szTemp[264]; // [rsp+180h] [rbp+78h] BYREF
  wchar_t szPattern[524]; // [rsp+390h] [rbp+288h] BYREF

  *(_QWORD *)clsid = this;
  v2 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, 0x800u);
  this->_pLocTbl = v2;
  v3 = (unsigned int *)v2;
  if ( !v2 )
    return 2147942414LL;
  *(_QWORD *)v2 = 2048;
  *((_DWORD *)v2 + 2) = 16;
  *((_DWORD *)v2 + 3) = 16;
  cbTemp = 0;
  if ( !(unsigned int)OpenClassesRootKeyExW(L"FileType", 0x2000000u, &cbTemp) )
  {
    for ( i = 0; ; ++i )
    {
      LODWORD(hkClsid) = 40;
      if ( RegEnumKeyExW(cbTemp, i, &szBuf[4], (LPDWORD)&hkClsid, 0, 0, 0, 0) )
        break;
      szClsid[3] = 0;
      memset_0(&szTemp[4], 0, 0x208u);
      cbValue[0] = 520;
      StringCchCopyW(&szClsid[4], 0x50u, L"Clsid\\");
      StringCchCatW(&szClsid[4], 0x50u, &szBuf[4]);
      if ( !QueryClassesRootValueW(&szClsid[4], &szTemp[4], cbValue) )
      {
        hkFileType = 0;
        *(_OWORD *)&clsid[8] = 0;
        if ( CLSIDFromString(&szBuf[4], (LPCLSID)&clsid[8]) >= 0
          && !RegOpenKeyExW(cbTemp, &szBuf[4], 0, 0x20019u, &hkFileType) )
        {
          v6 = 0;
LABEL_10:
          LODWORD(hkClsid) = 10;
          if ( RegEnumKeyExW(hkFileType, v6, (LPWSTR)&clsid[24], (LPDWORD)&hkClsid, 0, 0, 0, 0) )
          {
            RegCloseKey(hkFileType);
            continue;
          }
          HIDWORD(hkClsid) = 1024;
          if ( wRegQueryValue(hkFileType, (const wchar_t *)&clsid[24], &szPattern[4], (unsigned int *)&hkClsid + 1) )
            goto LABEL_31;
          v7 = HIDWORD(hkClsid);
          v8 = HIDWORD(hkClsid) & 0xFFFFFFFE;
          if ( v8 >= 0x402 )
            _report_rangecheckfailure();
          *(wchar_t *)((char *)&szPattern[4] + v8) = 0;
          v9 = 1;
          if ( v7 + 1 < v7 || (v10 = (v7 + 1) >> 1, v11 = v10 + v3[3], v11 < v10) )
          {
            v13 = v3;
          }
          else
          {
            v12 = v11 + 32;
            v13 = v3;
            if ( v11 + 32 >= v11 )
            {
              v9 = 0;
              goto LABEL_19;
            }
          }
          v12 = -1;
LABEL_19:
          if ( v12 <= *v3 )
          {
            if ( v9 )
              goto LABEL_31;
            v18 = *(_QWORD **)clsid;
            goto LABEL_27;
          }
          if ( !v9 )
          {
            v14 = *v3 + 2048;
            if ( v12 > v14 )
              v14 = v12;
            v15 = v14;
            v16 = (unsigned int *)HeapAlloc(g_hHeap, 0, v14);
            v17 = v16;
            if ( v16 )
            {
              memcpy_0(v16, v3, v13[3]);
              HeapFree(g_hHeap, 0, v3);
              v18 = *(_QWORD **)clsid;
              v3 = v17;
              **(_QWORD **)clsid = v17;
              *v17 = v15;
              v7 = HIDWORD(hkClsid);
LABEL_27:
              v19 = (SPatternEntry *)(*v18 + v3[3]);
              if ( ParseEntry(&szPattern[4], v7, v19, (const _GUID *)&clsid[8]) )
              {
                ulCb = v3[1];
                if ( ulCb <= v19->ulCb )
                  ulCb = v19->ulCb;
                v3[1] = ulCb;
                v3[3] += v19->ulEntryLen;
              }
            }
          }
LABEL_31:
          ++v6;
          goto LABEL_10;
        }
      }
    }
    RegCloseKey(cbTemp);
  }
  *v3 = v3[3] + 16;
  return 0;
}

```

## disassembly

```asm
0x180059380  mov     rax, rsp
0x180059383  mov     [rax+10h], rbx
0x180059387  mov     [rax+18h], rsi
0x18005938b  mov     [rax+20h], rdi
0x18005938f  push    rbp
0x180059390  push    r12
0x180059392  push    r13
0x180059394  push    r14
0x180059396  push    r15
0x180059398  lea     rbp, [rax-6D8h]
0x18005939f  sub     rsp, 7B0h
0x1800593a6  mov     rax, cs:__security_cookie
0x1800593ad  xor     rax, rsp
0x1800593b0  mov     [rbp+6D0h+var_30], rax
0x1800593b7  mov     rdi, this
0x1800593ba  mov     qword ptr [rsp+7D0h+clsid.Data1], this
0x1800593bf  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800593c6  mov     esi, 800h
0x1800593cb  mov     r8d, esi; dwBytes
0x1800593ce  xor     edx, edx; dwFlags
0x1800593d0  call    cs:__imp_HeapAlloc
0x1800593d7  nop     dword ptr [rax+rax+00h]
0x1800593dc  xor     r14d, r14d
0x1800593df  mov     [rdi], rax
0x1800593e2  mov     rbx, rax
0x1800593e5  test    rax, rax
0x1800593e8  jnz     short loc_1800593F4
0x1800593ea  mov     eax, 8007000Eh
0x1800593ef  jmp     loc_1800596EC
0x1800593f4  mov     [rax], rsi
0x1800593f7  lea     r8, [rsp+7D0h+cbTemp]; phkResult
0x1800593fc  mov     dword ptr [rax+8], 10h
0x180059403  lea     this, aFiletype; "FileType"
0x18005940a  mov     dword ptr [rax+0Ch], 10h
0x180059411  mov     edx, 2000000h; samDesired
0x180059416  mov     [rsp+7D0h+cbTemp], r14
0x18005941b  call    OpenClassesRootKeyExW
0x180059420  test    eax, eax
0x180059422  jnz     loc_1800596E2
0x180059428  mov     r12d, r14d
0x18005942b  mov     this, [rsp+7D0h+cbTemp]; hKey
0x180059430  lea     r9, [rsp+7D0h+hkClsid]; lpcchName
0x180059435  mov     qword ptr [rsp+7D0h+Size], r14; lpftLastWriteTime
0x18005943a  lea     r8, [rbp+6D0h+szBuf+8]; lpName
0x18005943e  mov     [rsp+7D0h+lpcchClass], r14; lpcchClass
0x180059443  mov     edx, r12d; dwIndex
0x180059446  mov     [rsp+7D0h+lpClass], r14; lpClass
0x18005944b  mov     [rsp+7D0h+lpReserved], r14; lpReserved
0x180059450  mov     dword ptr [rsp+7D0h+hkClsid], 28h ; '('
0x180059458  call    cs:__imp_RegEnumKeyExW
0x18005945f  nop     dword ptr [rax+rax+00h]
0x180059464  test    eax, eax
0x180059466  jnz     loc_1800596D1
0x18005946c  xor     edx, edx; Val
0x18005946e  mov     [rbp+6D0h+szClsid+6], r14w
0x180059473  mov     r8d, 208h; Size
0x180059479  lea     this, [rbp+6D0h+szTemp+8]; void *
0x180059480  call    memset_0
0x180059485  lea     r8, aClsid_2; "Clsid\\"
0x18005948c  mov     [rsp+7D0h+cbValue], 208h
0x180059494  mov     edx, 50h ; 'P'; cchDest
0x180059499  lea     this, [rbp+6D0h+szClsid+8]; pszDest
0x18005949d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800594a2  lea     r8, [rbp+6D0h+szBuf+8]; pszSrc
0x1800594a6  mov     edx, 50h ; 'P'; cchDest
0x1800594ab  lea     this, [rbp+6D0h+szClsid+8]; pszDest
0x1800594af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800594b4  lea     r8, [rsp+7D0h+cbValue]; lpcbValue
0x1800594b9  lea     rdx, [rbp+6D0h+szTemp+8]; pszValue
0x1800594c0  lea     this, [rbp+6D0h+szClsid+8]; pszSubKey
0x1800594c4  call    QueryClassesRootValueW
0x1800594c9  test    eax, eax
0x1800594cb  jnz     loc_1800596C3
0x1800594d1  xorps   xmm0, xmm0
0x1800594d4  mov     [rsp+7D0h+hkFileType], r14
0x1800594d9  lea     rdx, [rsp+7D0h+clsid.Data4]; pclsid
0x1800594de  lea     this, [rbp+6D0h+szBuf+8]; lpsz
0x1800594e2  movups  xmmword ptr [rsp+7D0h+clsid.Data4], xmm0
0x1800594e7  call    cs:__imp_CLSIDFromString
0x1800594ee  nop     dword ptr [rax+rax+00h]
0x1800594f3  test    eax, eax
0x1800594f5  js      loc_1800596C3
0x1800594fb  mov     this, [rsp+7D0h+cbTemp]; hKey
0x180059500  lea     rax, [rsp+7D0h+hkFileType]
0x180059505  mov     r9d, 20019h; samDesired
0x18005950b  mov     [rsp+7D0h+lpReserved], rax; phkResult
0x180059510  xor     r8d, r8d; ulOptions
0x180059513  lea     rdx, [rbp+6D0h+szBuf+8]; lpSubKey
0x180059517  call    cs:__imp_RegOpenKeyExW
0x18005951e  nop     dword ptr [rax+rax+00h]
0x180059523  test    eax, eax
0x180059525  jnz     loc_1800596C3
0x18005952b  mov     r15d, r14d
0x18005952e  mov     this, [rsp+7D0h+hkFileType]; hKey
0x180059533  lea     r9, [rsp+7D0h+hkClsid]; lpcchName
0x180059538  mov     qword ptr [rsp+7D0h+Size], r14; lpftLastWriteTime
0x18005953d  lea     r8, [rsp+7D0h+szNum+8]; lpName
0x180059542  mov     [rsp+7D0h+lpcchClass], r14; lpcchClass
0x180059547  mov     edx, r15d; dwIndex
0x18005954a  mov     [rsp+7D0h+lpClass], r14; lpClass
0x18005954f  mov     [rsp+7D0h+lpReserved], r14; lpReserved
0x180059554  mov     dword ptr [rsp+7D0h+hkClsid], 0Ah
0x18005955c  call    cs:__imp_RegEnumKeyExW
0x180059563  nop     dword ptr [rax+rax+00h]
0x180059568  mov     this, [rsp+7D0h+hkFileType]; hKey
0x18005956d  test    eax, eax
0x18005956f  jnz     loc_1800596B7
0x180059575  lea     r9, [rsp+7D0h+hkClsid+4]; lpdwSize
0x18005957a  mov     dword ptr [rsp+7D0h+hkClsid+4], 400h
0x180059582  lea     r8, [rbp+6D0h+szPattern+8]; lpValue
0x180059589  lea     rdx, [rsp+7D0h+szNum+8]; lpSubKey
0x18005958e  call    wRegQueryValue
0x180059593  test    eax, eax
0x180059595  jnz     loc_1800596AF
0x18005959b  mov     edx, dword ptr [rsp+7D0h+hkClsid+4]; cb
0x18005959f  mov     eax, edx
0x1800595a1  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800595a5  cmp     rax, 402h
0x1800595ab  jnb     loc_1800596CB
0x1800595b1  lea     ecx, [rdx+1]
0x1800595b4  mov     [rbp+rax+6D0h+szPattern+8], r14w
0x1800595bd  mov     r9d, 1
0x1800595c3  cmp     ecx, edx
0x1800595c5  jb      short loc_1800595EA
0x1800595c7  mov     r8d, [rbx+0Ch]
0x1800595cb  shr     ecx, 1
0x1800595cd  add     r8d, ecx
0x1800595d0  cmp     r8d, ecx
0x1800595d3  jb      short loc_1800595EA
0x1800595d5  lea     ecx, [r8+20h]
0x1800595d9  mov     rdi, rbx
0x1800595dc  lea     esi, [r9+0Bh]
0x1800595e0  cmp     ecx, r8d
0x1800595e3  jb      short loc_1800595F2
0x1800595e5  mov     r9d, r14d
0x1800595e8  jmp     short loc_1800595F5
0x1800595ea  mov     esi, 0Ch
0x1800595ef  mov     rdi, rbx
0x1800595f2  or      ecx, 0FFFFFFFFh
0x1800595f5  mov     eax, [rbx]
0x1800595f7  cmp     ecx, eax
0x1800595f9  jbe     short loc_18005966F
0x1800595fb  test    r9d, r9d
0x1800595fe  jnz     loc_1800596AF
0x180059604  add     eax, 800h
0x180059609  cmp     ecx, eax
0x18005960b  cmova   eax, ecx
0x18005960e  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180059615  mov     r8d, eax; dwBytes
0x180059618  xor     edx, edx; dwFlags
0x18005961a  mov     r13d, eax
0x18005961d  call    cs:__imp_HeapAlloc
0x180059624  nop     dword ptr [rax+rax+00h]
0x180059629  mov     r14, rax
0x18005962c  test    rax, rax
0x18005962f  jz      short loc_1800596AC
0x180059631  mov     r8d, [rsi+rdi]; Size
0x180059635  mov     rdx, rbx; Src
0x180059638  mov     this, rax; void *
0x18005963b  call    memcpy_0
0x180059640  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x180059647  mov     r8, rbx; lpMem
0x18005964a  xor     edx, edx; dwFlags
0x18005964c  call    cs:__imp_HeapFree
0x180059653  nop     dword ptr [rax+rax+00h]
0x180059658  mov     rax, qword ptr [rsp+7D0h+clsid.Data1]
0x18005965d  mov     rbx, r14
0x180059660  mov     [rax], r14
0x180059663  mov     [r14], r13d
0x180059666  xor     r14d, r14d
0x180059669  mov     edx, dword ptr [rsp+7D0h+hkClsid+4]
0x18005966d  jmp     short loc_180059679
0x18005966f  test    r9d, r9d
0x180059672  jnz     short loc_1800596AF
0x180059674  mov     rax, qword ptr [rsp+7D0h+clsid.Data1]
0x180059679  mov     edi, [rbx+0Ch]
0x18005967c  lea     r9, [rsp+7D0h+clsid.Data4]; rclsid
0x180059681  add     rdi, [rax]
0x180059684  lea     this, [rbp+6D0h+szPattern+8]; psz
0x18005968b  mov     r8, rdi; pEntry
0x18005968e  call    ParseEntry
0x180059693  test    eax, eax
0x180059695  jz      short loc_1800596AF
0x180059697  mov     eax, [rbx+4]
0x18005969a  cmp     eax, [rdi+18h]
0x18005969d  cmovbe  eax, [rdi+18h]
0x1800596a1  mov     [rbx+4], eax
0x1800596a4  mov     eax, [rdi+10h]
0x1800596a7  add     [rbx+0Ch], eax
0x1800596aa  jmp     short loc_1800596AF
0x1800596ac  xor     r14d, r14d
0x1800596af  inc     r15d
0x1800596b2  jmp     loc_18005952E
0x1800596b7  call    cs:__imp_RegCloseKey
0x1800596be  nop     dword ptr [rax+rax+00h]
0x1800596c3  inc     r12d
0x1800596c6  jmp     loc_18005942B
0x1800596cb  call    __report_rangecheckfailure
0x1800596d1  mov     this, [rsp+7D0h+cbTemp]; hKey
0x1800596d6  call    cs:__imp_RegCloseKey
0x1800596dd  nop     dword ptr [rax+rax+00h]
0x1800596e2  mov     eax, [rbx+0Ch]
0x1800596e5  add     eax, 10h
0x1800596e8  mov     [rbx], eax
0x1800596ea  xor     eax, eax
0x1800596ec  mov     this, [rbp+6D0h+var_30]
0x1800596f3  xor     this, rsp; StackCookie
0x1800596f6  call    __security_check_cookie
0x1800596fb  lea     r11, [rsp+7D0h+var_20]
0x180059703  mov     rbx, [r11+38h]
0x180059707  mov     rsi, [r11+40h]
0x18005970b  mov     rdi, [r11+48h]
0x18005970f  mov     rsp, r11
0x180059712  pop     r15
0x180059714  pop     r14
0x180059716  pop     r13
0x180059718  pop     r12
0x18005971a  pop     rbp
0x18005971b  retn
```
