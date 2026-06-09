# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800091f0`
- end: `0x180009482`
- name: `?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z`
- size: `658`
- prototype: `int __fastcall(__int64, HKEY, const WCHAR *, const WCHAR *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001d3c`
- `0x180008910`
- `0x180009120`
- `0x180009d10`

## callees

- `0x1800091f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000938a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009477`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000938a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800093fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009477`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009346`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800092c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009338`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000937c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009338`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000937c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800093ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009469`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009405`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009227`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009227`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009279`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009279`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800092f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009327`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009361`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009327`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009361`

## pseudocode

```c
int __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
        __int64 a1,
        HKEY a2,
        const WCHAR *a3,
        const WCHAR *a4)
{
  int result; // eax
  bool v7; // sf
  HKEY v8; // rsi
  BYTE *v9; // rbx
  LSTATUS v10; // eax
  signed int v11; // edi
  DWORD v12; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS v14; // eax
  __int64 v15; // rsi
  DWORD v16; // ebp
  HANDLE v17; // rax
  WCHAR *v18; // rax
  WCHAR *v19; // r15
  DWORD v20; // eax
  DWORD v21; // esi
  HANDLE v22; // rax
  void *v23; // rbp
  HANDLE v24; // rax
  __int64 v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  result = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
  {
    v8 = hKey;
    v9 = 0;
    Type = 0;
    cbData = 0;
    v10 = RegQueryValueExW(hKey, a4, 0, &Type, 0, &cbData);
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    if ( v11 < 0 )
      goto LABEL_27;
    if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
    {
LABEL_30:
      v11 = -2147024883;
      goto LABEL_27;
    }
    v12 = cbData;
    ProcessHeap = GetProcessHeap();
    v9 = (BYTE *)HeapAlloc(ProcessHeap, 0, v12);
    if ( v9 )
    {
      v14 = RegQueryValueExW(v8, a4, 0, &Type, v9, &cbData);
      v11 = v14;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_27;
      v15 = (cbData >> 1) - 1;
      if ( Type != 2 || (v16 = ExpandEnvironmentStringsW((LPCWSTR)v9, 0, 0)) == 0 )
      {
LABEL_20:
        if ( !*(_WORD *)&v9[2 * v15] )
        {
          v23 = *(void **)a1;
          if ( *(_QWORD *)a1 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, v23);
            *(_QWORD *)a1 = 0;
          }
          *(_QWORD *)(a1 + 8) = 0;
          *(_QWORD *)(a1 + 16) = 0;
          if ( v9 )
          {
            v25 = (unsigned int)(v15 + 1);
            if ( (_DWORD)v15 != -1 )
            {
              *(_QWORD *)a1 = v9;
              *(_QWORD *)(a1 + 8) = v25 - 1;
              *(_QWORD *)(a1 + 16) = (unsigned int)v25;
              *(_WORD *)&v9[2 * (unsigned int)v25 - 2] = 0;
            }
          }
          v9 = 0;
          goto LABEL_27;
        }
        goto LABEL_30;
      }
      v17 = GetProcessHeap();
      v18 = (WCHAR *)HeapAlloc(v17, 0, 2LL * v16);
      v19 = v18;
      if ( v18 )
      {
        v20 = ExpandEnvironmentStringsW((LPCWSTR)v9, v18, v16);
        v21 = v20;
        if ( !v20 || v20 > v16 )
        {
          v11 = -2147024774;
          v27 = GetProcessHeap();
          HeapFree(v27, 0, v19);
          goto LABEL_27;
        }
        v11 = 0;
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v9);
        v15 = v21 - 1;
        v9 = (BYTE *)v19;
        goto LABEL_20;
      }
    }
    v11 = -2147024882;
LABEL_27:
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v9);
    RegCloseKey(hKey);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800091f0  push    rbp
0x1800091f2  push    r12
0x1800091f4  push    r14
0x1800091f6  sub     rsp, 40h
0x1800091fa  mov     r14, rcx
0x1800091fd  mov     rax, r8
0x180009200  mov     r10, rdx
0x180009203  lea     rcx, [rsp+58h+hKey]
0x180009208  mov     [rsp+58h+phkResult], rcx; phkResult
0x18000920d  mov     rbp, r9
0x180009210  xor     r12d, r12d
0x180009213  mov     rcx, r10; hKey
0x180009216  mov     r9d, 20019h; samDesired
0x18000921c  mov     [rsp+58h+hKey], r12
0x180009221  xor     r8d, r8d; ulOptions
0x180009224  mov     rdx, rax; lpSubKey
0x180009227  call    cs:__imp_RegOpenKeyExW
0x18000922d  test    eax, eax
0x18000922f  jg      loc_180009432
0x180009235  js      loc_180009421
0x18000923b  mov     [rsp+58h+arg_0], rbx
0x180009240  lea     rax, [rsp+58h+cbData]
0x180009245  mov     [rsp+58h+arg_8], rsi
0x18000924a  lea     r9, [rsp+58h+Type]; lpType
0x18000924f  mov     rsi, [rsp+58h+hKey]
0x180009254  xor     r8d, r8d; lpReserved
0x180009257  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000925c  mov     rcx, rsi; hKey
0x18000925f  mov     rdx, rbp; lpValueName
0x180009262  mov     [rsp+58h+arg_10], rdi
0x180009267  mov     rbx, r12
0x18000926a  mov     [rsp+58h+Type], r12d
0x18000926f  mov     [rsp+58h+cbData], r12d
0x180009274  mov     [rsp+58h+phkResult], r12; lpData
0x180009279  call    cs:__imp_RegQueryValueExW
0x18000927f  mov     edi, eax
0x180009281  test    eax, eax
0x180009283  jg      loc_180009441
0x180009289  mov     [rsp+58h+arg_18], r15
0x18000928e  test    edi, edi
0x180009290  js      loc_1800093EC
0x180009296  mov     eax, [rsp+58h+Type]
0x18000929a  dec     eax
0x18000929c  cmp     eax, 1
0x18000929f  ja      loc_18000945D
0x1800092a5  mov     eax, [rsp+58h+cbData]
0x1800092a9  test    eax, eax
0x1800092ab  jz      loc_18000945D
0x1800092b1  test    al, 1
0x1800092b3  jnz     loc_18000945D
0x1800092b9  mov     ebx, eax
0x1800092bb  call    cs:__imp_GetProcessHeap
0x1800092c1  mov     r8d, ebx; dwBytes
0x1800092c4  xor     edx, edx; dwFlags
0x1800092c6  mov     rcx, rax; hHeap
0x1800092c9  call    cs:__imp_HeapAlloc
0x1800092cf  mov     rbx, rax
0x1800092d2  test    rax, rax
0x1800092d5  jz      loc_18000942B
0x1800092db  lea     rax, [rsp+58h+cbData]
0x1800092e0  xor     r8d, r8d; lpReserved
0x1800092e3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800092e8  lea     r9, [rsp+58h+Type]; lpType
0x1800092ed  mov     rdx, rbp; lpValueName
0x1800092f0  mov     [rsp+58h+phkResult], rbx; lpData
0x1800092f5  mov     rcx, rsi; hKey
0x1800092f8  call    cs:__imp_RegQueryValueExW
0x1800092fe  mov     edi, eax
0x180009300  test    eax, eax
0x180009302  jg      loc_18000944F
0x180009308  test    edi, edi
0x18000930a  js      loc_1800093EC
0x180009310  mov     esi, [rsp+58h+cbData]
0x180009314  shr     esi, 1
0x180009316  dec     esi
0x180009318  cmp     [rsp+58h+Type], 2
0x18000931d  jnz     short loc_180009395
0x18000931f  xor     r8d, r8d; nSize
0x180009322  xor     edx, edx; lpDst
0x180009324  mov     rcx, rbx; lpSrc
0x180009327  call    cs:__imp_ExpandEnvironmentStringsW
0x18000932d  mov     ebp, eax
0x18000932f  test    eax, eax
0x180009331  jz      short loc_180009395
0x180009333  mov     edi, ebp
0x180009335  add     rdi, rdi
0x180009338  call    cs:__imp_GetProcessHeap
0x18000933e  mov     r8, rdi; dwBytes
0x180009341  xor     edx, edx; dwFlags
0x180009343  mov     rcx, rax; hHeap
0x180009346  call    cs:__imp_HeapAlloc
0x18000934c  mov     r15, rax
0x18000934f  test    rax, rax
0x180009352  jz      loc_18000942B
0x180009358  mov     r8d, ebp; nSize
0x18000935b  mov     rdx, rax; lpDst
0x18000935e  mov     rcx, rbx; lpSrc
0x180009361  call    cs:__imp_ExpandEnvironmentStringsW
0x180009367  mov     esi, eax
0x180009369  test    eax, eax
0x18000936b  jz      loc_180009464
0x180009371  cmp     eax, ebp
0x180009373  ja      loc_180009464
0x180009379  mov     edi, r12d
0x18000937c  call    cs:__imp_GetProcessHeap
0x180009382  mov     r8, rbx; lpMem
0x180009385  xor     edx, edx; dwFlags
0x180009387  mov     rcx, rax; hHeap
0x18000938a  call    cs:__imp_HeapFree
0x180009390  dec     esi
0x180009392  mov     rbx, r15
0x180009395  cmp     [rbx+rsi*2], r12w
0x18000939a  jnz     loc_18000945D
0x1800093a0  mov     rbp, [r14]
0x1800093a3  test    rbp, rbp
0x1800093a6  jz      short loc_1800093BF
0x1800093a8  call    cs:__imp_GetProcessHeap
0x1800093ae  mov     r8, rbp; lpMem
0x1800093b1  xor     edx, edx; dwFlags
0x1800093b3  mov     rcx, rax; hHeap
0x1800093b6  call    cs:__imp_HeapFree
0x1800093bc  mov     [r14], r12
0x1800093bf  mov     [r14+8], r12
0x1800093c3  mov     [r14+10h], r12
0x1800093c7  test    rbx, rbx
0x1800093ca  jz      short loc_1800093E9
0x1800093cc  lea     eax, [rsi+1]
0x1800093cf  mov     ecx, eax
0x1800093d1  test    eax, eax
0x1800093d3  jz      short loc_1800093E9
0x1800093d5  dec     rax
0x1800093d8  mov     [r14], rbx
0x1800093db  mov     [r14+8], rax
0x1800093df  mov     [r14+10h], rcx
0x1800093e3  mov     [rbx+rcx*2-2], r12w
0x1800093e9  mov     rbx, r12
0x1800093ec  call    cs:__imp_GetProcessHeap
0x1800093f2  mov     r8, rbx; lpMem
0x1800093f5  xor     edx, edx; dwFlags
0x1800093f7  mov     rcx, rax; hHeap
0x1800093fa  call    cs:__imp_HeapFree
0x180009400  mov     rcx, [rsp+58h+hKey]; hKey
0x180009405  call    cs:__imp_RegCloseKey
0x18000940b  mov     r15, [rsp+58h+arg_18]
0x180009410  mov     eax, edi
0x180009412  mov     rdi, [rsp+58h+arg_10]
0x180009417  mov     rsi, [rsp+58h+arg_8]
0x18000941c  mov     rbx, [rsp+58h+arg_0]
0x180009421  add     rsp, 40h
0x180009425  pop     r14
0x180009427  pop     r12
0x180009429  pop     rbp
0x18000942a  retn
0x18000942b  mov     edi, 8007000Eh
0x180009430  jmp     short loc_1800093EC
0x180009432  movzx   eax, ax
0x180009435  or      eax, 80070000h
0x18000943a  test    eax, eax
0x18000943c  jmp     loc_180009235
0x180009441  movzx   edi, ax
0x180009444  or      edi, 80070000h
0x18000944a  jmp     loc_180009289
0x18000944f  movzx   edi, ax
0x180009452  or      edi, 80070000h
0x180009458  jmp     loc_180009308
0x18000945d  mov     edi, 8007000Dh
0x180009462  jmp     short loc_1800093EC
0x180009464  mov     edi, 8007007Ah
0x180009469  call    cs:__imp_GetProcessHeap
0x18000946f  mov     r8, r15; lpMem
0x180009472  xor     edx, edx; dwFlags
0x180009474  mov     rcx, rax; hHeap
0x180009477  call    cs:__imp_HeapFree
0x18000947d  jmp     loc_1800093EC
```
