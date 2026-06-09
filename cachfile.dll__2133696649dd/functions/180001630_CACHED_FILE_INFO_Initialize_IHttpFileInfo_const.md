# CACHED_FILE_INFO::Initialize(IHttpFileInfo const *)

- ea: `0x180001630`
- end: `0x1800019b0`
- name: `?Initialize@CACHED_FILE_INFO@@QEAAJPEBVIHttpFileInfo@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(CACHED_FILE_INFO *__hidden this, const struct IHttpFileInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800013f0`

## callees

- `0x180001630`
- `0x1800019c0`
- `0x180001ab0`
- `0x180003c32`
- `0x180003c70`
- `0x180004010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000190e`
- `msvcrt!wcsrchr` at `0x18000190e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000199e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000199e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800016a7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800016a7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001974`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001974`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001755`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001755`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000195f`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000195f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000184f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001921`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000184f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018cb`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018d5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800018e7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001921`

## pseudocode

```c
__int64 __fastcall CACHED_FILE_INFO::Initialize(CACHED_FILE_INFO *this, const struct IHttpFileInfo *a2)
{
  __int64 v4; // rdi
  unsigned __int16 *Str; // rbx
  int FileIntoMemoryCache; // ebx
  void *v7; // rax
  const unsigned __int16 *v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rsi
  char *v11; // rax
  __int64 v12; // rdi
  char *v13; // r8
  __int64 v14; // rdx
  unsigned int v15; // ebp
  unsigned int v16; // esi
  char *v17; // rcx
  char *v18; // rax
  char *v19; // rdx
  char *v20; // rcx
  unsigned __int64 v22; // rbx
  void *v23; // rax
  FILE_CACHE *v24; // rcx
  const wchar_t *v25; // rbp
  wchar_t *v26; // rax
  __int64 v27; // rsi
  _BYTE v28[64]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v29[256]; // [rsp+70h] [rbp-238h] BYREF

  v4 = (*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 136LL))(a2);
  Str = (unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 144LL))(a2);
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v28, v29, 0x100u);
  if ( !Str || ((*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 56LL))(a2) & 0x10) != 0 )
  {
    v25 = (const wchar_t *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 88LL))(a2);
    v26 = wcsrchr(v25, 0x5Cu);
    if ( !v26 )
    {
      STRU::~STRU((STRU *)v28);
      return 2147942487LL;
    }
    v27 = v26 - v25;
    if ( v27 >= 4 || ((*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 56LL))(a2) & 0x10) == 0 )
    {
      FileIntoMemoryCache = STRU::Copy((STRU *)v28, v25, v27);
      if ( FileIntoMemoryCache < 0 )
        goto LABEL_28;
      Str = STRU::QueryStr((STRU *)v28);
    }
  }
  if ( *Str != 92 || Str[1] != 92 || *((_BYTE *)g_pFileCache + 66) )
  {
    FileIntoMemoryCache = (*(__int64 (__fastcall **)(struct IHttpServer *, unsigned __int16 *, __int64, char *))(*(_QWORD *)g_pGlobalInfo + 192LL))(
                            g_pGlobalInfo,
                            Str,
                            v4,
                            (char *)this + 328);
    if ( FileIntoMemoryCache >= 0 )
      goto LABEL_5;
LABEL_28:
    STRU::~STRU((STRU *)v28);
    return (unsigned int)FileIntoMemoryCache;
  }
  *((_DWORD *)this + 85) = GetTickCount();
