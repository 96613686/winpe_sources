# InitNonRedistConfig(void)

- ea: `0x18004de58`
- end: `0x18004e080`
- name: `?InitNonRedistConfig@@YAJXZ`
- size: `552`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004aa88`

## callees

- `0x18004de58`
- `0x1800502bc`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004deb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004deb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e02b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e02b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004dfb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004dfb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004defc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004defc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e059`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e067`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004df20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004df74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dff6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004df20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004df74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dff6`

## pseudocode

```c
__int64 InitNonRedistConfig(void)
{
  unsigned int v0; // ebx
  unsigned __int16 *v1; // r14
  DWORD v2; // r12d
  void *v3; // rax
  signed __int64 v4; // rdi
  unsigned __int64 v5; // rcx
  DWORD v6; // esi
  unsigned int v7; // r15d
  unsigned __int16 *v8; // rax
  _QWORD *v9; // rax
  DWORD i; // esi
  void *v11; // rcx
  DWORD cValues; // [rsp+B0h] [rbp+48h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+B8h] [rbp+50h] BYREF
  DWORD cchValueName; // [rsp+C0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+60h] BYREF

  v0 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  hKey = 0;
  if ( g_arrConfigNonRedistFiles )
    return v0;
  v1 = 0;
  v2 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Ole\\NonRedist", 0, 1u, &hKey)
    || RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0) )
  {
    v9 = CoTaskMemAlloc(8u);
    v4 = (signed __int64)v9;
    if ( v9 )
    {
      v2 = 1;
      *v9 = 0;
LABEL_17:
      v4 &= -(__int64)(_InterlockedCompareExchange64((volatile signed __int64 *)&g_arrConfigNonRedistFiles, v4, 0) != 0);
      goto LABEL_18;
    }
  }
  else
  {
    v3 = CoTaskMemAlloc(saturated_mul(cValues + 1, 8u));
    v4 = (signed __int64)v3;
    if ( v3 )
    {
      memset_0(v3, 0, 8LL * (cValues + 1));
      v2 = cValues + 1;
      v5 = cbMaxValueNameLen + 1;
      if ( (unsigned int)v5 < cbMaxValueNameLen )
      {
        cbMaxValueNameLen = -1;
        v0 = -2147024362;
        goto LABEL_18;
      }
      ++cbMaxValueNameLen;
      v1 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v5, 2u));
      if ( v1 )
      {
        v6 = 0;
        v7 = 0;
        v0 = 0;
        while ( v6 < cValues )
        {
          cchValueName = cbMaxValueNameLen;
          if ( !RegEnumValueW(hKey, v6, v1, &cchValueName, 0, 0, 0, 0) )
          {
            v8 = DupeString(v1);
            *(_QWORD *)(v4 + 8LL * v7) = v8;
            if ( !v8 )
              goto LABEL_5;
            ++v7;
          }
          ++v6;
        }
        goto LABEL_17;
      }
    }
  }
LABEL_5:
  v0 = -2147024882;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 )
  {
    for ( i = 0; i < v2; ++i )
    {
      v11 = *(void **)(v4 + 8LL * i);
      if ( v11 )
        CoTaskMemFree(v11);
    }
    CoTaskMemFree((LPVOID)v4);
  }
  if ( v1 )
    CoTaskMemFree(v1);
  return v0;
}

```

## disassembly

