# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800010b0`
- end: `0x180001300`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `592`
- prototype: `enum REQUEST_NOTIFICATION_STATUS __high(unsigned int, int, struct IHttpContext *, struct IHttpEventProvider *, struct IHttpCompletionInfo *)`
- caller_count: `17`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001070`
- `0x180001090`
- `0x180007610`
- `0x180007670`
- `0x1800076d0`
- `0x180007730`
- `0x180007790`
- `0x1800077f0`
- `0x180007850`
- `0x1800078b0`
- `0x180007910`
- `0x180007970`
- `0x180007c10`
- `0x180007cb0`
- `0x180007d10`
- `0x180007db0`
- `0x180007e90`

## callees

- `0x1800010b0`
- `0x180001310`
- `0x180002000`
- `0x180002bb0`
- `0x180009010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180001133`
- `msvcrt!wcsstr` at `0x180001133`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001282`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800063a5`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800063c0`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001282`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800063a5`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x1800063c0`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001271`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006391`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800063cf`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001271`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180006391`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x1800063cf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012db`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012ed`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012db`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012ed`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012ab`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800012ab`

## pseudocode

```c
__int64 __fastcall RequestDoWork(
        int a1,
        __int64 a2,
        struct IHttpContext *a3,
        struct IMapHandlerProvider *a4,
        __int64 a5)
{
  __int64 v8; // rax
  const wchar_t *v9; // rax
  __int64 v11; // r14
  __int64 (__fastcall ***v12)(_QWORD, void *); // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ebp
  __int64 v16; // rbp
  __int64 v17; // rsi
  int v18; // ecx
  __int64 v19; // rdi
  char *Str; // rax
  STRA *v21; // rcx
  __int16 CCH; // ax
  STRA *v23; // rcx
  void (__fastcall *v24)(__int64, _QWORD, char *, _QWORD, _DWORD); // rsi
  char *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  struct INativeSectionException *v28[5]; // [rsp+40h] [rbp-28h] BYREF

  v28[0] = 0;
  a5 = 0;
  if ( g_fHttpCompressionInited )
    goto LABEL_2;
  v15 = 0;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)g_pCompressionLock);
  if ( !g_fHttpCompressionInited )
  {
    v15 = HTTP_COMPRESSION::Initialize(v18, v28);
    if ( v15 >= 0 )
    {
      g_fHttpCompressionInited = 1;
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)g_pCompressionLock);
      goto LABEL_2;
    }
  }
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)g_pCompressionLock);
  if ( v15 >= 0 )
  {
LABEL_2:
    if ( a1 == 16 )
    {
      if ( (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 192LL))(a3)
        && (v8 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 192LL))(a3),
            v9 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v8 + 16LL))(v8, 0),
            wcsstr(v9, L"StaticFileModule"))
        && (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3)
        && (v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 208LL))(a3),
            ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14) & 0x10) == 0) )
      {
        v15 = HTTP_COMPRESSION::DoStaticFileCompression(a3, a4, v28);
        if ( v15 < 0 )
          goto LABEL_22;
      }
      else
      {
        (*(void (__fastcall **)(struct IHttpContext *, __int64, _QWORD))(*(_QWORD *)a3 + 80LL))(a3, 256, 0);
      }
    }
    else if ( a1 == 256 )
    {
      v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      if ( (unsigned int)*(unsigned __int16 *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11) + 8)
         - 200 < 0x64 )
      {
        v12 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 56LL))(a3);
        v13 = (**v12)(v12, g_pModuleContext);
        if ( v13 )
        {
          v16 = *(_QWORD *)(v13 + 8);
          if ( HTTP_COMPRESSION::sm_fSendCacheHeaders )
          {
            v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
            Str = STRA::QueryStr((STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader);
            v21 = (STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader;
            *(_QWORD *)(v19 + 352) = Str;
            CCH = STRA::QueryCCH(v21);
            v23 = (STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader;
            *(_WORD *)(v19 + 344) = CCH;
            v24 = *(void (__fastcall **)(__int64, _QWORD, char *, _QWORD, _DWORD))(*(_QWORD *)v11 + 32LL);
            LOWORD(v19) = STRA::QueryCCH(v23);
            v25 = STRA::QueryStr((STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader);
            v24(v11, 0, v25, (unsigned __int16)v19, 0);
          }
          v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
          *(_QWORD *)(v17 + 272) = STRA::QueryStr((STRA *)(v16 + 56));
          *(_WORD *)(v17 + 264) = STRA::QueryCCH((STRA *)(v16 + 56));
          HTTP_COMPRESSION::UpdateVaryHeader(a3);
        }
      }
    }
    return 0;
  }
LABEL_22:
  if ( v28[0] )
    (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v28[0])(
      v28[0],
      &IID_IAppHostConfigException,
      &a5);
  v26 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26) + 536) = 0;
  v27 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
  (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v27 + 24LL))(
    v27,
    500,
    "Internal Server Error",
    19,
    v15,
    a5,
    0);
  if ( a5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 16LL))(a5);
    a5 = 0;
  }
  if ( v28[0] )
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v28[0] + 16LL))(v28[0]);
  return 2;
}

```

