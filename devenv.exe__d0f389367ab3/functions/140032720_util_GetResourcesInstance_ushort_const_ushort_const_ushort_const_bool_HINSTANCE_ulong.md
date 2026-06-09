# util_GetResourcesInstance(ushort const *,ushort const *,ushort const *,bool,HINSTANCE__ * *,ulong *)

- ea: `0x140032720`
- end: `0x140032981`
- name: `?util_GetResourcesInstance@@YAHPEBG00_NPEAPEAUHINSTANCE__@@PEAK@Z`
- size: `609`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, HINSTANCE *, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000b4a0`
- `0x14002fbd8`
- `0x140033820`

## callees

- `0x140001020`
- `0x140001040`
- `0x1400021b8`
- `0x140032588`
- `0x140032670`
- `0x140032720`
- `0x140032984`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x14003283b`
- `KERNEL32!GetModuleFileNameW` at `0x14003283b`
- `KERNEL32!LoadLibraryExW` at `0x14003294f`
- `KERNEL32!LoadLibraryExW` at `0x14003294f`
- `KERNEL32!GetLastError` at `0x14003295d`
- `KERNEL32!GetLastError` at `0x14003295d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400327dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400327dc`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x140032876`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x140032876`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall util_GetResourcesInstance(
        const unsigned __int16 *a1,
        wchar_t *p_Drive,
        unsigned __int16 *a3,
        char a4,
        HINSTANCE *a5,
        unsigned int *a6)
{
  char v6; // r15
  OLECHAR *v10; // rbx
  HKEY v11; // rcx
  int v12; // r8d
  const unsigned __int16 *v13; // r9
  BOOL v14; // edi
  unsigned int UILocale; // r13d
  __int64 v17; // rax
  __int64 v18; // rax
  signed int UILibraryFileName; // edi
  HMODULE Library; // rax
  signed int LastError; // eax
  unsigned int v22; // [rsp+28h] [rbp-D8h]
  unsigned int v23; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v25; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v26; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[526]; // [rsp+72h] [rbp-8Eh] BYREF
  wchar_t Dir; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v31[526]; // [rsp+282h] [rbp+182h] BYREF
  wchar_t Drive; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v33[1038]; // [rsp+492h] [rbp+392h] BYREF

  v6 = a4;
  v26 = a3;
  v10 = 0;
  Filename = 0;
  memset_0(v29, 0, 0x206u);
  Drive = 0;
  memset_0(v33, 0, sizeof(v33));
  Dir = 0;
  memset_0(v31, 0, 0x206u);
  lpLibFileName = 0;
  if ( !a3 )
    goto LABEL_4;
  if ( a5 )
  {
    *a5 = 0;
LABEL_7:
    UILocale = util_GetUILocale(v11, a1, v12, v13);
    if ( !(unsigned int)s_IsFullPath(p_Drive) )
    {
      GetModuleFileNameW(0, &Filename, 0x104u);
      _wsplitpath_s(&Filename, &Drive, 0x208u, &Dir, 0x104u, 0, 0, 0, 0);
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)&v33[2 * v17 - 2] );
      v18 = 2 * v17;
      v25 = (unsigned __int16 *)&v33[v18 - 2];
      UILibraryFileName = StringCchCopyExW((unsigned __int16 *)&v33[v18 - 2], 520 - (v18 >> 1), &Dir, &v25, 0, v22);
      if ( UILibraryFileName >= 0 && p_Drive )
        UILibraryFileName = StringCchCopyExW(v25, 520 - (v25 - &Drive), p_Drive, &v25, 0, v23);
      p_Drive = &Drive;
      if ( UILibraryFileName < 0 )
        goto LABEL_21;
      v6 = a4;
    }
    _mm_lfence();
    UILibraryFileName = W_GetUILibraryFileName(UILocale, p_Drive, v26, 0, 0, (unsigned __int16 **)&lpLibFileName, a6);
    if ( UILibraryFileName >= 0 )
    {
      if ( a5 )
      {
        if ( !v6 )
        {
          Library = LoadLibraryExW(lpLibFileName, 0, 0);
          *a5 = Library;
          if ( !Library )
          {
            LastError = GetLastError();
            UILibraryFileName = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              UILibraryFileName = LastError;
          }
        }
      }
    }
LABEL_21:
    v14 = UILibraryFileName >= 0;
    v10 = (OLECHAR *)lpLibFileName;
    goto LABEL_5;
  }
  if ( a6 )
    goto LABEL_7;
LABEL_4:
  v14 = 0;
