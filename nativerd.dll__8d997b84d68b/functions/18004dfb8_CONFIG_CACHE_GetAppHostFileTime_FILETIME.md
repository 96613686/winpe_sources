# CONFIG_CACHE::GetAppHostFileTime(_FILETIME *)

- ea: `0x18004dfb8`
- end: `0x18004e2cf`
- name: `?GetAppHostFileTime@CONFIG_CACHE@@QEAAJPEAU_FILETIME@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(CONFIG_CACHE *this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x18001e750`

## callees

- `0x1800012c0`
- `0x180003480`
- `0x180008d00`
- `0x180016440`
- `0x1800174d0`
- `0x18001753c`
- `0x180017a64`
- `0x1800412fc`
- `0x18004dfb8`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e21a`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004e210`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004e210`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e266`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e256`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004e266`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004e160`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x18004e160`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e28c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e296`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e2a0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e28c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e296`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004e2a0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e174`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e1ab`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e174`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18004e1ab`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e015`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e03e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e063`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e015`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e03e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18004e063`

## string_xrefs

- `0x18004e1ba`: `CONFIG_CACHE::GetAppHostFileTime`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::GetAppHostFileTime(CONFIG_CACHE *this, struct _FILETIME *a2)
{
  signed int appended; // ebx
  int v5; // eax
  HANDLE v6; // rdi
  const unsigned __int16 *Str; // rax
  const unsigned __int16 *v8; // rax
  HANDLE v9; // rax
  void *v10; // rsi
  signed int LastError; // eax
  signed int v12; // eax
  signed int v13; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v16; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v18[2]; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+80h] [rbp-80h]
  __int64 v20; // [rsp+88h] [rbp-78h]
  __int128 v21; // [rsp+90h] [rbp-70h]
  __int128 v22; // [rsp+A0h] [rbp-60h]
  _BYTE v23[56]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v24[56]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v25[64]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v26[3]; // [rsp+160h] [rbp+60h] BYREF
  int v27; // [rsp+178h] [rbp+78h]
  int v28; // [rsp+17Ch] [rbp+7Ch]
  int v29; // [rsp+180h] [rbp+80h]
  char v30; // [rsp+184h] [rbp+84h] BYREF
  unsigned __int16 v31[32]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v32[264]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v33[264]; // [rsp+560h] [rbp+460h] BYREF

  memset_0(v32, 0, 0x208u);
  STRU::STRU((STRU *)v25, v32, 0x104u);
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v24, v31, 0x20u);
  memset_0(v33, 0, 0x208u);
  STRU::STRU((STRU *)v23, v33, 0x104u);
  v29 &= 0xFFFFFFF0;
  v18[0] = &PARSE_ERROR_INFO::`vftable';
  v16 = 0;
  v26[0] = &v30;
  v18[1] = 1;
  v27 = -1;
  v28 = -1;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  hObject = 0;
  TokenHandle = 0;
  v26[1] = 0;
  v26[2] = 0;
  appended = PATH::Parse((PATH *)v26, L"MACHINE/WEBROOT/APPHOST");
  if ( appended >= 0 )
  {
    v5 = CONFIG_PATH_MAPPER::MapConfig(
           (CONFIG_CACHE *)((char *)this + 64),
           (struct PATH *)v26,
           2,
           0,
           (struct STRU *)v25,
           (struct STRU *)v24,
           &hObject,
           &v16,
           0,
           (struct PARSE_ERROR_INFO *)v18);
    v6 = hObject;
    appended = v5;
    if ( v5 >= 0 )
    {
      appended = STRU::Copy((STRU *)v23, (const struct STRU *)v25);
      if ( appended >= 0 )
      {
        Str = STRU::QueryStr((STRU *)v24);
        appended = CONFIG_PATH_MAPPER::AppendFileName((struct STRU *)v23, Str);
        if ( appended >= 0 )
        {
          appended = CONFIG_CACHE::Impersonate(v6, &TokenHandle);
          if ( appended >= 0 )
          {
            v8 = STRU::QueryStr((STRU *)v23);
            v9 = FILE_HELPER::CreateFileAndWriteEvent(
                   L"CONFIG_CACHE::GetAppHostFileTime",
                   v8,
                   0,
                   7,
                   3u,
                   0x80u,
                   (char *)0xFFFFFFFFFFFFFFFFLL);
            v10 = v9;
            if ( v9 == (HANDLE)-1LL )
            {
              LastError = GetLastError();
              appended = LastError;
              if ( LastError > 0 )
                appended = (unsigned __int16)LastError | 0x80070000;
            }
            else
            {
              if ( !GetFileTime(v9, 0, 0, a2) )
              {
                v12 = GetLastError();
                appended = v12;
                if ( v12 > 0 )
                  appended = (unsigned __int16)v12 | 0x80070000;
              }
              CloseHandle(v10);
            }
            v13 = CONFIG_CACHE::Unimpersonate(v6, TokenHandle);
            if ( v13 < 0 && appended >= 0 )
              appended = v13;
          }
        }
      }
    }
    if ( v6 )
      CloseHandle(v6);
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  PATH::Destroy((PATH *)v26);
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v18);
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004dfb8  mov     [rsp-8+arg_10], rbx
0x18004dfbd  mov     [rsp-8+arg_18], rsi
0x18004dfc2  push    rbp
0x18004dfc3  push    rdi
0x18004dfc4  push    r14
0x18004dfc6  lea     rbp, [rsp-680h]
0x18004dfce  sub     rsp, 780h
0x18004dfd5  mov     rax, cs:__security_cookie
0x18004dfdc  xor     rax, rsp
0x18004dfdf  mov     [rbp+690h+var_20], rax
0x18004dfe6  mov     r14, rdx
0x18004dfe9  mov     rdi, rcx
0x18004dfec  mov     esi, 208h
0x18004dff1  lea     rcx, [rbp+690h+var_440]; void *
0x18004dff8  mov     r8d, esi; Size
0x18004dffb  xor     edx, edx; Val
0x18004dffd  call    memset_0
0x18004e002  mov     ebx, 104h
0x18004e007  lea     rdx, [rbp+690h+var_440]
0x18004e00e  mov     r8d, ebx
0x18004e011  lea     rcx, [rbp+690h+var_670]
0x18004e015  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e01b  xor     edx, edx; Val
0x18004e01d  lea     rcx, [rbp+690h+var_480]; void *
0x18004e024  lea     r8d, [rdx+40h]; Size
0x18004e028  call    memset_0
0x18004e02d  mov     r8d, 20h ; ' '
0x18004e033  lea     rdx, [rbp+690h+var_480]
0x18004e03a  lea     rcx, [rbp+690h+var_6A8]
0x18004e03e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e044  mov     r8d, esi; Size
0x18004e047  lea     rcx, [rbp+690h+var_230]; void *
0x18004e04e  xor     edx, edx; Val
0x18004e050  call    memset_0
0x18004e055  mov     r8d, ebx
0x18004e058  lea     rdx, [rbp+690h+var_230]
0x18004e05f  lea     rcx, [rbp+690h+var_6E0]
0x18004e063  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18004e069  and     [rbp+690h+var_610], 0FFFFFFF0h
0x18004e070  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x18004e077  mov     [rsp+790h+var_720], rax
0x18004e07c  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18004e083  lea     rax, [rbp+690h+var_60C]
0x18004e08a  mov     [rsp+790h+var_738], 0
0x18004e092  mov     [rbp+690h+var_630], rax
0x18004e096  lea     rcx, [rbp+690h+var_630]; this
0x18004e09a  or      eax, 0FFFFFFFFh
0x18004e09d  mov     [rsp+790h+var_718], 1
0x18004e0a6  xorps   xmm0, xmm0
0x18004e0a9  mov     [rbp+690h+var_618], eax
0x18004e0ac  xorps   xmm1, xmm1
0x18004e0af  mov     [rbp+690h+var_614], eax
0x18004e0b2  mov     [rbp+690h+var_710], 0
0x18004e0b9  mov     [rbp+690h+var_708], 0
0x18004e0c1  movdqa  [rbp+690h+var_700], xmm0
0x18004e0c6  movdqa  [rbp+690h+var_6F0], xmm1
0x18004e0cb  mov     [rsp+790h+hObject], 0
0x18004e0d4  mov     [rsp+790h+TokenHandle], 0
0x18004e0dd  mov     [rbp+690h+var_628], 0
0x18004e0e5  mov     [rbp+690h+var_620], 0
0x18004e0ed  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x18004e0f2  mov     ebx, eax
0x18004e0f4  test    eax, eax
0x18004e0f6  js      loc_18004E25C
0x18004e0fc  lea     rax, [rsp+790h+var_720]
0x18004e101  xor     r9d, r9d; struct _PATH_CACHE_NODE *
0x18004e104  mov     [rsp+790h+var_748], rax; struct PARSE_ERROR_INFO *
0x18004e109  lea     rcx, [rdi+40h]; this
0x18004e10d  mov     [rsp+790h+var_750], 0; struct CONFIG_VDIR **
0x18004e116  lea     rax, [rsp+790h+var_738]
0x18004e11b  mov     [rsp+790h+var_758], rax; unsigned int *
0x18004e120  lea     rdx, [rbp+690h+var_630]; struct PATH *
0x18004e124  lea     rax, [rsp+790h+hObject]
0x18004e129  mov     [rsp+790h+var_760], rax; void **
0x18004e12e  lea     r8d, [r9+2]; unsigned int
0x18004e132  lea     rax, [rbp+690h+var_6A8]
0x18004e136  mov     [rsp+790h+var_768], rax; struct STRU *
0x18004e13b  lea     rax, [rbp+690h+var_670]
0x18004e13f  mov     [rsp+790h+var_770], rax; struct STRU *
0x18004e144  call    ?MapConfig@CONFIG_PATH_MAPPER@@QEAAJPEAVPATH@@KPEAU_PATH_CACHE_NODE@@PEAVSTRU@@2PEAPEAXPEAKPEAPEAVCONFIG_VDIR@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_PATH_MAPPER::MapConfig(PATH *,ulong,_PATH_CACHE_NODE *,STRU *,STRU *,void * *,ulong *,CONFIG_VDIR * *,PARSE_ERROR_INFO *)
0x18004e149  mov     rdi, [rsp+790h+hObject]
0x18004e14e  mov     ebx, eax
0x18004e150  test    eax, eax
0x18004e152  js      loc_18004E24E
0x18004e158  lea     rdx, [rbp+690h+var_670]
0x18004e15c  lea     rcx, [rbp+690h+var_6E0]
0x18004e160  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x18004e166  mov     ebx, eax
0x18004e168  test    eax, eax
0x18004e16a  js      loc_18004E24E
0x18004e170  lea     rcx, [rbp+690h+var_6A8]
0x18004e174  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004e17a  mov     rdx, rax; unsigned __int16 *
0x18004e17d  lea     rcx, [rbp+690h+var_6E0]; struct STRU *
0x18004e181  call    ?AppendFileName@CONFIG_PATH_MAPPER@@SAJPEAVSTRU@@PEBG@Z; CONFIG_PATH_MAPPER::AppendFileName(STRU *,ushort const *)
0x18004e186  mov     ebx, eax
0x18004e188  test    eax, eax
0x18004e18a  js      loc_18004E24E
0x18004e190  lea     rdx, [rsp+790h+TokenHandle]; TokenHandle
0x18004e195  mov     rcx, rdi; hToken
0x18004e198  call    ?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z; CONFIG_CACHE::Impersonate(void *,void * *)
0x18004e19d  mov     ebx, eax
0x18004e19f  test    eax, eax
0x18004e1a1  js      loc_18004E24E
0x18004e1a7  lea     rcx, [rbp+690h+var_6E0]
0x18004e1ab  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004e1b1  mov     [rsp+790h+var_760], 0FFFFFFFFFFFFFFFFh; void *
0x18004e1ba  lea     rcx, aConfigCacheGet; "CONFIG_CACHE::GetAppHostFileTime"
0x18004e1c1  mov     rdx, rax; unsigned __int16 *
0x18004e1c4  mov     dword ptr [rsp+790h+var_768], 80h; unsigned int
0x18004e1cc  mov     r9d, 7; unsigned int
0x18004e1d2  mov     dword ptr [rsp+790h+var_770], 3; unsigned int
0x18004e1da  mov     r8d, 80000000h; unsigned int
0x18004e1e0  call    ?CreateFileAndWriteEvent@FILE_HELPER@@SAPEAXPEBG0KKKKPEAX@Z; FILE_HELPER::CreateFileAndWriteEvent(ushort const *,ushort const *,ulong,ulong,ulong,ulong,void *)
0x18004e1e5  mov     rsi, rax
0x18004e1e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004e1ec  jnz     short loc_18004E205
0x18004e1ee  call    cs:__imp_GetLastError
0x18004e1f4  mov     ebx, eax
0x18004e1f6  test    eax, eax
0x18004e1f8  jle     short loc_18004E238
0x18004e1fa  movzx   ebx, ax
0x18004e1fd  or      ebx, 80070000h
0x18004e203  jmp     short loc_18004E238
0x18004e205  mov     r9, r14; lpLastWriteTime
0x18004e208  xor     r8d, r8d; lpLastAccessTime
0x18004e20b  xor     edx, edx; lpCreationTime
0x18004e20d  mov     rcx, rsi; hFile
0x18004e210  call    cs:__imp_GetFileTime
0x18004e216  test    eax, eax
0x18004e218  jnz     short loc_18004E22F
0x18004e21a  call    cs:__imp_GetLastError
0x18004e220  mov     ebx, eax
0x18004e222  test    eax, eax
0x18004e224  jle     short loc_18004E22F
0x18004e226  movzx   ebx, ax
0x18004e229  or      ebx, 80070000h
0x18004e22f  mov     rcx, rsi; hObject
0x18004e232  call    cs:__imp_CloseHandle
0x18004e238  mov     rdx, [rsp+790h+TokenHandle]; void *
0x18004e23d  mov     rcx, rdi; void *
0x18004e240  call    ?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z; CONFIG_CACHE::Unimpersonate(void *,void *)
0x18004e245  test    eax, eax
0x18004e247  jns     short loc_18004E24E
0x18004e249  test    ebx, ebx
0x18004e24b  cmovns  ebx, eax
0x18004e24e  test    rdi, rdi
0x18004e251  jz      short loc_18004E25C
0x18004e253  mov     rcx, rdi; hObject
0x18004e256  call    cs:__imp_CloseHandle
0x18004e25c  mov     rcx, [rsp+790h+TokenHandle]; hObject
0x18004e261  test    rcx, rcx
0x18004e264  jz      short loc_18004E275
0x18004e266  call    cs:__imp_CloseHandle
0x18004e26c  mov     [rsp+790h+TokenHandle], 0
0x18004e275  lea     rcx, [rbp+690h+var_630]; this
0x18004e279  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x18004e27e  lea     rcx, [rsp+790h+var_720]; this
0x18004e283  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x18004e288  lea     rcx, [rbp+690h+var_6E0]
0x18004e28c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e292  lea     rcx, [rbp+690h+var_6A8]
0x18004e296  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e29c  lea     rcx, [rbp+690h+var_670]
0x18004e2a0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18004e2a6  mov     eax, ebx
0x18004e2a8  mov     rcx, [rbp+690h+var_20]
0x18004e2af  xor     rcx, rsp; StackCookie
0x18004e2b2  call    __security_check_cookie
0x18004e2b7  lea     r11, [rsp+790h+var_10]
0x18004e2bf  mov     rbx, [r11+30h]
0x18004e2c3  mov     rsi, [r11+38h]
0x18004e2c7  mov     rsp, r11
0x18004e2ca  pop     r14
0x18004e2cc  pop     rdi
0x18004e2cd  pop     rbp
0x18004e2ce  retn
```
