# EnumSysCallback

- ea: `0x18002e830`
- end: `0x18002e9de`
- name: `EnumSysCallback`
- size: `430`
- prototype: `BOOL __stdcall(const void *pvSystemStore, DWORD dwFlags, PCERT_SYSTEM_STORE_INFO pStoreInfo, void *pvReserved, void *pvArg)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002e55c`
- `0x18002e830`
- `0x18003e582`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002e872`
- `msvcrt!_wcsicmp` at `0x18002e88a`
- `msvcrt!_wcsicmp` at `0x18002e872`
- `msvcrt!_wcsicmp` at `0x18002e88a`
- `CRYPT32!CertOpenStore` at `0x18002e8e3`
- `CRYPT32!CertOpenStore` at `0x18002e8e3`
- `CRYPT32!CertCloseStore` at `0x18002e90f`
- `CRYPT32!CertCloseStore` at `0x18002e90f`
- `CRYPT32!CryptFindLocalizedName` at `0x18002e922`
- `CRYPT32!CryptFindLocalizedName` at `0x18002e922`
- `CRYPT32!CertGetStoreProperty` at `0x18002e904`
- `CRYPT32!CertGetStoreProperty` at `0x18002e904`
- `USER32!SendMessageA` at `0x18002e9bf`
- `USER32!SendMessageA` at `0x18002e9bf`

## pseudocode

```c
__int64 __fastcall EnumSysCallback(
        WCHAR *pvSystemStore,
        DWORD dwFlags,
        PCERT_SYSTEM_STORE_INFO pStoreInfo,
        void *pvReserved,
        _QWORD *pvArg)
{
  HCERTSTORE v7; // rax
  void *v8; // rsi
  LPCWSTR LocalizedName; // rax
  WCHAR *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // rax
  HWND v15; // rcx
  int pvData; // [rsp+30h] [rbp-51h] BYREF
  DWORD pcbData[3]; // [rsp+34h] [rbp-4Dh] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-41h] BYREF
  int v20; // [rsp+50h] [rbp-31h]
  WCHAR *v21; // [rsp+68h] [rbp-19h]
  int v22; // [rsp+70h] [rbp-11h]
  __int64 v23; // [rsp+74h] [rbp-Dh]
  __int64 v24; // [rsp+80h] [rbp-1h]

  memset_0(lParam, 0, 0x60u);
  pcbData[0] = 4;
  pvData = 0;
  if ( _wcsicmp(pvSystemStore, L"acrs") )
  {
    if ( _wcsicmp(pvSystemStore, L"request") )
    {
      if ( (*(_BYTE *)(*pvArg + 16LL) & 8) == 0
        || (v7 = CertOpenStore(
                   (LPCSTR)0xA,
                   0x10001u,
                   0,
                   *((_DWORD *)pvArg + 6)
                 | dwFlags & 0xFFFF0002
                 | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*pvArg + 40LL) + 24LL) + 16LL * *((int *)pvArg + 11)) & 0x1000
                 | 2,
                   pvSystemStore),
            (v8 = v7) != 0)
        && (CertGetStoreProperty(v7, 0xEu, &pvData, pcbData), CertCloseStore(v8, 0), (pvData & 1) != 0) )
      {
        LocalizedName = CryptFindLocalizedName(pvSystemStore);
        v10 = pvSystemStore;
        v20 = 39;
        *(__m128i *)lParam = _mm_load_si128((const __m128i *)&_xmm_ffffffffffff0002ffffffffffff0000);
        if ( LocalizedName )
          v10 = (WCHAR *)LocalizedName;
        v21 = v10;
        if ( v10 )
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          v22 = v11;
        }
        else
        {
          v22 = 0;
        }
        v12 = *pvArg;
        v13 = *((int *)pvArg + 11);
        v23 = 0;
        v14 = AllocAndReturnOpenStoreStruct(
                0,
                0,
                dwFlags & 0xFFFF0000 | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 40) + 24LL) + 16 * v13) & 0x1000,
                10,
                pvSystemStore,
                v13);
        v15 = (HWND)pvArg[2];
        v24 = v14;
        pvArg[4] = SendMessageA(v15, 0x1132u, 0, (LPARAM)lParam);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002e830  push    rbp
