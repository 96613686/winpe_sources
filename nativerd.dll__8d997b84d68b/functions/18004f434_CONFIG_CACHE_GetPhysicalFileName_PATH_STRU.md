# CONFIG_CACHE::GetPhysicalFileName(PATH *,STRU *)

- ea: `0x18004f434`
- end: `0x18004f5f9`
- name: `?GetPhysicalFileName@CONFIG_CACHE@@QEAAJPEAVPATH@@PEAVSTRU@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(CONFIG_CACHE *__hidden this, struct PATH *, struct STRU *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18003ada4`

## callees

- `0x180003440`
- `0x180008d00`
- `0x180015230`
- `0x180017490`
- `0x18004f434`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18004f5c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004f5cf`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004f5c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004f5cf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004f56a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004f58b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004f56a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004f58b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004f48e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004f4b9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004f48e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004f4b9`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004f55b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004f578`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004f55b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18004f578`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004f5a1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004f5a1`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18004f54c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18004f54c`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18004f5b2`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18004f5b2`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::GetPhysicalFileName(CONFIG_CACHE *this, struct PATH *a2, struct STRU *a3)
{
  unsigned __int16 *Str; // rbx
  struct _PATH_CACHE_NODE *v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[56]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v10[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v11[264]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v12[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v8 = 0;
  memset_0(v11, 0, 0x208u);
  STRU::STRU((STRU *)v9, v11, 0x104u);
  memset_0(v12, 0, 0x208u);
  STRU::STRU((STRU *)v10, v12, 0x104u);
  if ( a2 && a3 )
  {
    CONFIG_CACHE::ReadLock(this);
    if ( (int)CONFIG_CACHE::CacheLookup(this, a2, &v8) >= 0
      && (int)CONFIG_PATH_MAPPER::MapConfig(
                (CONFIG_CACHE *)((char *)this + 64),
                a2,
                *((_DWORD *)a2 + 6) - 1,
                v8,
                (struct STRU *)v9,
                (struct STRU *)v10,
                0,
                0,
                0,
                0) >= 0
      && (int)STRU::Copy(a3, (const struct STRU *)v9) >= 0 )
    {
      if ( STRU::QueryCCH((STRU *)v9) && (Str = STRU::QueryStr((STRU *)v9), Str[STRU::QueryCCH((STRU *)v9) - 1] == 92)
        || *STRU::QueryStr((STRU *)v10) == 92
        || (int)STRU::Append(a3, L"\\") >= 0 )
      {
        STRU::Append(a3, (const struct STRU *)v10);
      }
    }
    CONFIG_CACHE::ReadUnlock(this);
  }
  STRU::~STRU((STRU *)v10);
  STRU::~STRU((STRU *)v9);
  return 0;
}

```

## disassembly

```asm
0x18004f434  mov     [rsp-8+arg_18], rbx
0x18004f439  push    rbp
0x18004f43a  push    rsi
0x18004f43b  push    rdi
0x18004f43c  lea     rbp, [rsp-400h]
0x18004f444  sub     rsp, 500h
0x18004f44b  mov     rax, cs:__security_cookie
0x18004f452  xor     rax, rsp
0x18004f455  mov     [rbp+410h+var_20], rax
0x18004f45c  mov     rdi, r8
0x18004f45f  mov     [rsp+510h+var_4C0], 0
0x18004f468  mov     rbx, rdx
0x18004f46b  mov     rsi, rcx
0x18004f46e  xor     edx, edx; Val
0x18004f470  lea     rcx, [rbp+410h+var_440]; void *
0x18004f474  mov     r8d, 208h; Size
0x18004f47a  call    memset_0
0x18004f47f  mov     r8d, 104h
0x18004f485  lea     rdx, [rbp+410h+var_440]
0x18004f489  lea     rcx, [rsp+510h+var_4B8]
0x18004f48e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004f494  xor     edx, edx; Val
0x18004f496  lea     rcx, [rbp+410h+var_230]; void *
0x18004f49d  mov     r8d, 208h; Size
0x18004f4a3  call    memset_0
0x18004f4a8  mov     r8d, 104h
0x18004f4ae  lea     rdx, [rbp+410h+var_230]
0x18004f4b5  lea     rcx, [rbp+410h+var_480]
0x18004f4b9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004f4bf  test    rbx, rbx
0x18004f4c2  jz      loc_18004F5C0
0x18004f4c8  test    rdi, rdi
0x18004f4cb  jz      loc_18004F5C0
0x18004f4d1  mov     rcx, rsi; this
0x18004f4d4  call    ?ReadLock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::ReadLock(void)
0x18004f4d9  lea     r8, [rsp+510h+var_4C0]; struct _PATH_CACHE_NODE **
0x18004f4de  mov     rdx, rbx; struct PATH *
0x18004f4e1  mov     rcx, rsi; this
0x18004f4e4  call    ?CacheLookup@CONFIG_CACHE@@AEAAJPEAVPATH@@PEAPEAU_PATH_CACHE_NODE@@@Z; CONFIG_CACHE::CacheLookup(PATH *,_PATH_CACHE_NODE * *)
0x18004f4e9  test    eax, eax
0x18004f4eb  js      loc_18004F5B8
0x18004f4f1  mov     r8d, [rbx+18h]
0x18004f4f5  lea     rax, [rbp+410h+var_480]
0x18004f4f9  mov     r9, [rsp+510h+var_4C0]; struct _PATH_CACHE_NODE *
0x18004f4fe  lea     rcx, [rsi+40h]; this
0x18004f502  mov     [rsp+510h+var_4C8], 0; struct PARSE_ERROR_INFO *
0x18004f50b  dec     r8d; unsigned int
0x18004f50e  mov     [rsp+510h+var_4D0], 0; struct CONFIG_VDIR **
0x18004f517  mov     rdx, rbx; struct PATH *
0x18004f51a  mov     [rsp+510h+var_4D8], 0; unsigned int *
0x18004f523  mov     [rsp+510h+var_4E0], 0; void **
0x18004f52c  mov     [rsp+510h+var_4E8], rax; struct STRU *
0x18004f531  lea     rax, [rsp+510h+var_4B8]
0x18004f536  mov     [rsp+510h+var_4F0], rax; struct STRU *
0x18004f53b  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x18004f540  test    eax, eax
0x18004f542  js      short loc_18004F5B8
0x18004f544  lea     rdx, [rsp+510h+var_4B8]
0x18004f549  mov     rcx, rdi
0x18004f54c  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18004f552  test    eax, eax
0x18004f554  js      short loc_18004F5B8
0x18004f556  lea     rcx, [rsp+510h+var_4B8]
0x18004f55b  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004f561  test    eax, eax
0x18004f563  jz      short loc_18004F587
0x18004f565  lea     rcx, [rsp+510h+var_4B8]
0x18004f56a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004f570  lea     rcx, [rsp+510h+var_4B8]
0x18004f575  mov     rbx, rax
0x18004f578  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004f57e  dec     eax
0x18004f580  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x18004f585  jz      short loc_18004F5AB
0x18004f587  lea     rcx, [rbp+410h+var_480]
0x18004f58b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004f591  cmp     word ptr [rax], 5Ch ; '\'
0x18004f595  jz      short loc_18004F5AB
0x18004f597  lea     rdx, asc_18005F940; "\\"
0x18004f59e  mov     rcx, rdi
0x18004f5a1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18004f5a7  test    eax, eax
0x18004f5a9  js      short loc_18004F5B8
0x18004f5ab  lea     rdx, [rbp+410h+var_480]
0x18004f5af  mov     rcx, rdi
0x18004f5b2  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18004f5b8  mov     rcx, rsi; this
0x18004f5bb  call    ?ReadUnlock@CONFIG_CACHE@@AEAAXXZ; CONFIG_CACHE::ReadUnlock(void)
0x18004f5c0  lea     rcx, [rbp+410h+var_480]
0x18004f5c4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004f5ca  lea     rcx, [rsp+510h+var_4B8]
0x18004f5cf  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004f5d5  xor     eax, eax
0x18004f5d7  mov     rcx, [rbp+410h+var_20]
0x18004f5de  xor     rcx, rsp; StackCookie
0x18004f5e1  call    __security_check_cookie
0x18004f5e6  mov     rbx, [rsp+510h+arg_18]
0x18004f5ee  add     rsp, 500h
0x18004f5f5  pop     rdi
0x18004f5f6  pop     rsi
0x18004f5f7  pop     rbp
0x18004f5f8  retn
```
