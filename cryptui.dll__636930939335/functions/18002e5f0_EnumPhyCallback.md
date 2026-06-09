# EnumPhyCallback

- ea: `0x18002e5f0`
- end: `0x18002e824`
- name: `EnumPhyCallback`
- size: `564`
- prototype: `BOOL __stdcall(const void *pvSystemStore, DWORD dwFlags, LPCWSTR pwszStoreName, PCERT_PHYSICAL_STORE_INFO pStoreInfo, void *pvReserved, void *pvArg)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c754`
- `0x18000df7c`
- `0x18002e55c`
- `0x18002e5f0`
- `0x18003e582`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e696`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e696`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e805`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e805`
- `CRYPT32!CertOpenStore` at `0x18002e722`
- `CRYPT32!CertOpenStore` at `0x18002e722`
- `CRYPT32!CertCloseStore` at `0x18002e74d`
- `CRYPT32!CertCloseStore` at `0x18002e74d`
- `CRYPT32!CryptFindLocalizedName` at `0x18002e760`
- `CRYPT32!CryptFindLocalizedName` at `0x18002e760`
- `CRYPT32!CertGetStoreProperty` at `0x18002e742`
- `CRYPT32!CertGetStoreProperty` at `0x18002e742`
- `USER32!SendMessageA` at `0x18002e7fc`
- `USER32!SendMessageA` at `0x18002e7fc`

## pseudocode

