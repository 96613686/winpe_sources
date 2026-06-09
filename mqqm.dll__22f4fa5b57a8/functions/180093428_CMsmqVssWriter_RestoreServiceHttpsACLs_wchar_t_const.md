# CMsmqVssWriter::RestoreServiceHttpsACLs(wchar_t const *)

- ea: `0x180093428`
- end: `0x180093858`
- name: `?RestoreServiceHttpsACLs@CMsmqVssWriter@@AEAAJPEB_W@Z`
- size: `1072`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009331c`

## callees

- `0x18000bb04`
- `0x18000cb80`
- `0x1800261c0`
- `0x18002c61c`
- `0x180090140`
- `0x180092810`
- `0x180093428`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800934a8`
- `msvcrt!free` at `0x1800934eb`
- `msvcrt!free` at `0x1800934f5`
- `msvcrt!free` at `0x18009353e`
- `msvcrt!free` at `0x180093552`
- `msvcrt!free` at `0x18009355c`
- `msvcrt!free` at `0x18009359e`
- `msvcrt!free` at `0x1800935b2`
- `msvcrt!free` at `0x1800935bc`
- `msvcrt!free` at `0x1800935fd`
- `msvcrt!free` at `0x180093611`
- `msvcrt!free` at `0x18009361b`
- `msvcrt!free` at `0x180093659`
- `msvcrt!free` at `0x18009366d`
- `msvcrt!free` at `0x180093677`
- `msvcrt!free` at `0x1800936b7`
- `msvcrt!free` at `0x1800936cb`
- `msvcrt!free` at `0x1800936d5`
- `msvcrt!free` at `0x18009370c`
- `msvcrt!free` at `0x180093720`
- `msvcrt!free` at `0x18009372a`
- `msvcrt!free` at `0x1800937d8`
- `msvcrt!free` at `0x1800937e2`
- `msvcrt!free` at `0x1800937f6`
- `msvcrt!free` at `0x180093800`
- `msvcrt!free` at `0x18009380f`
- `msvcrt!free` at `0x180093819`
- `msvcrt!free` at `0x18009382d`
- `msvcrt!free` at `0x180093837`
- `msvcrt!free` at `0x1800934a8`
- `msvcrt!free` at `0x1800934eb`
- `msvcrt!free` at `0x1800934f5`
- `msvcrt!free` at `0x18009353e`
- `msvcrt!free` at `0x180093552`
- `msvcrt!free` at `0x18009355c`
- `msvcrt!free` at `0x18009359e`
- `msvcrt!free` at `0x1800935b2`
- `msvcrt!free` at `0x1800935bc`
- `msvcrt!free` at `0x1800935fd`
- `msvcrt!free` at `0x180093611`
- `msvcrt!free` at `0x18009361b`
- `msvcrt!free` at `0x180093659`
- `msvcrt!free` at `0x18009366d`
- `msvcrt!free` at `0x180093677`
- `msvcrt!free` at `0x1800936b7`
- `msvcrt!free` at `0x1800936cb`
- `msvcrt!free` at `0x1800936d5`
- `msvcrt!free` at `0x18009370c`
- `msvcrt!free` at `0x180093720`
- `msvcrt!free` at `0x18009372a`
- `msvcrt!free` at `0x1800937d8`
- `msvcrt!free` at `0x1800937e2`
- `msvcrt!free` at `0x1800937f6`
- `msvcrt!free` at `0x180093800`
- `msvcrt!free` at `0x18009380f`
- `msvcrt!free` at `0x180093819`
- `msvcrt!free` at `0x18009382d`
- `msvcrt!free` at `0x180093837`
- `msvcrt!wcsstr` at `0x180093573`
- `msvcrt!wcsstr` at `0x180093631`
- `msvcrt!wcsstr` at `0x180093573`
- `msvcrt!wcsstr` at `0x180093631`
- `msvcrt!wcschr` at `0x18009368f`
- `msvcrt!wcschr` at `0x18009368f`
- `msvcrt!_snwscanf_s` at `0x180093772`
- `msvcrt!_snwscanf_s` at `0x180093772`
- `ADVAPI32!SetFileSecurityW` at `0x180093798`
- `ADVAPI32!SetFileSecurityW` at `0x180093798`
- `KERNEL32!GetLastError` at `0x1800937a2`
- `KERNEL32!GetLastError` at `0x1800937a2`

## string_xrefs

