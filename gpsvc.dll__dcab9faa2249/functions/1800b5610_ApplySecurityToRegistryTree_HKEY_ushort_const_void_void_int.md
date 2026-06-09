# ApplySecurityToRegistryTree(HKEY__ *,ushort const *,void *,void *,int)

- ea: `0x1800b5610`
- end: `0x1800b588c`
- name: `?ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEBGPEAX2H@Z`
- size: `636`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, void *, void *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b5610`
- `0x1800b5894`

## callees

- `0x180066284`
- `0x180075ec0`
- `0x1800b5610`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b576c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b576c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b575e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b575e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5870`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b56c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b56c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5862`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b572c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b572c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b56e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5786`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b56e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b5786`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5686`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5686`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b57d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800b57d7`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800b56b2`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x1800b56b2`

## string_xrefs

- `0x1800b581a`: `Failed to apply security to <%ls>`
- `0x1800b5840`: `Failed to apply security to <%ls>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ApplySecurityToRegistryTree(HKEY a1, const unsigned __int16 *a2, void *a3, void *a4, int a5)
{
  WCHAR *v6; // rsi
  signed int Key; // eax
  unsigned int v11; // ebx
  bool v12; // cc
  void *v13; // r8
  DWORD v14; // eax
  DWORD i; // edi
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-11h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-Dh] BYREF
  DWORD cchName; // [rsp+68h] [rbp-9h] BYREF
  HKEY hKey[10]; // [rsp+70h] [rbp-1h] BYREF

  cSubKeys = 0;
  v6 = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  hKey[0] = 0;
  SetPolicyOwnerOnKey(a1, a2);
  if ( a5 )
  {
    Key = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x40000u, 0, hKey, 0);
    v11 = Key;
    v12 = Key <= 0;
    if ( Key )
      goto LABEL_3;
    v13 = a3;
  }
  else
  {
    Key = RegOpenKeyExW(a1, a2, 0, 0x40000u, hKey);
    v11 = Key;
    v12 = Key <= 0;
    if ( Key )
      goto LABEL_3;
    v13 = a4;
  }
  Key = RegSetKeySecurity(hKey[0], 4u, v13);
  v11 = Key;
  v12 = Key <= 0;
  if ( !Key )
  {
    RegCloseKey(hKey[0]);
    hKey[0] = 0;
    Key = RegOpenKeyExW(a1, a2, 0, 0x20019u, hKey);
    v11 = Key;
    v12 = Key <= 0;
    if ( !Key )
    {
      Key = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v11 = Key;
      v12 = Key <= 0;
      if ( !Key )
      {
        if ( cSubKeys )
        {
          v14 = cbMaxSubKeyLen;
          if ( cbMaxSubKeyLen )
          {
            ++cbMaxSubKeyLen;
            v6 = (WCHAR *)LocalAlloc(0x40u, 2LL * (v14 + 1));
            if ( !v6 )
            {
              Key = GetLastError();
              v11 = Key;
              v12 = Key <= 0;
              goto LABEL_3;
            }
            for ( i = 0; i < cSubKeys; ++i )
            {
              cchName = cbMaxSubKeyLen;
              Key = RegEnumKeyExW(hKey[0], i, v6, &cchName, 0, 0, 0, 0);
              v11 = Key;
              v12 = Key <= 0;
              if ( Key )
                goto LABEL_3;
              if ( (int)ApplySecurityToRegistryTree(hKey[0], v6, a3, a4, 0) < 0 && *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(2u, L"Failed to apply security to <%ls>", v6);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(2u, L"Failed to apply security to <%ls>", v6);
                }
              }
            }
          }
        }
        v11 = 0;
        goto LABEL_27;
      }
    }
  }
LABEL_3:
  if ( !v12 )
    v11 = (unsigned __int16)Key | 0x80070000;
LABEL_27:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v6 )
    LocalFree(v6);
  return v11;
}

```

## disassembly

