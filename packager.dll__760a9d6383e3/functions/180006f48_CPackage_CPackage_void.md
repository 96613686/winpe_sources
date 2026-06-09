# CPackage::CPackage(void)

- ea: `0x180006f48`
- end: `0x180007104`
- name: `??0CPackage@@QEAA@XZ`
- size: `444`
- prototype: `CPackage *__fastcall(CPackage *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000a760`

## callees

- `0x180006f48`
- `0x18000a6ec`
- `0x18000a718`
- `0x18000cbf0`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180007057`
- `SHLWAPI!PathFindFileNameW` at `0x180007057`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007044`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180007044`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180007078`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x180007078`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180007098`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x180007098`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800070bb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800070bb`
- `KERNEL32!lstrcmpW` at `0x180007067`
- `KERNEL32!lstrcmpW` at `0x180007067`

## pseudocode

```c
CPackage *__fastcall CPackage::CPackage(CPackage *this)
{
  BOOL v1; // edi
  const WCHAR *FileNameW; // rax
  DWORD FileVersionInfoSizeW; // eax
  void *v5; // rsi
  unsigned int puLen; // [rsp+20h] [rbp-258h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-250h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-248h] BYREF

  *(_QWORD *)this = &CPackage::`vftable'{for `IEnumOLEVERB'};
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 1) = &CPackage::`vftable'{for `IOleCommandTarget'};
  v1 = 1;
  ++g_cRefThisDll;
  *((_QWORD *)this + 2) = &CPackage::`vftable'{for `IOleObject'};
  *((_DWORD *)this + 22) = 1;
  *((_QWORD *)this + 3) = &CPackage::`vftable'{for `IViewObject2'};
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 4) = &CPackage::`vftable'{for `IDataObject'};
  *((_QWORD *)this + 5) = &CPackage::`vftable'{for `IPersistStorage'};
  *((_QWORD *)this + 6) = &CPackage::`vftable'{for `IAdviseSink'};
  *((_QWORD *)this + 7) = &CPackage::`vftable'{for `IRunnableObject'};
  *((_QWORD *)this + 8) = &CPackage::`vftable'{for `IPersistFile'};
  *((_QWORD *)this + 9) = &CPackage::`vftable'{for `IExternalConnection'};
  *((_QWORD *)this + 10) = &CPackage::`vftable'{for `IOlePackagerLinkNotify'};
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_DWORD *)this + 48) = 0;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    FileNameW = PathFindFileNameW(Filename);
    if ( !lstrcmpW(L"EXCEL.EXE", FileNameW) )
    {
      FileVersionInfoSizeW = GetFileVersionInfoSizeW(Filename, 0);
      v5 = operator new(FileVersionInfoSizeW);
      GetFileVersionInfoW(Filename, 0, 0x104u, v5);
      lpBuffer = 0;
      puLen = 0;
      if ( VerQueryValueW(v5, L"\\", &lpBuffer, &puLen) )
        v1 = *((_DWORD *)lpBuffer + 3) < 0xA0000u;
      *((_DWORD *)this + 48) = v1;
      operator delete(v5);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180006f48  push    rbx
0x180006f4a  push    rbp
0x180006f4b  push    rsi
0x180006f4c  push    rdi
0x180006f4d  sub     rsp, 258h
0x180006f54  mov     rax, cs:__security_cookie
0x180006f5b  xor     rax, rsp
0x180006f5e  mov     [rsp+278h+var_38], rax
0x180006f66  xor     ebp, ebp
0x180006f68  lea     rax, ??_7CPackage@@6BIEnumOLEVERB@@@; const CPackage::`vftable'{for `IEnumOLEVERB'}
0x180006f6f  mov     [rcx], rax
0x180006f72  lea     rdx, [rsp+278h+Filename]; lpFilename
0x180006f77  lea     rax, ??_7CPackage@@6BIOleCommandTarget@@@; const CPackage::`vftable'{for `IOleCommandTarget'}
0x180006f7e  mov     [rcx+70h], rbp
0x180006f82  mov     [rcx+8], rax
0x180006f86  mov     edi, 1
0x180006f8b  add     cs:?g_cRefThisDll@@3JA, edi; long g_cRefThisDll
0x180006f91  lea     rax, ??_7CPackage@@6BIOleObject@@@; const CPackage::`vftable'{for `IOleObject'}
0x180006f98  mov     [rcx+10h], rax
0x180006f9c  mov     rbx, rcx
0x180006f9f  lea     rax, ??_7CPackage@@6BIViewObject2@@@; const CPackage::`vftable'{for `IViewObject2'}
0x180006fa6  mov     [rcx+58h], edi
0x180006fa9  mov     [rcx+18h], rax
0x180006fad  mov     r8d, 104h; nSize
0x180006fb3  lea     rax, ??_7CPackage@@6BIDataObject@@@; const CPackage::`vftable'{for `IDataObject'}
0x180006fba  mov     [rcx+78h], rbp
0x180006fbe  mov     [rcx+20h], rax
0x180006fc2  lea     rax, ??_7CPackage@@6BIPersistStorage@@@; const CPackage::`vftable'{for `IPersistStorage'}
0x180006fc9  mov     [rcx+28h], rax
0x180006fcd  lea     rax, ??_7CPackage@@6BIAdviseSink@@@; const CPackage::`vftable'{for `IAdviseSink'}
0x180006fd4  mov     [rcx+30h], rax
0x180006fd8  lea     rax, ??_7CPackage@@6BIRunnableObject@@@; const CPackage::`vftable'{for `IRunnableObject'}
0x180006fdf  mov     [rcx+38h], rax
0x180006fe3  lea     rax, ??_7CPackage@@6BIPersistFile@@@; const CPackage::`vftable'{for `IPersistFile'}
0x180006fea  mov     [rcx+40h], rax
0x180006fee  lea     rax, ??_7CPackage@@6BIExternalConnection@@@; const CPackage::`vftable'{for `IExternalConnection'}
0x180006ff5  mov     [rcx+48h], rax
0x180006ff9  lea     rax, ??_7CPackage@@6BIOlePackagerLinkNotify@@@; const CPackage::`vftable'{for `IOlePackagerLinkNotify'}
0x180007000  mov     [rcx+50h], rax
0x180007004  mov     [rcx+88h], rbp
0x18000700b  mov     [rcx+90h], rbp
0x180007012  mov     [rcx+0A0h], rbp
0x180007019  mov     [rcx+0A8h], rbp
0x180007020  mov     [rcx+0B0h], rbp
0x180007027  mov     [rcx+0B8h], rbp
0x18000702e  mov     [rcx+0E0h], rbp
0x180007035  mov     [rcx+0E8h], rbp
0x18000703c  mov     [rcx+0C0h], ebp
0x180007042  xor     ecx, ecx; hModule
0x180007044  call    cs:__imp_GetModuleFileNameW
0x18000704a  test    eax, eax
0x18000704c  jz      loc_1800070E5
0x180007052  lea     rcx, [rsp+278h+Filename]; pszPath
0x180007057  call    cs:__imp_PathFindFileNameW
0x18000705d  mov     rdx, rax; lpString2
0x180007060  lea     rcx, String1; "EXCEL.EXE"
0x180007067  call    cs:__imp_lstrcmpW
0x18000706d  test    eax, eax
0x18000706f  jnz     short loc_1800070E5
0x180007071  xor     edx, edx; lpdwHandle
0x180007073  lea     rcx, [rsp+278h+Filename]; lptstrFilename
0x180007078  call    cs:__imp_GetFileVersionInfoSizeW
0x18000707e  mov     ecx, eax; unsigned __int64
0x180007080  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007085  mov     r9, rax; lpData
0x180007088  lea     rcx, [rsp+278h+Filename]; lptstrFilename
0x18000708d  xor     edx, edx; dwHandle
0x18000708f  mov     r8d, 104h; dwLen
0x180007095  mov     rsi, rax
0x180007098  call    cs:__imp_GetFileVersionInfoW
0x18000709e  lea     r9, [rsp+278h+puLen]; puLen
0x1800070a3  mov     [rsp+278h+lpBuffer], rbp
0x1800070a8  lea     r8, [rsp+278h+lpBuffer]; lplpBuffer
0x1800070ad  mov     [rsp+278h+puLen], ebp
0x1800070b1  lea     rdx, SubBlock; "\\"
0x1800070b8  mov     rcx, rsi; pBlock
0x1800070bb  call    cs:__imp_VerQueryValueW
0x1800070c1  test    eax, eax
0x1800070c3  jz      short loc_1800070D7
0x1800070c5  mov     rax, [rsp+278h+lpBuffer]
0x1800070ca  mov     edi, ebp
0x1800070cc  cmp     dword ptr [rax+0Ch], 0A0000h
0x1800070d3  setb    dil
0x1800070d7  mov     rcx, rsi; lpMem
0x1800070da  mov     [rbx+0C0h], edi
0x1800070e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800070e5  mov     rax, rbx
0x1800070e8  mov     rcx, [rsp+278h+var_38]
0x1800070f0  xor     rcx, rsp; StackCookie
0x1800070f3  call    __security_check_cookie
0x1800070f8  add     rsp, 258h
0x1800070ff  pop     rdi
0x180007100  pop     rsi
0x180007101  pop     rbp
0x180007102  pop     rbx
0x180007103  retn
```
