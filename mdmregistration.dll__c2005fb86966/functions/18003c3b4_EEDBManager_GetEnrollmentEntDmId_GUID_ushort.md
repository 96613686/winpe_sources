# EEDBManager::GetEnrollmentEntDmId(_GUID,ushort * *)

- ea: `0x18003c3b4`
- end: `0x18003c6cc`
- name: `?GetEnrollmentEntDmId@EEDBManager@@SAJU_GUID@@PEAPEAG@Z`
- size: `792`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x1800031a0`
- `0x18003c3b4`
- `0x18003cfb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c598`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c598`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c633`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003c633`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c581`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c61f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c581`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c61f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c484`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c484`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c4a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c4a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c55b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c604`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c55b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003c604`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c4ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003c4ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c519`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c65f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c67c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c692`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c419`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c495`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c519`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c5cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c649`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c65f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c67c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c692`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c45f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c45f`

## pseudocode

```c
__int64 __fastcall EEDBManager::GetEnrollmentEntDmId(
        struct _GUID *a1,
        unsigned __int16 **a2,
        const unsigned __int16 *a3)
{
  int v4; // eax
  HKEY v5; // rcx
  signed int v6; // ebx
  HKEY v8; // rdi
  HKEY v9; // r14
  HKEY v10; // rsi
  DWORD LastError; // ebx
  LSTATUS v12; // eax
  HKEY v13; // rcx
  LSTATUS ValueW; // eax
  DWORD v15; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbx
  LSTATUS v19; // eax
  signed int v20; // edi
  HANDLE v21; // rax
  HKEY v22; // rcx
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName[3]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY phkResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v28; // [rsp+70h] [rbp-90h]
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  *(struct _GUID *)phkResult = *a1;
  hKey = 0;
  v4 = EEDBManager::OpenEnrollmentKey((struct _GUID *)phkResult, (unsigned int)a2, a3, &hKey);
  v5 = hKey;
  v6 = v4;
  if ( v4 < 0 )
  {
LABEL_2:
    if ( v5 )
      RegCloseKey(v5);
    return (unsigned int)v6;
  }
  hkey = 0;
  phkResult[0] = (HKEY)&hkey;
  phkResult[1] = 0;
  v28 = 1;
  RegOpenKeyExW(hKey, L"DMClient", 0, 0x20019u, &phkResult[1]);
  if ( v28 )
  {
    v8 = phkResult[0];
    v9 = phkResult[1];
    v10 = *(HKEY *)phkResult[0];
    if ( *(_QWORD *)phkResult[0] )
    {
      LastError = GetLastError();
      RegCloseKey(v10);
      SetLastError(LastError);
    }
    *(_QWORD *)v8 = v9;
  }
  memset_0(Name, 0, 0x208u);
  cchName[0] = 260;
  v12 = RegEnumKeyExW(hkey, 0, Name, cchName, 0, 0, 0, 0);
  v6 = v12;
  if ( v12 > 0 )
    v6 = (unsigned __int16)v12 | 0x80070000;
  v13 = hkey;
  if ( v6 < 0 )
  {
LABEL_12:
    if ( v13 )
      RegCloseKey(v13);
    v5 = hKey;
    goto LABEL_2;
  }
  pcbData = 0;
  ValueW = RegGetValueW(hkey, Name, L"EntDMID", 2u, 0, 0, &pcbData);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( v6 < 0 )
  {
    v13 = hkey;
    goto LABEL_12;
  }
  v15 = pcbData;
  ProcessHeap = GetProcessHeap();
  v17 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v15);
  v18 = v17;
  if ( v17 )
  {
    v19 = RegGetValueW(hkey, Name, L"EntDMID", 2u, 0, v17, &pcbData);
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 >= 0 )
    {
      v22 = hkey;
      *a2 = v18;
      if ( v22 )
        RegCloseKey(v22);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    else
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v18);
      if ( hkey )
        RegCloseKey(hkey);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v20;
    }
  }
  else
  {
    if ( hkey )
      RegCloseKey(hkey);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003c3b4  mov     [rsp-8+arg_10], rbx
0x18003c3b9  mov     [rsp-8+arg_18], rsi
0x18003c3be  push    rbp
0x18003c3bf  push    rdi
0x18003c3c0  push    r12
0x18003c3c2  push    r14
0x18003c3c4  push    r15
0x18003c3c6  lea     rbp, [rsp-1A0h]
0x18003c3ce  sub     rsp, 2A0h
0x18003c3d5  mov     rax, cs:__security_cookie
0x18003c3dc  xor     rax, rsp
0x18003c3df  mov     [rbp+1C0h+var_30], rax
0x18003c3e6  movaps  xmm0, xmmword ptr [rcx]
0x18003c3e9  lea     r9, [rsp+2C0h+hKey]; HKEY *
0x18003c3ee  xor     r12d, r12d
0x18003c3f1  movdqa  xmmword ptr [rsp+2C0h+var_260], xmm0
0x18003c3f7  lea     rcx, [rsp+2C0h+var_260]; struct _GUID
0x18003c3fc  mov     [rsp+2C0h+hKey], r12
0x18003c401  mov     r15, rdx
0x18003c404  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x18003c409  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003c40e  mov     ebx, eax
0x18003c410  test    eax, eax
0x18003c412  jns     short loc_18003C42C
0x18003c414  test    rcx, rcx
0x18003c417  jz      short loc_18003C425
0x18003c419  call    cs:__imp_RegCloseKey
0x18003c420  nop     dword ptr [rax+rax+00h]
0x18003c425  mov     eax, ebx
0x18003c427  jmp     loc_18003C6A0
0x18003c42c  lea     rax, [rsp+2C0h+hkey]
0x18003c431  mov     [rsp+2C0h+hkey], r12
0x18003c436  mov     [rsp+2C0h+var_260], rax
0x18003c43b  lea     rdx, aDmclient; "DMClient"
0x18003c442  lea     rax, [rsp+2C0h+var_260+8]
0x18003c447  mov     [rsp+2C0h+var_260+8], r12
0x18003c44c  mov     r9d, 20019h; samDesired
0x18003c452  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18003c457  xor     r8d, r8d; ulOptions
0x18003c45a  mov     [rsp+2C0h+var_250], 1
0x18003c45f  call    cs:__imp_RegOpenKeyExW
0x18003c466  nop     dword ptr [rax+rax+00h]
0x18003c46b  cmp     [rsp+2C0h+var_250], r12b
0x18003c470  jz      short loc_18003C4B2
0x18003c472  mov     rdi, [rsp+2C0h+var_260]
0x18003c477  mov     r14, [rsp+2C0h+var_260+8]
0x18003c47c  mov     rsi, [rdi]
0x18003c47f  test    rsi, rsi
0x18003c482  jz      short loc_18003C4AF
0x18003c484  call    cs:__imp_GetLastError
0x18003c48b  nop     dword ptr [rax+rax+00h]
0x18003c490  mov     rcx, rsi; hKey
0x18003c493  mov     ebx, eax
0x18003c495  call    cs:__imp_RegCloseKey
0x18003c49c  nop     dword ptr [rax+rax+00h]
0x18003c4a1  mov     ecx, ebx; dwErrCode
0x18003c4a3  call    cs:__imp_SetLastError
0x18003c4aa  nop     dword ptr [rax+rax+00h]
0x18003c4af  mov     [rdi], r14
0x18003c4b2  xor     edx, edx; Val
0x18003c4b4  lea     rcx, [rbp+1C0h+Name]; void *
0x18003c4b8  mov     r8d, 208h; Size
0x18003c4be  call    memset_0
0x18003c4c3  mov     rcx, [rsp+2C0h+hkey]; hKey
0x18003c4c8  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x18003c4cd  mov     [rsp+2C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003c4d2  lea     r8, [rbp+1C0h+Name]; lpName
0x18003c4d6  mov     [rsp+2C0h+lpcchClass], r12; lpcchClass
0x18003c4db  xor     edx, edx; dwIndex
0x18003c4dd  mov     [rsp+2C0h+lpClass], r12; lpClass
0x18003c4e2  mov     [rsp+2C0h+phkResult], r12; lpReserved
0x18003c4e7  mov     [rsp+2C0h+cchName], 104h
0x18003c4ef  call    cs:__imp_RegEnumKeyExW
0x18003c4f6  nop     dword ptr [rax+rax+00h]
0x18003c4fb  mov     ebx, eax
0x18003c4fd  mov     esi, 80070000h
0x18003c502  test    eax, eax
0x18003c504  jle     short loc_18003C50B
0x18003c506  movzx   ebx, ax
0x18003c509  or      ebx, esi
0x18003c50b  mov     rcx, [rsp+2C0h+hkey]; hkey
0x18003c510  test    ebx, ebx
0x18003c512  jns     short loc_18003C52F
0x18003c514  test    rcx, rcx
0x18003c517  jz      short loc_18003C525
0x18003c519  call    cs:__imp_RegCloseKey
0x18003c520  nop     dword ptr [rax+rax+00h]
0x18003c525  mov     rcx, [rsp+2C0h+hKey]
0x18003c52a  jmp     loc_18003C414
0x18003c52f  lea     rax, [rsp+2C0h+pcbData]
0x18003c534  mov     [rsp+2C0h+pcbData], r12d
0x18003c539  mov     [rsp+2C0h+lpcchClass], rax; pcbData
0x18003c53e  lea     r8, aEntdmid; "EntDMID"
0x18003c545  mov     edi, 2
0x18003c54a  mov     [rsp+2C0h+lpClass], r12; pvData
0x18003c54f  mov     r9d, edi; dwFlags
0x18003c552  mov     [rsp+2C0h+phkResult], r12; pdwType
0x18003c557  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x18003c55b  call    cs:__imp_RegGetValueW
0x18003c562  nop     dword ptr [rax+rax+00h]
0x18003c567  mov     ebx, eax
0x18003c569  test    eax, eax
0x18003c56b  jle     short loc_18003C572
0x18003c56d  movzx   ebx, ax
0x18003c570  or      ebx, esi
0x18003c572  test    ebx, ebx
0x18003c574  jns     short loc_18003C57D
0x18003c576  mov     rcx, [rsp+2C0h+hkey]
0x18003c57b  jmp     short loc_18003C514
0x18003c57d  mov     ebx, [rsp+2C0h+pcbData]
0x18003c581  call    cs:__imp_GetProcessHeap
0x18003c588  nop     dword ptr [rax+rax+00h]
0x18003c58d  mov     r8d, ebx; dwBytes
0x18003c590  mov     edx, 8; dwFlags
0x18003c595  mov     rcx, rax; hHeap
0x18003c598  call    cs:__imp_HeapAlloc
0x18003c59f  nop     dword ptr [rax+rax+00h]
0x18003c5a4  mov     rcx, [rsp+2C0h+hkey]; hkey
0x18003c5a9  mov     rbx, rax
0x18003c5ac  test    rax, rax
0x18003c5af  jnz     short loc_18003C5E2
0x18003c5b1  test    rcx, rcx
0x18003c5b4  jz      short loc_18003C5C2
0x18003c5b6  call    cs:__imp_RegCloseKey
0x18003c5bd  nop     dword ptr [rax+rax+00h]
0x18003c5c2  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003c5c7  test    rcx, rcx
0x18003c5ca  jz      short loc_18003C5D8
0x18003c5cc  call    cs:__imp_RegCloseKey
0x18003c5d3  nop     dword ptr [rax+rax+00h]
0x18003c5d8  mov     eax, 8007000Eh
0x18003c5dd  jmp     loc_18003C6A0
0x18003c5e2  lea     rax, [rsp+2C0h+pcbData]
0x18003c5e7  mov     r9d, edi; dwFlags
0x18003c5ea  mov     [rsp+2C0h+lpcchClass], rax; pcbData
0x18003c5ef  lea     r8, aEntdmid; "EntDMID"
0x18003c5f6  mov     [rsp+2C0h+lpClass], rbx; pvData
0x18003c5fb  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x18003c5ff  mov     [rsp+2C0h+phkResult], r12; pdwType
0x18003c604  call    cs:__imp_RegGetValueW
0x18003c60b  nop     dword ptr [rax+rax+00h]
0x18003c610  mov     edi, eax
0x18003c612  test    eax, eax
0x18003c614  jle     short loc_18003C61B
0x18003c616  movzx   edi, ax
0x18003c619  or      edi, esi
0x18003c61b  test    edi, edi
0x18003c61d  jns     short loc_18003C66F
0x18003c61f  call    cs:__imp_GetProcessHeap
0x18003c626  nop     dword ptr [rax+rax+00h]
0x18003c62b  mov     r8, rbx; lpMem
0x18003c62e  xor     edx, edx; dwFlags
0x18003c630  mov     rcx, rax; hHeap
0x18003c633  call    cs:__imp_HeapFree
0x18003c63a  nop     dword ptr [rax+rax+00h]
0x18003c63f  mov     rcx, [rsp+2C0h+hkey]; hKey
0x18003c644  test    rcx, rcx
0x18003c647  jz      short loc_18003C655
0x18003c649  call    cs:__imp_RegCloseKey
0x18003c650  nop     dword ptr [rax+rax+00h]
0x18003c655  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003c65a  test    rcx, rcx
0x18003c65d  jz      short loc_18003C66B
0x18003c65f  call    cs:__imp_RegCloseKey
0x18003c666  nop     dword ptr [rax+rax+00h]
0x18003c66b  mov     eax, edi
0x18003c66d  jmp     short loc_18003C6A0
0x18003c66f  mov     rcx, [rsp+2C0h+hkey]; hKey
0x18003c674  mov     [r15], rbx
0x18003c677  test    rcx, rcx
0x18003c67a  jz      short loc_18003C688
0x18003c67c  call    cs:__imp_RegCloseKey
0x18003c683  nop     dword ptr [rax+rax+00h]
0x18003c688  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003c68d  test    rcx, rcx
0x18003c690  jz      short loc_18003C69E
0x18003c692  call    cs:__imp_RegCloseKey
0x18003c699  nop     dword ptr [rax+rax+00h]
0x18003c69e  xor     eax, eax
0x18003c6a0  mov     rcx, [rbp+1C0h+var_30]
0x18003c6a7  xor     rcx, rsp; StackCookie
0x18003c6aa  call    __security_check_cookie
0x18003c6af  lea     r11, [rsp+2C0h+var_20]
0x18003c6b7  mov     rbx, [r11+40h]
0x18003c6bb  mov     rsi, [r11+48h]
0x18003c6bf  mov     rsp, r11
0x18003c6c2  pop     r15
0x18003c6c4  pop     r14
0x18003c6c6  pop     r12
0x18003c6c8  pop     rdi
0x18003c6c9  pop     rbp
0x18003c6ca  retn
```