- `0x180093496`: `writer/mqwriter`
- `0x1800934d9`: `writer/mqwriter`
- `0x18009352b`: `writer/mqwriter`
- `0x180093587`: `writer/mqwriter`
- `0x1800935e6`: `writer/mqwriter`
- `0x180093642`: `writer/mqwriter`
- `0x1800936a0`: `writer/mqwriter`
- `0x1800936f5`: `writer/mqwriter`
- `0x1800937c5`: `writer/mqwriter`
- `0x180093466`: `config`
- `0x18009345a`: `msmqwebacl.bkp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CMsmqVssWriter::RestoreServiceHttpsACLs(CMsmqVssWriter *this, const wchar_t *a2)
{
  wchar_t *v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r13d
  wchar_t *v8; // rbx
  CMsmqVssWriter *v9; // rcx
  unsigned int v10; // r8d
  int HttpPhysicalDirectory; // eax
  CMsmqVssWriter *v12; // rcx
  unsigned int v13; // esi
  int v14; // eax
  void *v15; // r15
  wchar_t *v16; // rsi
  const wchar_t *v17; // rsi
  wchar_t *v18; // rax
  wchar_t *v19; // rax
  const wchar_t *v20; // r14
  unsigned __int64 v21; // r12
  _BYTE *v22; // rsi
  signed int LastError; // eax
  signed int v24; // r14d
  CMsmqVssWriter *v25; // [rsp+90h] [rbp+40h] BYREF
  void *v26; // [rsp+A0h] [rbp+50h] BYREF
  void *Block; // [rsp+A8h] [rbp+58h] BYREF

  v25 = this;
  v3 = (wchar_t *)MmAllocate(0x20Au);
  v4 = StringCchPrintfW(v3, 0x105u, L"%s\\%s\\%s", a2, L"config", L"msmqwebacl.bkp", v3);
  v5 = v4;
  v6 = 0;
  if ( v4 < 0 )
  {
    LogMsgHR(v4, (wchar_t *)L"writer/mqwriter", 0x1B8u);
    free(v3);
    return v5;
  }
  v8 = (wchar_t *)MmAllocate(0x20Au);
  HttpPhysicalDirectory = CMsmqVssWriter::GetHttpPhysicalDirectory(v9, v8, v10);
  v13 = HttpPhysicalDirectory;
  if ( HttpPhysicalDirectory < 0 )
  {
    LogMsgHR(HttpPhysicalDirectory, (wchar_t *)L"writer/mqwriter", 0x1C2u);
    free(v8);
    free(v3);
    return v13;
  }
  v26 = (void *)-1LL;
  Block = 0;
  v14 = CMsmqVssWriter::ReadRestoreFile(v12, v3, &v26, (wchar_t **)&Block);
  v13 = v14;
  if ( v14 < 0 )
  {
    LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x1CCu);
    free(Block);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  v15 = Block;
  v16 = wcsstr((const wchar_t *)Block, L"\r\n\r\n");
  if ( !v16 )
  {
    v13 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0x1E0u);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  v17 = &v16[mqwcslen(L"\r\n\r\n")];
  if ( !*v17 )
  {
    v13 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0x1F4u);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  v18 = wcsstr(v17, L"\r\n");
  if ( !v18 )
  {
    v13 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0x208u);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  *v18 = 0;
  v19 = wcschr(v17, 0x3Du);
  if ( !v19 )
  {
    v13 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0x21Cu);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  *v19 = 0;
  v20 = v19 + 1;
  if ( !v19[1] )
  {
    v13 = -1072824314;
    LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0x230u);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return v13;
  }
  v21 = mqwcslen(v19 + 1) >> 1;
  v22 = MmAllocate(v21);
  if ( (_DWORD)v21 )
  {
    do
    {
      LODWORD(v25) = 0;
      _snwscanf_s(v20, 2u, L"%02x", &v25);
      v22[v6++] = (_BYTE)v25;
      v20 += 2;
    }
    while ( v6 < (unsigned int)v21 );
  }
  if ( SetFileSecurityW(v8, 4u, v22) )
  {
    free(v22);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return 0;
  }
  else
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0x80070000;
    if ( v24 < 0 )
      LogMsgHR(v24, (wchar_t *)L"writer/mqwriter", 0x244u);
    free(v22);
    free(v15);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)&v26);
    free(v8);
    free(v3);
    return (unsigned int)v24;
  }
}

```