```asm
0x1800b5610  push    rbp
0x1800b5612  push    rbx
0x1800b5613  push    rsi
0x1800b5614  push    rdi
0x1800b5615  push    r12
0x1800b5617  push    r13
0x1800b5619  push    r14
0x1800b561b  push    r15
0x1800b561d  lea     rbp, [rsp-17h]
0x1800b5622  sub     rsp, 88h
0x1800b5629  xor     r13d, r13d
0x1800b562c  mov     r15, r9
0x1800b562f  mov     [rbp+4Fh+cSubKeys], r13d
0x1800b5633  mov     esi, r13d
0x1800b5636  mov     [rbp+4Fh+cbMaxSubKeyLen], r13d
0x1800b563a  mov     r12, r8
0x1800b563d  mov     [rbp+4Fh+cchName], r13d
0x1800b5641  mov     rdi, rdx
0x1800b5644  mov     [rbp+4Fh+hKey], r13
0x1800b5648  mov     r14, rcx
0x1800b564b  call    ?SetPolicyOwnerOnKey@@YAKPEAUHKEY__@@PEBG@Z; SetPolicyOwnerOnKey(HKEY__ *,ushort const *)
0x1800b5650  xor     r8d, r8d; ulOptions
0x1800b5653  lea     rax, [rbp+4Fh+hKey]
0x1800b5657  mov     rdx, rdi; lpSubKey
0x1800b565a  mov     rcx, r14; hKey
0x1800b565d  cmp     [rbp+4Fh+arg_20], r13d
0x1800b5661  jz      loc_1800B577B
0x1800b5667  mov     [rsp+0C0h+lpdwDisposition], r13; lpdwDisposition
0x1800b566c  xor     r9d, r9d; lpClass
0x1800b566f  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800b5674  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800b5679  mov     [rsp+0C0h+samDesired], 40000h; samDesired
0x1800b5681  mov     [rsp+0C0h+dwOptions], r13d; dwOptions
0x1800b5686  call    cs:__imp_RegCreateKeyExW
0x1800b568c  mov     ebx, eax
0x1800b568e  test    eax, eax
0x1800b5690  jz      short loc_1800B56A6
0x1800b5692  jle     loc_1800B5859
0x1800b5698  movzx   ebx, ax
0x1800b569b  or      ebx, 80070000h
0x1800b56a1  jmp     loc_1800B5859
0x1800b56a6  mov     r8, r12; pSecurityDescriptor
0x1800b56a9  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800b56ad  mov     edx, 4; SecurityInformation
0x1800b56b2  call    cs:__imp_RegSetKeySecurity
0x1800b56b8  mov     ebx, eax
0x1800b56ba  test    eax, eax
0x1800b56bc  jnz     short loc_1800B5692
0x1800b56be  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800b56c2  call    cs:__imp_RegCloseKey
0x1800b56c8  lea     rax, [rbp+4Fh+hKey]
0x1800b56cc  mov     [rbp+4Fh+hKey], r13
0x1800b56d0  mov     r9d, 20019h; samDesired
0x1800b56d6  mov     qword ptr [rsp+0C0h+dwOptions], rax; phkResult
0x1800b56db  xor     r8d, r8d; ulOptions
0x1800b56de  mov     rdx, rdi; lpSubKey
0x1800b56e1  mov     rcx, r14; hKey
0x1800b56e4  call    cs:__imp_RegOpenKeyExW
0x1800b56ea  mov     ebx, eax
0x1800b56ec  test    eax, eax
0x1800b56ee  jnz     short loc_1800B5692
0x1800b56f0  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800b56f4  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x1800b56f8  mov     [rsp+0C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800b56fd  xor     r9d, r9d; lpReserved
0x1800b5700  mov     [rsp+0C0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800b5705  xor     r8d, r8d; lpcchClass
0x1800b5708  mov     [rsp+0C0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800b570d  xor     edx, edx; lpClass
0x1800b570f  mov     [rsp+0C0h+lpdwDisposition], r13; lpcbMaxValueNameLen
0x1800b5714  mov     [rsp+0C0h+phkResult], r13; lpcValues
0x1800b5719  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpcbMaxClassLen
0x1800b571e  mov     qword ptr [rsp+0C0h+samDesired], rax; lpcbMaxSubKeyLen
0x1800b5723  lea     rax, [rbp+4Fh+cSubKeys]
0x1800b5727  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpcSubKeys
0x1800b572c  call    cs:__imp_RegQueryInfoKeyW
0x1800b5732  mov     ebx, eax
0x1800b5734  test    eax, eax
0x1800b5736  jnz     loc_1800B5692
0x1800b573c  cmp     [rbp+4Fh+cSubKeys], r13d
0x1800b5740  jz      loc_1800B5856
0x1800b5746  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x1800b5749  test    eax, eax
0x1800b574b  jz      loc_1800B5856
0x1800b5751  inc     eax
0x1800b5753  lea     ecx, [rbx+40h]; uFlags
0x1800b5756  mov     edx, eax
0x1800b5758  add     rdx, rdx; uBytes
0x1800b575b  mov     [rbp+4Fh+cbMaxSubKeyLen], eax
0x1800b575e  call    cs:__imp_LocalAlloc
0x1800b5764  mov     rsi, rax
0x1800b5767  test    rax, rax
0x1800b576a  jnz     short loc_1800B579E
0x1800b576c  call    cs:__imp_GetLastError
0x1800b5772  mov     ebx, eax
0x1800b5774  test    eax, eax
0x1800b5776  jmp     loc_1800B5692
0x1800b577b  mov     r9d, 40000h; samDesired
0x1800b5781  mov     qword ptr [rsp+0C0h+dwOptions], rax; phkResult
0x1800b5786  call    cs:__imp_RegOpenKeyExW
0x1800b578c  mov     ebx, eax
0x1800b578e  test    eax, eax
0x1800b5790  jnz     loc_1800B5692
0x1800b5796  mov     r8, r15
0x1800b5799  jmp     loc_1800B56A9
0x1800b579e  mov     edi, r13d
0x1800b57a1  mov     r14d, 2
0x1800b57a7  cmp     edi, [rbp+4Fh+cSubKeys]
0x1800b57aa  jnb     loc_1800B5856
0x1800b57b0  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x1800b57b3  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x1800b57b7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800b57bb  mov     r8, rsi; lpName
0x1800b57be  mov     [rsp+0C0h+phkResult], r13; lpftLastWriteTime
0x1800b57c3  mov     edx, edi; dwIndex
0x1800b57c5  mov     [rsp+0C0h+lpSecurityAttributes], r13; lpcchClass
0x1800b57ca  mov     qword ptr [rsp+0C0h+samDesired], r13; lpClass
0x1800b57cf  mov     qword ptr [rsp+0C0h+dwOptions], r13; lpReserved
0x1800b57d4  mov     [rbp+4Fh+cchName], eax
0x1800b57d7  call    cs:__imp_RegEnumKeyExW
0x1800b57dd  mov     ebx, eax
0x1800b57df  test    eax, eax
0x1800b57e1  jnz     loc_1800B5692
0x1800b57e7  mov     rcx, [rbp+4Fh+hKey]; HKEY
0x1800b57eb  mov     r9, r15; void *
0x1800b57ee  mov     r8, r12; void *
0x1800b57f1  mov     [rsp+0C0h+dwOptions], r13d; int
0x1800b57f6  mov     rdx, rsi; unsigned __int16 *
0x1800b57f9  call    ?ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEBGPEAX2H@Z; ApplySecurityToRegistryTree(HKEY__ *,ushort const *,void *,void *,int)
0x1800b57fe  test    eax, eax
0x1800b5800  jns     short loc_1800B584F
0x1800b5802  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800b5809  jz      short loc_1800B584F
0x1800b580b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b5812  test    rax, rax
0x1800b5815  jz      short loc_1800B582B
0x1800b5817  mov     r8, rsi
0x1800b581a  lea     rdx, aFailedToApplyS; "Failed to apply security to <%ls>"
0x1800b5821  mov     ecx, r14d
0x1800b5824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5829  jmp     short loc_1800B584F
0x1800b582b  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800b5832  jz      short loc_1800B584F
0x1800b5834  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b583b  jz      short loc_1800B584F
0x1800b583d  mov     r8, rsi
0x1800b5840  lea     rdx, aFailedToApplyS; "Failed to apply security to <%ls>"
0x1800b5847  mov     ecx, r14d; unsigned int
0x1800b584a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b584f  inc     edi
0x1800b5851  jmp     loc_1800B57A7
0x1800b5856  mov     ebx, r13d
0x1800b5859  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800b585d  test    rcx, rcx
0x1800b5860  jz      short loc_1800B5868
0x1800b5862  call    cs:__imp_RegCloseKey
0x1800b5868  test    rsi, rsi
0x1800b586b  jz      short loc_1800B5876
0x1800b586d  mov     rcx, rsi; hMem
0x1800b5870  call    cs:__imp_LocalFree
0x1800b5876  mov     eax, ebx
0x1800b5878  add     rsp, 88h
0x1800b587f  pop     r15
0x1800b5881  pop     r14
0x1800b5883  pop     r13
0x1800b5885  pop     r12
0x1800b5887  pop     rdi
0x1800b5888  pop     rsi
0x1800b5889  pop     rbx
0x1800b588a  pop     rbp
0x1800b588b  retn
```
