# AppendSpecificPropertyPages(tagCAUUID *,ulong,_GUID *,ushort *,HKEY__ *)

- ea: `0x18003238c`
- end: `0x180032646`
- name: `?AppendSpecificPropertyPages@@YAXPEAUtagCAUUID@@KPEAU_GUID@@PEAGPEAUHKEY__@@@Z`
- size: `698`
- prototype: `void __fastcall(struct tagCAUUID *, int, struct _GUID *, unsigned __int16 *, HKEY hKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800229d0`
- `0x180038344`

## callees

- `0x18000909c`
- `0x18001f620`
- `0x18003238c`
- `0x180044850`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800324f4`
- `ADVAPI32!RegQueryValueExW` at `0x1800324f4`
- `ADVAPI32!RegCloseKey` at `0x1800325fa`
- `ADVAPI32!RegCloseKey` at `0x180032618`
- `ADVAPI32!RegCloseKey` at `0x1800325fa`
- `ADVAPI32!RegCloseKey` at `0x180032618`
- `ADVAPI32!RegOpenKeyExW` at `0x1800323ec`
- `ADVAPI32!RegOpenKeyExW` at `0x180032480`
- `ADVAPI32!RegOpenKeyExW` at `0x1800323ec`
- `ADVAPI32!RegOpenKeyExW` at `0x180032480`
- `ADVAPI32!RegEnumKeyW` at `0x1800324af`
- `ADVAPI32!RegEnumKeyW` at `0x1800325dc`
- `ADVAPI32!RegEnumKeyW` at `0x1800324af`
- `ADVAPI32!RegEnumKeyW` at `0x1800325dc`
- `ole32!CoTaskMemAlloc` at `0x180032568`
- `ole32!CoTaskMemAlloc` at `0x180032568`
- `ole32!StringFromGUID2` at `0x18003242c`
- `ole32!StringFromGUID2` at `0x18003242c`
- `ole32!CoTaskMemFree` at `0x180032598`
- `ole32!CoTaskMemFree` at `0x180032598`
- `ole32!IIDFromString` at `0x18003250e`
- `ole32!IIDFromString` at `0x18003250e`

## pseudocode

```c
void __fastcall AppendSpecificPropertyPages(
        struct tagCAUUID *a1,
        int a2,
        struct _GUID *a3,
        unsigned __int16 *a4,
        HKEY hKey)
{
  HKEY v9; // rcx
  DWORD v10; // r14d
  unsigned int cElems; // r8d
  unsigned int v12; // ecx
  _GUID *pElems; // rdx
  __int64 v14; // rax
  unsigned int v15; // ecx
  _GUID *v16; // rax
  _GUID *v17; // rdi
  __int64 v18; // rax
  _GUID v19; // xmm0
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v21; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  GUID Data; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Name[40]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[256]; // [rsp+100h] [rbp+0h] BYREF

  phkResult = 0;
  if ( RegOpenKeyExW(hKey, L"PageAliases", 0, 0x20019u, &phkResult) )
  {
    v9 = 0;
    phkResult = 0;
  }
  else
  {
    v9 = phkResult;
  }
  if ( a2 )
  {
    do
    {
      StringFromGUID2(&a3[--a2], sz, 39);
      v21 = 0;
      StringCchPrintfW(SubKey, 0x100u, L"%s\\%s\\PropertyPages", a4, sz);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v21) )
      {
        v10 = 0;
        for ( Data = 0; !RegEnumKeyW(v21, v10, Name, 0x28u); Data = 0 )
        {
          if ( !phkResult || (cbData = 16, RegQueryValueExW(phkResult, Name, 0, 0, (LPBYTE)&Data, &cbData)) )
            IIDFromString(Name, &Data);
          cElems = a1->cElems;
          v12 = a1->cElems;
          pElems = a1->pElems;
          if ( a1->cElems )
          {
            while ( 1 )
            {
              v14 = *(_QWORD *)&Data.Data1 - *(_QWORD *)&pElems->Data1;
              if ( *(_QWORD *)&Data.Data1 == *(_QWORD *)&pElems->Data1 )
                v14 = *(_QWORD *)Data.Data4 - *(_QWORD *)pElems->Data4;
              if ( !v14 )
                break;
              ++pElems;
              if ( !--v12 )
                goto LABEL_15;
            }
          }
          else
          {
LABEL_15:
            v15 = cElems + 1;
            if ( cElems + 1 < cElems )
              break;
            if ( 16 * (unsigned __int64)v15 > 0xFFFFFFFF )
              break;
            v16 = (_GUID *)CoTaskMemAlloc(16 * v15);
            v17 = v16;
            if ( !v16 )
              break;
            if ( a1->cElems )
            {
              memcpy_0(v16, a1->pElems, 16LL * a1->cElems);
              CoTaskMemFree(a1->pElems);
            }
            v18 = a1->cElems;
            v19 = Data;
            a1->pElems = v17;
            v17[v18] = v19;
            ++a1->cElems;
          }
          ++v10;
        }
        RegCloseKey(v21);
      }
    }
    while ( a2 );
    v9 = phkResult;
  }
  if ( v9 )
    RegCloseKey(v9);
}

