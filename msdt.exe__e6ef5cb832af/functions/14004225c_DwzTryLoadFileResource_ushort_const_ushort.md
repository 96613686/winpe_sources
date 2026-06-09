# DwzTryLoadFileResource(ushort const *,ushort * *)

- ea: `0x14004225c`
- end: `0x140042703`
- name: `?DwzTryLoadFileResource@@YAJPEBGPEAPEAG@Z`
- size: `1191`
- prototype: `__int64 __fastcall(OLECHAR *psz, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14002d40c`

## callees

- `0x1400039b1`
- `0x140020420`
- `0x140041020`
- `0x14004225c`
- `0x14004270c`
- `0x140050ae0`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004266f`
- `KERNEL32!GetLastError` at `0x14004266f`
- `KERNEL32!HeapAlloc` at `0x1400422d4`
- `KERNEL32!HeapAlloc` at `0x140042560`
- `KERNEL32!HeapAlloc` at `0x14004259a`
- `KERNEL32!HeapAlloc` at `0x1400422d4`
- `KERNEL32!HeapAlloc` at `0x140042560`
- `KERNEL32!HeapAlloc` at `0x14004259a`
- `KERNEL32!HeapFree` at `0x14004243f`
- `KERNEL32!HeapFree` at `0x140042464`
- `KERNEL32!HeapFree` at `0x140042489`
- `KERNEL32!HeapFree` at `0x14004243f`
- `KERNEL32!HeapFree` at `0x140042464`
- `KERNEL32!HeapFree` at `0x140042489`
- `KERNEL32!GetProcessHeap` at `0x1400422bd`
- `KERNEL32!GetProcessHeap` at `0x14004242b`
- `KERNEL32!GetProcessHeap` at `0x140042450`
- `KERNEL32!GetProcessHeap` at `0x140042475`
- `KERNEL32!GetProcessHeap` at `0x14004254c`
- `KERNEL32!GetProcessHeap` at `0x140042586`
- `KERNEL32!GetProcessHeap` at `0x1400422bd`
- `KERNEL32!GetProcessHeap` at `0x14004242b`
- `KERNEL32!GetProcessHeap` at `0x140042450`
- `KERNEL32!GetProcessHeap` at `0x140042475`
- `KERNEL32!GetProcessHeap` at `0x14004254c`
- `KERNEL32!GetProcessHeap` at `0x140042586`
- `KERNEL32!FreeLibrary` at `0x140042406`
- `KERNEL32!FreeLibrary` at `0x140042406`
- `KERNEL32!LoadLibraryExW` at `0x14004236d`
- `KERNEL32!LoadLibraryExW` at `0x14004236d`
- `msvcrt!mbstowcs_s` at `0x14004261e`
- `msvcrt!mbstowcs_s` at `0x14004261e`
- `msvcrt!wcstok` at `0x140042358`
- `msvcrt!wcstok` at `0x140042396`
- `msvcrt!wcstok` at `0x140042358`
- `msvcrt!wcstok` at `0x140042396`
- `OLEAUT32!__imp_SysAllocString` at `0x140042645`
- `OLEAUT32!__imp_SysAllocString` at `0x1400426bf`
- `OLEAUT32!__imp_SysAllocString` at `0x140042645`
- `OLEAUT32!__imp_SysAllocString` at `0x1400426bf`
- `OLEAUT32!__imp_SysFreeString` at `0x14004241a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004241a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DwzTryLoadFileResource(OLECHAR *psz, unsigned __int16 **a2)
{
  OLECHAR *v2; // rsi
  wchar_t *v4; // r14
  char *v5; // r13
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  wchar_t *v8; // r15
  unsigned int v9; // ebx
  int v10; // eax
  wchar_t **v11; // r8
  wchar_t *v12; // rax
  HMODULE Library; // rbx
  wchar_t **v14; // r8
  wchar_t *v15; // rax
  const unsigned __int16 *v16; // r8
  int v17; // eax
  HMODULE v18; // r12
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  int v23; // eax
  int v24; // r9d
  int v25; // eax
  size_t v26; // r12
  SIZE_T v27; // rbx
  HANDLE v28; // rax
  wchar_t *v29; // rax
  HANDLE v30; // rax
  wchar_t *v31; // rax
  signed int LastError; // eax
  int MaxCount; // [rsp+20h] [rbp-79h]
  HMODULE hLibModule; // [rsp+30h] [rbp-69h]
  struct IStream *v35; // [rsp+38h] [rbp-61h] BYREF
  int v36; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-51h] BYREF
  size_t PtNumOfCharConverted; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 **v39; // [rsp+58h] [rbp-41h]
  _BYTE v40[16]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v41; // [rsp+70h] [rbp-29h]

  v2 = 0;
  v39 = a2;
  v37 = 0;
  v4 = 0;
  v36 = 0;
  v5 = 0;
  PtNumOfCharConverted = 0;
  v35 = 0;
  memset_0(v40, 0, 0x50u);
  if ( *psz != 64 )
  {
    v18 = 0;
    v9 = 0;
    v8 = 0;
    v2 = SysAllocString(psz);
    if ( !v2 )
    {
      v9 = -2147024882;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", 180, -2147024882);
LABEL_16:
      if ( v2 )
        SysFreeString(v2);
      if ( !v8 )
        goto LABEL_20;
      goto LABEL_19;
    }
    goto LABEL_13;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", 109, -2147024882);
    goto LABEL_24;
  }
  v10 = ExpandVariables(v7, 0x400u, psz);
  v9 = v10;
  if ( v10 >= 0 )
  {
    v12 = wcstok(v8, L"@, ", v11);
    Library = LoadLibraryExW(v12, 0, 2u);
    hLibModule = Library;
    if ( (unsigned __int64)Library - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", 117, v9);
      v18 = hLibModule;
LABEL_14:
      if ( !v18 )
        goto LABEL_16;
      goto LABEL_15;
    }
    v15 = wcstok(0, L", ", v14);
    if ( *v15 == 45 )
    {
      v17 = DwzTryLoadResourceString(psz, &v37);
      v9 = v17;
      if ( v17 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", 126, v17);
        v2 = v37;
LABEL_10:
        v18 = hLibModule;
LABEL_15:
        FreeLibrary(v18);
        goto LABEL_16;
      }
      v2 = v37;
      goto LABEL_12;
    }
    v23 = CreateStreamFromResource(Library, v15, v16, &v35);
    v9 = v23;
    if ( v23 >= 0 )
    {
      v25 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)v35 + 96LL))(v35, v40, 1);
      v9 = v25;
      if ( v25 >= 0 )
      {
        v26 = v41 + 2;
        v27 = 2 * (v41 + 2);
        v28 = GetProcessHeap();
        v29 = (wchar_t *)HeapAlloc(v28, 0, v27);
        v4 = v29;
        if ( v29 )
        {
          v5 = (char *)v29;
          v30 = GetProcessHeap();
          v31 = (wchar_t *)HeapAlloc(v30, 0, v27);
          v4 = v31;
          if ( v31 )
          {
            *v31 = 0;
            *v5 = 0;
            v25 = (*(__int64 (__fastcall **)(struct IStream *, char *, _QWORD, int *))(*(_QWORD *)v35 + 24LL))(
                    v35,
                    v5,
                    (unsigned int)v41,
                    &v36);
            v9 = v25;
            if ( v25 >= 0 )
            {
              if ( v26 )
              {
                v4[v26 - 1] = 0;
                v5[v26 - 1] = 0;
              }
              if ( mbstowcs_s(&PtNumOfCharConverted, v4, v26, v5, 0xFFFFFFFFFFFFFFFFuLL) )
              {
                v9 = -2147467259;
                v24 = 172;
                MaxCount = -2147467259;
                goto LABEL_29;
              }
              v2 = SysAllocString(v4);
              if ( v2 )
              {
LABEL_12:
                v18 = hLibModule;
LABEL_13:
                *v39 = v2;
                v2 = 0;
                goto LABEL_14;
              }
              v25 = -2147024882;
              v24 = 176;
              v9 = -2147024882;
            }
            else
            {
              v24 = 154;
            }
          }
          else
          {
            v25 = -2147024882;
            v24 = 146;
            v9 = -2147024882;
          }
        }
        else
        {
          v25 = -2147024882;
          v24 = 142;
          v9 = -2147024882;
        }
      }
      else
      {
        v24 = 138;
      }
      MaxCount = v25;
    }
    else
    {
      MaxCount = v23;
      v24 = 132;
    }
