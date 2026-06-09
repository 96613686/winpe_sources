# LoadPreloadDlls(HINSTANCE__ * * *)

- ea: `0x140001f54`
- end: `0x140002208`
- name: `?LoadPreloadDlls@@YAHPEAPEAPEAUHINSTANCE__@@@Z`
- size: `692`
- prototype: `__int64 __fastcall(HINSTANCE **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400024d0`

## callees

- `0x140001f54`
- `0x140002850`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x140001fef`
- `ADVAPI32!RegQueryValueExA` at `0x140002043`
- `ADVAPI32!RegQueryValueExA` at `0x140001fef`
- `ADVAPI32!RegQueryValueExA` at `0x140002043`
- `ADVAPI32!RegCloseKey` at `0x1400021d2`
- `ADVAPI32!RegCloseKey` at `0x1400021d2`
- `ADVAPI32!RegOpenKeyExA` at `0x140001fb6`
- `ADVAPI32!RegOpenKeyExA` at `0x140001fb6`
- `KERNEL32!LocalAlloc` at `0x14000200e`
- `KERNEL32!LocalAlloc` at `0x1400020ad`
- `KERNEL32!LocalAlloc` at `0x14000200e`
- `KERNEL32!LocalAlloc` at `0x1400020ad`
- `KERNEL32!LoadLibraryA` at `0x1400020e2`
- `KERNEL32!LoadLibraryA` at `0x1400020e2`
- `KERNEL32!LocalFree` at `0x1400021e0`
- `KERNEL32!LocalFree` at `0x1400021e0`
- `msvcrt!sprintf_s` at `0x140002112`
- `msvcrt!sprintf_s` at `0x140002155`
- `msvcrt!sprintf_s` at `0x140002112`
- `msvcrt!sprintf_s` at `0x140002155`
- `iisutil!PuDbgPrint` at `0x140002146`
- `iisutil!PuDbgPrint` at `0x140002189`
- `iisutil!PuDbgPrint` at `0x140002146`
- `iisutil!PuDbgPrint` at `0x140002189`

## string_xrefs

- `0x140001f86`: `System\CurrentControlSet\Services\InetInfo\Parameters`
- `0x140001fe0`: `PreloadDlls`
- `0x14000203c`: `PreloadDlls`
- `0x14000210b`: `Preloading FAILED for DLL: %s\n`
- `0x14000212d`: `LoadPreloadDlls`
- `0x140002170`: `LoadPreloadDlls`
- `0x14000214e`: `Preloaded DLL: %s\n`

## pseudocode

```c
__int64 __fastcall LoadPreloadDlls(HINSTANCE **a1)
{
  unsigned int v1; // r13d
  unsigned int v3; // ebx
  BYTE *v4; // rdi
  int v5; // ecx
  BYTE *v6; // r8
  unsigned int v7; // r9d
  int v8; // eax
  HINSTANCE *v9; // rax
  DWORD v10; // edx
  BYTE *v11; // rsi
  const CHAR *v12; // r15
  int v13; // r14d
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  char Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF

  v1 = 0;
  *a1 = 0;
  hKey = 0;
  v3 = 1;
  cbData = 0;
  Type = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\InetInfo\\Parameters", 0, 1u, &hKey) )
  {
    cbData = 0;
    v4 = 0;
    if ( !RegQueryValueExA(hKey, "PreloadDlls", 0, &Type, 0, &cbData) && cbData > 2 )
    {
      v4 = (BYTE *)LocalAlloc(0, cbData);
      if ( !v4 || RegQueryValueExA(hKey, "PreloadDlls", 0, &Type, v4, &cbData) || Type != 7 || cbData <= 2 )
        goto LABEL_25;
      v5 = 0;
      v6 = v4;
      v7 = 0;
      v4[cbData - 1] = 0;
      v4[cbData - 2] = 0;
      if ( cbData != 1 )
      {
        do
        {
          v8 = v5 + 1;
          if ( *v6 )
            v8 = v5;
          ++v7;
          v5 = v8;
          ++v6;
        }
        while ( v7 < (unsigned __int64)cbData - 1 );
      }
      v9 = (HINSTANCE *)LocalAlloc(0, 8LL * (unsigned int)(v5 + 1));
      *a1 = v9;
      if ( v9 )
      {
        v10 = cbData;
        v11 = v4;
        v12 = (const CHAR *)v4;
        v13 = 0;
        if ( cbData != 1 )
        {
          do
          {
            if ( *v11 )
            {
              ++v11;
            }
            else
            {
              (*a1)[v13] = LoadLibraryA(v12);
              if ( (*a1)[v13] )
              {
                sprintf_s(Buffer, 0x100u, "Preloaded DLL: %s\n", v12);
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
                    1119,
                    "LoadPreloadDlls",
                    Buffer);
                ++v13;
              }
              else
              {
                sprintf_s(Buffer, 0x100u, "Preloading FAILED for DLL: %s\n", v12);
                if ( (g_dwDebugFlags & 3) != 0 )
                  PuDbgPrint(
                    g_pDebug,
                    "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx",
                    1115,
                    "LoadPreloadDlls",
                    Buffer);
              }
              v10 = cbData;
              v12 = (const CHAR *)++v11;
            }
            ++v1;
          }
          while ( v1 < (unsigned __int64)v10 - 1 );
        }
        (*a1)[v13] = 0;
      }
      else
      {
LABEL_25:
        v3 = 0;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( v4 )
      LocalFree(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x140001f54  push    rbp
0x140001f56  push    rbx
0x140001f57  push    rsi
0x140001f58  push    rdi
0x140001f59  push    r12
0x140001f5b  push    r13
0x140001f5d  push    r14
0x140001f5f  push    r15
0x140001f61  lea     rbp, [rsp-58h]
0x140001f66  sub     rsp, 158h
0x140001f6d  mov     rax, cs:__security_cookie
0x140001f74  xor     rax, rsp
0x140001f77  mov     [rbp+90h+var_50], rax
0x140001f7b  xor     r13d, r13d
0x140001f7e  lea     rax, [rsp+190h+hKey]
0x140001f83  mov     [rcx], r13
0x140001f86  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\In"...
0x140001f8d  mov     r12, rcx
0x140001f90  mov     [rsp+190h+hKey], r13
0x140001f95  mov     ebx, 1
0x140001f9a  mov     [rsp+190h+cbData], r13d
0x140001f9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140001fa6  mov     [rsp+190h+Type], r13d
0x140001fab  mov     r9d, ebx; samDesired
0x140001fae  mov     [rsp+190h+phkResult], rax; phkResult
0x140001fb3  xor     r8d, r8d; ulOptions
0x140001fb6  call    cs:__imp_RegOpenKeyExA
0x140001fbc  test    eax, eax
0x140001fbe  jnz     loc_1400021E6
0x140001fc4  mov     rcx, [rsp+190h+hKey]; hKey
0x140001fc9  lea     rax, [rsp+190h+cbData]
0x140001fce  mov     [rsp+190h+lpcbData], rax; lpcbData
0x140001fd3  lea     r9, [rsp+190h+Type]; lpType
0x140001fd8  xor     r8d, r8d; lpReserved
0x140001fdb  mov     [rsp+190h+phkResult], r13; lpData
0x140001fe0  lea     rdx, aPreloaddlls; "PreloadDlls"
0x140001fe7  mov     [rsp+190h+cbData], r13d
0x140001fec  mov     edi, r13d
0x140001fef  call    cs:__imp_RegQueryValueExA
0x140001ff5  test    eax, eax
0x140001ff7  jnz     loc_1400021C8
0x140001ffd  cmp     [rsp+190h+cbData], 2
0x140002002  jbe     loc_1400021C8
0x140002008  mov     edx, [rsp+190h+cbData]; uBytes
0x14000200c  xor     ecx, ecx; uFlags
0x14000200e  call    cs:__imp_LocalAlloc
0x140002014  mov     rdi, rax
0x140002017  test    rax, rax
0x14000201a  jz      loc_1400021C5
0x140002020  mov     rcx, [rsp+190h+hKey]; hKey
0x140002025  lea     rax, [rsp+190h+cbData]
0x14000202a  mov     [rsp+190h+lpcbData], rax; lpcbData
0x14000202f  lea     r9, [rsp+190h+Type]; lpType
0x140002034  xor     r8d, r8d; lpReserved
0x140002037  mov     [rsp+190h+phkResult], rdi; lpData
0x14000203c  lea     rdx, aPreloaddlls; "PreloadDlls"
0x140002043  call    cs:__imp_RegQueryValueExA
0x140002049  test    eax, eax
0x14000204b  jnz     loc_1400021C5
0x140002051  cmp     [rsp+190h+Type], 7
0x140002056  jnz     loc_1400021C5
0x14000205c  cmp     [rsp+190h+cbData], 2
0x140002061  jbe     loc_1400021C5
0x140002067  mov     eax, [rsp+190h+cbData]
0x14000206b  mov     ecx, r13d
0x14000206e  mov     r8, rdi
0x140002071  mov     r9d, r13d
0x140002074  mov     [rax+rdi-1], r13b
0x140002079  mov     eax, [rsp+190h+cbData]
0x14000207d  mov     [rax+rdi-2], r13b
0x140002082  mov     edx, [rsp+190h+cbData]
0x140002086  sub     rdx, rbx
0x140002089  jz      short loc_1400020A4
0x14000208b  cmp     [r8], r13b
0x14000208e  lea     eax, [rcx+1]
0x140002091  cmovnz  eax, ecx
0x140002094  add     r9d, ebx
0x140002097  mov     ecx, eax
0x140002099  add     r8, rbx
0x14000209c  mov     eax, r9d
0x14000209f  cmp     rax, rdx
0x1400020a2  jb      short loc_14000208B
0x1400020a4  lea     edx, [rcx+1]
0x1400020a7  xor     ecx, ecx; uFlags
0x1400020a9  shl     rdx, 3; uBytes
0x1400020ad  call    cs:__imp_LocalAlloc
0x1400020b3  mov     [r12], rax
0x1400020b7  test    rax, rax
0x1400020ba  jz      loc_1400021C5
0x1400020c0  mov     edx, [rsp+190h+cbData]
0x1400020c4  mov     rsi, rdi
0x1400020c7  mov     r15, rdi
0x1400020ca  mov     r14d, r13d
0x1400020cd  cmp     rdx, rbx
0x1400020d0  jz      loc_1400021B5
0x1400020d6  cmp     byte ptr [rsi], 0
0x1400020d9  jnz     loc_14000219E
0x1400020df  mov     rcx, r15; lpLibFileName
0x1400020e2  call    cs:__imp_LoadLibraryA
0x1400020e8  mov     rcx, [r12]
0x1400020ec  mov     r9, r15
0x1400020ef  mov     edx, r14d
0x1400020f2  mov     [rcx+rdx*8], rax
0x1400020f6  lea     rcx, [rsp+190h+Buffer]; Buffer
0x1400020fb  mov     rax, [r12]
0x1400020ff  cmp     qword ptr [rax+rdx*8], 0
0x140002104  mov     edx, 100h; BufferCount
0x140002109  jnz     short loc_14000214E
0x14000210b  lea     r8, aPreloadingFail; "Preloading FAILED for DLL: %s\n"
0x140002112  call    cs:__imp_sprintf_s
0x140002118  test    cs:g_dwDebugFlags, 3
0x14000211f  jz      short loc_140002192
0x140002121  mov     rcx, cs:g_pDebug
0x140002128  lea     rax, [rsp+190h+Buffer]
0x14000212d  lea     r9, aLoadpreloaddll; "LoadPreloadDlls"
0x140002134  mov     [rsp+190h+phkResult], rax
0x140002139  mov     r8d, 45Bh
0x14000213f  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140002146  call    cs:__imp_PuDbgPrint
0x14000214c  jmp     short loc_140002192
0x14000214e  lea     r8, aPreloadedDllS; "Preloaded DLL: %s\n"
0x140002155  call    cs:__imp_sprintf_s
0x14000215b  test    cs:g_dwDebugFlags, 3
0x140002162  jz      short loc_14000218F
0x140002164  mov     rcx, cs:g_pDebug
0x14000216b  lea     rax, [rsp+190h+Buffer]
0x140002170  lea     r9, aLoadpreloaddll; "LoadPreloadDlls"
0x140002177  mov     [rsp+190h+phkResult], rax
0x14000217c  mov     r8d, 45Fh
0x140002182  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140002189  call    cs:__imp_PuDbgPrint
0x14000218f  add     r14d, ebx
0x140002192  mov     edx, [rsp+190h+cbData]
0x140002196  inc     rsi
0x140002199  mov     r15, rsi
0x14000219c  jmp     short loc_1400021A1
0x14000219e  inc     rsi
0x1400021a1  add     r13d, ebx
0x1400021a4  mov     ecx, edx
0x1400021a6  sub     rcx, rbx
0x1400021a9  mov     eax, r13d
0x1400021ac  cmp     rax, rcx
0x1400021af  jb      loc_1400020D6
0x1400021b5  mov     rax, [r12]
0x1400021b9  xor     r13d, r13d
0x1400021bc  mov     ecx, r14d
0x1400021bf  mov     [rax+rcx*8], r13
0x1400021c3  jmp     short loc_1400021C8
0x1400021c5  mov     ebx, r13d
0x1400021c8  mov     rcx, [rsp+190h+hKey]; hKey
0x1400021cd  test    rcx, rcx
0x1400021d0  jz      short loc_1400021D8
0x1400021d2  call    cs:__imp_RegCloseKey
0x1400021d8  test    rdi, rdi
0x1400021db  jz      short loc_1400021E6
0x1400021dd  mov     rcx, rdi; hMem
0x1400021e0  call    cs:__imp_LocalFree
0x1400021e6  mov     eax, ebx
0x1400021e8  mov     rcx, [rbp+90h+var_50]
0x1400021ec  xor     rcx, rsp; StackCookie
0x1400021ef  call    __security_check_cookie
0x1400021f4  add     rsp, 158h
0x1400021fb  pop     r15
0x1400021fd  pop     r14
0x1400021ff  pop     r13
0x140002201  pop     r12
0x140002203  pop     rdi
0x140002204  pop     rsi
0x140002205  pop     rbx
0x140002206  pop     rbp
0x140002207  retn
```
