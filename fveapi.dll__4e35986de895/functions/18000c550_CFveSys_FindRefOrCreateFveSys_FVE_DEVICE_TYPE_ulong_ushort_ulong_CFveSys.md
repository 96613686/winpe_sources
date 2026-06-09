# CFveSys::FindRefOrCreateFveSys(_FVE_DEVICE_TYPE,ulong,ushort *,ulong,CFveSys * *)

- ea: `0x18000c550`
- end: `0x18000c7fe`
- name: `?FindRefOrCreateFveSys@CFveSys@@CAJW4_FVE_DEVICE_TYPE@@KPEAGKPEAPEAV1@@Z`
- size: `686`
- prototype: `static int __high(enum _FVE_DEVICE_TYPE, unsigned int, unsigned __int16 *, unsigned int, struct CFveSys **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000c4d0`

## callees

- `0x180005410`
- `0x180009d00`
- `0x18000aae0`
- `0x18000ba30`
- `0x18000c550`
- `0x18000c804`
- `0x18000c848`
- `0x18005e158`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c5d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c71b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011fb22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c71b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18011fb22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c7d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18011fb3f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c66e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000c66e`

## pseudocode

```c
__int64 __fastcall CFveSys::FindRefOrCreateFveSys(
        unsigned int a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        int a4,
        __int64 a5)
{
  int LastHresultError; // ebx
  __int64 FileW; // rsi
  int v9; // r14d
  struct CFveSys **i; // rcx
  struct CFveSys *v11; // rax
  void *v12; // rax
  struct CFveSys *v13; // rcx
  void *lpMem; // [rsp+50h] [rbp-278h] BYREF
  __int64 v18; // [rsp+58h] [rbp-270h]
  void *v19; // [rsp+60h] [rbp-268h]
  WCHAR FileName[264]; // [rsp+70h] [rbp-258h] BYREF

  LastHresultError = 0;
  v19 = 0;
  lpMem = 0;
  FileW = -1;
  v18 = -1;
  memset_0(FileName, 0, 0x208u);
  v9 = 0;
  if ( a5 )
  {
    CFveSys::FveSysInit();
    EnterCriticalSection(&CFveSys::_ListLock);
    v9 = 1;
    for ( i = &CFveSys::_ClassList; ; i = (struct CFveSys **)((char *)v11 + 72) )
    {
      v11 = *i;
      if ( !*i )
        goto LABEL_4;
      if ( *((_DWORD *)v11 + 24) == a1 && *((_DWORD *)v11 + 26) == a2 && *((_DWORD *)v11 + 25) == a4 )
        break;
    }
    if ( v11 )
    {
      _InterlockedAdd((volatile signed __int32 *)v11 + 16, 1u);
      *(_QWORD *)a5 = *i;
LABEL_13:
      LeaveCriticalSection(&CFveSys::_ListLock);
      v9 = 0;
      goto LABEL_23;
    }
LABEL_4:
    LastHresultError = CFveApiBase::CopyString(a3, (unsigned __int16 **)&lpMem);
    if ( LastHresultError >= 0 )
    {
      LastHresultError = StringCchPrintfW(FileName, 0x104u, L"%s\\SYS", a3);
      if ( LastHresultError >= 0 )
      {
        FileW = (__int64)CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0, 0);
        v18 = FileW;
        if ( FileW == -1 )
        {
          LastHresultError = GetLastHresultError();
        }
        else
        {
          v12 = operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v12 )
            v12 = (void *)CFveSys::CFveSys(v12, FileW, a1, a2, lpMem, a4);
          v19 = v12;
          if ( v12 )
          {
            *(_QWORD *)a5 = v12;
            v19 = 0;
            FileW = -1;
            v18 = -1;
            lpMem = 0;
            v13 = CFveSys::_ClassList;
            if ( CFveSys::_ClassList )
            {
              *((_QWORD *)CFveSys::_ClassList + 10) = v12;
              v13 = CFveSys::_ClassList;
            }
            *(_QWORD *)(*(_QWORD *)a5 + 72LL) = v13;
            CFveSys::_ClassList = *(struct CFveSys **)a5;
            goto LABEL_13;
          }
          LastHresultError = -2147024882;
        }
      }
    }
  }
  else
  {
    LastHresultError = -2147024809;
  }
