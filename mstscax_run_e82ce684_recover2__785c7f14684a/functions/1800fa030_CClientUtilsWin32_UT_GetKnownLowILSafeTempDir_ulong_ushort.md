# CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(ulong,ushort *)

- ea: `0x1800fa030`
- end: `0x1800fa326`
- name: `?UT_GetKnownLowILSafeTempDir@CClientUtilsWin32@@SAJKPEAG@Z`
- size: `758`
- prototype: `static int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1804aad5c`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180085e04`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x1800fa030`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800fa08f`
- `KERNEL32!GetLastError` at `0x1800fa0cc`
- `KERNEL32!GetLastError` at `0x1800fa11e`
- `KERNEL32!GetLastError` at `0x1800fa232`
- `KERNEL32!GetLastError` at `0x1800fa08f`
- `KERNEL32!GetLastError` at `0x1800fa0cc`
- `KERNEL32!GetLastError` at `0x1800fa11e`
- `KERNEL32!GetLastError` at `0x1800fa232`
- `KERNEL32!LoadLibraryExW` at `0x1800fa062`
- `KERNEL32!LoadLibraryExW` at `0x1800fa062`
- `KERNEL32!CreateDirectoryW` at `0x1800fa224`
- `KERNEL32!CreateDirectoryW` at `0x1800fa224`
- `KERNEL32!GetProcAddress` at `0x1800fa0f4`
- `KERNEL32!GetProcAddress` at `0x1800fa0f4`
- `KERNEL32!FreeLibrary` at `0x1800fa30a`
- `KERNEL32!FreeLibrary` at `0x1800fa30a`
- `OLE32!CoTaskMemFree` at `0x1800fa2fc`
- `OLE32!CoTaskMemFree` at `0x1800fa2fc`

## string_xrefs

- `0x1800fa059`: `shell32.dll`
- `0x1800fa0ea`: `SHGetKnownFolderPath`
- `0x1800fa1a1`: `%s\Temp`
- `0x1800fa193`: `SHGetKnownFolderPath(LocalAppDataLow) failed`
- `0x1800fa1f0`: `StringCchPrintf(KnownFolderPath\Temp) failed`

## pseudocode

```c
__int64 __fastcall CClientUtilsWin32::UT_GetKnownLowILSafeTempDir(__int64 a1, unsigned __int16 *a2)
{
  void *v2; // rcx
  HMODULE Library; // rax
  HMODULE v5; // r14
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // ebx
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  signed int LastError; // eax
  signed int v18; // ebp
  HKEY v19; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v21; // eax
  void *v23; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v23 = 0;
  if ( a2 )
  {
    Library = LoadLibraryExW(L"shell32.dll", 0, 0);
    v5 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "SHGetKnownFolderPath");
      if ( ProcAddress )
      {
        v11 = ((__int64 (__fastcall *)(const GUID *, _QWORD, _QWORD, void **))ProcAddress)(
                &FOLDERID_LocalAppDataLow,
                0,
                0,
                &v23);
        if ( v11 >= 0 )
        {
          v11 = StringCchPrintfW(a2, 0x104u, L"%s\\Temp", v23);
          if ( v11 >= 0 )
          {
            if ( CreateDirectoryW(a2, 0) )
              goto LABEL_45;
            LastError = GetLastError();
            v18 = LastError;
            if ( LastError == 183 )
              goto LABEL_45;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
            else
              v11 = LastError;
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
            {
              if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  52,
                  &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  CurrentThreadActivityIdPrefix,
                  v18);
                v19 = WPP_GLOBAL_Control;
              }
              if ( v19 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v19[7] & 1) != 0 && *((_BYTE *)v19 + 25) >= 3u )
              {
                v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  53,
                  (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
                  v21,
                  (__int64)a2);
              }
            }
LABEL_43:
            if ( v11 >= 0 )
            {
LABEL_45:
              v2 = v23;
              goto LABEL_47;
            }
LABEL_44:
            *a2 = 0;
            goto LABEL_45;
          }
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 51;
          v16 = "StringCchPrintf(KnownFolderPath\\Temp) failed";
        }
        else
        {
          if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
            || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_44;
          }
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 50;
          v16 = "SHGetKnownFolderPath(LocalAppDataLow) failed";
        }
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v15,
          (unsigned int)&WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids,
          v14,
          (__int64)v16,
          v11);
        goto LABEL_44;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = GetLastError();
        v7 = v13;
        if ( v13 > 0 )
          v7 = (unsigned __int16)v13 | 0x80070000;
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 49;
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 48;
LABEL_9:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids, v8, v7);
    }
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_43;
  }
  v5 = 0;
  v11 = -2147024809;