```

## disassembly

```asm
0x18003238c  push    rbp
0x18003238e  push    rbx
0x18003238f  push    rsi
0x180032390  push    rdi
0x180032391  push    r12
0x180032393  push    r14
0x180032395  push    r15
0x180032397  lea     rbp, [rsp-210h]
0x18003239f  sub     rsp, 310h
0x1800323a6  mov     rax, cs:__security_cookie
0x1800323ad  xor     rax, rsp
0x1800323b0  mov     [rbp+240h+var_40], rax
0x1800323b7  mov     r12, r9
0x1800323ba  mov     [rsp+340h+var_310], 0
0x1800323c3  mov     r15, r8
0x1800323c6  lea     rax, [rsp+340h+var_310]
0x1800323cb  mov     esi, edx
0x1800323cd  mov     [rsp+340h+phkResult], rax; phkResult
0x1800323d2  mov     rbx, rcx
0x1800323d5  lea     rdx, aPagealiases; "PageAliases"
0x1800323dc  mov     rcx, [rbp+240h+hKey]; hKey
0x1800323e3  mov     r9d, 20019h; samDesired
0x1800323e9  xor     r8d, r8d; ulOptions
0x1800323ec  call    cs:__imp_RegOpenKeyExW
0x1800323f3  nop     dword ptr [rax+rax+00h]
0x1800323f8  test    eax, eax
0x1800323fa  jz      short loc_180032405
0x1800323fc  xor     ecx, ecx
0x1800323fe  mov     [rsp+340h+var_310], rcx
0x180032403  jmp     short loc_18003240A
0x180032405  mov     rcx, [rsp+340h+var_310]
0x18003240a  test    esi, esi
0x18003240c  jz      loc_180032613
0x180032412  mov     edi, 0FFFFFFFFh
0x180032417  add     esi, edi
0x180032419  lea     rdx, [rbp+240h+sz]; lpsz
0x18003241d  mov     ecx, esi
0x18003241f  mov     r8d, 27h ; '''; cchMax
0x180032425  shl     rcx, 4
0x180032429  add     rcx, r15; rguid
0x18003242c  call    cs:__imp_StringFromGUID2
0x180032433  nop     dword ptr [rax+rax+00h]
0x180032438  lea     rax, [rbp+240h+sz]
0x18003243c  mov     [rsp+340h+var_308], 0
0x180032445  mov     r9, r12
0x180032448  mov     [rsp+340h+phkResult], rax
0x18003244d  lea     r8, aSSPropertypage; "%s\\%s\\PropertyPages"
0x180032454  mov     edx, 100h; unsigned __int64
0x180032459  lea     rcx, [rbp+240h+SubKey]; unsigned __int16 *
0x18003245d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032462  lea     rax, [rsp+340h+var_308]
0x180032467  mov     r9d, 20019h; samDesired
0x18003246d  xor     r8d, r8d; ulOptions
0x180032470  mov     [rsp+340h+phkResult], rax; phkResult
0x180032475  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x180032479  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032480  call    cs:__imp_RegOpenKeyExW
0x180032487  nop     dword ptr [rax+rax+00h]
0x18003248c  test    eax, eax
0x18003248e  jnz     loc_180032606
0x180032494  mov     rcx, [rsp+340h+var_308]; hKey
0x180032499  lea     r9d, [rax+28h]; cchName
0x18003249d  xorps   xmm0, xmm0
0x1800324a0  lea     r8, [rsp+340h+Name]; lpName
0x1800324a5  xor     edx, edx; dwIndex
0x1800324a7  xor     r14d, r14d
0x1800324aa  movups  xmmword ptr [rsp+340h+Data.Data1], xmm0
0x1800324af  call    cs:__imp_RegEnumKeyW
0x1800324b6  nop     dword ptr [rax+rax+00h]
0x1800324bb  test    eax, eax
0x1800324bd  jnz     loc_1800325F5
0x1800324c3  mov     rcx, [rsp+340h+var_310]; hKey
0x1800324c8  test    rcx, rcx
0x1800324cb  jz      short loc_180032504
0x1800324cd  lea     rax, [rsp+340h+cbData]
0x1800324d2  mov     [rsp+340h+cbData], 10h
0x1800324da  mov     [rsp+340h+lpcbData], rax; lpcbData
0x1800324df  lea     rdx, [rsp+340h+Name]; lpValueName
0x1800324e4  lea     rax, [rsp+340h+Data]
0x1800324e9  xor     r9d, r9d; lpType
0x1800324ec  xor     r8d, r8d; lpReserved
0x1800324ef  mov     [rsp+340h+phkResult], rax; lpData
0x1800324f4  call    cs:__imp_RegQueryValueExW
0x1800324fb  nop     dword ptr [rax+rax+00h]
0x180032500  test    eax, eax
0x180032502  jz      short loc_18003251A
0x180032504  lea     rdx, [rsp+340h+Data]; lpiid
0x180032509  lea     rcx, [rsp+340h+Name]; lpsz
0x18003250e  call    cs:__imp_IIDFromString
0x180032515  nop     dword ptr [rax+rax+00h]
0x18003251a  mov     r8d, [rbx]
0x18003251d  mov     ecx, r8d
0x180032520  mov     rdx, [rbx+8]
0x180032524  test    r8d, r8d
0x180032527  jz      short loc_180032549
0x180032529  mov     rax, qword ptr [rsp+340h+Data.Data1]
0x18003252e  sub     rax, [rdx]
0x180032531  jnz     short loc_18003253C
0x180032533  mov     rax, qword ptr [rsp+340h+Data.Data4]
0x180032538  sub     rax, [rdx+8]
0x18003253c  test    rax, rax
0x18003253f  jz      short loc_1800325BE
0x180032541  add     rdx, 10h
0x180032545  add     ecx, edi
0x180032547  jnz     short loc_180032529
0x180032549  lea     ecx, [r8+1]
0x18003254d  cmp     ecx, r8d
0x180032550  jb      loc_1800325F0
0x180032556  mov     eax, ecx
0x180032558  shl     rax, 4
0x18003255c  cmp     rax, rdi
0x18003255f  ja      loc_1800325F0
0x180032565  shl     ecx, 4; cb
0x180032568  call    cs:__imp_CoTaskMemAlloc
0x18003256f  nop     dword ptr [rax+rax+00h]
0x180032574  mov     rdi, rax
0x180032577  test    rax, rax
0x18003257a  jz      short loc_1800325F0
0x18003257c  cmp     dword ptr [rbx], 0
0x18003257f  jz      short loc_1800325A4
0x180032581  mov     r8d, [rbx]
0x180032584  mov     rcx, rax; void *
0x180032587  mov     rdx, [rbx+8]; Src
0x18003258b  shl     r8, 4; Size
0x18003258f  call    memcpy_0
0x180032594  mov     rcx, [rbx+8]; pv
0x180032598  call    cs:__imp_CoTaskMemFree
0x18003259f  nop     dword ptr [rax+rax+00h]
0x1800325a4  mov     eax, [rbx]
0x1800325a6  movups  xmm0, xmmword ptr [rsp+340h+Data.Data1]
0x1800325ab  add     rax, rax
0x1800325ae  mov     [rbx+8], rdi
0x1800325b2  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x1800325b7  inc     dword ptr [rbx]
0x1800325b9  mov     edi, 0FFFFFFFFh
0x1800325be  mov     rcx, [rsp+340h+var_308]; hKey
0x1800325c3  lea     r8, [rsp+340h+Name]; lpName
0x1800325c8  xorps   xmm0, xmm0
0x1800325cb  inc     r14d
0x1800325ce  mov     edx, r14d; dwIndex
0x1800325d1  mov     r9d, 28h ; '('; cchName
0x1800325d7  movups  xmmword ptr [rsp+340h+Data.Data1], xmm0
0x1800325dc  call    cs:__imp_RegEnumKeyW
0x1800325e3  nop     dword ptr [rax+rax+00h]
0x1800325e8  test    eax, eax
0x1800325ea  jz      loc_1800324C3
0x1800325f0  mov     edi, 0FFFFFFFFh
0x1800325f5  mov     rcx, [rsp+340h+var_308]; hKey
0x1800325fa  call    cs:__imp_RegCloseKey
0x180032601  nop     dword ptr [rax+rax+00h]
0x180032606  test    esi, esi
0x180032608  jnz     loc_180032417
0x18003260e  mov     rcx, [rsp+340h+var_310]; hKey
0x180032613  test    rcx, rcx
0x180032616  jz      short loc_180032624
0x180032618  call    cs:__imp_RegCloseKey
0x18003261f  nop     dword ptr [rax+rax+00h]
0x180032624  mov     rcx, [rbp+240h+var_40]
0x18003262b  xor     rcx, rsp; StackCookie
0x18003262e  call    __security_check_cookie
0x180032633  add     rsp, 310h
0x18003263a  pop     r15
0x18003263c  pop     r14
0x18003263e  pop     r12
0x180032640  pop     rdi
0x180032641  pop     rsi
0x180032642  pop     rbx
0x180032643  pop     rbp
0x180032644  retn
```
