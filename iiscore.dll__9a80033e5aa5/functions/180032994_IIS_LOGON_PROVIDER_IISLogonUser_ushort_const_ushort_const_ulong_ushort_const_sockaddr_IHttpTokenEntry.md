# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x180032994`
- end: `0x180032d07`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001b8a0`

## callees

- `0x180019558`
- `0x18001a2a8`
- `0x180031d28`
- `0x180031eb4`
- `0x180032994`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!wcschr` at `0x180032ac0`
- `msvcrt!wcschr` at `0x180032ac0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032cab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032cab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032bd9`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180032b54`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180032b54`
- `SspiCli!LsaFreeReturnBuffer` at `0x180032cbb`
- `SspiCli!LsaFreeReturnBuffer` at `0x180032cbb`
- `SspiCli!SeciFreeCallContext` at `0x180032cc8`
- `SspiCli!SeciFreeCallContext` at `0x180032cc8`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180032c3a`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180032c3a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180032cd2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180032cdc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180032cd2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180032cdc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032aa2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032ab4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032adf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032af7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b0d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b70`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032aa2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032ab4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032adf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032af7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b0d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b25`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180032b70`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180032a1a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180032a45`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180032a1a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180032a45`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180032bb3`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180032bb3`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::IISLogonUser(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        struct sockaddr *a6,
        struct IHttpTokenEntry **a7)
{
  signed int v11; // ebx
  const wchar_t *v12; // rax
  unsigned int v13; // esi
  const WCHAR *Str; // rax
  __int64 v15; // rdx
  unsigned int i; // ebx
  const WCHAR *v17; // rax
  signed int LastError; // eax
  signed int v19; // eax
  _DWORD *v20; // rdi
  int phToken; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh] BYREF
  DWORD pdwProfileLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpszDomain; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v28; // [rsp+70h] [rbp-90h]
  PVOID Buffer; // [rsp+78h] [rbp-88h] BYREF
  struct IHttpTokenEntry **v30; // [rsp+80h] [rbp-80h]
  _BYTE v31[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v33[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v34[256]; // [rsp+300h] [rbp+200h] BYREF

  v30 = a7;
  hObject = 0;
  Buffer = 0;
  pdwProfileLength = 0;
  v28 = 0;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v32, v33, 0x100u);
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v31, v34, 0x100u);
  v24 = 0;
  v23 = 0;
  if ( !a7 )
  {
    v11 = -2147024809;
    goto LABEL_41;
  }
  v11 = IIS_LOGON_PROVIDER::DetermineUserAndDomain(this, a2, a5, (struct STRU *)v32, (struct STRU *)v31, &v24);
  if ( v11 < 0 )
    goto LABEL_35;
  if ( v24 || !*STRU::QueryStr((STRU *)v31) || (v12 = STRU::QueryStr((STRU *)v32), !wcschr(v12, 0x40u)) )
  {
    v13 = 1;
    if ( *STRU::QueryStr((STRU *)v31) )
      Str = STRU::QueryStr((STRU *)v31);
    else
      Str = 0;
    goto LABEL_13;
  }
  v13 = 2;
  if ( *((_DWORD *)this + 641) )
  {
    Str = STRU::QueryStr((STRU *)v31);
    v28 = 0;
LABEL_13:
    lpszDomain = Str;
    goto LABEL_14;
  }
  lpszDomain = 0;
  v28 = STRU::QueryStr((STRU *)v31);