LABEL_23:
  if ( v9 )
    LeaveCriticalSection(&CFveSys::_ListLock);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( lpMem )
    CFveApiBase::FastFree(lpMem);
  return (unsigned int)LastHresultError;
}

```

## disassembly

```asm
0x18000c550  push    rbx
0x18000c552  push    rsi
0x18000c553  push    rdi
0x18000c554  push    r12
0x18000c556  push    r13
0x18000c558  push    r14
0x18000c55a  push    r15
0x18000c55c  sub     rsp, 290h
0x18000c563  mov     rax, cs:__security_cookie
0x18000c56a  xor     rax, rsp
0x18000c56d  mov     [rsp+2C8h+var_48], rax
0x18000c575  mov     [rsp+2C8h+var_280], r9d
0x18000c57a  mov     r12, r8
0x18000c57d  mov     [rsp+2C8h+var_27C], edx
0x18000c581  mov     r13d, ecx
0x18000c584  mov     r15, [rsp+2C8h+arg_20]
0x18000c58c  xor     ebx, ebx
0x18000c58e  xor     edi, edi
0x18000c590  mov     [rsp+2C8h+var_268], rdi
0x18000c595  mov     [rsp+2C8h+lpMem], rbx
0x18000c59a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c59e  mov     [rsp+2C8h+var_270], rsi
0x18000c5a3  xor     edx, edx; Val
0x18000c5a5  mov     r8d, 208h; Size
0x18000c5ab  lea     rcx, [rsp+2C8h+FileName]; void *
0x18000c5b0  call    memset_0
0x18000c5b5  xor     r14d, r14d
0x18000c5b8  mov     [rsp+2C8h+var_284], r14d
0x18000c5bd  test    r15, r15
0x18000c5c0  jz      loc_18000C779
0x18000c5c6  call    ?FveSysInit@CFveSys@@SAXXZ; CFveSys::FveSysInit(void)
0x18000c5cb  lea     rcx, ?_ListLock@CFveSys@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c5d2  call    cs:__imp_EnterCriticalSection
0x18000c5d9  nop     dword ptr [rax+rax+00h]
0x18000c5de  lea     r14d, [rbx+1]
0x18000c5e2  mov     [rsp+2C8h+var_284], r14d
0x18000c5e7  lea     rcx, ?_ClassList@CFveSys@@0PEAV1@EA; CFveSys * CFveSys::_ClassList
0x18000c5ee  mov     edx, [rsp+2C8h+var_27C]
0x18000c5f2  mov     r8d, [rsp+2C8h+var_280]
0x18000c5f7  mov     rax, [rcx]
0x18000c5fa  test    rax, rax
0x18000c5fd  jnz     loc_18000C731
0x18000c603  lea     rdx, [rsp+2C8h+lpMem]; unsigned __int16 **
0x18000c608  mov     rcx, r12; unsigned __int16 *
0x18000c60b  call    ?CopyString@CFveApiBase@@SAJPEBGPEAPEAG@Z; CFveApiBase::CopyString(ushort const *,ushort * *)
0x18000c610  mov     ebx, eax
0x18000c612  mov     [rsp+2C8h+var_288], eax
0x18000c616  test    eax, eax
0x18000c618  js      loc_18000C780
0x18000c61e  mov     r9, r12
0x18000c621  lea     r8, aSSys; "%s\\SYS"
0x18000c628  mov     edx, 104h; unsigned __int64
0x18000c62d  lea     rcx, [rsp+2C8h+FileName]; unsigned __int16 *
0x18000c632  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c637  mov     ebx, eax
0x18000c639  mov     [rsp+2C8h+var_288], eax
0x18000c63d  test    eax, eax
0x18000c63f  js      loc_18000C780
0x18000c645  mov     [rsp+2C8h+hTemplateFile], 0; hTemplateFile
0x18000c64e  mov     [rsp+2C8h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000c656  mov     r8d, 3; dwShareMode
0x18000c65c  mov     [rsp+2C8h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000c661  xor     r9d, r9d; lpSecurityAttributes
0x18000c664  mov     edx, 0C0000000h; dwDesiredAccess
0x18000c669  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x18000c66e  call    cs:__imp_CreateFileW
0x18000c675  nop     dword ptr [rax+rax+00h]
0x18000c67a  mov     rsi, rax
0x18000c67d  mov     [rsp+2C8h+var_270], rax
0x18000c682  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c686  jz      loc_18000C76C
0x18000c68c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c693  mov     ecx, 78h ; 'x'; unsigned __int64
0x18000c698  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c69d  test    rax, rax
0x18000c6a0  jz      short loc_18000C6C7
0x18000c6a2  mov     ecx, [rsp+2C8h+var_280]
0x18000c6a6  mov     [rsp+2C8h+dwFlagsAndAttributes], ecx
0x18000c6aa  mov     rcx, [rsp+2C8h+lpMem]
0x18000c6af  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x18000c6b4  mov     r9d, [rsp+2C8h+var_27C]
0x18000c6b9  mov     r8d, r13d
0x18000c6bc  mov     rdx, rsi
0x18000c6bf  mov     rcx, rax
0x18000c6c2  call    ??0CFveSys@@AEAA@PEAXW4_FVE_DEVICE_TYPE@@KPEAGK@Z; CFveSys::CFveSys(void *,_FVE_DEVICE_TYPE,ulong,ushort *,ulong)
0x18000c6c7  mov     rdi, rax
0x18000c6ca  mov     [rsp+2C8h+var_268], rax
0x18000c6cf  test    rax, rax
0x18000c6d2  jz      short loc_18000C745
0x18000c6d4  mov     [r15], rax
0x18000c6d7  xor     edi, edi
0x18000c6d9  mov     [rsp+2C8h+var_268], rdi
0x18000c6de  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000c6e2  mov     [rsp+2C8h+var_270], rsi
0x18000c6e7  mov     [rsp+2C8h+lpMem], rdi
0x18000c6ec  mov     rcx, cs:?_ClassList@CFveSys@@0PEAV1@EA; CFveSys * CFveSys::_ClassList
0x18000c6f3  test    rcx, rcx
0x18000c6f6  jz      short loc_18000C703
0x18000c6f8  mov     [rcx+50h], rax
0x18000c6fc  mov     rcx, cs:?_ClassList@CFveSys@@0PEAV1@EA; CFveSys * CFveSys::_ClassList
0x18000c703  mov     rax, [r15]
0x18000c706  mov     [rax+48h], rcx
0x18000c70a  mov     rax, [r15]
0x18000c70d  mov     cs:?_ClassList@CFveSys@@0PEAV1@EA, rax; CFveSys * CFveSys::_ClassList
0x18000c714  lea     rcx, ?_ListLock@CFveSys@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c71b  call    cs:__imp_LeaveCriticalSection
0x18000c722  nop     dword ptr [rax+rax+00h]
0x18000c727  xor     r14d, r14d
0x18000c72a  mov     [rsp+2C8h+var_284], r14d
0x18000c72f  jmp     short loc_18000C780
0x18000c731  cmp     [rax+60h], r13d
0x18000c735  jnz     short loc_18000C73C
0x18000c737  cmp     [rax+68h], edx
0x18000c73a  jz      short loc_18000C750
0x18000c73c  lea     rcx, [rax+48h]
0x18000c740  jmp     loc_18000C5F7
0x18000c745  mov     ebx, 8007000Eh
0x18000c74a  mov     [rsp+2C8h+var_288], ebx
0x18000c74e  jmp     short loc_18000C780
0x18000c750  cmp     [rax+64h], r8d
0x18000c754  jnz     short loc_18000C73C
0x18000c756  test    rax, rax
0x18000c759  jz      loc_18000C603
0x18000c75f  lock add [rax+40h], r14d
0x18000c764  mov     rax, [rcx]
0x18000c767  mov     [r15], rax
0x18000c76a  jmp     short loc_18000C714
0x18000c76c  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18000c771  mov     ebx, eax
0x18000c773  mov     [rsp+2C8h+var_288], eax
0x18000c777  jmp     short loc_18000C780
0x18000c779  mov     ebx, 80070057h
0x18000c77e  jmp     short loc_18000C74A
0x18000c780  test    r14d, r14d
0x18000c783  jnz     short loc_18000C7C0
0x18000c785  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000c789  jnz     short loc_18000C7D5
0x18000c78b  test    rdi, rdi
0x18000c78e  jnz     short loc_18000C7E6
0x18000c790  mov     rcx, [rsp+2C8h+lpMem]; lpMem
0x18000c795  test    rcx, rcx
0x18000c798  jnz     short loc_18000C7F7
0x18000c79a  mov     eax, ebx
0x18000c79c  mov     rcx, [rsp+2C8h+var_48]
0x18000c7a4  xor     rcx, rsp; StackCookie
0x18000c7a7  call    __security_check_cookie
0x18000c7ac  add     rsp, 290h
0x18000c7b3  pop     r15
0x18000c7b5  pop     r14
0x18000c7b7  pop     r13
0x18000c7b9  pop     r12
0x18000c7bb  pop     rdi
0x18000c7bc  pop     rsi
0x18000c7bd  pop     rbx
0x18000c7be  retn
0x18000c7c0  lea     rcx, ?_ListLock@CFveSys@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000c7c7  call    cs:__imp_LeaveCriticalSection
0x18000c7ce  nop     dword ptr [rax+rax+00h]
0x18000c7d3  jmp     short loc_18000C785
0x18000c7d5  mov     rcx, rsi; hObject
0x18000c7d8  call    cs:__imp_CloseHandle
0x18000c7df  nop     dword ptr [rax+rax+00h]
0x18000c7e4  jmp     short loc_18000C78B
0x18000c7e6  mov     rax, [rdi]
0x18000c7e9  mov     rcx, rdi
0x18000c7ec  mov     rax, [rax+10h]
0x18000c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f5  jmp     short loc_18000C790
0x18000c7f7  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18000c7fc  jmp     short loc_18000C79A
0x18011fb0c  push    rbp
0x18011fb0e  sub     rsp, 40h
0x18011fb12  mov     rbp, rdx
0x18011fb15  cmp     dword ptr [rbp+44h], 0
0x18011fb19  jz      short loc_18011FB35
0x18011fb1b  lea     rcx, ?_ListLock@CFveSys@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011fb22  call    cs:__imp_LeaveCriticalSection
0x18011fb29  nop     dword ptr [rax+rax+00h]
0x18011fb2e  mov     dword ptr [rbp+44h], 0
0x18011fb35  mov     rcx, [rbp+58h]; hObject
0x18011fb39  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18011fb3d  jz      short loc_18011FB53
0x18011fb3f  call    cs:__imp_CloseHandle
0x18011fb46  nop     dword ptr [rax+rax+00h]
0x18011fb4b  mov     qword ptr [rbp+58h], 0FFFFFFFFFFFFFFFFh
0x18011fb53  mov     rcx, [rbp+60h]
0x18011fb57  test    rcx, rcx
0x18011fb5a  jz      short loc_18011FB70
0x18011fb5c  mov     rax, [rcx]
0x18011fb5f  mov     rax, [rax+10h]
0x18011fb63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011fb68  mov     qword ptr [rbp+60h], 0
0x18011fb70  mov     rcx, [rbp+50h]; lpMem
0x18011fb74  test    rcx, rcx
0x18011fb77  jz      short loc_18011FB7F
0x18011fb79  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x18011fb7e  nop
0x18011fb7f  add     rsp, 40h
0x18011fb83  pop     rbp
0x18011fb84  retn
```
