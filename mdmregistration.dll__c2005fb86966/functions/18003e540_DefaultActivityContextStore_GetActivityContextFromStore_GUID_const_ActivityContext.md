# DefaultActivityContextStore::GetActivityContextFromStore(_GUID const &,ActivityContext * *)

- ea: `0x18003e540`
- end: `0x18003e9aa`
- name: `?GetActivityContextFromStore@DefaultActivityContextStore@@UEAAJAEBU_GUID@@PEAPEAVActivityContext@@@Z`
- size: `1130`
- prototype: `int(DefaultActivityContextStore *__hidden this, const struct _GUID *, struct ActivityContext **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800026d0`
- `0x180002710`
- `0x18000312a`
- `0x18000bd7c`
- `0x18003cd7c`
- `0x18003d170`
- `0x18003e540`
- `0x1800402c4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e925`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003e925`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e7c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e862`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e8ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e8f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e7c0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e862`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e8ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e8f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e950`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e950`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e5b1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003e5b1`

## string_xrefs

- `0x18003e8a1`: `AttemptCounter`
- `0x18003e8ec`: `Rollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DefaultActivityContextStore::GetActivityContextFromStore(
        DefaultActivityContextStore *this,
        const struct _GUID *a2,
        struct ActivityContext **a3)
{
  ActivityContext *v4; // rbx
  LSTATUS v5; // edi
  __int64 v6; // rcx
  OLECHAR *p_sz; // rax
  __int64 v8; // r12
  __int64 v9; // rax
  __int16 *v10; // rcx
  __int64 v11; // rdx
  _WORD *v12; // r9
  __int16 v13; // r8
  _WORD *v14; // rcx
  __int64 v15; // rdx
  _WORD *v16; // rax
  __int64 v17; // rcx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  __int64 v19; // r15
  HKEY v20; // r14
  ActivityContext *v21; // rax
  ActivityContext *v22; // rax
  ActivityContext *v23; // rsi
  struct _GUID *v24; // rax
  __int16 *v25; // rcx
  _WORD *v26; // rax
  __int16 v27; // dx
  _WORD *v28; // rcx
  int v30; // [rsp+40h] [rbp-C0h] BYREF
  int v31; // [rsp+44h] [rbp-BCh] BYREF
  int v32; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v34; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v35; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v36; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hkey; // [rsp+60h] [rbp-A0h] BYREF
  struct ActivityContext **v38; // [rsp+68h] [rbp-98h]
  _WORD v39[40]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+C0h] [rbp-40h] BYREF
  char v41; // [rsp+C2h] [rbp-3Eh] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE pvData[528]; // [rsp+320h] [rbp+220h] BYREF

  v38 = a3;
  hkey = 0;
  SubKey[0] = 0;
  v39[0] = 0;
  v4 = 0;
  sz = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    goto LABEL_50;
  }
  if ( StringFromGUID2(a2, &sz, 39) != 39 )
    goto LABEL_49;
  v6 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v6;
  }
  while ( v6 );
  if ( !v6 )
  {
    v5 = -2147024809;
    goto LABEL_50;
  }
  if ( (unsigned __int64)(37 - v6) > 0x24 )
    goto LABEL_49;
  v8 = 2147483646;
  v9 = 2147483646;
  v10 = (__int16 *)&v41;
  v11 = 39;
  v12 = v39;
  do
  {
    if ( !v9 )
      break;
    v13 = *v10;
    if ( !*v10 )
      break;
    ++v10;
    *v12++ = v13;
    --v9;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  if ( !v11 )
  {
    v5 = -2147024774;
    goto LABEL_50;
  }
  v15 = 39;
  v16 = v39;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v15;
  }
  while ( v15 );
  v5 = v15 == 0 ? 0x80070057 : 0;
  v17 = (39 - v15) & -(__int64)(v15 != 0);
  if ( !v15 )
    goto LABEL_50;
  if ( (unsigned __int64)(v17 - 2) > 0x24 )
  {
LABEL_49:
    v5 = -2147418113;
    goto LABEL_50;
  }
  v39[v17 - 1] = 0;
  EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
  v19 = 260;
  v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v39);
  if ( v5 >= 0 )
  {
    v5 = EEDBManager::OpenHKEY(SubKey, 131097, &hkey);
    if ( v5 >= 0 )
    {
      v20 = hkey;
      v21 = (ActivityContext *)operator new(0x3D8u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = 0;
      if ( v21 && (v22 = ActivityContext::ActivityContext(v21), (v23 = v22) != 0) )
      {
        (*(void (__fastcall **)(ActivityContext *))(*(_QWORD *)v22 + 8LL))(v22);
        v4 = v23;
        v24 = (struct _GUID *)((char *)v23 + 8);
        if ( v23 != (ActivityContext *)-8LL )
        {
          if ( a2 )
          {
            *v24 = *a2;
            pcbData = 520;
            if ( RegGetValueW(v20, 0, L"OrchestratorType", 2u, 0, pvData, &pcbData) )
              goto LABEL_36;
            v25 = (__int16 *)pvData;
            v26 = (_WORD *)((char *)v23 + 448);
            do
            {
              if ( !v8 )
                break;
              v27 = *v25;
              if ( !*v25 )
                break;
              ++v25;
              *v26++ = v27;
              --v8;
              --v19;
            }
            while ( v19 );
            v28 = v26 - 1;
            if ( v19 )
              v28 = v26;
            *v28 = 0;
            v5 = v19 == 0 ? 0x8007007A : 0;
            if ( v19 )
            {
LABEL_36:
              v30 = 0;
              v34 = 4;
              if ( !RegGetValueW(v20, 0, L"ActivityType", 0x10u, 0, &v30, &v34) )
              {
                *((_DWORD *)v23 + 8) = v30;
                v5 = 0;
              }
              v31 = 0;
              v35 = 4;
              if ( !RegGetValueW(v20, 0, L"AttemptCounter", 0x10u, 0, &v31, &v35) )
                *((_DWORD *)v23 + 242) = v31;
              v32 = 0;
              v36 = 4;
              if ( !RegGetValueW(v20, 0, L"Rollback", 0x10u, 0, &v32, &v36) )
                *((_DWORD *)v23 + 108) = v32;
              v4 = 0;
              *v38 = v23;
            }
            goto LABEL_46;
          }
          *v24 = 0;
        }
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
        v5 = -2147418113;
      }
      else
      {
        v5 = -2147024882;
      }
LABEL_46:
      if ( v20 )
        RegCloseKey(v20);
    }
  }
LABEL_50:
  if ( v4 )
    (*(void (__fastcall **)(ActivityContext *))(*(_QWORD *)v4 + 16LL))(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e540  mov     [rsp-8+arg_0], rbx
0x18003e545  push    rbp
0x18003e546  push    rsi
0x18003e547  push    rdi
0x18003e548  push    r12
0x18003e54a  push    r13
0x18003e54c  push    r14
0x18003e54e  push    r15
0x18003e550  lea     rbp, [rsp-440h]
0x18003e558  sub     rsp, 540h
0x18003e55f  mov     rax, cs:__security_cookie
0x18003e566  xor     rax, rsp
0x18003e569  mov     [rbp+470h+var_40], rax
0x18003e570  mov     [rsp+570h+var_508], r8
0x18003e575  mov     r13, rdx
0x18003e578  xor     r15d, r15d
0x18003e57b  mov     [rsp+570h+hkey], r15
0x18003e580  mov     [rbp+470h+SubKey], r15w
0x18003e585  mov     [rsp+570h+var_500], r15w
0x18003e58b  mov     ebx, r15d
0x18003e58e  mov     [rbp+470h+sz], r15w
0x18003e593  test    r8, r8
0x18003e596  jnz     short loc_18003E5A2
0x18003e598  mov     edi, 80070057h
0x18003e59d  jmp     loc_18003E968
0x18003e5a2  mov     esi, 27h ; '''
0x18003e5a7  mov     r8d, esi; cchMax
0x18003e5aa  lea     rdx, [rbp+470h+sz]; lpsz
0x18003e5ae  mov     rcx, r13; rguid
0x18003e5b1  call    cs:__imp_StringFromGUID2
0x18003e5b8  nop     dword ptr [rax+rax+00h]
0x18003e5bd  cmp     eax, esi
0x18003e5bf  jnz     loc_18003E963
0x18003e5c5  mov     ecx, esi
0x18003e5c7  lea     rax, [rbp+470h+sz]
0x18003e5cb  cmp     [rax], r15w
0x18003e5cf  jz      short loc_18003E5DB
0x18003e5d1  add     rax, 2
0x18003e5d5  sub     rcx, 1
0x18003e5d9  jnz     short loc_18003E5CB
0x18003e5db  mov     rax, rcx
0x18003e5de  neg     rax
0x18003e5e1  sbb     edx, edx
0x18003e5e3  not     edx
0x18003e5e5  mov     edi, 80070057h
0x18003e5ea  and     edx, edi
0x18003e5ec  test    rcx, rcx
0x18003e5ef  jnz     short loc_18003E5F8
0x18003e5f1  mov     edi, edx
0x18003e5f3  jmp     loc_18003E968
0x18003e5f8  mov     eax, 25h ; '%'
0x18003e5fd  sub     rax, rcx
0x18003e600  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18003e607  test    rcx, rcx
0x18003e60a  cmovz   rax, rdx
0x18003e60e  cmp     rax, 24h ; '$'
0x18003e612  ja      loc_18003E963
0x18003e618  mov     r12d, 7FFFFFFEh
0x18003e61e  mov     eax, r12d
0x18003e621  lea     rcx, [rbp+470h+var_4AE]
0x18003e625  mov     rdx, rsi
0x18003e628  lea     r9, [rsp+570h+var_500]
0x18003e62d  test    rax, rax
0x18003e630  jz      short loc_18003E651
0x18003e632  movzx   r8d, word ptr [rcx]
0x18003e636  test    r8w, r8w
0x18003e63a  jz      short loc_18003E651
0x18003e63c  add     rcx, 2
0x18003e640  mov     [r9], r8w
0x18003e644  add     r9, 2
0x18003e648  dec     rax
0x18003e64b  sub     rdx, 1
0x18003e64f  jnz     short loc_18003E62D
0x18003e651  mov     rax, rdx
0x18003e654  neg     rax
0x18003e657  sbb     r8d, r8d
0x18003e65a  not     r8d
0x18003e65d  and     r8d, 8007007Ah
0x18003e664  lea     rcx, [r9-2]
0x18003e668  test    rdx, rdx
0x18003e66b  cmovnz  rcx, r9
0x18003e66f  mov     [rcx], r15w
0x18003e673  jz      loc_18003E95E
0x18003e679  mov     rdx, rsi
0x18003e67c  lea     rax, [rsp+570h+var_500]
0x18003e681  cmp     [rax], r15w
0x18003e685  jz      short loc_18003E691
0x18003e687  add     rax, 2
0x18003e68b  sub     rdx, 1
0x18003e68f  jnz     short loc_18003E681
0x18003e691  mov     rax, rdx
0x18003e694  neg     rax
0x18003e697  sbb     ecx, ecx
0x18003e699  not     ecx
0x18003e69b  and     edi, ecx
0x18003e69d  mov     rax, rdx
0x18003e6a0  sub     rsi, rdx
0x18003e6a3  neg     rax
0x18003e6a6  sbb     rcx, rcx
0x18003e6a9  and     rcx, rsi
0x18003e6ac  test    rdx, rdx
0x18003e6af  jz      loc_18003E968
0x18003e6b5  lea     rax, [rcx-2]
0x18003e6b9  cmp     rax, 24h ; '$'
0x18003e6bd  ja      loc_18003E963
0x18003e6c3  mov     word ptr [rsp+rcx*2+570h+var_508+6], r15w
0x18003e6c9  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003e6ce  lea     rcx, [rsp+570h+var_500]
0x18003e6d3  mov     [rsp+570h+pvData], rcx
0x18003e6d8  lea     rcx, aContext_0; "Context"
0x18003e6df  mov     [rsp+570h+pdwType], rcx
0x18003e6e4  mov     r9, rax
0x18003e6e7  lea     r8, aSSS; "%s\\%s\\%s"
0x18003e6ee  mov     r15d, 104h
0x18003e6f4  mov     edx, r15d; unsigned __int64
0x18003e6f7  lea     rcx, [rbp+470h+SubKey]; unsigned __int16 *
0x18003e6fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003e700  mov     edi, eax
0x18003e702  test    eax, eax
0x18003e704  js      loc_18003E968
0x18003e70a  lea     r8, [rsp+570h+hkey]; HKEY *
0x18003e70f  mov     edx, 20019h; unsigned int
0x18003e714  lea     rcx, [rbp+470h+SubKey]; lpSubKey
0x18003e718  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x18003e71d  mov     edi, eax
0x18003e71f  test    eax, eax
0x18003e721  js      loc_18003E968
0x18003e727  mov     r14, [rsp+570h+hkey]
0x18003e72c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003e733  mov     ecx, 3D8h; unsigned __int64
0x18003e738  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003e73d  xor     edi, edi
0x18003e73f  test    rax, rax
0x18003e742  jz      loc_18003E943
0x18003e748  mov     rcx, rax; this
0x18003e74b  call    ??0ActivityContext@@QEAA@XZ; ActivityContext::ActivityContext(void)
0x18003e750  mov     rsi, rax
0x18003e753  test    rax, rax
0x18003e756  jz      loc_18003E943
0x18003e75c  mov     rcx, [rax]
0x18003e75f  mov     rax, [rcx+8]
0x18003e763  mov     rcx, rsi
0x18003e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e76b  mov     rbx, rsi
0x18003e76e  lea     rax, [rsi+8]
0x18003e772  test    rax, rax
0x18003e775  jz      loc_18003E925
0x18003e77b  test    r13, r13
0x18003e77e  jz      loc_18003E91F
0x18003e784  movups  xmm0, xmmword ptr [r13+0]
0x18003e789  movdqu  xmmword ptr [rax], xmm0
0x18003e78d  mov     [rsp+570h+var_524], 208h
0x18003e795  lea     rax, [rsp+570h+var_524]
0x18003e79a  mov     [rsp+570h+pcbData], rax; pcbData
0x18003e79f  lea     rax, [rbp+470h+var_250]
0x18003e7a6  mov     [rsp+570h+pvData], rax; pvData
0x18003e7ab  mov     [rsp+570h+pdwType], rdi; pdwType
0x18003e7b0  lea     r9d, [rdi+2]; dwFlags
0x18003e7b4  lea     r8, aOrchestratorty; "OrchestratorType"
0x18003e7bb  xor     edx, edx; lpSubKey
0x18003e7bd  mov     rcx, r14; hkey
0x18003e7c0  call    cs:__imp_RegGetValueW
0x18003e7c7  nop     dword ptr [rax+rax+00h]
0x18003e7cc  test    eax, eax
0x18003e7ce  jnz     short loc_18003E826
0x18003e7d0  lea     rcx, [rbp+470h+var_250]
0x18003e7d7  lea     rax, [rsi+1C0h]
0x18003e7de  test    r12, r12
0x18003e7e1  jz      short loc_18003E7FF
0x18003e7e3  movzx   edx, word ptr [rcx]
0x18003e7e6  test    dx, dx
0x18003e7e9  jz      short loc_18003E7FF
0x18003e7eb  add     rcx, 2
0x18003e7ef  mov     [rax], dx
0x18003e7f2  add     rax, 2
0x18003e7f6  dec     r12
0x18003e7f9  sub     r15, 1
0x18003e7fd  jnz     short loc_18003E7DE
0x18003e7ff  lea     rcx, [rax-2]
0x18003e803  test    r15, r15
0x18003e806  cmovnz  rcx, rax
0x18003e80a  mov     [rcx], di
0x18003e80d  mov     rax, r15
0x18003e810  neg     rax
0x18003e813  sbb     edi, edi
0x18003e815  not     edi
0x18003e817  and     edi, 8007007Ah
0x18003e81d  test    r15, r15
0x18003e820  jz      loc_18003E948
0x18003e826  xor     r15d, r15d
0x18003e829  mov     [rsp+570h+var_530], r15d
0x18003e82e  lea     ebx, [r15+4]
0x18003e832  mov     [rsp+570h+var_520], ebx
0x18003e836  lea     rax, [rsp+570h+var_520]
0x18003e83b  mov     [rsp+570h+pcbData], rax; pcbData
0x18003e840  lea     rax, [rsp+570h+var_530]
0x18003e845  mov     [rsp+570h+pvData], rax; pvData
0x18003e84a  mov     [rsp+570h+pdwType], r15; pdwType
0x18003e84f  lea     r12d, [r15+10h]
0x18003e853  mov     r9d, r12d; dwFlags
0x18003e856  lea     r8, aActivitytype; "ActivityType"
0x18003e85d  xor     edx, edx; lpSubKey
0x18003e85f  mov     rcx, r14; hkey
0x18003e862  call    cs:__imp_RegGetValueW
0x18003e869  nop     dword ptr [rax+rax+00h]
0x18003e86e  test    eax, eax
0x18003e870  jnz     short loc_18003E87C
0x18003e872  mov     eax, [rsp+570h+var_530]
0x18003e876  mov     [rsi+20h], eax
0x18003e879  mov     edi, r15d
0x18003e87c  mov     [rsp+570h+var_52C], r15d
0x18003e881  mov     [rsp+570h+var_51C], ebx
0x18003e885  lea     rax, [rsp+570h+var_51C]
0x18003e88a  mov     [rsp+570h+pcbData], rax; pcbData
0x18003e88f  lea     rax, [rsp+570h+var_52C]
0x18003e894  mov     [rsp+570h+pvData], rax; pvData
0x18003e899  mov     [rsp+570h+pdwType], r15; pdwType
0x18003e89e  mov     r9d, r12d; dwFlags
0x18003e8a1  lea     r8, aAttemptcounter; "AttemptCounter"
0x18003e8a8  xor     edx, edx; lpSubKey
0x18003e8aa  mov     rcx, r14; hkey
0x18003e8ad  call    cs:__imp_RegGetValueW
0x18003e8b4  nop     dword ptr [rax+rax+00h]
0x18003e8b9  test    eax, eax
0x18003e8bb  jnz     short loc_18003E8C7
0x18003e8bd  mov     eax, [rsp+570h+var_52C]
0x18003e8c1  mov     [rsi+3C8h], eax
0x18003e8c7  mov     [rsp+570h+var_528], r15d
0x18003e8cc  mov     [rsp+570h+var_518], ebx
0x18003e8d0  lea     rax, [rsp+570h+var_518]
0x18003e8d5  mov     [rsp+570h+pcbData], rax; pcbData
0x18003e8da  lea     rax, [rsp+570h+var_528]
0x18003e8df  mov     [rsp+570h+pvData], rax; pvData
0x18003e8e4  mov     [rsp+570h+pdwType], r15; pdwType
0x18003e8e9  mov     r9d, r12d; dwFlags
0x18003e8ec  lea     r8, aRollback; "Rollback"
0x18003e8f3  xor     edx, edx; lpSubKey
0x18003e8f5  mov     rcx, r14; hkey
0x18003e8f8  call    cs:__imp_RegGetValueW
0x18003e8ff  nop     dword ptr [rax+rax+00h]
0x18003e904  test    eax, eax
0x18003e906  jnz     short loc_18003E912
0x18003e908  mov     eax, [rsp+570h+var_528]
0x18003e90c  mov     [rsi+1B0h], eax
0x18003e912  mov     rbx, r15
0x18003e915  mov     rax, [rsp+570h+var_508]
0x18003e91a  mov     [rax], rsi
0x18003e91d  jmp     short loc_18003E948
0x18003e91f  xorps   xmm0, xmm0
0x18003e922  movups  xmmword ptr [rax], xmm0
0x18003e925  call    cs:__imp__o__errno
0x18003e92c  nop     dword ptr [rax+rax+00h]
0x18003e931  mov     dword ptr [rax], 16h
0x18003e937  call    _invalid_parameter_noinfo
0x18003e93c  mov     edi, 8000FFFFh
0x18003e941  jmp     short loc_18003E948
0x18003e943  mov     edi, 8007000Eh
0x18003e948  test    r14, r14
0x18003e94b  jz      short loc_18003E968
0x18003e94d  mov     rcx, r14; hKey
0x18003e950  call    cs:__imp_RegCloseKey
0x18003e957  nop     dword ptr [rax+rax+00h]
0x18003e95c  jmp     short loc_18003E968
0x18003e95e  mov     edi, r8d
0x18003e961  jmp     short loc_18003E968
0x18003e963  mov     edi, 8000FFFFh
0x18003e968  test    rbx, rbx
0x18003e96b  jz      short loc_18003E97D
0x18003e96d  mov     rax, [rbx]
0x18003e970  mov     rcx, rbx
0x18003e973  mov     rax, [rax+10h]
0x18003e977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e97c  nop
0x18003e97d  mov     eax, edi
0x18003e97f  mov     rcx, [rbp+470h+var_40]
0x18003e986  xor     rcx, rsp; StackCookie
0x18003e989  call    __security_check_cookie
0x18003e98e  mov     rbx, [rsp+570h+arg_0]
0x18003e996  add     rsp, 540h
0x18003e99d  pop     r15
0x18003e99f  pop     r14
0x18003e9a1  pop     r13
0x18003e9a3  pop     r12
0x18003e9a5  pop     rdi
0x18003e9a6  pop     rsi
0x18003e9a7  pop     rbp
0x18003e9a8  retn
```
