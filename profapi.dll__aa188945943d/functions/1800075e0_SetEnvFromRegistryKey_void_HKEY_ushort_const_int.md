# _SetEnvFromRegistryKey(void * *,HKEY__ *,ushort const *,int)

- ea: `0x1800075e0`
- end: `0x180007c4e`
- name: `?_SetEnvFromRegistryKey@@YAXPEAPEAXPEAUHKEY__@@PEBGH@Z`
- size: `1646`
- prototype: `void __fastcall(void **, HKEY, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006de0`
- `0x180007e40`

## callees

- `0x180004230`
- `0x1800075e0`
- `0x180007c60`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ba4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ba4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007740`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007af7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800076f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007740`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007af7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000772f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ae6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bb2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800078e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000790a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007934`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007975`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000799f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b4a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b74`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800078e0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000790a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007934`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007975`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000799f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b4a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b74`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007a96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007643`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007643`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800077c5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800077c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800076ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800076ae`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180007c00`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180007c00`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007836`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007898`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007836`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007898`
- `ntdll!RtlSetEnvironmentVar` at `0x1800079eb`
- `ntdll!RtlSetEnvironmentVar` at `0x1800079eb`
- `ntdll!RtlNtStatusToDosError` at `0x18000783e`
- `ntdll!RtlNtStatusToDosError` at `0x1800078a0`
- `ntdll!RtlNtStatusToDosError` at `0x1800079f3`
- `ntdll!RtlNtStatusToDosError` at `0x18000783e`
- `ntdll!RtlNtStatusToDosError` at `0x1800078a0`
- `ntdll!RtlNtStatusToDosError` at `0x1800079f3`

## string_xrefs

- `0x18000792a`: `Os2LibPath`
- `0x180007900`: `LibPath`

## pseudocode

```c
void __fastcall _SetEnvFromRegistryKey(void **a1, HKEY a2, const unsigned __int16 *a3, int a4)
{
  void **v4; // rsi
  int v5; // r14d
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS v8; // eax
  bool v9; // sf
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  BYTE *v12; // r15
  __int64 v13; // rax
  SIZE_T v14; // rbx
  HANDLE v15; // rax
  void *v16; // rdi
  int v17; // r13d
  DWORD v18; // r12d
  LSTATUS v19; // eax
  bool v20; // sf
  void *v21; // rsi
  __int64 v22; // r8
  NTSTATUS v23; // eax
  signed int v24; // eax
  signed int v25; // ebx
  SIZE_T v26; // rbx
  _WORD *v27; // r14
  NTSTATUS v28; // eax
  signed int v29; // eax
  int v30; // esi
  WCHAR *v31; // rbx
  __int64 v32; // rax
  __int64 v33; // r8
  NTSTATUS v34; // eax
  HANDLE v35; // rax
  HANDLE v36; // rax
  __int64 v37; // r8
  HANDLE v38; // rax
  __int64 v39; // r8
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-9Ch] BYREF
  int v42; // [rsp+70h] [rbp-98h]
  DWORD Type; // [rsp+74h] [rbp-94h] BYREF
  DWORD cValues[2]; // [rsp+78h] [rbp-90h] BYREF
  void **v45; // [rsp+80h] [rbp-88h]
  unsigned __int64 v46; // [rsp+88h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-78h] BYREF
  DWORD cbData; // [rsp+98h] [rbp-70h] BYREF
  DWORD cchValueName; // [rsp+9Ch] [rbp-6Ch] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v51; // [rsp+A8h] [rbp-60h]
  WCHAR szShortPath[264]; // [rsp+B8h] [rbp-50h] BYREF

  v4 = a1;
  v45 = a1;
  v5 = a4;
  v42 = a4;
  hKey = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    cValues[0] = 0;
    cbMaxValueNameLen = 0;
    cbMaxValueLen = 0;
    ftLastWriteTime = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, &ftLastWriteTime);
    v9 = v8 < 0;
    if ( v8 > 0 )
      v9 = 1;
    if ( !v9 && cbMaxValueLen + 2 >= cbMaxValueLen )
    {
      cbMaxValueLen += 2;
      v10 = cbMaxValueLen;
      ProcessHeap = GetProcessHeap();
      v12 = (BYTE *)HeapAlloc(ProcessHeap, 8u, v10 + 2);
      if ( v12 )
      {
        v46 = 0;
        v13 = 2LL * ++cbMaxValueNameLen;
        v14 = v13;
        if ( is_mul_ok(cbMaxValueNameLen, 2u) )
        {
          v15 = GetProcessHeap();
          v16 = HeapAlloc(v15, 8u, v14);
          if ( v16 )
          {
            v17 = 0;
            while ( 1 )
            {
              v18 = 0;
              if ( cValues[0] )
                break;
LABEL_50:
              if ( ++v17 >= 2 )
              {
                ResultFromHeapFree(v16);
                goto LABEL_52;
              }
            }
            while ( 1 )
            {
              cchValueName = cbMaxValueNameLen;
              cbData = cbMaxValueLen;
              Type = 0;
              v19 = RegEnumValueW(hKey, v18, (LPWSTR)v16, &cchValueName, 0, &Type, v12, &cbData);
              v20 = v19 < 0;
              if ( v19 > 0 )
                v20 = 1;
              if ( v20 )
                goto LABEL_50;
              if ( !v5
                || CompareStringOrdinal((LPCWCH)v16, -1, L"TEMP", -1, 1) != 2
                && CompareStringOrdinal((LPCWCH)v16, -1, L"TMP", -1, 1) != 2 )
              {
                break;
              }
LABEL_49:
              if ( ++v18 >= cValues[0] )
                goto LABEL_50;
            }
            if ( !v17 )
            {
              if ( Type != 1 )
                goto LABEL_49;
              v27 = v12;
              v30 = 0;
              goto LABEL_31;
            }
            if ( Type != 2 && v17 == 1 )
              goto LABEL_49;
            v21 = *v4;
            v22 = -1;
            v46 = 0;
            do
              ++v22;
            while ( *(_WORD *)&v12[2 * v22] );
            v23 = RtlExpandEnvironmentStrings(v21, v12, v22, 0, 0, &v46);
            v24 = RtlNtStatusToDosError(v23);
            v25 = v24;
            if ( v24 > 0 )
              v25 = (unsigned __int16)v24 | 0x80070000;
            if ( v25 != -2147024774 )
              goto LABEL_26;
            v51 = 0;
            v26 = 2 * v46;
            if ( !is_mul_ok(v46, 2u) )
            {
              v25 = -2147024362;
LABEL_26:
              v27 = 0;
              goto LABEL_30;
            }
            v36 = GetProcessHeap();
            v27 = HeapAlloc(v36, 8u, v26);
            v25 = -2147024882;
            if ( v27 )
            {
              v37 = -1;
              do
                ++v37;
              while ( *(_WORD *)&v12[2 * v37] );
              v28 = RtlExpandEnvironmentStrings(v21, v12, v37, v27, v46, &v46);
              v29 = RtlNtStatusToDosError(v28);
              v25 = v29;
              if ( v29 > 0 )
                v25 = (unsigned __int16)v29 | 0x80070000;
              if ( v25 < 0 )
              {
                v38 = GetProcessHeap();
                if ( HeapFree(v38, 0, v27) )
                  goto LABEL_26;
                GetLastError();
                v27 = 0;
              }
            }
LABEL_30:
            v30 = 1;
            if ( v25 < 0 )
            {
LABEL_45:
              if ( v27 )
              {
                v35 = GetProcessHeap();
                if ( !HeapFree(v35, 0, v27) )
                  GetLastError();
              }
LABEL_48:
              v5 = v42;
              v4 = v45;
              goto LABEL_49;
            }
LABEL_31:
            if ( CompareStringOrdinal((LPCWCH)v16, -1, L"Path", -1, 1) == 2
              || CompareStringOrdinal((LPCWCH)v16, -1, L"LibPath", -1, 1) == 2
              || CompareStringOrdinal((LPCWCH)v16, -1, L"Os2LibPath", -1, 1) == 2 )
            {
              _AppendEnvValue(v45, (const unsigned __int16 *)v16, v27);
            }
            else
            {
              if ( v27 && *v27 )
              {
                v31 = v27;
                if ( (CompareStringOrdinal((LPCWCH)v16, -1, L"TEMP", -1, 1) == 2
                   || CompareStringOrdinal((LPCWCH)v16, -1, L"TMP", -1, 1) == 2)
                  && GetShortPathNameW(v27, szShortPath, 0x104u) - 1 <= 0x102 )
                {
                  v31 = szShortPath;
                }
                v32 = -1;
                do
                  ++v32;
                while ( v31[v32] );
                v33 = -1;
                do
                  ++v33;
                while ( *((_WORD *)v16 + v33) );
                v34 = RtlSetEnvironmentVar(v45, v16, v33, v31, v32);
              }
              else
              {
                v39 = -1;
                do
                  ++v39;
                while ( *((_WORD *)v16 + v39) );
                v34 = RtlSetEnvironmentVar(v45, v16, v39, 0, 0);
              }
              RtlNtStatusToDosError(v34);
            }
            if ( !v30 )
              goto LABEL_48;
            goto LABEL_45;
          }
        }
LABEL_52:
        ResultFromHeapFree(v12);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800075e0  mov     r11, rsp
0x1800075e3  push    rbp
0x1800075e4  lea     rbp, [r11-208h]
0x1800075eb  sub     rsp, 300h
0x1800075f2  mov     rax, cs:__security_cookie
0x1800075f9  xor     rax, rsp
0x1800075fc  mov     [rbp+200h+var_40], rax
0x180007603  mov     [r11-10h], rsi
0x180007607  mov     r10, r8
0x18000760a  mov     rsi, rcx
0x18000760d  mov     [rsp+300h+var_288], rcx
0x180007612  mov     [r11-18h], rdi
0x180007616  lea     rcx, [rbp+200h+hKey]
0x18000761a  mov     rax, rdx
0x18000761d  mov     [r11-30h], r14
0x180007621  mov     [rsp+300h+phkResult], rcx; phkResult
0x180007626  mov     r14d, r9d
0x180007629  mov     [rsp+300h+var_298], r9d
0x18000762e  xor     edi, edi
0x180007630  mov     rcx, rax; hKey
0x180007633  mov     [rbp+200h+hKey], rdi
0x180007637  mov     r9d, 20019h; samDesired
0x18000763d  xor     r8d, r8d; ulOptions
0x180007640  mov     rdx, r10; lpSubKey
0x180007643  call    cs:__imp_RegOpenKeyExW
0x180007649  test    eax, eax
0x18000764b  jg      loc_180007BD5
0x180007651  js      loc_180007A75
0x180007657  mov     rcx, [rbp+200h+hKey]; hKey
0x18000765b  lea     rax, [rbp+200h+ftLastWriteTime]
0x18000765f  mov     [rsp+300h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180007664  xor     r9d, r9d; lpReserved
0x180007667  mov     [rsp+300h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18000766c  lea     rax, [rsp+300h+cbMaxValueLen]
0x180007671  mov     [rsp+300h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180007676  xor     r8d, r8d; lpcchClass
0x180007679  lea     rax, [rsp+300h+cbMaxValueNameLen]
0x18000767e  mov     [rsp+300h+cValues], edi
0x180007682  mov     [rsp+300h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180007687  xor     edx, edx; lpClass
0x180007689  lea     rax, [rsp+300h+cValues]
0x18000768e  mov     [rsp+300h+cbMaxValueNameLen], edi
0x180007692  mov     [rsp+300h+lpcValues], rax; lpcValues
0x180007697  mov     [rsp+300h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18000769c  mov     [rsp+300h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x1800076a1  mov     [rsp+300h+phkResult], rdi; lpcSubKeys
0x1800076a6  mov     [rsp+300h+cbMaxValueLen], edi
0x1800076aa  mov     qword ptr [rbp+200h+ftLastWriteTime.dwLowDateTime], rdi
0x1800076ae  call    cs:__imp_RegQueryInfoKeyW
0x1800076b4  test    eax, eax
0x1800076b6  jg      loc_180007BE4
0x1800076bc  js      loc_180007A75
0x1800076c2  mov     eax, [rsp+300h+cbMaxValueLen]
0x1800076c6  lea     ecx, [rax+2]
0x1800076c9  cmp     ecx, eax
0x1800076cb  jb      loc_180007A75
0x1800076d1  mov     [rsp+300h+arg_18], rbx
0x1800076d9  mov     [rsp+300h+var_30], r15
0x1800076e1  mov     ebx, ecx
0x1800076e3  mov     [rsp+300h+cbMaxValueLen], ecx
0x1800076e7  call    cs:__imp_GetProcessHeap
0x1800076ed  lea     r8, [rbx+2]; dwBytes
0x1800076f1  mov     edx, 8; dwFlags
0x1800076f6  mov     rcx, rax; hHeap
0x1800076f9  call    cs:__imp_HeapAlloc
0x1800076ff  mov     r15, rax
0x180007702  test    rax, rax
0x180007705  jz      loc_180007A65
0x18000770b  mov     ecx, [rsp+300h+cbMaxValueNameLen]
0x18000770f  mov     eax, 2
0x180007714  inc     ecx
0x180007716  mov     [rbp+200h+var_280], rdi
0x18000771a  mov     edx, ecx
0x18000771c  mul     rdx
0x18000771f  mov     [rsp+300h+cbMaxValueNameLen], ecx
0x180007723  mov     rbx, rax
0x180007726  test    rdx, rdx
0x180007729  jnz     loc_180007A5D
0x18000772f  call    cs:__imp_GetProcessHeap
0x180007735  mov     r8, rbx; dwBytes
0x180007738  mov     edx, 8; dwFlags
0x18000773d  mov     rcx, rax; hHeap
0x180007740  call    cs:__imp_HeapAlloc
0x180007746  mov     rdi, rax
0x180007749  test    rax, rax
0x18000774c  jz      loc_180007A5D
0x180007752  mov     [rsp+300h+var_18], r12
0x18000775a  mov     [rsp+300h+var_20], r13
0x180007762  xor     r13d, r13d
0x180007765  xor     r12d, r12d
0x180007768  cmp     [rsp+300h+cValues], r12d
0x18000776d  jbe     loc_180007A38
0x180007773  nop     dword ptr [rax+00h]
0x180007777  nop     word ptr [rax+rax+00000000h]
0x180007780  mov     eax, [rsp+300h+cbMaxValueNameLen]
0x180007784  lea     r9, [rbp+200h+cchValueName]; lpcchValueName
0x180007788  mov     rcx, [rbp+200h+hKey]; hKey
0x18000778c  mov     r8, rdi; lpValueName
0x18000778f  mov     [rbp+200h+cchValueName], eax
0x180007792  mov     edx, r12d; dwIndex
0x180007795  mov     eax, [rsp+300h+cbMaxValueLen]
0x180007799  mov     [rbp+200h+cbData], eax
0x18000779c  lea     rax, [rbp+200h+cbData]
0x1800077a0  mov     [rsp+300h+lpcValues], rax; lpcbData
0x1800077a5  lea     rax, [rsp+300h+Type]
0x1800077aa  mov     [rsp+300h+lpcbMaxClassLen], r15; lpData
0x1800077af  mov     [rsp+300h+lpcbMaxSubKeyLen], rax; lpType
0x1800077b4  mov     [rsp+300h+phkResult], 0; lpReserved
0x1800077bd  mov     [rsp+300h+Type], 0
0x1800077c5  call    cs:__imp_RegEnumValueW
0x1800077cb  test    eax, eax
0x1800077cd  jg      loc_180007AD7
0x1800077d3  js      loc_180007A38
0x1800077d9  test    r14d, r14d
0x1800077dc  jnz     loc_180007B2F
0x1800077e2  test    r13d, r13d
0x1800077e5  jz      loc_180007AC2
0x1800077eb  cmp     [rsp+300h+Type], 2
0x1800077f0  jnz     loc_180007C3F
0x1800077f6  mov     rsi, [rsi]
0x1800077f9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180007800  mov     [rbp+200h+var_280], 0
0x180007808  nop     dword ptr [rax+rax+00000000h]
0x180007810  inc     r8
0x180007813  cmp     word ptr [r15+r8*2], 0
0x180007819  jnz     short loc_180007810
0x18000781b  lea     rax, [rbp+200h+var_280]
0x18000781f  xor     r9d, r9d
0x180007822  mov     [rsp+300h+lpcbMaxSubKeyLen], rax
0x180007827  mov     rdx, r15
0x18000782a  mov     rcx, rsi
0x18000782d  mov     [rsp+300h+phkResult], 0
0x180007836  call    cs:__imp_RtlExpandEnvironmentStrings
0x18000783c  mov     ecx, eax; Status
0x18000783e  call    cs:__imp_RtlNtStatusToDosError
0x180007844  mov     ebx, eax
0x180007846  test    eax, eax
0x180007848  jg      loc_180007B88
0x18000784e  cmp     ebx, 8007007Ah
0x180007854  jnz     short loc_180007878
0x180007856  mov     eax, 2
0x18000785b  mov     [rbp+200h+var_260], 0
0x180007863  mul     [rbp+200h+var_280]
0x180007867  mov     rbx, rax
0x18000786a  test    rdx, rdx
0x18000786d  jz      loc_180007AE6
0x180007873  mov     ebx, 80070216h
0x180007878  xor     r14d, r14d
0x18000787b  jmp     short loc_1800078B8
0x18000787d  lea     rax, [rbp+200h+var_280]
0x180007881  mov     r9, r14
0x180007884  mov     [rsp+300h+lpcbMaxSubKeyLen], rax
0x180007889  mov     rdx, r15
0x18000788c  mov     rax, [rbp+200h+var_280]
0x180007890  mov     rcx, rsi
0x180007893  mov     [rsp+300h+phkResult], rax
0x180007898  call    cs:__imp_RtlExpandEnvironmentStrings
0x18000789e  mov     ecx, eax; Status
0x1800078a0  call    cs:__imp_RtlNtStatusToDosError
0x1800078a6  mov     ebx, eax
0x1800078a8  test    eax, eax
0x1800078aa  jg      loc_180007AB4
0x1800078b0  test    ebx, ebx
0x1800078b2  js      loc_180007B96
0x1800078b8  mov     esi, 1
0x1800078bd  test    ebx, ebx
0x1800078bf  js      loc_1800079FD
0x1800078c5  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800078cb  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
0x1800078d3  mov     edx, r9d; cchCount1
0x1800078d6  lea     r8, aPath; "Path"
0x1800078dd  mov     rcx, rdi; lpString1
0x1800078e0  call    cs:__imp_CompareStringOrdinal
0x1800078e6  cmp     eax, 2
0x1800078e9  jz      loc_180007BC0
0x1800078ef  mov     r9d, 0FFFFFFFFh; cchCount2
0x1800078f5  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
0x1800078fd  mov     edx, r9d; cchCount1
0x180007900  lea     r8, aLibpath; "LibPath"
0x180007907  mov     rcx, rdi; lpString1
0x18000790a  call    cs:__imp_CompareStringOrdinal
0x180007910  cmp     eax, 2
0x180007913  jz      loc_180007BC0
0x180007919  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000791f  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
0x180007927  mov     edx, r9d; cchCount1
0x18000792a  lea     r8, aOs2libpath; "Os2LibPath"
0x180007931  mov     rcx, rdi; lpString1
0x180007934  call    cs:__imp_CompareStringOrdinal
0x18000793a  cmp     eax, 2
0x18000793d  jz      loc_180007BC0
0x180007943  test    r14, r14
0x180007946  jz      loc_180007C1C
0x18000794c  cmp     word ptr [r14], 0
0x180007951  jz      loc_180007C1C
0x180007957  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000795d  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
0x180007965  mov     edx, r9d; cchCount1
0x180007968  lea     r8, String2; "TEMP"
0x18000796f  mov     rcx, rdi; lpString1
0x180007972  mov     rbx, r14
0x180007975  call    cs:__imp_CompareStringOrdinal
0x18000797b  cmp     eax, 2
0x18000797e  jz      loc_180007BF3
0x180007984  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000798a  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
0x180007992  mov     edx, r9d; cchCount1
0x180007995  lea     r8, aTmp; "TMP"
0x18000799c  mov     rcx, rdi; lpString1
0x18000799f  call    cs:__imp_CompareStringOrdinal
0x1800079a5  cmp     eax, 2
0x1800079a8  jz      loc_180007BF3
0x1800079ae  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800079b5  inc     rax
0x1800079b8  cmp     word ptr [rbx+rax*2], 0
0x1800079bd  jnz     short loc_1800079B5
0x1800079bf  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800079c6  nop     word ptr [rax+rax+00000000h]
0x1800079d0  inc     r8
0x1800079d3  cmp     word ptr [rdi+r8*2], 0
0x1800079d9  jnz     short loc_1800079D0
0x1800079db  mov     [rsp+300h+phkResult], rax
0x1800079e0  mov     r9, rbx
0x1800079e3  mov     rcx, [rsp+300h+var_288]
0x1800079e8  mov     rdx, rdi
0x1800079eb  call    cs:__imp_RtlSetEnvironmentVar
0x1800079f1  mov     ecx, eax; Status
0x1800079f3  call    cs:__imp_RtlNtStatusToDosError
0x1800079f9  test    esi, esi
0x1800079fb  jz      short loc_180007A20
0x1800079fd  test    r14, r14
0x180007a00  jz      short loc_180007A20
0x180007a02  call    cs:__imp_GetProcessHeap
0x180007a08  mov     r8, r14; lpMem
0x180007a0b  xor     edx, edx; dwFlags
0x180007a0d  mov     rcx, rax; hHeap
0x180007a10  call    cs:__imp_HeapFree
0x180007a16  test    eax, eax
0x180007a18  jnz     short loc_180007A20
0x180007a1a  call    cs:__imp_GetLastError
0x180007a20  mov     r14d, [rsp+300h+var_298]
0x180007a25  mov     rsi, [rsp+300h+var_288]
0x180007a2a  inc     r12d
0x180007a2d  cmp     r12d, [rsp+300h+cValues]
0x180007a32  jb      loc_180007780
0x180007a38  inc     r13d
0x180007a3b  cmp     r13d, 2
0x180007a3f  jl      loc_180007765
0x180007a45  mov     r13, [rsp+300h+var_20]
0x180007a4d  mov     rcx, rdi; lpMem
0x180007a50  mov     r12, [rsp+300h+var_18]
0x180007a58  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180007a5d  mov     rcx, r15; lpMem
0x180007a60  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x180007a65  mov     rbx, [rsp+300h+arg_18]
0x180007a6d  mov     r15, [rsp+300h+var_30]
0x180007a75  mov     rcx, [rbp+200h+hKey]; hKey
0x180007a79  mov     r14, [rsp+300h+var_28]
0x180007a81  mov     rdi, [rsp+300h+var_10]
0x180007a89  mov     rsi, [rsp+2F8h]
0x180007a91  test    rcx, rcx
0x180007a94  jz      short loc_180007A9C
0x180007a96  call    cs:__imp_RegCloseKey
0x180007a9c  mov     rcx, [rbp+200h+var_40]
0x180007aa3  xor     rcx, rsp; StackCookie
0x180007aa6  call    __security_check_cookie
0x180007aab  add     rsp, 300h
0x180007ab2  pop     rbp
0x180007ab3  retn
0x180007ab4  movzx   ebx, ax
0x180007ab7  or      ebx, 80070000h
0x180007abd  jmp     loc_1800078B0
0x180007ac2  cmp     [rsp+300h+Type], 1
0x180007ac7  jnz     loc_180007A2A
0x180007acd  mov     r14, r15
0x180007ad0  xor     esi, esi
0x180007ad2  jmp     loc_1800078C5
0x180007ad7  movzx   eax, ax
0x180007ada  or      eax, 80070000h
0x180007adf  test    eax, eax
0x180007ae1  jmp     loc_1800077D3
0x180007ae6  call    cs:__imp_GetProcessHeap
0x180007aec  mov     r8, rbx; dwBytes
0x180007aef  mov     edx, 8; dwFlags
0x180007af4  mov     rcx, rax; hHeap
0x180007af7  call    cs:__imp_HeapAlloc
0x180007afd  mov     r14, rax
0x180007b00  mov     ebx, 8007000Eh
0x180007b05  xor     eax, eax
0x180007b07  test    r14, r14
0x180007b0a  cmovnz  ebx, eax
0x180007b0d  jz      loc_1800078B8
0x180007b13  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180007b1a  nop     word ptr [rax+rax+00h]
0x180007b20  inc     r8
0x180007b23  cmp     [r15+r8*2], ax
0x180007b28  jnz     short loc_180007B20
0x180007b2a  jmp     loc_18000787D
0x180007b2f  mov     r9d, 0FFFFFFFFh; cchCount2
0x180007b35  mov     dword ptr [rsp+300h+phkResult], 1; bIgnoreCase
  ... truncated ...
```
