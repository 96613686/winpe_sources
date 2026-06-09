# CONFIG_FILE::Create(ushort const *,ushort const *,ulong,ulong,void *,void *)

- ea: `0x180025694`
- end: `0x18002598b`
- name: `?Create@CONFIG_FILE@@QEAAJPEBG0KKPEAX1@Z`
- size: `759`
- prototype: `__int64 __fastcall(CONFIG_FILE *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, void *, void *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007e30`
- `0x1800178dc`
- `0x1800244f0`

## callees

- `0x180010468`
- `0x18001c250`
- `0x1800235f8`
- `0x180023664`
- `0x180025694`
- `0x180025a10`
- `0x18005061c`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180025832`
- `msvcrt!wcsrchr` at `0x180025832`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800258a3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002594d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800258a3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002594d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180025874`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180025874`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025965`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180025965`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800258b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800258b2`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800256fd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800256fd`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002577a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002577a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180025859`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180025859`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025890`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180025890`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002576d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002576d`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002595a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18002595a`
- `iisutil!PuDbgPrint` at `0x18002575d`
- `iisutil!PuDbgPrint` at `0x18002575d`

## string_xrefs

- `0x18002574c`: `Createing config file %ws, %ws\n`
- `0x180025728`: `CONFIG_FILE::Create`
- `0x180025733`: `servercommon\inetsrv\iis\iisrearc\core\nativereader\dll\configfile.cxx`

## pseudocode

```c
__int64 __fastcall CONFIG_FILE::Create(
        CONFIG_FILE *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        void *a7)
{
  int v11; // ebx
  const wchar_t *v12; // rax
  void *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // r9
  SECTION_GROUP_TABLE *v18; // rax
  wchar_t *v19; // rax
  HANDLE FirstFileW; // rsi
  const unsigned __int16 *Str; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int16 v25; // ax
  unsigned int v26; // edx
  _BYTE v28[64]; // [rsp+40h] [rbp-4D8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+80h] [rbp-498h] BYREF
  unsigned __int16 v30[264]; // [rsp+2D0h] [rbp-248h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v30, 0, 0x208u);
  STRU::STRU((STRU *)v28, v30, 0x104u);
  if ( a2 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v12 = a3;
      if ( !a3 )
        v12 = L"(NULL)";
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\nativereader\\dll\\configfile.cxx",
        2650,
        "CONFIG_FILE::Create",
        "Createing config file %ws, %ws\n",
        a2,
        v12);
    }
    CReaderWriterLock3::WriteLock((CONFIG_FILE *)((char *)this + 184));
    v11 = STRU::Copy((CONFIG_FILE *)((char *)this + 72), a2);
    if ( v11 < 0 )
      goto LABEL_28;
    v13 = operator new(0x58u);
    if ( v13 )
    {
      v16 = CONFIG_CACHE::PathFlagsToAllowDefinitionLevel(a4, v14, v15, v13);
      v13 = (void *)LOCATION_TABLE::LOCATION_TABLE(v17, *((_QWORD *)this + 44), v16);
    }
    *((_QWORD *)this + 22) = v13;
    if ( !v13 )
      goto LABEL_11;
    if ( !*((_QWORD *)this + 16) )
    {
      v18 = (SECTION_GROUP_TABLE *)operator new(0x90u);
      if ( v18 )
        v18 = SECTION_GROUP_TABLE::SECTION_GROUP_TABLE(v18, 0);
      *((_QWORD *)this + 19) = v18;
      if ( !v18 )
      {
LABEL_11:
        v11 = -2147024888;
        goto LABEL_28;
      }
      v11 = SECTION_GROUP_TABLE::Create(v18, &szDomain);
      if ( v11 < 0 )
        goto LABEL_28;
    }
    v11 = SMALL_STRU::Copy((CONFIG_FILE *)((char *)this + 40), a3);
    if ( v11 < 0 )
      goto LABEL_28;
    v19 = wcsrchr(a3, 0x5Cu);
    if ( !v19 )
    {
      v11 = -2147024883;
      goto LABEL_28;
    }
    v11 = STRU::Copy((STRU *)v28, a3, v19 - a3 + 1);
    if ( v11 < 0 )
      goto LABEL_28;
    FirstFileW = FindFirstFileW(a3, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      v11 = STRU::Append((STRU *)v28, FindFileData.cAlternateFileName);
      if ( v11 < 0 )
      {
        FindClose(FirstFileW);
LABEL_27:
        if ( v11 >= 0 )
          goto LABEL_29;
LABEL_28:
        CReaderWriterLock3::WriteUnlock((CONFIG_FILE *)((char *)this + 184));
        goto LABEL_29;
      }
      FindClose(FirstFileW);
    }
    Str = STRU::QueryStr((STRU *)v28);
    SMALL_STRU::Copy((CONFIG_FILE *)((char *)this + 48), Str);
    v25 = CONFIG_CACHE::PathFlagsToAllowDefinitionLevel(a4, v22, v23, v24);
    *((_DWORD *)this + 68) &= 0xFFFFFC31;
    v26 = ((a4 & 0x80 | (a4 >> 3) & 0x100) >> 5)
        | (v25 << 6) & 0x3C0 ^ (*((_DWORD *)this + 68) | ~(unsigned __int8)(a4 >> 7) & 2);
    *((_DWORD *)this + 69) = a5;
    *((_DWORD *)this + 68) = v26;
    *((_QWORD *)this + 18) = a7;
    if ( (a4 & 0x4000) != 0 )
      goto LABEL_29;
    *((_QWORD *)this + 17) = a6;
    goto LABEL_27;
  }
  v11 = -2147024809;
