# OpenPrinterIfNoCacheHandle(ushort const *,void *,void * *,void * *)

- ea: `0x14005954c`
- end: `0x140059627`
- name: `?OpenPrinterIfNoCacheHandle@@YAJPEBGPEAXPEAPEAX2@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPWSTR pPrinterName, void *, void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140059214`

## callees

- `0x14005757c`
- `0x14005954c`
- `0x140063010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x1400595d5`
- `KERNEL32!FreeLibrary` at `0x1400595d5`
- `KERNEL32!GetLastError` at `0x1400595ff`
- `KERNEL32!GetLastError` at `0x1400595ff`
- `KERNEL32!GetProcAddress` at `0x140059599`
- `KERNEL32!GetProcAddress` at `0x140059599`
- `WINSPOOL!OpenPrinterW` at `0x1400595ed`
- `WINSPOOL!OpenPrinterW` at `0x1400595ed`

## pseudocode

```c
__int64 __fastcall OpenPrinterIfNoCacheHandle(LPWSTR pPrinterName, void *a2, void **a3, void **a4)
{
  int v8; // ebx
  FARPROC ProcAddress; // rax
  char v10; // di
  signed int LastError; // eax
  int v13; // [rsp+58h] [rbp+10h] BYREF
  HMODULE hModule; // [rsp+60h] [rbp+18h] BYREF

  *a3 = a2;
  *a4 = 0;
  hModule = 0;
  v8 = LoadLibraryFromSystemDirectory(pPrinterName, &hModule);
  if ( v8 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, (LPCSTR)0x152);
    if ( ProcAddress )
    {
      v13 = 0;
      v10 = 0;
      v8 = ((__int64 (__fastcall *)(void *, int *))ProcAddress)(a2, &v13);
      if ( v8 >= 0 )
        v10 = v13 & 1;
    }
    else
    {
      v10 = 1;
    }
    FreeLibrary(hModule);
    if ( v8 >= 0 && v10 )
    {
      if ( OpenPrinterW(pPrinterName, a4, 0) )
      {
        *a3 = *a4;
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14005954c  mov     [rsp+arg_0], rbx
0x140059551  push    rbp
0x140059552  push    rsi
0x140059553  push    rdi
0x140059554  push    r14
0x140059556  push    r15
0x140059558  sub     rsp, 20h
0x14005955c  mov     rbp, rdx
0x14005955f  mov     [r8], rdx
0x140059562  lea     rdx, [rsp+48h+hModule]
0x140059567  mov     qword ptr [r9], 0
0x14005956e  mov     rsi, r9
0x140059571  mov     [rsp+48h+hModule], 0
0x14005957a  mov     r14, r8
0x14005957d  mov     r15, rcx
0x140059580  call    LoadLibraryFromSystemDirectory
0x140059585  mov     ebx, eax
0x140059587  test    eax, eax
0x140059589  js      loc_140059614
0x14005958f  mov     rcx, [rsp+48h+hModule]; hModule
0x140059594  mov     edx, 152h; lpProcName
0x140059599  call    cs:__imp_GetProcAddress
0x14005959f  test    rax, rax
0x1400595a2  jz      short loc_1400595CD
0x1400595a4  lea     rdx, [rsp+48h+arg_8]
0x1400595a9  mov     [rsp+48h+arg_8], 0
0x1400595b1  mov     rcx, rbp
0x1400595b4  xor     dil, dil
0x1400595b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400595bc  mov     ebx, eax
0x1400595be  test    eax, eax
0x1400595c0  js      short loc_1400595D0
0x1400595c2  mov     dil, byte ptr [rsp+48h+arg_8]
0x1400595c7  and     dil, 1
0x1400595cb  jmp     short loc_1400595D0
0x1400595cd  mov     dil, 1
0x1400595d0  mov     rcx, [rsp+48h+hModule]; hLibModule
0x1400595d5  call    cs:__imp_FreeLibrary
0x1400595db  test    ebx, ebx
0x1400595dd  js      short loc_140059614
0x1400595df  test    dil, dil
0x1400595e2  jz      short loc_140059614
0x1400595e4  xor     r8d, r8d; pDefault
0x1400595e7  mov     rdx, rsi; phPrinter
0x1400595ea  mov     rcx, r15; pPrinterName
0x1400595ed  call    cs:__imp_OpenPrinterW
0x1400595f3  test    eax, eax
0x1400595f5  jz      short loc_1400595FF
0x1400595f7  mov     rax, [rsi]
0x1400595fa  mov     [r14], rax
0x1400595fd  jmp     short loc_140059614
0x1400595ff  call    cs:__imp_GetLastError
0x140059605  mov     ebx, eax
0x140059607  test    eax, eax
0x140059609  jle     short loc_140059614
0x14005960b  movzx   ebx, ax
0x14005960e  or      ebx, 80070000h
0x140059614  mov     eax, ebx
0x140059616  mov     rbx, [rsp+48h+arg_0]
0x14005961b  add     rsp, 20h
0x14005961f  pop     r15
0x140059621  pop     r14
0x140059623  pop     rdi
0x140059624  pop     rsi
0x140059625  pop     rbp
0x140059626  retn
```