LABEL_5:
  if ( ((*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 56LL))(a2) & 0x10) == 0 )
  {
    (*(void (__fastcall **)(const struct IHttpFileInfo *, char *))(*(_QWORD *)a2 + 64LL))(a2, (char *)this + 352);
    v22 = *((_QWORD *)this + 44);
    v23 = (void *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 80LL))(a2);
    FileIntoMemoryCache = FILE_CACHE::ReadFileIntoMemoryCache(v24, v23, v22, (void **)this + 45);
    if ( FileIntoMemoryCache < 0 )
      goto LABEL_28;
  }
  v7 = (void *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 80LL))(a2);
  FileIntoMemoryCache = CACHED_FILE_INFO::ReadSecurityDescriptor(this, v7);
  if ( FileIntoMemoryCache < 0 )
    goto LABEL_28;
  v8 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 88LL))(a2);
  FileIntoMemoryCache = STRU::Copy((CACHED_FILE_INFO *)((char *)this + 16), v8);
  if ( FileIntoMemoryCache < 0 )
    goto LABEL_28;
  (*(void (__fastcall **)(const struct IHttpFileInfo *, char *))(*(_QWORD *)a2 + 104LL))(a2, (char *)this + 344);
  *((_DWORD *)this + 84) = (*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 56LL))(a2);
  v9 = 2147483646;
  v10 = 2147483646;
  v11 = (char *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *, char *))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  (char *)this + 368);
  v12 = 30;
  v13 = (char *)this + 370;
  v14 = 30;
  do
  {
    if ( !v10 )
      break;
    if ( !*v11 )
      break;
    *v13++ = *v11++;
    --v10;
    --v14;
  }
  while ( v14 );
  v15 = -2147024774;
  v16 = -2147024774;
  if ( v14 )
    v16 = 0;
  v17 = v13 - 1;
  if ( v14 )
    v17 = v13;
  *v17 = 0;
  if ( v14 )
  {
    v18 = (char *)(*(__int64 (__fastcall **)(const struct IHttpFileInfo *))(*(_QWORD *)a2 + 112LL))(a2);
    v19 = (char *)this + 400;
    do
    {
      if ( !v9 )
        break;
      if ( !*v18 )
        break;
      *v19++ = *v18++;
      --v9;
      --v12;
    }
    while ( v12 );
    if ( v12 )
      v15 = 0;
    v20 = v19 - 1;
    if ( v12 )
      v20 = v19;
    *v20 = 0;
    STRU::~STRU((STRU *)v28);
    if ( v12 )
      return 0;
    else
      return v15;
  }
  else
  {
    STRU::~STRU((STRU *)v28);
    return v16;
  }
}

