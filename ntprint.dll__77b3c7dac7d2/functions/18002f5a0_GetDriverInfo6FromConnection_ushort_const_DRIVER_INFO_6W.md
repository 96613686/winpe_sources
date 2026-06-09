# GetDriverInfo6FromConnection(ushort const *,_DRIVER_INFO_6W * *)

- ea: `0x18002f5a0`
- end: `0x18002f767`
- name: `?GetDriverInfo6FromConnection@@YAJPEBGPEAPEAU_DRIVER_INFO_6W@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, struct _DRIVER_INFO_6W **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f364`

## callees

- `0x18000b200`
- `0x1800206ec`
- `0x18002f5a0`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f637`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f637`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f74e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f698`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f70e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f70e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f6b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f6b7`
- `WINSPOOL!OpenPrinterW` at `0x18002f5f3`
- `WINSPOOL!OpenPrinterW` at `0x18002f5f3`
- `WINSPOOL!ClosePrinter` at `0x18002f734`
- `WINSPOOL!ClosePrinter` at `0x18002f734`

## pseudocode

```c
__int64 __fastcall GetDriverInfo6FromConnection(LPWSTR pPrinterName, struct _DRIVER_INFO_6W **a2)
{
  HMODULE LibraryW; // rdi
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v6; // rcx
  NCoreLibrary *v7; // rcx
  NCoreLibrary *v8; // rcx
  FARPROC ProcAddress; // rbp
  NCoreLibrary *v10; // rcx
  struct _DRIVER_INFO_6W *v11; // rax
  struct _DRIVER_INFO_6W *v12; // rsi
  NCoreLibrary *v13; // rcx
  SIZE_T uBytes; // [rsp+70h] [rbp+8h] BYREF
  HANDLE phPrinter; // [rsp+80h] [rbp+18h] BYREF

  LibraryW = 0;
  phPrinter = 0;
  LODWORD(uBytes) = 0;
  if ( pPrinterName && a2
    || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR((NCoreLibrary *)pPrinterName), LastErrorAsFailHR >= 0) )
  {
    *a2 = 0;
    if ( OpenPrinterW(pPrinterName, &phPrinter, 0)
      || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v6), LastErrorAsFailHR >= 0) )
    {
      LibraryW = IsolationAwareLoadLibraryW(L"winspool.drv");
      if ( LibraryW || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v7), LastErrorAsFailHR >= 0) )
      {
        ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xEA);
        if ( ProcAddress || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8), LastErrorAsFailHR >= 0) )
        {
          if ( ((unsigned int (__fastcall *)(HANDLE, __int64, __int64))ProcAddress)(
                 phPrinter,
                 PlatformEnv[MyPlatform],
                 6) )
          {
            LastErrorAsFailHR = -2147467259;
          }
          else if ( GetLastError() == 122
                 || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10), LastErrorAsFailHR >= 0) )
          {
            v11 = (struct _DRIVER_INFO_6W *)LocalAlloc(0x40u, (unsigned int)uBytes);
            v12 = v11;
            if ( v11 )
            {
              LastErrorAsFailHR = 0;
              if ( ((unsigned int (__fastcall *)(HANDLE, __int64, __int64, struct _DRIVER_INFO_6W *, _DWORD, SIZE_T *))ProcAddress)(
                     phPrinter,
                     PlatformEnv[MyPlatform],
                     6,
                     v11,
                     uBytes,
                     &uBytes)
                || (LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v13), LastErrorAsFailHR >= 0) )
              {
                *a2 = v12;
              }
              else
              {
                LocalFree(v12);
              }
            }
            else
            {
              LastErrorAsFailHR = -2147024882;
            }
          }
        }
      }
    }
  }
  if ( phPrinter )
  {
    ClosePrinter(phPrinter);
    phPrinter = 0;
  }
  if ( LibraryW )
    FreeLibrary(LibraryW);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18002f5a0  mov     rax, rsp
0x18002f5a3  mov     [rax+10h], rbx
0x18002f5a7  push    rbp
0x18002f5a8  push    rsi
0x18002f5a9  push    rdi
0x18002f5aa  push    r13
0x18002f5ac  push    r14
0x18002f5ae  sub     rsp, 40h
0x18002f5b2  xor     edi, edi
0x18002f5b4  mov     qword ptr [rax+18h], 0
0x18002f5bc  mov     dword ptr [rax+8], 0
0x18002f5c3  mov     r14, rdx
0x18002f5c6  mov     rsi, rcx
0x18002f5c9  test    rcx, rcx
0x18002f5cc  jz      short loc_18002F5D3
0x18002f5ce  test    rdx, rdx
0x18002f5d1  jnz     short loc_18002F5E2
0x18002f5d3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f5d8  mov     ebx, eax
0x18002f5da  test    eax, eax
0x18002f5dc  js      loc_18002F727
0x18002f5e2  xor     r8d, r8d; pDefault
0x18002f5e5  mov     [r14], rdi
0x18002f5e8  lea     rdx, [rsp+68h+phPrinter]; phPrinter
0x18002f5f0  mov     rcx, rsi; pPrinterName
0x18002f5f3  call    cs:__imp_OpenPrinterW
0x18002f5f9  test    eax, eax
0x18002f5fb  jnz     short loc_18002F60C
0x18002f5fd  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f602  mov     ebx, eax
0x18002f604  test    eax, eax
0x18002f606  js      loc_18002F727
0x18002f60c  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x18002f613  call    IsolationAwareLoadLibraryW
0x18002f618  mov     rdi, rax
0x18002f61b  test    rax, rax
0x18002f61e  jnz     short loc_18002F62F
0x18002f620  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f625  mov     ebx, eax
0x18002f627  test    eax, eax
0x18002f629  js      loc_18002F727
0x18002f62f  mov     edx, 0EAh; lpProcName
0x18002f634  mov     rcx, rdi; hModule
0x18002f637  call    cs:__imp_GetProcAddress
0x18002f63d  mov     rbp, rax
0x18002f640  test    rax, rax
0x18002f643  jnz     short loc_18002F654
0x18002f645  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f64a  mov     ebx, eax
0x18002f64c  test    eax, eax
0x18002f64e  js      loc_18002F727
0x18002f654  movsxd  rdx, cs:MyPlatform
0x18002f65b  lea     rax, [rsp+68h+uBytes]
0x18002f660  mov     rcx, [rsp+68h+phPrinter]
0x18002f668  lea     r13, PlatformEnv
0x18002f66f  mov     [rsp+68h+var_40], rax
0x18002f674  xor     r9d, r9d
0x18002f677  mov     rax, rbp
0x18002f67a  mov     [rsp+68h+var_48], 0
0x18002f682  mov     rdx, [r13+rdx*8+0]
0x18002f687  lea     r8d, [r9+6]
0x18002f68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f690  test    eax, eax
0x18002f692  jnz     loc_18002F722
0x18002f698  call    cs:__imp_GetLastError
0x18002f69e  cmp     eax, 7Ah ; 'z'
0x18002f6a1  jz      short loc_18002F6AE
0x18002f6a3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f6a8  mov     ebx, eax
0x18002f6aa  test    eax, eax
0x18002f6ac  js      short loc_18002F727
0x18002f6ae  mov     edx, dword ptr [rsp+68h+uBytes]; uBytes
0x18002f6b2  mov     ecx, 40h ; '@'; uFlags
0x18002f6b7  call    cs:__imp_LocalAlloc
0x18002f6bd  mov     rsi, rax
0x18002f6c0  test    rax, rax
0x18002f6c3  jz      short loc_18002F71B
0x18002f6c5  mov     ecx, dword ptr [rsp+68h+uBytes]
0x18002f6c9  lea     rax, [rsp+68h+uBytes]
0x18002f6ce  movsxd  rdx, cs:MyPlatform
0x18002f6d5  xor     ebx, ebx
0x18002f6d7  mov     [rsp+68h+var_40], rax
0x18002f6dc  mov     r9, rsi
0x18002f6df  mov     [rsp+68h+var_48], ecx
0x18002f6e3  mov     rax, rbp
0x18002f6e6  mov     rcx, [rsp+68h+phPrinter]
0x18002f6ee  mov     rdx, [r13+rdx*8+0]
0x18002f6f3  lea     r8d, [rbx+6]
0x18002f6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6fc  test    eax, eax
0x18002f6fe  jnz     short loc_18002F716
0x18002f700  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002f705  mov     ebx, eax
0x18002f707  test    eax, eax
0x18002f709  jns     short loc_18002F716
0x18002f70b  mov     rcx, rsi; hMem
0x18002f70e  call    cs:__imp_LocalFree
0x18002f714  jmp     short loc_18002F727
0x18002f716  mov     [r14], rsi
0x18002f719  jmp     short loc_18002F727
0x18002f71b  mov     ebx, 8007000Eh
0x18002f720  jmp     short loc_18002F727
0x18002f722  mov     ebx, 80004005h
0x18002f727  mov     rcx, [rsp+68h+phPrinter]; hPrinter
0x18002f72f  test    rcx, rcx
0x18002f732  jz      short loc_18002F746
0x18002f734  call    cs:__imp_ClosePrinter
0x18002f73a  mov     [rsp+68h+phPrinter], 0
0x18002f746  test    rdi, rdi
0x18002f749  jz      short loc_18002F754
0x18002f74b  mov     rcx, rdi; hLibModule
0x18002f74e  call    cs:__imp_FreeLibrary
0x18002f754  mov     eax, ebx
0x18002f756  mov     rbx, [rsp+68h+arg_8]
0x18002f75b  add     rsp, 40h
0x18002f75f  pop     r14
0x18002f761  pop     r13
0x18002f763  pop     rdi
0x18002f764  pop     rsi
0x18002f765  pop     rbp
0x18002f766  retn
```
