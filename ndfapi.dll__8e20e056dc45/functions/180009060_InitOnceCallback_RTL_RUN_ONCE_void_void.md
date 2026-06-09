# InitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x180009060`
- end: `0x1800092b6`
- name: `?InitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `598`
- prototype: `__int64 __fastcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800026a6`
- `0x180006f9c`
- `0x18000710c`
- `0x180009060`
- `0x180009f2c`
- `0x18000a078`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000919e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000922e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000919e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000922e`
- `KERNEL32!GetLastError` at `0x180009126`
- `KERNEL32!GetLastError` at `0x180009126`
- `KERNEL32!CloseHandle` at `0x1800091b2`
- `KERNEL32!CloseHandle` at `0x18000929c`
- `KERNEL32!CloseHandle` at `0x1800091b2`
- `KERNEL32!CloseHandle` at `0x18000929c`
- `KERNEL32!OpenProcess` at `0x18000908a`
- `KERNEL32!OpenProcess` at `0x18000908a`
- `KERNEL32!GetCurrentProcessId` at `0x18000907a`
- `KERNEL32!GetCurrentProcessId` at `0x18000907a`
- `KERNEL32!QueryFullProcessImageNameA` at `0x180009116`
- `KERNEL32!QueryFullProcessImageNameA` at `0x180009179`
- `KERNEL32!QueryFullProcessImageNameA` at `0x180009116`
- `KERNEL32!QueryFullProcessImageNameA` at `0x180009179`

## pseudocode

```c
__int64 __fastcall InitOnceCallback(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  DWORD CurrentProcessId; // eax
  char *v4; // rbx
  LPSTR *v5; // rcx
  LPSTR *v6; // rax
  CHAR *v7; // r8
  BOOL v8; // edi
  __int64 v9; // r8
  __int64 v10; // r9
  void *v11; // rdx
  DWORD v12; // eax
  DWORD v13; // ecx
  const char *v14; // r9
  CHAR *v15; // r8
  LPSTR *v17; // rax
  LPSTR v18; // rcx
  unsigned __int64 v19; // rsi
  __int64 v20; // rdi
  __int64 v21; // rdx
  LPSTR *v22; // rax
  DWORD dwSize; // [rsp+20h] [rbp-48h] BYREF
  char *v24; // [rsp+28h] [rbp-40h]
  LPSTR lpExeName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v26; // [rsp+40h] [rbp-28h]
  unsigned __int64 v27; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  CurrentProcessId = GetCurrentProcessId();
  v4 = (char *)OpenProcess(0x1000u, 0, CurrentProcessId);
  v24 = v4;
  if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_21:
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    return 0;
  }
  dwSize = 260;
  v27 = 15;
  v26 = 0;
  LOBYTE(lpExeName[0]) = 0;
  std::string::_Copy((const void **)lpExeName, 0x104u, 0);
  v5 = lpExeName;
  if ( v27 >= 0x10 )
    v5 = (LPSTR *)lpExeName[0];
  memset_0(v5, 0, 0x104u);
  v6 = lpExeName;
  if ( v27 >= 0x10 )
    v6 = (LPSTR *)lpExeName[0];
  v26 = 260;
  *((_BYTE *)v6 + 260) = 0;
  v7 = (CHAR *)lpExeName;
  if ( v27 >= 0x10 )
    v7 = lpExeName[0];
  v8 = QueryFullProcessImageNameA(v4, 0, v7, &dwSize);
  if ( !v8 )
  {
    while ( GetLastError() == 122 )
    {
      v11 = (void *)dwSize;
      v12 = dwSize + (dwSize >> 1);
      v13 = -1;
      if ( v12 >= dwSize )
        v13 = dwSize + (dwSize >> 1);
      v14 = v12 < dwSize ? (const char *)0x80070216LL : 0LL;
      dwSize = v13;
      if ( v12 < (unsigned int)v11 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, v11, (unsigned int)retaddr, v14, dwSize);
LABEL_18:
        if ( v8 )
          goto LABEL_24;
        break;
      }
      std::string::resize(lpExeName, v13, retaddr, v14);
      v15 = (CHAR *)lpExeName;
      if ( v27 >= 0x10 )
        v15 = lpExeName[0];
      v8 = QueryFullProcessImageNameA(v4, 0, v15, &dwSize);
      if ( v8 )
        goto LABEL_18;
    }
    if ( v27 >= 0x10 )
      operator delete(lpExeName[0]);
    goto LABEL_21;
  }
LABEL_24:
  std::string::resize(lpExeName, dwSize, v9, v10);
  while ( 1 )
  {
    v17 = lpExeName;
    v18 = lpExeName[0];
    v19 = v27;
    if ( v27 >= 0x10 )
      v17 = (LPSTR *)lpExeName[0];
    v20 = v26;
    if ( *((_BYTE *)v17 + v26 - 1) )
      break;
    v21 = v26 - 1;
    if ( !v26 )
      std::wstring::_Xran();
    v22 = lpExeName;
    if ( v27 >= 0x10 )
      v22 = (LPSTR *)lpExeName[0];
    --v26;
    *((_BYTE *)v22 + v21) = 0;
  }
  if ( (unsigned __int64)qword_18002F6D0 >= 0x10 )
  {
    operator delete((void *)g_processPath);
    v19 = v27;
    v20 = v26;
    v18 = lpExeName[0];
  }
  LOBYTE(g_processPath) = 0;
  if ( v19 >= 0x10 )
  {
    g_processPath = (__int64)v18;
    lpExeName[0] = 0;
  }
  else if ( v20 != -1 )
  {
    memcpy_0(&g_processPath, lpExeName, v20 + 1);
  }
  qword_18002F6C8 = v20;
  qword_18002F6D0 = v19;
  v27 = 15;
  v26 = 0;
  LOBYTE(lpExeName[0]) = 0;
  CloseHandle(v4);
  return 1;
}

```

