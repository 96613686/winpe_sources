# HttpOpenFileHandle(ushort const *,ushort const *,ulong,void * *,void * *)

- ea: `0x18041baf0`
- end: `0x18041bde4`
- name: `?HttpOpenFileHandle@@YA_NPEBG0KPEAPEAX1@Z`
- size: `756`
- prototype: `bool __usercall@<al>(wchar_t *String1@<rcx>, wchar_t *@<rdx>, unsigned int@<r8d>, void **@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18041c060`

## callees

- `0x18007cf9c`
- `0x18007daa4`
- `0x18008d550`
- `0x1800f0f40`
- `0x1800f2560`
- `0x18041baf0`
- `0x18041c610`
- `0x1804da3af`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18041bc2c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18041bdb4`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18041bc2c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18041bdb4`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18041bb75`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18041bb75`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bb9b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bbc1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bbe7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bc0d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bb9b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bbc1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bbe7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18041bc0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041bd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041bd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041bd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18041bd98`

## string_xrefs

- `0x18041bbd9`: `httpReadFile`
- `0x18041bb91`: `httpOpenFileHandleW`
- `0x18041bb6e`: `symsrv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall HttpOpenFileHandle(wchar_t *String1, wchar_t *a2, __int64 a3, void **a4, void **a5)
{
  HMODULE Library; // rax
  __int64 v10; // rbx
  unsigned __int64 v11; // rdx
  wchar_t *i; // rcx
  wchar_t *v13; // rax
  const unsigned __int16 *v14; // r10
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rdx
  _QWORD v17[3]; // [rsp+40h] [rbp-198h] BYREF
  char v18; // [rsp+58h] [rbp-180h] BYREF

  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
    (unsigned int)v17,
    (unsigned int)&v18,
    150,
    (_DWORD)a4,
    1);
  if ( g_SymSrv == (HMODULE)-1LL )
    goto LABEL_9;
  if ( !g_SymSrv )
  {
    Library = LoadLibraryExW(L"symsrv.dll", 0, 0);
    g_SymSrv = Library;
    if ( !Library )
    {
LABEL_9:
      DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v17);
      return 0;
    }
    g_HttpOpenFileHandle = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **, void **))GetProcAddress(Library, "httpOpenFileHandleW");
    if ( !g_HttpOpenFileHandle
      || (g_HttpQueryDataAvailable = (int (*)(void *, unsigned int *, unsigned int, unsigned __int64))GetProcAddress(g_SymSrv, "httpQueryDataAvailable")) == 0
      || (g_HttpReadFile = (int (*)(void *, void *, unsigned int, unsigned int *))GetProcAddress(
                                                                                    g_SymSrv,
                                                                                    "httpReadFile")) == 0
      || (g_HttpCloseHandle = (int (*)(void *))GetProcAddress(g_SymSrv, "httpCloseHandle")) == 0 )
    {
      FreeLibrary(g_SymSrv);
      g_SymSrv = (HMODULE)-1LL;
      goto LABEL_9;
    }
  }
  if ( !g_HttpOpenFileHandle || !DbsDynamicString<unsigned short>::CopyStr(v17, a2, 0xFFFFFFFFLL) )
    goto LABEL_9;
  if ( !String1 || !*String1 )
    goto LABEL_32;
  v10 = -1;
  do
    ++v10;
  while ( String1[v10] );
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > v10 + 1 && !wcsncmp_0(String1, a2, (unsigned int)v10) )
  {
    i = &a2[v10];
  }
  else
  {
    if ( !(unsigned int)DbgClientLibIsUrlPathComponent(a2) )
      goto LABEL_32;
    v13 = wcschr(a2, 0x2Fu);
    if ( !v13 || v13 == a2 || *(v13 - 1) != 58 || v13[1] != 47 )
      goto LABEL_9;
    for ( i = v13 + 2; *i != 47; ++i )
    {
      if ( !*i )
        goto LABEL_9;
    }
  }
  if ( i )
  {
    v14 = (const unsigned __int16 *)v17[0];
    v15 = i - a2;
    *(_WORD *)(v17[0] + 2 * v15) = 0;
    v16 = &v14[v15 + 1];
    goto LABEL_33;
  }
