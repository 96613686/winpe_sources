# PlaliEnumCollectionsW(ushort const *,ulong *,ushort *)

- ea: `0x18012f050`
- end: `0x18012f317`
- name: `?PlaliEnumCollectionsW@@YAJPEBGPEAKPEAG@Z`
- size: `711`
- prototype: `__int64 __fastcall(LPCWSTR lpMachineName, unsigned int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180094dc0`
- `0x180132f38`

## callees

- `0x180046c60`
- `0x18012e71c`
- `0x18012f050`
- `0x18012f320`
- `0x1801317fc`
- `0x18013ae9a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f1ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f1ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f2e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f293`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f2e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012f111`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18012f111`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012f17f`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x18012f17f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f13f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18012f13f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f269`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f2a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f130`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f269`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18012f2a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f277`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f2b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f277`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18012f2b7`

## pseudocode

```c
__int64 __fastcall PlaliEnumCollectionsW(wchar_t *lpMachineName, unsigned int *a2, unsigned __int16 *a3)
{
  unsigned int v3; // r13d
  LSTATUS v7; // esi
  unsigned int v8; // edi
  DWORD v9; // r15d
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // r12
  DWORD i; // ebx
  unsigned int v13; // eax
  void *v14; // r15
  __int64 v15; // rbx
  const unsigned __int16 *v16; // r8
  __int64 v17; // r13
  HANDLE v18; // rax
  HANDLE v19; // rax
  int v20; // eax
  bool v21; // cc
  unsigned int v23; // [rsp+60h] [rbp-19h] BYREF
  DWORD v24; // [rsp+64h] [rbp-15h]
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-11h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-Dh] BYREF
  DWORD v27; // [rsp+70h] [rbp-9h]
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v29; // [rsp+80h] [rbp+7h]
  HKEY phkResult; // [rsp+88h] [rbp+Fh] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp+17h] BYREF
  unsigned int v33; // [rsp+F8h] [rbp+7Fh]

  v3 = 0;
  hKey = 0;
  v33 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v29 = 0;
  if ( a3 && *a2 )
  {
    memset_0(a3, 0, 2LL * *a2);
    v33 = *a2;
    v29 = a3;
  }
  v7 = 0;
  v8 = PlaliConnectToRegistry(lpMachineName, &hKey, 1, 0);
  if ( !v8 )
  {
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v7 )
    {
      v9 = 2 * cbMaxSubKeyLen + 2;
      v27 = v9;
      ProcessHeap = GetProcessHeap();
      v11 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v9);
      if ( v11 )
      {
        for ( i = 0; ; ++i )
        {
          v24 = i;
          if ( i >= cSubKeys || v7 )
            break;
          lpMem = 0;
          v23 = 0;
          v7 = RegEnumKeyW(hKey, i, v11, v9 >> 1);
          if ( !v7 )
          {
            phkResult = 0;
            v7 = RegOpenKeyExW(hKey, v11, 0, 0x20019u, &phkResult);
            if ( !v7 )
            {
              v13 = PlaliReadRegistryStringValue(phkResult, L"Collection Name", 1u, (unsigned __int16 **)&lpMem, &v23);
              v14 = lpMem;
              v8 = v13;
              if ( v13 || !lpMem || v23 <= 2 )
              {
                v8 = 0;
                v15 = -1;
                do
                  ++v15;
                while ( v11[v15] );
                v16 = v11;
              }
              else
              {
                v15 = -1;
                do
                  ++v15;
                while ( *((_WORD *)lpMem + v15) );
                v16 = (const unsigned __int16 *)lpMem;
              }
              v23 = v15 + v3 + 1;
              v17 = (unsigned int)(v15 + 1);
              if ( v23 < (unsigned int)v17 )
              {
                v8 = -1073738814;
                goto LABEL_37;
              }
              if ( a3 && v23 < *a2 )
              {
                StringCchCopyW(v29, v33, v16);
                v33 += -1 - v15;
                v29 += v17;
              }
              if ( v14 )
              {
                v18 = GetProcessHeap();
                HeapFree(v18, 0, v14);
              }
              v9 = v27;
              v3 = v23;
              i = v24;
            }
            if ( phkResult )
              RegCloseKey(phkResult);
          }
        }
        v19 = GetProcessHeap();
        HeapFree(v19, 0, v11);
        if ( !v7 )
        {
          v20 = 0;
          v21 = v3 + 1 <= *a2;
          *a2 = v3 + 1;
          if ( !v21 )
            v20 = -1073738814;
          v8 = v20;
        }
      }
      else
      {
        v7 = 14;
      }
    }
  }
