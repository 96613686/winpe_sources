# CONFIG_FILE::LoadLocationTags(void)

- ea: `0x180027888`
- end: `0x180027d7e`
- name: `?LoadLocationTags@CONFIG_FILE@@AEAAJXZ`
- size: `1270`
- prototype: `__int64 __fastcall(CONFIG_FILE *__hidden this)`
- caller_count: `6`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180026250`
- `0x18002680c`
- `0x180026b24`
- `0x180026b90`
- `0x18002a1b0`
- `0x180054d3c`

## callees

- `0x180011b54`
- `0x180016440`
- `0x1800174d0`
- `0x18001753c`
- `0x180017610`
- `0x180018d88`
- `0x18001be64`
- `0x18001c250`
- `0x18002738c`
- `0x180027888`
- `0x180028608`
- `0x18004587c`
- `0x18004b060`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027c90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ca8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027d53`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180027d53`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180027ae3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180027ae3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800278fb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800278fb`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180027b53`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180027b53`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002795e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002795e`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027cc3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180027cc3`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::LoadLocationTags(CONFIG_FILE *this)
{
  int FileHandle; // ebx
  __int64 v3; // rsi
  READ_ONLY_DOM *v4; // rdi
  int v5; // r12d
  __int64 v6; // r13
  __int64 v7; // rax
  const unsigned __int16 *ParseErrorFileName; // rax
  const unsigned __int16 *v9; // rcx
  READ_ONLY_DOM *v10; // rax
  __int64 (__fastcall ***v11)(_QWORD, _BYTE *, _QWORD); // rcx
  const wchar_t *Str; // rax
  struct LOCATION_CONTEXT *v13; // rax
  struct LOCATION_CONTEXT *v14; // rsi
  struct IConfigDomNode *v15; // rbx
  unsigned __int16 *v16; // rax
  signed int v17; // eax
  void *v19; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  struct IConfigDomNode *v22; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v25)(_QWORD, _BYTE *, _QWORD); // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v27[2]; // [rsp+80h] [rbp-80h] BYREF
  int v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int128 v30; // [rsp+A0h] [rbp-60h]
  __int128 v31; // [rsp+B0h] [rbp-50h]
  _BYTE v32[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v33[64]; // [rsp+100h] [rbp+0h] BYREF

  FileHandle = 0;
  v3 = -1;
  hObject = 0;
  v19 = (void *)-1LL;
  v24 = 0;
  v21 = 0;
  v4 = 0;
  v22 = 0;
  v25 = 0;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v32, v33, 0x40u);
  v5 = 1;
  v27[0] = &PARSE_ERROR_INFO::`vftable';
  v26[0] = &CONFIG_DOM_ERROR::`vftable';
  v27[1] = 1;
  v6 = 0;
  v26[1] = v27;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( !*((_QWORD *)this + 25) )
  {
    v5 = 0;
    goto LABEL_38;
  }
  CReaderWriterLock3::WriteLock((CONFIG_FILE *)((char *)this + 344));
  v7 = *((_QWORD *)this + 25);
  if ( v7 )
  {
    *((_QWORD *)this + 25) = 0;
    v6 = v7;
    FileHandle = CONFIG_CACHE::Impersonate(*(HANDLE *)(v7 + 80), &hObject);
    if ( FileHandle >= 0 )
    {
      v20[0] = *(_DWORD *)(v6 + 72);
      ParseErrorFileName = CONFIG_FILE::QueryParseErrorFileName(this);
      v9 = &szDomain;
      if ( *((_QWORD *)this + 5) )
        v9 = (const unsigned __int16 *)*((_QWORD *)this + 5);
      FileHandle = CONFIG_CACHE::GetFileHandle(v9, v20, &v19, ParseErrorFileName, (struct PARSE_ERROR_INFO *)v27);
      if ( FileHandle >= 0 )
      {
        v10 = (READ_ONLY_DOM *)operator new(0x28u);
        v4 = v10;
        if ( v10 )
        {
          *((_QWORD *)v10 + 2) = 0;
          *(_QWORD *)v10 = &READ_ONLY_DOM::`vftable';
          *((_QWORD *)v10 + 3) = 0;
          *((_QWORD *)v10 + 4) = 0;
          *((_QWORD *)v10 + 1) = 1;
          v3 = (__int64)v19;
          FileHandle = READ_ONLY_DOM::ParseXmlFile(
                         v10,
                         v19,
                         (struct PARSE_ERROR_INFO *)v27,
                         *((_QWORD *)this + 38) != 0,
                         (unsigned int)(((int)(*((_DWORD *)this + 68) << 22) >> 28) - 1) > 2);
          if ( FileHandle < 0
            || (FileHandle = (*(__int64 (__fastcall **)(READ_ONLY_DOM *, __int64 *))(*(_QWORD *)v4 + 16LL))(v4, &v24),
                FileHandle < 0)
            || (FileHandle = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD *))(*(_QWORD *)v24 + 8LL))(
                               v24,
                               &v21,
                               v27),
                FileHandle < 0)
            || !*((_QWORD *)this + 19) && (FileHandle = CONFIG_FILE::GetSectionGroupTable(this), FileHandle < 0) )
          {
LABEL_35:
            v17 = CONFIG_CACHE::Unimpersonate(*(void **)(v6 + 80), hObject);
            if ( FileHandle >= 0 && v17 < 0 )
              FileHandle = v17;
            goto LABEL_38;
          }
          v11 = (__int64 (__fastcall ***)(_QWORD, _BYTE *, _QWORD))v21;
          while ( v11 )
          {
            FileHandle = (**v11)(v11, v32, 0);
            if ( FileHandle < 0 )
              goto LABEL_34;
            Str = STRU::QueryStr((STRU *)v32);
            if ( !wcscmp_0(Str, L"location") )
            {
              *(_QWORD *)v20 = 0;
              v13 = (struct LOCATION_CONTEXT *)operator new(0x20u);
              v14 = v13;
              if ( v13 )
              {
                *((_DWORD *)v13 + 1) &= 0xFFFFF000;
                *(_DWORD *)v13 = 1;
                *((_QWORD *)v13 + 1) = 0;
                *((_QWORD *)v13 + 2) = 0;
                *((_QWORD *)v13 + 3) = 0;
              }
              else
              {
                v14 = 0;
              }
              InvasivePtr<LOCATION_CONTEXT>::Reset(v20);
              *(_QWORD *)v20 = v14;
              if ( !v14 )
              {
                FileHandle = -2147024882;
LABEL_31:
                InvasivePtr<LOCATION_CONTEXT>::Reset(v20);
                goto LABEL_34;
              }
              v15 = (struct IConfigDomNode *)v21;
              v16 = (unsigned __int16 *)STRU::QueryStr((CONFIG_FILE *)((char *)this + 72));
              FileHandle = LOCATION_CONTEXT::InitializeFromDomNode(
                             (__int64)v14,
                             (int)(*((_DWORD *)this + 68) << 22) >> 28,
                             v16,
                             v15,
                             (CONFIG_DOM_ERROR *)v26);
              if ( FileHandle < 0 )
                goto LABEL_31;
              FileHandle = ((__int64 (__fastcall **)(_QWORD, struct IConfigDomNode **, _QWORD *))*v21)[1](
                             v21,
                             &v22,
                             v27);
              if ( FileHandle < 0 )
                goto LABEL_31;
              FileHandle = CONFIG_FILE::ParseLocation(
                             this,
                             v22,
                             v14,
                             0,
                             (struct CONFIG_DOM_ERROR *)v26,
                             *(_DWORD *)(v6 + 76));
              if ( FileHandle < 0 )
                goto LABEL_31;
              if ( v22 )
              {
                (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v22 + 120LL))(v22);
                v22 = 0;
              }
              InvasivePtr<LOCATION_CONTEXT>::Reset(v20);
            }
            FileHandle = ((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))*v21)[2](v21, &v25, v27);
            if ( FileHandle < 0 )
              goto LABEL_34;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[15])(v21);
            v11 = v25;
            v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
          }
          FileHandle = LOCATION_TABLE::SetReadOnly(*((LOCATION_TABLE **)this + 22));
        }
        else
        {
          FileHandle = -2147024888;
          v4 = 0;
        }
      }
LABEL_34:
      v3 = (__int64)v19;
      goto LABEL_35;
    }
  }
LABEL_38:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  if ( v6 )
    SCHEMA_FILE_LIST::DereferenceSchemaFileList((SCHEMA_FILE_LIST *)v6);
  if ( v5 )
    CReaderWriterLock3::WriteUnlock((CONFIG_FILE *)((char *)this + 344));
  if ( v22 )
  {
    (*(void (__fastcall **)(struct IConfigDomNode *))(*(_QWORD *)v22 + 120LL))(v22);
    v22 = 0;
  }
  if ( v21 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v21)[15])(v21);
    v21 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 120LL))(v24);
    v24 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(READ_ONLY_DOM *))(*(_QWORD *)v4 + 56LL))(v4);
  v26[0] = &CONFIG_DOM_ERROR::`vftable';
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)v27);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)FileHandle;
}

