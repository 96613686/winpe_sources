# FindExecutable(_PROCESS_ENTRY *,ushort const *,ushort const *,ushort *,_FINDEXE_CALLBACK *,void *,ulong)

- ea: `0x1801a8ed0`
- end: `0x1801a92a7`
- name: `?FindExecutable@@YAPEAXPEAU_PROCESS_ENTRY@@PEBG1PEAGPEAU_FINDEXE_CALLBACK@@PEAXK@Z`
- size: `983`
- prototype: `void *__fastcall(struct _PROCESS_ENTRY *, LPCWSTR lpFileName, const unsigned __int16 *, unsigned __int16 *, struct _FINDEXE_CALLBACK *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1801a8e60`

## callees

- `0x1800089f0`
- `0x18000de4c`
- `0x18000dfac`
- `0x180011e08`
- `0x180011fb8`
- `0x180012e6c`
- `0x180012f54`
- `0x180016ebc`
- `0x180021374`
- `0x180023498`
- `0x1801a85f8`
- `0x1801a8c98`
- `0x1801a8ed0`
- `0x1801a9900`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a9099`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801a9099`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801a8fc9`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1801a8fc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a927c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a927c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a9267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a9267`

## string_xrefs

- `0x1801a8f8b`: `%_NT_SYMBOL_PATH%;%_NT_ALTERNATE_SYMBOL_PATH%`

## pseudocode

```c
void *__fastcall FindExecutable(
        struct _PROCESS_ENTRY *a1,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct _FINDEXE_CALLBACK *a5,
        void *a6,
        unsigned int a7)
{
  struct _PROCESS_ENTRY *v9; // r14
  __int64 v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // rcx
  void *v13; // rsi
  int v14; // r8d
  int v15; // r9d
  const unsigned __int16 *v17; // r13
  unsigned __int64 v18; // r8
  int v19; // r9d
  int v20; // r9d
  int (*cb)(const unsigned __int16 *, void *); // [rsp+20h] [rbp-5A8h]
  LPWSTR FilePart; // [rsp+40h] [rbp-588h] BYREF
  unsigned __int16 *v23; // [rsp+48h] [rbp-580h]
  __int128 data; // [rsp+58h] [rbp-570h] BYREF
  __int128 v25; // [rsp+68h] [rbp-560h]
  struct _FINDEXE_CALLBACK *v26; // [rsp+78h] [rbp-550h]
  unsigned __int16 *v27; // [rsp+80h] [rbp-548h]
  wchar_t Str[264]; // [rsp+90h] [rbp-538h] BYREF
  unsigned __int16 v29[264]; // [rsp+2A0h] [rbp-328h] BYREF
  unsigned __int16 v30[104]; // [rsp+4B0h] [rbp-118h] BYREF

  v9 = a1;
  v27 = a4;
  v26 = a5;
  FilePart = 0;
  data = 0;
  v25 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    SetLastError(0x57u);
    return 0;
  }
  v23 = 0;
  if ( !a1 )
  {
    v10 = *((_QWORD *)a5 + 1);
    if ( v10 )
    {
      if ( *(_DWORD *)v10 == 4888 )
        v9 = *(struct _PROCESS_ENTRY **)(v10 + 8);
    }
  }
  v11 = ExpandPath(a3);
  v23 = v11;
  if ( !v11 )
  {
    if ( v9 )
    {
      v12 = (unsigned __int16 *)*((_QWORD *)v9 + 8);
    }
    else
    {
      wcscpy_s_ex(v30, 0x64u, L"%_NT_SYMBOL_PATH%;%_NT_ALTERNATE_SYMBOL_PATH%");
      v12 = v30;
    }
    v23 = ExpandPath(v12);
    v11 = v23;
  }
  if ( !GetFullPathNameW(lpFileName, 0x105u, a4, &FilePart) )
  {
    FreeIt(v11);
    return 0;
  }
  v13 = CheckExecutableImage(a4, a5, a7);
  if ( v13 == (void *)-1LL )
  {
    v29[0] = 0;
    v17 = v11;
    while ( v17 )
    {
      v17 = TokenFromSymbolPath(v17, Str, v14);
      if ( Str[0] && !IsCacheDir(Str, v29, v14) && !wcschr(Str, 0x2Au) )
      {
        *(_QWORD *)&data = v26;
        *((_QWORD *)&data + 1) = *((_QWORD *)v26 + 1);
        LODWORD(v25) = a7;
        if ( (unsigned int)CheckDirForExecutable(v9, Str, FilePart, a4, cb, &data) )
        {
          if ( v29[0] )
            CopyOpenFileToCache(v9, (void *)0xFFFFFFFFFFFFFFFFLL, a4, v19, v29);
          if ( (unsigned int)spew() )
            _pwprint(v9, L"%s found\n", a4);
LABEL_27:
          FreeIt(v11);
          return (void *)*((_QWORD *)&v25 + 1);
        }
        if ( !(unsigned int)symsrvTest(v9, Str, v18, 0)
          && EnumDirTreeW((HANDLE)0xFFFFFFFFFFFFFFFFLL, Str, FilePart, a4, cbFindExeSrchTree, &data) )
        {
          if ( v29[0] )
            CopyOpenFileToCache(v9, (void *)0xFFFFFFFFFFFFFFFFLL, a4, v20, v29);
          if ( (unsigned int)spew() )
            _pwprint(v9, L"%s found\n", a4);
          goto LABEL_27;
        }
        if ( (unsigned int)spew() )
          _pwprint(v9, L"%s not found in %s\n", FilePart, Str);
      }
    }
    *a4 = 0;
    FreeIt(v11);
    CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL);
    return 0;
  }
  if ( (unsigned int)GetCacheDir(v11, v29, v14) )
    v13 = CopyOpenFileToCache(v9, v13, a4, v15, v29);
  FreeIt(v11);
  return v13;
}

```

