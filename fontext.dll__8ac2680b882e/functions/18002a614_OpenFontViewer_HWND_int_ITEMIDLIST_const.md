# OpenFontViewer(HWND__ *,int,_ITEMIDLIST const *)

- ea: `0x18002a614`
- end: `0x18002a7c3`
- name: `?OpenFontViewer@@YAJPEAUHWND__@@HPEFBU_ITEMIDLIST@@@Z`
- size: `431`
- prototype: `int(HWND, int, const struct _ITEMIDLIST *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180010bd4`
- `0x18002a7cc`
- `0x18002bda0`

## callees

- `0x180006598`
- `0x180006624`
- `0x180006668`
- `0x18002265c`
- `0x18002a614`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `SHELL32!ShellExecuteExW` at `0x18002a78d`
- `SHELL32!ShellExecuteExW` at `0x18002a78d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a699`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002a699`

## pseudocode

```c
__int64 __fastcall OpenFontViewer(HWND a1, int a2, const struct _ITEMIDLIST *a3)
{
  int v6; // ebx
  const unsigned __int16 *v7; // r8
  unsigned int v8; // r11d
  SHELLEXECUTEINFOW pExecInfo; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v11[272]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v13[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v14[264]; // [rsp+6E0h] [rbp+5E0h] BYREF

  memset_0(v13, 0, 0x208u);
  v6 = FID_FileName(a3, 0, v13);
  if ( v6 >= 0 )
  {
    memset_0(Buffer, 0, 0x208u);
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      memset_0(v14, 0, 0x208u);
      v6 = StringCchPrintfW(v14, 0x104u, L"%ls\\%ls", Buffer, L"fontview.exe");
      if ( v6 >= 0 )
      {
        memset_0(v11, 0, 0x216u);
        v7 = L" /p /d ";
        if ( !a2 )
          v7 = L" /d ";
        v6 = StringCchCopyW(v11, 0x10Bu, v7);
        if ( v6 >= 0 )
        {
          v6 = StringCchCatW(v11, v8, v13);
          if ( v6 >= 0 )
          {
            v6 = -2147467259;
            memset_0(&pExecInfo, 0, sizeof(pExecInfo));
            pExecInfo.cbSize = 112;
            pExecInfo.lpFile = v14;
            pExecInfo.fMask = 512;
            pExecInfo.lpParameters = v11;
            pExecInfo.hwnd = a1;
            pExecInfo.nShow = 1;
            if ( ShellExecuteExW(&pExecInfo) )
              return 0;
          }
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002a614  mov     [rsp-8+arg_8], rbx
0x18002a619  mov     [rsp-8+arg_18], rsi
0x18002a61e  push    rbp
0x18002a61f  push    rdi
0x18002a620  push    r15
0x18002a622  lea     rbp, [rsp-800h]
0x18002a62a  sub     rsp, 900h
0x18002a631  mov     rax, cs:__security_cookie
0x18002a638  xor     rax, rsp
0x18002a63b  mov     [rbp+810h+var_20], rax
0x18002a642  mov     rbx, r8
0x18002a645  mov     edi, edx
0x18002a647  mov     rsi, rcx
0x18002a64a  mov     r15d, 208h
0x18002a650  mov     r8d, r15d; Size
0x18002a653  lea     rcx, [rbp+810h+var_440]; void *
0x18002a65a  xor     edx, edx; Val
0x18002a65c  call    memset_0
0x18002a661  lea     r8, [rbp+810h+var_440]; unsigned __int16 *
0x18002a668  xor     edx, edx; unsigned int
0x18002a66a  mov     rcx, rbx; struct _ITEMIDLIST *
0x18002a66d  call    ?FID_FileName@@YAJPEFBU_ITEMIDLIST@@IPEAGI@Z; FID_FileName(_ITEMIDLIST const *,uint,ushort *,uint)
0x18002a672  mov     ebx, eax
0x18002a674  test    eax, eax
0x18002a676  js      loc_18002A79A
0x18002a67c  mov     r8d, r15d; Size
0x18002a67f  lea     rcx, [rbp+810h+Buffer]; void *
0x18002a686  xor     edx, edx; Val
0x18002a688  call    memset_0
0x18002a68d  mov     edx, 104h; uSize
0x18002a692  lea     rcx, [rbp+810h+Buffer]; lpBuffer
0x18002a699  call    cs:__imp_GetSystemDirectoryW
0x18002a69f  test    eax, eax
0x18002a6a1  jz      loc_18002A79A
0x18002a6a7  mov     r8d, r15d; Size
0x18002a6aa  lea     rcx, [rbp+810h+var_230]; void *
0x18002a6b1  xor     edx, edx; Val
0x18002a6b3  call    memset_0
0x18002a6b8  lea     rax, aFontviewExe; "fontview.exe"
0x18002a6bf  mov     edx, 104h; unsigned __int64
0x18002a6c4  lea     r9, [rbp+810h+Buffer]
0x18002a6cb  mov     [rsp+910h+var_8F0], rax
0x18002a6d0  lea     r8, aLsLs; "%ls\\%ls"
0x18002a6d7  lea     rcx, [rbp+810h+var_230]; unsigned __int16 *
0x18002a6de  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a6e3  mov     ebx, eax
0x18002a6e5  test    eax, eax
0x18002a6e7  js      loc_18002A79A
0x18002a6ed  xor     edx, edx; Val
0x18002a6ef  lea     r8d, [r15+0Eh]; Size
0x18002a6f3  lea     rcx, [rbp+810h+var_870]; void *
0x18002a6f7  call    memset_0
0x18002a6fc  lea     rax, aD_0; " /d "
0x18002a703  test    edi, edi
0x18002a705  lea     r8, aPD; " /p /d "
0x18002a70c  mov     r11d, 10Bh
0x18002a712  cmovz   r8, rax; unsigned __int16 *
0x18002a716  lea     rcx, [rbp+810h+var_870]; unsigned __int16 *
0x18002a71a  mov     edx, r11d; unsigned __int64
0x18002a71d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a722  mov     ebx, eax
0x18002a724  test    eax, eax
0x18002a726  js      short loc_18002A79A
0x18002a728  lea     r8, [rbp+810h+var_440]; unsigned __int16 *
0x18002a72f  mov     edx, r11d; unsigned __int64
0x18002a732  lea     rcx, [rbp+810h+var_870]; unsigned __int16 *
0x18002a736  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a73b  mov     ebx, eax
0x18002a73d  test    eax, eax
0x18002a73f  js      short loc_18002A79A
0x18002a741  mov     edi, 70h ; 'p'
0x18002a746  lea     rcx, [rsp+910h+pExecInfo]; void *
0x18002a74b  mov     r8d, edi; Size
0x18002a74e  xor     edx, edx; Val
0x18002a750  mov     ebx, 80004005h
0x18002a755  call    memset_0
0x18002a75a  lea     rax, [rbp+810h+var_230]
0x18002a761  mov     [rsp+910h+pExecInfo.cbSize], edi
0x18002a765  mov     [rsp+910h+pExecInfo.lpFile], rax
0x18002a76a  lea     rcx, [rsp+910h+pExecInfo]; pExecInfo
0x18002a76f  lea     rax, [rbp+810h+var_870]
0x18002a773  mov     [rsp+910h+pExecInfo.fMask], 200h
0x18002a77b  mov     [rsp+910h+pExecInfo.lpParameters], rax
0x18002a780  mov     [rsp+910h+pExecInfo.hwnd], rsi
0x18002a785  mov     [rsp+910h+pExecInfo.nShow], 1
0x18002a78d  call    cs:__imp_ShellExecuteExW
0x18002a793  xor     ecx, ecx
0x18002a795  test    eax, eax
0x18002a797  cmovnz  ebx, ecx
0x18002a79a  mov     eax, ebx
0x18002a79c  mov     rcx, [rbp+810h+var_20]
0x18002a7a3  xor     rcx, rsp; StackCookie
0x18002a7a6  call    __security_check_cookie
0x18002a7ab  lea     r11, [rsp+910h+var_10]
0x18002a7b3  mov     rbx, [r11+28h]
0x18002a7b7  mov     rsi, [r11+38h]
0x18002a7bb  mov     rsp, r11
0x18002a7be  pop     r15
0x18002a7c0  pop     rdi
0x18002a7c1  pop     rbp
0x18002a7c2  retn
```
