# GetColorMatchingModule

- ea: `0x18000bf9c`
- end: `0x18000c306`
- name: `GetColorMatchingModule`
- size: `874`
- prototype: `_QWORD *__fastcall(unsigned int)`
- caller_count: `13`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000be90`
- `0x18001ed70`
- `0x18002a6f8`
- `0x18002a770`
- `0x18003b830`
- `0x18003b970`
- `0x18003bab0`
- `0x18003be00`
- `0x18003bf20`
- `0x18003c0c0`
- `0x18003c240`
- `0x18003cec4`
- `0x18003dd20`

## callees

- `0x18000be44`
- `0x18000bf9c`
- `0x1800181d0`
- `0x18002e5f0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c0c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c050`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c050`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c2de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c2ce`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c2ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c108`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c108`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c153`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c21d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c153`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c1e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c21d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c284`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bff0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c284`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c020`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c020`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bfe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bfe1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c089`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c089`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c0de`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c0de`

## string_xrefs

- `0x18000c0fb`: `icm32.dll`

## pseudocode

```c
_QWORD *__fastcall GetColorMatchingModule(unsigned int a1)
{
  DWORD CurrentProcessId; // esi
  _QWORD *i; // rbx
  HMODULE LibraryW; // rdi
  __int64 HeapObject; // rax
  FARPROC ProcAddress; // rax
  FARPROC *v7; // rsi
  unsigned int j; // r14d
  FARPROC v9; // rax
  __int64 k; // r14
  FARPROC v11; // rax
  __int64 m; // r14
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  CHAR MultiByteStr[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[12]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Data[259]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v20; // [rsp+266h] [rbp+166h]

  hKey = 0;
  Type = 0;
  cbData = 0;
  CurrentProcessId = GetCurrentProcessId();
  EnterCriticalSection(&critsec);
  for ( i = (_QWORD *)gpCMMChain; i; i = (_QWORD *)i[21] )
  {
    if ( *((_DWORD *)i + 3) == a1 && *((_DWORD *)i + 4) == CurrentProcessId )
    {
      ++*((_DWORD *)i + 1);
      break;
    }
  }
  LeaveCriticalSection(&critsec);
  if ( !i )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, gszICMatcher, 0, 0x2000000u, &hKey)
      && (*(_DWORD *)MultiByteStr = _byteswap_ulong(a1), MultiByteToWideChar(0, 0, MultiByteStr, 4, WideCharStr, 5))
      && (cbData = 260, WideCharStr[4] = 0, !RegQueryValueExW(hKey, WideCharStr, 0, &Type, (LPBYTE)Data, &cbData))
      && (v20 = 0, (LibraryW = LoadLibraryW(Data)) != 0)
      || a1 == 1466527264 && (LibraryW = LoadLibraryExW(gszDefaultCMM, 0, 0x800u)) != 0 )
    {
      HeapObject = AllocateHeapObject(541281613);
      if ( HeapObject )
      {
        i = (_QWORD *)(HeapObject ^ 0x49434D20);
        *((_DWORD *)i + 1) = 1;
        *((_DWORD *)i + 3) = a1;
        *((_DWORD *)i + 4) = CurrentProcessId;
        i[3] = LibraryW;
        ProcAddress = GetProcAddress(LibraryW, gszCMMReqFns);
        i[4] = ProcAddress;
        if ( ProcAddress
          && ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) >= 0x50000
          && ((unsigned int (__fastcall *)(__int64))i[4])(1) == a1 )
        {
          v7 = (FARPROC *)(i + 5);
          for ( j = 1; j < 8; ++j )
          {
            v9 = GetProcAddress(LibraryW, (&gszCMMReqFns)[j]);
            *v7 = v9;
            if ( !v9 )
              goto LABEL_34;
            ++v7;
          }
          for ( k = 0; (unsigned int)k < 6; k = (unsigned int)(k + 1) )
          {
            v11 = GetProcAddress(LibraryW, gszCMMOptFns[k]);
            *v7 = v11;
            if ( a1 == 1466527264 && !v11 )
              goto LABEL_34;
            ++v7;
          }
          for ( m = 0; m != 3; ++m )
            *v7++ = GetProcAddress(LibraryW, gszPSFns[m]);
          if ( !i[18] || !i[19] || !i[20] )
          {
            *((_DWORD *)i + 2) |= 1u;
            i[18] = 0;
            i[19] = 0;
            i[20] = 0;
          }
          EnterCriticalSection(&critsec);
          i[21] = gpCMMChain;
          gpCMMChain = (__int64)i;
          LeaveCriticalSection(&critsec);
          goto LABEL_37;
        }
LABEL_34:
        if ( i )
        {
          --*((_DWORD *)i + 1);
          *(_DWORD *)i = 0;
          MemFree(i);
          i = 0;
        }
      }
      FreeLibrary(LibraryW);
    }