LABEL_29:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", v24, MaxCount);
    goto LABEL_10;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzTryLoadFileResource", 112, v10);
LABEL_19:
  v19 = GetProcessHeap();
  HeapFree(v19, 0, v8);
LABEL_20:
  if ( v4 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v4);
  }
  if ( v5 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v5);
  }
LABEL_24:
  if ( v35 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v35 + 16LL))(v35);
  return v9;
}

```

## disassembly

```asm
0x14004225c  mov     [rsp-8+arg_10], rbx
0x140042261  push    rbp
0x140042262  push    rsi
0x140042263  push    rdi
0x140042264  push    r12
0x140042266  push    r13
0x140042268  push    r14
0x14004226a  push    r15
0x14004226c  lea     rbp, [rsp-27h]
0x140042271  sub     rsp, 0C0h
0x140042278  mov     rax, cs:__security_cookie
0x14004227f  xor     rax, rsp
0x140042282  mov     [rbp+57h+var_40], rax
0x140042286  xor     esi, esi
0x140042288  mov     [rbp+57h+var_98], rdx
0x14004228c  mov     rdi, rcx
0x14004228f  mov     [rbp+57h+var_A8], rsi
0x140042293  xor     r14d, r14d
0x140042296  mov     [rbp+57h+var_B0], esi
0x140042299  xor     r13d, r13d
0x14004229c  mov     [rbp+57h+PtNumOfCharConverted], rsi
0x1400422a0  xor     edx, edx; Val
0x1400422a2  mov     [rbp+57h+var_B8], r13
0x1400422a6  lea     rcx, [rbp+57h+var_90]; void *
0x1400422aa  lea     r8d, [r14+50h]; Size
0x1400422ae  call    memset_0
0x1400422b3  cmp     word ptr [rdi], 40h ; '@'
0x1400422b7  jnz     loc_1400426B4
0x1400422bd  call    cs:__imp_GetProcessHeap
0x1400422c4  nop     dword ptr [rax+rax+00h]
0x1400422c9  xor     edx, edx; dwFlags
0x1400422cb  mov     r8d, 800h; dwBytes
0x1400422d1  mov     rcx, rax; hHeap
0x1400422d4  call    cs:__imp_HeapAlloc
0x1400422db  nop     dword ptr [rax+rax+00h]
0x1400422e0  mov     r15, rax
0x1400422e3  test    rax, rax
0x1400422e6  jnz     short loc_140042312
0x1400422e8  mov     eax, 8007000Eh
0x1400422ed  lea     r9d, [r14+6Dh]
0x1400422f1  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x1400422f8  mov     [rsp+0F0h+MaxCount], eax
0x1400422fc  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042303  mov     ebx, eax
0x140042305  lea     ecx, [rsi+1]; Level
0x140042308  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004230d  jmp     loc_140042495
0x140042312  mov     r8, rdi; lpSrc
0x140042315  mov     edx, 400h; unsigned __int64
0x14004231a  mov     rcx, r15; unsigned __int16 *
0x14004231d  call    ?ExpandVariables@@YAJPEAG_KPEBG@Z; ExpandVariables(ushort *,unsigned __int64,ushort const *)
0x140042322  mov     ebx, eax
0x140042324  test    eax, eax
0x140042326  jns     short loc_14004234E
0x140042328  mov     r9d, 70h ; 'p'
0x14004232e  mov     [rsp+0F0h+MaxCount], eax
0x140042332  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x140042339  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140042340  lea     ecx, [r9-6Fh]; Level
0x140042344  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140042349  jmp     loc_14004242B
0x14004234e  lea     rdx, asc_1400713E8; "@, "
0x140042355  mov     rcx, r15; String
0x140042358  call    cs:__imp_wcstok
0x14004235f  nop     dword ptr [rax+rax+00h]
0x140042364  xor     edx, edx; hFile
0x140042366  mov     rcx, rax; lpLibFileName
0x140042369  lea     r8d, [rdx+2]; dwFlags
0x14004236d  call    cs:__imp_LoadLibraryExW
0x140042374  nop     dword ptr [rax+rax+00h]
0x140042379  mov     rbx, rax
0x14004237c  mov     [rbp+57h+hLibModule], rax
0x140042380  dec     rax
0x140042383  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140042387  ja      loc_14004266F
0x14004238d  lea     rdx, asc_1400713F0; ", "
0x140042394  xor     ecx, ecx; String
0x140042396  call    cs:__imp_wcstok
0x14004239d  nop     dword ptr [rax+rax+00h]
0x1400423a2  mov     ecx, 2Dh ; '-'
0x1400423a7  cmp     cx, [rax]
0x1400423aa  jnz     loc_1400424D4
0x1400423b0  lea     rdx, [rbp+57h+var_A8]; unsigned __int16 **
0x1400423b4  mov     rcx, rdi; psz
0x1400423b7  call    ?DwzTryLoadResourceString@@YAJPEBGPEAPEAG@Z; DwzTryLoadResourceString(ushort const *,ushort * *)
0x1400423bc  mov     ebx, eax
0x1400423be  test    eax, eax
0x1400423c0  jns     short loc_1400423ED
0x1400423c2  mov     r9d, 7Eh ; '~'
0x1400423c8  mov     [rsp+0F0h+MaxCount], eax
0x1400423cc  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x1400423d3  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400423da  lea     ecx, [r9-7Dh]; Level
0x1400423de  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400423e3  mov     rsi, [rbp+57h+var_A8]
0x1400423e7  mov     r12, [rbp+57h+hLibModule]
0x1400423eb  jmp     short loc_140042403
0x1400423ed  mov     rsi, [rbp+57h+var_A8]
0x1400423f1  mov     r12, [rbp+57h+hLibModule]
0x1400423f5  mov     rax, [rbp+57h+var_98]
0x1400423f9  mov     [rax], rsi
0x1400423fc  xor     esi, esi
0x1400423fe  test    r12, r12
0x140042401  jz      short loc_140042412
0x140042403  mov     rcx, r12; hLibModule
0x140042406  call    cs:__imp_FreeLibrary
0x14004240d  nop     dword ptr [rax+rax+00h]
0x140042412  test    rsi, rsi
0x140042415  jz      short loc_140042426
0x140042417  mov     rcx, rsi; bstrString
0x14004241a  call    cs:__imp_SysFreeString
0x140042421  nop     dword ptr [rax+rax+00h]
0x140042426  test    r15, r15
0x140042429  jz      short loc_14004244B
0x14004242b  call    cs:__imp_GetProcessHeap
0x140042432  nop     dword ptr [rax+rax+00h]
0x140042437  mov     r8, r15; lpMem
0x14004243a  xor     edx, edx; dwFlags
0x14004243c  mov     rcx, rax; hHeap
0x14004243f  call    cs:__imp_HeapFree
0x140042446  nop     dword ptr [rax+rax+00h]
0x14004244b  test    r14, r14
0x14004244e  jz      short loc_140042470
0x140042450  call    cs:__imp_GetProcessHeap
0x140042457  nop     dword ptr [rax+rax+00h]
0x14004245c  mov     r8, r14; lpMem
0x14004245f  xor     edx, edx; dwFlags
0x140042461  mov     rcx, rax; hHeap
0x140042464  call    cs:__imp_HeapFree
0x14004246b  nop     dword ptr [rax+rax+00h]
0x140042470  test    r13, r13
0x140042473  jz      short loc_140042495
0x140042475  call    cs:__imp_GetProcessHeap
0x14004247c  nop     dword ptr [rax+rax+00h]
0x140042481  mov     r8, r13; lpMem
0x140042484  xor     edx, edx; dwFlags
0x140042486  mov     rcx, rax; hHeap
0x140042489  call    cs:__imp_HeapFree
0x140042490  nop     dword ptr [rax+rax+00h]
0x140042495  mov     rcx, [rbp+57h+var_B8]
0x140042499  test    rcx, rcx
0x14004249c  jz      short loc_1400424AA
0x14004249e  mov     rax, [rcx]
0x1400424a1  mov     rax, [rax+10h]
0x1400424a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400424aa  mov     eax, ebx
0x1400424ac  mov     rcx, [rbp+57h+var_40]
0x1400424b0  xor     rcx, rsp; StackCookie
0x1400424b3  call    __security_check_cookie
0x1400424b8  mov     rbx, [rsp+0F0h+arg_10]
0x1400424c0  add     rsp, 0C0h
0x1400424c7  pop     r15
0x1400424c9  pop     r14
0x1400424cb  pop     r13
0x1400424cd  pop     r12
0x1400424cf  pop     rdi
0x1400424d0  pop     rsi
0x1400424d1  pop     rbp
0x1400424d2  retn
0x1400424d4  lea     r9, [rbp+57h+var_B8]; struct IStream **
0x1400424d8  mov     rdx, rax; unsigned __int16 *
0x1400424db  mov     rcx, rbx; hModule
0x1400424de  call    ?CreateStreamFromResource@@YAJPEAUHINSTANCE__@@PEBG1PEAPEAUIStream@@@Z; CreateStreamFromResource(HINSTANCE__ *,ushort const *,ushort const *,IStream * *)
0x1400424e3  mov     ebx, eax
0x1400424e5  test    eax, eax
0x1400424e7  jns     short loc_140042510
0x1400424e9  mov     [rsp+0F0h+MaxCount], eax
0x1400424ed  mov     r9d, 84h
0x1400424f3  mov     ecx, 1; Level
0x1400424f8  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400424ff  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x140042506  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14004250b  jmp     loc_1400423E7
0x140042510  mov     rcx, [rbp+57h+var_B8]
0x140042514  lea     rdx, [rbp+57h+var_90]
0x140042518  mov     edi, 1
0x14004251d  mov     r8d, edi
0x140042520  mov     rax, [rcx]
0x140042523  mov     rax, [rax+60h]
0x140042527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004252c  mov     ebx, eax
0x14004252e  test    eax, eax
0x140042530  jns     short loc_140042540
0x140042532  mov     r9d, 8Ah
0x140042538  mov     [rsp+0F0h+MaxCount], eax
0x14004253c  mov     ecx, edi
0x14004253e  jmp     short loc_1400424F8
0x140042540  mov     r12, [rbp+57h+var_80]
0x140042544  add     r12, 2
0x140042548  lea     rbx, [r12+r12]
0x14004254c  call    cs:__imp_GetProcessHeap
0x140042553  nop     dword ptr [rax+rax+00h]
0x140042558  mov     r8, rbx; dwBytes
0x14004255b  xor     edx, edx; dwFlags
0x14004255d  mov     rcx, rax; hHeap
0x140042560  call    cs:__imp_HeapAlloc
0x140042567  nop     dword ptr [rax+rax+00h]
0x14004256c  mov     r14, rax
0x14004256f  test    rax, rax
0x140042572  jnz     short loc_140042583
0x140042574  mov     eax, 8007000Eh
0x140042579  mov     r9d, 8Eh
0x14004257f  mov     ebx, eax
0x140042581  jmp     short loc_140042538
0x140042583  mov     r13, rax
0x140042586  call    cs:__imp_GetProcessHeap
0x14004258d  nop     dword ptr [rax+rax+00h]
0x140042592  mov     r8, rbx; dwBytes
0x140042595  xor     edx, edx; dwFlags
0x140042597  mov     rcx, rax; hHeap
0x14004259a  call    cs:__imp_HeapAlloc
0x1400425a1  nop     dword ptr [rax+rax+00h]
0x1400425a6  mov     r14, rax
0x1400425a9  test    rax, rax
0x1400425ac  jnz     short loc_1400425C0
0x1400425ae  mov     eax, 8007000Eh
0x1400425b3  mov     r9d, 92h
0x1400425b9  mov     ebx, eax
0x1400425bb  jmp     loc_140042538
0x1400425c0  xor     eax, eax
0x1400425c2  lea     r9, [rbp+57h+var_B0]
0x1400425c6  mov     [r14], ax
0x1400425ca  mov     rdx, r13
0x1400425cd  mov     [r13+0], al
0x1400425d1  mov     rcx, [rbp+57h+var_B8]
0x1400425d5  mov     r8d, dword ptr [rbp+57h+var_80]
0x1400425d9  mov     rax, [rcx]
0x1400425dc  mov     rax, [rax+18h]
0x1400425e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400425e5  mov     ebx, eax
0x1400425e7  test    eax, eax
0x1400425e9  jns     short loc_1400425F6
0x1400425eb  mov     r9d, 9Ah
0x1400425f1  jmp     loc_140042538
0x1400425f6  test    r12, r12
0x1400425f9  jz      short loc_140042608
0x1400425fb  xor     eax, eax
0x1400425fd  mov     [r14+r12*2-2], ax
0x140042603  mov     [r12+r13-1], al
0x140042608  mov     r9, r13; SrcBuf
0x14004260b  mov     qword ptr [rsp+0F0h+MaxCount], 0FFFFFFFFFFFFFFFFh; MaxCount
0x140042614  mov     r8, r12; SizeInWords
0x140042617  lea     rcx, [rbp+57h+PtNumOfCharConverted]; PtNumOfCharConverted
0x14004261b  mov     rdx, r14; DstBuf
0x14004261e  call    cs:__imp_mbstowcs_s
0x140042625  nop     dword ptr [rax+rax+00h]
0x14004262a  test    eax, eax
0x14004262c  jz      short loc_140042642
0x14004262e  mov     ebx, 80004005h
0x140042633  mov     r9d, 0ACh
0x140042639  mov     [rsp+0F0h+MaxCount], ebx
0x14004263d  jmp     loc_14004253C
0x140042642  mov     rcx, r14; psz
0x140042645  call    cs:__imp_SysAllocString
0x14004264c  nop     dword ptr [rax+rax+00h]
0x140042651  mov     rsi, rax
0x140042654  test    rax, rax
0x140042657  jnz     loc_1400423F1
0x14004265d  mov     eax, 8007000Eh
0x140042662  mov     r9d, 0B0h
0x140042668  mov     ebx, eax
0x14004266a  jmp     loc_140042538
0x14004266f  call    cs:__imp_GetLastError
0x140042676  nop     dword ptr [rax+rax+00h]
0x14004267b  mov     ebx, eax
0x14004267d  test    eax, eax
0x14004267f  jle     short loc_14004268A
0x140042681  movzx   ebx, ax
0x140042684  or      ebx, 80070000h
0x14004268a  mov     r9d, 75h ; 'u'
0x140042690  mov     [rsp+0F0h+MaxCount], ebx
0x140042694  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x14004269b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400426a2  lea     ecx, [r9-74h]; Level
0x1400426a6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400426ab  mov     r12, [rbp+57h+hLibModule]
0x1400426af  jmp     loc_1400423FE
0x1400426b4  mov     rcx, rdi; psz
0x1400426b7  xor     r12d, r12d
0x1400426ba  xor     ebx, ebx
0x1400426bc  xor     r15d, r15d
0x1400426bf  call    cs:__imp_SysAllocString
0x1400426c6  nop     dword ptr [rax+rax+00h]
0x1400426cb  mov     rsi, rax
0x1400426ce  test    rax, rax
0x1400426d1  jnz     loc_1400423F5
0x1400426d7  mov     eax, 8007000Eh
0x1400426dc  lea     r8, aDwztryloadfile; "DwzTryLoadFileResource"
0x1400426e3  mov     r9d, 0B4h
0x1400426e9  mov     [rsp+0F0h+MaxCount], eax
0x1400426ed  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400426f4  mov     ebx, eax
0x1400426f6  lea     ecx, [rsi+1]; Level
0x1400426f9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400426fe  jmp     loc_140042412
```