## disassembly

```asm
0x180009060  push    rbp
0x180009062  push    rbx
0x180009063  push    rsi
0x180009064  push    rdi
0x180009065  mov     rbp, rsp
0x180009068  sub     rsp, 68h
0x18000906c  mov     rax, cs:__security_cookie
0x180009073  xor     rax, rsp
0x180009076  mov     [rbp+var_18], rax
0x18000907a  call    cs:__imp_GetCurrentProcessId
0x180009080  mov     r8d, eax; dwProcessId
0x180009083  xor     edx, edx; bInheritHandle
0x180009085  mov     ecx, 1000h; dwDesiredAccess
0x18000908a  call    cs:__imp_OpenProcess
0x180009090  mov     rbx, rax
0x180009093  mov     [rbp+var_40], rax
0x180009097  dec     rax
0x18000909a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000909e  ja      loc_1800091A5
0x1800090a4  mov     edi, 104h
0x1800090a9  mov     [rbp+dwSize], edi
0x1800090ac  mov     [rbp+var_20], 0Fh
0x1800090b4  mov     [rbp+var_28], 0
0x1800090bc  mov     byte ptr [rbp+lpExeName], 0
0x1800090c0  xor     r8d, r8d
0x1800090c3  mov     edx, edi
0x1800090c5  lea     rcx, [rbp+lpExeName]; Src
0x1800090c9  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800090ce  lea     rcx, [rbp+lpExeName]
0x1800090d2  cmp     [rbp+var_20], 10h
0x1800090d7  cmovnb  rcx, [rbp+lpExeName]; void *
0x1800090dc  mov     r8d, edi; Size
0x1800090df  xor     edx, edx; Val
0x1800090e1  call    memset_0
0x1800090e6  lea     rax, [rbp+lpExeName]
0x1800090ea  cmp     [rbp+var_20], 10h
0x1800090ef  cmovnb  rax, [rbp+lpExeName]
0x1800090f4  mov     [rbp+var_28], rdi
0x1800090f8  mov     byte ptr [rax+104h], 0
0x1800090ff  lea     r8, [rbp+lpExeName]
0x180009103  cmp     [rbp+var_20], 10h
0x180009108  cmovnb  r8, [rbp+lpExeName]; lpExeName
0x18000910d  lea     r9, [rbp+dwSize]; lpdwSize
0x180009111  xor     edx, edx; dwFlags
0x180009113  mov     rcx, rbx; hProcess
0x180009116  call    cs:__imp_QueryFullProcessImageNameA
0x18000911c  mov     edi, eax
0x18000911e  test    eax, eax
0x180009120  jnz     loc_1800091CF
0x180009126  call    cs:__imp_GetLastError
0x18000912c  cmp     eax, 7Ah ; 'z'
0x18000912f  jnz     short loc_180009193
0x180009131  mov     edx, [rbp+dwSize]; void *
0x180009134  mov     eax, edx
0x180009136  shr     eax, 1
0x180009138  add     eax, edx
0x18000913a  or      ecx, 0FFFFFFFFh
0x18000913d  cmp     eax, edx
0x18000913f  cmovnb  ecx, eax
0x180009142  sbb     r9d, r9d
0x180009145  and     r9d, 80070216h; char *
0x18000914c  mov     [rbp+dwSize], ecx
0x18000914f  mov     r8, [rbp+20h]; unsigned int
0x180009153  cmp     eax, edx
0x180009155  jb      short loc_180009187
0x180009157  mov     edx, ecx
0x180009159  lea     rcx, [rbp+lpExeName]
0x18000915d  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::resize(unsigned __int64)
0x180009162  lea     r8, [rbp+lpExeName]
0x180009166  cmp     [rbp+var_20], 10h
0x18000916b  cmovnb  r8, [rbp+lpExeName]; lpExeName
0x180009170  lea     r9, [rbp+dwSize]; lpdwSize
0x180009174  xor     edx, edx; dwFlags
0x180009176  mov     rcx, rbx; hProcess
0x180009179  call    cs:__imp_QueryFullProcessImageNameA
0x18000917f  mov     edi, eax
0x180009181  test    eax, eax
0x180009183  jz      short loc_180009126
0x180009185  jmp     short loc_18000918F
0x180009187  mov     rcx, r8; this
0x18000918a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000918f  test    edi, edi
0x180009191  jnz     short loc_1800091CF
0x180009193  cmp     [rbp+var_20], 10h
0x180009198  jb      short loc_1800091A5
0x18000919a  mov     rcx, [rbp+lpExeName]
0x18000919e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800091a4  nop
0x1800091a5  lea     rax, [rbx-1]
0x1800091a9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800091ad  ja      short loc_1800091B8
0x1800091af  mov     rcx, rbx; hObject
0x1800091b2  call    cs:__imp_CloseHandle
0x1800091b8  xor     eax, eax
0x1800091ba  mov     rcx, [rbp+var_18]
0x1800091be  xor     rcx, rsp; StackCookie
0x1800091c1  call    __security_check_cookie
0x1800091c6  add     rsp, 68h
0x1800091ca  pop     rdi
0x1800091cb  pop     rsi
0x1800091cc  pop     rbx
0x1800091cd  pop     rbp
0x1800091ce  retn
0x1800091cf  mov     edx, [rbp+dwSize]
0x1800091d2  lea     rcx, [rbp+lpExeName]
0x1800091d6  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K@Z; std::string::resize(unsigned __int64)
0x1800091db  lea     rax, [rbp+lpExeName]
0x1800091df  mov     rcx, [rbp+lpExeName]
0x1800091e3  mov     rsi, [rbp+var_20]
0x1800091e7  cmp     rsi, 10h
0x1800091eb  cmovnb  rax, rcx
0x1800091ef  mov     rdi, [rbp+var_28]
0x1800091f3  cmp     byte ptr [rdi+rax-1], 0
0x1800091f8  jnz     short loc_18000921D
0x1800091fa  lea     rdx, [rdi-1]
0x1800091fe  cmp     rdi, rdx
0x180009201  jb      loc_1800092AC
0x180009207  lea     rax, [rbp+lpExeName]
0x18000920b  cmp     rsi, 10h
0x18000920f  cmovnb  rax, rcx
0x180009213  mov     [rbp+var_28], rdx
0x180009217  mov     byte ptr [rdx+rax], 0
0x18000921b  jmp     short loc_1800091DB
0x18000921d  cmp     cs:qword_18002F6D0, 10h
0x180009225  jb      short loc_180009240
0x180009227  mov     rcx, cs:?g_processPath@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string g_processPath
0x18000922e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009234  mov     rsi, [rbp+var_20]
0x180009238  mov     rdi, [rbp+var_28]
0x18000923c  mov     rcx, [rbp+lpExeName]
0x180009240  mov     byte ptr cs:?g_processPath@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A, 0; std::string g_processPath
0x180009247  cmp     rsi, 10h
0x18000924b  jnb     short loc_180009268
0x18000924d  lea     r8, [rdi+1]; Size
0x180009251  test    r8, r8
0x180009254  jz      short loc_180009277
0x180009256  lea     rdx, [rbp+lpExeName]; Src
0x18000925a  lea     rcx, ?g_processPath@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; void *
0x180009261  call    memcpy_0
0x180009266  jmp     short loc_180009277
0x180009268  mov     cs:?g_processPath@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A, rcx; std::string g_processPath
0x18000926f  mov     [rbp+lpExeName], 0
0x180009277  mov     cs:qword_18002F6C8, rdi
0x18000927e  mov     cs:qword_18002F6D0, rsi
0x180009285  mov     [rbp+var_20], 0Fh
0x18000928d  mov     [rbp+var_28], 0
0x180009295  mov     byte ptr [rbp+lpExeName], 0
0x180009299  mov     rcx, rbx; hObject
0x18000929c  call    cs:__imp_CloseHandle
0x1800092a2  mov     eax, 1
0x1800092a7  jmp     loc_1800091BA
0x1800092ac  lea     rcx, [rbp+lpExeName]
0x1800092b0  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
```
