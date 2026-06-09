# AppendSpecificPropertyPages(tagCAUUID *,ulong,_GUID *,ushort *,HKEY__ *)

- ea: `0x100206a3`
- end: `0x100208ee`
- name: `?AppendSpecificPropertyPages@@YGXPAUtagCAUUID@@KPAU_GUID@@PAGPAUHKEY__@@@Z`
- size: `587`
- prototype: `void __userpurge(int@<edx>, int@<ecx>, struct tagCAUUID *, unsigned int, HKEY hKey, unsigned __int16 *, HKEY)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x10009a20`
- `0x100208f4`

## callees

- `0x10006937`
- `0x100206a3`
- `0x1003aba0`
- `0x1003bcf8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x100207d1`
- `ADVAPI32!RegQueryValueExW` at `0x100207d1`
- `ADVAPI32!RegCloseKey` at `0x100208b8`
- `ADVAPI32!RegCloseKey` at `0x100208d7`
- `ADVAPI32!RegCloseKey` at `0x100208b8`
- `ADVAPI32!RegCloseKey` at `0x100208d7`
- `ADVAPI32!RegOpenKeyExW` at `0x100206e8`
- `ADVAPI32!RegOpenKeyExW` at `0x10020768`
- `ADVAPI32!RegOpenKeyExW` at `0x100206e8`
- `ADVAPI32!RegOpenKeyExW` at `0x10020768`
- `ADVAPI32!RegEnumKeyW` at `0x10020794`
- `ADVAPI32!RegEnumKeyW` at `0x1002089e`
- `ADVAPI32!RegEnumKeyW` at `0x10020794`
- `ADVAPI32!RegEnumKeyW` at `0x1002089e`
- `ole32!CoTaskMemAlloc` at `0x10020837`
- `ole32!CoTaskMemAlloc` at `0x10020837`
- `ole32!StringFromGUID2` at `0x10020722`
- `ole32!StringFromGUID2` at `0x10020722`
- `ole32!CoTaskMemFree` at `0x1002085c`
- `ole32!CoTaskMemFree` at `0x1002085c`
- `ole32!IIDFromString` at `0x100207e6`
- `ole32!IIDFromString` at `0x100207e6`

## pseudocode

```c
void __userpurge AppendSpecificPropertyPages(
        int a1@<edx>,
        int a2@<ecx>,
        struct tagCAUUID *a3,
        unsigned int a4,
        HKEY hKey,
        unsigned __int16 *a6,
        HKEY a7)
{
  struct tagCAUUID *v7; // edi
  HKEY v10; // eax
  unsigned int v11; // esi
  unsigned int v12; // ecx
  int i; // edi
  int v14; // edx
  char *v15; // eax
  char *v16; // esi
  unsigned int *v17; // edi
  int v18; // [esp+10h] [ebp-2D4h]
  DWORD cbData; // [esp+14h] [ebp-2D0h] BYREF
  unsigned int v20; // [esp+18h] [ebp-2CCh]
  DWORD v21; // [esp+1Ch] [ebp-2C8h]
  HKEY v22; // [esp+20h] [ebp-2C4h] BYREF
  HKEY phkResult; // [esp+24h] [ebp-2C0h] BYREF
  GUID Data; // [esp+28h] [ebp-2BCh] BYREF
  WCHAR SubKey[256]; // [esp+38h] [ebp-2ACh] BYREF
  OLECHAR sz[40]; // [esp+238h] [ebp-ACh] BYREF
  WCHAR Name[42]; // [esp+288h] [ebp-5Ch] BYREF

  v7 = a3;
  v20 = a4;
  if ( RegOpenKeyExW(hKey, L"PageAliases", 0, 0x20019u, &phkResult) )
  {
    v10 = 0;
    phkResult = 0;
  }
  else
  {
    v10 = phkResult;
  }
  if ( a1 )
  {
    do
    {
      v18 = --a1;
      StringFromGUID2((const GUID *const)&v7[2 * a1], sz, 39);
      StringCchPrintfW(SubKey, 0x100u, L"%s\\%s\\PropertyPages", v20, sz);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &v22) )
      {
        v21 = 0;
        memset(&Data, 0, sizeof(Data));
        if ( !RegEnumKeyW(v22, 0, Name, 0x28u) )
        {
          do
          {
            if ( !phkResult || (cbData = 16, RegQueryValueExW(phkResult, Name, 0, 0, (LPBYTE)&Data, &cbData)) )
              IIDFromString(Name, &Data);
            v11 = *(_DWORD *)a2;
            v12 = *(_DWORD *)a2;
            for ( i = *(_DWORD *)(a2 + 4); v12; --v12 )
            {
              v14 = 0;
              while ( *(&Data.Data1 + v14) == *(_DWORD *)(i + 4 * v14) )
              {
                if ( ++v14 == 4 )
                  goto LABEL_22;
              }
              i += 16;
            }
            if ( v11 + 1 < v11 )
              break;
            if ( !is_mul_ok(0x10u, v11 + 1) )
              break;
            v15 = (char *)CoTaskMemAlloc(16 * (v11 + 1));
            v16 = v15;
            if ( !v15 )
              break;
            if ( *(_DWORD *)a2 )
            {
              memcpy(v15, *(const void **)(a2 + 4), 16 * *(_DWORD *)a2);
              CoTaskMemFree(*(LPVOID *)(a2 + 4));
            }
            v17 = (unsigned int *)&v16[16 * *(_DWORD *)a2];
            *(_DWORD *)(a2 + 4) = v16;
            *v17++ = Data.Data1;
            *v17++ = *(_DWORD *)&Data.Data2;
            *v17 = *(_DWORD *)Data.Data4;
            v17[1] = *(_DWORD *)&Data.Data4[4];
            ++*(_DWORD *)a2;
LABEL_22:
            memset(&Data, 0, sizeof(Data));
            ++v21;
          }
          while ( !RegEnumKeyW(v22, v21, Name, 0x28u) );
          a1 = v18;
        }
        RegCloseKey(v22);
        v7 = a3;
      }
    }
    while ( a1 );
    v10 = phkResult;
  }
  if ( v10 )
    RegCloseKey(v10);
}

```

