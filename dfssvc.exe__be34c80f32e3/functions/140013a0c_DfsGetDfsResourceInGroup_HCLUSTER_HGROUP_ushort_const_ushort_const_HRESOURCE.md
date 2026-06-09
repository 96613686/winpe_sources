# DfsGetDfsResourceInGroup(_HCLUSTER *,_HGROUP *,ushort const *,ushort const *,_HRESOURCE * *)

- ea: `0x140013a0c`
- end: `0x140013ce4`
- name: `?DfsGetDfsResourceInGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEBG2PEAPEAU_HRESOURCE@@@Z`
- size: `728`
- prototype: `unsigned int(struct _HCLUSTER *, struct _HGROUP *, const unsigned __int16 *, const unsigned __int16 *, struct _HRESOURCE **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013864`

## callees

- `0x140013a0c`
- `0x14005ce3a`
- `0x14005ce70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140013baf`
- `msvcrt!_wcsicmp` at `0x140013c00`
- `msvcrt!_wcsicmp` at `0x140013baf`
- `msvcrt!_wcsicmp` at `0x140013c00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140013c27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013cb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140013cb2`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x140013c74`
- `CLUSAPI!ClusterGroupCloseEnum` at `0x140013c74`
- `CLUSAPI!OpenClusterResource` at `0x140013b11`
- `CLUSAPI!OpenClusterResource` at `0x140013b11`
- `CLUSAPI!ClusterGroupEnum` at `0x140013aef`
- `CLUSAPI!ClusterGroupEnum` at `0x140013aef`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x140013a93`
- `CLUSAPI!ClusterGroupOpenEnum` at `0x140013a93`
- `CLUSAPI!ClusterRegCloseKey` at `0x140013c8a`
- `CLUSAPI!ClusterRegCloseKey` at `0x140013c9e`
- `CLUSAPI!ClusterRegCloseKey` at `0x140013c8a`
- `CLUSAPI!ClusterRegCloseKey` at `0x140013c9e`
- `CLUSAPI!ClusterRegOpenKey` at `0x140013b7b`
- `CLUSAPI!ClusterRegOpenKey` at `0x140013b7b`
- `CLUSAPI!GetClusterResourceKey` at `0x140013b51`
- `CLUSAPI!GetClusterResourceKey` at `0x140013b51`
- `CLUSAPI!GetClusterResourceNetworkName` at `0x140013be6`
- `CLUSAPI!GetClusterResourceNetworkName` at `0x140013be6`
- `CLUSAPI!CloseClusterResource` at `0x140013c13`
- `CLUSAPI!CloseClusterResource` at `0x140013c4f`
- `CLUSAPI!CloseClusterResource` at `0x140013c13`
- `CLUSAPI!CloseClusterResource` at `0x140013c4f`
- `RESUTILS!ResUtilGetSzValue` at `0x140013b95`
- `RESUTILS!ResUtilGetSzValue` at `0x140013b95`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x140013b33`
- `RESUTILS!ResUtilResourceTypesEqual` at `0x140013b33`

## string_xrefs

- `0x140013b8c`: `ShareName`

## pseudocode

```c
__int64 __fastcall DfsGetDfsResourceInGroup(
        struct _HCLUSTER *a1,
        struct _HGROUP *a2,
        wchar_t *a3,
        const unsigned __int16 *a4,
        struct _HRESOURCE **a5)
{
  DWORD LastError; // ebx
  struct _HGROUPENUM *v6; // rsi
  struct _HRESOURCE *v7; // rdi
  HKEY v8; // r14
  wchar_t *v9; // r15
  DWORD i; // r12d
  struct _HRESOURCE *v12; // rax
  HKEY ClusterResourceKey; // rax
  const wchar_t *SzValue; // rax
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-CCh] BYREF
  DWORD dwType; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h]
  HCLUSTER hCluster; // [rsp+50h] [rbp-B0h]
  struct _HRESOURCE **v22; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szResourceName[264]; // [rsp+270h] [rbp+170h] BYREF

  LastError = 0;
  hCluster = a1;
  phkResult = 0;
  String2 = a3;
  v6 = 0;
  v7 = 0;
  v22 = a5;
  v8 = 0;
  v9 = 0;
  if ( !a1 || !a2 || !a4 || !a5 )
  {
    LastError = 87;
LABEL_26:
    v7 = 0;
    goto LABEL_27;
  }
  v6 = ClusterGroupOpenEnum(a2, 1u);
  if ( v6 )
  {
    for ( i = 0; ; ++i )
    {
      v7 = 0;
      if ( LastError )
        break;
      dwType = 0;
      cchName = 260;
      LastError = ClusterGroupEnum(v6, i, &dwType, szResourceName, &cchName);
      if ( !LastError )
      {
        v12 = OpenClusterResource(hCluster, szResourceName);
        v7 = v12;
        if ( !v12 )
          goto LABEL_19;
        if ( ResUtilResourceTypesEqual(L"Distributed File System", v12) )
        {
          ClusterResourceKey = GetClusterResourceKey(v7, 0x20019u);
          v8 = ClusterResourceKey;
          if ( !ClusterResourceKey )
          {
LABEL_19:
            LastError = GetLastError();
            break;
          }
          LastError = ClusterRegOpenKey(ClusterResourceKey, L"Parameters", 0x20019u, &phkResult);
          SzValue = ResUtilGetSzValue(phkResult, L"ShareName");
          v9 = (wchar_t *)SzValue;
          if ( SzValue )
          {
            if ( !_wcsicmp(SzValue, a4) )
            {
              memset_0(Buffer, 0, 0x208u);
              nSize = 260;
              if ( GetClusterResourceNetworkName(v7, Buffer, &nSize) )
              {
                if ( !_wcsicmp(Buffer, String2) )
                  break;
              }
            }
          }
        }
        CloseClusterResource(v7);
      }
    }
    if ( LastError == 259 )
      LastError = 1168;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError )
  {
    if ( v7 )
      CloseClusterResource(v7);
    goto LABEL_26;
  }
