# IsFileInDriverStoreOrDriverPath

- ea: `0x180074420`
- end: `0x1800745a4`
- name: `IsFileInDriverStoreOrDriverPath`
- size: `388`
- prototype: `__int64 __fastcall(LPCWCH lpString2)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006ed08`

## callees

- `0x180074420`
- `0x1800ad700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744fa`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007449d`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007457c`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007449d`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18007457c`
- `SPOOLSS!DllFreeSplMem` at `0x1800744ad`
- `SPOOLSS!DllFreeSplMem` at `0x18007458f`
- `SPOOLSS!DllFreeSplMem` at `0x1800744ad`
- `SPOOLSS!DllFreeSplMem` at `0x18007458f`
- `SPOOLSS!DllAllocSplMem` at `0x18007450c`
- `SPOOLSS!DllAllocSplMem` at `0x18007450c`
- `SPOOLSS!GetPrinterDriverDirectoryW` at `0x1800744f0`
- `SPOOLSS!GetPrinterDriverDirectoryW` at `0x18007453c`
- `SPOOLSS!GetPrinterDriverDirectoryW` at `0x1800744f0`
- `SPOOLSS!GetPrinterDriverDirectoryW` at `0x18007453c`

## pseudocode

```c
_BOOL8 __fastcall IsFileInDriverStoreOrDriverPath(LPCWCH lpString2)
{
  unsigned __int64 cchCount2; // rbx
  BOOL v3; // esi
  unsigned __int64 v4; // rdi
  LPCWCH v5; // rbp
  WCHAR *v6; // rbx
  unsigned __int64 v7; // r9
  LPCWCH lpString1; // [rsp+98h] [rbp+10h] BYREF

  cchCount2 = -1;
  v3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( lpString2[v4] );
  lpString1 = 0;
  if ( (int)NPackageInstallLocalspl::TDriverStore::GetDriverStoreRootPath((unsigned __int16 **)&lpString1) < 0 )
  {
    v6 = (WCHAR *)lpString1;
LABEL_11:
    LODWORD(lpString1) = 0;
    if ( !GetPrinterDriverDirectoryW(0, 0, 1u, 0, 0, (LPDWORD)&lpString1) && GetLastError() == 122 )
      v6 = (WCHAR *)DllAllocSplMem((unsigned int)lpString1);
    if ( v6 )
    {
      if ( GetPrinterDriverDirectoryW(0, 0, 1u, (LPBYTE)v6, (DWORD)lpString1, (LPDWORD)&lpString1) )
      {
        v7 = ((unsigned __int64)(unsigned int)lpString1 >> 1) - 1;
        if ( v7 < v4 )
          v3 = CompareStringEx(0, 0x10u, v6, v7, lpString2, ((unsigned int)lpString1 >> 1) - 1, 0, 0, 0) == 2;
      }
    }
    DllFreeSplMem(v6);
    return v3;
  }
  v5 = lpString1;
  do
    ++cchCount2;
  while ( lpString1[cchCount2] );
  if ( cchCount2 < v4 )
    LOBYTE(v3) = CompareStringEx(0, 0x10u, lpString1, cchCount2, lpString2, cchCount2, 0, 0, 0) == 2;
  DllFreeSplMem(v5);
  v6 = 0;
  if ( !v3 )
    goto LABEL_11;
  return v3;
}

```

## disassembly

