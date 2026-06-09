# FILE_LISTENER::Initialize(ushort const *,IFILE_LISTENER_CALLBACK *,int)

- ea: `0x1800042f0`
- end: `0x18000453d`
- name: `?Initialize@FILE_LISTENER@@QEAAJPEBGPEAVIFILE_LISTENER_CALLBACK@@H@Z`
- size: `589`
- prototype: `__int64 __fastcall(FILE_LISTENER *__hidden this, const unsigned __int16 *, struct IFILE_LISTENER_CALLBACK *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007b00`

## callees

- `0x1800042f0`
- `0x1800046c0`
- `0x18000ee10`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800043ec`
- `msvcrt!wcsrchr` at `0x1800043ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000442a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000447e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800044a1`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800044a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000446e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000446e`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180004420`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180004420`
- `iisutil!IsPathUnc` at `0x180004361`
- `iisutil!IsPathUnc` at `0x180004361`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800044fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000450e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800044fa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000450e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043d2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800043d2`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004323`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180004323`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004404`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004404`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800044ca`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800044ca`

## pseudocode

```c
__int64 __fastcall FILE_LISTENER::Initialize(
        FILE_LISTENER *this,
        const unsigned __int16 *a2,
        struct IFILE_LISTENER_CALLBACK *a3)
{
  unsigned __int64 v6; // rax
  _DWORD *v7; // rbp
  signed int v8; // ebx
  _QWORD *v9; // rcx
  wchar_t *v10; // rax
  int v11; // edi
  signed int LastError; // eax
  HANDLE FileW; // rax
  signed int v14; // eax
  PVOID OldValue; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v17[32]; // [rsp+48h] [rbp-70h] BYREF
  wchar_t *Str; // [rsp+68h] [rbp-50h]

  STRU::STRU((STRU *)v17);
  OldValue = 0;
  if ( !a2 )
    goto LABEL_32;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0x104 )
  {
LABEL_32:
    v8 = -2147024809;
    goto LABEL_33;
  }
  v7 = (_DWORD *)((char *)this + 188);
  v8 = IsPathUnc(a2, (int *)this + 47);
  if ( v8 < 0 )
    goto LABEL_33;
  if ( *v7 == 1 )
  {
    v9 = (_QWORD *)qword_180017F80;
    if ( *(struct _LIST_ENTRY **)qword_180017F80 != &FILE_LISTENER::sm_UncListenersList )
      __fastfail(3u);
    *((_QWORD *)this + 24) = &FILE_LISTENER::sm_UncListenersList;
    *((_QWORD *)this + 25) = v9;
    *v9 = (char *)this + 192;
    qword_180017F80 = (__int64)this + 192;
  }
  v8 = STRU::Copy((FILE_LISTENER *)((char *)this + 16), a2);
  if ( v8 < 0 )
    goto LABEL_33;
  if ( *v7 )
    goto LABEL_31;
  v8 = STRU::Copy((STRU *)v17, a2);
  if ( v8 >= 0 )
  {
    v10 = wcsrchr(Str, 0x5Cu);
    if ( v10 )
    {
      *v10 = 0;
      STRU::SyncWithBuffer((STRU *)v17);
      v11 = 0;
      if ( FILE_LISTENER::sm_fIsWow64 == 1 )
      {
        if ( Wow64DisableWow64FsRedirection(&OldValue) )
        {
          v11 = 1;
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_33;
        }
      }
      FileW = CreateFileW(Str, 1u, 7u, 0, 3u, 0x42000000u, 0);
      *((_QWORD *)this + 10) = FileW;
      if ( FileW == (HANDLE)-1LL || !CreateIoCompletionPort(FileW, FILE_LISTENER::sm_hCompletionPort, 0, 0) )
      {
        v14 = GetLastError();
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
        goto LABEL_29;
      }
      if ( v11 == 1 )
      {
        FILE_LISTENER::RestoreWow64Redirection(OldValue);
        v11 = 0;
      }
      if ( !BUFFER::Resize((FILE_LISTENER *)((char *)this + 136), 0x800u) )
      {
        v8 = -2147024888;
LABEL_29:
        if ( v11 == 1 )
          FILE_LISTENER::RestoreWow64Redirection(OldValue);
        goto LABEL_33;
      }
LABEL_31:
      *((_QWORD *)this + 11) = a3;
      *((_DWORD *)this + 32) = 0;
      STRU::~STRU((STRU *)v17);
      return 0;
    }
    goto LABEL_32;
  }
