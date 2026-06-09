# Reg_FindGeneralFontEntryFromFile(ushort const *,int,ushort *,uint)

- ea: `0x180026420`
- end: `0x180026527`
- name: `?Reg_FindGeneralFontEntryFromFile@@YAJPEBGHPEAGI@Z`
- size: `263`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180007d30`

## callees

- `0x180006624`
- `0x1800139f4`
- `0x180025da8`
- `0x180026420`
- `0x180026864`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800264c4`
- `msvcrt!_wcsicmp` at `0x1800264c4`
- `SHLWAPI!PathFindFileNameW` at `0x180026468`
- `SHLWAPI!PathFindFileNameW` at `0x180026468`

## pseudocode

```c
__int64 __fastcall Reg_FindGeneralFontEntryFromFile(const unsigned __int16 *a1, int a2, unsigned __int16 *a3)
{
  const WCHAR *FileNameW; // rdi
  unsigned int v6; // ebx
  HKEY v8; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+28h] [rbp-D8h]
  void **v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v12[260]; // [rsp+3Ch] [rbp-C4h] BYREF
  wchar_t String1[526]; // [rsp+244h] [rbp+144h] BYREF

  FileNameW = a1;
  *a3 = 0;
  if ( PathIsInFontsDirectory(1, a1) )
    FileNameW = PathFindFileNameW(FileNameW);
  v11 = a2;
  memset_0(v12, 0, sizeof(v12));
  memset_0(String1, 0, 0x410u);
  v8 = 0;
  v10 = &CFontRegValue_General::`vftable';
  v9 = 0;
  while ( 1 )
  {
    v6 = CFontRegValueEnum::Next(&v8, (struct CFontRegValue *)&v10);
    if ( v6 )
      break;
    if ( !_wcsicmp(String1, FileNameW) )
    {
      v6 = StringCchCopyW(a3, 0x104u, v12);
      break;
    }
  }
  CFontRegValueEnum::Reset((CFontRegValueEnum *)&v8);
  return v6;
}

```

## disassembly

```asm
0x180026420  mov     [rsp-8+arg_8], rbx
0x180026425  push    rbp
0x180026426  push    rsi
0x180026427  push    rdi
0x180026428  lea     rbp, [rsp-570h]
0x180026430  sub     rsp, 670h
0x180026437  mov     rax, cs:__security_cookie
0x18002643e  xor     rax, rsp
0x180026441  mov     [rbp+580h+var_20], rax
0x180026448  xor     eax, eax
0x18002644a  mov     ebx, edx
0x18002644c  mov     rdi, rcx
0x18002644f  mov     [r8], ax
0x180026453  mov     rdx, rcx; unsigned __int16 *
0x180026456  mov     rsi, r8
0x180026459  lea     ecx, [rax+1]; int
0x18002645c  call    ?PathIsInFontsDirectory@@YA_NHPEBG@Z; PathIsInFontsDirectory(int,ushort const *)
0x180026461  test    al, al
0x180026463  jz      short loc_180026471
0x180026465  mov     rcx, rdi; pszPath
0x180026468  call    cs:__imp_PathFindFileNameW
0x18002646e  mov     rdi, rax
0x180026471  xor     edx, edx; Val
0x180026473  mov     [rsp+680h+var_648], ebx
0x180026477  mov     r8d, 208h; Size
0x18002647d  lea     rcx, [rsp+680h+var_644]; void *
0x180026482  call    memset_0
0x180026487  xor     edx, edx; Val
0x180026489  lea     rcx, [rbp+580h+String1]; void *
0x180026490  mov     r8d, 410h; Size
0x180026496  call    memset_0
0x18002649b  lea     rax, ??_7CFontRegValue_General@@6B@; const CFontRegValue_General::`vftable'
0x1800264a2  mov     [rsp+680h+var_660], 0
0x1800264ab  mov     [rsp+680h+var_650], rax
0x1800264b0  mov     [rsp+680h+var_658], 0
0x1800264b8  jmp     short loc_1800264CE
0x1800264ba  mov     rdx, rdi; String2
0x1800264bd  lea     rcx, [rbp+580h+String1]; String1
0x1800264c4  call    cs:__imp__wcsicmp
0x1800264ca  test    eax, eax
0x1800264cc  jz      short loc_1800264E5
0x1800264ce  lea     rdx, [rsp+680h+var_650]; struct CFontRegValue *
0x1800264d3  lea     rcx, [rsp+680h+var_660]; this
0x1800264d8  call    ?Next@CFontRegValueEnum@@QEAAJPEAVCFontRegValue@@@Z; CFontRegValueEnum::Next(CFontRegValue *)
0x1800264dd  mov     ebx, eax
0x1800264df  test    eax, eax
0x1800264e1  jz      short loc_1800264BA
0x1800264e3  jmp     short loc_1800264F9
0x1800264e5  lea     r8, [rsp+680h+var_644]; unsigned __int16 *
0x1800264ea  mov     edx, 104h; unsigned __int64
0x1800264ef  mov     rcx, rsi; unsigned __int16 *
0x1800264f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800264f7  mov     ebx, eax
0x1800264f9  lea     rcx, [rsp+680h+var_660]; this
0x1800264fe  call    ?Reset@CFontRegValueEnum@@QEAAXXZ; CFontRegValueEnum::Reset(void)
0x180026503  mov     eax, ebx
0x180026505  mov     rcx, [rbp+580h+var_20]
0x18002650c  xor     rcx, rsp; StackCookie
0x18002650f  call    __security_check_cookie
0x180026514  mov     rbx, [rsp+680h+arg_8]
0x18002651c  add     rsp, 670h
0x180026523  pop     rdi
0x180026524  pop     rsi
0x180026525  pop     rbp
0x180026526  retn
```
