# SockLoadTransportMapping

- ea: `0x18001097c`
- end: `0x180010dfa`
- name: `SockLoadTransportMapping`
- size: `1150`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000b3a0`
- `0x180010680`

## callees

- `0x18001097c`
- `0x180038104`
- `0x18003aec4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180010b43`
- `ntdll!RtlFreeHeap` at `0x180010c7b`
- `ntdll!RtlFreeHeap` at `0x180010dd4`
- `ntdll!RtlFreeHeap` at `0x180010b43`
- `ntdll!RtlFreeHeap` at `0x180010c7b`
- `ntdll!RtlFreeHeap` at `0x180010dd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010de4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010c8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010de4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010c0e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010c0e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010b29`

## string_xrefs

- `0x1800109ee`: `System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall SockLoadTransportMapping(WCHAR *a1, PVOID *a2)
{
  __int64 v3; // rax
  WCHAR *v4; // rsi
  unsigned __int64 v5; // rbx
  WCHAR *v6; // rax
  WCHAR *v7; // rdi
  unsigned __int64 v8; // rbx
  __int64 v9; // r9
  const wchar_t *v10; // r8
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  bool v13; // zf
  WCHAR *v14; // rcx
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rax
  __int64 v17; // r8
  WCHAR *v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  WCHAR *v21; // rcx
  WCHAR *v22; // rax
  unsigned __int64 v23; // rdx
  __int64 v24; // r8
  const wchar_t *v25; // rcx
  WCHAR *v26; // rax
  unsigned __int64 i; // rdx
  WCHAR *v28; // rcx
  unsigned int v29; // ebx
  __int64 v30; // rcx
  unsigned int v32; // eax
  __int64 v33; // rcx
  BYTE *v34; // rax
  unsigned int v35; // eax
  unsigned __int64 v36; // rcx
  PVOID v37; // rbx
  unsigned __int64 v38; // r9
  DWORD v39; // eax
  __int64 v40; // rcx
  DWORD LastError; // eax
  __int64 v42; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v3 = -1;
  cbData = 0;
  v4 = a1;
  Type = 0;
  do
    ++v3;
  while ( a1[v3] );
  v5 = (unsigned int)(2 * v3 + 108);
  v6 = (WCHAR *)((__int64 (__fastcall *)(HANDLE, _QWORD, unsigned __int64))SockAllocateHeapRoutine)(
                  SockPrivateHeap,
                  0,
                  v5);
  v7 = v6;
  if ( v6 )
  {
    v8 = v5 >> 1;
    if ( v8 )
    {
      v9 = 2147483646;
      v10 = L"System\\CurrentControlSet\\Services\\";
      v11 = 2147483646;
      v12 = v8;
      do
      {
        if ( !v11 )
          break;
        if ( !*v10 )
          break;
        *v6++ = *v10++;
        --v11;
        --v12;
      }
      while ( v12 );
      v13 = v12 == 0;
      v14 = v6 - 1;
      v15 = v8;
      if ( !v13 )
        v14 = v6;
      v16 = v7;
      *v14 = 0;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v15;
      }
      while ( v15 );
      v17 = (v8 - v15) & -(__int64)(v15 != 0);
      if ( v15 )
      {
        v18 = &v7[v17];
        v19 = 2147483646;
        v20 = v8 - v17;
        if ( v8 != v17 )
        {
          do
          {
            if ( !v19 )
              break;
            if ( !*v4 )
              break;
            *v18++ = *v4++;
            --v19;
            --v20;
          }
          while ( v20 );
        }
        v21 = v18 - 1;
        if ( v20 )
          v21 = v18;
        *v21 = 0;
      }
      v22 = v7;
      v23 = v8;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v8;
      }
      while ( v8 );
      v24 = (v23 - v8) & -(__int64)(v8 != 0);
      if ( v8 )
      {
        v25 = L"\\Parameters\\Winsock";
        v26 = &v7[v24];
        for ( i = v23 - v24; i; --i )
        {
          if ( !v9 )
            break;
          if ( !*v25 )
            break;
          *v26++ = *v25++;
          --v9;
        }
        v28 = v26 - 1;
        if ( i )
          v28 = v26;
        *v28 = 0;
      }
    }
    v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
    RtlFreeHeap(SockPrivateHeap, 0, v7);
    if ( v29 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v30, 22, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, v29);
      return v29;
    }
    cbData = 0;
    v32 = RegQueryValueExW(hKey, L"Mapping", 0, &Type, 0, &cbData);
    v29 = v32;
    if ( v32 != 234 && v32 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v33, 23, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, v32);
    }
    else if ( Type == 3 )
    {
      if ( cbData < 0x14 )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 25, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids);
        v29 = 24;
      }
      else
      {
        v34 = (BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                        SockPrivateHeap,
                        0,
                        cbData);
        *a2 = v34;
        if ( v34 )
        {
          v35 = RegQueryValueExW(hKey, L"Mapping", 0, &Type, v34, &cbData);
          v29 = v35;
          if ( !v35 )
          {
            v37 = *a2;
            v38 = *(unsigned int *)*a2;
            if ( v38 > 0x15555554 || (v36 = 12 * v38 + 8, cbData < v36) )
            {
              if ( (xmmword_180063D60 & 2) != 0 )
                WPP_SF_l(v36, 28, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, v38);
              RtlFreeHeap(SockPrivateHeap, 0, v37);
              RegCloseKey(hKey);
              return 24;
            }
            else
            {
              RegCloseKey(hKey);
              return 0;
            }
          }
          if ( (xmmword_180063D60 & 2) != 0 )
            WPP_SF_l(v36, 27, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, v35);
          RtlFreeHeap(SockPrivateHeap, 0, *a2);
        }
        else
        {
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            LastError = GetLastError();
            WPP_SF_l(v42, 26, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, LastError);
          }
          v29 = 8;
        }
      }
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_(1025, 24, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids);
      v29 = 1804;
    }
    RegCloseKey(hKey);
    return v29;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    v39 = GetLastError();
    WPP_SF_l(v40, 21, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids, v39);
  }
  return 8;
}

