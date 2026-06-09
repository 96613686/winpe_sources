# CONFIG_CACHE::CopyAppHostLevelFile(ushort const *,ushort const *)

- ea: `0x18004d674`
- end: `0x18004d90a`
- name: `?CopyAppHostLevelFile@CONFIG_CACHE@@AEAAJPEBG0@Z`
- size: `662`
- prototype: `__int64 __fastcall(CONFIG_CACHE *this, const unsigned __int16 *Str, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180039ed0`
- `0x180039f10`

## callees

- `0x1800012c0`
- `0x180003480`
- `0x180008d00`
- `0x180016440`
- `0x1800174d0`
- `0x18001753c`
- `0x180017a64`
- `0x18004d674`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d863`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d863`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d8a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d896`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004d8a6`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18004d859`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18004d859`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004d803`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004d803`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004d8dc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d818`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d84a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d818`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004d84a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d6d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d6fc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d721`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d6d3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d6fc`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004d721`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::CopyAppHostLevelFile(
        CONFIG_CACHE *this,
        const unsigned __int16 *Str,
        const unsigned __int16 *a3)
{
  signed int appended; // ebx
  int v7; // eax
  HANDLE v8; // rdi
  const WCHAR *v9; // rax
  signed int LastError; // eax
  int v11; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[2]; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+80h] [rbp-80h]
  __int64 v18; // [rsp+88h] [rbp-78h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  _BYTE v21[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v22[56]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v23[64]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v24[3]; // [rsp+160h] [rbp+60h] BYREF
  int v25; // [rsp+178h] [rbp+78h]
  int v26; // [rsp+17Ch] [rbp+7Ch]
  int v27; // [rsp+180h] [rbp+80h]
  char v28; // [rsp+184h] [rbp+84h] BYREF
  unsigned __int16 v29[32]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v30[264]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v31[264]; // [rsp+560h] [rbp+460h] BYREF

  memset_0(v30, 0, 0x208u);
  STRU::STRU((STRU *)v23, v30, 0x104u);
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v22, v29, 0x20u);
  memset_0(v31, 0, 0x208u);
  STRU::STRU((STRU *)v21, v31, 0x104u);
  v27 &= 0xFFFFFFF0;
  v16[0] = &PARSE_ERROR_INFO::`vftable';
  v14 = 0;
  v24[0] = &v28;
  v16[1] = 1;
  v25 = -1;
  v26 = -1;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  hObject = 0;
  TokenHandle = 0;
  v24[1] = 0;
  v24[2] = 0;
  appended = PATH::Parse((PATH *)v24, L"MACHINE/WEBROOT/APPHOST");
  if ( appended >= 0 )
  {
    v7 = CONFIG_PATH_MAPPER::MapConfig(
           (CONFIG_CACHE *)((char *)this + 64),
           (struct PATH *)v24,
           2,
           0,
           (struct STRU *)v23,
           (struct STRU *)v22,
           &hObject,
           &v14,
           0,
           (struct PARSE_ERROR_INFO *)v16);
    v8 = hObject;
    appended = v7;
    if ( v7 >= 0 )
    {
      appended = STRU::Copy((STRU *)v21, (const struct STRU *)v23);
      if ( appended >= 0 )
      {
        if ( !Str )
          Str = STRU::QueryStr((STRU *)v22);
        appended = CONFIG_PATH_MAPPER::AppendFileName((struct STRU *)v21, Str);
        if ( appended >= 0 )
        {
          appended = CONFIG_CACHE::Impersonate(v8, &TokenHandle);
          if ( appended >= 0 )
          {
            v9 = STRU::QueryStr((STRU *)v21);
            if ( !CopyFileW(v9, a3, 0) )
            {
              LastError = GetLastError();
              appended = LastError;
              if ( LastError > 0 )
                appended = (unsigned __int16)LastError | 0x80070000;
            }
            v11 = CONFIG_CACHE::Unimpersonate(v8, TokenHandle);
            if ( v11 < 0 && appended >= 0 )
              appended = v11;
          }
        }
      }
    }
    if ( v8 )
      CloseHandle(v8);
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  PATH::Destroy((PATH *)v24);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v16);
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v23);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004d674  mov     [rsp-8+arg_18], rbx
0x18004d679  push    rbp
0x18004d67a  push    rsi
0x18004d67b  push    rdi
0x18004d67c  push    r14
0x18004d67e  push    r15
0x18004d680  lea     rbp, [rsp-680h]
0x18004d688  sub     rsp, 780h
0x18004d68f  mov     rax, cs:__security_cookie
0x18004d696  xor     rax, rsp
0x18004d699  mov     [rbp+6A0h+var_30], rax
0x18004d6a0  mov     r14, r8
0x18004d6a3  mov     rsi, rdx
0x18004d6a6  mov     rdi, rcx
0x18004d6a9  mov     r15d, 208h
0x18004d6af  mov     r8d, r15d; Size
0x18004d6b2  lea     rcx, [rbp+6A0h+var_450]; void *
0x18004d6b9  xor     edx, edx; Val
0x18004d6bb  call    memset_0
0x18004d6c0  mov     ebx, 104h
0x18004d6c5  lea     rdx, [rbp+6A0h+var_450]
0x18004d6cc  mov     r8d, ebx
0x18004d6cf  lea     rcx, [rbp+6A0h+var_680]
0x18004d6d3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d6d9  xor     edx, edx; Val
0x18004d6db  lea     rcx, [rbp+6A0h+var_490]; void *
0x18004d6e2  lea     r8d, [rdx+40h]; Size
0x18004d6e6  call    memset_0
0x18004d6eb  mov     r8d, 20h ; ' '
0x18004d6f1  lea     rdx, [rbp+6A0h+var_490]
0x18004d6f8  lea     rcx, [rbp+6A0h+var_6B8]
0x18004d6fc  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d702  mov     r8d, r15d; Size
0x18004d705  lea     rcx, [rbp+6A0h+var_240]; void *
0x18004d70c  xor     edx, edx; Val
0x18004d70e  call    memset_0
0x18004d713  mov     r8d, ebx
0x18004d716  lea     rdx, [rbp+6A0h+var_240]
0x18004d71d  lea     rcx, [rbp+6A0h+var_6F0]
0x18004d721  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004d727  and     [rbp+6A0h+var_620], 0FFFFFFF0h
0x18004d72e  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18004d735  xor     r15d, r15d
0x18004d738  mov     [rsp+7A0h+var_730], rax
0x18004d73d  lea     rax, [rbp+6A0h+var_61C]
0x18004d744  mov     [rsp+7A0h+var_748], r15d
0x18004d749  mov     [rbp+6A0h+var_640], rax
0x18004d74d  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18004d754  or      eax, 0FFFFFFFFh
0x18004d757  mov     [rsp+7A0h+var_728], 1
0x18004d760  xorps   xmm0, xmm0
0x18004d763  mov     [rbp+6A0h+var_628], eax
0x18004d766  xorps   xmm1, xmm1
0x18004d769  mov     [rbp+6A0h+var_624], eax
0x18004d76c  lea     rcx, [rbp+6A0h+var_640]; this
0x18004d770  mov     [rbp+6A0h+var_720], r15d
0x18004d774  mov     [rbp+6A0h+var_718], r15
0x18004d778  movdqa  [rbp+6A0h+var_710], xmm0
0x18004d77d  movdqa  [rbp+6A0h+var_700], xmm1
0x18004d782  mov     [rsp+7A0h+hObject], r15
0x18004d787  mov     [rsp+7A0h+TokenHandle], r15
0x18004d78c  mov     [rbp+6A0h+var_638], r15
0x18004d790  mov     [rbp+6A0h+var_630], r15
0x18004d794  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x18004d799  mov     ebx, eax
0x18004d79b  test    eax, eax
0x18004d79d  js      loc_18004D89C
0x18004d7a3  lea     rax, [rsp+7A0h+var_730]
0x18004d7a8  xor     r9d, r9d; struct _PATH_CACHE_NODE *
0x18004d7ab  mov     [rsp+7A0h+var_758], rax; struct PARSE_ERROR_INFO *
0x18004d7b0  lea     rcx, [rdi+40h]; this
0x18004d7b4  mov     [rsp+7A0h+var_760], r15; struct CONFIG_VDIR **
0x18004d7b9  lea     rax, [rsp+7A0h+var_748]
0x18004d7be  mov     [rsp+7A0h+var_768], rax; unsigned int *
0x18004d7c3  lea     r8d, [r15+2]; unsigned int
0x18004d7c7  lea     rax, [rsp+7A0h+hObject]
0x18004d7cc  mov     [rsp+7A0h+var_770], rax; void **
0x18004d7d1  lea     rdx, [rbp+6A0h+var_640]; struct PATH *
0x18004d7d5  lea     rax, [rbp+6A0h+var_6B8]
0x18004d7d9  mov     [rsp+7A0h+var_778], rax; struct STRU *
0x18004d7de  lea     rax, [rbp+6A0h+var_680]
0x18004d7e2  mov     [rsp+7A0h+var_780], rax; struct STRU *
0x18004d7e7  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x18004d7ec  mov     rdi, [rsp+7A0h+hObject]
0x18004d7f1  mov     ebx, eax
0x18004d7f3  test    eax, eax
0x18004d7f5  js      loc_18004D88E
0x18004d7fb  lea     rdx, [rbp+6A0h+var_680]
0x18004d7ff  lea     rcx, [rbp+6A0h+var_6F0]
0x18004d803  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x18004d809  mov     ebx, eax
0x18004d80b  test    eax, eax
0x18004d80d  js      short loc_18004D88E
0x18004d80f  test    rsi, rsi
0x18004d812  jnz     short loc_18004D821
0x18004d814  lea     rcx, [rbp+6A0h+var_6B8]
0x18004d818  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d81e  mov     rsi, rax
0x18004d821  mov     rdx, rsi; unsigned __int16 *
0x18004d824  lea     rcx, [rbp+6A0h+var_6F0]; struct STRU *
0x18004d828  call    ?AppendFileName@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@PEBG@Z; CONFIG_PATH_MAPPER::AppendFileName(STRU *,ushort const *)
0x18004d82d  mov     ebx, eax
0x18004d82f  test    eax, eax
0x18004d831  js      short loc_18004D88E
0x18004d833  lea     rdx, [rsp+7A0h+TokenHandle]; TokenHandle
0x18004d838  mov     rcx, rdi; hToken
0x18004d83b  call    ?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z; CONFIG_CACHE::Impersonate(void *,void * *)
0x18004d840  mov     ebx, eax
0x18004d842  test    eax, eax
0x18004d844  js      short loc_18004D88E
0x18004d846  lea     rcx, [rbp+6A0h+var_6F0]
0x18004d84a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004d850  xor     r8d, r8d; bFailIfExists
0x18004d853  mov     rdx, r14; lpNewFileName
0x18004d856  mov     rcx, rax; lpExistingFileName
0x18004d859  call    cs:__imp_CopyFileW
0x18004d85f  test    eax, eax
0x18004d861  jnz     short loc_18004D878
0x18004d863  call    cs:__imp_GetLastError
0x18004d869  mov     ebx, eax
0x18004d86b  test    eax, eax
0x18004d86d  jle     short loc_18004D878
0x18004d86f  movzx   ebx, ax
0x18004d872  or      ebx, 80070000h
0x18004d878  mov     rdx, [rsp+7A0h+TokenHandle]; void *
0x18004d87d  mov     rcx, rdi; void *
0x18004d880  call    ?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z; CONFIG_CACHE::Unimpersonate(void *,void *)
0x18004d885  test    eax, eax
0x18004d887  jns     short loc_18004D88E
0x18004d889  test    ebx, ebx
0x18004d88b  cmovns  ebx, eax
0x18004d88e  test    rdi, rdi
0x18004d891  jz      short loc_18004D89C
0x18004d893  mov     rcx, rdi; hObject
0x18004d896  call    cs:__imp_CloseHandle
0x18004d89c  mov     rcx, [rsp+7A0h+TokenHandle]; hObject
0x18004d8a1  test    rcx, rcx
0x18004d8a4  jz      short loc_18004D8B1
0x18004d8a6  call    cs:__imp_CloseHandle
0x18004d8ac  mov     [rsp+7A0h+TokenHandle], r15
0x18004d8b1  lea     rcx, [rbp+6A0h+var_640]; this
0x18004d8b5  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x18004d8ba  lea     rcx, [rsp+7A0h+var_730]; this
0x18004d8bf  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x18004d8c4  lea     rcx, [rbp+6A0h+var_6F0]
0x18004d8c8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004d8ce  lea     rcx, [rbp+6A0h+var_6B8]
0x18004d8d2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004d8d8  lea     rcx, [rbp+6A0h+var_680]
0x18004d8dc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004d8e2  mov     eax, ebx
0x18004d8e4  mov     rcx, [rbp+6A0h+var_30]
0x18004d8eb  xor     rcx, rsp; StackCookie
0x18004d8ee  call    __security_check_cookie
0x18004d8f3  mov     rbx, [rsp+7A0h+arg_18]
0x18004d8fb  add     rsp, 780h
0x18004d902  pop     r15
0x18004d904  pop     r14
0x18004d906  pop     rdi
0x18004d907  pop     rsi
0x18004d908  pop     rbp
0x18004d909  retn
```
