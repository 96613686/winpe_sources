# CModule::RegisterServer(void)

- ea: `0x180018004`
- end: `0x180018259`
- name: `?RegisterServer@CModule@@QEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018950`

## callees

- `0x180018004`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018236`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018226`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018236`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800180ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001818a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800180ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001818a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001810e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018141`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800181c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800181fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001810e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018141`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800181c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800181fa`

## string_xrefs

- `0x18001802b`: `msdrm.dll`
- `0x1800180a5`: `CLSID\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}\InProcServer32`
- `0x180018165`: `CLSID\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}\InProcServer32`
- `0x18001812c`: `ThreadingModel`
- `0x1800181e5`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall CModule::RegisterServer(CModule *this)
{
  const wchar_t *v1; // r8
  _WORD *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rdx
  _WORD *v5; // rcx
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  __int64 v8; // rdi
  __int64 v9; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  _WORD Data[264]; // [rsp+60h] [rbp-A0h] BYREF

  v1 = L"msdrm.dll";
  hKey = 0;
  v2 = Data;
  phkResult = 0;
  v3 = 2147483646;
  v4 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*v1 )
      break;
    *v2++ = *v1++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = v2 - 1;
  if ( v4 )
    v5 = v2;
  *v5 = 0;
  v6 = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
  {
    v7 = RegCreateKeyExW(
           HKEY_CLASSES_ROOT,
           L"CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36E5A32}\\InProcServer32",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    v8 = -1;
    if ( v7 )
      goto LABEL_13;
    v9 = -1;
    do
      ++v9;
    while ( Data[v9] );
    v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)Data, 2 * v9 + 2);
    if ( v7 || (v7 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, L"Free", 8u)) != 0 )
    {
LABEL_13:
      if ( v7 != 183 )
        goto LABEL_19;
    }
    v7 = RegCreateKeyExW(
           HKEY_CLASSES_ROOT,
           L"CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70CF743C}\\InProcServer32",
           0,
           0,
           0,
           2u,
           0,
           &phkResult,
           0);
    if ( v7 )
      goto LABEL_18;
    do
      ++v8;
    while ( Data[v8] );
    v7 = RegSetValueExW(phkResult, 0, 0, 1u, (const BYTE *)Data, 2 * v8 + 2);
    if ( v7 || (v7 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, L"Free", 8u)) != 0 )
    {
LABEL_18:
      if ( v7 != 183 )
      {
LABEL_19:
        if ( v7 > 0 )
          v6 = (unsigned __int16)v7 | 0x80070000;
        else
          v6 = v7;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  return v6;
}

```

## disassembly

```asm
0x180018004  push    rbp
0x180018006  push    rbx
0x180018007  push    rsi
0x180018008  push    rdi
0x180018009  lea     rbp, [rsp-188h]
0x180018011  sub     rsp, 288h
0x180018018  mov     rax, cs:__security_cookie
0x18001801f  xor     rax, rsp
0x180018022  mov     [rbp+1A0h+var_30], rax
0x180018029  xor     esi, esi
0x18001802b  lea     r8, aMsdrmDll_0; "msdrm.dll"
0x180018032  mov     [rsp+2A0h+hKey], rsi
0x180018037  lea     rax, [rsp+2A0h+Data]
0x18001803c  mov     [rsp+2A0h+var_248], rsi
0x180018041  mov     ecx, 7FFFFFFEh
0x180018046  mov     edx, 104h
0x18001804b  test    rcx, rcx
0x18001804e  jz      short loc_18001806F
0x180018050  movzx   r9d, word ptr [r8]
0x180018054  test    r9w, r9w
0x180018058  jz      short loc_18001806F
0x18001805a  mov     [rax], r9w
0x18001805e  add     r8, 2
0x180018062  add     rax, 2
0x180018066  dec     rcx
0x180018069  sub     rdx, 1
0x18001806d  jnz     short loc_18001804B
0x18001806f  test    rdx, rdx
0x180018072  lea     rcx, [rax-2]
0x180018076  cmovnz  rcx, rax
0x18001807a  mov     rax, rdx
0x18001807d  neg     rax
0x180018080  sbb     ebx, ebx
0x180018082  not     ebx
0x180018084  mov     [rcx], si
0x180018087  and     ebx, 8007007Ah
0x18001808d  test    rdx, rdx
0x180018090  jz      loc_18001823C
0x180018096  mov     [rsp+2A0h+lpdwDisposition], rsi; lpdwDisposition
0x18001809b  lea     rax, [rsp+2A0h+hKey]
0x1800180a0  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800180a5  lea     rdx, SubKey; "CLSID\\{CF2CF428-325B-48D3-8CA8-7633E36"...
0x1800180ac  mov     [rsp+2A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800180b1  xor     r9d, r9d; lpClass
0x1800180b4  mov     [rsp+2A0h+samDesired], 2; samDesired
0x1800180bc  xor     r8d, r8d; Reserved
0x1800180bf  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800180c6  mov     [rsp+2A0h+dwOptions], esi; dwOptions
0x1800180ca  call    cs:__imp_RegCreateKeyExW
0x1800180d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800180d4  test    eax, eax
0x1800180d6  jnz     short loc_18001814B
0x1800180d8  lea     rcx, [rsp+2A0h+Data]
0x1800180dd  mov     rax, rdi
0x1800180e0  inc     rax
0x1800180e3  cmp     [rcx+rax*2], si
0x1800180e7  jnz     short loc_1800180E0
0x1800180e9  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800180ee  lea     eax, ds:2[rax*2]
0x1800180f5  mov     [rsp+2A0h+samDesired], eax; cbData
0x1800180f9  mov     r9d, 1; dwType
0x1800180ff  lea     rax, [rsp+2A0h+Data]
0x180018104  xor     r8d, r8d; Reserved
0x180018107  xor     edx, edx; lpValueName
0x180018109  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001810e  call    cs:__imp_RegSetValueExW
0x180018114  test    eax, eax
0x180018116  jnz     short loc_18001814B
0x180018118  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001811d  lea     rax, Data; "Free"
0x180018124  mov     [rsp+2A0h+samDesired], 8; cbData
0x18001812c  lea     rdx, ValueName; "ThreadingModel"
0x180018133  mov     r9d, 1; dwType
0x180018139  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x18001813e  xor     r8d, r8d; Reserved
0x180018141  call    cs:__imp_RegSetValueExW
0x180018147  test    eax, eax
0x180018149  jz      short loc_180018156
0x18001814b  cmp     eax, 0B7h
0x180018150  jnz     loc_18001820B
0x180018156  mov     [rsp+2A0h+lpdwDisposition], rsi; lpdwDisposition
0x18001815b  lea     rax, [rsp+2A0h+var_248]
0x180018160  mov     [rsp+2A0h+phkResult], rax; phkResult
0x180018165  lea     rdx, aClsidBf5cb1487; "CLSID\\{BF5CB148-7C77-4D8A-A53E-D81C70C"...
0x18001816c  mov     [rsp+2A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180018171  xor     r9d, r9d; lpClass
0x180018174  mov     [rsp+2A0h+samDesired], 2; samDesired
0x18001817c  xor     r8d, r8d; Reserved
0x18001817f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180018186  mov     [rsp+2A0h+dwOptions], esi; dwOptions
0x18001818a  call    cs:__imp_RegCreateKeyExW
0x180018190  test    eax, eax
0x180018192  jnz     short loc_180018204
0x180018194  lea     rax, [rsp+2A0h+Data]
0x180018199  inc     rdi
0x18001819c  cmp     [rax+rdi*2], si
0x1800181a0  jnz     short loc_180018199
0x1800181a2  mov     rcx, [rsp+2A0h+var_248]; hKey
0x1800181a7  lea     eax, ds:2[rdi*2]
0x1800181ae  mov     [rsp+2A0h+samDesired], eax; cbData
0x1800181b2  mov     r9d, 1; dwType
0x1800181b8  lea     rax, [rsp+2A0h+Data]
0x1800181bd  xor     r8d, r8d; Reserved
0x1800181c0  xor     edx, edx; lpValueName
0x1800181c2  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800181c7  call    cs:__imp_RegSetValueExW
0x1800181cd  test    eax, eax
0x1800181cf  jnz     short loc_180018204
0x1800181d1  mov     rcx, [rsp+2A0h+var_248]; hKey
0x1800181d6  lea     rax, Data; "Free"
0x1800181dd  mov     [rsp+2A0h+samDesired], 8; cbData
0x1800181e5  lea     rdx, ValueName; "ThreadingModel"
0x1800181ec  mov     r9d, 1; dwType
0x1800181f2  mov     qword ptr [rsp+2A0h+dwOptions], rax; lpData
0x1800181f7  xor     r8d, r8d; Reserved
0x1800181fa  call    cs:__imp_RegSetValueExW
0x180018200  test    eax, eax
0x180018202  jz      short loc_18001821C
0x180018204  cmp     eax, 0B7h
0x180018209  jz      short loc_18001821C
0x18001820b  test    eax, eax
0x18001820d  jg      short loc_180018213
0x18001820f  mov     ebx, eax
0x180018211  jmp     short loc_18001821C
0x180018213  movzx   ebx, ax
0x180018216  or      ebx, 80070000h
0x18001821c  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180018221  test    rcx, rcx
0x180018224  jz      short loc_18001822C
0x180018226  call    cs:__imp_RegCloseKey
0x18001822c  mov     rcx, [rsp+2A0h+var_248]; hKey
0x180018231  test    rcx, rcx
0x180018234  jz      short loc_18001823C
0x180018236  call    cs:__imp_RegCloseKey
0x18001823c  mov     eax, ebx
0x18001823e  mov     rcx, [rbp+1A0h+var_30]
0x180018245  xor     rcx, rsp; StackCookie
0x180018248  call    __security_check_cookie
0x18001824d  add     rsp, 288h
0x180018254  pop     rdi
0x180018255  pop     rsi
0x180018256  pop     rbx
0x180018257  pop     rbp
0x180018258  retn
```