```

## disassembly

```asm
0x180027888  push    rbp
0x18002788a  push    rbx
0x18002788b  push    rsi
0x18002788c  push    rdi
0x18002788d  push    r12
0x18002788f  push    r13
0x180027891  push    r14
0x180027893  push    r15
0x180027895  lea     rbp, [rsp-98h]
0x18002789d  sub     rsp, 198h
0x1800278a4  mov     rax, cs:__security_cookie
0x1800278ab  xor     rax, rsp
0x1800278ae  mov     [rbp+0D0h+var_50], rax
0x1800278b5  xor     ebx, ebx
0x1800278b7  mov     r15, rcx
0x1800278ba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800278be  mov     [rsp+1D0h+hObject], rbx
0x1800278c3  lea     rcx, [rbp+0D0h+var_D0]; void *
0x1800278c7  mov     [rsp+1D0h+var_1A0], rsi
0x1800278cc  xor     edx, edx; Val
0x1800278ce  mov     [rsp+1D0h+var_178], rbx
0x1800278d3  mov     r8d, 80h; Size
0x1800278d9  mov     [rsp+1D0h+var_190], rbx
0x1800278de  mov     edi, ebx
0x1800278e0  mov     [rsp+1D0h+var_188], rbx
0x1800278e5  mov     [rsp+1D0h+var_170], rbx
0x1800278ea  call    memset_0
0x1800278ef  lea     r8d, [rbx+40h]
0x1800278f3  lea     rdx, [rbp+0D0h+var_D0]
0x1800278f7  lea     rcx, [rbp+0D0h+var_110]
0x1800278fb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180027901  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180027908  xorps   xmm0, xmm0
0x18002790b  lea     r12d, [rbx+1]
0x18002790f  mov     [rbp+0D0h+var_150], rax
0x180027913  lea     rax, ??_7CONFIG_DOM_ERROR@@6B@; const CONFIG_DOM_ERROR::`vftable'
0x18002791a  xorps   xmm1, xmm1
0x18002791d  lea     r14, [r15+158h]
0x180027924  mov     [rsp+1D0h+var_168], rax
0x180027929  lea     rax, [rbp+0D0h+var_150]
0x18002792d  mov     [rbp+0D0h+var_148], r12
0x180027931  mov     r13d, ebx
0x180027934  mov     [rsp+1D0h+var_160], rax
0x180027939  mov     [rbp+0D0h+var_140], ebx
0x18002793c  mov     [rbp+0D0h+var_138], rbx
0x180027940  movdqa  [rbp+0D0h+var_130], xmm0
0x180027945  movdqa  [rbp+0D0h+var_120], xmm1
0x18002794a  cmp     [r15+0C8h], rbx
0x180027951  jnz     short loc_18002795B
0x180027953  mov     r12d, ebx
0x180027956  jmp     loc_180027C86
0x18002795b  mov     rcx, r14
0x18002795e  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180027964  mov     rax, [r15+0C8h]
0x18002796b  test    rax, rax
0x18002796e  jz      loc_180027C86
0x180027974  mov     [r15+0C8h], rbx
0x18002797b  lea     rdx, [rsp+1D0h+hObject]; TokenHandle
0x180027980  mov     rcx, [rax+50h]; hToken
0x180027984  mov     r13, rax
0x180027987  call    ?Impersonate@CONFIG_CACHE@@SAJPEAXPEAPEAX@Z; CONFIG_CACHE::Impersonate(void *,void * *)
0x18002798c  mov     ebx, eax
0x18002798e  test    eax, eax
0x180027990  js      loc_180027C86
0x180027996  mov     eax, [r13+48h]
0x18002799a  mov     rcx, r15; this
0x18002799d  mov     [rsp+1D0h+var_198], eax
0x1800279a1  call    ?QueryParseErrorFileName@CONFIG_FILE@@QEBAPEBGXZ; CONFIG_FILE::QueryParseErrorFileName(void)
0x1800279a6  lea     rdx, [rbp+0D0h+var_150]
0x1800279aa  xor     esi, esi
0x1800279ac  cmp     [r15+28h], rsi
0x1800279b0  lea     rcx, szDomain
0x1800279b7  mov     [rsp+1D0h+var_1B0], rdx; struct PARSE_ERROR_INFO *
0x1800279bc  lea     r8, [rsp+1D0h+var_1A0]; void **
0x1800279c1  cmovnz  rcx, [r15+28h]; unsigned __int16 *
0x1800279c6  lea     rdx, [rsp+1D0h+var_198]; unsigned int *
0x1800279cb  mov     r9, rax; unsigned __int16 *
0x1800279ce  call    ?GetFileHandle@CONFIG_CACHE@@SAJPEBGPEAKPEAPEAX0PEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::GetFileHandle(ushort const *,ulong *,void * *,ushort const *,PARSE_ERROR_INFO *)
0x1800279d3  mov     ebx, eax
0x1800279d5  test    eax, eax
0x1800279d7  js      loc_180027C69
0x1800279dd  lea     ecx, [rsi+28h]; Size
0x1800279e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800279e5  mov     rdi, rax
0x1800279e8  test    rax, rax
0x1800279eb  jz      loc_180027C61
0x1800279f1  mov     [rdi+10h], rsi
0x1800279f5  lea     rax, ??_7READ_ONLY_DOM@@6B@; const READ_ONLY_DOM::`vftable'
0x1800279fc  mov     [rdi], rax
0x1800279ff  lea     r8, [rbp+0D0h+var_150]
0x180027a03  mov     rax, [rax+8]
0x180027a07  mov     edx, esi
0x180027a09  mov     [rdi+18h], rsi
0x180027a0d  mov     r9d, esi
0x180027a10  mov     [rdi+20h], rsi
0x180027a14  mov     [rdi+8], r12
0x180027a18  mov     ecx, [r15+110h]
0x180027a1f  shl     ecx, 16h
0x180027a22  sar     ecx, 1Ch
0x180027a25  sub     ecx, r12d
0x180027a28  cmp     ecx, 2
0x180027a2b  mov     rcx, rdi
0x180027a2e  setnbe  dl
0x180027a31  cmp     [r15+130h], rsi
0x180027a38  mov     rsi, [rsp+1D0h+var_1A0]
0x180027a3d  mov     dword ptr [rsp+1D0h+var_1B0], edx
0x180027a41  setnz   r9b
0x180027a45  mov     rdx, rsi
0x180027a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a4d  mov     ebx, eax
0x180027a4f  test    eax, eax
0x180027a51  js      loc_180027C6E
0x180027a57  mov     rax, [rdi]
0x180027a5a  lea     rdx, [rsp+1D0h+var_178]
0x180027a5f  mov     rcx, rdi
0x180027a62  mov     rax, [rax+10h]
0x180027a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a6b  mov     ebx, eax
0x180027a6d  test    eax, eax
0x180027a6f  js      loc_180027C6E
0x180027a75  mov     rcx, [rsp+1D0h+var_178]
0x180027a7a  lea     r8, [rbp+0D0h+var_150]
0x180027a7e  lea     rdx, [rsp+1D0h+var_190]
0x180027a83  mov     rax, [rcx]
0x180027a86  mov     rax, [rax+8]
0x180027a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a8f  mov     ebx, eax
0x180027a91  test    eax, eax
0x180027a93  js      loc_180027C6E
0x180027a99  cmp     qword ptr [r15+98h], 0
0x180027aa1  jnz     short loc_180027AB5
0x180027aa3  mov     rcx, r15; this
0x180027aa6  call    ?GetSectionGroupTable@CONFIG_FILE@@AEAAJXZ; CONFIG_FILE::GetSectionGroupTable(void)
0x180027aab  mov     ebx, eax
0x180027aad  test    eax, eax
0x180027aaf  js      loc_180027C6E
0x180027ab5  mov     rcx, [rsp+1D0h+var_190]
0x180027aba  test    rcx, rcx
0x180027abd  jz      loc_180027C51
0x180027ac3  mov     rax, [rcx]
0x180027ac6  lea     rdx, [rbp+0D0h+var_110]
0x180027aca  xor     r8d, r8d
0x180027acd  mov     rax, [rax]
0x180027ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ad5  mov     ebx, eax
0x180027ad7  test    eax, eax
0x180027ad9  js      loc_180027C69
0x180027adf  lea     rcx, [rbp+0D0h+var_110]
0x180027ae3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180027ae9  mov     rcx, rax; String1
0x180027aec  lea     rdx, aLocation; "location"
0x180027af3  call    wcscmp_0
0x180027af8  xor     ebx, ebx
0x180027afa  test    eax, eax
0x180027afc  jnz     loc_180027C00
0x180027b02  lea     ecx, [rbx+20h]; Size
0x180027b05  mov     qword ptr [rsp+1D0h+var_198], rbx
0x180027b0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027b0f  mov     rsi, rax
0x180027b12  test    rax, rax
0x180027b15  jz      short loc_180027B2F
0x180027b17  and     dword ptr [rax+4], 0FFFFF000h
0x180027b1e  mov     [rax], r12d
0x180027b21  mov     [rax+8], rbx
0x180027b25  mov     [rax+10h], rbx
0x180027b29  mov     [rax+18h], rbx
0x180027b2d  jmp     short loc_180027B32
0x180027b2f  mov     rsi, rbx
0x180027b32  lea     rcx, [rsp+1D0h+var_198]
0x180027b37  call    ?Reset@?$InvasivePtr@VLOCATION_CONTEXT@@@@QEAAXXZ; InvasivePtr<LOCATION_CONTEXT>::Reset(void)
0x180027b3c  mov     qword ptr [rsp+1D0h+var_198], rsi
0x180027b41  test    rsi, rsi
0x180027b44  jz      loc_180027C40
0x180027b4a  mov     rbx, [rsp+1D0h+var_190]
0x180027b4f  lea     rcx, [r15+48h]
0x180027b53  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180027b59  mov     edx, [r15+110h]
0x180027b60  lea     rcx, [rsp+1D0h+var_168]
0x180027b65  shl     edx, 16h
0x180027b68  mov     r9, rbx
0x180027b6b  mov     [rsp+1D0h+var_1B0], rcx
0x180027b70  mov     r8, rax
0x180027b73  sar     edx, 1Ch
0x180027b76  mov     rcx, rsi
0x180027b79  call    ?InitializeFromDomNode@LOCATION_CONTEXT@@QEAAJW4_ALLOW_DEFINITION_LEVEL@@PEBGPEAVIConfigDomNode@@PEAVCONFIG_DOM_ERROR@@@Z; LOCATION_CONTEXT::InitializeFromDomNode(_ALLOW_DEFINITION_LEVEL,ushort const *,IConfigDomNode *,CONFIG_DOM_ERROR *)
0x180027b7e  mov     ebx, eax
0x180027b80  test    eax, eax
0x180027b82  js      loc_180027C45
0x180027b88  mov     rcx, [rsp+1D0h+var_190]
0x180027b8d  lea     r8, [rbp+0D0h+var_150]
0x180027b91  lea     rdx, [rsp+1D0h+var_188]
0x180027b96  mov     rax, [rcx]
0x180027b99  mov     rax, [rax+8]
0x180027b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ba2  mov     ebx, eax
0x180027ba4  test    eax, eax
0x180027ba6  js      loc_180027C45
0x180027bac  mov     eax, [r13+4Ch]
0x180027bb0  xor     r9d, r9d; struct CONFIG_SEGMENT *
0x180027bb3  mov     rdx, [rsp+1D0h+var_188]; struct IConfigDomNode *
0x180027bb8  mov     r8, rsi; struct LOCATION_CONTEXT *
0x180027bbb  mov     [rsp+1D0h+var_1A8], eax; unsigned int
0x180027bbf  mov     rcx, r15; this
0x180027bc2  lea     rax, [rsp+1D0h+var_168]
0x180027bc7  mov     [rsp+1D0h+var_1B0], rax; struct CONFIG_DOM_ERROR *
0x180027bcc  call    ?ParseLocation@CONFIG_FILE@@AEAAJPEAVIConfigDomNode@@PEAVLOCATION_CONTEXT@@PEAVCONFIG_SEGMENT@@PEAVCONFIG_DOM_ERROR@@K@Z; CONFIG_FILE::ParseLocation(IConfigDomNode *,LOCATION_CONTEXT *,CONFIG_SEGMENT *,CONFIG_DOM_ERROR *,ulong)
0x180027bd1  mov     ebx, eax
0x180027bd3  test    eax, eax
0x180027bd5  js      short loc_180027C45
0x180027bd7  mov     rcx, [rsp+1D0h+var_188]
0x180027bdc  test    rcx, rcx
0x180027bdf  jz      short loc_180027BF6
0x180027be1  mov     rax, [rcx]
0x180027be4  mov     rax, [rax+78h]
0x180027be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bed  mov     [rsp+1D0h+var_188], 0
0x180027bf6  lea     rcx, [rsp+1D0h+var_198]
0x180027bfb  call    ?Reset@?$InvasivePtr@VLOCATION_CONTEXT@@@@QEAAXXZ; InvasivePtr<LOCATION_CONTEXT>::Reset(void)
0x180027c00  mov     rcx, [rsp+1D0h+var_190]
0x180027c05  lea     r8, [rbp+0D0h+var_150]
0x180027c09  lea     rdx, [rsp+1D0h+var_170]
0x180027c0e  mov     rax, [rcx]
0x180027c11  mov     rax, [rax+10h]
0x180027c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c1a  mov     ebx, eax
0x180027c1c  test    eax, eax
0x180027c1e  js      short loc_180027C69
0x180027c20  mov     rcx, [rsp+1D0h+var_190]
0x180027c25  mov     rax, [rcx]
0x180027c28  mov     rax, [rax+78h]
0x180027c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c31  mov     rcx, [rsp+1D0h+var_170]
0x180027c36  mov     [rsp+1D0h+var_190], rcx
0x180027c3b  jmp     loc_180027ABA
0x180027c40  mov     ebx, 8007000Eh
0x180027c45  lea     rcx, [rsp+1D0h+var_198]
0x180027c4a  call    ?Reset@?$InvasivePtr@VLOCATION_CONTEXT@@@@QEAAXXZ; InvasivePtr<LOCATION_CONTEXT>::Reset(void)
0x180027c4f  jmp     short loc_180027C69
0x180027c51  mov     rcx, [r15+0B0h]; this
0x180027c58  call    ?SetReadOnly@LOCATION_TABLE@@QEAAJXZ; LOCATION_TABLE::SetReadOnly(void)
0x180027c5d  mov     ebx, eax
0x180027c5f  jmp     short loc_180027C69
0x180027c61  mov     ebx, 80070008h
0x180027c66  mov     rdi, rsi
0x180027c69  mov     rsi, [rsp+1D0h+var_1A0]
0x180027c6e  mov     rdx, [rsp+1D0h+hObject]; void *
0x180027c73  mov     rcx, [r13+50h]; void *
0x180027c77  call    ?Unimpersonate@CONFIG_CACHE@@SAJPEAX0@Z; CONFIG_CACHE::Unimpersonate(void *,void *)
0x180027c7c  test    ebx, ebx
0x180027c7e  js      short loc_180027C86
0x180027c80  test    eax, eax
0x180027c82  jns     short loc_180027C86
0x180027c84  mov     ebx, eax
0x180027c86  mov     rcx, [rsp+1D0h+hObject]; hObject
0x180027c8b  test    rcx, rcx
0x180027c8e  jz      short loc_180027C9F
0x180027c90  call    cs:__imp_CloseHandle
0x180027c96  mov     [rsp+1D0h+hObject], 0
0x180027c9f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180027ca3  jz      short loc_180027CAE
0x180027ca5  mov     rcx, rsi; hObject
0x180027ca8  call    cs:__imp_CloseHandle
0x180027cae  test    r13, r13
0x180027cb1  jz      short loc_180027CBB
0x180027cb3  mov     rcx, r13; this
0x180027cb6  call    ?DereferenceSchemaFileList@SCHEMA_FILE_LIST@@QEAAXXZ; SCHEMA_FILE_LIST::DereferenceSchemaFileList(void)
0x180027cbb  test    r12d, r12d
0x180027cbe  jz      short loc_180027CC9
0x180027cc0  mov     rcx, r14
0x180027cc3  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027cc9  mov     rcx, [rsp+1D0h+var_188]
0x180027cce  test    rcx, rcx
0x180027cd1  jz      short loc_180027CE8
0x180027cd3  mov     rax, [rcx]
0x180027cd6  mov     rax, [rax+78h]
0x180027cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cdf  mov     [rsp+1D0h+var_188], 0
0x180027ce8  mov     rcx, [rsp+1D0h+var_190]
0x180027ced  test    rcx, rcx
0x180027cf0  jz      short loc_180027D07
0x180027cf2  mov     rax, [rcx]
0x180027cf5  mov     rax, [rax+78h]
0x180027cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027cfe  mov     [rsp+1D0h+var_190], 0
0x180027d07  mov     rcx, [rsp+1D0h+var_178]
0x180027d0c  test    rcx, rcx
0x180027d0f  jz      short loc_180027D26
0x180027d11  mov     rax, [rcx]
0x180027d14  mov     rax, [rax+78h]
0x180027d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d1d  mov     [rsp+1D0h+var_178], 0
0x180027d26  test    rdi, rdi
0x180027d29  jz      short loc_180027D3A
0x180027d2b  mov     rax, [rdi]
0x180027d2e  mov     rcx, rdi
0x180027d31  mov     rax, [rax+38h]
0x180027d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d3a  lea     rax, ??_7CONFIG_DOM_ERROR@@6B@; const CONFIG_DOM_ERROR::`vftable'
0x180027d41  lea     rcx, [rbp+0D0h+var_150]; this
0x180027d45  mov     [rsp+1D0h+var_168], rax
  ... truncated ...
```
