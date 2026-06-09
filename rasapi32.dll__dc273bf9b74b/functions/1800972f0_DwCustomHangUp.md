# DwCustomHangUp

- ea: `0x1800972f0`
- end: `0x1800975b0`
- name: `DwCustomHangUp`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180075e60`

## callees

- `0x18000b0f4`
- `0x180011450`
- `0x180028050`
- `0x18004e580`
- `0x18004e984`
- `0x1800972f0`
- `0x1800c09d0`
- `0x1800ded06`
- `0x1800ded50`
- `0x1800dee10`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800974f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800974f0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180097395`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800973a6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180097395`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800973a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097555`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800974e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800974e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800974aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800974aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009748e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009748e`

## pseudocode

```c
__int64 __fastcall DwCustomHangUp(const CHAR *a1, const CHAR *a2, __int64 a3)
{
  DWORD EntryPropertiesW; // ebx
  HMODULE v6; // rsi
  WCHAR *v7; // rdi
  WCHAR *v8; // r15
  WCHAR *v9; // rax
  WCHAR *v10; // r14
  DWORD ExpandedDllPath; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  DWORD v16; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPCCH lpMultiByteStr; // [rsp+40h] [rbp-C0h]
  tagRASENTRYW v19; // [rsp+50h] [rbp-B0h] BYREF

  lpMultiByteStr = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1074, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
  }
  EntryPropertiesW = 0;
  v6 = 0;
  memset_0(&v19, 0, 0x1A44u);
  v16 = 0;
  v7 = 0;
  lpLibFileName = 0;
  v8 = (WCHAR *)GlobalAlloc(0x40u, 0x20Au);
  v9 = (WCHAR *)GlobalAlloc(0x40u, 0x202u);
  v10 = v9;
  if ( v8 )
  {
    if ( v9 )
    {
      StrncpyAtoW_0(v8, a1);
      StrncpyAtoW_0(v10, lpMultiByteStr);
      v16 = 6724;
      v19.dwSize = 6724;
      EntryPropertiesW = RasGetEntryPropertiesW(v8, v10, &v19, &v16, 0, 0);
      if ( !EntryPropertiesW )
      {
        ExpandedDllPath = DwGetExpandedDllPath(v19.szCustomDialDll, (WCHAR **)&lpLibFileName);
        EntryPropertiesW = ExpandedDllPath;
        if ( ExpandedDllPath )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              1075,
              WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
              ExpandedDllPath);
          }
          v7 = (WCHAR *)lpLibFileName;
        }
        else
        {
          v7 = (WCHAR *)lpLibFileName;
          Library = LoadLibraryExW(lpLibFileName, 0, 0);
          v6 = Library;
          if ( Library && (ProcAddress = GetProcAddress(Library, "RasCustomHangUp")) != 0 )
          {
            EntryPropertiesW = ((__int64 (__fastcall *)(__int64))ProcAddress)(a3);
          }
          else
          {
            LastError = GetLastError();
            EntryPropertiesW = LastError;
            if ( LastError
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                1076,
                WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
                LastError);
            }
          }
        }
      }
    }
  }
  Free0(v8);
  Free0(v10);
  if ( v6 )
    FreeLibrary(v6);
  if ( v7 )
    LocalFree(v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      1077,
      WPP_425b3625ab793a6219f8039beff53b24_Traceguids,
      EntryPropertiesW);
  }
  return EntryPropertiesW;
}