LABEL_29:
  STRU::~STRU((STRU *)v28);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180025694  push    rbx
0x180025696  push    rbp
0x180025697  push    rsi
0x180025698  push    rdi
0x180025699  push    r14
0x18002569b  sub     rsp, 4F0h
0x1800256a2  mov     rax, cs:__security_cookie
0x1800256a9  xor     rax, rsp
0x1800256ac  mov     [rsp+518h+var_38], rax
0x1800256b4  mov     rsi, r8
0x1800256b7  mov     rbx, rdx
0x1800256ba  mov     rdi, rcx
0x1800256bd  xor     edx, edx; Val
0x1800256bf  mov     r8d, 250h; Size
0x1800256c5  lea     rcx, [rsp+518h+FindFileData]; void *
0x1800256cd  mov     r14d, r9d
0x1800256d0  call    memset_0
0x1800256d5  xor     edx, edx; Val
0x1800256d7  lea     rcx, [rsp+518h+var_248]; void *
0x1800256df  mov     r8d, 208h; Size
0x1800256e5  call    memset_0
0x1800256ea  mov     r8d, 104h
0x1800256f0  lea     rdx, [rsp+518h+var_248]
0x1800256f8  lea     rcx, [rsp+518h+var_4D8]
0x1800256fd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180025703  test    rbx, rbx
0x180025706  jnz     short loc_180025712
0x180025708  mov     ebx, 80070057h
0x18002570d  jmp     loc_180025960
0x180025712  test    byte ptr cs:g_dwDebugFlags, 3
0x180025719  jz      short loc_180025763
0x18002571b  test    rsi, rsi
0x18002571e  lea     rcx, aNull; "(NULL)"
0x180025725  mov     rax, rsi
0x180025728  lea     r9, aConfigFileCrea; "CONFIG_FILE::Create"
0x18002572f  cmovz   rax, rcx
0x180025733  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002573a  mov     rcx, cs:g_pDebug
0x180025741  mov     r8d, 0A5Ah
0x180025747  mov     [rsp+518h+var_4E8], rax
0x18002574c  lea     rax, aCreateingConfi; "Createing config file %ws, %ws\n"
0x180025753  mov     [rsp+518h+var_4F0], rbx
0x180025758  mov     [rsp+518h+var_4F8], rax
0x18002575d  call    cs:__imp_PuDbgPrint
0x180025763  lea     rbp, [rdi+0B8h]
0x18002576a  mov     rcx, rbp
0x18002576d  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180025773  lea     rcx, [rdi+48h]
0x180025777  mov     rdx, rbx
0x18002577a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180025780  mov     ebx, eax
0x180025782  test    eax, eax
0x180025784  js      loc_180025957
0x18002578a  mov     ecx, 58h ; 'X'; Size
0x18002578f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025794  mov     r9, rax
0x180025797  test    rax, rax
0x18002579a  jz      short loc_1800257B6
0x18002579c  mov     ecx, r14d
0x18002579f  call    ?PathFlagsToAllowDefinitionLevel@CONFIG_CACHE@@SA?AW4_ALLOW_DEFINITION_LEVEL@@K@Z; CONFIG_CACHE::PathFlagsToAllowDefinitionLevel(ulong)
0x1800257a4  mov     rdx, [rdi+160h]
0x1800257ab  mov     r8d, eax
0x1800257ae  mov     rcx, r9
0x1800257b1  call    ??0LOCATION_TABLE@@QEAA@PEAVSCHEMA_TABLE@@W4_ALLOW_DEFINITION_LEVEL@@@Z; LOCATION_TABLE::LOCATION_TABLE(SCHEMA_TABLE *,_ALLOW_DEFINITION_LEVEL)
0x1800257b6  mov     [rdi+0B0h], rax
0x1800257bd  test    rax, rax
0x1800257c0  jnz     short loc_1800257CC
0x1800257c2  mov     ebx, 80070008h
0x1800257c7  jmp     loc_180025957
0x1800257cc  cmp     qword ptr [rdi+80h], 0
0x1800257d4  jnz     short loc_180025814
0x1800257d6  mov     ecx, 90h; Size
0x1800257db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800257e0  test    rax, rax
0x1800257e3  jz      short loc_1800257EF
0x1800257e5  xor     edx, edx; struct SECTION_GROUP_TABLE *
0x1800257e7  mov     rcx, rax; this
0x1800257ea  call    ??0SECTION_GROUP_TABLE@@QEAA@PEAV0@@Z; SECTION_GROUP_TABLE::SECTION_GROUP_TABLE(SECTION_GROUP_TABLE *)
0x1800257ef  mov     [rdi+98h], rax
0x1800257f6  test    rax, rax
0x1800257f9  jz      short loc_1800257C2
0x1800257fb  lea     rdx, szDomain; unsigned __int16 *
0x180025802  mov     rcx, rax; this
0x180025805  call    ?Create@SECTION_GROUP_TABLE@@QEAAJPEBG@Z; SECTION_GROUP_TABLE::Create(ushort const *)
0x18002580a  mov     ebx, eax
0x18002580c  test    eax, eax
0x18002580e  js      loc_180025957
0x180025814  lea     rcx, [rdi+28h]; this
0x180025818  mov     rdx, rsi; unsigned __int16 *
0x18002581b  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180025820  mov     ebx, eax
0x180025822  test    eax, eax
0x180025824  js      loc_180025957
0x18002582a  mov     edx, 5Ch ; '\'; Ch
0x18002582f  mov     rcx, rsi; Str
0x180025832  call    cs:__imp_wcsrchr
0x180025838  test    rax, rax
0x18002583b  jnz     short loc_180025847
0x18002583d  mov     ebx, 8007000Dh
0x180025842  jmp     loc_180025957
0x180025847  sub     rax, rsi
0x18002584a  lea     rcx, [rsp+518h+var_4D8]
0x18002584f  sar     rax, 1
0x180025852  mov     rdx, rsi
0x180025855  lea     r8d, [rax+1]
0x180025859  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002585f  mov     ebx, eax
0x180025861  test    eax, eax
0x180025863  js      loc_180025957
0x180025869  lea     rdx, [rsp+518h+FindFileData]; lpFindFileData
0x180025871  mov     rcx, rsi; lpFileName
0x180025874  call    cs:__imp_FindFirstFileW
0x18002587a  mov     rsi, rax
0x18002587d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025881  jz      short loc_1800258AD
0x180025883  lea     rdx, [rsp+518h+FindFileData.cAlternateFileName]
0x18002588b  lea     rcx, [rsp+518h+var_4D8]
0x180025890  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180025896  mov     ebx, eax
0x180025898  test    eax, eax
0x18002589a  js      loc_18002594A
0x1800258a0  mov     rcx, rsi; hFindFile
0x1800258a3  call    cs:__imp_FindClose
0x1800258a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800258ad  lea     rcx, [rsp+518h+var_4D8]
0x1800258b2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800258b8  mov     rdx, rax; unsigned __int16 *
0x1800258bb  lea     rcx, [rdi+30h]; this
0x1800258bf  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x1800258c4  mov     ecx, r14d
0x1800258c7  call    ?PathFlagsToAllowDefinitionLevel@CONFIG_CACHE@@SA?AW4_ALLOW_DEFINITION_LEVEL@@K@Z; CONFIG_CACHE::PathFlagsToAllowDefinitionLevel(ulong)
0x1800258cc  and     dword ptr [rdi+110h], 0FFFFFC31h
0x1800258d6  mov     edx, r14d
0x1800258d9  shr     edx, 7
0x1800258dc  mov     ecx, r14d
0x1800258df  shl     eax, 6
0x1800258e2  not     edx
0x1800258e4  and     eax, 3C0h
0x1800258e9  shr     ecx, 3
0x1800258ec  and     edx, 2
0x1800258ef  and     ecx, 100h
0x1800258f5  or      edx, [rdi+110h]
0x1800258fb  xor     edx, eax
0x1800258fd  mov     eax, r14d
0x180025900  and     eax, 80h
0x180025905  or      ecx, eax
0x180025907  mov     eax, [rsp+518h+arg_20]
0x18002590e  shr     ecx, 5
0x180025911  or      edx, ecx
0x180025913  mov     [rdi+114h], eax
0x180025919  mov     rax, [rsp+518h+arg_30]
0x180025921  mov     [rdi+110h], edx
0x180025927  mov     [rdi+90h], rax
0x18002592e  bt      r14d, 0Eh
0x180025933  jb      short loc_180025960
0x180025935  mov     rax, [rsp+518h+arg_28]
0x18002593d  mov     [rdi+88h], rax
0x180025944  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180025948  jz      short loc_180025953
0x18002594a  mov     rcx, rsi; hFindFile
0x18002594d  call    cs:__imp_FindClose
0x180025953  test    ebx, ebx
0x180025955  jns     short loc_180025960
0x180025957  mov     rcx, rbp
0x18002595a  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180025960  lea     rcx, [rsp+518h+var_4D8]
0x180025965  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002596b  mov     eax, ebx
0x18002596d  mov     rcx, [rsp+518h+var_38]
0x180025975  xor     rcx, rsp; StackCookie
0x180025978  call    __security_check_cookie
0x18002597d  add     rsp, 4F0h
0x180025984  pop     r14
0x180025986  pop     rdi
0x180025987  pop     rsi
0x180025988  pop     rbp
0x180025989  pop     rbx
0x18002598a  retn
```
