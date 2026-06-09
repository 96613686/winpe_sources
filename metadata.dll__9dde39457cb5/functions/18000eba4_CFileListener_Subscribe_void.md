# CFileListener::Subscribe(void)

- ea: `0x18000eba4`
- end: `0x18000ed3d`
- name: `?Subscribe@CFileListener@@QEAAJXZ`
- size: `409`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f128`

## callees

- `0x18000a528`
- `0x18000ea0c`
- `0x18000eba4`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!RegisterWaitForSingleObject` at `0x18000ecc9`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000ecc9`
- `KERNEL32!FindFirstChangeNotificationW` at `0x18000ec23`
- `KERNEL32!FindFirstChangeNotificationW` at `0x18000ec23`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec8d`
- `KERNEL32!LeaveCriticalSection` at `0x18000ec8d`
- `KERNEL32!EnterCriticalSection` at `0x18000ec6e`
- `KERNEL32!EnterCriticalSection` at `0x18000ec6e`
- `KERNEL32!CompareFileTime` at `0x18000ec80`
- `KERNEL32!CompareFileTime` at `0x18000ec80`
- `KERNEL32!GetLastError` at `0x18000ecd6`
- `KERNEL32!GetLastError` at `0x18000ecd6`
- `KERNEL32!GetFileAttributesExW` at `0x18000ec51`
- `KERNEL32!GetFileAttributesExW` at `0x18000ec51`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ec14`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ec41`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ec14`
- `IisRTL!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000ec41`

## pseudocode

```c
__int64 __fastcall CFileListener::Subscribe(HANDLE *this)
{
  signed int v2; // ebx
  int v3; // esi
  const WCHAR *Str; // rax
  HANDLE v5; // rax
  const WCHAR *v6; // rax
  signed int LastError; // eax
  __int128 FileInformation; // [rsp+30h] [rbp-38h] BYREF
  FILETIME FileTime1[2]; // [rsp+40h] [rbp-28h] BYREF
  int v11; // [rsp+50h] [rbp-18h]

  v11 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  if ( *((_DWORD *)this + 152) )
  {
    v2 = -2147418113;
LABEL_15:
    CFileListener::StopListening((CFileListener *)this, (void *)0xFFFFFFFFFFFFFFFFLL);
    return (unsigned int)v2;
  }
  *((_DWORD *)this + 152) = 1;
  if ( *((_DWORD *)this + 137) )
  {
    v2 = AttemptNetConnection();
    if ( v2 < 0 )
      goto LABEL_15;
  }
  v3 = 0;
  Str = STRU::QueryStr((STRU *)(this + 40));
  v5 = FindFirstChangeNotificationW(Str, 0, 0x11u);
  this[72] = v5;
  if ( v5 != (HANDLE)-1LL )
  {
    v6 = STRU::QueryStr((STRU *)(this + 33));
    if ( GetFileAttributesExW(v6, GetFileExInfoStandard, &FileInformation) )
    {
      this[74] = *(HANDLE *)&FileTime1[0].dwHighDateTime;
      EnterCriticalSection(&CriticalSection);
      CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, &FileTime2);
      LeaveCriticalSection(&CriticalSection);
      (*(void (__fastcall **)(HANDLE *))*this)(this);
      if ( RegisterWaitForSingleObject(this + 73, this[72], CFileListener::sChangeCallback, this, 0xFFFFFFFF, 0x94u) )
        return 0;
      v3 = 1;
    }
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( v2 < 0 )
  {
    if ( v3 && !this[73] )
      (*((void (__fastcall **)(HANDLE *))*this + 1))(this);
    goto LABEL_15;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000eba4  mov     [rsp+arg_8], rbx
0x18000eba9  mov     [rsp+arg_10], rsi
0x18000ebae  push    rdi
0x18000ebaf  sub     rsp, 60h
0x18000ebb3  mov     rax, cs:__security_cookie
0x18000ebba  xor     rax, rsp
0x18000ebbd  mov     [rsp+68h+var_10], rax
0x18000ebc2  xor     eax, eax
0x18000ebc4  xorps   xmm0, xmm0
0x18000ebc7  mov     rdi, rcx
0x18000ebca  mov     [rsp+68h+var_18], eax
0x18000ebce  movups  [rsp+68h+FileInformation], xmm0
0x18000ebd3  movups  xmmword ptr [rsp+68h+FileTime1.dwLowDateTime], xmm0
0x18000ebd8  cmp     [rcx+260h], eax
0x18000ebde  jz      short loc_18000EBEA
0x18000ebe0  mov     ebx, 8000FFFFh
0x18000ebe5  jmp     loc_18000ED0C
0x18000ebea  mov     dword ptr [rcx+260h], 1
0x18000ebf4  cmp     [rcx+224h], eax
0x18000ebfa  jz      short loc_18000EC0B
0x18000ebfc  call    ?AttemptNetConnection@@YAJXZ; AttemptNetConnection(void)
0x18000ec01  mov     ebx, eax
0x18000ec03  test    eax, eax
0x18000ec05  js      loc_18000ED0C
0x18000ec0b  lea     rcx, [rdi+140h]
0x18000ec12  xor     esi, esi
0x18000ec14  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ec1a  xor     edx, edx; bWatchSubtree
0x18000ec1c  lea     r8d, [rsi+11h]; dwNotifyFilter
0x18000ec20  mov     rcx, rax; lpPathName
0x18000ec23  call    cs:__imp_FindFirstChangeNotificationW
0x18000ec29  mov     [rdi+240h], rax
0x18000ec30  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ec34  jz      loc_18000ECD6
0x18000ec3a  lea     rcx, [rdi+108h]
0x18000ec41  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000ec47  lea     r8, [rsp+68h+FileInformation]; lpFileInformation
0x18000ec4c  xor     edx, edx; fInfoLevelId
0x18000ec4e  mov     rcx, rax; lpFileName
0x18000ec51  call    cs:__imp_GetFileAttributesExW
0x18000ec57  test    eax, eax
0x18000ec59  jz      short loc_18000ECD6
0x18000ec5b  mov     rax, qword ptr [rsp+68h+FileTime1.dwHighDateTime]
0x18000ec60  lea     rcx, CriticalSection; lpCriticalSection
0x18000ec67  mov     [rdi+250h], rax
0x18000ec6e  call    cs:__imp_EnterCriticalSection
0x18000ec74  lea     rdx, FileTime2; lpFileTime2
0x18000ec7b  lea     rcx, [rsp+68h+FileTime1.dwHighDateTime]; lpFileTime1
0x18000ec80  call    cs:__imp_CompareFileTime
0x18000ec86  lea     rcx, CriticalSection; lpCriticalSection
0x18000ec8d  call    cs:__imp_LeaveCriticalSection
0x18000ec93  mov     rax, [rdi]
0x18000ec96  mov     rcx, rdi
0x18000ec99  mov     rax, [rax]
0x18000ec9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eca1  mov     rdx, [rdi+240h]; hObject
0x18000eca8  lea     rcx, [rdi+248h]; phNewWaitObject
0x18000ecaf  mov     r9, rdi; Context
0x18000ecb2  mov     [rsp+68h+dwFlags], 94h; dwFlags
0x18000ecba  lea     r8, ?sChangeCallback@CFileListener@@CAXPEAXE@Z; Callback
0x18000ecc1  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000ecc9  call    cs:__imp_RegisterWaitForSingleObject
0x18000eccf  test    eax, eax
0x18000ecd1  jnz     short loc_18000ED1A
0x18000ecd3  lea     esi, [rax+1]
0x18000ecd6  call    cs:__imp_GetLastError
0x18000ecdc  mov     ebx, eax
0x18000ecde  test    eax, eax
0x18000ece0  jle     short loc_18000ECEB
0x18000ece2  movzx   ebx, ax
0x18000ece5  or      ebx, 80070000h
0x18000eceb  test    ebx, ebx
0x18000eced  jns     short loc_18000ED1C
0x18000ecef  test    esi, esi
0x18000ecf1  jz      short loc_18000ED0C
0x18000ecf3  cmp     qword ptr [rdi+248h], 0
0x18000ecfb  jnz     short loc_18000ED0C
0x18000ecfd  mov     rax, [rdi]
0x18000ed00  mov     rcx, rdi
0x18000ed03  mov     rax, [rax+8]
0x18000ed07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed0c  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x18000ed10  mov     rcx, rdi; this
0x18000ed13  call    ?StopListening@CFileListener@@AEAAJPEAX@Z; CFileListener::StopListening(void *)
0x18000ed18  jmp     short loc_18000ED1C
0x18000ed1a  xor     ebx, ebx
0x18000ed1c  mov     eax, ebx
0x18000ed1e  mov     rcx, [rsp+68h+var_10]
0x18000ed23  xor     rcx, rsp; StackCookie
0x18000ed26  call    __security_check_cookie
0x18000ed2b  lea     r11, [rsp+68h+var_8]
0x18000ed30  mov     rbx, [r11+18h]
0x18000ed34  mov     rsi, [r11+20h]
0x18000ed38  mov     rsp, r11
0x18000ed3b  pop     rdi
0x18000ed3c  retn
```