LABEL_47:
  if ( v2 )
    CoTaskMemFree(v2);
  if ( v5 )
    FreeLibrary(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800fa030  mov     [rsp+arg_0], rbx
0x1800fa035  mov     [rsp+arg_10], rbp
0x1800fa03a  push    rdi
0x1800fa03b  push    r14
0x1800fa03d  push    r15
0x1800fa03f  sub     rsp, 30h
0x1800fa043  xor     ecx, ecx; pv
0x1800fa045  mov     r15, rdx
0x1800fa048  mov     [rsp+48h+arg_8], rcx
0x1800fa04d  test    rdx, rdx
0x1800fa050  jz      loc_1800FA2EF
0x1800fa056  xor     r8d, r8d; dwFlags
0x1800fa059  lea     rcx, aShell32Dll_0; "shell32.dll"
0x1800fa060  xor     edx, edx; hFile
0x1800fa062  call    cs:__imp_LoadLibraryExW
0x1800fa068  mov     r14, rax
0x1800fa06b  test    rax, rax
0x1800fa06e  jnz     short loc_1800FA0EA
0x1800fa070  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa077  lea     rdi, WPP_GLOBAL_Control
0x1800fa07e  cmp     rcx, rdi
0x1800fa081  jz      short loc_1800FA0CC
0x1800fa083  test    byte ptr [rcx+1Ch], 8
0x1800fa087  jz      short loc_1800FA0CC
0x1800fa089  cmp     byte ptr [rcx+19h], 2
0x1800fa08d  jb      short loc_1800FA0CC
0x1800fa08f  call    cs:__imp_GetLastError
0x1800fa095  mov     ebx, eax
0x1800fa097  test    eax, eax
0x1800fa099  jle     short loc_1800FA0A4
0x1800fa09b  movzx   ebx, ax
0x1800fa09e  or      ebx, 80070000h
0x1800fa0a4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa0a9  mov     edx, 30h ; '0'
0x1800fa0ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa0b5  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1800fa0bc  mov     r9d, eax
0x1800fa0bf  mov     dword ptr [rsp+48h+var_28], ebx
0x1800fa0c3  mov     rcx, [rcx+10h]
0x1800fa0c7  call    WPP_SF_Dd
0x1800fa0cc  call    cs:__imp_GetLastError
0x1800fa0d2  mov     ebx, eax
0x1800fa0d4  test    eax, eax
0x1800fa0d6  jle     loc_1800FA2DE
0x1800fa0dc  movzx   ebx, ax
0x1800fa0df  or      ebx, 80070000h
0x1800fa0e5  jmp     loc_1800FA2DE
0x1800fa0ea  lea     rdx, aShgetknownfold; "SHGetKnownFolderPath"
0x1800fa0f1  mov     rcx, rax; hModule
0x1800fa0f4  call    cs:__imp_GetProcAddress
0x1800fa0fa  test    rax, rax
0x1800fa0fd  jnz     short loc_1800FA142
0x1800fa0ff  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa106  lea     rdi, WPP_GLOBAL_Control
0x1800fa10d  cmp     rax, rdi
0x1800fa110  jz      short loc_1800FA0CC
0x1800fa112  test    byte ptr [rax+1Ch], 8
0x1800fa116  jz      short loc_1800FA0CC
0x1800fa118  cmp     byte ptr [rax+19h], 2
0x1800fa11c  jb      short loc_1800FA0CC
0x1800fa11e  call    cs:__imp_GetLastError
0x1800fa124  mov     ebx, eax
0x1800fa126  test    eax, eax
0x1800fa128  jle     short loc_1800FA133
0x1800fa12a  movzx   ebx, ax
0x1800fa12d  or      ebx, 80070000h
0x1800fa133  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa138  mov     edx, 31h ; '1'
0x1800fa13d  jmp     loc_1800FA0AE
0x1800fa142  lea     r9, [rsp+48h+arg_8]
0x1800fa147  xor     r8d, r8d
0x1800fa14a  xor     edx, edx
0x1800fa14c  lea     rcx, FOLDERID_LocalAppDataLow
0x1800fa153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fa158  mov     ebx, eax
0x1800fa15a  test    eax, eax
0x1800fa15c  jns     short loc_1800FA19C
0x1800fa15e  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa165  lea     rdi, WPP_GLOBAL_Control
0x1800fa16c  cmp     rax, rdi
0x1800fa16f  jz      loc_1800FA2E2
0x1800fa175  test    byte ptr [rax+1Ch], 8
0x1800fa179  jz      loc_1800FA2E2
0x1800fa17f  cmp     byte ptr [rax+19h], 2
0x1800fa183  jb      loc_1800FA2E2
0x1800fa189  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa18e  mov     edx, 32h ; '2'
0x1800fa193  lea     rcx, aShgetknownfold_0; "SHGetKnownFolderPath(LocalAppDataLow) f"...
0x1800fa19a  jmp     short loc_1800FA1F7
0x1800fa19c  mov     r9, [rsp+48h+arg_8]
0x1800fa1a1  lea     r8, aSTemp; "%s\\Temp"
0x1800fa1a8  mov     edx, 104h; unsigned __int64
0x1800fa1ad  mov     rcx, r15; unsigned __int16 *
0x1800fa1b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fa1b5  mov     ebx, eax
0x1800fa1b7  test    eax, eax
0x1800fa1b9  jns     short loc_1800FA21F
0x1800fa1bb  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa1c2  lea     rdi, WPP_GLOBAL_Control
0x1800fa1c9  cmp     rax, rdi
0x1800fa1cc  jz      loc_1800FA2E2
0x1800fa1d2  test    byte ptr [rax+1Ch], 8
0x1800fa1d6  jz      loc_1800FA2E2
0x1800fa1dc  cmp     byte ptr [rax+19h], 2
0x1800fa1e0  jb      loc_1800FA2E2
0x1800fa1e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa1eb  mov     edx, 33h ; '3'
0x1800fa1f0  lea     rcx, aStringcchprint_16; "StringCchPrintf(KnownFolderPath\\Temp) "...
0x1800fa1f7  mov     [rsp+48h+var_20], ebx
0x1800fa1fb  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1800fa202  mov     [rsp+48h+var_28], rcx
0x1800fa207  mov     r9d, eax
0x1800fa20a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa211  mov     rcx, [rcx+10h]
0x1800fa215  call    WPP_SF_DsD
0x1800fa21a  jmp     loc_1800FA2E2
0x1800fa21f  xor     edx, edx; lpSecurityAttributes
0x1800fa221  mov     rcx, r15; lpPathName
0x1800fa224  call    cs:__imp_CreateDirectoryW
0x1800fa22a  test    eax, eax
0x1800fa22c  jnz     loc_1800FA2E8
0x1800fa232  call    cs:__imp_GetLastError
0x1800fa238  mov     ebp, eax
0x1800fa23a  cmp     eax, 0B7h
0x1800fa23f  jz      loc_1800FA2E8
0x1800fa245  test    eax, eax
0x1800fa247  jg      short loc_1800FA24D
0x1800fa249  mov     ebx, eax
0x1800fa24b  jmp     short loc_1800FA256
0x1800fa24d  movzx   ebx, bp
0x1800fa250  or      ebx, 80070000h
0x1800fa256  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa25d  lea     rdi, WPP_GLOBAL_Control
0x1800fa264  cmp     rax, rdi
0x1800fa267  jz      short loc_1800FA2DE
0x1800fa269  test    byte ptr [rax+1Ch], 1
0x1800fa26d  jz      short loc_1800FA2A4
0x1800fa26f  cmp     byte ptr [rax+19h], 2
0x1800fa273  jb      short loc_1800FA2A4
0x1800fa275  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa27a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa281  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1800fa288  mov     edx, 34h ; '4'
0x1800fa28d  mov     dword ptr [rsp+48h+var_28], ebp
0x1800fa291  mov     r9d, eax
0x1800fa294  mov     rcx, [rcx+10h]
0x1800fa298  call    WPP_SF_Dd
0x1800fa29d  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa2a4  cmp     rax, rdi
0x1800fa2a7  jz      short loc_1800FA2DE
0x1800fa2a9  test    byte ptr [rax+1Ch], 1
0x1800fa2ad  jz      short loc_1800FA2DE
0x1800fa2af  cmp     byte ptr [rax+19h], 3
0x1800fa2b3  jb      short loc_1800FA2DE
0x1800fa2b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa2ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fa2c1  lea     r8, WPP_32fa989a62503b6cc115b7f5368ef77a_Traceguids
0x1800fa2c8  mov     edx, 35h ; '5'
0x1800fa2cd  mov     [rsp+48h+var_28], r15
0x1800fa2d2  mov     r9d, eax
0x1800fa2d5  mov     rcx, [rcx+10h]
0x1800fa2d9  call    WPP_SF_DS
0x1800fa2de  test    ebx, ebx
0x1800fa2e0  jns     short loc_1800FA2E8
0x1800fa2e2  xor     eax, eax
0x1800fa2e4  mov     [r15], ax
0x1800fa2e8  mov     rcx, [rsp+48h+arg_8]
0x1800fa2ed  jmp     short loc_1800FA2F7
0x1800fa2ef  xor     r14d, r14d
0x1800fa2f2  mov     ebx, 80070057h
0x1800fa2f7  test    rcx, rcx
0x1800fa2fa  jz      short loc_1800FA302
0x1800fa2fc  call    cs:__imp_CoTaskMemFree
0x1800fa302  test    r14, r14
0x1800fa305  jz      short loc_1800FA310
0x1800fa307  mov     rcx, r14; hLibModule
0x1800fa30a  call    cs:__imp_FreeLibrary
0x1800fa310  mov     rbp, [rsp+48h+arg_10]
0x1800fa315  mov     eax, ebx
0x1800fa317  mov     rbx, [rsp+48h+arg_0]
0x1800fa31c  add     rsp, 30h
0x1800fa320  pop     r15
0x1800fa322  pop     r14
0x1800fa324  pop     rdi
0x1800fa325  retn
```