LABEL_33:
  STRU::~STRU((STRU *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800042f0  mov     [rsp+arg_10], rbx
0x1800042f5  push    rbp
0x1800042f6  push    rsi
0x1800042f7  push    rdi
0x1800042f8  push    r14
0x1800042fa  push    r15
0x1800042fc  sub     rsp, 90h
0x180004303  mov     rax, cs:__security_cookie
0x18000430a  xor     rax, rsp
0x18000430d  mov     [rsp+0B8h+var_38], rax
0x180004315  mov     rsi, rcx
0x180004318  mov     r14, r8
0x18000431b  lea     rcx, [rsp+0B8h+var_70]
0x180004320  mov     rdi, rdx
0x180004323  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180004329  xor     r15d, r15d
0x18000432c  mov     [rsp+0B8h+OldValue], r15
0x180004331  test    rdi, rdi
0x180004334  jz      loc_180004504
0x18000433a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000433e  inc     rax
0x180004341  cmp     [rdi+rax*2], r15w
0x180004346  jnz     short loc_18000433E
0x180004348  cmp     rax, 104h
0x18000434e  ja      loc_180004504
0x180004354  lea     rbp, [rsi+0BCh]
0x18000435b  mov     rcx, rdi
0x18000435e  mov     rdx, rbp
0x180004361  call    cs:__imp_?IsPathUnc@@YAJPEBGPEAH@Z; IsPathUnc(ushort const *,int *)
0x180004367  mov     ebx, eax
0x180004369  test    eax, eax
0x18000436b  js      loc_180004509
0x180004371  cmp     dword ptr [rbp+0], 1
0x180004375  jnz     short loc_1800043A9
0x180004377  mov     rcx, cs:qword_180017F80
0x18000437e  lea     rdx, ?sm_UncListenersList@FILE_LISTENER@@0U_LIST_ENTRY@@A; _LIST_ENTRY FILE_LISTENER::sm_UncListenersList
0x180004385  cmp     [rcx], rdx
0x180004388  jz      short loc_180004391
0x18000438a  mov     ecx, 3
0x18000438f  int     29h; Win8: RtlFailFast(ecx)
0x180004391  lea     rax, [rsi+0C0h]
0x180004398  mov     [rax], rdx
0x18000439b  mov     [rax+8], rcx
0x18000439f  mov     [rcx], rax
0x1800043a2  mov     cs:qword_180017F80, rax
0x1800043a9  lea     rcx, [rsi+10h]
0x1800043ad  mov     rdx, rdi
0x1800043b0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800043b6  mov     ebx, eax
0x1800043b8  test    eax, eax
0x1800043ba  js      loc_180004509
0x1800043c0  cmp     [rbp+0], r15d
0x1800043c4  jnz     loc_1800044EA
0x1800043ca  mov     rdx, rdi
0x1800043cd  lea     rcx, [rsp+0B8h+var_70]
0x1800043d2  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800043d8  mov     ebx, eax
0x1800043da  test    eax, eax
0x1800043dc  js      loc_180004509
0x1800043e2  mov     rcx, [rsp+0B8h+Str]; Str
0x1800043e7  mov     edx, 5Ch ; '\'; Ch
0x1800043ec  call    cs:__imp_wcsrchr
0x1800043f2  test    rax, rax
0x1800043f5  jz      loc_180004504
0x1800043fb  lea     rcx, [rsp+0B8h+var_70]
0x180004400  mov     [rax], r15w
0x180004404  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000440a  cmp     cs:?sm_fIsWow64@FILE_LISTENER@@0HA, 1; int FILE_LISTENER::sm_fIsWow64
0x180004411  mov     edi, r15d
0x180004414  mov     ebp, 80070000h
0x180004419  jnz     short loc_180004449
0x18000441b  lea     rcx, [rsp+0B8h+OldValue]; OldValue
0x180004420  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180004426  test    eax, eax
0x180004428  jnz     short loc_180004444
0x18000442a  call    cs:__imp_GetLastError
0x180004430  mov     ebx, eax
0x180004432  test    eax, eax
0x180004434  jle     short loc_18000443B
0x180004436  movzx   ebx, ax
0x180004439  or      ebx, ebp
0x18000443b  test    ebx, ebx
0x18000443d  jns     short loc_180004449
0x18000443f  jmp     loc_180004509
0x180004444  mov     edi, 1
0x180004449  mov     rcx, [rsp+0B8h+Str]; lpFileName
0x18000444e  xor     r9d, r9d; lpSecurityAttributes
0x180004451  mov     [rsp+0B8h+hTemplateFile], r15; hTemplateFile
0x180004456  mov     [rsp+0B8h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x18000445e  mov     [rsp+0B8h+dwCreationDisposition], 3; dwCreationDisposition
0x180004466  lea     edx, [r9+1]; dwDesiredAccess
0x18000446a  lea     r8d, [r9+7]; dwShareMode
0x18000446e  call    cs:__imp_CreateFileW
0x180004474  mov     [rsi+50h], rax
0x180004478  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000447c  jnz     short loc_180004491
0x18000447e  call    cs:__imp_GetLastError
0x180004484  mov     ebx, eax
0x180004486  test    eax, eax
0x180004488  jle     short loc_1800044D9
0x18000448a  movzx   ebx, ax
0x18000448d  or      ebx, ebp
0x18000448f  jmp     short loc_1800044D9
0x180004491  mov     rdx, cs:?sm_hCompletionPort@FILE_LISTENER@@0PEAXEA; ExistingCompletionPort
0x180004498  xor     r9d, r9d; NumberOfConcurrentThreads
0x18000449b  xor     r8d, r8d; CompletionKey
0x18000449e  mov     rcx, rax; FileHandle
0x1800044a1  call    cs:__imp_CreateIoCompletionPort
0x1800044a7  test    rax, rax
0x1800044aa  jz      short loc_18000447E
0x1800044ac  cmp     edi, 1
0x1800044af  jnz     short loc_1800044BE
0x1800044b1  mov     rcx, [rsp+0B8h+OldValue]; void *
0x1800044b6  call    ?RestoreWow64Redirection@FILE_LISTENER@@SAJPEAX@Z; FILE_LISTENER::RestoreWow64Redirection(void *)
0x1800044bb  mov     edi, r15d
0x1800044be  lea     rcx, [rsi+88h]
0x1800044c5  mov     edx, 800h
0x1800044ca  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800044d0  test    al, al
0x1800044d2  jnz     short loc_1800044EA
0x1800044d4  mov     ebx, 80070008h
0x1800044d9  cmp     edi, 1
0x1800044dc  jnz     short loc_180004509
0x1800044de  mov     rcx, [rsp+0B8h+OldValue]; void *
0x1800044e3  call    ?RestoreWow64Redirection@FILE_LISTENER@@SAJPEAX@Z; FILE_LISTENER::RestoreWow64Redirection(void *)
0x1800044e8  jmp     short loc_180004509
0x1800044ea  lea     rcx, [rsp+0B8h+var_70]
0x1800044ef  mov     [rsi+58h], r14
0x1800044f3  mov     [rsi+80h], r15d
0x1800044fa  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004500  xor     eax, eax
0x180004502  jmp     short loc_180004516
0x180004504  mov     ebx, 80070057h
0x180004509  lea     rcx, [rsp+0B8h+var_70]
0x18000450e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004514  mov     eax, ebx
0x180004516  mov     rcx, [rsp+0B8h+var_38]
0x18000451e  xor     rcx, rsp; StackCookie
0x180004521  call    __security_check_cookie
0x180004526  mov     rbx, [rsp+0B8h+arg_10]
0x18000452e  add     rsp, 90h
0x180004535  pop     r15
0x180004537  pop     r14
0x180004539  pop     rdi
0x18000453a  pop     rsi
0x18000453b  pop     rbp
0x18000453c  retn
```