LABEL_14:
  if ( !a6 )
    goto LABEL_20;
  if ( a6->sa_family == 2 )
  {
    v15 = 16;
  }
  else
  {
    if ( a6->sa_family != 23 )
      goto LABEL_20;
    v15 = 28;
  }
  v11 = SeciAllocateAndSetIPAddress(a6, v15, &v23);
  if ( v11 >= 0 )
  {
LABEL_20:
    for ( i = 0; i < v13; ++i )
    {
      v17 = STRU::QueryStr((STRU *)v32);
      if ( LogonUserExW(v17, (&lpszDomain)[i], a3, a4, 0, &hObject, 0, &Buffer, &pdwProfileLength, 0) )
      {
        v20 = operator new(0x108u);
        if ( !v20 )
        {
          v11 = -2147024888;
          goto LABEL_35;
        }
        v20[3] = 1;
        *(_QWORD *)v20 = &TOKEN_ENTRY::`vftable';
        *((_QWORD *)v20 + 2) = 0;
        *((_QWORD *)v20 + 3) = 0;
        v20[29] = 0;
        TOKEN_KEY::TOKEN_KEY((TOKEN_KEY *)(v20 + 30));
        CSmallSpinLock::CSmallSpinLock((CSmallSpinLock *)(v20 + 62));
        v20[65] &= 0xFFFFFFFC;
        v20[63] = 0;
        v20[64] = 2;
        v20[2] = 1313558356;
        v11 = TOKEN_ENTRY::Create((TOKEN_ENTRY *)v20, hObject, a2, a3, a4, phToken);
        if ( v11 < 0 )
        {
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v20 + 16LL))(v20);
          goto LABEL_35;
        }
        *v30 = (struct IHttpTokenEntry *)v20;
        goto LABEL_37;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147023570 )
        break;
    }
    v19 = GetLastError();
    v11 = v19;
    if ( v19 > 0 )
      v11 = (unsigned __int16)v19 | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_37;
  }
LABEL_35:
  if ( hObject )
    CloseHandle(hObject);
LABEL_37:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v23 )
    SeciFreeCallContext();
LABEL_41:
  STRU::~STRU((STRU *)v31);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180032994  push    rbp
0x180032996  push    rbx
0x180032997  push    rsi
0x180032998  push    rdi
0x180032999  push    r12
0x18003299b  push    r13
0x18003299d  push    r14
0x18003299f  push    r15
0x1800329a1  lea     rbp, [rsp-418h]
0x1800329a9  sub     rsp, 518h
0x1800329b0  mov     rax, cs:__security_cookie
0x1800329b7  xor     rax, rsp
0x1800329ba  mov     [rbp+450h+var_50], rax
0x1800329c1  mov     rsi, [rbp+450h+arg_30]
0x1800329c8  xor     eax, eax
0x1800329ca  mov     rdi, [rbp+450h+arg_28]
0x1800329d1  mov     r12, r8
0x1800329d4  mov     rbx, [rbp+450h+arg_20]
0x1800329db  mov     r15, rdx
0x1800329de  mov     r14, rcx
0x1800329e1  mov     [rbp+450h+var_4D0], rsi
0x1800329e5  xor     edx, edx; Val
0x1800329e7  mov     [rsp+550h+hObject], rax
0x1800329ec  mov     r8d, 200h; Size
0x1800329f2  mov     [rsp+550h+Buffer], rax
0x1800329f7  lea     rcx, [rbp+450h+var_450]; void *
0x1800329fb  mov     [rsp+550h+var_4F8], eax
0x1800329ff  mov     [rsp+550h+var_4E0], rax
0x180032a04  mov     r13d, r9d
0x180032a07  call    memset_0
0x180032a0c  mov     r8d, 100h
0x180032a12  lea     rdx, [rbp+450h+var_450]
0x180032a16  lea     rcx, [rbp+450h+var_490]
0x180032a1a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180032a20  xor     edx, edx; Val
0x180032a22  lea     rcx, [rbp+450h+var_250]; void *
0x180032a29  mov     r8d, 200h; Size
0x180032a2f  call    memset_0
0x180032a34  mov     r8d, 100h
0x180032a3a  lea     rdx, [rbp+450h+var_250]
0x180032a41  lea     rcx, [rbp+450h+var_4C8]
0x180032a45  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180032a4b  xor     eax, eax
0x180032a4d  mov     [rsp+550h+var_4FC], eax
0x180032a51  mov     [rsp+550h+var_500], eax
0x180032a55  test    rsi, rsi
0x180032a58  jnz     short loc_180032A64
0x180032a5a  mov     ebx, 80070057h
0x180032a5f  jmp     loc_180032CCE
0x180032a64  lea     rax, [rsp+550h+var_4FC]
0x180032a69  mov     r8, rbx; unsigned __int16 *
0x180032a6c  mov     [rsp+550h+phToken], rax; int *
0x180032a71  lea     r9, [rbp+450h+var_490]; struct STRU *
0x180032a75  lea     rax, [rbp+450h+var_4C8]
0x180032a79  mov     rdx, r15; unsigned __int16 *
0x180032a7c  mov     rcx, r14; this
0x180032a7f  mov     qword ptr [rsp+550h+dwLogonProvider], rax; struct STRU *
0x180032a84  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x180032a89  xor     esi, esi
0x180032a8b  mov     ebx, eax
0x180032a8d  test    eax, eax
0x180032a8f  js      loc_180032C9E
0x180032a95  lea     ebx, [rsi+2]
0x180032a98  cmp     [rsp+550h+var_4FC], esi
0x180032a9c  jnz     short loc_180032B04
0x180032a9e  lea     rcx, [rbp+450h+var_4C8]
0x180032aa2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032aa8  cmp     [rax], si
0x180032aab  jz      short loc_180032B04
0x180032aad  lea     rcx, [rbp+450h+var_490]
0x180032ab1  lea     ebx, [rsi+40h]
0x180032ab4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032aba  mov     rcx, rax; Str
0x180032abd  movzx   edx, bx; Ch
0x180032ac0  call    cs:__imp_wcschr
0x180032ac6  lea     ebx, [rsi+2]
0x180032ac9  test    rax, rax
0x180032acc  jz      short loc_180032B04
0x180032ace  xor     eax, eax
0x180032ad0  lea     rcx, [rbp+450h+var_4C8]
0x180032ad4  mov     esi, ebx
0x180032ad6  cmp     [r14+0A04h], eax
0x180032add  jz      short loc_180032AEF
0x180032adf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032ae5  xor     r14d, r14d
0x180032ae8  mov     [rsp+550h+var_4E0], r14
0x180032aed  jmp     short loc_180032B2B
0x180032aef  xor     r14d, r14d
0x180032af2  mov     [rsp+550h+lpszDomain], r14
0x180032af7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032afd  mov     [rsp+550h+var_4E0], rax
0x180032b02  jmp     short loc_180032B30
0x180032b04  lea     rcx, [rbp+450h+var_4C8]
0x180032b08  mov     esi, 1
0x180032b0d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032b13  xor     r14d, r14d
0x180032b16  cmp     [rax], r14w
0x180032b1a  jnz     short loc_180032B21
0x180032b1c  mov     eax, r14d
0x180032b1f  jmp     short loc_180032B2B
0x180032b21  lea     rcx, [rbp+450h+var_4C8]
0x180032b25  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032b2b  mov     [rsp+550h+lpszDomain], rax
0x180032b30  test    rdi, rdi
0x180032b33  jz      short loc_180032B64
0x180032b35  cmp     [rdi], bx
0x180032b38  jnz     short loc_180032B41
0x180032b3a  mov     edx, 10h
0x180032b3f  jmp     short loc_180032B4C
0x180032b41  cmp     word ptr [rdi], 17h
0x180032b45  jnz     short loc_180032B64
0x180032b47  mov     edx, 1Ch
0x180032b4c  lea     r8, [rsp+550h+var_500]
0x180032b51  mov     rcx, rdi
0x180032b54  call    cs:__imp_SeciAllocateAndSetIPAddress
0x180032b5a  mov     ebx, eax
0x180032b5c  test    eax, eax
0x180032b5e  js      loc_180032CA1
0x180032b64  mov     ebx, r14d
0x180032b67  mov     edi, 80070000h
0x180032b6c  lea     rcx, [rbp+450h+var_490]
0x180032b70  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180032b76  mov     [rsp+550h+pQuotaLimits], r14; pQuotaLimits
0x180032b7b  lea     rcx, [rsp+550h+var_4F8]
0x180032b80  mov     [rsp+550h+pdwProfileLength], rcx; pdwProfileLength
0x180032b85  mov     r9d, r13d; dwLogonType
0x180032b88  lea     rcx, [rsp+550h+Buffer]
0x180032b8d  mov     edx, ebx
0x180032b8f  mov     [rsp+550h+ppProfileBuffer], rcx; ppProfileBuffer
0x180032b94  mov     r8, r12; lpszPassword
0x180032b97  lea     rcx, [rsp+550h+hObject]
0x180032b9c  mov     [rsp+550h+ppLogonSid], r14; ppLogonSid
0x180032ba1  mov     [rsp+550h+phToken], rcx; int
0x180032ba6  mov     rcx, rax; lpszUsername
0x180032ba9  mov     rdx, [rsp+rdx*8+550h+lpszDomain]; lpszDomain
0x180032bae  mov     [rsp+550h+dwLogonProvider], r14d; dwLogonProvider
0x180032bb3  call    cs:__imp_LogonUserExW
0x180032bb9  test    eax, eax
0x180032bbb  jnz     short loc_180032BF7
0x180032bbd  call    cs:__imp_GetLastError
0x180032bc3  test    eax, eax
0x180032bc5  jle     short loc_180032BCC
0x180032bc7  movzx   eax, ax
0x180032bca  or      eax, edi
0x180032bcc  cmp     eax, 8007052Eh
0x180032bd1  jnz     short loc_180032BD9
0x180032bd3  inc     ebx
0x180032bd5  cmp     ebx, esi
0x180032bd7  jb      short loc_180032B6C
0x180032bd9  call    cs:__imp_GetLastError
0x180032bdf  mov     ebx, eax
0x180032be1  test    eax, eax
0x180032be3  jle     short loc_180032BEA
0x180032be5  movzx   ebx, ax
0x180032be8  or      ebx, edi
0x180032bea  test    ebx, ebx
0x180032bec  jns     loc_180032CB1
0x180032bf2  jmp     loc_180032CA1
0x180032bf7  mov     ecx, 108h; Size
0x180032bfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032c01  mov     rdi, rax
0x180032c04  test    rax, rax
0x180032c07  jz      loc_180032C97
0x180032c0d  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180032c14  mov     dword ptr [rdi+0Ch], 1
0x180032c1b  lea     rcx, [rdi+78h]; this
0x180032c1f  mov     [rdi], rax
0x180032c22  mov     [rdi+10h], r14
0x180032c26  mov     [rdi+18h], r14
0x180032c2a  mov     [rdi+74h], r14d
0x180032c2e  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x180032c33  lea     rcx, [rdi+0F8h]
0x180032c3a  call    cs:__imp_??0CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::CSmallSpinLock(void)
0x180032c40  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x180032c47  mov     r9, r12; unsigned __int16 *
0x180032c4a  mov     [rdi+0FCh], r14d
0x180032c51  mov     r8, r15; unsigned __int16 *
0x180032c54  mov     dword ptr [rdi+100h], 2
0x180032c5e  mov     rcx, rdi; this
0x180032c61  mov     dword ptr [rdi+8], 4E4B4F54h
0x180032c68  mov     rdx, [rsp+550h+hObject]; void *
0x180032c6d  mov     [rsp+550h+dwLogonProvider], r13d; unsigned int
0x180032c72  call    ?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z; TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)
0x180032c77  mov     ebx, eax
0x180032c79  test    eax, eax
0x180032c7b  jns     short loc_180032C8E
0x180032c7d  mov     rax, [rdi]
0x180032c80  mov     rcx, rdi
0x180032c83  mov     rax, [rax+10h]
0x180032c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c8c  jmp     short loc_180032CA1
0x180032c8e  mov     rax, [rbp+450h+var_4D0]
0x180032c92  mov     [rax], rdi
0x180032c95  jmp     short loc_180032CB1
0x180032c97  mov     ebx, 80070008h
0x180032c9c  jmp     short loc_180032CA1
0x180032c9e  xor     r14d, r14d
0x180032ca1  mov     rcx, [rsp+550h+hObject]; hObject
0x180032ca6  test    rcx, rcx
0x180032ca9  jz      short loc_180032CB1
0x180032cab  call    cs:__imp_CloseHandle
0x180032cb1  mov     rcx, [rsp+550h+Buffer]; Buffer
0x180032cb6  test    rcx, rcx
0x180032cb9  jz      short loc_180032CC1
0x180032cbb  call    cs:__imp_LsaFreeReturnBuffer
0x180032cc1  cmp     [rsp+550h+var_500], r14d
0x180032cc6  jz      short loc_180032CCE
0x180032cc8  call    cs:__imp_SeciFreeCallContext
0x180032cce  lea     rcx, [rbp+450h+var_4C8]
0x180032cd2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180032cd8  lea     rcx, [rbp+450h+var_490]
0x180032cdc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180032ce2  mov     eax, ebx
0x180032ce4  mov     rcx, [rbp+450h+var_50]
0x180032ceb  xor     rcx, rsp; StackCookie
0x180032cee  call    __security_check_cookie
0x180032cf3  add     rsp, 518h
0x180032cfa  pop     r15
0x180032cfc  pop     r14
0x180032cfe  pop     r13
0x180032d00  pop     r12
0x180032d02  pop     rdi
0x180032d03  pop     rsi
0x180032d04  pop     rbx
0x180032d05  pop     rbp
0x180032d06  retn
```
