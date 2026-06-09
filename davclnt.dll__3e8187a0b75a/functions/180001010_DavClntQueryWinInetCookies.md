# DavClntQueryWinInetCookies

- ea: `0x180001010`
- end: `0x180001305`
- name: `DavClntQueryWinInetCookies`
- size: `757`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001310`
- `0x180003b90`
- `0x180007ad0`
- `0x18000e034`
- `0x18000e494`

## callees

- `0x180001010`
- `0x180010a14`
- `0x180010be8`
- `0x180010c28`
- `0x180011244`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800010bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800010bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001246`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800010af`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800010f8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800010f8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180001083`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180001083`
- `KERNEL32!LocalAlloc` at `0x18000119a`
- `KERNEL32!LocalAlloc` at `0x18000119a`
- `KERNEL32!LocalFree` at `0x180001251`
- `KERNEL32!LocalFree` at `0x180001251`

## string_xrefs

- `0x18000107c`: `WinInet.dll`

## pseudocode

```c
__int64 __fastcall DavClntQueryWinInetCookies(__int64 a1, _QWORD *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbp
  DWORD LastError; // esi
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v8)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // r12
  DWORD v9; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  char *v13; // r15
  int v14; // eax
  SIZE_T v15; // rsi
  char *v16; // rax
  SIZE_T v17; // rsi
  __int64 v18; // rcx
  const wchar_t *v19; // rdx
  char *v20; // rcx
  int v22; // [rsp+70h] [rbp+8h] BYREF

  v22 = 0;
  if ( !a1 || !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 338, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    LastError = 87;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a1);
  LibraryW = LoadLibraryW(L"WinInet.dll");
  v5 = LibraryW;
  if ( !LibraryW )
  {
    LastError = 1157;
LABEL_45:
    *a2 = 0;
    goto LABEL_46;
  }
  ProcAddress = GetProcAddress(LibraryW, "InternetGetCookieExW");
  v8 = (unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))ProcAddress;
  if ( ProcAddress )
  {
    LastError = 0;
    if ( !((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, int *, int, _QWORD))ProcAddress)(
            a1,
            0,
            0,
            &v22,
            0x2000,
            0) )
      LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 341, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    if ( LastError == 122 )
    {
      v14 = v22;
    }
    else
    {
      v13 = 0;
      if ( LastError )
        goto LABEL_14;
      v14 = v22;
      if ( !v22 )
        goto LABEL_14;
    }
    v15 = (unsigned int)(v14 + 18);
    v16 = (char *)LocalAlloc(0x40u, v15);
    v13 = v16;
    if ( v16 )
    {
      v17 = v15 >> 1;
      if ( v17 )
      {
        v18 = 2147483646;
        v19 = L"Cookie: ";
        do
        {
          if ( !v18 )
            break;
          if ( !*v19 )
            break;
          *(_WORD *)v16 = *v19++;
          v16 += 2;
          --v18;
          --v17;
        }
        while ( v17 );
        v20 = v16 - 2;
        if ( v17 )
          v20 = v16;
        *(_WORD *)v20 = 0;
      }
      LastError = 0;
      if ( v8(a1, 0, v13 + 16, &v22, 0x2000, 0) )
        goto LABEL_14;
      LastError = GetLastError();
      LocalFree(v13);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_13;
      v11 = 343;
      v12 = LastError;
    }
    else
    {
      LastError = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v11 = 342;
      v12 = 8;
    }
  }
  else
  {
    v9 = GetLastError();
    LastError = v9;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v11 = 340;
    v12 = v9;
  }
  WPP_SF_d(v10[2], v11, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v12);
LABEL_13:
  v13 = 0;
LABEL_14:
  *a2 = v13;
  FreeLibrary(v5);