LABEL_32:
  v16 = (const unsigned __int16 *)v17[0];
  v14 = 0;
LABEL_33:
  if ( !g_HttpOpenFileHandle(v14, v16, 0, a4, a5) )
  {
    if ( GetLastError() == 123 || GetLastError() == 21 )
    {
      FreeLibrary(g_SymSrv);
      g_SymSrv = (HMODULE)-1LL;
      g_HttpOpenFileHandle = 0;
    }
    goto LABEL_9;
  }
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(v17);
  return 1;
}

```

## disassembly

```asm
0x18041baf0  push    rbx
0x18041baf2  push    rbp
0x18041baf3  push    rsi
0x18041baf4  push    rdi
0x18041baf5  push    r12
0x18041baf7  push    r14
0x18041baf9  push    r15
0x18041bafb  sub     rsp, 1A0h
0x18041bb02  mov     [rsp+1D8h+var_1A8], 0FFFFFFFFFFFFFFFEh
0x18041bb0b  mov     rax, cs:__security_cookie
0x18041bb12  xor     rax, rsp
0x18041bb15  mov     [rsp+1D8h+var_48], rax
0x18041bb1d  mov     rbp, r9
0x18041bb20  mov     rdi, rdx
0x18041bb23  mov     rsi, rcx
0x18041bb26  mov     r14, [rsp+1D8h+arg_20]
0x18041bb2e  mov     byte ptr [rsp+1D8h+var_1B8], 1
0x18041bb33  mov     r8d, 96h
0x18041bb39  lea     rdx, [rsp+1D8h+var_180]
0x18041bb3e  lea     rcx, [rsp+1D8h+var_198]
0x18041bb43  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x18041bb48  nop
0x18041bb49  mov     rax, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_SymSrv
0x18041bb50  or      r12, 0FFFFFFFFFFFFFFFFh
0x18041bb54  cmp     rax, r12
0x18041bb57  jz      loc_18041BC3F
0x18041bb5d  xor     r15d, r15d
0x18041bb60  test    rax, rax
0x18041bb63  jnz     loc_18041BC6E
0x18041bb69  xor     r8d, r8d; dwFlags
0x18041bb6c  xor     edx, edx; hFile
0x18041bb6e  lea     rcx, aSymsrvDll; "symsrv.dll"
0x18041bb75  call    cs:__imp_LoadLibraryExW
0x18041bb7c  nop     dword ptr [rax+rax+00h]
0x18041bb81  mov     cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_SymSrv
0x18041bb88  test    rax, rax
0x18041bb8b  jz      loc_18041BC3F
0x18041bb91  lea     rdx, aHttpopenfileha; "httpOpenFileHandleW"
0x18041bb98  mov     rcx, rax; hModule
0x18041bb9b  call    cs:__imp_GetProcAddress
0x18041bba2  nop     dword ptr [rax+rax+00h]
0x18041bba7  mov     cs:?g_HttpOpenFileHandle@@3P6AHPEBG0KPEAPEAX1@ZEA, rax; int (*g_HttpOpenFileHandle)(ushort const *,ushort const *,ulong,void * *,void * *)
0x18041bbae  test    rax, rax
0x18041bbb1  jz      short loc_18041BC25
0x18041bbb3  lea     rdx, aHttpquerydataa; "httpQueryDataAvailable"
0x18041bbba  mov     rcx, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; hModule
0x18041bbc1  call    cs:__imp_GetProcAddress
0x18041bbc8  nop     dword ptr [rax+rax+00h]
0x18041bbcd  mov     cs:?g_HttpQueryDataAvailable@@3P6AHPEAXPEAKK_K@ZEA, rax; int (*g_HttpQueryDataAvailable)(void *,ulong *,ulong,unsigned __int64)
0x18041bbd4  test    rax, rax
0x18041bbd7  jz      short loc_18041BC25
0x18041bbd9  lea     rdx, aHttpreadfile; "httpReadFile"
0x18041bbe0  mov     rcx, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; hModule
0x18041bbe7  call    cs:__imp_GetProcAddress
0x18041bbee  nop     dword ptr [rax+rax+00h]
0x18041bbf3  mov     cs:?g_HttpReadFile@@3P6AHPEAX0KPEAK@ZEA, rax; int (*g_HttpReadFile)(void *,void *,ulong,ulong *)
0x18041bbfa  test    rax, rax
0x18041bbfd  jz      short loc_18041BC25
0x18041bbff  lea     rdx, aHttpclosehandl; "httpCloseHandle"
0x18041bc06  mov     rcx, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; hModule
0x18041bc0d  call    cs:__imp_GetProcAddress
0x18041bc14  nop     dword ptr [rax+rax+00h]
0x18041bc19  mov     cs:?g_HttpCloseHandle@@3P6AHPEAX@ZEA, rax; int (*g_HttpCloseHandle)(void *)
0x18041bc20  test    rax, rax
0x18041bc23  jnz     short loc_18041BC6E
0x18041bc25  mov     rcx, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; hLibModule
0x18041bc2c  call    cs:__imp_FreeLibrary
0x18041bc33  nop     dword ptr [rax+rax+00h]
0x18041bc38  mov     cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_SymSrv
0x18041bc3f  lea     rcx, [rsp+1D8h+var_198]
0x18041bc44  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18041bc49  xor     al, al
0x18041bc4b  mov     rcx, [rsp+1D8h+var_48]
0x18041bc53  xor     rcx, rsp; StackCookie
0x18041bc56  call    __security_check_cookie
0x18041bc5b  add     rsp, 1A0h
0x18041bc62  pop     r15
0x18041bc64  pop     r14
0x18041bc66  pop     r12
0x18041bc68  pop     rdi
0x18041bc69  pop     rsi
0x18041bc6a  pop     rbp
0x18041bc6b  pop     rbx
0x18041bc6c  retn
0x18041bc6e  cmp     cs:?g_HttpOpenFileHandle@@3P6AHPEBG0KPEAPEAX1@ZEA, r15; int (*g_HttpOpenFileHandle)(ushort const *,ushort const *,ulong,void * *,void * *)
0x18041bc75  jz      short loc_18041BC3F
0x18041bc77  or      r8d, 0FFFFFFFFh
0x18041bc7b  mov     rdx, rdi
0x18041bc7e  lea     rcx, [rsp+1D8h+var_198]
0x18041bc83  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x18041bc88  test    rax, rax
0x18041bc8b  jz      short loc_18041BC3F
0x18041bc8d  test    rsi, rsi
0x18041bc90  jz      loc_18041BD61
0x18041bc96  cmp     [rsi], r15w
0x18041bc9a  jz      loc_18041BD61
0x18041bca0  mov     rbx, r12
0x18041bca3  inc     rbx
0x18041bca6  cmp     [rsi+rbx*2], r15w
0x18041bcab  jnz     short loc_18041BCA3
0x18041bcad  mov     rdx, r12
0x18041bcb0  inc     rdx
0x18041bcb3  cmp     [rdi+rdx*2], r15w
0x18041bcb8  jnz     short loc_18041BCB0
0x18041bcba  lea     rax, [rbx+1]
0x18041bcbe  cmp     rdx, rax
0x18041bcc1  jbe     short loc_18041BCDB
0x18041bcc3  mov     r8d, ebx; MaxCount
0x18041bcc6  mov     rdx, rdi; String2
0x18041bcc9  mov     rcx, rsi; String1
0x18041bccc  call    wcsncmp_0
0x18041bcd1  test    eax, eax
0x18041bcd3  jnz     short loc_18041BCDB
0x18041bcd5  lea     rcx, [rdi+rbx*2]
0x18041bcd9  jmp     short loc_18041BD42
0x18041bcdb  mov     rcx, rdi; String1
0x18041bcde  call    DbgClientLibIsUrlPathComponent
0x18041bce3  test    eax, eax
0x18041bce5  jz      short loc_18041BD61
0x18041bce7  mov     ebx, 2Fh ; '/'
0x18041bcec  mov     edx, ebx; Ch
0x18041bcee  mov     rcx, rdi; Str
0x18041bcf1  call    cs:__imp_wcschr
0x18041bcf8  nop     dword ptr [rax+rax+00h]
0x18041bcfd  mov     rcx, rax
0x18041bd00  test    rax, rax
0x18041bd03  jz      loc_18041BC3F
0x18041bd09  cmp     rax, rdi
0x18041bd0c  jz      loc_18041BC3F
0x18041bd12  cmp     word ptr [rax-2], 3Ah ; ':'
0x18041bd17  jnz     loc_18041BC3F
0x18041bd1d  cmp     [rax+2], bx
0x18041bd21  jnz     loc_18041BC3F
0x18041bd27  add     rcx, 4
0x18041bd2b  jmp     short loc_18041BD3A
0x18041bd2d  test    ax, ax
0x18041bd30  jz      loc_18041BC3F
0x18041bd36  add     rcx, 2
0x18041bd3a  movzx   eax, word ptr [rcx]
0x18041bd3d  cmp     ax, bx
0x18041bd40  jnz     short loc_18041BD2D
0x18041bd42  test    rcx, rcx
0x18041bd45  jz      short loc_18041BD61
0x18041bd47  mov     r10, [rsp+1D8h+var_198]
0x18041bd4c  sub     rcx, rdi
0x18041bd4f  sar     rcx, 1
0x18041bd52  mov     [r10+rcx*2], r15w
0x18041bd57  lea     rdx, [r10+2]
0x18041bd5b  lea     rdx, [rdx+rcx*2]
0x18041bd5f  jmp     short loc_18041BD69
0x18041bd61  mov     rdx, [rsp+1D8h+var_198]
0x18041bd66  mov     r10, r15
0x18041bd69  mov     [rsp+1D8h+var_1B8], r14
0x18041bd6e  mov     r9, rbp
0x18041bd71  xor     r8d, r8d
0x18041bd74  mov     rcx, r10
0x18041bd77  mov     rax, cs:?g_HttpOpenFileHandle@@3P6AHPEBG0KPEAPEAX1@ZEA; int (*g_HttpOpenFileHandle)(ushort const *,ushort const *,ulong,void * *,void * *)
0x18041bd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18041bd83  test    eax, eax
0x18041bd85  jnz     short loc_18041BDD3
0x18041bd87  call    cs:__imp_GetLastError
0x18041bd8e  nop     dword ptr [rax+rax+00h]
0x18041bd93  cmp     eax, 7Bh ; '{'
0x18041bd96  jz      short loc_18041BDAD
0x18041bd98  call    cs:__imp_GetLastError
0x18041bd9f  nop     dword ptr [rax+rax+00h]
0x18041bda4  cmp     eax, 15h
0x18041bda7  jnz     loc_18041BC3F
0x18041bdad  mov     rcx, cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA; hLibModule
0x18041bdb4  call    cs:__imp_FreeLibrary
0x18041bdbb  nop     dword ptr [rax+rax+00h]
0x18041bdc0  mov     cs:?g_SymSrv@@3PEAUHINSTANCE__@@EA, r12; HINSTANCE__ * g_SymSrv
0x18041bdc7  mov     cs:?g_HttpOpenFileHandle@@3P6AHPEBG0KPEAPEAX1@ZEA, r15; int (*g_HttpOpenFileHandle)(ushort const *,ushort const *,ulong,void * *,void * *)
0x18041bdce  jmp     loc_18041BC3F
0x18041bdd3  lea     rcx, [rsp+1D8h+var_198]
0x18041bdd8  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18041bddd  mov     al, 1
0x18041bddf  jmp     loc_18041BC4B
```