## disassembly

```asm
0x1801a8ed0  push    rbx
0x1801a8ed2  push    rsi
0x1801a8ed3  push    rdi
0x1801a8ed4  push    r12
0x1801a8ed6  push    r13
0x1801a8ed8  push    r14
0x1801a8eda  push    r15
0x1801a8edc  sub     rsp, 590h
0x1801a8ee3  mov     rax, cs:__security_cookie
0x1801a8eea  xor     rax, rsp
0x1801a8eed  mov     [rsp+5C8h+var_48], rax
0x1801a8ef5  mov     r15, r9
0x1801a8ef8  mov     rsi, rdx
0x1801a8efb  mov     r14, rcx
0x1801a8efe  mov     [rsp+5C8h+var_548], r9
0x1801a8f06  mov     r13, [rsp+5C8h+arg_20]
0x1801a8f0e  mov     [rsp+5C8h+var_550], r13
0x1801a8f13  mov     eax, [rsp+5C8h+arg_30]
0x1801a8f1a  mov     [rsp+5C8h+var_590], eax
0x1801a8f1e  xor     ebx, ebx
0x1801a8f20  mov     [rsp+5C8h+FilePart], rbx
0x1801a8f25  xorps   xmm0, xmm0
0x1801a8f28  movups  [rsp+5C8h+var_570], xmm0
0x1801a8f2d  movups  [rsp+5C8h+var_560], xmm0
0x1801a8f32  test    rdx, rdx
0x1801a8f35  jz      loc_1801A9277
0x1801a8f3b  cmp     [rdx], bx
0x1801a8f3e  jz      loc_1801A9277
0x1801a8f44  mov     [rsp+5C8h+var_598], rbx
0x1801a8f49  mov     [rsp+5C8h+var_580], rbx
0x1801a8f4e  mov     r12d, ebx
0x1801a8f51  test    rcx, rcx
0x1801a8f54  jnz     short loc_1801A8F6B
0x1801a8f56  mov     rax, [r13+8]
0x1801a8f5a  test    rax, rax
0x1801a8f5d  jz      short loc_1801A8F6B
0x1801a8f5f  cmp     dword ptr [rax], 1318h
0x1801a8f65  jnz     short loc_1801A8F6B
0x1801a8f67  mov     r14, [rax+8]
0x1801a8f6b  mov     rcx, r8; unsigned __int16 *
0x1801a8f6e  call    ?ExpandPath@@YAPEAGPEBG@Z; ExpandPath(ushort const *)
0x1801a8f73  mov     rdi, rax
0x1801a8f76  mov     [rsp+5C8h+var_580], rax
0x1801a8f7b  test    rax, rax
0x1801a8f7e  jnz     short loc_1801A8FB9
0x1801a8f80  test    r14, r14
0x1801a8f83  jz      short loc_1801A8F8B
0x1801a8f85  mov     rcx, [r14+40h]
0x1801a8f89  jmp     short loc_1801A8FAC
0x1801a8f8b  lea     r8, aNtSymbolPathNt; "%_NT_SYMBOL_PATH%;%_NT_ALTERNATE_SYMBOL"...
0x1801a8f92  mov     edx, 64h ; 'd'; unsigned __int64
0x1801a8f97  lea     rcx, [rsp+5C8h+var_118]; unsigned __int16 *
0x1801a8f9f  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8fa4  lea     rcx, [rsp+5C8h+var_118]; unsigned __int16 *
0x1801a8fac  call    ?ExpandPath@@YAPEAGPEBG@Z; ExpandPath(ushort const *)
0x1801a8fb1  mov     [rsp+5C8h+var_580], rax
0x1801a8fb6  mov     rdi, rax
0x1801a8fb9  lea     r9, [rsp+5C8h+FilePart]; lpFilePart
0x1801a8fbe  mov     r8, r15; lpBuffer
0x1801a8fc1  mov     edx, 105h; nBufferLength
0x1801a8fc6  mov     rcx, rsi; lpFileName
0x1801a8fc9  call    cs:__imp_GetFullPathNameW
0x1801a8fcf  test    eax, eax
0x1801a8fd1  jz      loc_1801A9211
0x1801a8fd7  mov     r8d, [rsp+5C8h+var_590]; unsigned int
0x1801a8fdc  mov     rdx, r13; struct _FINDEXE_CALLBACK *
0x1801a8fdf  mov     rcx, r15; unsigned __int16 *
0x1801a8fe2  call    ?CheckExecutableImage@@YAPEAXPEBGPEAU_FINDEXE_CALLBACK@@K@Z; CheckExecutableImage(ushort const *,_FINDEXE_CALLBACK *,ulong)
0x1801a8fe7  mov     rsi, rax
0x1801a8fea  mov     [rsp+5C8h+var_598], rax
0x1801a8fef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a8ff3  jz      short loc_1801A903C
0x1801a8ff5  lea     rdx, [rsp+5C8h+var_328]; unsigned __int16 *
0x1801a8ffd  mov     rcx, rdi; unsigned __int16 *
0x1801a9000  call    ?GetCacheDir@@YAHPEBGPEAGH@Z; GetCacheDir(ushort const *,ushort *,int)
0x1801a9005  test    eax, eax
0x1801a9007  jz      short loc_1801A902C
0x1801a9009  lea     rax, [rsp+5C8h+var_328]
0x1801a9011  mov     [rsp+5C8h+cb], rax; unsigned __int16 *
0x1801a9016  mov     r8, r15; unsigned __int16 *
0x1801a9019  mov     rdx, rsi; void *
0x1801a901c  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a901f  call    ?CopyOpenFileToCache@@YAPEAXPEAU_PROCESS_ENTRY@@PEAXPEAGHPEBG@Z; CopyOpenFileToCache(_PROCESS_ENTRY *,void *,ushort *,int,ushort const *)
0x1801a9024  mov     rsi, rax
0x1801a9027  mov     [rsp+5C8h+var_598], rax
0x1801a902c  mov     rcx, rdi; lpMem
0x1801a902f  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a9034  mov     rax, rsi
0x1801a9037  jmp     loc_1801A9284
0x1801a903c  mov     [rsp+5C8h+var_328], bx
0x1801a9044  mov     r13, rdi
0x1801a9047  test    r13, r13
0x1801a904a  jz      loc_1801A920F
0x1801a9050  lea     rdx, [rsp+5C8h+Str]; unsigned __int16 *
0x1801a9058  mov     rcx, r13; unsigned __int16 *
0x1801a905b  call    ?TokenFromSymbolPath@@YAPEAGPEBGPEAGH@Z; TokenFromSymbolPath(ushort const *,ushort *,int)
0x1801a9060  mov     r13, rax
0x1801a9063  cmp     [rsp+5C8h+Str], bx
0x1801a906b  jz      loc_1801A920A
0x1801a9071  lea     rdx, [rsp+5C8h+var_328]; unsigned __int16 *
0x1801a9079  lea     rcx, [rsp+5C8h+Str]; unsigned __int16 *
0x1801a9081  call    ?IsCacheDir@@YAHPEBGPEAGH@Z; IsCacheDir(ushort const *,ushort *,int)
0x1801a9086  test    eax, eax
0x1801a9088  jnz     loc_1801A920A
0x1801a908e  lea     edx, [rax+2Ah]; Ch
0x1801a9091  lea     rcx, [rsp+5C8h+Str]; Str
0x1801a9099  call    cs:__imp_wcschr
0x1801a909f  test    rax, rax
0x1801a90a2  jnz     loc_1801A920A
0x1801a90a8  mov     rax, [rsp+5C8h+var_550]
0x1801a90ad  mov     qword ptr [rsp+5C8h+var_570], rax
0x1801a90b2  mov     rax, [rax+8]
0x1801a90b6  mov     qword ptr [rsp+5C8h+var_570+8], rax
0x1801a90bb  mov     eax, [rsp+5C8h+var_590]
0x1801a90bf  mov     dword ptr [rsp+5C8h+var_560], eax
0x1801a90c3  lea     rax, [rsp+5C8h+var_570]
0x1801a90c8  mov     [rsp+5C8h+data], rax; void *
0x1801a90cd  mov     r9, r15; unsigned __int16 *
0x1801a90d0  mov     r8, [rsp+5C8h+FilePart]; unsigned __int16 *
0x1801a90d5  lea     rdx, [rsp+5C8h+Str]; unsigned __int16 *
0x1801a90dd  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a90e0  call    ?CheckDirForExecutable@@YAHPEAU_PROCESS_ENTRY@@PEBG1PEAGP6AH1PEAX@Z3@Z; CheckDirForExecutable(_PROCESS_ENTRY *,ushort const *,ushort const *,ushort *,int (*)(ushort const *,void *),void *)
0x1801a90e5  test    eax, eax
0x1801a90e7  jz      short loc_1801A9140
0x1801a90e9  cmp     [rsp+5C8h+var_328], bx
0x1801a90f1  jz      short loc_1801A9113
0x1801a90f3  lea     rax, [rsp+5C8h+var_328]
0x1801a90fb  mov     [rsp+5C8h+cb], rax; unsigned __int16 *
0x1801a9100  mov     r8, r15; unsigned __int16 *
0x1801a9103  mov     rdx, rsi; void *
0x1801a9106  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a9109  call    ?CopyOpenFileToCache@@YAPEAXPEAU_PROCESS_ENTRY@@PEAXPEAGHPEBG@Z; CopyOpenFileToCache(_PROCESS_ENTRY *,void *,ushort *,int,ushort const *)
0x1801a910e  mov     [rsp+5C8h+var_598], rax
0x1801a9113  call    ?spew@@YAHXZ; spew(void)
0x1801a9118  test    eax, eax
0x1801a911a  jz      short loc_1801A912E
0x1801a911c  mov     r8, r15
0x1801a911f  lea     rdx, aSFound; "%s found\n"
0x1801a9126  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a9129  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a912e  mov     rcx, rdi; lpMem
0x1801a9131  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a9136  mov     rax, qword ptr [rsp+5C8h+var_560+8]
0x1801a913b  jmp     loc_1801A9284
0x1801a9140  xor     r9d, r9d; int
0x1801a9143  lea     rdx, [rsp+5C8h+Str]; unsigned __int16 *
0x1801a914b  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a914e  call    ?symsrvTest@@YAHPEAU_PROCESS_ENTRY@@PEAG_KH@Z; symsrvTest(_PROCESS_ENTRY *,ushort *,unsigned __int64,int)
0x1801a9153  test    eax, eax
0x1801a9155  jnz     loc_1801A91E5
0x1801a915b  lea     rax, [rsp+5C8h+var_570]
0x1801a9160  mov     [rsp+5C8h+data], rax; data
0x1801a9165  lea     rax, ?cbFindExeSrchTree@@YAHPEBGPEAX@Z; cbFindExeSrchTree(ushort const *,void *)
0x1801a916c  mov     [rsp+5C8h+cb], rax; cb
0x1801a9171  mov     r9, r15; OutputPathBuffer
0x1801a9174  mov     r8, [rsp+5C8h+FilePart]; InputPathName
0x1801a9179  lea     rdx, [rsp+5C8h+Str]; RootPath
0x1801a9181  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x1801a9185  call    EnumDirTreeW
0x1801a918a  test    eax, eax
0x1801a918c  jz      short loc_1801A91E5
0x1801a918e  cmp     [rsp+5C8h+var_328], bx
0x1801a9196  jz      short loc_1801A91B8
0x1801a9198  lea     rax, [rsp+5C8h+var_328]
0x1801a91a0  mov     [rsp+5C8h+cb], rax; unsigned __int16 *
0x1801a91a5  mov     r8, r15; unsigned __int16 *
0x1801a91a8  mov     rdx, rsi; void *
0x1801a91ab  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a91ae  call    ?CopyOpenFileToCache@@YAPEAXPEAU_PROCESS_ENTRY@@PEAXPEAGHPEBG@Z; CopyOpenFileToCache(_PROCESS_ENTRY *,void *,ushort *,int,ushort const *)
0x1801a91b3  mov     [rsp+5C8h+var_598], rax
0x1801a91b8  call    ?spew@@YAHXZ; spew(void)
0x1801a91bd  test    eax, eax
0x1801a91bf  jz      short loc_1801A91D3
0x1801a91c1  mov     r8, r15
0x1801a91c4  lea     rdx, aSFound; "%s found\n"
0x1801a91cb  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a91ce  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a91d3  mov     rcx, rdi; lpMem
0x1801a91d6  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a91db  mov     rax, qword ptr [rsp+5C8h+var_560+8]
0x1801a91e0  jmp     loc_1801A9284
0x1801a91e5  call    ?spew@@YAHXZ; spew(void)
0x1801a91ea  test    eax, eax
0x1801a91ec  jz      short loc_1801A920A
0x1801a91ee  lea     r9, [rsp+5C8h+Str]
0x1801a91f6  mov     r8, [rsp+5C8h+FilePart]
0x1801a91fb  lea     rdx, aSNotFoundInS; "%s not found in %s\n"
0x1801a9202  mov     rcx, r14; struct _PROCESS_ENTRY *
0x1801a9205  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a920a  jmp     loc_1801A9047
0x1801a920f  jmp     short loc_1801A923C
0x1801a9211  mov     rcx, rdi; lpMem
0x1801a9214  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a9219  xor     eax, eax
0x1801a921b  jmp     short loc_1801A9284
0x1801a921d  mov     r12d, 57h ; 'W'
0x1801a9223  mov     [rsp+5C8h+var_578], r12d
0x1801a9228  xor     ebx, ebx
0x1801a922a  mov     rsi, [rsp+5C8h+var_598]
0x1801a922f  mov     rdi, [rsp+5C8h+var_580]
0x1801a9234  mov     r15, [rsp+5C8h+var_548]
0x1801a923c  mov     [r15], bx
0x1801a9240  jmp     short loc_1801A9257
0x1801a9242  mov     r12d, 57h ; 'W'
0x1801a9248  mov     [rsp+5C8h+var_578], r12d
0x1801a924d  mov     rsi, [rsp+5C8h+var_598]
0x1801a9252  mov     rdi, [rsp+5C8h+var_580]
0x1801a9257  mov     rcx, rdi; lpMem
0x1801a925a  call    ?FreeIt@@YAXPEAX@Z; FreeIt(void *)
0x1801a925f  test    rsi, rsi
0x1801a9262  jz      short loc_1801A926D
0x1801a9264  mov     rcx, rsi; hObject
0x1801a9267  call    cs:__imp_CloseHandle
0x1801a926d  test    r12d, r12d
0x1801a9270  jz      short loc_1801A9282
0x1801a9272  mov     ecx, r12d
0x1801a9275  jmp     short loc_1801A927C
0x1801a9277  mov     ecx, 57h ; 'W'; dwErrCode
0x1801a927c  call    cs:__imp_SetLastError
0x1801a9282  xor     eax, eax
0x1801a9284  mov     rcx, [rsp+5C8h+var_48]
0x1801a928c  xor     rcx, rsp; StackCookie
0x1801a928f  call    __security_check_cookie
0x1801a9294  add     rsp, 590h
0x1801a929b  pop     r15
0x1801a929d  pop     r14
0x1801a929f  pop     r13
0x1801a92a1  pop     r12
0x1801a92a3  pop     rdi
0x1801a92a4  pop     rsi
0x1801a92a5  pop     rbx
0x1801a92a6  retn
```