```

## disassembly

```asm
0x1800972f0  mov     [rsp-8+arg_18], rbx
0x1800972f5  push    rbp
0x1800972f6  push    rsi
0x1800972f7  push    rdi
0x1800972f8  push    r12
0x1800972fa  push    r13
0x1800972fc  push    r14
0x1800972fe  push    r15
0x180097300  lea     rbp, [rsp-19B0h]
0x180097308  mov     eax, 1AB0h
0x18009730d  call    _alloca_probe
0x180097312  sub     rsp, rax
0x180097315  mov     rax, cs:__security_cookie
0x18009731c  xor     rax, rsp
0x18009731f  mov     [rbp+19E0h+var_40], rax
0x180097326  mov     r12, r8
0x180097329  mov     [rsp+1AE0h+lpMultiByteStr], rdx
0x18009732e  mov     r13, rcx
0x180097331  mov     rcx, cs:WPP_GLOBAL_Control
0x180097338  lea     rax, WPP_GLOBAL_Control
0x18009733f  cmp     rcx, rax
0x180097342  jz      short loc_180097368
0x180097344  test    dword ptr [rcx+1Ch], 800h
0x18009734b  jz      short loc_180097368
0x18009734d  cmp     byte ptr [rcx+19h], 6
0x180097351  jb      short loc_180097368
0x180097353  mov     rcx, [rcx+10h]
0x180097357  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18009735e  mov     edx, 432h
0x180097363  call    WPP_SF_
0x180097368  xor     edx, edx; Val
0x18009736a  lea     rcx, [rsp+1AE0h+var_1A90]; void *
0x18009736f  mov     r8d, 1A44h; Size
0x180097375  xor     ebx, ebx
0x180097377  xor     esi, esi
0x180097379  call    memset_0
0x18009737e  lea     r14d, [rbx+40h]
0x180097382  mov     [rsp+1AE0h+var_1AB0], ebx
0x180097386  xor     edi, edi
0x180097388  mov     ecx, r14d; uFlags
0x18009738b  mov     edx, 20Ah; dwBytes
0x180097390  mov     [rsp+1AE0h+lpLibFileName], rdi
0x180097395  call    cs:__imp_GlobalAlloc
0x18009739b  mov     edx, 202h; dwBytes
0x1800973a0  mov     ecx, r14d; uFlags
0x1800973a3  mov     r15, rax
0x1800973a6  call    cs:__imp_GlobalAlloc
0x1800973ac  mov     r14, rax
0x1800973af  test    r15, r15
0x1800973b2  jz      loc_1800974C3
0x1800973b8  test    rax, rax
0x1800973bb  jz      loc_1800974C3
0x1800973c1  mov     ebx, 0FDE9h
0x1800973c6  mov     r8d, 105h
0x1800973cc  mov     r9d, ebx
0x1800973cf  mov     rdx, r13; lpMultiByteStr
0x1800973d2  mov     rcx, r15; lpWideCharStr
0x1800973d5  call    StrncpyAtoW_0
0x1800973da  mov     rdx, [rsp+1AE0h+lpMultiByteStr]; lpMultiByteStr
0x1800973df  mov     r9d, ebx
0x1800973e2  mov     r8d, 101h
0x1800973e8  mov     rcx, r14; lpWideCharStr
0x1800973eb  call    StrncpyAtoW_0
0x1800973f0  lea     r9, [rsp+1AE0h+var_1AB0]; LPDWORD
0x1800973f5  mov     [rsp+1AE0h+var_1AB8], rsi; LPDWORD
0x1800973fa  lea     r8, [rsp+1AE0h+var_1A90]; struct tagRASENTRYW *
0x1800973ff  mov     [rsp+1AE0h+var_1AB0], 1A44h
0x180097407  mov     rdx, r14; LPCWSTR
0x18009740a  mov     [rsp+1AE0h+var_1A90.dwSize], 1A44h
0x180097412  mov     rcx, r15; LPCWSTR
0x180097415  mov     [rsp+1AE0h+var_1AC0], rsi; LPBYTE
0x18009741a  call    RasGetEntryPropertiesW
0x18009741f  mov     ebx, eax
0x180097421  test    eax, eax
0x180097423  jnz     loc_1800974C3
0x180097429  lea     rdx, [rsp+1AE0h+lpLibFileName]
0x18009742e  lea     rcx, [rbp+19E0h+var_1A90.szCustomDialDll]; lpSrc
0x180097435  call    DwGetExpandedDllPath
0x18009743a  mov     ebx, eax
0x18009743c  test    eax, eax
0x18009743e  jz      short loc_180097481
0x180097440  mov     rcx, cs:WPP_GLOBAL_Control
0x180097447  lea     r12, WPP_GLOBAL_Control
0x18009744e  cmp     rcx, r12
0x180097451  jz      short loc_18009747A
0x180097453  test    dword ptr [rcx+1Ch], 800h
0x18009745a  jz      short loc_18009747A
0x18009745c  cmp     byte ptr [rcx+19h], 2
0x180097460  jb      short loc_18009747A
0x180097462  mov     rcx, [rcx+10h]
0x180097466  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18009746d  mov     edx, 433h
0x180097472  mov     r9d, eax
0x180097475  call    WPP_SF_d
0x18009747a  mov     rdi, [rsp+1AE0h+lpLibFileName]
0x18009747f  jmp     short loc_1800974CA
0x180097481  mov     rdi, [rsp+1AE0h+lpLibFileName]
0x180097486  xor     r8d, r8d; dwFlags
0x180097489  mov     rcx, rdi; lpLibFileName
0x18009748c  xor     edx, edx; hFile
0x18009748e  call    cs:__imp_LoadLibraryExW
0x180097494  mov     rsi, rax
0x180097497  test    rax, rax
0x18009749a  jz      loc_180097555
0x1800974a0  lea     rdx, aRascustomhangu; "RasCustomHangUp"
0x1800974a7  mov     rcx, rax; hModule
0x1800974aa  call    cs:__imp_GetProcAddress
0x1800974b0  test    rax, rax
0x1800974b3  jz      loc_180097555
0x1800974b9  mov     rcx, r12
0x1800974bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800974c1  mov     ebx, eax
0x1800974c3  lea     r12, WPP_GLOBAL_Control
0x1800974ca  mov     rcx, r15
0x1800974cd  call    Free0
0x1800974d2  mov     rcx, r14
0x1800974d5  call    Free0
0x1800974da  test    rsi, rsi
0x1800974dd  jz      short loc_1800974E8
0x1800974df  mov     rcx, rsi; hLibModule
0x1800974e2  call    cs:__imp_FreeLibrary
0x1800974e8  test    rdi, rdi
0x1800974eb  jz      short loc_1800974F6
0x1800974ed  mov     rcx, rdi; hMem
0x1800974f0  call    cs:__imp_LocalFree
0x1800974f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800974fd  cmp     rcx, r12
0x180097500  jz      short loc_180097529
0x180097502  test    dword ptr [rcx+1Ch], 800h
0x180097509  jz      short loc_180097529
0x18009750b  cmp     byte ptr [rcx+19h], 6
0x18009750f  jb      short loc_180097529
0x180097511  mov     rcx, [rcx+10h]
0x180097515  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18009751c  mov     edx, 435h
0x180097521  mov     r9d, ebx
0x180097524  call    WPP_SF_d
0x180097529  mov     eax, ebx
0x18009752b  mov     rcx, [rbp+19E0h+var_40]
0x180097532  xor     rcx, rsp; StackCookie
0x180097535  call    __security_check_cookie
0x18009753a  mov     rbx, [rsp+1AE0h+arg_18]
0x180097542  add     rsp, 1AB0h
0x180097549  pop     r15
0x18009754b  pop     r14
0x18009754d  pop     r13
0x18009754f  pop     r12
0x180097551  pop     rdi
0x180097552  pop     rsi
0x180097553  pop     rbp
0x180097554  retn
0x180097555  call    cs:__imp_GetLastError
0x18009755b  mov     ebx, eax
0x18009755d  test    eax, eax
0x18009755f  jz      loc_1800974C3
0x180097565  mov     rcx, cs:WPP_GLOBAL_Control
0x18009756c  lea     r12, WPP_GLOBAL_Control
0x180097573  cmp     rcx, r12
0x180097576  jz      loc_1800974CA
0x18009757c  test    dword ptr [rcx+1Ch], 800h
0x180097583  jz      loc_1800974CA
0x180097589  cmp     byte ptr [rcx+19h], 2
0x18009758d  jb      loc_1800974CA
0x180097593  mov     rcx, [rcx+10h]
0x180097597  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x18009759e  mov     edx, 434h
0x1800975a3  mov     r9d, eax
0x1800975a6  call    WPP_SF_d
0x1800975ab  jmp     loc_1800974CA
```
