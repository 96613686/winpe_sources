# GetIkev2TrafficSelectors

- ea: `0x18002f8cc`
- end: `0x18002fb2d`
- name: `GetIkev2TrafficSelectors`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180021e38`

## callees

- `0x18002ef48`
- `0x18002f8cc`
- `0x18002fb34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f96d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002faed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f96d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002faed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002fb06`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f964`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f97b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f964`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002f97b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fafb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fafb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002fb14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002faa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fabf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fad6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002faa8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fabf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fad6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f936`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f936`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fa74`

## pseudocode

```c
__int64 __fastcall GetIkev2TrafficSelectors(HKEY a1, __int64 a2, __int64 a3, __int64 a4)
{
  _DWORD *v4; // r14
  char *v5; // rdi
  LSTATUS v7; // eax
  unsigned int Ikev2TrafficSelectorsRegParams; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  char *v11; // rax
  __int64 v12; // rcx
  HANDLE v13; // rax
  HANDLE v14; // rax
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
        ProcessHeap = GetProcessHeap();
        v4 = HeapAlloc(ProcessHeap, 0, 0x68u);
        v10 = GetProcessHeap();
        v11 = (char *)HeapAlloc(v10, 0, 0x68u);
        v5 = v11;
        if ( v4 && v11 )
        {
          *(_DWORD *)((char *)v4 + 6) = -65536;
          *v4 = 7;
          v4[9] = -1;
          *((_BYTE *)v4 + 4) = 0;
          v4[4] = 0;
          *(_DWORD *)((char *)v4 + 10) = 0x20000;
          *((_WORD *)v4 + 16) = 2;
          *(_DWORD *)v11 = 7;
          *((_DWORD *)v11 + 9) = -1;
          *(_DWORD *)(v11 + 6) = -65536;
          v11[4] = 0;
          *((_DWORD *)v11 + 4) = 0;
          *(_DWORD *)(v11 + 10) = 0x20000;
          *((_WORD *)v11 + 16) = 2;
          GetDefaultTrafficSelector(23, v4 + 13);
          GetDefaultTrafficSelector(v12, v5 + 52);
          Ikev2TrafficSelectorsRegParams = 0;
          *(_DWORD *)a4 = 2;
          *(_DWORD *)(a4 + 4) = 2;
          *(_QWORD *)(a4 + 8) = v4;
          *(_QWORD *)(a4 + 16) = v5;
        }
        else
        {
          Ikev2TrafficSelectorsRegParams = 8;
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
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v4);
    }
    if ( v5 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v5);
    }
  }
  return Ikev2TrafficSelectorsRegParams;
}

```

## disassembly

