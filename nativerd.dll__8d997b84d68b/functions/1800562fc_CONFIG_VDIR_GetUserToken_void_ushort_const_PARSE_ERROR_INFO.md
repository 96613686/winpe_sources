# CONFIG_VDIR::GetUserToken(void * *,ushort const *,PARSE_ERROR_INFO *)

- ea: `0x1800562fc`
- end: `0x1800566ad`
- name: `?GetUserToken@CONFIG_VDIR@@QEAAJPEAPEAXPEBGPEAVPARSE_ERROR_INFO@@@Z`
- size: `945`
- prototype: `__int64 __fastcall(CONFIG_VDIR *this, void **, unsigned __int16 *, struct PARSE_ERROR_INFO *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008d00`
- `0x180016ba0`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x18001e610`
- `0x180044228`
- `0x180044df0`
- `0x1800562fc`
- `0x180059230`
- `0x18005989c`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180056452`
- `msvcrt!wcspbrk` at `0x180056452`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005655e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005655e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180056554`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180056554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005652a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056516`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005652a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056685`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180056685`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056490`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180056490`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180056359`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180056359`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005647c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18005647c`

## string_xrefs

- `0x1800565e7`: `physicalPath`
- `0x18005659d`: `CONFIG_VDIR::GetUserToken`

## pseudocode

```c
__int64 __fastcall CONFIG_VDIR::GetUserToken(
        CONFIG_VDIR *this,
        void **a2,
        unsigned __int16 *a3,
        struct PARSE_ERROR_INFO *a4)
{
  signed int v6; // esi
  __int64 v8; // rcx
  wchar_t *v9; // rdi
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  unsigned __int16 *v12; // rbx
  unsigned __int16 *Str; // r8
  unsigned int v14; // eax
  int CachedToken; // eax
  TOKEN_CACHE_ENTRY *v16; // r14
  HANDLE CurrentProcess; // rdi
  void *ImpersonationToken; // rbx
  HANDLE v19; // rax
  signed int LastError; // eax
  HANDLE v21; // rbx
  unsigned int v22; // eax
  int v23; // edx
  int v24; // ecx
  __int64 v25; // rcx
  unsigned int v27; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v28; // [rsp+44h] [rbp-BCh] BYREF
  TOKEN_CACHE_ENTRY *v29; // [rsp+48h] [rbp-B8h] BYREF
  struct INativePropertyException *v30; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v32; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v35[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v36[64]; // [rsp+C0h] [rbp-40h] BYREF

  v33 = a3;
  v28 = 0;
  v6 = 0;
  memset_0(v36, 0, sizeof(v36));
  STRU::STRU((STRU *)v35, v36, 0x40u);
  *a2 = 0;
  v8 = *((_QWORD *)this + 1);
  String = 0;
  v32 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  if ( !v8 )
    goto LABEL_36;
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)(v8 + 16) + 64LL))(
         v8 + 16,
         L"userName",
         &String,
         0,
         0);
  if ( v6 >= 0 )
  {
    v9 = String;
    if ( *String )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, struct INativePropertyException **, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL) + 64LL))(
             *((_QWORD *)this + 1) + 16LL,
             L"password",
             &v32,
             &v30,
             0);
      if ( v6 >= 0 )
      {
        if ( v30 )
        {
          PARSE_ERROR_INFO::CopyPropertyException(a4, v30);
LABEL_7:
          v6 = -2147024883;
          goto LABEL_34;
        }
        v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 1) + 16LL)
                                                                                                 + 48LL))(
               *((_QWORD *)this + 1) + 16LL,
               L"logonMethod",
               &v27,
               0,
               0);
        if ( v6 >= 0 )
        {
          v10 = wcspbrk(v9, L"/\\");
          v11 = v10;
          if ( !v10 )
          {
            v12 = v9;
            Str = L".";
            goto LABEL_13;
          }
          v6 = STRU::Copy((STRU *)v35, v9, v10 - v9);
          if ( v6 >= 0 )
          {
            Str = STRU::QueryStr((STRU *)v35);
            v12 = v11 + 1;
LABEL_13:
            if ( v27 )
            {
              switch ( v27 )
              {
                case 1u:
                  v14 = 4;
                  break;
                case 2u:
                  v14 = 3;
                  break;
                case 3u:
                  v14 = 8;
                  break;
                default:
                  goto LABEL_7;
              }
            }
            else
            {
              v14 = 2;
            }
            v27 = v14;
            CachedToken = TOKEN_CACHE::GetCachedToken((TOKEN_CACHE *)&v29, v12, Str, v32, v14, &v29, &v28);
            v16 = v29;
            v6 = CachedToken;
            if ( CachedToken >= 0 )
            {
              if ( !v28 )
              {
                CurrentProcess = GetCurrentProcess();
                ImpersonationToken = TOKEN_CACHE_ENTRY::QueryImpersonationToken(v16);
                v19 = GetCurrentProcess();
                if ( DuplicateHandle(v19, ImpersonationToken, CurrentProcess, a2, 0, 0, 2u) )
                {
                  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 1) != 0 )
                  {
                    v21 = *a2;
                    v22 = (unsigned int)TOKEN_CACHE_ENTRY::QueryImpersonationToken(v16);
                    McTemplateU0zpp_EtwEventWriteTransfer(
                      v24,
                      v23,
                      (unsigned int)L"CONFIG_VDIR::GetUserToken",
                      v22,
                      (char)v21);
                  }
                }
                else
                {
                  LastError = GetLastError();
                  v6 = LastError;
                  if ( LastError > 0 )
                    v6 = (unsigned __int16)LastError | 0x80070000;
                }
                goto LABEL_32;
              }
              if ( (int)v28 > 0 )
                v6 = (unsigned __int16)v28 | 0x80070000;
              else
                v6 = v28;
            }
            v25 = *((_QWORD *)this + 1) + 16LL;
            v29 = 0;
            v34 = 0;
            (*(void (__fastcall **)(__int64, const wchar_t *, TOKEN_CACHE_ENTRY **, _QWORD, _QWORD))(*(_QWORD *)v25 + 64LL))(
              v25,
              L"physicalPath",
              &v29,
              0,
              0);
            *(_QWORD *)&v34 = v29;
            *((_QWORD *)&v34 + 1) = String;
            SMALL_STRU::Copy((struct PARSE_ERROR_INFO *)((char *)a4 + 32), v33);
            PARSE_ERROR_INFO::SetErrorInfo(
              a4,
              (unsigned int)v6,
              3,
              3221228208LL,
              &v34,
              *(_DWORD *)(*((_QWORD *)this + 1) + 64LL),
              0,
              *(_QWORD *)(*((_QWORD *)this + 1) + 56LL),
              v27,
              v29);