LABEL_46:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180001010  mov     rax, rsp
0x180001013  push    rsi
0x180001014  sub     rsp, 60h
0x180001018  mov     [rax+10h], rbx
0x18000101c  mov     rbx, rdx
0x18000101f  mov     [rax+18h], rbp
0x180001023  mov     [rax+20h], rdi
0x180001027  mov     [rax-18h], r13
0x18000102b  xor     r13d, r13d
0x18000102e  mov     [rax-20h], r14
0x180001032  mov     r14, rcx
0x180001035  mov     [rax+8], r13d
0x180001039  test    rcx, rcx
0x18000103c  jz      loc_18000127E
0x180001042  test    rdx, rdx
0x180001045  jz      loc_18000127E
0x18000104b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001052  lea     rdi, WPP_GLOBAL_Control
0x180001059  cmp     rcx, rdi
0x18000105c  jz      short loc_18000107C
0x18000105e  test    byte ptr [rcx+1Ch], 20h
0x180001062  jz      short loc_18000107C
0x180001064  mov     rcx, [rcx+10h]
0x180001068  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000106f  mov     edx, 153h
0x180001074  mov     r9, r14
0x180001077  call    WPP_SF_S
0x18000107c  lea     rcx, LibFileName; "WinInet.dll"
0x180001083  call    cs:__imp_LoadLibraryW
0x180001089  mov     rbp, rax
0x18000108c  test    rax, rax
0x18000108f  jnz     short loc_18000109B
0x180001091  mov     esi, 485h
0x180001096  jmp     loc_1800012B1
0x18000109b  mov     [rsp+68h+var_10], r12
0x1800010a0  lea     rdx, ProcName; "InternetGetCookieExW"
0x1800010a7  mov     rcx, rbp; hModule
0x1800010aa  mov     [rsp+68h+var_28], r15
0x1800010af  call    cs:__imp_GetProcAddress
0x1800010b5  mov     r12, rax
0x1800010b8  test    rax, rax
0x1800010bb  jnz     short loc_18000110D
0x1800010bd  call    cs:__imp_GetLastError
0x1800010c3  mov     esi, eax
0x1800010c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800010cc  cmp     rcx, rdi
0x1800010cf  jz      short loc_1800010EF
0x1800010d1  test    byte ptr [rcx+1Ch], 1
0x1800010d5  jz      short loc_1800010EF
0x1800010d7  mov     edx, 154h
0x1800010dc  mov     r9d, eax
0x1800010df  mov     rcx, [rcx+10h]
0x1800010e3  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800010ea  call    WPP_SF_d
0x1800010ef  mov     r15, r13
0x1800010f2  mov     rcx, rbp; hLibModule
0x1800010f5  mov     [rbx], r15
0x1800010f8  call    cs:__imp_FreeLibrary
0x1800010fe  mov     r15, [rsp+68h+var_28]
0x180001103  mov     r12, [rsp+68h+var_10]
0x180001108  jmp     loc_1800012B4
0x18000110d  mov     [rsp+68h+var_40], r13
0x180001112  lea     r9, [rsp+68h+arg_0]
0x180001117  xor     r8d, r8d
0x18000111a  mov     [rsp+68h+var_48], 2000h
0x180001122  xor     edx, edx
0x180001124  mov     rcx, r14
0x180001127  mov     esi, r13d
0x18000112a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000112f  test    eax, eax
0x180001131  jnz     short loc_18000113B
0x180001133  call    cs:__imp_GetLastError
0x180001139  mov     esi, eax
0x18000113b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001142  cmp     rcx, rdi
0x180001145  jz      short loc_18000116D
0x180001147  test    byte ptr [rcx+1Ch], 1
0x18000114b  jz      short loc_18000116D
0x18000114d  mov     eax, [rsp+68h+arg_0]
0x180001151  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180001158  mov     rcx, [rcx+10h]
0x18000115c  mov     edx, 155h
0x180001161  mov     r9d, esi
0x180001164  mov     [rsp+68h+var_48], eax
0x180001168  call    WPP_SF_dd
0x18000116d  cmp     esi, 7Ah ; 'z'
0x180001170  jz      short loc_18000118A
0x180001172  mov     r15, r13
0x180001175  test    esi, esi
0x180001177  jnz     loc_1800010F2
0x18000117d  mov     eax, [rsp+68h+arg_0]
0x180001181  test    eax, eax
0x180001183  jnz     short loc_18000118E
0x180001185  jmp     loc_1800010F2
0x18000118a  mov     eax, [rsp+68h+arg_0]
0x18000118e  add     eax, 12h
0x180001191  mov     ecx, 40h ; '@'; uFlags
0x180001196  mov     edx, eax; uBytes
0x180001198  mov     esi, eax
0x18000119a  call    cs:__imp_LocalAlloc
0x1800011a0  mov     r15, rax
0x1800011a3  test    rax, rax
0x1800011a6  jnz     short loc_1800011D4
0x1800011a8  mov     esi, 8
0x1800011ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800011b4  cmp     rcx, rdi
0x1800011b7  jz      loc_1800010EF
0x1800011bd  test    byte ptr [rcx+1Ch], 1
0x1800011c1  jz      loc_1800010EF
0x1800011c7  mov     edx, 156h
0x1800011cc  mov     r9d, esi
0x1800011cf  jmp     loc_1800010DF
0x1800011d4  shr     rsi, 1
0x1800011d7  jz      short loc_180001218
0x1800011d9  mov     ecx, 7FFFFFFEh
0x1800011de  lea     rdx, aCookie; "Cookie: "
0x1800011e5  test    rcx, rcx
0x1800011e8  jz      short loc_180001209
0x1800011ea  movzx   r8d, word ptr [rdx]
0x1800011ee  test    r8w, r8w
0x1800011f2  jz      short loc_180001209
0x1800011f4  mov     [rax], r8w
0x1800011f8  add     rdx, 2
0x1800011fc  add     rax, 2
0x180001200  dec     rcx
0x180001203  sub     rsi, 1
0x180001207  jnz     short loc_1800011E5
0x180001209  test    rsi, rsi
0x18000120c  lea     rcx, [rax-2]
0x180001210  cmovnz  rcx, rax
0x180001214  mov     [rcx], r13w
0x180001218  lea     r8, [r15+10h]
0x18000121c  mov     [rsp+68h+var_40], r13
0x180001221  lea     r9, [rsp+68h+arg_0]
0x180001226  mov     [rsp+68h+var_48], 2000h
0x18000122e  xor     edx, edx
0x180001230  mov     rcx, r14
0x180001233  mov     rax, r12
0x180001236  mov     esi, r13d
0x180001239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000123e  test    eax, eax
0x180001240  jnz     loc_1800010F2
0x180001246  call    cs:__imp_GetLastError
0x18000124c  mov     rcx, r15; hMem
0x18000124f  mov     esi, eax
0x180001251  call    cs:__imp_LocalFree
0x180001257  mov     rcx, cs:WPP_GLOBAL_Control
0x18000125e  cmp     rcx, rdi
0x180001261  jz      loc_1800010EF
0x180001267  test    byte ptr [rcx+1Ch], 2
0x18000126b  jz      loc_1800010EF
0x180001271  mov     edx, 157h
0x180001276  mov     r9d, esi
0x180001279  jmp     loc_1800010DF
0x18000127e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001285  lea     rdi, WPP_GLOBAL_Control
0x18000128c  cmp     rcx, rdi
0x18000128f  jz      short loc_1800012AC
0x180001291  test    byte ptr [rcx+1Ch], 1
0x180001295  jz      short loc_1800012AC
0x180001297  mov     rcx, [rcx+10h]
0x18000129b  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800012a2  mov     edx, 152h
0x1800012a7  call    WPP_SF_
0x1800012ac  mov     esi, 57h ; 'W'
0x1800012b1  mov     [rbx], r13
0x1800012b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800012bb  mov     r14, [rsp+68h+var_20]
0x1800012c0  cmp     rcx, rdi
0x1800012c3  mov     rdi, [rsp+68h+arg_18]
0x1800012cb  mov     r13, [rsp+68h+var_18]
0x1800012d0  mov     rbp, [rsp+68h+arg_10]
0x1800012d8  mov     rbx, [rsp+68h+arg_8]
0x1800012dd  jz      short loc_1800012FD
0x1800012df  test    byte ptr [rcx+1Ch], 20h
0x1800012e3  jz      short loc_1800012FD
0x1800012e5  mov     rcx, [rcx+10h]
0x1800012e9  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x1800012f0  mov     edx, 158h
0x1800012f5  mov     r9d, esi
0x1800012f8  call    WPP_SF_d
0x1800012fd  mov     eax, esi
0x1800012ff  add     rsp, 60h
0x180001303  pop     rsi
0x180001304  retn
```
