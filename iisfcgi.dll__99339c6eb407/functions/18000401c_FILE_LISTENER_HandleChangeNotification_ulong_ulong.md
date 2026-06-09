# FILE_LISTENER::HandleChangeNotification(ulong,ulong)

- ea: `0x18000401c`
- end: `0x1800042e7`
- name: `?HandleChangeNotification@FILE_LISTENER@@AEAAXKK@Z`
- size: `715`
- prototype: `void __fastcall(FILE_LISTENER *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003eb0`

## callees

- `0x180001048`
- `0x180003e1c`
- `0x18000401c`
- `0x180004544`
- `0x1800045e0`
- `0x1800046c0`
- `0x18000ee10`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004144`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004257`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004257`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000418a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000418a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800041d3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800041d3`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18000413a`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18000413a`

## pseudocode

```c
void __fastcall FILE_LISTENER::HandleChangeNotification(FILE_LISTENER *this, int a2, int a3)
{
  int v4; // edi
  int v5; // r13d
  int v6; // r12d
  __int64 v7; // rbx
  __int64 v8; // r14
  int v9; // eax
  void *v11; // rcx
  signed int LastError; // eax
  signed int v13; // eax
  void (__fastcall *v15)(__int64, _QWORD); // [rsp+20h] [rbp-50h]
  HANDLE hObject; // [rsp+28h] [rbp-48h] BYREF
  PVOID OldValue; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-30h] BYREF
  FILETIME FileTime2[2]; // [rsp+50h] [rbp-20h] BYREF
  int v21; // [rsp+60h] [rbp-10h]

  hObject = (HANDLE)-1LL;
  v4 = 0;
  v21 = 0;
  v5 = 0;
  OldValue = 0;
  v6 = 0;
  v18 = 0;
  v7 = 0;
  v8 = 0;
  v9 = a3;
  FileInformation = 0;
  *(_OWORD *)&FileTime2[0].dwLowDateTime = 0;
  if ( !*((_DWORD *)this + 47) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 1, 0xFFFFFFFF) == 1 )
    {
      FILE_LISTENER::~FILE_LISTENER(this);
      operator delete(this);
      v9 = a3;
    }
    else
    {
      v9 = a3;
    }
  }
  if ( *((_DWORD *)this + 2) )
    goto LABEL_40;
  if ( *((_DWORD *)this + 46) == 1 )
    return;
  if ( !v9 )
  {
    if ( a2 == 5 )
    {
      _InterlockedExchange((volatile __int32 *)this + 2, 1);
      v11 = (void *)*((_QWORD *)this + 10);
      if ( v11 != (void *)-1LL )
      {
        CloseHandle(v11);
        *((_QWORD *)this + 10) = -1;
      }
      goto LABEL_11;
    }
    if ( a2 > 0 )
    {
LABEL_11:
      v4 = (unsigned __int16)a2 | 0x80070000;
      goto LABEL_39;
    }
    v4 = a2;
LABEL_39:
    if ( v4 >= 0 )
      goto LABEL_40;
    goto LABEL_41;
  }
  v7 = *((_QWORD *)this + 11);
  if ( *((_DWORD *)this + 32) == 1 )
  {
    v6 = 1;
    v8 = *((_QWORD *)this + 11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v8);
  }
  if ( FILE_LISTENER::sm_fIsWow64 == 1 )
  {
    if ( Wow64DisableWow64FsRedirection(&OldValue) )
    {
      v5 = 1;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
      {
        if ( v6 == 1 )
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, (unsigned int)v4);
        goto LABEL_41;
      }
    }
  }
  if ( !GetFileAttributesExW(*((LPCWSTR *)this + 6), GetFileExInfoStandard, &FileInformation) )
  {
    if ( v6 == 1 )
    {
      v15 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 40LL);
      v13 = GetLastError();
      if ( v13 > 0 )
        v13 = (unsigned __int16)v13 | 0x80070000;
      v15(v8, (unsigned int)v13);
    }
    *((_QWORD *)this + 9) = 0;
    goto LABEL_40;
  }
  if ( !CompareFileTime((const FILETIME *)this + 9, (const FILETIME *)&FileTime2[0].dwHighDateTime) )
  {
LABEL_40:
    FILE_LISTENER::ListenForChanges(this);
    goto LABEL_41;
  }
  v4 = FILE_LISTENER::OpenFile((LPCWSTR *)this, &hObject);
  if ( v4 < 0 )
  {
    if ( v6 == 1 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 40LL))(v8, (unsigned int)v4);
    goto LABEL_41;
  }
  if ( v6 != 1 || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, &v18), v4 >= 0) )
  {
    if ( !(**(unsigned int (__fastcall ***)(__int64))v7)(v7) )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
    goto LABEL_39;
  }
LABEL_41:
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v5 )
    FILE_LISTENER::RestoreWow64Redirection(OldValue);
  if ( v6 == 1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 24LL))(v8);
  if ( v4 >= 0 && v7 && (**(unsigned int (__fastcall ***)(__int64))v7)(v7) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
  if ( v6 == 1 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 48LL))(v8, v18);
}

```