LABEL_27:
  *v22 = v7;
  if ( v6 )
    ClusterGroupCloseEnum(v6);
  if ( phkResult )
    ClusterRegCloseKey(phkResult);
  if ( v8 )
    ClusterRegCloseKey(v8);
  if ( v9 )
    LocalFree(v9);
  return LastError;
}

```

## disassembly

```asm
0x140013a0c  push    rbp
0x140013a0e  push    rbx
0x140013a0f  push    rsi
0x140013a10  push    rdi
0x140013a11  push    r12
0x140013a13  push    r13
0x140013a15  push    r14
0x140013a17  push    r15
0x140013a19  lea     rbp, [rsp-398h]
0x140013a21  sub     rsp, 498h
0x140013a28  mov     rax, cs:__security_cookie
0x140013a2f  xor     rax, rsp
0x140013a32  mov     [rbp+3D0h+var_50], rax
0x140013a39  xor     ebx, ebx
0x140013a3b  mov     [rsp+4D0h+hCluster], rcx
0x140013a40  and     [rsp+4D0h+phkResult], rbx
0x140013a45  mov     rax, rdx
0x140013a48  mov     rdx, rcx
0x140013a4b  mov     [rsp+4D0h+String2], r8
0x140013a50  mov     rcx, [rbp+3D0h+arg_20]
0x140013a57  xor     esi, esi
0x140013a59  xor     edi, edi
0x140013a5b  mov     [rsp+4D0h+var_478], rcx
0x140013a60  xor     r14d, r14d
0x140013a63  xor     r15d, r15d
0x140013a66  mov     r13, r9
0x140013a69  test    rdx, rdx
0x140013a6c  jz      loc_140013C5D
0x140013a72  test    rax, rax
0x140013a75  jz      loc_140013C5D
0x140013a7b  test    r9, r9
0x140013a7e  jz      loc_140013C5D
0x140013a84  test    rcx, rcx
0x140013a87  jz      loc_140013C5D
0x140013a8d  lea     edx, [rbx+1]; dwType
0x140013a90  mov     rcx, rax; hGroup
0x140013a93  call    cs:__imp_ClusterGroupOpenEnum
0x140013a9a  nop     dword ptr [rax+rax+00h]
0x140013a9f  mov     rsi, rax
0x140013aa2  test    rax, rax
0x140013aa5  jnz     short loc_140013ABA
0x140013aa7  call    cs:__imp_GetLastError
0x140013aae  nop     dword ptr [rax+rax+00h]
0x140013ab3  mov     ebx, eax
0x140013ab5  jmp     loc_140013C43
0x140013aba  xor     r12d, r12d
0x140013abd  xor     edi, edi
0x140013abf  test    ebx, ebx
0x140013ac1  jnz     loc_140013C35
0x140013ac7  and     [rsp+4D0h+dwType], edi
0x140013acb  lea     rax, [rsp+4D0h+cchName]
0x140013ad0  lea     r9, [rbp+3D0h+szResourceName]; lpszResourceName
0x140013ad7  mov     [rsp+4D0h+lpcchName], rax; lpcchName
0x140013adc  lea     r8, [rsp+4D0h+dwType]; lpdwType
0x140013ae1  mov     [rsp+4D0h+cchName], 104h
0x140013ae9  mov     edx, r12d; dwIndex
0x140013aec  mov     rcx, rsi; hGroupEnum
0x140013aef  call    cs:__imp_ClusterGroupEnum
0x140013af6  nop     dword ptr [rax+rax+00h]
0x140013afb  mov     ebx, eax
0x140013afd  test    eax, eax
0x140013aff  jnz     loc_140013C1F
0x140013b05  mov     rcx, [rsp+4D0h+hCluster]; hCluster
0x140013b0a  lea     rdx, [rbp+3D0h+szResourceName]; lpszResourceName
0x140013b11  call    cs:__imp_OpenClusterResource
0x140013b18  nop     dword ptr [rax+rax+00h]
0x140013b1d  mov     rdi, rax
0x140013b20  test    rax, rax
0x140013b23  jz      loc_140013C27
0x140013b29  mov     rdx, rax; hResource
0x140013b2c  lea     rcx, szResTypeName; "Distributed File System"
0x140013b33  call    cs:__imp_ResUtilResourceTypesEqual
0x140013b3a  nop     dword ptr [rax+rax+00h]
0x140013b3f  test    eax, eax
0x140013b41  jz      loc_140013C10
0x140013b47  mov     ebx, 20019h
0x140013b4c  mov     rcx, rdi; hResource
0x140013b4f  mov     edx, ebx; samDesired
0x140013b51  call    cs:__imp_GetClusterResourceKey
0x140013b58  nop     dword ptr [rax+rax+00h]
0x140013b5d  mov     r14, rax
0x140013b60  test    rax, rax
0x140013b63  jz      loc_140013C27
0x140013b69  lea     r9, [rsp+4D0h+phkResult]; phkResult
0x140013b6e  mov     r8d, ebx; samDesired
0x140013b71  lea     rdx, szSubKey; "Parameters"
0x140013b78  mov     rcx, rax; hKey
0x140013b7b  call    cs:__imp_ClusterRegOpenKey
0x140013b82  nop     dword ptr [rax+rax+00h]
0x140013b87  mov     rcx, [rsp+4D0h+phkResult]; hkeyClusterKey
0x140013b8c  lea     rdx, pszValueName; "ShareName"
0x140013b93  mov     ebx, eax
0x140013b95  call    cs:__imp_ResUtilGetSzValue
0x140013b9c  nop     dword ptr [rax+rax+00h]
0x140013ba1  mov     r15, rax
0x140013ba4  test    rax, rax
0x140013ba7  jz      short loc_140013C10
0x140013ba9  mov     rdx, r13; String2
0x140013bac  mov     rcx, rax; String1
0x140013baf  call    cs:__imp__wcsicmp
0x140013bb6  nop     dword ptr [rax+rax+00h]
0x140013bbb  test    eax, eax
0x140013bbd  jnz     short loc_140013C10
0x140013bbf  xor     edx, edx; Val
0x140013bc1  lea     rcx, [rsp+4D0h+Buffer]; void *
0x140013bc6  mov     r8d, 208h; Size
0x140013bcc  call    memset_0
0x140013bd1  lea     r8, [rsp+4D0h+nSize]; nSize
0x140013bd6  mov     [rsp+4D0h+nSize], 104h
0x140013bde  lea     rdx, [rsp+4D0h+Buffer]; lpBuffer
0x140013be3  mov     rcx, rdi; hResource
0x140013be6  call    cs:__imp_GetClusterResourceNetworkName
0x140013bed  nop     dword ptr [rax+rax+00h]
0x140013bf2  test    eax, eax
0x140013bf4  jz      short loc_140013C10
0x140013bf6  mov     rdx, [rsp+4D0h+String2]; String2
0x140013bfb  lea     rcx, [rsp+4D0h+Buffer]; String1
0x140013c00  call    cs:__imp__wcsicmp
0x140013c07  nop     dword ptr [rax+rax+00h]
0x140013c0c  test    eax, eax
0x140013c0e  jz      short loc_140013C35
0x140013c10  mov     rcx, rdi; hResource
0x140013c13  call    cs:__imp_CloseClusterResource
0x140013c1a  nop     dword ptr [rax+rax+00h]
0x140013c1f  inc     r12d
0x140013c22  jmp     loc_140013ABD
0x140013c27  call    cs:__imp_GetLastError
0x140013c2e  nop     dword ptr [rax+rax+00h]
0x140013c33  mov     ebx, eax
0x140013c35  cmp     ebx, 103h
0x140013c3b  mov     eax, 490h
0x140013c40  cmovz   ebx, eax
0x140013c43  test    ebx, ebx
0x140013c45  jz      short loc_140013C64
0x140013c47  test    rdi, rdi
0x140013c4a  jz      short loc_140013C62
0x140013c4c  mov     rcx, rdi; hResource
0x140013c4f  call    cs:__imp_CloseClusterResource
0x140013c56  nop     dword ptr [rax+rax+00h]
0x140013c5b  jmp     short loc_140013C62
0x140013c5d  mov     ebx, 57h ; 'W'
0x140013c62  xor     edi, edi
0x140013c64  mov     rax, [rsp+4D0h+var_478]
0x140013c69  mov     [rax], rdi
0x140013c6c  test    rsi, rsi
0x140013c6f  jz      short loc_140013C80
0x140013c71  mov     rcx, rsi; hGroupEnum
0x140013c74  call    cs:__imp_ClusterGroupCloseEnum
0x140013c7b  nop     dword ptr [rax+rax+00h]
0x140013c80  mov     rcx, [rsp+4D0h+phkResult]; hKey
0x140013c85  test    rcx, rcx
0x140013c88  jz      short loc_140013C96
0x140013c8a  call    cs:__imp_ClusterRegCloseKey
0x140013c91  nop     dword ptr [rax+rax+00h]
0x140013c96  test    r14, r14
0x140013c99  jz      short loc_140013CAA
0x140013c9b  mov     rcx, r14; hKey
0x140013c9e  call    cs:__imp_ClusterRegCloseKey
0x140013ca5  nop     dword ptr [rax+rax+00h]
0x140013caa  test    r15, r15
0x140013cad  jz      short loc_140013CBE
0x140013caf  mov     rcx, r15; hMem
0x140013cb2  call    cs:__imp_LocalFree
0x140013cb9  nop     dword ptr [rax+rax+00h]
0x140013cbe  mov     eax, ebx
0x140013cc0  mov     rcx, [rbp+3D0h+var_50]
0x140013cc7  xor     rcx, rsp; StackCookie
0x140013cca  call    __security_check_cookie
0x140013ccf  add     rsp, 498h
0x140013cd6  pop     r15
0x140013cd8  pop     r14
0x140013cda  pop     r13
0x140013cdc  pop     r12
0x140013cde  pop     rdi
0x140013cdf  pop     rsi
0x140013ce0  pop     rbx
0x140013ce1  pop     rbp
0x140013ce2  retn
```