## disassembly

```asm
0x100206a3  mov     edi, edi
0x100206a5  push    ebp
0x100206a6  mov     ebp, esp
0x100206a8  sub     esp, 2D8h
0x100206ae  mov     eax, ___security_cookie
0x100206b3  xor     eax, ebp
0x100206b5  mov     [ebp+var_8], eax
0x100206b8  mov     eax, [ebp+arg_4]
0x100206bb  push    ebx
0x100206bc  push    esi
0x100206bd  push    edi
0x100206be  mov     edi, [ebp+arg_0]
0x100206c1  mov     ebx, ecx
0x100206c3  lea     ecx, [ebp+phkResult]
0x100206c9  mov     [ebp+var_2CC], eax
0x100206cf  mov     eax, [ebp+hKey]
0x100206d2  mov     esi, edx
0x100206d4  push    ecx; phkResult
0x100206d5  push    20019h; samDesired
0x100206da  push    0; ulOptions
0x100206dc  push    offset SubKey; "PageAliases"
0x100206e1  push    eax; hKey
0x100206e2  mov     [ebp+var_2D8], edi
0x100206e8  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x100206ee  test    eax, eax
0x100206f0  jz      short loc_100206FC
0x100206f2  xor     eax, eax
0x100206f4  mov     [ebp+phkResult], eax
0x100206fa  jmp     short loc_10020702
0x100206fc  mov     eax, [ebp+phkResult]
0x10020702  test    esi, esi
0x10020704  jz      loc_100208D2
0x1002070a  push    27h ; '''; cchMax
0x1002070c  lea     eax, [ebp+sz]
0x10020712  dec     esi
0x10020713  push    eax; lpsz
0x10020714  mov     eax, esi
0x10020716  mov     [ebp+var_2D4], esi
0x1002071c  shl     eax, 4
0x1002071f  add     eax, edi
0x10020721  push    eax; rguid
0x10020722  call    ds:__imp__StringFromGUID2@12; StringFromGUID2(x,x,x)
0x10020728  lea     eax, [ebp+sz]
0x1002072e  push    eax
0x1002072f  push    [ebp+var_2CC]
0x10020735  lea     eax, [ebp+SubKey]
0x1002073b  push    offset aSSPropertypage; "%s\\%s\\PropertyPages"
0x10020740  push    100h; unsigned int
0x10020745  push    eax; unsigned __int16 *
0x10020746  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x1002074b  add     esp, 14h
0x1002074e  lea     eax, [ebp+var_2C4]
0x10020754  push    eax; phkResult
0x10020755  push    20019h; samDesired
0x1002075a  push    0; ulOptions
0x1002075c  lea     eax, [ebp+SubKey]
0x10020762  push    eax; lpSubKey
0x10020763  push    80000002h; hKey
0x10020768  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1002076e  test    eax, eax
0x10020770  jnz     loc_100208C4
0x10020776  mov     [ebp+var_2C8], eax
0x1002077c  lea     edi, [ebp+Data]
0x10020782  stosd
0x10020783  push    28h ; '('; cchName
0x10020785  stosd
0x10020786  stosd
0x10020787  stosd
0x10020788  lea     eax, [ebp+Name]
0x1002078b  push    eax; lpName
0x1002078c  push    0; dwIndex
0x1002078e  push    [ebp+var_2C4]; hKey
0x10020794  call    ds:__imp__RegEnumKeyW@16; RegEnumKeyW(x,x,x,x)
0x1002079a  test    eax, eax
0x1002079c  jnz     loc_100208B2
0x100207a2  cmp     [ebp+phkResult], 0
0x100207a9  jz      short loc_100207DB
0x100207ab  lea     eax, [ebp+cbData]
0x100207b1  mov     [ebp+cbData], 10h
0x100207bb  push    eax; lpcbData
0x100207bc  lea     eax, [ebp+Data]
0x100207c2  push    eax; lpData
0x100207c3  push    0; lpType
0x100207c5  push    0; lpReserved
0x100207c7  lea     eax, [ebp+Name]
0x100207ca  push    eax; lpValueName
0x100207cb  push    [ebp+phkResult]; hKey
0x100207d1  call    ds:__imp__RegQueryValueExW@24; RegQueryValueExW(x,x,x,x,x,x)
0x100207d7  test    eax, eax
0x100207d9  jz      short loc_100207EC
0x100207db  lea     eax, [ebp+Data]
0x100207e1  push    eax; lpiid
0x100207e2  lea     eax, [ebp+Name]
0x100207e5  push    eax; lpsz
0x100207e6  call    ds:__imp__IIDFromString@8; IIDFromString(x,x)
0x100207ec  mov     esi, [ebx]
0x100207ee  mov     ecx, esi
0x100207f0  mov     edi, [ebx+4]
0x100207f3  test    ecx, ecx
0x100207f5  jz      short loc_1002081B
0x100207f7  xor     edx, edx
0x100207f9  lea     eax, [ebp+Data]
0x100207ff  mov     eax, [eax+edx*4]
0x10020802  cmp     eax, [edi+edx*4]
0x10020805  jnz     short loc_1002080F
0x10020807  inc     edx
0x10020808  cmp     edx, 4
0x1002080b  jz      short loc_10020878
0x1002080d  jmp     short loc_100207F9
0x1002080f  push    10h
0x10020811  pop     edx
0x10020812  add     edi, edx
0x10020814  sub     ecx, 1
0x10020817  jnz     short loc_100207F7
0x10020819  jmp     short loc_1002081E
0x1002081b  push    10h
0x1002081d  pop     edx
0x1002081e  lea     eax, [esi+1]
0x10020821  cmp     eax, esi
0x10020823  jb      loc_100208AC
0x10020829  mul     edx
0x1002082b  test    edx, edx
0x1002082d  ja      short loc_100208AC
0x1002082f  jb      short loc_10020836
0x10020831  cmp     eax, 0FFFFFFFFh
0x10020834  ja      short loc_100208AC
0x10020836  push    eax; cb
0x10020837  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1002083d  mov     esi, eax
0x1002083f  test    esi, esi
0x10020841  jz      short loc_100208AC
0x10020843  mov     ecx, [ebx]
0x10020845  test    ecx, ecx
0x10020847  jz      short loc_10020862
0x10020849  shl     ecx, 4
0x1002084c  push    ecx; Size
0x1002084d  push    dword ptr [ebx+4]; Src
0x10020850  push    esi; void *
0x10020851  call    _memcpy
0x10020856  add     esp, 0Ch
0x10020859  push    dword ptr [ebx+4]; pv
0x1002085c  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x10020862  mov     edi, [ebx]
0x10020864  shl     edi, 4
0x10020867  add     edi, esi
0x10020869  mov     [ebx+4], esi
0x1002086c  lea     esi, [ebp+Data]
0x10020872  movsd
0x10020873  movsd
0x10020874  movsd
0x10020875  movsd
0x10020876  inc     dword ptr [ebx]
0x10020878  mov     ecx, [ebp+var_2C8]
0x1002087e  lea     edi, [ebp+Data]
0x10020884  xor     eax, eax
0x10020886  inc     ecx
0x10020887  stosd
0x10020888  push    28h ; '('; cchName
0x1002088a  mov     [ebp+var_2C8], ecx
0x10020890  stosd
0x10020891  stosd
0x10020892  stosd
0x10020893  lea     eax, [ebp+Name]
0x10020896  push    eax; lpName
0x10020897  push    ecx; dwIndex
0x10020898  push    [ebp+var_2C4]; hKey
0x1002089e  call    ds:__imp__RegEnumKeyW@16; RegEnumKeyW(x,x,x,x)
0x100208a4  test    eax, eax
0x100208a6  jz      loc_100207A2
0x100208ac  mov     esi, [ebp+var_2D4]
0x100208b2  push    [ebp+var_2C4]; hKey
0x100208b8  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100208be  mov     edi, [ebp+var_2D8]
0x100208c4  test    esi, esi
0x100208c6  jnz     loc_1002070A
0x100208cc  mov     eax, [ebp+phkResult]
0x100208d2  test    eax, eax
0x100208d4  jz      short loc_100208DD
0x100208d6  push    eax; hKey
0x100208d7  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x100208dd  mov     ecx, [ebp+var_8]
0x100208e0  pop     edi
0x100208e1  pop     esi
0x100208e2  xor     ecx, ebp; StackCookie
0x100208e4  pop     ebx
0x100208e5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100208ea  leave
0x100208eb  retn    0Ch
```