```c
__int64 __fastcall EnumPhyCallback(
        const unsigned __int16 *pvSystemStore,
        DWORD dwFlags,
        LPCWSTR pwszStoreName,
        PCERT_PHYSICAL_STORE_INFO pStoreInfo,
        void *pvReserved,
        LPARAM *pvArg)
{
  bool v10; // zf
  LPARAM *v11; // r14
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  __int64 result; // rax
  unsigned __int16 *pvPara; // rdi
  HCERTSTORE v17; // rax
  void *v18; // rsi
  const WCHAR *LocalizedName; // rax
  LPARAM v20; // rcx
  __int64 v21; // rax
  LPARAM v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  HWND v25; // rcx
  DWORD pcbData[4]; // [rsp+30h] [rbp-69h] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-59h] BYREF
  int v28; // [rsp+50h] [rbp-49h]
  LPCWSTR v29; // [rsp+68h] [rbp-31h]
  int v30; // [rsp+70h] [rbp-29h]
  __int64 v31; // [rsp+74h] [rbp-25h]
  __int64 v32; // [rsp+80h] [rbp-19h]
  int pvData; // [rsp+108h] [rbp+6Fh] BYREF

  memset_0(lParam, 0, 0x60u);
  pcbData[0] = 4;
  v10 = (pStoreInfo->dwFlags & 6) == 0;
  pvData = 0;
  if ( !v10 )
    return 1;
  v11 = pvArg;
  if ( (*(_BYTE *)(*pvArg + 16) & 4) != 0 && (pStoreInfo->dwOpenFlags & 0x8000) != 0 )
    return 1;
  v12 = -1;
  if ( pvSystemStore )
  {
    v13 = -1;
    do
      ++v13;
    while ( pvSystemStore[v13] );
  }
  else
  {
    LODWORD(v13) = 0;
  }
  if ( pwszStoreName )
  {
    do
      ++v12;
    while ( pwszStoreName[v12] );
  }
  else
  {
    LODWORD(v12) = 0;
  }
  v14 = (int)v13 + 2 + (int)v12;
  result = (__int64)LocalAlloc(0x40u, 2 * v14);
  pvPara = (unsigned __int16 *)result;
  if ( result )
  {
    StringCchCopyW((unsigned __int16 *)result, v14, pvSystemStore);
    StringCchCatW(pvPara, v14, L"\\");
    StringCchCatW(pvPara, v14, pwszStoreName);
    if ( (*(_BYTE *)(*v11 + 16) & 8) != 0 )
    {
      v17 = CertOpenStore(
              (LPCSTR)0xE,
              0x10001u,
              0,
              *((_DWORD *)v11 + 6)
            | dwFlags & 0xFFFF0002
            | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*v11 + 40) + 24LL) + 16LL * *((int *)v11 + 12)) & 0x1000
            | 2,
              pvPara);
      v18 = v17;
      if ( !v17 )
      {
LABEL_25:
        LocalFree(pvPara);
        return 1;
      }
      CertGetStoreProperty(v17, 0xEu, &pvData, pcbData);
      CertCloseStore(v18, 0);
      if ( (pvData & 1) == 0 )
        return 1;
    }
    LocalizedName = CryptFindLocalizedName(pwszStoreName);
    v20 = v11[4];
    v28 = 39;
    if ( LocalizedName )
      pwszStoreName = LocalizedName;
    lParam[0] = v20;
    lParam[1] = -65534;
    v29 = pwszStoreName;
    if ( pwszStoreName )
    {
      v21 = -1;
      do
        ++v21;
      while ( pwszStoreName[v21] );
      v30 = v21;
    }
    else
    {
      v30 = 0;
    }
    v22 = *v11;
    v23 = *((int *)v11 + 12);
    v31 = 0;
    v24 = AllocAndReturnOpenStoreStruct(
            0,
            0,
            dwFlags & 0xFFFF0000 | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 40) + 24LL) + 16 * v23) & 0x1000,
            14,
            pvPara,
            -1);
    v25 = (HWND)v11[2];
    v32 = v24;
    SendMessageA(v25, 0x1132u, 0, (LPARAM)lParam);
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x18002e5f0  push    rbp
0x18002e5f2  push    rbx
0x18002e5f3  push    rsi
0x18002e5f4  push    rdi
0x18002e5f5  push    r12
0x18002e5f7  push    r13
0x18002e5f9  push    r14
0x18002e5fb  push    r15
0x18002e5fd  lea     rbp, [rsp-0Fh]
0x18002e602  sub     rsp, 0A8h
0x18002e609  mov     r12d, edx
0x18002e60c  mov     rbx, r8
0x18002e60f  xor     edx, edx; Val
0x18002e611  mov     r15, rcx
0x18002e614  lea     rcx, [rbp+47h+lParam]; void *
0x18002e618  mov     rdi, r9
0x18002e61b  lea     r8d, [rdx+60h]; Size
0x18002e61f  call    memset_0
0x18002e624  xor     r13d, r13d
0x18002e627  mov     [rbp+47h+pcbData], 4
0x18002e62e  test    byte ptr [rdi+28h], 6
0x18002e632  mov     [rbp+47h+pvData], r13d
0x18002e636  jnz     loc_18002E80B
0x18002e63c  mov     r14, [rbp+47h+pvArg]
0x18002e640  mov     rax, [r14]
0x18002e643  test    byte ptr [rax+10h], 4
0x18002e647  jz      short loc_18002E656
0x18002e649  test    dword ptr [rdi+14h], 8000h
0x18002e650  jnz     loc_18002E80B
0x18002e656  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e65a  test    r15, r15
0x18002e65d  jz      short loc_18002E66E
0x18002e65f  mov     rcx, rax
0x18002e662  inc     rcx
0x18002e665  cmp     [r15+rcx*2], r13w
0x18002e66a  jnz     short loc_18002E662
0x18002e66c  jmp     short loc_18002E671
0x18002e66e  mov     ecx, r13d
0x18002e671  test    rbx, rbx
0x18002e674  jz      short loc_18002E682
0x18002e676  inc     rax
0x18002e679  cmp     [rbx+rax*2], r13w
0x18002e67e  jnz     short loc_18002E676
0x18002e680  jmp     short loc_18002E685
0x18002e682  mov     eax, r13d
0x18002e685  add     ecx, 2
0x18002e688  add     eax, ecx
0x18002e68a  mov     ecx, 40h ; '@'; uFlags
0x18002e68f  movsxd  rsi, eax
0x18002e692  lea     rdx, [rsi+rsi]; uBytes
0x18002e696  call    cs:__imp_LocalAlloc
0x18002e69c  mov     rdi, rax
0x18002e69f  test    rax, rax
0x18002e6a2  jz      loc_18002E810
0x18002e6a8  mov     r8, r15; unsigned __int16 *
0x18002e6ab  mov     rdx, rsi; unsigned __int64
0x18002e6ae  mov     rcx, rdi; unsigned __int16 *
0x18002e6b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e6b6  lea     r8, asc_180044C30; "\\"
0x18002e6bd  mov     rdx, rsi; unsigned __int64
0x18002e6c0  mov     rcx, rdi; unsigned __int16 *
0x18002e6c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e6c8  mov     r8, rbx; unsigned __int16 *
0x18002e6cb  mov     rdx, rsi; unsigned __int64
0x18002e6ce  mov     rcx, rdi; unsigned __int16 *
0x18002e6d1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002e6d6  mov     rax, [r14]
0x18002e6d9  mov     r15d, 0Eh
0x18002e6df  test    byte ptr [rax+10h], 8
0x18002e6e3  jz      short loc_18002E75D
0x18002e6e5  mov     rax, [rax+28h]
0x18002e6e9  xor     r8d, r8d; hCryptProv
0x18002e6ec  movsxd  rcx, dword ptr [r14+30h]
0x18002e6f0  mov     edx, 10001h; dwEncodingType
0x18002e6f5  add     rcx, rcx
0x18002e6f8  mov     [rsp+0E0h+pvPara], rdi; pvPara
0x18002e6fd  mov     rax, [rax+18h]
0x18002e701  mov     r9d, [rax+rcx*8]
0x18002e705  mov     eax, r12d
0x18002e708  and     r9d, 1000h
0x18002e70f  and     eax, 0FFFF0002h
0x18002e714  or      r9d, eax
0x18002e717  mov     ecx, r15d; lpszStoreProvider
0x18002e71a  or      r9d, [r14+18h]
0x18002e71e  or      r9d, 2; dwFlags
0x18002e722  call    cs:__imp_CertOpenStore
0x18002e728  mov     rsi, rax
0x18002e72b  test    rax, rax
0x18002e72e  jz      loc_18002E802
0x18002e734  lea     r9, [rbp+47h+pcbData]; pcbData
0x18002e738  mov     edx, r15d; dwPropId
0x18002e73b  lea     r8, [rbp+47h+pvData]; pvData
0x18002e73f  mov     rcx, rax; hCertStore
0x18002e742  call    cs:__imp_CertGetStoreProperty
0x18002e748  xor     edx, edx; dwFlags
0x18002e74a  mov     rcx, rsi; hCertStore
0x18002e74d  call    cs:__imp_CertCloseStore
0x18002e753  test    byte ptr [rbp+47h+pvData], 1
0x18002e757  jz      loc_18002E80B
0x18002e75d  mov     rcx, rbx; pwszCryptName
0x18002e760  call    cs:__imp_CryptFindLocalizedName
0x18002e766  mov     rcx, [r14+20h]
0x18002e76a  test    rax, rax
0x18002e76d  mov     [rbp+47h+var_90], 27h ; '''
0x18002e774  cmovnz  rbx, rax
0x18002e778  mov     [rbp+47h+lParam], rcx
0x18002e77c  mov     [rbp+47h+var_98], 0FFFFFFFFFFFF0002h
0x18002e784  mov     [rbp+47h+var_78], rbx
0x18002e788  test    rbx, rbx
0x18002e78b  jz      short loc_18002E7A0
0x18002e78d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e791  inc     rax
0x18002e794  cmp     [rbx+rax*2], r13w
0x18002e799  jnz     short loc_18002E791
0x18002e79b  mov     [rbp+47h+var_70], eax
0x18002e79e  jmp     short loc_18002E7A4
0x18002e7a0  mov     [rbp+47h+var_70], r13d
0x18002e7a4  mov     rax, [r14]
0x18002e7a7  and     r12d, 0FFFF0000h
0x18002e7ae  movsxd  rdx, dword ptr [r14+30h]
0x18002e7b2  mov     r9, r15; int
0x18002e7b5  mov     [rbp+47h+var_6C], r13
0x18002e7b9  add     rdx, rdx
0x18002e7bc  mov     [rsp+0E0h+var_B8], 0FFFFFFFFh; int
0x18002e7c4  mov     rcx, [rax+28h]
0x18002e7c8  mov     [rsp+0E0h+pvPara], rdi; Src
0x18002e7cd  mov     rax, [rcx+18h]
0x18002e7d1  xor     ecx, ecx; int
0x18002e7d3  mov     r8d, [rax+rdx*8]
0x18002e7d7  xor     edx, edx; int
0x18002e7d9  and     r8d, 1000h
0x18002e7e0  or      r8d, r12d; int
0x18002e7e3  call    AllocAndReturnOpenStoreStruct
0x18002e7e8  mov     rcx, [r14+10h]; hWnd
0x18002e7ec  lea     r9, [rbp+47h+lParam]; lParam
0x18002e7f0  xor     r8d, r8d; wParam
0x18002e7f3  mov     [rbp+47h+var_60], rax
0x18002e7f7  mov     edx, 1132h; Msg
0x18002e7fc  call    cs:__imp_SendMessageA
0x18002e802  mov     rcx, rdi; hMem
0x18002e805  call    cs:__imp_LocalFree
0x18002e80b  mov     eax, 1
0x18002e810  add     rsp, 0A8h
0x18002e817  pop     r15
0x18002e819  pop     r14
0x18002e81b  pop     r13
0x18002e81d  pop     r12
0x18002e81f  pop     rdi
0x18002e820  pop     rsi
0x18002e821  pop     rbx
0x18002e822  pop     rbp
0x18002e823  retn
```
