# GetCommonAppDataDirectory(ushort *)

- ea: `0x1801a2834`
- end: `0x1801a2962`
- name: `?GetCommonAppDataDirectory@@YAHPEAG@Z`
- size: `302`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801a360c`

## callees

- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1801a2834`
- `0x1801aef74`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a2922`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1801a2922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a292c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a292c`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a287d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801a287d`

## string_xrefs

- `0x1801a285b`: `shell32.dll`
- `0x1801a2873`: `SHGetSpecialFolderPathW`

## pseudocode

```c
_BOOL8 __fastcall GetCommonAppDataDirectory(unsigned __int16 *a1)
{
  __int64 v1; // rax
  HMODULE SysLib; // rax
  FARPROC ProcAddress; // r10
  unsigned __int64 v4; // rdx
  unsigned __int16 v6[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = qword_1802B7790;
  if ( qword_1802B7790 )
    goto LABEL_5;
  SysLib = LoadSysLib(L"shell32.dll");
  qword_1802B7790 = (__int64)SysLib;
  if ( !SysLib )
  {
    v1 = -1;
    qword_1802B7790 = -1;
LABEL_5:
    ProcAddress = (FARPROC)qword_1802B7578;
    goto LABEL_6;
  }
  ProcAddress = GetProcAddress(SysLib, "SHGetSpecialFolderPathW");
  qword_1802B7578 = (__int64)ProcAddress;
  v1 = qword_1802B7790;
LABEL_6:
  if ( v1 == -1 )
    return 0;
  if ( !ProcAddress )
    return 0;
  v6[0] = 0;
  if ( !((unsigned int (__fastcall *)(_QWORD, unsigned __int16 *, __int64, _QWORD))ProcAddress)(0, v6, 35, 0) )
    return 0;
  wcscpy_s_ex(&PathName, 0x105u, v6);
  if ( !(unsigned int)BackslashCat(&PathName, 261) )
    return 0;
  wcscat_s_ex(&PathName, v4, L"dbg");
  return CreateDirectoryW(&PathName, 0) || GetLastError() == 183;
}

```

## disassembly

```asm
0x1801a2834  push    rdi
0x1801a2836  sub     rsp, 250h
0x1801a283d  mov     rax, cs:__security_cookie
0x1801a2844  xor     rax, rsp
0x1801a2847  mov     [rsp+258h+var_18], rax
0x1801a284f  mov     rax, cs:qword_1802B7790
0x1801a2856  test    rax, rax
0x1801a2859  jnz     short loc_1801A28A1
0x1801a285b  lea     rcx, aShell32Dll; "shell32.dll"
0x1801a2862  call    ?LoadSysLib@@YAPEAUHINSTANCE__@@PEBG@Z; LoadSysLib(ushort const *)
0x1801a2867  mov     cs:qword_1802B7790, rax
0x1801a286e  test    rax, rax
0x1801a2871  jz      short loc_1801A2896
0x1801a2873  lea     rdx, aShgetspecialfo; "SHGetSpecialFolderPathW"
0x1801a287a  mov     rcx, rax; hModule
0x1801a287d  call    cs:__imp_GetProcAddress
0x1801a2883  mov     r10, rax
0x1801a2886  mov     cs:qword_1802B7578, rax
0x1801a288d  mov     rax, cs:qword_1802B7790
0x1801a2894  jmp     short loc_1801A28A8
0x1801a2896  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a289a  mov     cs:qword_1802B7790, rax
0x1801a28a1  mov     r10, cs:qword_1802B7578
0x1801a28a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a28ac  jz      loc_1801A2947
0x1801a28b2  test    r10, r10
0x1801a28b5  jz      loc_1801A2947
0x1801a28bb  xor     eax, eax
0x1801a28bd  lea     rdx, [rsp+258h+var_228]
0x1801a28c2  mov     [rsp+258h+var_228], ax
0x1801a28c7  xor     r9d, r9d
0x1801a28ca  xor     ecx, ecx
0x1801a28cc  lea     r8d, [rax+23h]
0x1801a28d0  mov     rax, r10
0x1801a28d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a28d8  test    eax, eax
0x1801a28da  jz      short loc_1801A2947
0x1801a28dc  mov     edi, 105h
0x1801a28e1  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x1801a28e6  mov     edx, edi; unsigned __int64
0x1801a28e8  lea     rcx, PathName; unsigned __int16 *
0x1801a28ef  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a28f4  mov     edx, edi
0x1801a28f6  lea     rcx, PathName
0x1801a28fd  call    BackslashCat
0x1801a2902  test    eax, eax
0x1801a2904  jz      short loc_1801A2947
0x1801a2906  lea     r8, aDbg_1; "dbg"
0x1801a290d  lea     rcx, PathName; unsigned __int16 *
0x1801a2914  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a2919  xor     edx, edx; lpSecurityAttributes
0x1801a291b  lea     rcx, PathName; lpPathName
0x1801a2922  call    cs:__imp_CreateDirectoryW
0x1801a2928  test    eax, eax
0x1801a292a  jnz     short loc_1801A2940
0x1801a292c  call    cs:__imp_GetLastError
0x1801a2932  xor     ecx, ecx
0x1801a2934  cmp     eax, 0B7h
0x1801a2939  setz    cl
0x1801a293c  mov     eax, ecx
0x1801a293e  jmp     short loc_1801A2949
0x1801a2940  mov     eax, 1
0x1801a2945  jmp     short loc_1801A2949
0x1801a2947  xor     eax, eax
0x1801a2949  mov     rcx, [rsp+258h+var_18]
0x1801a2951  xor     rcx, rsp; StackCookie
0x1801a2954  call    __security_check_cookie
0x1801a2959  add     rsp, 250h
0x1801a2960  pop     rdi
0x1801a2961  retn
```
