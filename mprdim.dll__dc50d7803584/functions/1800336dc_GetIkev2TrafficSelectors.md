# GetIkev2TrafficSelectors

- ea: `0x1800336dc`
- end: `0x1800338f4`
- name: `GetIkev2TrafficSelectors`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800165cc`

## callees

- `0x180032e20`
- `0x1800336dc`
- `0x1800338fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033776`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003378b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180033776`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003378b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800338db`
- `ADVAPI32!RegOpenKeyExW` at `0x180033746`
- `ADVAPI32!RegOpenKeyExW` at `0x1800337fe`
- `ADVAPI32!RegOpenKeyExW` at `0x18003383f`
- `ADVAPI32!RegOpenKeyExW` at `0x180033746`
- `ADVAPI32!RegOpenKeyExW` at `0x1800337fe`
- `ADVAPI32!RegOpenKeyExW` at `0x18003383f`
- `ADVAPI32!RegCloseKey` at `0x180033873`
- `ADVAPI32!RegCloseKey` at `0x18003388a`
- `ADVAPI32!RegCloseKey` at `0x1800338a1`
- `ADVAPI32!RegCloseKey` at `0x180033873`
- `ADVAPI32!RegCloseKey` at `0x18003388a`
- `ADVAPI32!RegCloseKey` at `0x1800338a1`

## pseudocode

```c
__int64 __fastcall GetIkev2TrafficSelectors(HKEY a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // r14
  char *v5; // rsi
  LSTATUS v7; // eax
  unsigned int Ikev2TrafficSelectorsRegParams; // ebx
  char *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rcx
  HKEY hkey; // [rsp+68h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+48h] BYREF

  v4 = 0;
  hKey = 0;
  v5 = 0;
  hkey = 0;
  phkResult = 0;
  if ( a4 && a1 )
  {
    v7 = RegOpenKeyExW(a1, L"TrafficSelectors", 0, 0x20019u, &hKey);
    Ikev2TrafficSelectorsRegParams = v7;
    if ( v7 )
    {
      if ( v7 == 2 )
      {
        Ikev2TrafficSelectorsRegParams = 8;
        v4 = (char *)HeapAlloc(hHeap, 8u, 0x68u);
        v9 = (char *)HeapAlloc(hHeap, 8u, 0x68u);
        v5 = v9;
        if ( v4 )
        {
          if ( v9 )
          {
            GetDefaultTrafficSelector(2, v4);
            GetDefaultTrafficSelector(v10, v5);
            GetDefaultTrafficSelector(23, v4 + 52);
            GetDefaultTrafficSelector(v11, v5 + 52);
            Ikev2TrafficSelectorsRegParams = 0;
            *(_DWORD *)a4 = 2;
            *(_DWORD *)(a4 + 4) = 2;
            *(_QWORD *)(a4 + 8) = v4;
            *(_QWORD *)(a4 + 16) = v5;
          }
        }
      }
    }
    else
    {
      Ikev2TrafficSelectorsRegParams = RegOpenKeyExW(hKey, L"Initiator", 0, 0x20019u, &hkey);
      if ( !Ikev2TrafficSelectorsRegParams )
      {
        Ikev2TrafficSelectorsRegParams = GetIkev2TrafficSelectorsRegParams(hkey, a4 + 8);
        if ( !Ikev2TrafficSelectorsRegParams )
        {
          Ikev2TrafficSelectorsRegParams = RegOpenKeyExW(hKey, L"Responder", 0, 0x20019u, &phkResult);
          if ( !Ikev2TrafficSelectorsRegParams )
            Ikev2TrafficSelectorsRegParams = GetIkev2TrafficSelectorsRegParams(phkResult, a4 + 16);
        }
      }
    }
  }
  else
  {
    Ikev2TrafficSelectorsRegParams = 87;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( Ikev2TrafficSelectorsRegParams )
  {
    if ( v4 )
      HeapFree(hHeap, 0, v4);
    if ( v5 )
      HeapFree(hHeap, 0, v5);
  }
  return Ikev2TrafficSelectorsRegParams;
}

```

## disassembly

```asm
0x1800336dc  mov     r11, rsp
0x1800336df  mov     [r11+8], rbx
0x1800336e3  mov     [r11+18h], r8
0x1800336e7  mov     [r11+10h], rdx
0x1800336eb  push    rbp
0x1800336ec  push    rsi
0x1800336ed  push    rdi
0x1800336ee  push    r12
0x1800336f0  push    r14
0x1800336f2  mov     rbp, rsp
0x1800336f5  sub     rsp, 30h
0x1800336f9  xor     r14d, r14d
0x1800336fc  mov     [rbp+hKey], 0
0x180033704  xor     esi, esi
0x180033706  mov     [rbp+hkey], 0
0x18003370e  mov     [rbp+arg_18], 0
0x180033716  mov     rdi, r9
0x180033719  test    r9, r9
0x18003371c  jz      loc_180033865
0x180033722  test    rcx, rcx
0x180033725  jz      loc_180033865
0x18003372b  lea     rax, [rbp+hKey]
0x18003372f  mov     r12d, 20019h
0x180033735  mov     r9d, r12d; samDesired
0x180033738  mov     [r11-38h], rax
0x18003373c  xor     r8d, r8d; ulOptions
0x18003373f  lea     rdx, aTrafficselecto; "TrafficSelectors"
0x180033746  call    cs:__imp_RegOpenKeyExW
0x18003374c  mov     ebx, eax
0x18003374e  test    eax, eax
0x180033750  jz      loc_1800337E4
0x180033756  lea     r12d, [r14+2]
0x18003375a  cmp     eax, r12d
0x18003375d  jnz     loc_18003386A
0x180033763  mov     rcx, cs:hHeap; hHeap
0x18003376a  lea     esi, [r14+68h]
0x18003376e  lea     ebx, [rsi-60h]
0x180033771  mov     r8d, esi; dwBytes
0x180033774  mov     edx, ebx; dwFlags
0x180033776  call    cs:__imp_HeapAlloc
0x18003377c  mov     rcx, cs:hHeap; hHeap
0x180033783  mov     r8d, esi; dwBytes
0x180033786  mov     edx, ebx; dwFlags
0x180033788  mov     r14, rax
0x18003378b  call    cs:__imp_HeapAlloc
0x180033791  mov     rsi, rax
0x180033794  test    r14, r14
0x180033797  jz      loc_18003386A
0x18003379d  test    rax, rax
0x1800337a0  jz      loc_18003386A
0x1800337a6  mov     rdx, r14
0x1800337a9  mov     ecx, r12d
0x1800337ac  call    GetDefaultTrafficSelector
0x1800337b1  mov     rdx, rsi
0x1800337b4  call    GetDefaultTrafficSelector
0x1800337b9  lea     rdx, [r14+34h]
0x1800337bd  lea     ecx, [rbx+0Fh]
0x1800337c0  call    GetDefaultTrafficSelector
0x1800337c5  lea     rdx, [rsi+34h]
0x1800337c9  call    GetDefaultTrafficSelector
0x1800337ce  xor     ebx, ebx
0x1800337d0  mov     [rdi], r12d
0x1800337d3  mov     [rdi+4], r12d
0x1800337d7  mov     [rdi+8], r14
0x1800337db  mov     [rdi+10h], rsi
0x1800337df  jmp     loc_18003386A
0x1800337e4  mov     rcx, [rbp+hKey]; hKey
0x1800337e8  lea     rax, [rbp+hkey]
0x1800337ec  mov     r9d, r12d; samDesired
0x1800337ef  mov     [rsp+30h+phkResult], rax; phkResult
0x1800337f4  xor     r8d, r8d; ulOptions
0x1800337f7  lea     rdx, aInitiator; "Initiator"
0x1800337fe  call    cs:__imp_RegOpenKeyExW
0x180033804  mov     ebx, eax
0x180033806  test    eax, eax
0x180033808  jnz     short loc_18003386A
0x18003380a  mov     rcx, [rbp+hkey]; hkey
0x18003380e  lea     rax, [rdi+8]
0x180033812  mov     r9, rdi
0x180033815  mov     [rsp+30h+phkResult], rax; __int64
0x18003381a  call    GetIkev2TrafficSelectorsRegParams
0x18003381f  mov     ebx, eax
0x180033821  test    eax, eax
0x180033823  jnz     short loc_18003386A
0x180033825  mov     rcx, [rbp+hKey]; hKey
0x180033829  lea     rax, [rbp+arg_18]
0x18003382d  mov     r9d, r12d; samDesired
0x180033830  mov     [rsp+30h+phkResult], rax; phkResult
0x180033835  xor     r8d, r8d; ulOptions
0x180033838  lea     rdx, aResponder; "Responder"
0x18003383f  call    cs:__imp_RegOpenKeyExW
0x180033845  mov     ebx, eax
0x180033847  test    eax, eax
0x180033849  jnz     short loc_18003386A
0x18003384b  mov     rcx, [rbp+arg_18]; hkey
0x18003384f  lea     rax, [rdi+10h]
0x180033853  lea     r9, [rdi+4]
0x180033857  mov     [rsp+30h+phkResult], rax; __int64
0x18003385c  call    GetIkev2TrafficSelectorsRegParams
0x180033861  mov     ebx, eax
0x180033863  jmp     short loc_18003386A
0x180033865  mov     ebx, 57h ; 'W'
0x18003386a  mov     rcx, [rbp+hKey]; hKey
0x18003386e  test    rcx, rcx
0x180033871  jz      short loc_180033881
0x180033873  call    cs:__imp_RegCloseKey
0x180033879  mov     [rbp+hKey], 0
0x180033881  mov     rcx, [rbp+hkey]; hKey
0x180033885  test    rcx, rcx
0x180033888  jz      short loc_180033898
0x18003388a  call    cs:__imp_RegCloseKey
0x180033890  mov     [rbp+hkey], 0
0x180033898  mov     rcx, [rbp+arg_18]; hKey
0x18003389c  test    rcx, rcx
0x18003389f  jz      short loc_1800338AF
0x1800338a1  call    cs:__imp_RegCloseKey
0x1800338a7  mov     [rbp+arg_18], 0
0x1800338af  test    ebx, ebx
0x1800338b1  jz      short loc_1800338E1
0x1800338b3  test    r14, r14
0x1800338b6  jz      short loc_1800338CA
0x1800338b8  mov     rcx, cs:hHeap; hHeap
0x1800338bf  mov     r8, r14; lpMem
0x1800338c2  xor     edx, edx; dwFlags
0x1800338c4  call    cs:__imp_HeapFree
0x1800338ca  test    rsi, rsi
0x1800338cd  jz      short loc_1800338E1
0x1800338cf  mov     rcx, cs:hHeap; hHeap
0x1800338d6  mov     r8, rsi; lpMem
0x1800338d9  xor     edx, edx; dwFlags
0x1800338db  call    cs:__imp_HeapFree
0x1800338e1  mov     eax, ebx
0x1800338e3  mov     rbx, [rsp+30h+arg_0]
0x1800338e8  add     rsp, 30h
0x1800338ec  pop     r14
0x1800338ee  pop     r12
0x1800338f0  pop     rdi
0x1800338f1  pop     rsi
0x1800338f2  pop     rbp
0x1800338f3  retn
```