```

## disassembly

```asm
0x180001630  mov     [rsp+arg_10], rbx
0x180001635  push    rbp
0x180001636  push    rsi
0x180001637  push    rdi
0x180001638  push    r14
0x18000163a  push    r15
0x18000163c  sub     rsp, 280h
0x180001643  mov     rax, cs:__security_cookie
0x18000164a  xor     rax, rsp
0x18000164d  mov     [rsp+2A8h+var_38], rax
0x180001655  mov     rax, [rdx]
0x180001658  mov     r15, rcx
0x18000165b  mov     rcx, rdx
0x18000165e  mov     r14, rdx
0x180001661  mov     rax, [rax+88h]
0x180001668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000166d  mov     rdx, [r14]
0x180001670  mov     rdi, rax
0x180001673  mov     rcx, r14
0x180001676  mov     rax, [rdx+90h]
0x18000167d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001682  xor     edx, edx; Val
0x180001684  lea     rcx, [rsp+2A8h+var_238]; void *
0x180001689  mov     r8d, 200h; Size
0x18000168f  mov     rbx, rax
0x180001692  call    memset_0
0x180001697  mov     r8d, 100h
0x18000169d  lea     rdx, [rsp+2A8h+var_238]
0x1800016a2  lea     rcx, [rsp+2A8h+var_278]
0x1800016a7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800016ad  test    rbx, rbx
0x1800016b0  jz      loc_1800018F4
0x1800016b6  mov     rcx, [r14]
0x1800016b9  mov     rax, [rcx+38h]
0x1800016bd  mov     rcx, r14
0x1800016c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016c5  test    al, 10h
0x1800016c7  jnz     loc_1800018F4
0x1800016cd  cmp     word ptr [rbx], 5Ch ; '\'
0x1800016d1  jz      loc_180001982
0x1800016d7  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800016de  lea     r9, [r15+148h]
0x1800016e5  mov     r8, rdi
0x1800016e8  mov     rdx, rbx
0x1800016eb  mov     rax, [rcx]
0x1800016ee  mov     rax, [rax+0C0h]
0x1800016f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016fa  mov     ebx, eax
0x1800016fc  test    eax, eax
0x1800016fe  js      loc_1800018C6
0x180001704  mov     rax, [r14]
0x180001707  mov     rcx, r14
0x18000170a  mov     rax, [rax+38h]
0x18000170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001713  test    al, 10h
0x180001715  jz      loc_18000187E
0x18000171b  mov     rax, [r14]
0x18000171e  mov     rcx, r14
0x180001721  mov     rax, [rax+50h]
0x180001725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000172a  mov     rdx, rax; void *
0x18000172d  mov     rcx, r15; this
0x180001730  call    ?ReadSecurityDescriptor@CACHED_FILE_INFO@@AEAAJPEAX@Z; CACHED_FILE_INFO::ReadSecurityDescriptor(void *)
0x180001735  mov     ebx, eax
0x180001737  test    eax, eax
0x180001739  js      loc_1800018C6
0x18000173f  mov     rax, [r14]
0x180001742  mov     rcx, r14
0x180001745  mov     rax, [rax+58h]
0x180001749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000174e  lea     rcx, [r15+10h]
0x180001752  mov     rdx, rax
0x180001755  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000175b  mov     ebx, eax
0x18000175d  test    eax, eax
0x18000175f  js      loc_1800018C6
0x180001765  mov     rax, [r14]
0x180001768  lea     rdx, [r15+158h]
0x18000176f  mov     rcx, r14
0x180001772  mov     rax, [rax+68h]
0x180001776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000177b  mov     rax, [r14]
0x18000177e  mov     rcx, r14
0x180001781  mov     rax, [rax+38h]
0x180001785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000178a  mov     [r15+150h], eax
0x180001791  lea     rdx, [r15+170h]
0x180001798  mov     rax, [r14]
0x18000179b  mov     ebx, 7FFFFFFEh
0x1800017a0  mov     rcx, r14
0x1800017a3  mov     esi, ebx
0x1800017a5  mov     rax, [rax+60h]
0x1800017a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017ae  mov     edi, 1Eh
0x1800017b3  lea     r8, [r15+172h]
0x1800017ba  mov     edx, edi
0x1800017bc  nop     dword ptr [rax+00h]
0x1800017c0  test    rsi, rsi
0x1800017c3  jz      short loc_1800017DE
0x1800017c5  movzx   ecx, byte ptr [rax]
0x1800017c8  test    cl, cl
0x1800017ca  jz      short loc_1800017DE
0x1800017cc  mov     [r8], cl
0x1800017cf  inc     rax
0x1800017d2  inc     r8
0x1800017d5  dec     rsi
0x1800017d8  sub     rdx, 1
0x1800017dc  jnz     short loc_1800017C0
0x1800017de  xor     ecx, ecx
0x1800017e0  mov     ebp, 8007007Ah
0x1800017e5  test    rdx, rdx
0x1800017e8  mov     esi, ebp
0x1800017ea  cmovnz  esi, ecx
0x1800017ed  lea     rcx, [r8-1]
0x1800017f1  cmovnz  rcx, r8
0x1800017f5  mov     byte ptr [rcx], 0
0x1800017f8  jz      loc_1800018E2
0x1800017fe  mov     rax, [r14]
0x180001801  mov     rcx, r14
0x180001804  mov     rax, [rax+70h]
0x180001808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000180d  lea     rdx, [r15+190h]
0x180001814  test    rbx, rbx
0x180001817  jz      short loc_180001831
0x180001819  movzx   ecx, byte ptr [rax]
0x18000181c  test    cl, cl
0x18000181e  jz      short loc_180001831
0x180001820  mov     [rdx], cl
0x180001822  inc     rax
0x180001825  inc     rdx
0x180001828  dec     rbx
0x18000182b  sub     rdi, 1
0x18000182f  jnz     short loc_180001814
0x180001831  xor     ecx, ecx
0x180001833  test    rdi, rdi
0x180001836  cmovnz  ebp, ecx
0x180001839  lea     rcx, [rdx-1]
0x18000183d  cmovnz  rcx, rdx
0x180001841  mov     byte ptr [rcx], 0
0x180001844  lea     rcx, [rsp+2A8h+var_278]
0x180001849  jnz     loc_1800018D5
0x18000184f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001855  mov     eax, ebp
0x180001857  mov     rcx, [rsp+2A8h+var_38]
0x18000185f  xor     rcx, rsp; StackCookie
0x180001862  call    __security_check_cookie
0x180001867  mov     rbx, [rsp+2A8h+arg_10]
0x18000186f  add     rsp, 280h
0x180001876  pop     r15
0x180001878  pop     r14
0x18000187a  pop     rdi
0x18000187b  pop     rsi
0x18000187c  pop     rbp
0x18000187d  retn
0x18000187e  mov     rax, [r14]
0x180001881  lea     rdx, [r15+160h]
0x180001888  mov     rcx, r14
0x18000188b  mov     rax, [rax+40h]
0x18000188f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001894  mov     rax, [r14]
0x180001897  mov     rcx, r14
0x18000189a  mov     rbx, [r15+160h]
0x1800018a1  mov     rax, [rax+50h]
0x1800018a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018aa  lea     r9, [r15+168h]; void **
0x1800018b1  mov     r8, rbx; unsigned __int64
0x1800018b4  mov     rdx, rax; void *
0x1800018b7  call    ?ReadFileIntoMemoryCache@FILE_CACHE@@QEAAJPEAX_KPEAPEAX@Z; FILE_CACHE::ReadFileIntoMemoryCache(void *,unsigned __int64,void * *)
0x1800018bc  mov     ebx, eax
0x1800018be  test    eax, eax
0x1800018c0  jns     loc_18000171B
0x1800018c6  lea     rcx, [rsp+2A8h+var_278]
0x1800018cb  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800018d1  mov     eax, ebx
0x1800018d3  jmp     short loc_180001857
0x1800018d5  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800018db  xor     eax, eax
0x1800018dd  jmp     loc_180001857
0x1800018e2  lea     rcx, [rsp+2A8h+var_278]
0x1800018e7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800018ed  mov     eax, esi
0x1800018ef  jmp     loc_180001857
0x1800018f4  mov     rax, [r14]
0x1800018f7  mov     rcx, r14
0x1800018fa  mov     rax, [rax+58h]
0x1800018fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001903  mov     edx, 5Ch ; '\'; Ch
0x180001908  mov     rcx, rax; Str
0x18000190b  mov     rbp, rax
0x18000190e  call    cs:__imp_wcsrchr
0x180001914  mov     rsi, rax
0x180001917  test    rax, rax
0x18000191a  jnz     short loc_180001931
0x18000191c  lea     rcx, [rsp+2A8h+var_278]
0x180001921  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001927  mov     eax, 80070057h
0x18000192c  jmp     loc_180001857
0x180001931  sub     rsi, rbp
0x180001934  sar     rsi, 1
0x180001937  cmp     rsi, 4
0x18000193b  jge     short loc_180001954
0x18000193d  mov     rax, [r14]
0x180001940  mov     rcx, r14
0x180001943  mov     rax, [rax+38h]
0x180001947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000194c  test    al, 10h
0x18000194e  jnz     loc_1800016CD
0x180001954  mov     r8d, esi
0x180001957  lea     rcx, [rsp+2A8h+var_278]
0x18000195c  mov     rdx, rbp
0x18000195f  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180001965  lea     rcx, [rsp+2A8h+var_278]
0x18000196a  mov     ebx, eax
0x18000196c  test    eax, eax
0x18000196e  js      loc_1800018CB
0x180001974  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000197a  mov     rbx, rax
0x18000197d  jmp     loc_1800016CD
0x180001982  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180001987  jnz     loc_1800016D7
0x18000198d  mov     rax, cs:?g_pFileCache@@3PEAVFILE_CACHE@@EA; FILE_CACHE * g_pFileCache
0x180001994  cmp     byte ptr [rax+42h], 0
0x180001998  jnz     loc_1800016D7
0x18000199e  call    cs:__imp_GetTickCount
0x1800019a4  mov     [r15+154h], eax
0x1800019ab  jmp     loc_180001704
```