LABEL_32:
            if ( v16 )
              TOKEN_CACHE_ENTRY::DereferenceCacheEntry(v16);
          }
        }
      }
    }
  }
LABEL_34:
  if ( v30 )
  {
    (*(void (__fastcall **)(struct INativePropertyException *))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
  }
LABEL_36:
  STRU::~STRU((STRU *)v35);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800562fc  push    rbp
0x1800562fe  push    rbx
0x1800562ff  push    rsi
0x180056300  push    rdi
0x180056301  push    r12
0x180056303  push    r13
0x180056305  push    r14
0x180056307  push    r15
0x180056309  lea     rbp, [rsp-58h]
0x18005630e  sub     rsp, 158h
0x180056315  mov     rax, cs:__security_cookie
0x18005631c  xor     rax, rsp
0x18005631f  mov     [rbp+90h+var_50], rax
0x180056323  mov     [rsp+190h+var_128], r8
0x180056328  mov     r12, rdx
0x18005632b  mov     r15, rcx
0x18005632e  xor     r14d, r14d
0x180056331  xor     edx, edx; Val
0x180056333  mov     [rsp+190h+var_14C], r14d
0x180056338  mov     r8d, 80h; Size
0x18005633e  lea     rcx, [rbp+90h+var_D0]; void *
0x180056342  mov     esi, r14d
0x180056345  mov     r13, r9
0x180056348  call    memset_0
0x18005634d  lea     r8d, [r14+40h]
0x180056351  lea     rdx, [rbp+90h+var_D0]
0x180056355  lea     rcx, [rbp+90h+var_110]
0x180056359  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005635f  mov     [r12], r14
0x180056363  mov     rcx, [r15+8]
0x180056367  mov     [rsp+190h+String], r14
0x18005636c  mov     [rsp+190h+var_130], r14
0x180056371  mov     [rsp+190h+var_150], r14d
0x180056376  mov     [rsp+190h+var_148], r14
0x18005637b  mov     [rsp+190h+var_140], r14
0x180056380  test    rcx, rcx
0x180056383  jz      loc_180056681
0x180056389  add     rcx, 10h
0x18005638d  mov     qword ptr [rsp+190h+dwDesiredAccess], r14
0x180056392  xor     r9d, r9d
0x180056395  lea     r8, [rsp+190h+String]
0x18005639a  lea     rdx, aUsername; "userName"
0x1800563a1  mov     rax, [rcx]
0x1800563a4  mov     rax, [rax+40h]
0x1800563a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563ad  mov     esi, eax
0x1800563af  test    eax, eax
0x1800563b1  js      loc_180056666
0x1800563b7  mov     rdi, [rsp+190h+String]
0x1800563bc  cmp     [rdi], r14w
0x1800563c0  jz      loc_180056666
0x1800563c6  mov     rcx, [r15+8]
0x1800563ca  lea     r9, [rsp+190h+var_140]
0x1800563cf  add     rcx, 10h
0x1800563d3  mov     qword ptr [rsp+190h+dwDesiredAccess], r14
0x1800563d8  lea     r8, [rsp+190h+var_130]
0x1800563dd  lea     rdx, aPassword; "password"
0x1800563e4  mov     rax, [rcx]
0x1800563e7  mov     rax, [rax+40h]
0x1800563eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563f0  mov     esi, eax
0x1800563f2  test    eax, eax
0x1800563f4  js      loc_180056666
0x1800563fa  mov     rdx, [rsp+190h+var_140]; struct INativePropertyException *
0x1800563ff  test    rdx, rdx
0x180056402  jz      short loc_180056416
0x180056404  mov     rcx, r13; this
0x180056407  call    ?CopyPropertyException@PARSE_ERROR_INFO@@QEAAJPEAVINativePropertyException@@@Z; PARSE_ERROR_INFO::CopyPropertyException(INativePropertyException *)
0x18005640c  mov     esi, 8007000Dh
0x180056411  jmp     loc_180056666
0x180056416  mov     rcx, [r15+8]
0x18005641a  lea     r8, [rsp+190h+var_150]
0x18005641f  add     rcx, 10h
0x180056423  mov     qword ptr [rsp+190h+dwDesiredAccess], r14
0x180056428  xor     r9d, r9d
0x18005642b  lea     rdx, aLogonmethod; "logonMethod"
0x180056432  mov     rax, [rcx]
0x180056435  mov     rax, [rax+30h]
0x180056439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005643e  mov     esi, eax
0x180056440  test    eax, eax
0x180056442  js      loc_180056666
0x180056448  lea     rdx, Control; "/\\"
0x18005644f  mov     rcx, rdi; String
0x180056452  call    cs:__imp_wcspbrk
0x180056458  mov     rbx, rax
0x18005645b  test    rax, rax
0x18005645e  jnz     short loc_18005646C
0x180056460  mov     rbx, rdi
0x180056463  lea     r8, asc_180060C9C; "."
0x18005646a  jmp     short loc_18005649D
0x18005646c  mov     r8, rbx
0x18005646f  lea     rcx, [rbp+90h+var_110]
0x180056473  sub     r8, rdi
0x180056476  mov     rdx, rdi
0x180056479  sar     r8, 1
0x18005647c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180056482  mov     esi, eax
0x180056484  test    eax, eax
0x180056486  js      loc_180056666
0x18005648c  lea     rcx, [rbp+90h+var_110]
0x180056490  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180056496  mov     r8, rax; unsigned __int16 *
0x180056499  add     rbx, 2
0x18005649d  mov     ecx, [rsp+190h+var_150]
0x1800564a1  mov     edi, 3
0x1800564a6  test    ecx, ecx
0x1800564a8  jz      short loc_1800564CD
0x1800564aa  sub     ecx, 1
0x1800564ad  jz      short loc_1800564C6
0x1800564af  sub     ecx, 1
0x1800564b2  jz      short loc_1800564C2
0x1800564b4  cmp     ecx, 1
0x1800564b7  jnz     loc_18005640C
0x1800564bd  lea     eax, [rdi+5]
0x1800564c0  jmp     short loc_1800564D2
0x1800564c2  mov     eax, edi
0x1800564c4  jmp     short loc_1800564D2
0x1800564c6  mov     eax, 4
0x1800564cb  jmp     short loc_1800564D2
0x1800564cd  mov     eax, 2
0x1800564d2  mov     r9, [rsp+190h+var_130]; unsigned __int16 *
0x1800564d7  lea     rcx, [rsp+190h+var_14C]
0x1800564dc  mov     qword ptr [rsp+190h+dwOptions], rcx; unsigned int *
0x1800564e1  mov     rdx, rbx; unsigned __int16 *
0x1800564e4  lea     rcx, [rsp+190h+var_148]; this
0x1800564e9  mov     [rsp+190h+var_150], eax
0x1800564ed  mov     qword ptr [rsp+190h+bInheritHandle], rcx; struct TOKEN_CACHE_ENTRY **
0x1800564f2  mov     [rsp+190h+dwDesiredAccess], eax; unsigned int
0x1800564f6  call    ?GetCachedToken@TOKEN_CACHE@@QEAAJPEAG00KPEAPEAVTOKEN_CACHE_ENTRY@@PEAK@Z; TOKEN_CACHE::GetCachedToken(ushort *,ushort *,ushort *,ulong,TOKEN_CACHE_ENTRY * *,ulong *)
0x1800564fb  mov     r14, [rsp+190h+var_148]
0x180056500  mov     esi, eax
0x180056502  test    eax, eax
0x180056504  js      loc_1800565BD
0x18005650a  mov     eax, [rsp+190h+var_14C]
0x18005650e  test    eax, eax
0x180056510  jnz     loc_1800565AE
0x180056516  call    cs:__imp_GetCurrentProcess
0x18005651c  mov     rcx, r14; this
0x18005651f  mov     rdi, rax
0x180056522  call    ?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)
0x180056527  mov     rbx, rax
0x18005652a  call    cs:__imp_GetCurrentProcess
0x180056530  mov     [rsp+190h+dwOptions], 2; dwOptions
0x180056538  mov     r9, r12; lpTargetHandle
0x18005653b  mov     rcx, rax; hSourceProcessHandle
0x18005653e  mov     [rsp+190h+bInheritHandle], 0; bInheritHandle
0x180056546  mov     r8, rdi; hTargetProcessHandle
0x180056549  mov     [rsp+190h+dwDesiredAccess], 0; dwDesiredAccess
0x180056551  mov     rdx, rbx; hSourceHandle
0x180056554  call    cs:__imp_DuplicateHandle
0x18005655a  test    eax, eax
0x18005655c  jnz     short loc_18005657C
0x18005655e  call    cs:__imp_GetLastError
0x180056564  mov     esi, eax
0x180056566  test    eax, eax
0x180056568  jle     loc_180056656
0x18005656e  movzx   esi, ax
0x180056571  or      esi, 80070000h
0x180056577  jmp     loc_180056656
0x18005657c  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 1
0x180056583  jz      loc_180056656
0x180056589  mov     rbx, [r12]
0x18005658d  mov     rcx, r14; this
0x180056590  call    ?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ; TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)
0x180056595  mov     r9, rax
0x180056598  mov     qword ptr [rsp+190h+dwDesiredAccess], rbx
0x18005659d  lea     r8, aConfigVdirGetu; "CONFIG_VDIR::GetUserToken"
0x1800565a4  call    McTemplateU0zpp_EtwEventWriteTransfer
0x1800565a9  jmp     loc_180056656
0x1800565ae  jg      short loc_1800565B4
0x1800565b0  mov     esi, eax
0x1800565b2  jmp     short loc_1800565BD
0x1800565b4  movzx   esi, ax
0x1800565b7  or      esi, 80070000h
0x1800565bd  mov     rcx, [r15+8]
0x1800565c1  lea     r8, [rsp+190h+var_148]
0x1800565c6  add     rcx, 10h
0x1800565ca  mov     [rsp+190h+var_148], 0
0x1800565d3  xorps   xmm0, xmm0
0x1800565d6  mov     qword ptr [rsp+190h+dwDesiredAccess], 0
0x1800565df  movups  [rsp+190h+var_120], xmm0
0x1800565e4  xor     r9d, r9d
0x1800565e7  lea     rdx, aPhysicalpath; "physicalPath"
0x1800565ee  mov     rax, [rcx]
0x1800565f1  mov     rax, [rax+40h]
0x1800565f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565fa  mov     rax, [rsp+190h+var_148]
0x1800565ff  lea     rcx, [r13+20h]; this
0x180056603  mov     rdx, [rsp+190h+var_128]; unsigned __int16 *
0x180056608  mov     qword ptr [rsp+190h+var_120], rax
0x18005660d  mov     rax, [rsp+190h+String]
0x180056612  mov     qword ptr [rsp+190h+var_120+8], rax
0x180056617  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x18005661c  mov     rdx, [r15+8]
0x180056620  mov     r9d, 0C0000AB0h
0x180056626  mov     r8d, edi
0x180056629  mov     rcx, r13
0x18005662c  mov     rax, [rdx+38h]
0x180056630  mov     [rsp+190h+var_158], rax
0x180056635  mov     eax, [rdx+40h]
0x180056638  mov     edx, esi
0x18005663a  mov     qword ptr [rsp+190h+dwOptions], 0
0x180056643  mov     [rsp+190h+bInheritHandle], eax
0x180056647  lea     rax, [rsp+190h+var_120]
0x18005664c  mov     qword ptr [rsp+190h+dwDesiredAccess], rax
0x180056651  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180056656  test    r14, r14
0x180056659  jz      short loc_180056663
0x18005665b  mov     rcx, r14; this
0x18005665e  call    ?DereferenceCacheEntry@TOKEN_CACHE_ENTRY@@QEAAXXZ; TOKEN_CACHE_ENTRY::DereferenceCacheEntry(void)
0x180056663  xor     r14d, r14d
0x180056666  mov     rcx, [rsp+190h+var_140]
0x18005666b  test    rcx, rcx
0x18005666e  jz      short loc_180056681
0x180056670  mov     rax, [rcx]
0x180056673  mov     rax, [rax+10h]
0x180056677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005667c  mov     [rsp+190h+var_140], r14
0x180056681  lea     rcx, [rbp+90h+var_110]
0x180056685  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005668b  mov     eax, esi
0x18005668d  mov     rcx, [rbp+90h+var_50]
0x180056691  xor     rcx, rsp; StackCookie
0x180056694  call    __security_check_cookie
0x180056699  add     rsp, 158h
0x1800566a0  pop     r15
0x1800566a2  pop     r14
0x1800566a4  pop     r13
0x1800566a6  pop     r12
0x1800566a8  pop     rdi
0x1800566a9  pop     rsi
0x1800566aa  pop     rbx
0x1800566ab  pop     rbp
0x1800566ac  retn
```
