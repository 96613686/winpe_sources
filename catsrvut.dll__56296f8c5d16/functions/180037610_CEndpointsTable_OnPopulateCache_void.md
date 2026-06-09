# CEndpointsTable::OnPopulateCache(void)

- ea: `0x180037610`
- end: `0x180037985`
- name: `?OnPopulateCache@CEndpointsTable@@UEAAJXZ`
- size: `885`
- prototype: `__int64 __fastcall(CEndpointsTable *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180014ec8`
- `0x180037610`
- `0x1800391d0`
- `0x180053994`
- `0x180054464`
- `0x180054630`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037943`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037932`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037943`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376bf`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800376bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800377ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800377ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037743`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037743`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800377e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037776`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800377e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037953`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037953`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEndpointsTable::OnPopulateCache(CEndpointsTable *this)
{
  __int64 v3; // rax
  int v4; // ebx
  const unsigned __int16 *v5; // r10
  BYTE *v6; // r14
  LSTATUS v7; // edi
  __int64 v8; // r13
  __int64 v9; // r10
  __int64 v10; // rax
  __int64 v11; // r8
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-B8h] BYREF
  void *v17; // [rsp+50h] [rbp-B0h]
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v19[264]; // [rsp+270h] [rbp+170h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( *((_DWORD *)this + 37) )
    return CCustomDataTable::PopulateCache(this);
  lpsz = 0;
  if ( *((_DWORD *)this + 32) != 1 )
    return 2147942487LL;
  v3 = *((_QWORD *)this + 15);
  if ( !v3 )
    return 2147942487LL;
  if ( *(_DWORD *)(v3 + 8) )
    return 2147942487LL;
  if ( *(_DWORD *)(v3 + 12) != 2 )
    return 2147942487LL;
  if ( *(_DWORD *)(v3 + 16) != 72 )
    return 2147942487LL;
  if ( (*(_DWORD *)(v3 + 20) & 0xFFFFFFEF) != 0 )
    return 2147942487LL;
  v17 = *(void **)v3;
  if ( StringFromIID((const IID *const)v17, &lpsz) < 0 || !lpsz || !*lpsz )
    return 2147942487LL;
  v4 = StringCchCopyW(SubKey, 0x104u, L"Software\\Classes\\AppID\\");
  if ( v4 >= 0 )
  {
    v4 = StringCchCatW(SubKey, 0x104u, v5);
    if ( v4 >= 0 )
    {
      v6 = 0;
      v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      if ( !v7 )
      {
        v7 = RegQueryValueExW(hKey, L"Endpoints", 0, &Type, 0, &cbData);
        if ( !v7 )
        {
          if ( !cbData )
            goto LABEL_34;
          v6 = (BYTE *)CoTaskMemAlloc(saturated_mul((unsigned __int64)cbData >> 1, 2u));
          if ( !v6 )
          {
            v4 = -2147024882;
            goto LABEL_41;
          }
          v7 = RegQueryValueExW(hKey, L"Endpoints", 0, &Type, v6, &cbData);
          if ( !v7 )
          {
            v8 = 0;
            while ( *(_WORD *)&v6[2 * v8] )
            {
              if ( v4 < 0 )
                goto LABEL_40;
              v4 = StringCchCopyW(v19, 0x104u, (const unsigned __int16 *)&v6[2 * v8]);
              if ( v4 < 0 )
                goto LABEL_40;
              v10 = -1;
              do
                ++v10;
              while ( *(_WORD *)(v9 + 2 * v10) );
              v8 += v10 + 1;
              v15 = v8;
              ++*((_DWORD *)this + 36);
              v4 = CSimpleDataTableCursor::InternalAddRowForInsert((CEndpointsTable *)((char *)this + 40));
              if ( v4 >= 0 )
              {
                v4 = CSimpleDataTableCursor::InternalSetWriteColumn(
                       (CEndpointsTable *)((char *)this + 40),
                       0,
                       4u,
                       (_WORD *)this + 72);
                if ( v4 >= 0 )
                {
                  v11 = -1;
                  do
                    ++v11;
                  while ( v19[v11] );
                  v4 = CSimpleDataTableCursor::InternalSetWriteColumn(
                         (CEndpointsTable *)((char *)this + 40),
                         1u,
                         2 * (int)v11 + 2,
                         v19);
                  if ( v4 >= 0 )
                  {
                    v4 = CSimpleDataTableCursor::InternalSetWriteColumn(
                           (CEndpointsTable *)((char *)this + 40),
                           2u,
                           0x10u,
                           v17);
                    if ( v4 >= 0 )
                    {
                      v4 = CSimpleDataTableCursor::InternalSetWriteColumn(
                             (CEndpointsTable *)((char *)this + 40),
                             3u,
                             4u,
                             &v15);
                      if ( v4 >= 0 )
                        v4 = CSimpleDataTableCursor::InternalSetRow((CEndpointsTable *)((char *)this + 40));
                    }
                  }
                }
              }
            }
LABEL_34:
            if ( v4 < 0 )
              goto LABEL_39;
          }
        }
      }
      if ( v7 )
      {
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        else
          v4 = v7;
      }
LABEL_39:
      if ( v6 )
LABEL_40:
        CoTaskMemFree(v6);
    }
  }
LABEL_41:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180037610  push    rbp
0x180037612  push    rbx
0x180037613  push    rsi
0x180037614  push    rdi
0x180037615  push    r12
0x180037617  push    r13
0x180037619  push    r14
0x18003761b  push    r15
0x18003761d  lea     rbp, [rsp-398h]
0x180037625  sub     rsp, 498h
0x18003762c  mov     rax, cs:__security_cookie
0x180037633  xor     rax, rsp
0x180037636  mov     [rbp+3D0h+var_50], rax
0x18003763d  mov     rsi, rcx
0x180037640  xor     r12d, r12d
0x180037643  mov     [rsp+4D0h+hKey], r12
0x180037648  mov     [rsp+4D0h+Type], r12d
0x18003764d  mov     [rsp+4D0h+cbData], r12d
0x180037652  cmp     [rcx+94h], r12d
0x180037659  jz      short loc_180037665
0x18003765b  call    ?PopulateCache@CCustomDataTable@@UEAAJXZ; CCustomDataTable::PopulateCache(void)
0x180037660  jmp     loc_180037962
0x180037665  mov     [rsp+4D0h+lpsz], r12
0x18003766a  cmp     dword ptr [rcx+80h], 1
0x180037671  jnz     loc_18003795D
0x180037677  mov     rax, [rcx+78h]
0x18003767b  test    rax, rax
0x18003767e  jz      loc_18003795D
0x180037684  cmp     [rax+8], r12d
0x180037688  jnz     loc_18003795D
0x18003768e  cmp     dword ptr [rax+0Ch], 2
0x180037692  jnz     loc_18003795D
0x180037698  cmp     dword ptr [rax+10h], 48h ; 'H'
0x18003769c  jnz     loc_18003795D
0x1800376a2  test    dword ptr [rax+14h], 0FFFFFFEFh
0x1800376a9  jnz     loc_18003795D
0x1800376af  mov     rax, [rax]
0x1800376b2  mov     [rsp+4D0h+var_480], rax
0x1800376b7  lea     rdx, [rsp+4D0h+lpsz]; lplpsz
0x1800376bc  mov     rcx, rax; rclsid
0x1800376bf  call    cs:__imp_StringFromIID
0x1800376c5  test    eax, eax
0x1800376c7  js      loc_18003795D
0x1800376cd  mov     r10, [rsp+4D0h+lpsz]
0x1800376d2  test    r10, r10
0x1800376d5  jz      loc_18003795D
0x1800376db  cmp     r12w, [r10]
0x1800376df  jz      loc_18003795D
0x1800376e5  lea     r8, aSoftwareClasse; "Software\\Classes\\AppID\\"
0x1800376ec  mov     edx, 104h; unsigned __int64
0x1800376f1  lea     rcx, [rsp+4D0h+SubKey]; unsigned __int16 *
0x1800376f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800376fb  mov     ebx, eax
0x1800376fd  test    eax, eax
0x1800376ff  js      loc_180037939
0x180037705  mov     r8, r10; unsigned __int16 *
0x180037708  mov     edx, 104h; unsigned __int64
0x18003770d  lea     rcx, [rsp+4D0h+SubKey]; unsigned __int16 *
0x180037712  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180037717  mov     ebx, eax
0x180037719  test    eax, eax
0x18003771b  js      loc_180037939
0x180037721  mov     r14, r12
0x180037724  lea     rax, [rsp+4D0h+hKey]
0x180037729  mov     [rsp+4D0h+phkResult], rax; phkResult
0x18003772e  mov     r9d, 20019h; samDesired
0x180037734  xor     r8d, r8d; ulOptions
0x180037737  lea     rdx, [rsp+4D0h+SubKey]; lpSubKey
0x18003773c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037743  call    cs:__imp_RegOpenKeyExW
0x180037749  mov     edi, eax
0x18003774b  test    eax, eax
0x18003774d  jnz     loc_180037917
0x180037753  lea     rax, [rsp+4D0h+cbData]
0x180037758  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x18003775d  mov     [rsp+4D0h+phkResult], r12; lpData
0x180037762  lea     r9, [rsp+4D0h+Type]; lpType
0x180037767  xor     r8d, r8d; lpReserved
0x18003776a  lea     rdx, aEndpoints; "Endpoints"
0x180037771  mov     rcx, [rsp+4D0h+hKey]; hKey
0x180037776  call    cs:__imp_RegQueryValueExW
0x18003777c  mov     edi, eax
0x18003777e  test    eax, eax
0x180037780  jnz     loc_180037917
0x180037786  mov     eax, [rsp+4D0h+cbData]
0x18003778a  test    eax, eax
0x18003778c  jz      loc_180037913
0x180037792  mov     ecx, eax
0x180037794  shr     rcx, 1
0x180037797  lea     eax, [rdi+2]
0x18003779a  mul     rcx
0x18003779d  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800377a4  cmovb   rax, r15
0x1800377a8  mov     rcx, rax; cb
0x1800377ab  call    cs:__imp_CoTaskMemAlloc
0x1800377b1  mov     r14, rax
0x1800377b4  test    rax, rax
0x1800377b7  jnz     short loc_1800377C3
0x1800377b9  mov     ebx, 8007000Eh
0x1800377be  jmp     loc_180037939
0x1800377c3  lea     rax, [rsp+4D0h+cbData]
0x1800377c8  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x1800377cd  mov     [rsp+4D0h+phkResult], r14; lpData
0x1800377d2  lea     r9, [rsp+4D0h+Type]; lpType
0x1800377d7  xor     r8d, r8d; lpReserved
0x1800377da  lea     rdx, aEndpoints; "Endpoints"
0x1800377e1  mov     rcx, [rsp+4D0h+hKey]; hKey
0x1800377e6  call    cs:__imp_RegQueryValueExW
0x1800377ec  mov     edi, eax
0x1800377ee  test    eax, eax
0x1800377f0  jnz     loc_180037917
0x1800377f6  mov     r13, r12
0x1800377f9  jmp     short loc_180037802
0x1800377fb  xor     r12d, r12d
0x1800377fe  or      r15, 0FFFFFFFFFFFFFFFFh
0x180037802  lea     r10, [r14+r13*2]
0x180037806  cmp     [r10], r12w
0x18003780a  jz      loc_180037913
0x180037810  test    ebx, ebx
0x180037812  js      loc_18003792F
0x180037818  mov     r8, r10; unsigned __int16 *
0x18003781b  mov     edx, 104h; unsigned __int64
0x180037820  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x180037827  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003782c  mov     ebx, eax
0x18003782e  test    eax, eax
0x180037830  js      loc_18003792F
0x180037836  mov     rax, r15
0x180037839  inc     rax
0x18003783c  cmp     [r10+rax*2], r12w
0x180037841  jnz     short loc_180037839
0x180037843  inc     rax
0x180037846  add     r13, rax
0x180037849  mov     [rsp+4D0h+var_490], r13d
0x18003784e  lea     r12, [rsi+90h]
0x180037855  inc     dword ptr [r12]
0x180037859  lea     r15, [rsi+28h]
0x18003785d  mov     rcx, r15; this
0x180037860  call    ?InternalAddRowForInsert@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalAddRowForInsert(void)
0x180037865  mov     ebx, eax
0x180037867  test    eax, eax
0x180037869  js      short loc_1800377FB
0x18003786b  mov     r9, r12; void *
0x18003786e  xor     edx, edx; unsigned int
0x180037870  lea     r8d, [rdx+4]; unsigned int
0x180037874  mov     rcx, r15; this
0x180037877  call    ?InternalSetWriteColumn@CSimpleDataTableCursor@@QEAAJKKPEAX@Z; CSimpleDataTableCursor::InternalSetWriteColumn(ulong,ulong,void *)
0x18003787c  mov     ebx, eax
0x18003787e  xor     r12d, r12d
0x180037881  test    eax, eax
0x180037883  js      loc_1800377FE
0x180037889  lea     rax, [rbp+3D0h+var_260]
0x180037890  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037894  inc     r8
0x180037897  cmp     [rax+r8*2], r12w
0x18003789c  jnz     short loc_180037894
0x18003789e  lea     r8d, ds:2[r8*2]; unsigned int
0x1800378a6  lea     r9, [rbp+3D0h+var_260]; void *
0x1800378ad  mov     edx, 1; unsigned int
0x1800378b2  mov     rcx, r15; this
0x1800378b5  call    ?InternalSetWriteColumn@CSimpleDataTableCursor@@QEAAJKKPEAX@Z; CSimpleDataTableCursor::InternalSetWriteColumn(ulong,ulong,void *)
0x1800378ba  mov     ebx, eax
0x1800378bc  test    eax, eax
0x1800378be  js      loc_1800377FE
0x1800378c4  mov     r9, [rsp+4D0h+var_480]; void *
0x1800378c9  mov     edx, 2; unsigned int
0x1800378ce  lea     r8d, [rdx+0Eh]; unsigned int
0x1800378d2  mov     rcx, r15; this
0x1800378d5  call    ?InternalSetWriteColumn@CSimpleDataTableCursor@@QEAAJKKPEAX@Z; CSimpleDataTableCursor::InternalSetWriteColumn(ulong,ulong,void *)
0x1800378da  mov     ebx, eax
0x1800378dc  test    eax, eax
0x1800378de  js      loc_1800377FE
0x1800378e4  lea     r9, [rsp+4D0h+var_490]; void *
0x1800378e9  mov     edx, 3; unsigned int
0x1800378ee  lea     r8d, [rdx+1]; unsigned int
0x1800378f2  mov     rcx, r15; this
0x1800378f5  call    ?InternalSetWriteColumn@CSimpleDataTableCursor@@QEAAJKKPEAX@Z; CSimpleDataTableCursor::InternalSetWriteColumn(ulong,ulong,void *)
0x1800378fa  mov     ebx, eax
0x1800378fc  test    eax, eax
0x1800378fe  js      loc_1800377FE
0x180037904  mov     rcx, r15; this
0x180037907  call    ?InternalSetRow@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InternalSetRow(void)
0x18003790c  mov     ebx, eax
0x18003790e  jmp     loc_1800377FE
0x180037913  test    ebx, ebx
0x180037915  js      short loc_18003792A
0x180037917  test    edi, edi
0x180037919  jz      short loc_18003792A
0x18003791b  jg      short loc_180037921
0x18003791d  mov     ebx, edi
0x18003791f  jmp     short loc_18003792A
0x180037921  movzx   ebx, di
0x180037924  or      ebx, 80070000h
0x18003792a  test    r14, r14
0x18003792d  jz      short loc_180037939
0x18003792f  mov     rcx, r14; pv
0x180037932  call    cs:__imp_CoTaskMemFree
0x180037938  nop
0x180037939  mov     rcx, [rsp+4D0h+lpsz]; pv
0x18003793e  test    rcx, rcx
0x180037941  jz      short loc_180037949
0x180037943  call    cs:__imp_CoTaskMemFree
0x180037949  mov     rcx, [rsp+4D0h+hKey]; hKey
0x18003794e  test    rcx, rcx
0x180037951  jz      short loc_180037959
0x180037953  call    cs:__imp_RegCloseKey
0x180037959  mov     eax, ebx
0x18003795b  jmp     short loc_180037962
0x18003795d  mov     eax, 80070057h
0x180037962  mov     rcx, [rbp+3D0h+var_50]
0x180037969  xor     rcx, rsp; StackCookie
0x18003796c  call    __security_check_cookie
0x180037971  add     rsp, 498h
0x180037978  pop     r15
0x18003797a  pop     r14
0x18003797c  pop     r13
0x18003797e  pop     r12
0x180037980  pop     rdi
0x180037981  pop     rsi
0x180037982  pop     rbx
0x180037983  pop     rbp
0x180037984  retn
```
