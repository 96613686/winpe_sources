# DfsCreateRequiredDfsKeys(void)

- ea: `0x140018304`
- end: `0x1400185f4`
- name: `?DfsCreateRequiredDfsKeys@@YAKXZ`
- size: `752`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018e88`

## callees

- `0x140005a94`
- `0x140018304`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001835f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400183ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400183ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001848c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018519`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001835f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400183ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400183ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001848c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140018519`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400184a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001852f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001858d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400184a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001852f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001858d`

## pseudocode

```c
__int64 DfsCreateRequiredDfsKeys(void)
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  unsigned int v2; // eax
  unsigned int *v3; // r10
  HKEY v5; // [rsp+90h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+48h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+50h] BYREF

  hKey = 0;
  v5 = 0;
  phkResult = 0;
  v0 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Dfs", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &hKey, 0);
  if ( v0 )
    goto LABEL_24;
  v0 = RegCreateKeyExW(hKey, L"Roots", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &phkResult, 0);
  RegCloseKey(hKey);
  if ( v0 )
    goto LABEL_24;
  v1 = RegCreateKeyExW(phkResult, L"Standalone", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &v5, 0);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 42, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v1);
    }
  }
  else
  {
    RegCloseKey(v5);
  }
  v2 = RegCreateKeyExW(phkResult, L"Domain", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &v5, 0);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x820) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_D(*((_QWORD *)pWppControl + 2), 43, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v2);
    }
  }
  else
  {
    RegCloseKey(v5);
  }
  v0 = RegCreateKeyExW(phkResult, L"domainV2", 0, (LPWSTR)&Class, 0, 0x2001Fu, 0, &v5, 0);
  if ( !v0 )
  {
    RegCloseKey(v5);
LABEL_24:
    v3 = pWppControl;
    goto LABEL_25;
  }
  v3 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x820) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 44, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v0);
    goto LABEL_24;
  }
LABEL_25:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    v3 = pWppControl;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v3
    && (((1 << (v0 != 0 ? 11 : 31)) | 0x20) & v3[7]) != 0
    && *((_BYTE *)v3 + 25) >= 3u )
  {
    WPP_SF_D(*((_QWORD *)v3 + 2), 45, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x140018304  mov     r11, rsp
0x140018307  push    rbp
0x140018308  push    rbx
0x140018309  push    rsi
0x14001830a  push    rdi
0x14001830b  push    r12
0x14001830d  push    r13
0x14001830f  push    r15
0x140018311  mov     rbp, rsp
0x140018314  sub     rsp, 50h
0x140018318  xor     esi, esi
0x14001831a  lea     rax, [rbp+hKey]
0x14001831e  mov     [r11-48h], rsi
0x140018322  lea     r13, Class
0x140018329  mov     [r11-50h], rax
0x14001832d  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Dfs"
0x140018334  mov     [r11-58h], rsi
0x140018338  mov     r12d, 2001Fh
0x14001833e  mov     [r11-60h], r12d
0x140018342  mov     r9, r13; lpClass
0x140018345  xor     r8d, r8d; Reserved
0x140018348  mov     [rsp+50h+dwOptions], esi; dwOptions
0x14001834c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140018353  mov     [rbp+hKey], rsi
0x140018357  mov     [rbp+arg_0], rsi
0x14001835b  mov     [rbp+arg_8], rsi
0x14001835f  call    cs:__imp_RegCreateKeyExW
0x140018366  nop     dword ptr [rax+rax+00h]
0x14001836b  lea     r15, WPP_GLOBAL_Control
0x140018372  mov     ebx, eax
0x140018374  lea     edi, [rsi+20h]
0x140018377  test    eax, eax
0x140018379  jnz     loc_14001857D
0x14001837f  mov     rcx, [rbp+hKey]; hKey
0x140018383  lea     rax, [rbp+arg_8]
0x140018387  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x14001838c  lea     rdx, aRoots; "Roots"
0x140018393  mov     [rsp+50h+phkResult], rax; phkResult
0x140018398  mov     r9, r13; lpClass
0x14001839b  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400183a0  xor     r8d, r8d; Reserved
0x1400183a3  mov     [rsp+50h+samDesired], r12d; samDesired
0x1400183a8  mov     [rsp+50h+dwOptions], esi; dwOptions
0x1400183ac  call    cs:__imp_RegCreateKeyExW
0x1400183b3  nop     dword ptr [rax+rax+00h]
0x1400183b8  mov     rcx, [rbp+hKey]; hKey
0x1400183bc  mov     ebx, eax
0x1400183be  call    cs:__imp_RegCloseKey
0x1400183c5  nop     dword ptr [rax+rax+00h]
0x1400183ca  test    ebx, ebx
0x1400183cc  jnz     loc_14001857D
0x1400183d2  mov     rcx, [rbp+arg_8]; hKey
0x1400183d6  lea     rax, [rbp+arg_0]
0x1400183da  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x1400183df  lea     rdx, aStandalone; "Standalone"
0x1400183e6  mov     [rsp+50h+phkResult], rax; phkResult
0x1400183eb  mov     r9, r13; lpClass
0x1400183ee  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1400183f3  xor     r8d, r8d; Reserved
0x1400183f6  mov     [rsp+50h+samDesired], r12d; samDesired
0x1400183fb  mov     [rsp+50h+dwOptions], esi; dwOptions
0x1400183ff  call    cs:__imp_RegCreateKeyExW
0x140018406  nop     dword ptr [rax+rax+00h]
0x14001840b  mov     r9d, eax
0x14001840e  test    eax, eax
0x140018410  jnz     short loc_140018424
0x140018412  mov     rcx, [rbp+arg_0]; hKey
0x140018416  call    cs:__imp_RegCloseKey
0x14001841d  nop     dword ptr [rax+rax+00h]
0x140018422  jmp     short loc_14001845F
0x140018424  cmp     cs:WPP_GLOBAL_Control, r15
0x14001842b  jz      short loc_14001845F
0x14001842d  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140018434  test    rcx, rcx
0x140018437  jz      short loc_14001845F
0x140018439  mov     eax, edi
0x14001843b  bts     eax, 0Bh
0x14001843f  test    [rcx+1Ch], eax
0x140018442  jz      short loc_14001845F
0x140018444  cmp     byte ptr [rcx+19h], 3
0x140018448  jb      short loc_14001845F
0x14001844a  mov     rcx, [rcx+10h]
0x14001844e  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x140018455  mov     edx, 2Ah ; '*'
0x14001845a  call    WPP_SF_D
0x14001845f  mov     rcx, [rbp+arg_8]; hKey
0x140018463  lea     rax, [rbp+arg_0]
0x140018467  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x14001846c  lea     rdx, aDomain_0; "Domain"
0x140018473  mov     [rsp+50h+phkResult], rax; phkResult
0x140018478  mov     r9, r13; lpClass
0x14001847b  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x140018480  xor     r8d, r8d; Reserved
0x140018483  mov     [rsp+50h+samDesired], r12d; samDesired
0x140018488  mov     [rsp+50h+dwOptions], esi; dwOptions
0x14001848c  call    cs:__imp_RegCreateKeyExW
0x140018493  nop     dword ptr [rax+rax+00h]
0x140018498  mov     r9d, eax
0x14001849b  test    eax, eax
0x14001849d  jnz     short loc_1400184B1
0x14001849f  mov     rcx, [rbp+arg_0]; hKey
0x1400184a3  call    cs:__imp_RegCloseKey
0x1400184aa  nop     dword ptr [rax+rax+00h]
0x1400184af  jmp     short loc_1400184EC
0x1400184b1  cmp     cs:WPP_GLOBAL_Control, r15
0x1400184b8  jz      short loc_1400184EC
0x1400184ba  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400184c1  test    rcx, rcx
0x1400184c4  jz      short loc_1400184EC
0x1400184c6  mov     eax, edi
0x1400184c8  bts     eax, 0Bh
0x1400184cc  test    [rcx+1Ch], eax
0x1400184cf  jz      short loc_1400184EC
0x1400184d1  cmp     byte ptr [rcx+19h], 3
0x1400184d5  jb      short loc_1400184EC
0x1400184d7  mov     rcx, [rcx+10h]
0x1400184db  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x1400184e2  mov     edx, 2Bh ; '+'
0x1400184e7  call    WPP_SF_D
0x1400184ec  mov     rcx, [rbp+arg_8]; hKey
0x1400184f0  lea     rax, [rbp+arg_0]
0x1400184f4  mov     [rsp+50h+lpdwDisposition], rsi; lpdwDisposition
0x1400184f9  lea     rdx, aDomainv2; "domainV2"
0x140018500  mov     [rsp+50h+phkResult], rax; phkResult
0x140018505  mov     r9, r13; lpClass
0x140018508  mov     [rsp+50h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x14001850d  xor     r8d, r8d; Reserved
0x140018510  mov     [rsp+50h+samDesired], r12d; samDesired
0x140018515  mov     [rsp+50h+dwOptions], esi; dwOptions
0x140018519  call    cs:__imp_RegCreateKeyExW
0x140018520  nop     dword ptr [rax+rax+00h]
0x140018525  mov     ebx, eax
0x140018527  test    eax, eax
0x140018529  jnz     short loc_14001853D
0x14001852b  mov     rcx, [rbp+arg_0]; hKey
0x14001852f  call    cs:__imp_RegCloseKey
0x140018536  nop     dword ptr [rax+rax+00h]
0x14001853b  jmp     short loc_14001857D
0x14001853d  cmp     cs:WPP_GLOBAL_Control, r15
0x140018544  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14001854b  jz      short loc_140018584
0x14001854d  test    r10, r10
0x140018550  jz      short loc_140018584
0x140018552  mov     eax, edi
0x140018554  bts     eax, 0Bh
0x140018558  test    [r10+1Ch], eax
0x14001855c  jz      short loc_140018584
0x14001855e  cmp     byte ptr [r10+19h], 3
0x140018563  jb      short loc_140018584
0x140018565  mov     rcx, [r10+10h]
0x140018569  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x140018570  mov     edx, 2Ch ; ','
0x140018575  mov     r9d, ebx
0x140018578  call    WPP_SF_D
0x14001857d  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140018584  mov     rcx, [rbp+arg_8]; hKey
0x140018588  test    rcx, rcx
0x14001858b  jz      short loc_1400185A0
0x14001858d  call    cs:__imp_RegCloseKey
0x140018594  nop     dword ptr [rax+rax+00h]
0x140018599  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400185a0  cmp     cs:WPP_GLOBAL_Control, r15
0x1400185a7  jz      short loc_1400185E2
0x1400185a9  test    r10, r10
0x1400185ac  jz      short loc_1400185E2
0x1400185ae  mov     eax, ebx
0x1400185b0  neg     eax
0x1400185b2  sbb     ecx, ecx
0x1400185b4  and     ecx, 0FFFFFFECh
0x1400185b7  add     ecx, 1Fh
0x1400185ba  bts     edi, ecx
0x1400185bd  test    [r10+1Ch], edi
0x1400185c1  jz      short loc_1400185E2
0x1400185c3  cmp     byte ptr [r10+19h], 3
0x1400185c8  jb      short loc_1400185E2
0x1400185ca  mov     rcx, [r10+10h]
0x1400185ce  lea     r8, WPP_213e589ab7fb3f879ce2d29ab64c13d3_Traceguids
0x1400185d5  mov     edx, 2Dh ; '-'
0x1400185da  mov     r9d, ebx
0x1400185dd  call    WPP_SF_D
0x1400185e2  mov     eax, ebx
0x1400185e4  add     rsp, 50h
0x1400185e8  pop     r15
0x1400185ea  pop     r13
0x1400185ec  pop     r12
0x1400185ee  pop     rdi
0x1400185ef  pop     rsi
0x1400185f0  pop     rbx
0x1400185f1  pop     rbp
0x1400185f2  retn
```