0x18002e832  push    rbx
0x18002e833  push    rsi
0x18002e834  push    rdi
0x18002e835  push    r14
0x18002e837  push    r15
0x18002e839  lea     rbp, [rsp-27h]
0x18002e83e  sub     rsp, 0A8h
0x18002e845  mov     r14d, edx
0x18002e848  mov     rbx, rcx
0x18002e84b  xor     edx, edx; Val
0x18002e84d  lea     rcx, [rbp+4Fh+lParam]; void *
0x18002e851  lea     r8d, [rdx+60h]; Size
0x18002e855  call    memset_0
0x18002e85a  xor     r15d, r15d
0x18002e85d  mov     [rbp+4Fh+pcbData], 4
0x18002e864  lea     rdx, aAcrs; "acrs"
0x18002e86b  mov     [rbp+4Fh+pvData], r15d
0x18002e86f  mov     rcx, rbx; String1
0x18002e872  call    cs:__imp__wcsicmp
0x18002e878  test    eax, eax
0x18002e87a  jz      loc_18002E9C9
0x18002e880  lea     rdx, aRequest; "request"
0x18002e887  mov     rcx, rbx; String1
0x18002e88a  call    cs:__imp__wcsicmp
0x18002e890  test    eax, eax
0x18002e892  jz      loc_18002E9C9
0x18002e898  mov     rdi, [rbp+4Fh+pvArg]
0x18002e89c  mov     rax, [rdi]
0x18002e89f  test    byte ptr [rax+10h], 8
0x18002e8a3  jz      short loc_18002E91F
0x18002e8a5  mov     rax, [rax+28h]
0x18002e8a9  xor     r8d, r8d; hCryptProv
0x18002e8ac  movsxd  rdx, dword ptr [rdi+2Ch]
0x18002e8b0  add     rdx, rdx
0x18002e8b3  mov     [rsp+0D0h+pvPara], rbx; pvPara
0x18002e8b8  mov     rcx, [rax+18h]
0x18002e8bc  mov     eax, r14d
0x18002e8bf  and     eax, 0FFFF0002h
0x18002e8c4  mov     r9d, [rcx+rdx*8]
0x18002e8c8  mov     edx, 10001h; dwEncodingType
0x18002e8cd  and     r9d, 1000h
0x18002e8d4  lea     ecx, [r15+0Ah]; lpszStoreProvider
0x18002e8d8  or      r9d, eax
0x18002e8db  or      r9d, [rdi+18h]
0x18002e8df  or      r9d, 2; dwFlags
0x18002e8e3  call    cs:__imp_CertOpenStore
0x18002e8e9  mov     rsi, rax
0x18002e8ec  test    rax, rax
0x18002e8ef  jz      loc_18002E9C9
0x18002e8f5  lea     r9, [rbp+4Fh+pcbData]; pcbData
0x18002e8f9  mov     rcx, rax; hCertStore
0x18002e8fc  lea     r8, [rbp+4Fh+pvData]; pvData
0x18002e900  lea     edx, [r15+0Eh]; dwPropId
0x18002e904  call    cs:__imp_CertGetStoreProperty
0x18002e90a  xor     edx, edx; dwFlags
0x18002e90c  mov     rcx, rsi; hCertStore
0x18002e90f  call    cs:__imp_CertCloseStore
0x18002e915  test    byte ptr [rbp+4Fh+pvData], 1
0x18002e919  jz      loc_18002E9C9
0x18002e91f  mov     rcx, rbx; pwszCryptName
0x18002e922  call    cs:__imp_CryptFindLocalizedName
0x18002e928  movdqa  xmm0, cs:__xmm@ffffffffffff0002ffffffffffff0000
0x18002e930  mov     rcx, rbx
0x18002e933  test    rax, rax
0x18002e936  mov     [rbp+4Fh+var_80], 27h ; '''
0x18002e93d  movdqa  xmmword ptr [rbp+4Fh+lParam], xmm0
0x18002e942  cmovnz  rcx, rax
0x18002e946  mov     [rbp+4Fh+var_68], rcx
0x18002e94a  test    rcx, rcx
0x18002e94d  jz      short loc_18002E962
0x18002e94f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e953  inc     rax
0x18002e956  cmp     [rcx+rax*2], r15w
0x18002e95b  jnz     short loc_18002E953
0x18002e95d  mov     [rbp+4Fh+var_60], eax
0x18002e960  jmp     short loc_18002E966
0x18002e962  mov     [rbp+4Fh+var_60], r15d
0x18002e966  mov     rax, [rdi]
0x18002e969  and     r14d, 0FFFF0000h
0x18002e970  movsxd  r10, dword ptr [rdi+2Ch]
0x18002e974  mov     [rbp+4Fh+var_5C], r15
0x18002e978  mov     rdx, r10
0x18002e97b  add     rdx, rdx
0x18002e97e  mov     [rsp+0D0h+var_A8], r10d; int
0x18002e983  mov     rcx, [rax+28h]
0x18002e987  mov     [rsp+0D0h+pvPara], rbx; Src
0x18002e98c  mov     rax, [rcx+18h]
0x18002e990  xor     ecx, ecx; int
0x18002e992  mov     r8d, [rax+rdx*8]
0x18002e996  xor     edx, edx; int
0x18002e998  and     r8d, 1000h
0x18002e99f  or      r8d, r14d; int
0x18002e9a2  lea     r9d, [rdx+0Ah]; int
0x18002e9a6  call    AllocAndReturnOpenStoreStruct
0x18002e9ab  mov     rcx, [rdi+10h]; hWnd
0x18002e9af  lea     r9, [rbp+4Fh+lParam]; lParam
0x18002e9b3  xor     r8d, r8d; wParam
0x18002e9b6  mov     [rbp+4Fh+var_50], rax
0x18002e9ba  mov     edx, 1132h; Msg
0x18002e9bf  call    cs:__imp_SendMessageA
0x18002e9c5  mov     [rdi+20h], rax
0x18002e9c9  mov     eax, 1
0x18002e9ce  add     rsp, 0A8h
0x18002e9d5  pop     r15
0x18002e9d7  pop     r14
0x18002e9d9  pop     rdi
0x18002e9da  pop     rsi
0x18002e9db  pop     rbx
0x18002e9dc  pop     rbp
0x18002e9dd  retn
```