## disassembly

```asm
0x18000401c  mov     [rsp-38h+arg_10], rbx
0x180004021  push    rbp
0x180004022  push    rsi
0x180004023  push    rdi
0x180004024  push    r12
0x180004026  push    r13
0x180004028  push    r14
0x18000402a  push    r15
0x18000402c  mov     rbp, rsp
0x18000402f  sub     rsp, 70h
0x180004033  mov     rax, cs:__security_cookie
0x18000403a  xor     rax, rsp
0x18000403d  mov     [rbp+var_8], rax
0x180004041  mov     rsi, rcx
0x180004044  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x18000404c  xor     ecx, ecx
0x18000404e  xorps   xmm0, xmm0
0x180004051  xor     edi, edi
0x180004053  mov     [rbp+var_10], ecx
0x180004056  xor     r13d, r13d
0x180004059  mov     [rbp+OldValue], rcx
0x18000405d  xor     r12d, r12d
0x180004060  mov     [rbp+var_38], rcx
0x180004064  xor     ebx, ebx
0x180004066  xor     r14d, r14d
0x180004069  mov     eax, r8d
0x18000406c  mov     r15d, edx
0x18000406f  mov     dword ptr [rbp+var_50], eax
0x180004072  movups  [rbp+FileInformation], xmm0
0x180004076  movups  xmmword ptr [rbp+FileTime2.dwLowDateTime], xmm0
0x18000407a  cmp     [rsi+0BCh], ecx
0x180004080  jnz     short loc_1800040A7
0x180004082  or      eax, 0FFFFFFFFh
0x180004085  lock xadd [rsi+4], eax
0x18000408a  cmp     eax, 1
0x18000408d  jnz     short loc_1800040A4
0x18000408f  mov     rcx, rsi; this
0x180004092  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x180004097  mov     rcx, rsi; Block
0x18000409a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000409f  mov     eax, dword ptr [rbp+var_50]
0x1800040a2  jmp     short loc_1800040A7
0x1800040a4  mov     eax, r8d
0x1800040a7  cmp     [rsi+8], ebx
0x1800040aa  jnz     loc_180004245
0x1800040b0  cmp     dword ptr [rsi+0B8h], 1
0x1800040b7  jz      loc_1800042C3
0x1800040bd  test    eax, eax
0x1800040bf  jnz     short loc_180004102
0x1800040c1  cmp     r15d, 5
0x1800040c5  jnz     short loc_1800040F5
0x1800040c7  lea     eax, [r15-4]
0x1800040cb  xchg    eax, [rsi+8]
0x1800040ce  mov     rcx, [rsi+50h]; hObject
0x1800040d2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800040d6  jz      short loc_1800040E6
0x1800040d8  call    cs:__imp_CloseHandle
0x1800040de  mov     qword ptr [rsi+50h], 0FFFFFFFFFFFFFFFFh
0x1800040e6  movzx   edi, r15w
0x1800040ea  or      edi, 80070000h
0x1800040f0  jmp     loc_180004241
0x1800040f5  test    r15d, r15d
0x1800040f8  jg      short loc_1800040E6
0x1800040fa  mov     edi, r15d
0x1800040fd  jmp     loc_180004241
0x180004102  cmp     dword ptr [rsi+80h], 1
0x180004109  mov     rbx, [rsi+58h]
0x18000410d  jnz     short loc_180004127
0x18000410f  mov     rax, [rbx]
0x180004112  mov     rcx, rbx
0x180004115  mov     r12d, 1
0x18000411b  mov     r14, rbx
0x18000411e  mov     rax, [rax+10h]
0x180004122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004127  cmp     cs:?sm_fIsWow64@FILE_LISTENER@@0HA, 1; int FILE_LISTENER::sm_fIsWow64
0x18000412e  mov     r15d, 80070000h
0x180004134  jnz     short loc_180004180
0x180004136  lea     rcx, [rbp+OldValue]; OldValue
0x18000413a  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180004140  test    eax, eax
0x180004142  jnz     short loc_18000417A
0x180004144  call    cs:__imp_GetLastError
0x18000414a  mov     edi, eax
0x18000414c  test    eax, eax
0x18000414e  jle     short loc_180004156
0x180004150  movzx   edi, ax
0x180004153  or      edi, r15d
0x180004156  test    edi, edi
0x180004158  jns     short loc_180004180
0x18000415a  cmp     r12d, 1
0x18000415e  jnz     loc_18000424D
0x180004164  mov     rax, [r14]
0x180004167  mov     rax, [rax+28h]
0x18000416b  mov     rcx, r14
0x18000416e  mov     edx, edi
0x180004170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004175  jmp     loc_18000424D
0x18000417a  mov     r13d, 1
0x180004180  mov     rcx, [rsi+30h]; lpFileName
0x180004184  lea     r8, [rbp+FileInformation]; lpFileInformation
0x180004188  xor     edx, edx; fInfoLevelId
0x18000418a  call    cs:__imp_GetFileAttributesExW
0x180004190  test    eax, eax
0x180004192  jnz     short loc_1800041CB
0x180004194  cmp     r12d, 1
0x180004198  jnz     short loc_1800041C3
0x18000419a  mov     rax, [r14]
0x18000419d  mov     rax, [rax+28h]
0x1800041a1  mov     [rbp+var_50], rax
0x1800041a5  call    cs:__imp_GetLastError
0x1800041ab  test    eax, eax
0x1800041ad  jle     short loc_1800041B5
0x1800041af  movzx   eax, ax
0x1800041b2  or      eax, r15d
0x1800041b5  mov     edx, eax
0x1800041b7  mov     rcx, r14
0x1800041ba  mov     rax, [rbp+var_50]
0x1800041be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c3  xor     eax, eax
0x1800041c5  mov     [rsi+48h], rax
0x1800041c9  jmp     short loc_180004245
0x1800041cb  lea     rcx, [rsi+48h]; lpFileTime1
0x1800041cf  lea     rdx, [rbp+FileTime2.dwHighDateTime]; lpFileTime2
0x1800041d3  call    cs:__imp_CompareFileTime
0x1800041d9  test    eax, eax
0x1800041db  jz      short loc_180004245
0x1800041dd  lea     rdx, [rbp+hObject]; void **
0x1800041e1  mov     rcx, rsi; this
0x1800041e4  call    ?OpenFile@FILE_LISTENER@@QEAAJPEAPEAX@Z; FILE_LISTENER::OpenFile(void * *)
0x1800041e9  mov     edi, eax
0x1800041eb  test    eax, eax
0x1800041ed  jns     short loc_180004201
0x1800041ef  cmp     r12d, 1
0x1800041f3  jnz     short loc_18000424D
0x1800041f5  mov     rcx, [r14]
0x1800041f8  mov     rax, [rcx+28h]
0x1800041fc  jmp     loc_18000416B
0x180004201  cmp     r12d, 1
0x180004205  jnz     short loc_180004220
0x180004207  mov     rax, [r14]
0x18000420a  lea     rdx, [rbp+var_38]
0x18000420e  mov     rcx, r14
0x180004211  mov     rax, [rax+20h]
0x180004215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421a  mov     edi, eax
0x18000421c  test    eax, eax
0x18000421e  js      short loc_18000424D
0x180004220  mov     rax, [rbx]
0x180004223  mov     rcx, rbx
0x180004226  mov     rax, [rax]
0x180004229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422e  test    eax, eax
0x180004230  jnz     short loc_180004241
0x180004232  mov     rax, [rbx]
0x180004235  mov     rcx, rbx
0x180004238  mov     rax, [rax+8]
0x18000423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004241  test    edi, edi
0x180004243  js      short loc_18000424D
0x180004245  mov     rcx, rsi; this
0x180004248  call    ?ListenForChanges@FILE_LISTENER@@QEAAXXZ; FILE_LISTENER::ListenForChanges(void)
0x18000424d  mov     rcx, [rbp+hObject]; hObject
0x180004251  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004255  jz      short loc_18000425D
0x180004257  call    cs:__imp_CloseHandle
0x18000425d  test    r13d, r13d
0x180004260  jz      short loc_18000426B
0x180004262  mov     rcx, [rbp+OldValue]; void *
0x180004266  call    ?RestoreWow64Redirection@FILE_LISTENER@@SAJPEAX@Z; FILE_LISTENER::RestoreWow64Redirection(void *)
0x18000426b  cmp     r12d, 1
0x18000426f  jnz     short loc_180004280
0x180004271  mov     rax, [r14]
0x180004274  mov     rcx, r14
0x180004277  mov     rax, [rax+18h]
0x18000427b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004280  test    edi, edi
0x180004282  js      short loc_1800042AA
0x180004284  test    rbx, rbx
0x180004287  jz      short loc_1800042AA
0x180004289  mov     rax, [rbx]
0x18000428c  mov     rcx, rbx
0x18000428f  mov     rax, [rax]
0x180004292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004297  test    eax, eax
0x180004299  jz      short loc_1800042AA
0x18000429b  mov     rax, [rbx]
0x18000429e  mov     rcx, rbx
0x1800042a1  mov     rax, [rax+8]
0x1800042a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042aa  cmp     r12d, 1
0x1800042ae  jnz     short loc_1800042C3
0x1800042b0  mov     rax, [r14]
0x1800042b3  mov     rcx, r14
0x1800042b6  mov     rdx, [rbp+var_38]
0x1800042ba  mov     rax, [rax+30h]
0x1800042be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c3  mov     rcx, [rbp+var_8]
0x1800042c7  xor     rcx, rsp; StackCookie
0x1800042ca  call    __security_check_cookie
0x1800042cf  mov     rbx, [rsp+70h+arg_10]
0x1800042d7  add     rsp, 70h
0x1800042db  pop     r15
0x1800042dd  pop     r14
0x1800042df  pop     r13
0x1800042e1  pop     r12
0x1800042e3  pop     rdi
0x1800042e4  pop     rsi
0x1800042e5  pop     rbp
0x1800042e6  retn
```