```asm
0x18004de58  push    rbp
0x18004de5a  push    rbx
0x18004de5b  push    rsi
0x18004de5c  push    rdi
0x18004de5d  push    r12
0x18004de5f  push    r13
0x18004de61  push    r14
0x18004de63  push    r15
0x18004de65  mov     rbp, rsp
0x18004de68  sub     rsp, 68h
0x18004de6c  xor     r13d, r13d
0x18004de6f  cmp     cs:?g_arrConfigNonRedistFiles@@3PEAPEAGEA, r13; ushort * * g_arrConfigNonRedistFiles
0x18004de76  mov     ebx, r13d
0x18004de79  mov     [rbp+cValues], r13d
0x18004de7d  mov     [rbp+cbMaxValueNameLen], r13d
0x18004de81  mov     [rbp+hKey], r13
0x18004de85  jnz     loc_18004E06D
0x18004de8b  lea     rax, [rbp+hKey]
0x18004de8f  xor     r8d, r8d; ulOptions
0x18004de92  lea     esi, [r13+1]
0x18004de96  mov     [rsp+68h+phkResult], rax; phkResult
0x18004de9b  mov     r9d, esi; samDesired
0x18004de9e  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Ole\\NonRedist"
0x18004dea5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004deac  mov     r14d, r13d
0x18004deaf  mov     r12d, r13d
0x18004deb2  call    cs:__imp_RegOpenKeyExW
0x18004deb8  test    eax, eax
0x18004deba  jnz     loc_18004DFF1
0x18004dec0  mov     rcx, [rbp+hKey]; hKey
0x18004dec4  lea     rax, [rbp+cbMaxValueNameLen]
0x18004dec8  mov     [rsp+68h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004decd  xor     r9d, r9d; lpReserved
0x18004ded0  mov     [rsp+68h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004ded5  xor     r8d, r8d; lpcchClass
0x18004ded8  mov     [rsp+68h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18004dedd  xor     edx, edx; lpClass
0x18004dedf  mov     [rsp+68h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18004dee4  lea     rax, [rbp+cValues]
0x18004dee8  mov     [rsp+68h+lpcValues], rax; lpcValues
0x18004deed  mov     [rsp+68h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004def2  mov     [rsp+68h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18004def7  mov     [rsp+68h+phkResult], r13; lpcSubKeys
0x18004defc  call    cs:__imp_RegQueryInfoKeyW
0x18004df02  test    eax, eax
0x18004df04  jnz     loc_18004DFF1
0x18004df0a  mov     ecx, [rbp+cValues]
0x18004df0d  lea     eax, [rsi+7]
0x18004df10  inc     ecx
0x18004df12  lea     rbx, [r13-1]
0x18004df16  mul     rcx
0x18004df19  cmovb   rax, rbx
0x18004df1d  mov     rcx, rax; cb
0x18004df20  call    cs:__imp_CoTaskMemAlloc
0x18004df26  mov     rdi, rax
0x18004df29  test    rax, rax
0x18004df2c  jnz     short loc_18004DF38
0x18004df2e  mov     ebx, 8007000Eh
0x18004df33  jmp     loc_18004E022
0x18004df38  mov     r8d, [rbp+cValues]
0x18004df3c  xor     edx, edx; Val
0x18004df3e  inc     r8d
0x18004df41  mov     rcx, rdi; void *
0x18004df44  shl     r8, 3; Size
0x18004df48  call    memset_0
0x18004df4d  mov     eax, [rbp+cbMaxValueNameLen]
0x18004df50  mov     r12d, [rbp+cValues]
0x18004df54  inc     r12d
0x18004df57  lea     ecx, [rax+1]
0x18004df5a  cmp     ecx, eax
0x18004df5c  jb      loc_18004DFE3
0x18004df62  mov     [rbp+cbMaxValueNameLen], ecx
0x18004df65  mov     eax, 2
0x18004df6a  mul     rcx
0x18004df6d  cmovb   rax, rbx
0x18004df71  mov     rcx, rax; cb
0x18004df74  call    cs:__imp_CoTaskMemAlloc
0x18004df7a  mov     r14, rax
0x18004df7d  test    rax, rax
0x18004df80  jz      short loc_18004DF2E
0x18004df82  mov     esi, r13d
0x18004df85  mov     r15d, r13d
0x18004df88  mov     ebx, r13d
0x18004df8b  cmp     esi, [rbp+cValues]
0x18004df8e  jnb     short loc_18004E00E
0x18004df90  mov     eax, [rbp+cbMaxValueNameLen]
0x18004df93  lea     r9, [rbp+cchValueName]; lpcchValueName
0x18004df97  mov     rcx, [rbp+hKey]; hKey
0x18004df9b  mov     r8, r14; lpValueName
0x18004df9e  mov     [rsp+68h+lpcValues], r13; lpcbData
0x18004dfa3  mov     edx, esi; dwIndex
0x18004dfa5  mov     [rsp+68h+lpcbMaxClassLen], r13; lpData
0x18004dfaa  mov     [rsp+68h+lpcbMaxSubKeyLen], r13; lpType
0x18004dfaf  mov     [rsp+68h+phkResult], r13; lpReserved
0x18004dfb4  mov     [rbp+cchValueName], eax
0x18004dfb7  call    cs:__imp_RegEnumValueW
0x18004dfbd  test    eax, eax
0x18004dfbf  jnz     short loc_18004DFDF
0x18004dfc1  mov     rcx, r14; unsigned __int16 *
0x18004dfc4  call    ?DupeString@@YAPEAGPEAG@Z; DupeString(ushort *)
0x18004dfc9  mov     rcx, rax
0x18004dfcc  mov     eax, r15d
0x18004dfcf  mov     [rdi+rax*8], rcx
0x18004dfd3  test    rcx, rcx
0x18004dfd6  jz      loc_18004DF2E
0x18004dfdc  inc     r15d
0x18004dfdf  inc     esi
0x18004dfe1  jmp     short loc_18004DF8B
0x18004dfe3  mov     [rbp+cbMaxValueNameLen], 0FFFFFFFFh
0x18004dfea  mov     ebx, 80070216h
0x18004dfef  jmp     short loc_18004E022
0x18004dff1  mov     ecx, 8; cb
0x18004dff6  call    cs:__imp_CoTaskMemAlloc
0x18004dffc  mov     rdi, rax
0x18004dfff  test    rax, rax
0x18004e002  jz      loc_18004DF2E
0x18004e008  mov     r12d, esi
0x18004e00b  mov     [rax], r13
0x18004e00e  xor     eax, eax
0x18004e010  lock cmpxchg cs:?g_arrConfigNonRedistFiles@@3PEAPEAGEA, rdi; ushort * * g_arrConfigNonRedistFiles
0x18004e019  neg     rax
0x18004e01c  sbb     rcx, rcx
0x18004e01f  and     rdi, rcx
0x18004e022  mov     rcx, [rbp+hKey]; hKey
0x18004e026  test    rcx, rcx
0x18004e029  jz      short loc_18004E031
0x18004e02b  call    cs:__imp_RegCloseKey
0x18004e031  test    rdi, rdi
0x18004e034  jz      short loc_18004E05F
0x18004e036  mov     esi, r13d
0x18004e039  test    r12d, r12d
0x18004e03c  jz      short loc_18004E056
0x18004e03e  mov     eax, esi
0x18004e040  mov     rcx, [rdi+rax*8]; pv
0x18004e044  test    rcx, rcx
0x18004e047  jz      short loc_18004E04F
0x18004e049  call    cs:__imp_CoTaskMemFree
0x18004e04f  inc     esi
0x18004e051  cmp     esi, r12d
0x18004e054  jb      short loc_18004E03E
0x18004e056  mov     rcx, rdi; pv
0x18004e059  call    cs:__imp_CoTaskMemFree
0x18004e05f  test    r14, r14
0x18004e062  jz      short loc_18004E06D
0x18004e064  mov     rcx, r14; pv
0x18004e067  call    cs:__imp_CoTaskMemFree
0x18004e06d  mov     eax, ebx
0x18004e06f  add     rsp, 68h
0x18004e073  pop     r15
0x18004e075  pop     r14
0x18004e077  pop     r13
0x18004e079  pop     r12
0x18004e07b  pop     rdi
0x18004e07c  pop     rsi
0x18004e07d  pop     rbx
0x18004e07e  pop     rbp
0x18004e07f  retn
```