## disassembly

```asm
0x180093428  mov     [rsp-38h+arg_8], rbx
0x18009342d  mov     [rsp-38h+arg_0], rcx
0x180093432  push    rbp
0x180093433  push    rsi
0x180093434  push    rdi
0x180093435  push    r12
0x180093437  push    r13
0x180093439  push    r14
0x18009343b  push    r15
0x18009343d  mov     rbp, rsp
0x180093440  sub     rsp, 50h
0x180093444  mov     rbx, rdx
0x180093447  mov     esi, 20Ah
0x18009344c  mov     ecx, esi; unsigned __int64
0x18009344e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180093453  mov     rdi, rax
0x180093456  mov     [rbp+var_20], rax
0x18009345a  lea     rax, aMsmqwebaclBkp; "msmqwebacl.bkp"
0x180093461  mov     [rsp+50h+var_28], rax
0x180093466  lea     rax, aConfig; "config"
0x18009346d  mov     [rsp+50h+var_30], rax
0x180093472  mov     r9, rbx
0x180093475  lea     r8, aSSS; "%s\\%s\\%s"
0x18009347c  mov     edx, 105h; unsigned __int64
0x180093481  mov     rcx, rdi; wchar_t *
0x180093484  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180093489  mov     ebx, eax
0x18009348b  xor     r13d, r13d
0x18009348e  test    eax, eax
0x180093490  jns     short loc_1800934B6
0x180093492  lea     r8d, [rsi-52h]; unsigned __int16
0x180093496  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009349d  mov     ecx, eax; int
0x18009349f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800934a4  nop
0x1800934a5  mov     rcx, rdi; Block
0x1800934a8  call    cs:__imp_free
0x1800934ae  nop
0x1800934af  mov     eax, ebx
0x1800934b1  jmp     loc_180093840
0x1800934b6  mov     rcx, rsi; unsigned __int64
0x1800934b9  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800934be  mov     rbx, rax
0x1800934c1  mov     [rbp+var_18], rax
0x1800934c5  mov     rdx, rax; wchar_t *
0x1800934c8  call    ?GetHttpPhysicalDirectory@CMsmqVssWriter@@AEAAJPEA_WK@Z; CMsmqVssWriter::GetHttpPhysicalDirectory(wchar_t *,ulong)
0x1800934cd  mov     esi, eax
0x1800934cf  test    eax, eax
0x1800934d1  jns     short loc_180093503
0x1800934d3  mov     r8d, 1C2h; unsigned __int16
0x1800934d9  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800934e0  mov     ecx, eax; int
0x1800934e2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800934e7  nop
0x1800934e8  mov     rcx, rbx; Block
0x1800934eb  call    cs:__imp_free
0x1800934f1  nop
0x1800934f2  mov     rcx, rdi; Block
0x1800934f5  call    cs:__imp_free
0x1800934fb  nop
0x1800934fc  mov     eax, esi
0x1800934fe  jmp     loc_180093840
0x180093503  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x18009350b  mov     [rbp+Block], r13
0x18009350f  lea     r9, [rbp+Block]; wchar_t **
0x180093513  lea     r8, [rbp+arg_10]; void **
0x180093517  mov     rdx, rdi; wchar_t *
0x18009351a  call    ?ReadRestoreFile@CMsmqVssWriter@@AEAAJPEB_WPEAPEAXPEAPEA_W@Z; CMsmqVssWriter::ReadRestoreFile(wchar_t const *,void * *,wchar_t * *)
0x18009351f  mov     esi, eax
0x180093521  test    eax, eax
0x180093523  jns     short loc_180093565
0x180093525  mov     r8d, 1CCh; unsigned __int16
0x18009352b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093532  mov     ecx, eax; int
0x180093534  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093539  nop
0x18009353a  mov     rcx, [rbp+Block]; Block
0x18009353e  call    cs:__imp_free
0x180093544  nop
0x180093545  lea     rcx, [rbp+arg_10]; this
0x180093549  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x18009354e  nop
0x18009354f  mov     rcx, rbx; Block
0x180093552  call    cs:__imp_free
0x180093558  nop
0x180093559  mov     rcx, rdi; Block
0x18009355c  call    cs:__imp_free
0x180093562  nop
0x180093563  jmp     short loc_1800934FC
0x180093565  lea     rdx, SubStr; "\r\n\r\n"
0x18009356c  mov     r15, [rbp+Block]
0x180093570  mov     rcx, r15; Str
0x180093573  call    cs:__imp_wcsstr
0x180093579  mov     rsi, rax
0x18009357c  test    rax, rax
0x18009357f  jnz     short loc_1800935C8
0x180093581  mov     r8d, 1E0h; unsigned __int16
0x180093587  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009358e  mov     esi, 0C00E0006h
0x180093593  mov     ecx, esi; int
0x180093595  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009359a  nop
0x18009359b  mov     rcx, r15; Block
0x18009359e  call    cs:__imp_free
0x1800935a4  nop
0x1800935a5  lea     rcx, [rbp+arg_10]; this
0x1800935a9  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800935ae  nop
0x1800935af  mov     rcx, rbx; Block
0x1800935b2  call    cs:__imp_free
0x1800935b8  nop
0x1800935b9  mov     rcx, rdi; Block
0x1800935bc  call    cs:__imp_free
0x1800935c2  nop
0x1800935c3  jmp     loc_1800934FC
0x1800935c8  lea     rcx, SubStr; "\r\n\r\n"
0x1800935cf  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800935d4  mov     eax, eax
0x1800935d6  lea     rsi, [rsi+rax*2]
0x1800935da  cmp     [rsi], r13w
0x1800935de  jnz     short loc_180093627
0x1800935e0  mov     r8d, 1F4h; unsigned __int16
0x1800935e6  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800935ed  mov     esi, 0C00E0006h
0x1800935f2  mov     ecx, esi; int
0x1800935f4  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800935f9  nop
0x1800935fa  mov     rcx, r15; Block
0x1800935fd  call    cs:__imp_free
0x180093603  nop
0x180093604  lea     rcx, [rbp+arg_10]; this
0x180093608  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x18009360d  nop
0x18009360e  mov     rcx, rbx; Block
0x180093611  call    cs:__imp_free
0x180093617  nop
0x180093618  mov     rcx, rdi; Block
0x18009361b  call    cs:__imp_free
0x180093621  nop
0x180093622  jmp     loc_1800934FC
0x180093627  lea     rdx, asc_1801050C4; "\r\n"
0x18009362e  mov     rcx, rsi; Str
0x180093631  call    cs:__imp_wcsstr
0x180093637  test    rax, rax
0x18009363a  jnz     short loc_180093683
0x18009363c  mov     r8d, 208h; unsigned __int16
0x180093642  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180093649  mov     esi, 0C00E0006h
0x18009364e  mov     ecx, esi; int
0x180093650  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093655  nop
0x180093656  mov     rcx, r15; Block
0x180093659  call    cs:__imp_free
0x18009365f  nop
0x180093660  lea     rcx, [rbp+arg_10]; this
0x180093664  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x180093669  nop
0x18009366a  mov     rcx, rbx; Block
0x18009366d  call    cs:__imp_free
0x180093673  nop
0x180093674  mov     rcx, rdi; Block
0x180093677  call    cs:__imp_free
0x18009367d  nop
0x18009367e  jmp     loc_1800934FC
0x180093683  mov     [rax], r13w
0x180093687  mov     edx, 3Dh ; '='; Ch
0x18009368c  mov     rcx, rsi; Str
0x18009368f  call    cs:__imp_wcschr
0x180093695  test    rax, rax
0x180093698  jnz     short loc_1800936E1
0x18009369a  mov     r8d, 21Ch; unsigned __int16
0x1800936a0  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800936a7  mov     esi, 0C00E0006h
0x1800936ac  mov     ecx, esi; int
0x1800936ae  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800936b3  nop
0x1800936b4  mov     rcx, r15; Block
0x1800936b7  call    cs:__imp_free
0x1800936bd  nop
0x1800936be  lea     rcx, [rbp+arg_10]; this
0x1800936c2  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800936c7  nop
0x1800936c8  mov     rcx, rbx; Block
0x1800936cb  call    cs:__imp_free
0x1800936d1  nop
0x1800936d2  mov     rcx, rdi; Block
0x1800936d5  call    cs:__imp_free
0x1800936db  nop
0x1800936dc  jmp     loc_1800934FC
0x1800936e1  mov     [rax], r13w
0x1800936e5  lea     r14, [rax+2]
0x1800936e9  cmp     [r14], r13w
0x1800936ed  jnz     short loc_180093736
0x1800936ef  mov     r8d, 230h; unsigned __int16
0x1800936f5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800936fc  mov     esi, 0C00E0006h
0x180093701  mov     ecx, esi; int
0x180093703  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180093708  nop
0x180093709  mov     rcx, r15; Block
0x18009370c  call    cs:__imp_free
0x180093712  nop
0x180093713  lea     rcx, [rbp+arg_10]; this
0x180093717  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x18009371c  nop
0x18009371d  mov     rcx, rbx; Block
0x180093720  call    cs:__imp_free
0x180093726  nop
0x180093727  mov     rcx, rdi; Block
0x18009372a  call    cs:__imp_free
0x180093730  nop
0x180093731  jmp     loc_1800934FC
0x180093736  mov     rcx, r14; wchar_t *
0x180093739  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18009373e  mov     r12d, eax
0x180093741  shr     r12d, 1
0x180093744  mov     ecx, r12d; unsigned __int64
0x180093747  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18009374c  mov     rsi, rax
0x18009374f  mov     [rbp+var_10], rax
0x180093753  test    r12d, r12d
0x180093756  jz      short loc_18009378D
0x180093758  mov     dword ptr [rbp+arg_0], 0
0x18009375f  lea     r9, [rbp+arg_0]
0x180093763  lea     r8, a02x; "%02x"
0x18009376a  mov     edx, 2; BufferCount
0x18009376f  mov     rcx, r14; Buffer
0x180093772  call    cs:__imp__snwscanf_s
0x180093778  mov     ecx, r13d
0x18009377b  mov     al, byte ptr [rbp+arg_0]
0x18009377e  mov     [rcx+rsi], al
0x180093781  inc     r13d
0x180093784  add     r14, 4
0x180093788  cmp     r13d, r12d
0x18009378b  jb      short loc_180093758
0x18009378d  mov     r8, rsi; pSecurityDescriptor
0x180093790  mov     edx, 4; SecurityInformation
0x180093795  mov     rcx, rbx; lpFileName
0x180093798  call    cs:__imp_SetFileSecurityW
0x18009379e  test    eax, eax
0x1800937a0  jnz     short loc_18009380C
0x1800937a2  call    cs:__imp_GetLastError
0x1800937a8  mov     r14d, eax
0x1800937ab  test    eax, eax
0x1800937ad  jle     short loc_1800937BA
0x1800937af  movzx   r14d, ax
0x1800937b3  or      r14d, 80070000h
0x1800937ba  test    r14d, r14d
0x1800937bd  jns     short loc_1800937D5
0x1800937bf  mov     r8d, 244h; unsigned __int16
0x1800937c5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800937cc  mov     ecx, r14d; int
0x1800937cf  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800937d4  nop
0x1800937d5  mov     rcx, rsi; Block
0x1800937d8  call    cs:__imp_free
0x1800937de  nop
0x1800937df  mov     rcx, r15; Block
0x1800937e2  call    cs:__imp_free
0x1800937e8  nop
0x1800937e9  lea     rcx, [rbp+arg_10]; this
0x1800937ed  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800937f2  nop
0x1800937f3  mov     rcx, rbx; Block
0x1800937f6  call    cs:__imp_free
0x1800937fc  nop
0x1800937fd  mov     rcx, rdi; Block
0x180093800  call    cs:__imp_free
0x180093806  nop
0x180093807  mov     eax, r14d
0x18009380a  jmp     short loc_180093840
0x18009380c  mov     rcx, rsi; Block
0x18009380f  call    cs:__imp_free
0x180093815  nop
0x180093816  mov     rcx, r15; Block
0x180093819  call    cs:__imp_free
0x18009381f  nop
0x180093820  lea     rcx, [rbp+arg_10]; this
0x180093824  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x180093829  nop
0x18009382a  mov     rcx, rbx; Block
0x18009382d  call    cs:__imp_free
0x180093833  nop
0x180093834  mov     rcx, rdi; Block
0x180093837  call    cs:__imp_free
0x18009383d  nop
0x18009383e  xor     eax, eax
0x180093840  mov     rbx, [rsp+50h+arg_8]
0x180093848  add     rsp, 50h
0x18009384c  pop     r15
0x18009384e  pop     r14
0x180093850  pop     r13
0x180093852  pop     r12
0x180093854  pop     rdi
0x180093855  pop     rsi
0x180093856  pop     rbp
0x180093857  retn
```
