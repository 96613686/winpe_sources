# I_CertReadBINARYValueFromRegistry

- ea: `0x180001708`
- end: `0x18000181d`
- name: `I_CertReadBINARYValueFromRegistry`
- size: `277`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, BYTE **, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800015a4`

## callees

- `0x180001708`
- `0x1800042e0`
- `0x1800068b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000173f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000173f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001787`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800017d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001787`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800017d9`

## pseudocode

```c
__int64 __fastcall I_CertReadBINARYValueFromRegistry(HKEY hKey, __int64 a2, BYTE **a3, _DWORD *a4)
{
  unsigned int v4; // esi
  unsigned int v8; // edi
  BYTE *lpData; // rbx
  DWORD v10; // ecx
  int v11; // eax
  __int64 result; // rax
  LSTATUS v13; // eax
  __int64 lpcbData; // [rsp+78h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF
  DWORD Type; // [rsp+88h] [rbp+58h] BYREF

  lpcbData = a2;
  v4 = 0;
  v8 = 1;
  while ( 1 )
  {
    lpData = 0;
    LODWORD(lpcbData) = 0;
    if ( v4 > 5 )
    {
      v10 = -2147418113;
      goto LABEL_4;
    }
    Type = 0;
    cbData = 0;
    v13 = RegQueryValueExW(hKey, L"HpkpEncodedCtl", 0, &Type, 0, &cbData);
    if ( v13 )
    {
      v10 = v13;
      goto LABEL_4;
    }
    if ( Type != 3 || !cbData )
      break;
    if ( cbData > 0xFFFFFF )
    {
      v10 = 534;
      goto LABEL_4;
    }
    lpData = (BYTE *)PkiNonzeroAlloc(cbData);
    if ( !lpData )
      goto LABEL_5;
    LODWORD(lpcbData) = cbData;
    if ( !RegQueryValueExW(hKey, L"HpkpEncodedCtl", 0, &Type, lpData, (LPDWORD)&lpcbData) )
    {
      v11 = lpcbData;
      if ( (unsigned int)lpcbData <= cbData )
      {
        if ( (_DWORD)lpcbData )
          goto LABEL_6;
      }
    }
    PkiFree(lpData);
    ++v4;
  }
  v10 = 13;
LABEL_4:
  SetLastError(v10);
LABEL_5:
  v11 = lpcbData;
  v8 = 0;
LABEL_6:
  *a4 = v11;
  result = v8;
  *a3 = lpData;
  return result;
}

```

## disassembly

```asm
0x180001708  mov     [rsp-38h+arg_8], rdx
0x18000170d  push    rbp
0x18000170e  push    rbx
0x18000170f  push    rsi
0x180001710  push    rdi
0x180001711  push    r12
0x180001713  push    r14
0x180001715  push    r15
0x180001717  mov     rbp, rsp
0x18000171a  sub     rsp, 30h
0x18000171e  xor     esi, esi
0x180001720  mov     r15, r9
0x180001723  mov     r12, r8
0x180001726  mov     r14, rcx
0x180001729  lea     edi, [rsi+1]
0x18000172c  xor     ebx, ebx
0x18000172e  mov     dword ptr [rbp+arg_8], 0
0x180001735  cmp     esi, 5
0x180001738  jbe     short loc_180001762
0x18000173a  mov     ecx, 8000FFFFh; dwErrCode
0x18000173f  call    cs:__imp_SetLastError
0x180001745  mov     eax, dword ptr [rbp+arg_8]
0x180001748  xor     edi, edi
0x18000174a  mov     [r15], eax
0x18000174d  mov     eax, edi
0x18000174f  mov     [r12], rbx
0x180001753  add     rsp, 30h
0x180001757  pop     r15
0x180001759  pop     r14
0x18000175b  pop     r12
0x18000175d  pop     rdi
0x18000175e  pop     rsi
0x18000175f  pop     rbx
0x180001760  pop     rbp
0x180001761  retn
0x180001762  lea     rax, [rbp+cbData]
0x180001766  mov     [rbp+Type], ebx
0x180001769  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000176e  lea     r9, [rbp+Type]; lpType
0x180001772  xor     r8d, r8d; lpReserved
0x180001775  mov     [rsp+30h+lpData], rbx; lpData
0x18000177a  lea     rdx, ValueName; "HpkpEncodedCtl"
0x180001781  mov     [rbp+cbData], ebx
0x180001784  mov     rcx, r14; hKey
0x180001787  call    cs:__imp_RegQueryValueExW
0x18000178d  test    eax, eax
0x18000178f  jnz     short loc_180001802
0x180001791  cmp     [rbp+Type], 3
0x180001795  jnz     short loc_180001813
0x180001797  mov     eax, [rbp+cbData]
0x18000179a  test    eax, eax
0x18000179c  jz      short loc_180001813
0x18000179e  cmp     eax, 0FFFFFFh
0x1800017a3  ja      short loc_180001809
0x1800017a5  mov     ecx, eax; uBytes
0x1800017a7  call    PkiNonzeroAlloc
0x1800017ac  mov     rbx, rax
0x1800017af  test    rax, rax
0x1800017b2  jz      short loc_180001745
0x1800017b4  mov     ecx, [rbp+cbData]
0x1800017b7  lea     rax, [rbp+arg_8]
0x1800017bb  mov     dword ptr [rbp+arg_8], ecx
0x1800017be  lea     r9, [rbp+Type]; lpType
0x1800017c2  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800017c7  lea     rdx, ValueName; "HpkpEncodedCtl"
0x1800017ce  mov     rcx, r14; hKey
0x1800017d1  mov     [rsp+30h+lpData], rbx; lpData
0x1800017d6  xor     r8d, r8d; lpReserved
0x1800017d9  call    cs:__imp_RegQueryValueExW
0x1800017df  test    eax, eax
0x1800017e1  jnz     short loc_1800017F3
0x1800017e3  mov     eax, dword ptr [rbp+arg_8]
0x1800017e6  cmp     eax, [rbp+cbData]
0x1800017e9  ja      short loc_1800017F3
0x1800017eb  test    eax, eax
0x1800017ed  jnz     loc_18000174A
0x1800017f3  mov     rcx, rbx; hMem
0x1800017f6  call    PkiFree
0x1800017fb  add     esi, edi
0x1800017fd  jmp     loc_18000172C
0x180001802  mov     ecx, eax
0x180001804  jmp     loc_18000173F
0x180001809  mov     ecx, 216h
0x18000180e  jmp     loc_18000173F
0x180001813  mov     ecx, 0Dh
0x180001818  jmp     loc_18000173F
```