LABEL_37:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v8 )
    return v8;
  else
    return PlaliErrorToPdhStatus(v7);
}

```

## disassembly

```asm
0x18012f050  mov     [rsp-8+arg_0], rbx
0x18012f055  mov     [rsp-8+arg_10], r8
0x18012f05a  push    rbp
0x18012f05b  push    rsi
0x18012f05c  push    rdi
0x18012f05d  push    r12
0x18012f05f  push    r13
0x18012f061  push    r14
0x18012f063  push    r15
0x18012f065  lea     rbp, [rsp-27h]
0x18012f06a  sub     rsp, 0A0h
0x18012f071  xor     r13d, r13d
0x18012f074  mov     rdi, r8
0x18012f077  mov     [rbp+57h+hKey], r13
0x18012f07b  mov     r14, rdx
0x18012f07e  mov     dword ptr [rbp+57h+arg_18], r13d
0x18012f082  mov     rbx, rcx
0x18012f085  mov     [rbp+57h+cSubKeys], r13d
0x18012f089  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18012f08d  mov     [rbp+57h+var_50], r13
0x18012f091  test    r8, r8
0x18012f094  jz      short loc_18012F0B5
0x18012f096  cmp     [rdx], r13d
0x18012f099  jbe     short loc_18012F0B5
0x18012f09b  mov     r8d, [rdx]
0x18012f09e  mov     rcx, rdi; void *
0x18012f0a1  add     r8, r8; Size
0x18012f0a4  xor     edx, edx; Val
0x18012f0a6  call    memset_0
0x18012f0ab  mov     eax, [r14]
0x18012f0ae  mov     dword ptr [rbp+57h+arg_18], eax
0x18012f0b1  mov     [rbp+57h+var_50], rdi
0x18012f0b5  xor     r9d, r9d; int
0x18012f0b8  lea     rdx, [rbp+57h+hKey]; HKEY *
0x18012f0bc  mov     rcx, rbx; lpMachineName
0x18012f0bf  mov     esi, r13d
0x18012f0c2  lea     r8d, [r9+1]; int
0x18012f0c6  call    ?PlaliConnectToRegistry@@YAJPEBGAEAPEAUHKEY__@@HH@Z; PlaliConnectToRegistry(ushort const *,HKEY__ * &,int,int)
0x18012f0cb  mov     edi, eax
0x18012f0cd  test    eax, eax
0x18012f0cf  jnz     loc_18012F2DE
0x18012f0d5  mov     rcx, [rbp+57h+hKey]; hKey
0x18012f0d9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18012f0dd  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18012f0e2  xor     r9d, r9d; lpReserved
0x18012f0e5  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18012f0ea  xor     r8d, r8d; lpcchClass
0x18012f0ed  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18012f0f2  xor     edx, edx; lpClass
0x18012f0f4  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18012f0f9  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x18012f0fe  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18012f103  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18012f108  lea     rax, [rbp+57h+cSubKeys]
0x18012f10c  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x18012f111  call    cs:__imp_RegQueryInfoKeyW
0x18012f117  mov     esi, eax
0x18012f119  test    eax, eax
0x18012f11b  jnz     loc_18012F2DE
0x18012f121  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x18012f124  lea     r15d, ds:2[rcx*2]
0x18012f12c  mov     [rbp+57h+var_60], r15d
0x18012f130  call    cs:__imp_GetProcessHeap
0x18012f136  mov     r8d, r15d; dwBytes
0x18012f139  lea     edx, [rdi+8]; dwFlags
0x18012f13c  mov     rcx, rax; hHeap
0x18012f13f  call    cs:__imp_HeapAlloc
0x18012f145  mov     r12, rax
0x18012f148  test    rax, rax
0x18012f14b  jz      loc_18012F2D9
0x18012f151  xor     edx, edx
0x18012f153  mov     ebx, edx
0x18012f155  mov     [rbp+57h+var_6C], ebx
0x18012f158  cmp     ebx, [rbp+57h+cSubKeys]
0x18012f15b  jnb     loc_18012F2A9
0x18012f161  test    esi, esi
0x18012f163  jnz     loc_18012F2A9
0x18012f169  mov     rcx, [rbp+57h+hKey]; hKey
0x18012f16d  mov     r9d, r15d
0x18012f170  mov     [rbp+57h+lpMem], rdx
0x18012f174  mov     r8, r12; lpName
0x18012f177  mov     [rbp+57h+var_70], edx
0x18012f17a  mov     edx, ebx; dwIndex
0x18012f17c  shr     r9d, 1; cchName
0x18012f17f  call    cs:__imp_RegEnumKeyW
0x18012f185  xor     edx, edx
0x18012f187  mov     esi, eax
0x18012f189  test    eax, eax
0x18012f18b  jnz     loc_18012F29B
0x18012f191  mov     rcx, [rbp+57h+hKey]; hKey
0x18012f195  lea     rax, [rbp+57h+phkResult]
0x18012f199  mov     [rbp+57h+phkResult], rdx
0x18012f19d  mov     r9d, 20019h; samDesired
0x18012f1a3  mov     rdx, r12; lpSubKey
0x18012f1a6  mov     [rsp+0D0h+lpcSubKeys], rax; phkResult
0x18012f1ab  xor     r8d, r8d; ulOptions
0x18012f1ae  call    cs:__imp_RegOpenKeyExW
0x18012f1b4  xor     edx, edx
0x18012f1b6  mov     esi, eax
0x18012f1b8  test    eax, eax
0x18012f1ba  jnz     loc_18012F28A
0x18012f1c0  mov     rcx, [rbp+57h+phkResult]; hKey
0x18012f1c4  lea     rax, [rbp+57h+var_70]
0x18012f1c8  lea     r9, [rbp+57h+lpMem]; unsigned __int16 **
0x18012f1cc  mov     [rsp+0D0h+lpcSubKeys], rax; unsigned int *
0x18012f1d1  lea     r8d, [rsi+1]; unsigned int
0x18012f1d5  lea     rdx, aCollectionName; "Collection Name"
0x18012f1dc  call    ?PlaliReadRegistryStringValue@@YAJPEAUHKEY__@@PEBGKPEAPEAGPEAK@Z; PlaliReadRegistryStringValue(HKEY__ *,ushort const *,ulong,ushort * *,ulong *)
0x18012f1e1  mov     r15, [rbp+57h+lpMem]
0x18012f1e5  xor     edx, edx
0x18012f1e7  mov     edi, eax
0x18012f1e9  test    eax, eax
0x18012f1eb  jnz     short loc_18012F20B
0x18012f1ed  test    r15, r15
0x18012f1f0  jz      short loc_18012F20B
0x18012f1f2  cmp     [rbp+57h+var_70], 2
0x18012f1f6  jbe     short loc_18012F20B
0x18012f1f8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012f1fc  inc     rbx
0x18012f1ff  cmp     [r15+rbx*2], dx
0x18012f204  jnz     short loc_18012F1FC
0x18012f206  mov     r8, r15
0x18012f209  jmp     short loc_18012F21E
0x18012f20b  mov     edi, edx
0x18012f20d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18012f211  inc     rbx
0x18012f214  cmp     [r12+rbx*2], dx
0x18012f219  jnz     short loc_18012F211
0x18012f21b  mov     r8, r12; unsigned __int16 *
0x18012f21e  inc     r13d
0x18012f221  add     r13d, ebx
0x18012f224  mov     [rbp+57h+var_70], r13d
0x18012f228  lea     r13d, [rbx+1]
0x18012f22c  mov     eax, [rbp+57h+var_70]
0x18012f22f  cmp     eax, r13d
0x18012f232  jb      short loc_18012F2A2
0x18012f234  cmp     [rbp+57h+arg_10], rdx
0x18012f238  jz      short loc_18012F264
0x18012f23a  cmp     eax, [r14]
0x18012f23d  jnb     short loc_18012F264
0x18012f23f  mov     edx, dword ptr [rbp+57h+arg_18]; unsigned __int64
0x18012f242  mov     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x18012f246  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012f24b  mov     rcx, [rbp+57h+var_50]
0x18012f24f  or      r11d, 0FFFFFFFFh
0x18012f253  sub     r11d, ebx
0x18012f256  add     dword ptr [rbp+57h+arg_18], r11d
0x18012f25a  xor     edx, edx
0x18012f25c  lea     rcx, [rcx+r13*2]
0x18012f260  mov     [rbp+57h+var_50], rcx
0x18012f264  test    r15, r15
0x18012f267  jz      short loc_18012F27F
0x18012f269  call    cs:__imp_GetProcessHeap
0x18012f26f  mov     r8, r15; lpMem
0x18012f272  xor     edx, edx; dwFlags
0x18012f274  mov     rcx, rax; hHeap
0x18012f277  call    cs:__imp_HeapFree
0x18012f27d  xor     edx, edx
0x18012f27f  mov     r15d, [rbp+57h+var_60]
0x18012f283  mov     r13d, [rbp+57h+var_70]
0x18012f287  mov     ebx, [rbp+57h+var_6C]
0x18012f28a  mov     rcx, [rbp+57h+phkResult]; hKey
0x18012f28e  test    rcx, rcx
0x18012f291  jz      short loc_18012F29B
0x18012f293  call    cs:__imp_RegCloseKey
0x18012f299  xor     edx, edx
0x18012f29b  inc     ebx
0x18012f29d  jmp     loc_18012F155
0x18012f2a2  mov     edi, 0C0000BC2h
0x18012f2a7  jmp     short loc_18012F2DE
0x18012f2a9  call    cs:__imp_GetProcessHeap
0x18012f2af  mov     r8, r12; lpMem
0x18012f2b2  xor     edx, edx; dwFlags
0x18012f2b4  mov     rcx, rax; hHeap
0x18012f2b7  call    cs:__imp_HeapFree
0x18012f2bd  test    esi, esi
0x18012f2bf  jnz     short loc_18012F2DE
0x18012f2c1  mov     eax, edi
0x18012f2c3  lea     ecx, [r13+1]
0x18012f2c7  cmp     ecx, [r14]
0x18012f2ca  mov     edi, 0C0000BC2h
0x18012f2cf  mov     [r14], ecx
0x18012f2d2  cmova   eax, edi
0x18012f2d5  mov     edi, eax
0x18012f2d7  jmp     short loc_18012F2DE
0x18012f2d9  mov     esi, 0Eh
0x18012f2de  mov     rcx, [rbp+57h+hKey]; hKey
0x18012f2e2  test    rcx, rcx
0x18012f2e5  jz      short loc_18012F2ED
0x18012f2e7  call    cs:__imp_RegCloseKey
0x18012f2ed  test    edi, edi
0x18012f2ef  jnz     short loc_18012F2FA
0x18012f2f1  mov     ecx, esi; unsigned int
0x18012f2f3  call    ?PlaliErrorToPdhStatus@@YAJK@Z; PlaliErrorToPdhStatus(ulong)
0x18012f2f8  jmp     short loc_18012F2FC
0x18012f2fa  mov     eax, edi
0x18012f2fc  mov     rbx, [rsp+0D0h+arg_0]
0x18012f304  add     rsp, 0A0h
0x18012f30b  pop     r15
0x18012f30d  pop     r14
0x18012f30f  pop     r13
0x18012f311  pop     r12
0x18012f313  pop     rdi
0x18012f314  pop     rsi
0x18012f315  pop     rbp
0x18012f316  retn
```
