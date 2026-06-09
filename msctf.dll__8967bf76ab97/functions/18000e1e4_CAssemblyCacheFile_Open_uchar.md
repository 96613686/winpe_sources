# CAssemblyCacheFile::Open(uchar * *)

- ea: `0x18000e1e4`
- end: `0x18000e376`
- name: `?Open@CAssemblyCacheFile@@QEAA_NPEAPEAE@Z`
- size: `402`
- prototype: `bool __fastcall(CAssemblyCacheFile *__hidden this, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180011e90`

## callees

- `0x18000e1e4`
- `0x18000e418`
- `0x18000e7b0`
- `0x18000fac0`
- `0x18005cb88`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000e272`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000e272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e366`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e366`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000e2fb`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000e2fb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000e31e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000e31e`

## string_xrefs

- `0x18000e2c2`: `Local\CTF.AsmListCache.FMP`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
bool __fastcall CAssemblyCacheFile::Open(CAssemblyCacheFile *this, unsigned __int8 **a2)
{
  _QWORD *v2; // rsi
  HANDLE v5; // rax
  unsigned int v6; // edx
  HANDLE v7; // rax
  LPVOID v8; // rax
  __int64 v10; // [rsp+28h] [rbp-440h]
  unsigned int SessionID; // [rsp+28h] [rbp-440h]
  unsigned __int16 v12[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Name[264]; // [rsp+240h] [rbp-228h] BYREF

  v2 = (_QWORD *)((char *)this + 48);
  *a2 = 0;
  if ( !*((_QWORD *)this + 6) )
  {
    v12[0] = 0;
    GetThreadDesktopName(v12, (unsigned int)a2);
    SessionID = GetSessionID();
    StringCchPrintfW(Name, 0x104u, L"%s%s%d", L"Local\\MSCTF.Asm.Mutex", v12, SessionID);
    v5 = OpenMutexW(0x100000u, 0, Name);
    *v2 = v5;
    if ( !v5 )
      return *a2 != 0;
    *((_QWORD *)this + 5) = v2;
    *((_QWORD *)this + 3) = 0;
    *((_DWORD *)this + 8) = 1;
  }
  if ( (unsigned int)CCicFileMappingStatic::Enter((CAssemblyCacheFile *)((char *)this + 8)) )
  {
    v12[0] = 0;
    GetThreadDesktopName(v12, v6);
    LODWORD(v10) = GetSessionID();
    StringCchPrintfW(Name, 0x104u, L"%s%s%d", L"Local\\CTF.AsmListCache.FMP", v12, v10);
    v7 = OpenFileMappingW(4u, 0, Name);
    *((_QWORD *)this + 2) = v7;
    if ( v7 )
    {
      v8 = MapViewOfFile(v7, 4u, 0, 0, 0);
      *((_QWORD *)this + 1) = v8;
      if ( !v8 )
      {
        CloseHandle(*((HANDLE *)this + 2));
        *((_QWORD *)this + 2) = 0;
      }
      v7 = (HANDLE)*((_QWORD *)this + 1);
    }
    *a2 = (unsigned __int8 *)v7;
  }
  return *a2 != 0;
}

```

## disassembly