```

## disassembly

```asm
0x18001097c  mov     [rsp-28h+arg_0], rbx
0x180010981  push    rbp
0x180010982  push    rsi
0x180010983  push    rdi
0x180010984  push    r14
0x180010986  push    r15
0x180010988  mov     rbp, rsp
0x18001098b  sub     rsp, 40h
0x18001098f  xor     r15d, r15d
0x180010992  mov     r14, rdx
0x180010995  mov     [rbp+hKey], r15
0x180010999  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001099d  mov     [rbp+cbData], r15d
0x1800109a1  mov     rsi, rcx
0x1800109a4  mov     [rbp+Type], r15d
0x1800109a8  inc     rax
0x1800109ab  cmp     [rcx+rax*2], r15w
0x1800109b0  jnz     short loc_1800109A8
0x1800109b2  mov     rcx, cs:SockPrivateHeap
0x1800109b9  lea     eax, ds:6Ch[rax*2]
0x1800109c0  mov     ebx, eax
0x1800109c2  xor     edx, edx
0x1800109c4  mov     r8d, eax
0x1800109c7  mov     rax, cs:SockAllocateHeapRoutine
0x1800109ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d3  mov     rdi, rax
0x1800109d6  test    rax, rax
0x1800109d9  jz      loc_180010CB0
0x1800109df  shr     rbx, 1
0x1800109e2  jz      loc_180010B0D
0x1800109e8  mov     r9d, 7FFFFFFEh
0x1800109ee  lea     r8, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\"
0x1800109f5  mov     ecx, r9d
0x1800109f8  mov     rdx, rbx
0x1800109fb  test    rcx, rcx
0x1800109fe  jz      short loc_180010A1F
0x180010a00  movzx   r10d, word ptr [r8]
0x180010a04  test    r10w, r10w
0x180010a08  jz      short loc_180010A1F
0x180010a0a  mov     [rax], r10w
0x180010a0e  add     r8, 2
0x180010a12  add     rax, 2
0x180010a16  dec     rcx
0x180010a19  sub     rdx, 1
0x180010a1d  jnz     short loc_1800109FB
0x180010a1f  test    rdx, rdx
0x180010a22  lea     rcx, [rax-2]
0x180010a26  mov     rdx, rbx
0x180010a29  cmovnz  rcx, rax
0x180010a2d  mov     rax, rdi
0x180010a30  mov     [rcx], r15w
0x180010a34  cmp     [rax], r15w
0x180010a38  jz      short loc_180010A44
0x180010a3a  add     rax, 2
0x180010a3e  sub     rdx, 1
0x180010a42  jnz     short loc_180010A34
0x180010a44  mov     rcx, rbx
0x180010a47  mov     rax, rdx
0x180010a4a  sub     rcx, rdx
0x180010a4d  neg     rax
0x180010a50  sbb     r8, r8
0x180010a53  and     r8, rcx
0x180010a56  test    rdx, rdx
0x180010a59  jz      short loc_180010A9D
0x180010a5b  mov     rax, rbx
0x180010a5e  lea     rdx, [rdi+r8*2]
0x180010a62  mov     rcx, r9
0x180010a65  sub     rax, r8
0x180010a68  jz      short loc_180010A8E
0x180010a6a  test    rcx, rcx
0x180010a6d  jz      short loc_180010A8E
0x180010a6f  movzx   r8d, word ptr [rsi]
0x180010a73  test    r8w, r8w
0x180010a77  jz      short loc_180010A8E
0x180010a79  mov     [rdx], r8w
0x180010a7d  add     rsi, 2
0x180010a81  add     rdx, 2
0x180010a85  dec     rcx
0x180010a88  sub     rax, 1
0x180010a8c  jnz     short loc_180010A6A
0x180010a8e  test    rax, rax
0x180010a91  lea     rcx, [rdx-2]
0x180010a95  cmovnz  rcx, rdx
0x180010a99  mov     [rcx], r15w
0x180010a9d  mov     rax, rdi
0x180010aa0  mov     rdx, rbx
0x180010aa3  cmp     [rax], r15w
0x180010aa7  jz      short loc_180010AB3
0x180010aa9  add     rax, 2
0x180010aad  sub     rbx, 1
0x180010ab1  jnz     short loc_180010AA3
0x180010ab3  mov     rcx, rdx
0x180010ab6  mov     rax, rbx
0x180010ab9  sub     rcx, rbx
0x180010abc  neg     rax
0x180010abf  sbb     r8, r8
0x180010ac2  and     r8, rcx
0x180010ac5  test    rbx, rbx
0x180010ac8  jz      short loc_180010B0D
0x180010aca  lea     rcx, aParametersWins; "\\Parameters\\Winsock"
0x180010ad1  lea     rax, [rdi+r8*2]
0x180010ad5  sub     rdx, r8
0x180010ad8  jz      short loc_180010AFE
0x180010ada  test    r9, r9
0x180010add  jz      short loc_180010AFE
0x180010adf  movzx   r8d, word ptr [rcx]
0x180010ae3  test    r8w, r8w
0x180010ae7  jz      short loc_180010AFE
0x180010ae9  mov     [rax], r8w
0x180010aed  add     rcx, 2
0x180010af1  add     rax, 2
0x180010af5  dec     r9
0x180010af8  sub     rdx, 1
0x180010afc  jnz     short loc_180010ADA
0x180010afe  test    rdx, rdx
0x180010b01  lea     rcx, [rax-2]
0x180010b05  cmovnz  rcx, rax
0x180010b09  mov     [rcx], r15w
0x180010b0d  lea     rax, [rbp+hKey]
0x180010b11  mov     r9d, 20019h; samDesired
0x180010b17  xor     r8d, r8d; ulOptions
0x180010b1a  mov     [rsp+40h+phkResult], rax; phkResult
0x180010b1f  mov     rdx, rdi; lpSubKey
0x180010b22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010b29  call    cs:__imp_RegOpenKeyExW
0x180010b30  nop     dword ptr [rax+rax+00h]
0x180010b35  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180010b3c  mov     r8, rdi; P
0x180010b3f  xor     edx, edx; Flags
0x180010b41  mov     ebx, eax
0x180010b43  call    cs:__imp_RtlFreeHeap
0x180010b4a  nop     dword ptr [rax+rax+00h]
0x180010b4f  test    ebx, ebx
0x180010b51  jz      short loc_180010B74
0x180010b53  test    byte ptr cs:xmmword_180063D60, 2
0x180010b5a  jnz     loc_180010CE3
0x180010b60  mov     eax, ebx
0x180010b62  mov     rbx, [rsp+40h+arg_0]
0x180010b67  add     rsp, 40h
0x180010b6b  pop     r15
0x180010b6d  pop     r14
0x180010b6f  pop     rdi
0x180010b70  pop     rsi
0x180010b71  pop     rbp
0x180010b72  retn
0x180010b74  mov     rcx, [rbp+hKey]; hKey
0x180010b78  lea     rax, [rbp+cbData]
0x180010b7c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180010b81  lea     r9, [rbp+Type]; lpType
0x180010b85  xor     r8d, r8d; lpReserved
0x180010b88  mov     [rsp+40h+phkResult], r15; lpData
0x180010b8d  lea     rdx, aMapping; "Mapping"
0x180010b94  mov     [rbp+cbData], r15d
0x180010b98  call    cs:__imp_RegQueryValueExW
0x180010b9f  nop     dword ptr [rax+rax+00h]
0x180010ba4  mov     ebx, eax
0x180010ba6  cmp     eax, 0EAh
0x180010bab  jz      short loc_180010BB5
0x180010bad  test    eax, eax
0x180010baf  jnz     loc_180010CFC
0x180010bb5  cmp     [rbp+Type], 3
0x180010bb9  jnz     loc_180010D1E
0x180010bbf  cmp     [rbp+cbData], 14h
0x180010bc3  jb      loc_180010D47
0x180010bc9  mov     r8d, [rbp+cbData]
0x180010bcd  xor     edx, edx
0x180010bcf  mov     rcx, cs:SockPrivateHeap
0x180010bd6  mov     rax, cs:SockAllocateHeapRoutine
0x180010bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be2  mov     [r14], rax
0x180010be5  test    rax, rax
0x180010be8  jz      loc_180010C9C
0x180010bee  lea     rcx, [rbp+cbData]
0x180010bf2  xor     r8d, r8d; lpReserved
0x180010bf5  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x180010bfa  lea     r9, [rbp+Type]; lpType
0x180010bfe  mov     rcx, [rbp+hKey]; hKey
0x180010c02  lea     rdx, aMapping; "Mapping"
0x180010c09  mov     [rsp+40h+phkResult], rax; lpData
0x180010c0e  call    cs:__imp_RegQueryValueExW
0x180010c15  nop     dword ptr [rax+rax+00h]
0x180010c1a  mov     ebx, eax
0x180010c1c  test    eax, eax
0x180010c1e  jnz     short loc_180010C62
0x180010c20  mov     rbx, [r14]
0x180010c23  mov     r9d, [rbx]
0x180010c26  cmp     r9, 15555554h
0x180010c2d  ja      loc_180010DAE
0x180010c33  lea     rax, [r9+r9*2]
0x180010c37  lea     rcx, ds:8[rax*4]
0x180010c3f  mov     eax, [rbp+cbData]
0x180010c42  cmp     rax, rcx
0x180010c45  jb      loc_180010DAE
0x180010c4b  mov     rcx, [rbp+hKey]; hKey
0x180010c4f  call    cs:__imp_RegCloseKey
0x180010c56  nop     dword ptr [rax+rax+00h]
0x180010c5b  xor     eax, eax
0x180010c5d  jmp     loc_180010B62
0x180010c62  test    byte ptr cs:xmmword_180063D60, 2
0x180010c69  jnz     loc_180010D95
0x180010c6f  mov     r8, [r14]; P
0x180010c72  xor     edx, edx; Flags
0x180010c74  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180010c7b  call    cs:__imp_RtlFreeHeap
0x180010c82  nop     dword ptr [rax+rax+00h]
0x180010c87  mov     rcx, [rbp+hKey]; hKey
0x180010c8b  call    cs:__imp_RegCloseKey
0x180010c92  nop     dword ptr [rax+rax+00h]
0x180010c97  jmp     loc_180010B60
0x180010c9c  test    byte ptr cs:xmmword_180063D60, 2
0x180010ca3  jnz     loc_180010D70
0x180010ca9  mov     ebx, 8
0x180010cae  jmp     short loc_180010C87
0x180010cb0  test    byte ptr cs:xmmword_180063D60, 2
0x180010cb7  jz      short loc_180010CD9
0x180010cb9  call    cs:__imp_GetLastError
0x180010cc0  nop     dword ptr [rax+rax+00h]
0x180010cc5  mov     edx, 15h
0x180010cca  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010cd1  mov     r9d, eax
0x180010cd4  call    WPP_SF_l
0x180010cd9  mov     eax, 8
0x180010cde  jmp     loc_180010B62
0x180010ce3  mov     edx, 16h
0x180010ce8  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010cef  mov     r9d, ebx
0x180010cf2  call    WPP_SF_l
0x180010cf7  jmp     loc_180010B60
0x180010cfc  test    byte ptr cs:xmmword_180063D60, 2
0x180010d03  jz      short loc_180010C87
0x180010d05  mov     edx, 17h
0x180010d0a  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010d11  mov     r9d, eax
0x180010d14  call    WPP_SF_l
0x180010d19  jmp     loc_180010C87
0x180010d1e  test    byte ptr cs:xmmword_180063D60, 2
0x180010d25  jz      short loc_180010D3D
0x180010d27  mov     edx, 18h
0x180010d2c  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010d33  mov     ecx, 401h
0x180010d38  call    WPP_SF_
0x180010d3d  mov     ebx, 70Ch
0x180010d42  jmp     loc_180010C87
0x180010d47  test    byte ptr cs:xmmword_180063D60, 2
0x180010d4e  jz      short loc_180010D66
0x180010d50  mov     edx, 19h
0x180010d55  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010d5c  mov     ecx, 401h
0x180010d61  call    WPP_SF_
0x180010d66  mov     ebx, 18h
0x180010d6b  jmp     loc_180010C87
0x180010d70  call    cs:__imp_GetLastError
0x180010d77  nop     dword ptr [rax+rax+00h]
0x180010d7c  mov     edx, 1Ah
0x180010d81  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010d88  mov     r9d, eax
0x180010d8b  call    WPP_SF_l
0x180010d90  jmp     loc_180010CA9
0x180010d95  mov     edx, 1Bh
0x180010d9a  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010da1  mov     r9d, eax
0x180010da4  call    WPP_SF_l
0x180010da9  jmp     loc_180010C6F
0x180010dae  test    byte ptr cs:xmmword_180063D60, 2
0x180010db5  jz      short loc_180010DC8
0x180010db7  mov     edx, 1Ch
0x180010dbc  lea     r8, WPP_119504d212cf33b3fd354731a5a20fa1_Traceguids
0x180010dc3  call    WPP_SF_l
0x180010dc8  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180010dcf  mov     r8, rbx; P
0x180010dd2  xor     edx, edx; Flags
0x180010dd4  call    cs:__imp_RtlFreeHeap
0x180010ddb  nop     dword ptr [rax+rax+00h]
0x180010de0  mov     rcx, [rbp+hKey]; hKey
0x180010de4  call    cs:__imp_RegCloseKey
0x180010deb  nop     dword ptr [rax+rax+00h]
0x180010df0  mov     eax, 18h
0x180010df5  jmp     loc_180010B62
```