LABEL_37:
    if ( hKey )
      RegCloseKey(hKey);
  }
  return i;
}

```

## disassembly

```asm
0x18000bf9c  push    rbp
0x18000bf9e  push    rbx
0x18000bf9f  push    rsi
0x18000bfa0  push    rdi
0x18000bfa1  push    r14
0x18000bfa3  push    r15
0x18000bfa5  lea     rbp, [rsp-188h]
0x18000bfad  sub     rsp, 288h
0x18000bfb4  mov     rax, cs:__security_cookie
0x18000bfbb  xor     rax, rsp
0x18000bfbe  mov     [rbp+1B0h+var_40], rax
0x18000bfc5  mov     r15d, ecx
0x18000bfc8  mov     [rsp+2B0h+hKey], 0
0x18000bfd1  mov     [rsp+2B0h+Type], 0
0x18000bfd9  mov     [rsp+2B0h+cbData], 0
0x18000bfe1  call    cs:__imp_GetCurrentProcessId
0x18000bfe7  lea     rcx, critsec; lpCriticalSection
0x18000bfee  mov     esi, eax
0x18000bff0  call    cs:__imp_EnterCriticalSection
0x18000bff6  mov     rbx, cs:gpCMMChain
0x18000bffd  test    rbx, rbx
0x18000c000  jz      short loc_18000C019
0x18000c002  cmp     [rbx+0Ch], r15d
0x18000c006  jnz     short loc_18000C00D
0x18000c008  cmp     [rbx+10h], esi
0x18000c00b  jz      short loc_18000C016
0x18000c00d  mov     rbx, [rbx+0A8h]
0x18000c014  jmp     short loc_18000BFFD
0x18000c016  inc     dword ptr [rbx+4]
0x18000c019  lea     rcx, critsec; lpCriticalSection
0x18000c020  call    cs:__imp_LeaveCriticalSection
0x18000c026  test    rbx, rbx
0x18000c029  jnz     loc_18000C2E4
0x18000c02f  lea     rax, [rsp+2B0h+hKey]
0x18000c034  mov     r9d, 2000000h; samDesired
0x18000c03a  xor     r8d, r8d; ulOptions
0x18000c03d  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000c042  lea     rdx, gszICMatcher; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000c049  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c050  call    cs:__imp_RegOpenKeyExW
0x18000c056  lea     r14d, [rbx+4]
0x18000c05a  test    eax, eax
0x18000c05c  jnz     loc_18000C0EC
0x18000c062  mov     eax, r15d
0x18000c065  mov     [rsp+2B0h+cchWideChar], 5; cchWideChar
0x18000c06d  bswap   eax
0x18000c06f  mov     dword ptr [rsp+2B0h+MultiByteStr], eax
0x18000c073  lea     r8, [rsp+2B0h+MultiByteStr]; lpMultiByteStr
0x18000c078  lea     rax, [rsp+2B0h+WideCharStr]
0x18000c07d  mov     r9d, r14d; cbMultiByte
0x18000c080  xor     edx, edx; dwFlags
0x18000c082  mov     [rsp+2B0h+phkResult], rax; lpWideCharStr
0x18000c087  xor     ecx, ecx; CodePage
0x18000c089  call    cs:__imp_MultiByteToWideChar
0x18000c08f  test    eax, eax
0x18000c091  jz      short loc_18000C0EC
0x18000c093  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000c098  lea     r9, [rsp+2B0h+Type]; lpType
0x18000c09d  xor     eax, eax
0x18000c09f  mov     [rsp+2B0h+cbData], 104h
0x18000c0a7  mov     [rsp+2B0h+var_260], ax
0x18000c0ac  lea     rdx, [rsp+2B0h+WideCharStr]; lpValueName
0x18000c0b1  lea     rax, [rsp+2B0h+cbData]
0x18000c0b6  xor     r8d, r8d; lpReserved
0x18000c0b9  mov     qword ptr [rsp+2B0h+cchWideChar], rax; lpcbData
0x18000c0be  lea     rax, [rsp+2B0h+Data]
0x18000c0c3  mov     [rsp+2B0h+phkResult], rax; lpData
0x18000c0c8  call    cs:__imp_RegQueryValueExW
0x18000c0ce  test    eax, eax
0x18000c0d0  jnz     short loc_18000C0EC
0x18000c0d2  lea     rcx, [rsp+2B0h+Data]; lpLibFileName
0x18000c0d7  mov     [rbp+1B0h+var_4A], ax
0x18000c0de  call    cs:__imp_LoadLibraryW
0x18000c0e4  mov     rdi, rax
0x18000c0e7  test    rax, rax
0x18000c0ea  jnz     short loc_18000C11A
0x18000c0ec  cmp     r15d, 57696E20h
0x18000c0f3  jnz     loc_18000C2D4
0x18000c0f9  xor     edx, edx; hFile
0x18000c0fb  lea     rcx, gszDefaultCMM; "icm32.dll"
0x18000c102  mov     r8d, 800h; dwFlags
0x18000c108  call    cs:__imp_LoadLibraryExW
0x18000c10e  mov     rdi, rax
0x18000c111  test    rax, rax
0x18000c114  jz      loc_18000C2D4
0x18000c11a  mov     ecx, 20434D4Dh
0x18000c11f  call    AllocateHeapObject
0x18000c124  test    rax, rax
0x18000c127  jz      loc_18000C2CB
0x18000c12d  mov     rdx, cs:gszCMMReqFns; lpProcName
0x18000c134  mov     rbx, rax
0x18000c137  xor     rbx, 49434D20h
0x18000c13e  mov     rcx, rdi; hModule
0x18000c141  mov     dword ptr [rbx+4], 1
0x18000c148  mov     [rbx+0Ch], r15d
0x18000c14c  mov     [rbx+10h], esi
0x18000c14f  mov     [rbx+18h], rdi
0x18000c153  call    cs:__imp_GetProcAddress
0x18000c159  mov     [rbx+20h], rax
0x18000c15d  test    rax, rax
0x18000c160  jz      loc_18000C2AE
0x18000c166  mov     ecx, r14d
0x18000c169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c16e  cmp     eax, 50000h
0x18000c173  jb      loc_18000C2AE
0x18000c179  mov     rax, [rbx+20h]
0x18000c17d  mov     ecx, 1
0x18000c182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c187  cmp     eax, r15d
0x18000c18a  jnz     loc_18000C2AE
0x18000c190  lea     rsi, [rbx+28h]
0x18000c194  mov     r14d, 1
0x18000c19a  lea     rax, __ImageBase
0x18000c1a1  cmp     r14d, 8
0x18000c1a5  jnb     short loc_18000C1D0
0x18000c1a7  mov     edx, r14d
0x18000c1aa  mov     rcx, rdi; hModule
0x18000c1ad  mov     rdx, ds:rva gszCMMReqFns[rax+rdx*8]; lpProcName
0x18000c1b5  call    cs:__imp_GetProcAddress
0x18000c1bb  mov     [rsi], rax
0x18000c1be  test    rax, rax
0x18000c1c1  jz      loc_18000C2AE
0x18000c1c7  add     rsi, 8
0x18000c1cb  inc     r14d
0x18000c1ce  jmp     short loc_18000C19A
0x18000c1d0  xor     r14d, r14d
0x18000c1d3  cmp     r14d, 6
0x18000c1d7  jnb     short loc_18000C20F
0x18000c1d9  mov     rdx, ds:rva gszCMMOptFns[rax+r14*8]; lpProcName
0x18000c1e1  mov     rcx, rdi; hModule
0x18000c1e4  call    cs:__imp_GetProcAddress
0x18000c1ea  mov     [rsi], rax
0x18000c1ed  cmp     r15d, 57696E20h
0x18000c1f4  jnz     short loc_18000C1FF
0x18000c1f6  test    rax, rax
0x18000c1f9  jz      loc_18000C2AE
0x18000c1ff  add     rsi, 8
0x18000c203  lea     rax, __ImageBase
0x18000c20a  inc     r14d
0x18000c20d  jmp     short loc_18000C1D3
0x18000c20f  xor     r14d, r14d
0x18000c212  mov     rdx, ds:rva gszPSFns[rax+r14*8]; lpProcName
0x18000c21a  mov     rcx, rdi; hModule
0x18000c21d  call    cs:__imp_GetProcAddress
0x18000c223  mov     [rsi], rax
0x18000c226  inc     r14
0x18000c229  lea     rsi, [rsi+8]
0x18000c22d  lea     rax, __ImageBase
0x18000c234  cmp     r14, 3
0x18000c238  jnz     short loc_18000C212
0x18000c23a  cmp     qword ptr [rbx+90h], 0
0x18000c242  jz      short loc_18000C258
0x18000c244  cmp     qword ptr [rbx+98h], 0
0x18000c24c  jz      short loc_18000C258
0x18000c24e  cmp     qword ptr [rbx+0A0h], 0
0x18000c256  jnz     short loc_18000C27D
0x18000c258  or      dword ptr [rbx+8], 1
0x18000c25c  mov     qword ptr [rbx+90h], 0
0x18000c267  mov     qword ptr [rbx+98h], 0
0x18000c272  mov     qword ptr [rbx+0A0h], 0
0x18000c27d  lea     rcx, critsec; lpCriticalSection
0x18000c284  call    cs:__imp_EnterCriticalSection
0x18000c28a  mov     rax, cs:gpCMMChain
0x18000c291  lea     rcx, critsec; lpCriticalSection
0x18000c298  mov     [rbx+0A8h], rax
0x18000c29f  mov     cs:gpCMMChain, rbx
0x18000c2a6  call    cs:__imp_LeaveCriticalSection
0x18000c2ac  jmp     short loc_18000C2D4
0x18000c2ae  test    rbx, rbx
0x18000c2b1  jz      short loc_18000C2C6
0x18000c2b3  dec     dword ptr [rbx+4]
0x18000c2b6  mov     rcx, rbx; lpMem
0x18000c2b9  mov     dword ptr [rbx], 0
0x18000c2bf  call    MemFree
0x18000c2c4  xor     ebx, ebx
0x18000c2c6  test    rdi, rdi
0x18000c2c9  jz      short loc_18000C2D4
0x18000c2cb  mov     rcx, rdi; hLibModule
0x18000c2ce  call    cs:__imp_FreeLibrary
0x18000c2d4  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18000c2d9  test    rcx, rcx
0x18000c2dc  jz      short loc_18000C2E4
0x18000c2de  call    cs:__imp_RegCloseKey
0x18000c2e4  mov     rax, rbx
0x18000c2e7  mov     rcx, [rbp+1B0h+var_40]
0x18000c2ee  xor     rcx, rsp; StackCookie
0x18000c2f1  call    __security_check_cookie
0x18000c2f6  add     rsp, 288h
0x18000c2fd  pop     r15
0x18000c2ff  pop     r14
0x18000c301  pop     rdi
0x18000c302  pop     rsi
0x18000c303  pop     rbx
0x18000c304  pop     rbp
0x18000c305  retn
```