```asm
0x180074420  push    rbx
0x180074422  push    rbp
0x180074423  push    rsi
0x180074424  push    rdi
0x180074425  push    r14
0x180074427  push    r15
0x180074429  sub     rsp, 58h
0x18007442d  xor     r15d, r15d
0x180074430  mov     r14, rcx
0x180074433  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180074437  mov     esi, r15d
0x18007443a  mov     rdi, rbx
0x18007443d  inc     rdi
0x180074440  cmp     [rcx+rdi*2], r15w
0x180074445  jnz     short loc_18007443D
0x180074447  lea     rcx, [rsp+88h+lpString1]; unsigned __int16 **
0x18007444f  mov     [rsp+88h+lpString1], r15
0x180074457  call    ?GetDriverStoreRootPath@TDriverStore@NPackageInstallLocalspl@@SAJPEAPEAG@Z; NPackageInstallLocalspl::TDriverStore::GetDriverStoreRootPath(ushort * *)
0x18007445c  test    eax, eax
0x18007445e  js      short loc_1800744C0
0x180074460  mov     rbp, [rsp+88h+lpString1]
0x180074468  inc     rbx
0x18007446b  cmp     [rbp+rbx*2+0], r15w
0x180074471  jnz     short loc_180074468
0x180074473  cmp     rbx, rdi
0x180074476  jnb     short loc_1800744AA
0x180074478  mov     [rsp+88h+lParam], r15; lParam
0x18007447d  mov     r9d, ebx; cchCount1
0x180074480  mov     [rsp+88h+lpReserved], r15; lpReserved
0x180074485  mov     r8, rbp; lpString1
0x180074488  mov     [rsp+88h+lpVersionInformation], r15; lpVersionInformation
0x18007448d  mov     edx, 10h; dwCmpFlags
0x180074492  mov     [rsp+88h+cchCount2], ebx; cchCount2
0x180074496  xor     ecx, ecx; lpLocaleName
0x180074498  mov     [rsp+88h+lpString2], r14; lpString2
0x18007449d  call    cs:__imp_CompareStringEx
0x1800744a3  cmp     eax, 2
0x1800744a6  setz    sil
0x1800744aa  mov     rcx, rbp
0x1800744ad  call    cs:__imp_DllFreeSplMem
0x1800744b3  mov     rbx, r15
0x1800744b6  test    esi, esi
0x1800744b8  jnz     loc_180074595
0x1800744be  jmp     short loc_1800744C8
0x1800744c0  mov     rbx, [rsp+88h+lpString1]
0x1800744c8  xor     r9d, r9d; pDriverDirectory
0x1800744cb  mov     dword ptr [rsp+88h+lpString1], r15d
0x1800744d3  lea     rax, [rsp+88h+lpString1]
0x1800744db  xor     edx, edx; pEnvironment
0x1800744dd  mov     qword ptr [rsp+88h+cchCount2], rax; pcbNeeded
0x1800744e2  xor     ecx, ecx; pName
0x1800744e4  mov     dword ptr [rsp+88h+lpString2], r15d; cbBuf
0x1800744e9  lea     ebp, [r9+1]
0x1800744ed  mov     r8d, ebp; Level
0x1800744f0  call    cs:__imp_GetPrinterDriverDirectoryW
0x1800744f6  test    eax, eax
0x1800744f8  jnz     short loc_180074515
0x1800744fa  call    cs:__imp_GetLastError
0x180074500  cmp     eax, 7Ah ; 'z'
0x180074503  jnz     short loc_180074515
0x180074505  mov     ecx, dword ptr [rsp+88h+lpString1]
0x18007450c  call    cs:__imp_DllAllocSplMem
0x180074512  mov     rbx, rax
0x180074515  test    rbx, rbx
0x180074518  jz      short loc_18007458C
0x18007451a  lea     rax, [rsp+88h+lpString1]
0x180074522  mov     r9, rbx; pDriverDirectory
0x180074525  mov     qword ptr [rsp+88h+cchCount2], rax; pcbNeeded
0x18007452a  mov     r8d, ebp; Level
0x18007452d  mov     eax, dword ptr [rsp+88h+lpString1]
0x180074534  xor     edx, edx; pEnvironment
0x180074536  xor     ecx, ecx; pName
0x180074538  mov     dword ptr [rsp+88h+lpString2], eax; cbBuf
0x18007453c  call    cs:__imp_GetPrinterDriverDirectoryW
0x180074542  test    eax, eax
0x180074544  jz      short loc_18007458C
0x180074546  mov     r9d, dword ptr [rsp+88h+lpString1]
0x18007454e  shr     r9, 1
0x180074551  dec     r9; cchCount1
0x180074554  cmp     r9, rdi
0x180074557  jnb     short loc_18007458C
0x180074559  mov     [rsp+88h+lParam], r15; lParam
0x18007455e  mov     r8, rbx; lpString1
0x180074561  mov     [rsp+88h+lpReserved], r15; lpReserved
0x180074566  mov     edx, 10h; dwCmpFlags
0x18007456b  mov     [rsp+88h+lpVersionInformation], r15; lpVersionInformation
0x180074570  xor     ecx, ecx; lpLocaleName
0x180074572  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x180074577  mov     [rsp+88h+lpString2], r14; lpString2
0x18007457c  call    cs:__imp_CompareStringEx
0x180074582  cmp     eax, 2
0x180074585  mov     esi, r15d
0x180074588  setz    sil
0x18007458c  mov     rcx, rbx
0x18007458f  call    cs:__imp_DllFreeSplMem
0x180074595  mov     eax, esi
0x180074597  add     rsp, 58h
0x18007459b  pop     r15
0x18007459d  pop     r14
0x18007459f  pop     rdi
0x1800745a0  pop     rsi
0x1800745a1  pop     rbp
0x1800745a2  pop     rbx
0x1800745a3  retn
```
