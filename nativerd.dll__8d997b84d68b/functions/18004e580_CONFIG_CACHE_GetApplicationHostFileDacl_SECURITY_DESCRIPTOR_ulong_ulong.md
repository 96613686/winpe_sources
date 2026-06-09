# CONFIG_CACHE::GetApplicationHostFileDacl(_SECURITY_DESCRIPTOR *,ulong,ulong *)

- ea: `0x18004e580`
- end: `0x18004e81a`
- name: `?GetApplicationHostFileDacl@CONFIG_CACHE@@QEAAJPEAU_SECURITY_DESCRIPTOR@@KPEAK@Z`
- size: `666`
- prototype: `int(CONFIG_CACHE *__hidden this, struct _SECURITY_DESCRIPTOR *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e740`

## callees

- `0x1800012c0`
- `0x180003480`
- `0x180008d00`
- `0x180016440`
- `0x1800174d0`
- `0x18001753c`
- `0x180017a64`
- `0x18004e580`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e778`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e7bb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004e76e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x18004e76e`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004e712`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004e712`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7dd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7dd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e7f1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e726`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e755`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e726`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e755`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e5e1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e60a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e62f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e5e1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e60a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e62f`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::GetApplicationHostFileDacl(
        CONFIG_CACHE *this,
        struct _SECURITY_DESCRIPTOR *a2,
        DWORD a3,
        unsigned int *a4)
{
  int appended; // ebx
  int v9; // eax
  HANDLE v10; // rdi
  const unsigned __int16 *Str; // rax
  const WCHAR *v12; // rax
  signed int LastError; // eax
  signed int v14; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v17; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[2]; // [rsp+70h] [rbp-90h] BYREF
  int v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  _BYTE v24[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[56]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v26[64]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v27[3]; // [rsp+160h] [rbp+60h] BYREF
  int v28; // [rsp+178h] [rbp+78h]
  int v29; // [rsp+17Ch] [rbp+7Ch]
  int v30; // [rsp+180h] [rbp+80h]
  char v31; // [rsp+184h] [rbp+84h] BYREF
  unsigned __int16 v32[32]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v33[264]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v34[264]; // [rsp+560h] [rbp+460h] BYREF

  memset_0(v33, 0, 0x208u);
  STRU::STRU((STRU *)v26, v33, 0x104u);
  memset_0(v32, 0, sizeof(v32));
  STRU::STRU((STRU *)v25, v32, 0x20u);
  memset_0(v34, 0, 0x208u);
  STRU::STRU((STRU *)v24, v34, 0x104u);
  v30 &= 0xFFFFFFF0;
  v19[0] = &PARSE_ERROR_INFO::`vftable';
  v17 = 0;
  v27[0] = &v31;
  v19[1] = 1;
  v28 = -1;
  v29 = -1;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  hObject = 0;
  TokenHandle = 0;
  v27[1] = 0;
  v27[2] = 0;
  appended = PATH::Parse((PATH *)v27, L"MACHINE/WEBROOT/APPHOST");
  if ( appended >= 0 )
  {
    v9 = CONFIG_PATH_MAPPER::MapConfig(
           (CONFIG_CACHE *)((char *)this + 64),
           (struct PATH *)v27,
           2,
           0,
           (struct STRU *)v26,
           (struct STRU *)v25,
           &hObject,
           &v17,
           0,
           (struct PARSE_ERROR_INFO *)v19);
    v10 = hObject;
    appended = v9;
    if ( v9 >= 0 )
    {
      appended = STRU::Copy((STRU *)v24, (const struct STRU *)v26);
      if ( appended >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v25);
        appended = CONFIG_PATH_MAPPER::AppendFileName((struct STRU *)v24, Str);
        if ( appended >= 0 )
        {
          appended = CONFIG_CACHE::Impersonate(v10, &TokenHandle);
          if ( appended >= 0 )
          {
            v12 = STRU::QueryStr((STRU *)v24);
            if ( !GetFileSecurityW(v12, 7u, a2, a3, a4) )
            {
              LastError = GetLastError();
              appended = LastError;
              if ( LastError > 0 )
                appended = (unsigned __int16)LastError | 0x80070000;
            }
            v14 = CONFIG_CACHE::Unimpersonate(v10, TokenHandle);
            if ( v14 < 0 && appended >= 0 )
              appended = v14;
          }
        }
      }
    }
    if ( v10 )
      CloseHandle(v10);
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  PATH::Destroy((PATH *)v27);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v19);
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004e580  push    rbp
0x18004e582  push    rbx
0x18004e583  push    rsi
0x18004e584  push    rdi
0x18004e585  push    r12
0x18004e587  push    r14
0x18004e589  push    r15
0x18004e58b  lea     rbp, [rsp-680h]
0x18004e593  sub     rsp, 780h
0x18004e59a  mov     rax, cs:__security_cookie
0x18004e5a1  xor     rax, rsp
0x18004e5a4  mov     [rbp+6B0h+var_40], rax
0x18004e5ab  mov     r14d, r8d
0x18004e5ae  mov     rsi, rdx
0x18004e5b1  mov     rdi, rcx
0x18004e5b4  mov     r12d, 208h
0x18004e5ba  mov     r8d, r12d; Size
0x18004e5bd  lea     rcx, [rbp+6B0h+var_460]; void *
0x18004e5c4  xor     edx, edx; Val
0x18004e5c6  mov     r15, r9
0x18004e5c9  call    memset_0
0x18004e5ce  mov     ebx, 104h
0x18004e5d3  lea     rdx, [rbp+6B0h+var_460]
0x18004e5da  mov     r8d, ebx
0x18004e5dd  lea     rcx, [rbp+6B0h+var_690]
0x18004e5e1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e5e7  xor     edx, edx; Val
0x18004e5e9  lea     rcx, [rbp+6B0h+var_4A0]; void *
0x18004e5f0  lea     r8d, [rdx+40h]; Size
0x18004e5f4  call    memset_0
0x18004e5f9  mov     r8d, 20h ; ' '
0x18004e5ff  lea     rdx, [rbp+6B0h+var_4A0]
0x18004e606  lea     rcx, [rbp+6B0h+var_6C8]
0x18004e60a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e610  mov     r8d, r12d; Size
0x18004e613  lea     rcx, [rbp+6B0h+var_250]; void *
0x18004e61a  xor     edx, edx; Val
0x18004e61c  call    memset_0
0x18004e621  mov     r8d, ebx
0x18004e624  lea     rdx, [rbp+6B0h+var_250]
0x18004e62b  lea     rcx, [rbp+6B0h+var_700]
0x18004e62f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e635  and     [rbp+6B0h+var_630], 0FFFFFFF0h
0x18004e63c  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18004e643  xor     r12d, r12d
0x18004e646  mov     [rsp+7B0h+var_740], rax
0x18004e64b  lea     rax, [rbp+6B0h+var_62C]
0x18004e652  mov     [rsp+7B0h+var_758], r12d
0x18004e657  mov     [rbp+6B0h+var_650], rax
0x18004e65b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18004e662  or      eax, 0FFFFFFFFh
0x18004e665  mov     [rsp+7B0h+var_738], 1
0x18004e66e  xorps   xmm0, xmm0
0x18004e671  mov     [rbp+6B0h+var_638], eax
0x18004e674  xorps   xmm1, xmm1
0x18004e677  mov     [rbp+6B0h+var_634], eax
0x18004e67a  lea     rcx, [rbp+6B0h+var_650]; this
0x18004e67e  mov     [rbp+6B0h+var_730], r12d
0x18004e682  mov     [rbp+6B0h+var_728], r12
0x18004e686  movdqa  [rbp+6B0h+var_720], xmm0
0x18004e68b  movdqa  [rbp+6B0h+var_710], xmm1
0x18004e690  mov     [rsp+7B0h+hObject], r12
0x18004e695  mov     [rsp+7B0h+TokenHandle], r12
0x18004e69a  mov     [rbp+6B0h+var_648], r12
0x18004e69e  mov     [rbp+6B0h+var_640], r12
0x18004e6a2  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x18004e6a7  mov     ebx, eax
0x18004e6a9  test    eax, eax
0x18004e6ab  js      loc_18004E7B1
0x18004e6b1  lea     rax, [rsp+7B0h+var_740]
0x18004e6b6  xor     r9d, r9d; struct _PATH_CACHE_NODE *
0x18004e6b9  mov     [rsp+7B0h+var_768], rax; struct PARSE_ERROR_INFO *
0x18004e6be  lea     rcx, [rdi+40h]; this
0x18004e6c2  mov     [rsp+7B0h+var_770], r12; struct CONFIG_VDIR **
0x18004e6c7  lea     rax, [rsp+7B0h+var_758]
0x18004e6cc  mov     [rsp+7B0h+var_778], rax; unsigned int *
0x18004e6d1  lea     r8d, [r12+2]; unsigned int
0x18004e6d6  lea     rax, [rsp+7B0h+hObject]
0x18004e6db  mov     [rsp+7B0h+var_780], rax; void **
0x18004e6e0  lea     rdx, [rbp+6B0h+var_650]; struct PATH *
0x18004e6e4  lea     rax, [rbp+6B0h+var_6C8]
0x18004e6e8  mov     [rsp+7B0h+var_788], rax; struct STRU *
0x18004e6ed  lea     rax, [rbp+6B0h+var_690]
0x18004e6f1  mov     [rsp+7B0h+lpnLengthNeeded], rax; struct STRU *
0x18004e6f6  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x18004e6fb  mov     rdi, [rsp+7B0h+hObject]
0x18004e700  mov     ebx, eax
0x18004e702  test    eax, eax
0x18004e704  js      loc_18004E7A3
0x18004e70a  lea     rdx, [rbp+6B0h+var_690]
0x18004e70e  lea     rcx, [rbp+6B0h+var_700]
0x18004e712  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x18004e718  mov     ebx, eax
0x18004e71a  test    eax, eax
0x18004e71c  js      loc_18004E7A3
0x18004e722  lea     rcx, [rbp+6B0h+var_6C8]
0x18004e726  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004e72c  mov     rdx, rax; unsigned __int16 *
0x18004e72f  lea     rcx, [rbp+6B0h+var_700]; struct STRU *
0x18004e733  call    ?AppendFileName@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@PEBG@Z; CONFIG_PATH_MAPPER::AppendFileName(STRU *,ushort const *)
0x18004e738  mov     ebx, eax
0x18004e73a  test    eax, eax
0x18004e73c  js      short loc_18004E7A3
0x18004e73e  lea     rdx, [rsp+7B0h+TokenHandle]; TokenHandle
0x18004e743  mov     rcx, rdi; hToken
0x18004e746  call    ?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z; CONFIG_CACHE::Impersonate(void *,void * *)
0x18004e74b  mov     ebx, eax
0x18004e74d  test    eax, eax
0x18004e74f  js      short loc_18004E7A3
0x18004e751  lea     rcx, [rbp+6B0h+var_700]
0x18004e755  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004e75b  mov     r9d, r14d; nLength
0x18004e75e  mov     [rsp+7B0h+lpnLengthNeeded], r15; lpnLengthNeeded
0x18004e763  mov     rcx, rax; lpFileName
0x18004e766  lea     edx, [r12+7]; RequestedInformation
0x18004e76b  mov     r8, rsi; pSecurityDescriptor
0x18004e76e  call    cs:__imp_GetFileSecurityW
0x18004e774  test    eax, eax
0x18004e776  jnz     short loc_18004E78D
0x18004e778  call    cs:__imp_GetLastError
0x18004e77e  mov     ebx, eax
0x18004e780  test    eax, eax
0x18004e782  jle     short loc_18004E78D
0x18004e784  movzx   ebx, ax
0x18004e787  or      ebx, 80070000h
0x18004e78d  mov     rdx, [rsp+7B0h+TokenHandle]; void *
0x18004e792  mov     rcx, rdi; void *
0x18004e795  call    ?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z; CONFIG_CACHE::Unimpersonate(void *,void *)
0x18004e79a  test    eax, eax
0x18004e79c  jns     short loc_18004E7A3
0x18004e79e  test    ebx, ebx
0x18004e7a0  cmovns  ebx, eax
0x18004e7a3  test    rdi, rdi
0x18004e7a6  jz      short loc_18004E7B1
0x18004e7a8  mov     rcx, rdi; hObject
0x18004e7ab  call    cs:__imp_CloseHandle
0x18004e7b1  mov     rcx, [rsp+7B0h+TokenHandle]; hObject
0x18004e7b6  test    rcx, rcx
0x18004e7b9  jz      short loc_18004E7C6
0x18004e7bb  call    cs:__imp_CloseHandle
0x18004e7c1  mov     [rsp+7B0h+TokenHandle], r12
0x18004e7c6  lea     rcx, [rbp+6B0h+var_650]; this
0x18004e7ca  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x18004e7cf  lea     rcx, [rsp+7B0h+var_740]; this
0x18004e7d4  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x18004e7d9  lea     rcx, [rbp+6B0h+var_700]
0x18004e7dd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e7e3  lea     rcx, [rbp+6B0h+var_6C8]
0x18004e7e7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e7ed  lea     rcx, [rbp+6B0h+var_690]
0x18004e7f1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e7f7  mov     eax, ebx
0x18004e7f9  mov     rcx, [rbp+6B0h+var_40]
0x18004e800  xor     rcx, rsp; StackCookie
0x18004e803  call    __security_check_cookie
0x18004e808  add     rsp, 780h
0x18004e80f  pop     r15
0x18004e811  pop     r14
0x18004e813  pop     r12
0x18004e815  pop     rdi
0x18004e816  pop     rsi
0x18004e817  pop     rbx
0x18004e818  pop     rbp
0x18004e819  retn
```