```asm
0x18000e1e4  mov     [rsp+arg_10], rbx
0x18000e1e9  mov     [rsp+arg_18], rsi
0x18000e1ee  push    rdi
0x18000e1ef  sub     rsp, 460h
0x18000e1f6  mov     rax, cs:__security_cookie
0x18000e1fd  xor     rax, rsp
0x18000e200  mov     [rsp+468h+var_18], rax
0x18000e208  lea     rsi, [rcx+30h]
0x18000e20c  mov     qword ptr [rdx], 0
0x18000e213  cmp     qword ptr [rsi], 0
0x18000e217  mov     rdi, rdx
0x18000e21a  mov     rbx, rcx
0x18000e21d  jnz     short loc_18000E297
0x18000e21f  xor     eax, eax
0x18000e221  lea     rcx, [rsp+468h+var_438]; unsigned __int16 *
0x18000e226  mov     [rsp+468h+var_438], ax
0x18000e22b  call    ?GetThreadDesktopName@@YAHPEAGK@Z; GetThreadDesktopName(ushort *,ulong)
0x18000e230  call    ?GetSessionID@@YAKXZ; GetSessionID(void)
0x18000e235  mov     dword ptr [rsp+468h+var_440], eax
0x18000e239  lea     r9, aLocalMsctfAsmM; "Local\\MSCTF.Asm.Mutex"
0x18000e240  lea     rax, [rsp+468h+var_438]
0x18000e245  mov     edx, 104h; unsigned __int64
0x18000e24a  lea     r8, aSSD; "%s%s%d"
0x18000e251  mov     [rsp+468h+dwNumberOfBytesToMap], rax
0x18000e256  lea     rcx, [rsp+468h+Name]; unsigned __int16 *
0x18000e25e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e263  lea     r8, [rsp+468h+Name]; lpName
0x18000e26b  xor     edx, edx; bInheritHandle
0x18000e26d  mov     ecx, 100000h; dwDesiredAccess
0x18000e272  call    cs:__imp_OpenMutexW
0x18000e278  mov     [rsi], rax
0x18000e27b  test    rax, rax
0x18000e27e  jz      loc_18000E334
0x18000e284  mov     [rbx+28h], rsi
0x18000e288  mov     qword ptr [rbx+18h], 0
0x18000e290  mov     dword ptr [rbx+20h], 1
0x18000e297  lea     rcx, [rbx+8]; this
0x18000e29b  call    ?Enter@CCicFileMappingStatic@@QEAAHXZ; CCicFileMappingStatic::Enter(void)
0x18000e2a0  test    eax, eax
0x18000e2a2  jz      loc_18000E334
0x18000e2a8  xor     eax, eax
0x18000e2aa  lea     rcx, [rsp+468h+var_438]; unsigned __int16 *
0x18000e2af  mov     [rsp+468h+var_438], ax
0x18000e2b4  call    ?GetThreadDesktopName@@YAHPEAGK@Z; GetThreadDesktopName(ushort *,ulong)
0x18000e2b9  call    ?GetSessionID@@YAKXZ; GetSessionID(void)
0x18000e2be  mov     dword ptr [rsp+468h+var_440], eax
0x18000e2c2  lea     r9, aLocalCtfAsmlis; "Local\\CTF.AsmListCache.FMP"
0x18000e2c9  lea     rax, [rsp+468h+var_438]
0x18000e2ce  mov     edx, 104h; unsigned __int64
0x18000e2d3  lea     r8, aSSD; "%s%s%d"
0x18000e2da  mov     [rsp+468h+dwNumberOfBytesToMap], rax
0x18000e2df  lea     rcx, [rsp+468h+Name]; unsigned __int16 *
0x18000e2e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e2ec  xor     edx, edx; bInheritHandle
0x18000e2ee  lea     r8, [rsp+468h+Name]; lpName
0x18000e2f6  lea     esi, [rdx+4]
0x18000e2f9  mov     ecx, esi; dwDesiredAccess
0x18000e2fb  call    cs:__imp_OpenFileMappingW
0x18000e301  mov     [rbx+10h], rax
0x18000e305  test    rax, rax
0x18000e308  jz      short loc_18000E360
0x18000e30a  xor     r9d, r9d; dwFileOffsetLow
0x18000e30d  mov     [rsp+468h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000e316  xor     r8d, r8d; dwFileOffsetHigh
0x18000e319  mov     edx, esi; dwDesiredAccess
0x18000e31b  mov     rcx, rax; hFileMappingObject
0x18000e31e  call    cs:__imp_MapViewOfFile
0x18000e324  mov     [rbx+8], rax
0x18000e328  test    rax, rax
0x18000e32b  jz      short loc_18000E362
0x18000e32d  mov     rax, [rbx+8]
0x18000e331  mov     [rdi], rax
0x18000e334  cmp     qword ptr [rdi], 0
0x18000e338  setnz   al
0x18000e33b  mov     rcx, [rsp+468h+var_18]
0x18000e343  xor     rcx, rsp; StackCookie
0x18000e346  call    __security_check_cookie
0x18000e34b  lea     r11, [rsp+468h+var_8]
0x18000e353  mov     rbx, [r11+20h]
0x18000e357  mov     rsi, [r11+28h]
0x18000e35b  mov     rsp, r11
0x18000e35e  pop     rdi
0x18000e35f  retn
0x18000e360  jmp     short loc_18000E331
0x18000e362  mov     rcx, [rbx+10h]; hObject
0x18000e366  call    cs:__imp_CloseHandle
0x18000e36c  mov     qword ptr [rbx+10h], 0
0x18000e374  jmp     short loc_18000E32D
```