LABEL_5:
  SysFreeString(v10);
  return v14;
}

```

## disassembly

```asm
0x140032720  mov     [rsp-8+arg_18], rbx
0x140032725  push    rbp
0x140032726  push    rsi
0x140032727  push    rdi
0x140032728  push    r12
0x14003272a  push    r13
0x14003272c  push    r14
0x14003272e  push    r15
0x140032730  lea     rbp, [rsp-7B0h]
0x140032738  sub     rsp, 8B0h
0x14003273f  mov     rax, cs:__security_cookie
0x140032746  xor     rax, rsp
0x140032749  mov     [rbp+7E0h+var_40], rax
0x140032750  mov     r15b, r9b
0x140032753  mov     [rsp+8E0h+var_890], r9b
0x140032758  mov     r13, r8
0x14003275b  mov     [rsp+8E0h+var_880], r8
0x140032760  mov     rsi, rdx
0x140032763  mov     rdi, rcx
0x140032766  mov     r14, [rbp+7E0h+arg_20]
0x14003276d  mov     r12, [rbp+7E0h+arg_28]
0x140032774  xor     ebx, ebx
0x140032776  mov     [rsp+8E0h+Filename], bx
0x14003277b  xor     edx, edx; Val
0x14003277d  mov     r8d, 206h; Size
0x140032783  lea     rcx, [rsp+8E0h+var_86E]; void *
0x140032788  call    memset_0
0x14003278d  mov     [rbp+7E0h+Drive], bx
0x140032794  xor     edx, edx; Val
0x140032796  mov     r8d, 40Eh; Size
0x14003279c  lea     rcx, [rbp+7E0h+var_44E]; void *
0x1400327a3  call    memset_0
0x1400327a8  mov     [rbp+7E0h+Dir], bx
0x1400327af  xor     edx, edx; Val
0x1400327b1  mov     r8d, 206h; Size
0x1400327b7  lea     rcx, [rbp+7E0h+var_65E]; void *
0x1400327be  call    memset_0
0x1400327c3  mov     [rsp+8E0h+lpLibFileName], rbx
0x1400327c8  test    r13, r13
0x1400327cb  jz      short loc_1400327D7
0x1400327cd  test    r14, r14
0x1400327d0  jnz     short loc_14003280E
0x1400327d2  test    r12, r12
0x1400327d5  jnz     short loc_140032811
0x1400327d7  mov     edi, ebx
0x1400327d9  mov     rcx, rbx; bstrString
0x1400327dc  call    cs:__imp_SysFreeString
0x1400327e2  mov     eax, edi
0x1400327e4  mov     rcx, [rbp+7E0h+var_40]
0x1400327eb  xor     rcx, rsp; StackCookie
0x1400327ee  call    __security_check_cookie
0x1400327f3  mov     rbx, [rsp+8E0h+arg_18]
0x1400327fb  add     rsp, 8B0h
0x140032802  pop     r15
0x140032804  pop     r14
0x140032806  pop     r13
0x140032808  pop     r12
0x14003280a  pop     rdi
0x14003280b  pop     rsi
0x14003280c  pop     rbp
0x14003280d  retn
0x14003280e  mov     [r14], rbx
0x140032811  mov     rdx, rdi; unsigned __int16 *
0x140032814  call    ?util_GetUILocale@@YAKPEAUHKEY__@@PEBGH1@Z; util_GetUILocale(HKEY__ *,ushort const *,int,ushort const *)
0x140032819  mov     r13d, eax
0x14003281c  mov     rcx, rsi
0x14003281f  call    s_IsFullPath
0x140032824  test    eax, eax
0x140032826  jnz     loc_14003290B
0x14003282c  mov     edi, 104h
0x140032831  mov     r8d, edi; nSize
0x140032834  lea     rdx, [rsp+8E0h+Filename]; lpFilename
0x140032839  xor     ecx, ecx; hModule
0x14003283b  call    cs:__imp_GetModuleFileNameW
0x140032841  mov     [rsp+8E0h+ExtCount], rbx; ExtCount
0x140032846  mov     [rsp+8E0h+Ext], rbx; Ext
0x14003284b  mov     [rsp+8E0h+FilenameCount], rbx; FilenameCount
0x140032850  mov     [rsp+8E0h+var_8B8], rbx; unsigned int
0x140032855  mov     [rsp+8E0h+DirCount], rdi; DirCount
0x14003285a  lea     r9, [rbp+7E0h+Dir]; Dir
0x140032861  mov     r15d, 208h
0x140032867  mov     r8d, r15d; DriveCount
0x14003286a  lea     rdx, [rbp+7E0h+Drive]; Drive
0x140032871  lea     rcx, [rsp+8E0h+Filename]; FullPath
0x140032876  call    cs:__imp__wsplitpath_s
0x14003287c  lea     rcx, [rbp+7E0h+Drive]
0x140032883  or      rax, 0FFFFFFFFFFFFFFFFh
0x140032887  inc     rax
0x14003288a  cmp     [rcx+rax*2], bx
0x14003288e  jnz     short loc_140032887
0x140032890  add     rax, rax
0x140032893  lea     rcx, [rbp+7E0h+Drive]
0x14003289a  add     rcx, rax; unsigned __int16 *
0x14003289d  mov     [rsp+8E0h+var_888], rcx
0x1400328a2  sar     rax, 1
0x1400328a5  mov     rdx, r15
0x1400328a8  sub     rdx, rax; unsigned __int64
0x1400328ab  mov     [rsp+8E0h+DirCount], rbx; unsigned __int64 *
0x1400328b0  lea     r9, [rsp+8E0h+var_888]; unsigned __int16 **
0x1400328b5  lea     r8, [rbp+7E0h+Dir]; unsigned __int16 *
0x1400328bc  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1400328c1  mov     edi, eax
0x1400328c3  test    eax, eax
0x1400328c5  js      short loc_1400328FB
0x1400328c7  test    rsi, rsi
0x1400328ca  jz      short loc_1400328FB
0x1400328cc  lea     rdx, [rbp+7E0h+Drive]
0x1400328d3  mov     rcx, [rsp+8E0h+var_888]; unsigned __int16 *
0x1400328d8  mov     rax, rcx
0x1400328db  sub     rax, rdx
0x1400328de  sar     rax, 1
0x1400328e1  sub     r15, rax
0x1400328e4  mov     [rsp+8E0h+DirCount], rbx; unsigned __int64 *
0x1400328e9  lea     r9, [rsp+8E0h+var_888]; unsigned __int16 **
0x1400328ee  mov     r8, rsi; unsigned __int16 *
0x1400328f1  mov     rdx, r15; unsigned __int64
0x1400328f4  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1400328f9  mov     edi, eax
0x1400328fb  lea     rsi, [rbp+7E0h+Drive]
0x140032902  test    edi, edi
0x140032904  js      short loc_140032971
0x140032906  mov     r15b, [rsp+8E0h+var_890]
0x14003290b  lfence
0x14003290e  mov     [rsp+8E0h+FilenameCount], r12; unsigned int *
0x140032913  lea     rax, [rsp+8E0h+lpLibFileName]
0x140032918  mov     [rsp+8E0h+var_8B8], rax; unsigned __int16 **
0x14003291d  mov     [rsp+8E0h+DirCount], rbx; __int64
0x140032922  xor     r9d, r9d; int (*)(__int64, unsigned int)
0x140032925  mov     r8, [rsp+8E0h+var_880]; unsigned __int16 *
0x14003292a  mov     rdx, rsi; unsigned __int16 *
0x14003292d  mov     ecx, r13d; unsigned int
0x140032930  call    ?W_GetUILibraryFileName@@YAJKPEBG0P6AH_JK@Z1PEAPEAGPEAK@Z; W_GetUILibraryFileName(ulong,ushort const *,ushort const *,int (*)(__int64,ulong),__int64,ushort * *,ulong *)
0x140032935  mov     edi, eax
0x140032937  test    eax, eax
0x140032939  js      short loc_140032971
0x14003293b  test    r14, r14
0x14003293e  jz      short loc_140032971
0x140032940  test    r15b, r15b
0x140032943  jnz     short loc_140032971
0x140032945  xor     r8d, r8d; dwFlags
0x140032948  xor     edx, edx; hFile
0x14003294a  mov     rcx, [rsp+8E0h+lpLibFileName]; lpLibFileName
0x14003294f  call    cs:__imp_LoadLibraryExW
0x140032955  mov     [r14], rax
0x140032958  test    rax, rax
0x14003295b  jnz     short loc_140032971
0x14003295d  call    cs:__imp_GetLastError
0x140032963  movzx   edi, ax
0x140032966  or      edi, 80070000h
0x14003296c  test    eax, eax
0x14003296e  cmovle  edi, eax
0x140032971  not     edi
0x140032973  shr     edi, 1Fh
0x140032976  mov     rbx, [rsp+8E0h+lpLibFileName]
0x14003297b  jmp     loc_1400327D9
```