```asm
0x18002f8cc  mov     r11, rsp
0x18002f8cf  mov     [r11+8], rbx
0x18002f8d3  mov     [r11+18h], r8
0x18002f8d7  mov     [r11+10h], rdx
0x18002f8db  push    rbp
0x18002f8dc  push    rsi
0x18002f8dd  push    rdi
0x18002f8de  push    r12
0x18002f8e0  push    r14
0x18002f8e2  mov     rbp, rsp
0x18002f8e5  sub     rsp, 30h
0x18002f8e9  xor     r14d, r14d
0x18002f8ec  mov     [rbp+hKey], 0
0x18002f8f4  xor     edi, edi
0x18002f8f6  mov     [rbp+hkey], 0
0x18002f8fe  mov     [rbp+arg_18], 0
0x18002f906  mov     rsi, r9
0x18002f909  test    r9, r9
0x18002f90c  jz      loc_18002FA9A
0x18002f912  test    rcx, rcx
0x18002f915  jz      loc_18002FA9A
0x18002f91b  lea     rax, [rbp+hKey]
0x18002f91f  mov     r12d, 20019h
0x18002f925  mov     r9d, r12d; samDesired
0x18002f928  mov     [r11-38h], rax
0x18002f92c  xor     r8d, r8d; ulOptions
0x18002f92f  lea     rdx, aTrafficselecto; "TrafficSelectors"
0x18002f936  call    cs:__imp_RegOpenKeyExW
0x18002f93c  mov     ebx, eax
0x18002f93e  test    eax, eax
0x18002f940  jz      loc_18002FA19
0x18002f946  lea     r12d, [r14+2]
0x18002f94a  cmp     eax, r12d
0x18002f94d  jnz     loc_18002FA9F
0x18002f953  call    cs:__imp_GetProcessHeap
0x18002f959  lea     ebx, [rdi+68h]
0x18002f95c  xor     edx, edx; dwFlags
0x18002f95e  mov     rcx, rax; hHeap
0x18002f961  mov     r8d, ebx; dwBytes
0x18002f964  call    cs:__imp_HeapAlloc
0x18002f96a  mov     r14, rax
0x18002f96d  call    cs:__imp_GetProcessHeap
0x18002f973  mov     r8d, ebx; dwBytes
0x18002f976  xor     edx, edx; dwFlags
0x18002f978  mov     rcx, rax; hHeap
0x18002f97b  call    cs:__imp_HeapAlloc
0x18002f981  mov     rdi, rax
0x18002f984  test    r14, r14
0x18002f987  jz      loc_18002FA0F
0x18002f98d  test    rax, rax
0x18002f990  jz      short loc_18002FA0F
0x18002f992  mov     dword ptr [r14+6], 0FFFF0000h
0x18002f99a  lea     edx, [rbx-61h]
0x18002f99d  mov     [r14], edx
0x18002f9a0  or      ecx, 0FFFFFFFFh
0x18002f9a3  mov     [r14+24h], ecx
0x18002f9a7  mov     byte ptr [r14+4], 0
0x18002f9ac  mov     dword ptr [r14+10h], 0
0x18002f9b4  mov     dword ptr [r14+0Ah], 20000h
0x18002f9bc  mov     [r14+20h], r12w
0x18002f9c1  mov     [rax], edx
0x18002f9c3  lea     rdx, [r14+34h]
0x18002f9c7  mov     [rax+24h], ecx
0x18002f9ca  lea     ecx, [rbx-51h]
0x18002f9cd  mov     dword ptr [rax+6], 0FFFF0000h
0x18002f9d4  mov     byte ptr [rax+4], 0
0x18002f9d8  mov     dword ptr [rax+10h], 0
0x18002f9df  mov     dword ptr [rax+0Ah], 20000h
0x18002f9e6  mov     [rax+20h], r12w
0x18002f9eb  call    GetDefaultTrafficSelector
0x18002f9f0  lea     rdx, [rdi+34h]
0x18002f9f4  call    GetDefaultTrafficSelector
0x18002f9f9  xor     ebx, ebx
0x18002f9fb  mov     [rsi], r12d
0x18002f9fe  mov     [rsi+4], r12d
0x18002fa02  mov     [rsi+8], r14
0x18002fa06  mov     [rsi+10h], rdi
0x18002fa0a  jmp     loc_18002FA9F
0x18002fa0f  mov     ebx, 8
0x18002fa14  jmp     loc_18002FA9F
0x18002fa19  mov     rcx, [rbp+hKey]; hKey
0x18002fa1d  lea     rax, [rbp+hkey]
0x18002fa21  mov     r9d, r12d; samDesired
0x18002fa24  mov     [rsp+30h+phkResult], rax; phkResult
0x18002fa29  xor     r8d, r8d; ulOptions
0x18002fa2c  lea     rdx, aInitiator; "Initiator"
0x18002fa33  call    cs:__imp_RegOpenKeyExW
0x18002fa39  mov     ebx, eax
0x18002fa3b  test    eax, eax
0x18002fa3d  jnz     short loc_18002FA9F
0x18002fa3f  mov     rcx, [rbp+hkey]; hkey
0x18002fa43  lea     rax, [rsi+8]
0x18002fa47  mov     r9, rsi
0x18002fa4a  mov     [rsp+30h+phkResult], rax; __int64
0x18002fa4f  call    GetIkev2TrafficSelectorsRegParams
0x18002fa54  mov     ebx, eax
0x18002fa56  test    eax, eax
0x18002fa58  jnz     short loc_18002FA9F
0x18002fa5a  mov     rcx, [rbp+hKey]; hKey
0x18002fa5e  lea     rax, [rbp+arg_18]
0x18002fa62  mov     r9d, r12d; samDesired
0x18002fa65  mov     [rsp+30h+phkResult], rax; phkResult
0x18002fa6a  xor     r8d, r8d; ulOptions
0x18002fa6d  lea     rdx, aResponder; "Responder"
0x18002fa74  call    cs:__imp_RegOpenKeyExW
0x18002fa7a  mov     ebx, eax
0x18002fa7c  test    eax, eax
0x18002fa7e  jnz     short loc_18002FA9F
0x18002fa80  mov     rcx, [rbp+arg_18]; hkey
0x18002fa84  lea     rax, [rsi+10h]
0x18002fa88  lea     r9, [rsi+4]
0x18002fa8c  mov     [rsp+30h+phkResult], rax; __int64
0x18002fa91  call    GetIkev2TrafficSelectorsRegParams
0x18002fa96  mov     ebx, eax
0x18002fa98  jmp     short loc_18002FA9F
0x18002fa9a  mov     ebx, 57h ; 'W'
0x18002fa9f  mov     rcx, [rbp+hKey]; hKey
0x18002faa3  test    rcx, rcx
0x18002faa6  jz      short loc_18002FAB6
0x18002faa8  call    cs:__imp_RegCloseKey
0x18002faae  mov     [rbp+hKey], 0
0x18002fab6  mov     rcx, [rbp+hkey]; hKey
0x18002faba  test    rcx, rcx
0x18002fabd  jz      short loc_18002FACD
0x18002fabf  call    cs:__imp_RegCloseKey
0x18002fac5  mov     [rbp+hkey], 0
0x18002facd  mov     rcx, [rbp+arg_18]; hKey
0x18002fad1  test    rcx, rcx
0x18002fad4  jz      short loc_18002FAE4
0x18002fad6  call    cs:__imp_RegCloseKey
0x18002fadc  mov     [rbp+arg_18], 0
0x18002fae4  test    ebx, ebx
0x18002fae6  jz      short loc_18002FB1A
0x18002fae8  test    r14, r14
0x18002faeb  jz      short loc_18002FB01
0x18002faed  call    cs:__imp_GetProcessHeap
0x18002faf3  mov     r8, r14; lpMem
0x18002faf6  xor     edx, edx; dwFlags
0x18002faf8  mov     rcx, rax; hHeap
0x18002fafb  call    cs:__imp_HeapFree
0x18002fb01  test    rdi, rdi
0x18002fb04  jz      short loc_18002FB1A
0x18002fb06  call    cs:__imp_GetProcessHeap
0x18002fb0c  mov     r8, rdi; lpMem
0x18002fb0f  xor     edx, edx; dwFlags
0x18002fb11  mov     rcx, rax; hHeap
0x18002fb14  call    cs:__imp_HeapFree
0x18002fb1a  mov     eax, ebx
0x18002fb1c  mov     rbx, [rsp+30h+arg_0]
0x18002fb21  add     rsp, 30h
0x18002fb25  pop     r14
0x18002fb27  pop     r12
0x18002fb29  pop     rdi
0x18002fb2a  pop     rsi
0x18002fb2b  pop     rbp
0x18002fb2c  retn
```