## disassembly

```asm
0x1800010b0  mov     rax, rsp
0x1800010b3  mov     [rax+10h], rbx
0x1800010b7  mov     [rax+18h], rbp
0x1800010bb  push    rsi
0x1800010bc  push    rdi
0x1800010bd  push    r15
0x1800010bf  sub     rsp, 50h
0x1800010c3  xor     r15d, r15d
0x1800010c6  mov     rsi, r9
0x1800010c9  cmp     cs:?g_fHttpCompressionInited@@3HA, r15d; int g_fHttpCompressionInited
0x1800010d0  mov     rbx, r8
0x1800010d3  mov     edi, ecx
0x1800010d5  mov     [rax-28h], r15
0x1800010d9  mov     [rax+28h], r15
0x1800010dd  jz      loc_1800012A1
0x1800010e3  cmp     edi, 10h
0x1800010e6  jnz     loc_180001171
0x1800010ec  mov     rax, [rbx]
0x1800010ef  mov     rcx, rbx
0x1800010f2  mov     rax, [rax+0C0h]
0x1800010f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010fe  test    rax, rax
0x180001101  jz      short loc_180001142
0x180001103  mov     rax, [rbx]
0x180001106  mov     rcx, rbx
0x180001109  mov     rax, [rax+0C0h]
0x180001110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001115  mov     r8, rax
0x180001118  xor     edx, edx
0x18000111a  mov     rcx, [rax]
0x18000111d  mov     rax, [rcx+10h]
0x180001121  mov     rcx, r8
0x180001124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001129  mov     rcx, rax; Str
0x18000112c  lea     rdx, aStaticfilemodu; "StaticFileModule"
0x180001133  call    cs:__imp_wcsstr
0x180001139  test    rax, rax
0x18000113c  jnz     loc_1800011E4
0x180001142  mov     rax, [rbx]
0x180001145  xor     r8d, r8d
0x180001148  mov     edx, 100h
0x18000114d  mov     rcx, rbx
0x180001150  mov     rax, [rax+50h]
0x180001154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001159  xor     eax, eax
0x18000115b  mov     rbx, [rsp+68h+arg_8]
0x180001160  mov     rbp, [rsp+68h+arg_10]
0x180001168  add     rsp, 50h
0x18000116c  pop     r15
0x18000116e  pop     rdi
0x18000116f  pop     rsi
0x180001170  retn
0x180001171  cmp     edi, 100h
0x180001177  jnz     short loc_180001159
0x180001179  mov     rax, [rbx]
0x18000117c  mov     rcx, rbx
0x18000117f  mov     [rsp+68h+arg_0], r14
0x180001184  mov     rax, [rax+20h]
0x180001188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000118d  mov     r14, rax
0x180001190  mov     rcx, [rax]
0x180001193  mov     rax, [rcx+8]
0x180001197  mov     rcx, r14
0x18000119a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000119f  movzx   ecx, word ptr [rax+8]
0x1800011a3  sub     ecx, 0C8h
0x1800011a9  cmp     ecx, 64h ; 'd'
0x1800011ac  jnb     short loc_1800011DA
0x1800011ae  mov     rcx, [rbx]
0x1800011b1  mov     rax, [rcx+38h]
0x1800011b5  mov     rcx, rbx
0x1800011b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011bd  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x1800011c4  mov     r8, rax
0x1800011c7  mov     rcx, [rax]
0x1800011ca  mov     rax, [rcx]
0x1800011cd  mov     rcx, r8
0x1800011d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011d5  test    rax, rax
0x1800011d8  jnz     short loc_18000124A
0x1800011da  mov     r14, [rsp+68h+arg_0]
0x1800011df  jmp     loc_180001159
0x1800011e4  mov     rax, [rbx]
0x1800011e7  mov     rcx, rbx
0x1800011ea  mov     rax, [rax+0D0h]
0x1800011f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011f6  test    rax, rax
0x1800011f9  jz      loc_180001142
0x1800011ff  mov     rax, [rbx]
0x180001202  mov     rcx, rbx
0x180001205  mov     rax, [rax+0D0h]
0x18000120c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001211  mov     rdx, rax
0x180001214  mov     rcx, [rax]
0x180001217  mov     rax, [rcx+38h]
0x18000121b  mov     rcx, rdx
0x18000121e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001223  test    al, 10h
0x180001225  jnz     loc_180001142
0x18000122b  lea     r8, [rsp+68h+var_28]; struct INativeSectionException **
0x180001230  mov     rdx, rsi; struct IMapHandlerProvider *
0x180001233  mov     rcx, rbx; struct IHttpContext *
0x180001236  call    ?DoStaticFileCompression@HTTP_COMPRESSION@@SAJPEAVIHttpContext@@PEAVIMapHandlerProvider@@PEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::DoStaticFileCompression(IHttpContext *,IMapHandlerProvider *,INativeSectionException * *)
0x18000123b  mov     ebp, eax
0x18000123d  test    eax, eax
0x18000123f  jns     loc_180001159
0x180001245  jmp     loc_1800063F4
0x18000124a  cmp     cs:?sm_fSendCacheHeaders@HTTP_COMPRESSION@@0HA, r15d; int HTTP_COMPRESSION::sm_fSendCacheHeaders
0x180001251  mov     rbp, [rax+8]
0x180001255  jnz     loc_180006378
0x18000125b  mov     rax, [r14]
0x18000125e  mov     rcx, r14
0x180001261  mov     rax, [rax+8]
0x180001265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126a  lea     rcx, [rbp+38h]
0x18000126e  mov     rsi, rax
0x180001271  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180001277  lea     rcx, [rbp+38h]
0x18000127b  mov     [rsi+110h], rax
0x180001282  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180001288  mov     rcx, rbx; struct IHttpContext *
0x18000128b  mov     [rsi+108h], ax
0x180001292  call    ?UpdateVaryHeader@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@@Z; HTTP_COMPRESSION::UpdateVaryHeader(IHttpContext *)
0x180001297  mov     r14, [rsp+68h+arg_0]
0x18000129c  jmp     loc_180001159
0x1800012a1  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x1800012a8  mov     ebp, r15d
0x1800012ab  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800012b1  cmp     cs:?g_fHttpCompressionInited@@3HA, r15d; int g_fHttpCompressionInited
0x1800012b8  jnz     short loc_1800012E6
0x1800012ba  lea     rdx, [rsp+68h+var_28]; struct INativeSectionException **
0x1800012bf  call    ?Initialize@HTTP_COMPRESSION@@SAJHPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::Initialize(int,INativeSectionException * *)
0x1800012c4  mov     ebp, eax
0x1800012c6  test    eax, eax
0x1800012c8  js      short loc_1800012E6
0x1800012ca  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x1800012d1  mov     cs:?g_fHttpCompressionInited@@3HA, 1; int g_fHttpCompressionInited
0x1800012db  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800012e1  jmp     loc_1800010E3
0x1800012e6  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x1800012ed  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800012f3  test    ebp, ebp
0x1800012f5  jns     loc_1800010E3
0x1800012fb  jmp     loc_1800063F4
0x180006378  mov     rax, [r14]
0x18000637b  mov     rcx, r14
0x18000637e  mov     rax, [rax+8]
0x180006382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006387  mov     rcx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x18000638e  mov     rdi, rax
0x180006391  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180006397  mov     rcx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x18000639e  mov     [rdi+160h], rax
0x1800063a5  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800063ab  mov     rcx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x1800063b2  mov     [rdi+158h], ax
0x1800063b9  mov     rax, [r14]
0x1800063bc  mov     rsi, [rax+20h]
0x1800063c0  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x1800063c6  mov     rcx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x1800063cd  mov     edi, eax
0x1800063cf  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x1800063d5  movzx   r9d, di
0x1800063d9  mov     [rsp+68h+var_48], r15d
0x1800063de  mov     r8, rax
0x1800063e1  xor     edx, edx
0x1800063e3  mov     rax, rsi
0x1800063e6  mov     rcx, r14
0x1800063e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ee  nop
0x1800063ef  jmp     loc_18000125B
0x1800063f4  mov     rcx, [rsp+68h+var_28]
0x1800063f9  test    rcx, rcx
0x1800063fc  jz      short loc_180006418
0x1800063fe  mov     rax, [rcx]
0x180006401  lea     r8, [rsp+68h+arg_20]
0x180006409  lea     rdx, IID_IAppHostConfigException
0x180006410  mov     rax, [rax]
0x180006413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006418  mov     rax, [rbx]
0x18000641b  mov     rcx, rbx
0x18000641e  mov     rax, [rax+20h]
0x180006422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006427  mov     rdx, rax
0x18000642a  mov     rcx, [rax]
0x18000642d  mov     rax, [rcx+8]
0x180006431  mov     rcx, rdx
0x180006434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006439  mov     rcx, rbx
0x18000643c  mov     [rax+218h], r15w
0x180006444  mov     rax, [rbx]
0x180006447  mov     rax, [rax+20h]
0x18000644b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006450  mov     r10, rax
0x180006453  mov     [rsp+68h+var_38], r15d
0x180006458  mov     edx, 1F4h
0x18000645d  lea     r8, aInternalServer; "Internal Server Error"
0x180006464  mov     r9d, 13h
0x18000646a  mov     rcx, [rax]
0x18000646d  mov     rax, [rcx+18h]
0x180006471  mov     rcx, [rsp+68h+arg_20]
0x180006479  mov     [rsp+68h+var_40], rcx
0x18000647e  mov     rcx, r10
0x180006481  mov     [rsp+68h+var_48], ebp
0x180006485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648a  mov     rcx, [rsp+68h+arg_20]
0x180006492  test    rcx, rcx
0x180006495  jz      short loc_1800064AB
0x180006497  mov     rax, [rcx]
0x18000649a  mov     rax, [rax+10h]
0x18000649e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064a3  mov     [rsp+68h+arg_20], r15
0x1800064ab  mov     rcx, [rsp+68h+var_28]
0x1800064b0  test    rcx, rcx
0x1800064b3  jz      short loc_1800064C1
0x1800064b5  mov     rax, [rcx]
0x1800064b8  mov     rax, [rax+10h]
0x1800064bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c1  mov     eax, 2
0x1800064c6  jmp     loc_18000115B
```
