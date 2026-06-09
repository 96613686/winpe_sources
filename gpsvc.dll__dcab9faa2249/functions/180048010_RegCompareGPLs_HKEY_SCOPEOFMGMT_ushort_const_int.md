# RegCompareGPLs(HKEY__ *,_SCOPEOFMGMT *,ushort const *,int *)

- ea: `0x180048010`
- end: `0x18004839e`
- name: `?RegCompareGPLs@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBGPEAH@Z`
- size: `910`
- prototype: `unsigned int(HKEY, struct _SCOPEOFMGMT *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800473b0`

## callees

- `0x180048010`
- `0x18007d320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800480de`
- `api-ms-win-crt-private-l1-1-0!_o__itow` at `0x1800480de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048270`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800482c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180048270`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800482c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048170`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048170`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048377`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004831d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004834d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004831d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004834d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048393`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048145`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180048145`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004805b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800480fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004805b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800480fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800481b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004825e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800482b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800481b5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180048205`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004825e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800482b7`

## string_xrefs

- `0x18004823a`: `DsPath`

## pseudocode

```c
LSTATUS __fastcall RegCompareGPLs(HKEY a1, struct _SCOPEOFMGMT *a2, const unsigned __int16 *a3, int *a4)
{
  LSTATUS result; // eax
  LSTATUS v7; // ebx
  int v8; // edi
  __int64 v9; // r15
  _WORD *v10; // rsi
  wchar_t *v11; // rax
  DWORD v12; // edi
  const WCHAR *v13; // rax
  const WCHAR *v14; // r13
  bool v15; // zf
  const WCHAR *v16; // rax
  const WCHAR *v17; // r13
  DWORD cbData; // [rsp+60h] [rbp-69h] BYREF
  DWORD Type; // [rsp+64h] [rbp-65h] BYREF
  int v20; // [rsp+68h] [rbp-61h]
  BYTE Data[4]; // [rsp+6Ch] [rbp-5Dh] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-59h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-49h] BYREF
  wchar_t Buffer[32]; // [rsp+90h] [rbp-39h] BYREF

  *a4 = 0;
  hKey = 0;
  result = RegOpenKeyExW(a1, a3, 0, 0xF003Fu, &hKey);
  v7 = result;
  if ( result )
  {
    *a4 = 1;
  }
  else
  {
    v8 = 0;
    phkResult = 0;
    v20 = 0;
    if ( a2 )
    {
      do
      {
        v9 = *((_QWORD *)a2 + 3);
        v10 = 0;
        while ( v9 )
        {
          if ( v7 || *a4 )
            break;
          Type = 0;
          cbData = 0;
          *(_DWORD *)Data = 0;
          cbMaxValueLen = 0;
          if ( v10 )
          {
            LocalFree(v10);
            v10 = 0;
          }
          v11 = _itow(v8, Buffer, 16);
          v7 = RegOpenKeyExW(hKey, v11, 0, 0xF003Fu, &phkResult);
          if ( !v7 )
          {
            v7 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
            if ( !v7 )
            {
              v12 = cbMaxValueLen + 2;
              if ( cbMaxValueLen + 2 >= cbMaxValueLen )
              {
                v10 = LocalAlloc(0x40u, v12);
                if ( v10 )
                {
                  Type = 0;
                  *(_DWORD *)Data = 0;
                  cbData = 4;
                  v7 = RegQueryValueExW(phkResult, L"Enabled", 0, &Type, Data, &cbData);
                  if ( !v7 && *(_DWORD *)Data == *(_DWORD *)(v9 + 8) )
                  {
                    Type = 0;
                    *(_DWORD *)Data = 0;
                    cbData = 4;
                    v7 = RegQueryValueExW(phkResult, L"NoOverride", 0, &Type, Data, &cbData);
                    if ( !v7 && *(_DWORD *)Data == *(_DWORD *)(v9 + 12) )
                    {
                      v13 = *(const WCHAR **)v9;
                      v14 = &DomainName;
                      v15 = *(_QWORD *)v9 == 0;
                      Type = 0;
                      if ( !v15 )
                        v14 = v13;
                      *v10 = 0;
                      cbData = v12;
                      v7 = RegQueryValueExW(phkResult, L"DsPath", 0, &Type, (LPBYTE)v10, &cbData);
                      if ( !v7 && !(unsigned int)_o__wcsicmp(v10, v14) )
                      {
                        v16 = *(const WCHAR **)a2;
                        v17 = &DomainName;
                        v15 = *(_QWORD *)a2 == 0;
                        Type = 0;
                        if ( !v15 )
                          v17 = v16;
                        *v10 = 0;
                        cbData = v12;
                        v7 = RegQueryValueExW(phkResult, L"SOM", 0, &Type, (LPBYTE)v10, &cbData);
                        if ( !v7 && !(unsigned int)_o__wcsicmp(v10, v17) )
                        {
                          RegCloseKey(phkResult);
                          v8 = v20 + 1;
                          phkResult = 0;
                          v9 = *(_QWORD *)(v9 + 16);
                          ++v20;
                          continue;
                        }
                      }
                    }
                  }
                }
              }
              else
              {
                v7 = 534;
              }
              v8 = v20;
            }
          }
          *a4 = 1;
        }
        a2 = (struct _SCOPEOFMGMT *)*((_QWORD *)a2 + 4);
        if ( v10 )
          LocalFree(v10);
      }
      while ( a2 );
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180048010  push    rbp
0x180048012  push    rbx
0x180048013  push    r12
0x180048015  push    r13
0x180048017  push    r14
0x180048019  lea     rbp, [rsp-37h]
0x18004801e  sub     rsp, 100h
0x180048025  mov     rax, cs:__security_cookie
0x18004802c  xor     rax, rsp
0x18004802f  mov     [rbp+57h+var_50], rax
0x180048033  mov     r12, rdx
0x180048036  mov     rax, r8
0x180048039  lea     rdx, [rbp+57h+hKey]
0x18004803d  xor     r13d, r13d
0x180048040  mov     [rsp+120h+phkResult], rdx; phkResult
0x180048045  mov     r14, r9
0x180048048  mov     [r9], r13d
0x18004804b  mov     rdx, rax; lpSubKey
0x18004804e  mov     r9d, 0F003Fh; samDesired
0x180048054  mov     [rbp+57h+hKey], r13
0x180048058  xor     r8d, r8d; ulOptions
0x18004805b  call    cs:__imp_RegOpenKeyExW
0x180048061  mov     ebx, eax
0x180048063  test    eax, eax
0x180048065  jnz     loc_18004836B
0x18004806b  mov     [rsp+120h+var_30], rdi
0x180048073  mov     edi, r13d
0x180048076  mov     [rbp+57h+var_B0], r13
0x18004807a  mov     [rbp+57h+var_B8], r13d
0x18004807e  test    r12, r12
0x180048081  jz      loc_180048319
0x180048087  mov     [rsp+120h+var_28], rsi
0x18004808f  mov     [rsp+120h+var_38], r15
0x180048097  mov     r15, [r12+18h]
0x18004809c  mov     rsi, r13
0x18004809f  test    r15, r15
0x1800480a2  jz      loc_1800482E9
0x1800480a8  test    ebx, ebx
0x1800480aa  jnz     loc_1800482E9
0x1800480b0  cmp     [r14], ebx
0x1800480b3  jnz     loc_1800482E9
0x1800480b9  mov     [rbp+57h+Type], r13d
0x1800480bd  mov     [rbp+57h+cbData], r13d
0x1800480c1  mov     dword ptr [rbp+57h+Data], r13d
0x1800480c5  mov     [rbp+57h+cbMaxValueLen], r13d
0x1800480c9  test    rsi, rsi
0x1800480cc  jnz     loc_180048374
0x1800480d2  mov     r8d, 10h; Radix
0x1800480d8  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800480dc  mov     ecx, edi; Value
0x1800480de  call    cs:__imp__itow
0x1800480e4  lea     rcx, [rbp+57h+var_B0]
0x1800480e8  mov     r9d, 0F003Fh; samDesired
0x1800480ee  mov     [rsp+120h+phkResult], rcx; phkResult
0x1800480f3  xor     r8d, r8d; ulOptions
0x1800480f6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800480fa  mov     rdx, rax; lpSubKey
0x1800480fd  call    cs:__imp_RegOpenKeyExW
0x180048103  mov     ebx, eax
0x180048105  test    eax, eax
0x180048107  jnz     loc_1800482D9
0x18004810d  mov     rcx, [rbp+57h+var_B0]; hKey
0x180048111  lea     rax, [rbp+57h+cbMaxValueLen]
0x180048115  mov     [rsp+120h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18004811a  xor     r9d, r9d; lpReserved
0x18004811d  mov     [rsp+120h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180048122  xor     r8d, r8d; lpcchClass
0x180048125  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18004812a  xor     edx, edx; lpClass
0x18004812c  mov     [rsp+120h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180048131  mov     [rsp+120h+lpcValues], r13; lpcValues
0x180048136  mov     [rsp+120h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18004813b  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180048140  mov     [rsp+120h+phkResult], r13; lpcSubKeys
0x180048145  call    cs:__imp_RegQueryInfoKeyW
0x18004814b  mov     ebx, eax
0x18004814d  test    eax, eax
0x18004814f  jnz     loc_1800482D9
0x180048155  mov     eax, [rbp+57h+cbMaxValueLen]
0x180048158  lea     edi, [rax+2]
0x18004815b  cmp     edi, eax
0x18004815d  jnb     short loc_180048169
0x18004815f  mov     ebx, 216h
0x180048164  jmp     loc_1800482D6
0x180048169  mov     edx, edi; uBytes
0x18004816b  mov     ecx, 40h ; '@'; uFlags
0x180048170  call    cs:__imp_LocalAlloc
0x180048176  mov     rsi, rax
0x180048179  test    rax, rax
0x18004817c  jz      loc_1800482D6
0x180048182  mov     rcx, [rbp+57h+var_B0]; hKey
0x180048186  lea     rax, [rbp+57h+cbData]
0x18004818a  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004818f  lea     r9, [rbp+57h+Type]; lpType
0x180048193  lea     rax, [rbp+57h+Data]
0x180048197  mov     [rbp+57h+Type], r13d
0x18004819b  xor     r8d, r8d; lpReserved
0x18004819e  mov     [rsp+120h+phkResult], rax; lpData
0x1800481a3  lea     rdx, aEnabled; "Enabled"
0x1800481aa  mov     dword ptr [rbp+57h+Data], r13d
0x1800481ae  mov     [rbp+57h+cbData], 4
0x1800481b5  call    cs:__imp_RegQueryValueExW
0x1800481bb  mov     ebx, eax
0x1800481bd  test    eax, eax
0x1800481bf  jnz     loc_1800482D6
0x1800481c5  mov     eax, [r15+8]
0x1800481c9  cmp     dword ptr [rbp+57h+Data], eax
0x1800481cc  jnz     loc_1800482D6
0x1800481d2  mov     rcx, [rbp+57h+var_B0]; hKey
0x1800481d6  lea     rax, [rbp+57h+cbData]
0x1800481da  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800481df  lea     r9, [rbp+57h+Type]; lpType
0x1800481e3  lea     rax, [rbp+57h+Data]
0x1800481e7  mov     [rbp+57h+Type], r13d
0x1800481eb  xor     r8d, r8d; lpReserved
0x1800481ee  mov     [rsp+120h+phkResult], rax; lpData
0x1800481f3  lea     rdx, aNooverride_0; "NoOverride"
0x1800481fa  mov     dword ptr [rbp+57h+Data], r13d
0x1800481fe  mov     [rbp+57h+cbData], 4
0x180048205  call    cs:__imp_RegQueryValueExW
0x18004820b  mov     ebx, eax
0x18004820d  test    eax, eax
0x18004820f  jnz     loc_1800482D6
0x180048215  mov     eax, [r15+0Ch]
0x180048219  cmp     dword ptr [rbp+57h+Data], eax
0x18004821c  jnz     loc_1800482D6
0x180048222  mov     rax, [r15]
0x180048225  lea     r13, DomainName
0x18004822c  test    rax, rax
0x18004822f  mov     [rbp+57h+Type], ebx
0x180048232  lea     r9, [rbp+57h+Type]; lpType
0x180048236  cmovnz  r13, rax
0x18004823a  lea     rdx, aDspath_0; "DsPath"
0x180048241  xor     eax, eax
0x180048243  xor     r8d, r8d; lpReserved
0x180048246  mov     [rsi], ax
0x180048249  lea     rax, [rbp+57h+cbData]
0x18004824d  mov     rcx, [rbp+57h+var_B0]; hKey
0x180048251  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbData
0x180048256  mov     [rsp+120h+phkResult], rsi; lpData
0x18004825b  mov     [rbp+57h+cbData], edi
0x18004825e  call    cs:__imp_RegQueryValueExW
0x180048264  mov     ebx, eax
0x180048266  test    eax, eax
0x180048268  jnz     short loc_1800482D3
0x18004826a  mov     rdx, r13
0x18004826d  mov     rcx, rsi
0x180048270  call    cs:__imp__o__wcsicmp
0x180048276  test    eax, eax
0x180048278  jnz     short loc_1800482D3
0x18004827a  mov     rax, [r12]
0x18004827e  lea     r13, DomainName
0x180048285  test    rax, rax
0x180048288  mov     [rbp+57h+Type], ebx
0x18004828b  lea     r9, [rbp+57h+Type]; lpType
0x18004828f  cmovnz  r13, rax
0x180048293  lea     rdx, aSom; "SOM"
0x18004829a  xor     eax, eax
0x18004829c  xor     r8d, r8d; lpReserved
0x18004829f  mov     [rsi], ax
0x1800482a2  lea     rax, [rbp+57h+cbData]
0x1800482a6  mov     rcx, [rbp+57h+var_B0]; hKey
0x1800482aa  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800482af  mov     [rsp+120h+phkResult], rsi; lpData
0x1800482b4  mov     [rbp+57h+cbData], edi
0x1800482b7  call    cs:__imp_RegQueryValueExW
0x1800482bd  mov     ebx, eax
0x1800482bf  test    eax, eax
0x1800482c1  jnz     short loc_1800482D3
0x1800482c3  mov     rdx, r13
0x1800482c6  mov     rcx, rsi
0x1800482c9  call    cs:__imp__o__wcsicmp
0x1800482cf  test    eax, eax
0x1800482d1  jz      short loc_180048349
0x1800482d3  xor     r13d, r13d
0x1800482d6  mov     edi, [rbp+57h+var_B8]
0x1800482d9  mov     dword ptr [r14], 1
0x1800482e0  test    r15, r15
0x1800482e3  jnz     loc_1800480A8
0x1800482e9  mov     r12, [r12+20h]
0x1800482ee  test    rsi, rsi
0x1800482f1  jnz     loc_180048385
0x1800482f7  test    r12, r12
0x1800482fa  jnz     loc_180048097
0x180048300  mov     rcx, [rbp+57h+var_B0]; hKey
0x180048304  mov     r15, [rsp+120h+var_38]
0x18004830c  mov     rsi, [rsp+120h+var_28]
0x180048314  test    rcx, rcx
0x180048317  jnz     short loc_180048393
0x180048319  mov     rcx, [rbp+57h+hKey]; hKey
0x18004831d  call    cs:__imp_RegCloseKey
0x180048323  mov     rdi, [rsp+120h+var_30]
0x18004832b  mov     eax, ebx
0x18004832d  mov     rcx, [rbp+57h+var_50]
0x180048331  xor     rcx, rsp; StackCookie
0x180048334  call    __security_check_cookie
0x180048339  add     rsp, 100h
0x180048340  pop     r14
0x180048342  pop     r13
0x180048344  pop     r12
0x180048346  pop     rbx
0x180048347  pop     rbp
0x180048348  retn
0x180048349  mov     rcx, [rbp+57h+var_B0]; hKey
0x18004834d  call    cs:__imp_RegCloseKey
0x180048353  mov     edi, [rbp+57h+var_B8]
0x180048356  xor     r13d, r13d
0x180048359  inc     edi
0x18004835b  mov     [rbp+57h+var_B0], r13
0x18004835f  mov     r15, [r15+10h]
0x180048363  mov     [rbp+57h+var_B8], edi
0x180048366  jmp     loc_1800482E0
0x18004836b  mov     dword ptr [r14], 1
0x180048372  jmp     short loc_18004832D
0x180048374  mov     rcx, rsi; hMem
0x180048377  call    cs:__imp_LocalFree
0x18004837d  mov     rsi, r13
0x180048380  jmp     loc_1800480D2
0x180048385  mov     rcx, rsi; hMem
0x180048388  call    cs:__imp_LocalFree
0x18004838e  jmp     loc_1800482F7
0x180048393  call    cs:__imp_RegCloseKey
0x180048399  jmp     loc_180048319
```
