# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x180035a78`
- end: `0x180035e68`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `1008`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001d0e0`

## callees

- `0x18001ab30`
- `0x18001b8a4`
- `0x180034bd8`
- `0x180034d84`
- `0x180035a78`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!wcschr` at `0x180035bc0`
- `msvcrt!wcschr` at `0x180035bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035ded`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035ded`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035d0f`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180035c72`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x180035c72`
- `SspiCli!LsaFreeReturnBuffer` at `0x180035e03`
- `SspiCli!LsaFreeReturnBuffer` at `0x180035e03`
- `SspiCli!SeciFreeCallContext` at `0x180035e16`
- `SspiCli!SeciFreeCallContext` at `0x180035e16`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180035d76`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180035d76`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035e26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035e36`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035e26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180035e36`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035b96`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035bae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035be5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c1f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c3d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c94`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035b96`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035bae`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035be5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c1f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c3d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180035c94`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180035afe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180035b2f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180035afe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180035b2f`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180035cdd`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180035cdd`

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
0x180035a78  push    rbp
0x180035a7a  push    rbx
0x180035a7b  push    rsi
0x180035a7c  push    rdi
0x180035a7d  push    r12
0x180035a7f  push    r13
0x180035a81  push    r14
0x180035a83  push    r15
0x180035a85  lea     rbp, [rsp-418h]
0x180035a8d  sub     rsp, 518h
0x180035a94  mov     rax, cs:__security_cookie
0x180035a9b  xor     rax, rsp
0x180035a9e  mov     [rbp+450h+var_50], rax
0x180035aa5  mov     rsi, [rbp+450h+arg_30]
0x180035aac  xor     eax, eax
0x180035aae  mov     rdi, [rbp+450h+arg_28]
0x180035ab5  mov     r12, r8
0x180035ab8  mov     rbx, [rbp+450h+arg_20]
0x180035abf  mov     r15, rdx
0x180035ac2  mov     r14, rcx
0x180035ac5  mov     [rbp+450h+var_4D0], rsi
0x180035ac9  xor     edx, edx; Val
0x180035acb  mov     [rsp+550h+hObject], rax
0x180035ad0  mov     r8d, 200h; Size
0x180035ad6  mov     [rsp+550h+Buffer], rax
0x180035adb  lea     rcx, [rbp+450h+var_450]; void *
0x180035adf  mov     [rsp+550h+var_4F8], eax
0x180035ae3  mov     [rsp+550h+var_4E0], rax
0x180035ae8  mov     r13d, r9d
0x180035aeb  call    memset_0
0x180035af0  mov     r8d, 100h
0x180035af6  lea     rdx, [rbp+450h+var_450]
0x180035afa  lea     rcx, [rbp+450h+var_490]
0x180035afe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180035b05  nop     dword ptr [rax+rax+00h]
0x180035b0a  xor     edx, edx; Val
0x180035b0c  lea     rcx, [rbp+450h+var_250]; void *
0x180035b13  mov     r8d, 200h; Size
0x180035b19  call    memset_0
0x180035b1e  mov     r8d, 100h
0x180035b24  lea     rdx, [rbp+450h+var_250]
0x180035b2b  lea     rcx, [rbp+450h+var_4C8]
0x180035b2f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180035b36  nop     dword ptr [rax+rax+00h]
0x180035b3b  xor     eax, eax
0x180035b3d  mov     [rsp+550h+var_4FC], eax
0x180035b41  mov     [rsp+550h+var_500], eax
0x180035b45  test    rsi, rsi
0x180035b48  jnz     short loc_180035B54
0x180035b4a  mov     ebx, 80070057h
0x180035b4f  jmp     loc_180035E22
0x180035b54  lea     rax, [rsp+550h+var_4FC]
0x180035b59  mov     r8, rbx; unsigned __int16 *
0x180035b5c  mov     [rsp+550h+phToken], rax; int *
0x180035b61  lea     r9, [rbp+450h+var_490]; struct STRU *
0x180035b65  lea     rax, [rbp+450h+var_4C8]
0x180035b69  mov     rdx, r15; unsigned __int16 *
0x180035b6c  mov     rcx, r14; this
0x180035b6f  mov     qword ptr [rsp+550h+dwLogonProvider], rax; struct STRU *
0x180035b74  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x180035b79  xor     esi, esi
0x180035b7b  mov     ebx, eax
0x180035b7d  test    eax, eax
0x180035b7f  js      loc_180035DE0
0x180035b85  lea     ebx, [rsi+2]
0x180035b88  cmp     [rsp+550h+var_4FC], esi
0x180035b8c  jnz     loc_180035C16
0x180035b92  lea     rcx, [rbp+450h+var_4C8]
0x180035b96  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035b9d  nop     dword ptr [rax+rax+00h]
0x180035ba2  cmp     [rax], si
0x180035ba5  jz      short loc_180035C16
0x180035ba7  lea     rcx, [rbp+450h+var_490]
0x180035bab  lea     ebx, [rsi+40h]
0x180035bae  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035bb5  nop     dword ptr [rax+rax+00h]
0x180035bba  mov     rcx, rax; Str
0x180035bbd  movzx   edx, bx; Ch
0x180035bc0  call    cs:__imp_wcschr
0x180035bc7  nop     dword ptr [rax+rax+00h]
0x180035bcc  lea     ebx, [rsi+2]
0x180035bcf  test    rax, rax
0x180035bd2  jz      short loc_180035C16
0x180035bd4  xor     eax, eax
0x180035bd6  lea     rcx, [rbp+450h+var_4C8]
0x180035bda  mov     esi, ebx
0x180035bdc  cmp     [r14+0A04h], eax
0x180035be3  jz      short loc_180035BFB
0x180035be5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035bec  nop     dword ptr [rax+rax+00h]
0x180035bf1  xor     r14d, r14d
0x180035bf4  mov     [rsp+550h+var_4E0], r14
0x180035bf9  jmp     short loc_180035C49
0x180035bfb  xor     r14d, r14d
0x180035bfe  mov     [rsp+550h+lpszDomain], r14
0x180035c03  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035c0a  nop     dword ptr [rax+rax+00h]
0x180035c0f  mov     [rsp+550h+var_4E0], rax
0x180035c14  jmp     short loc_180035C4E
0x180035c16  lea     rcx, [rbp+450h+var_4C8]
0x180035c1a  mov     esi, 1
0x180035c1f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035c26  nop     dword ptr [rax+rax+00h]
0x180035c2b  xor     r14d, r14d
0x180035c2e  cmp     [rax], r14w
0x180035c32  jnz     short loc_180035C39
0x180035c34  mov     eax, r14d
0x180035c37  jmp     short loc_180035C49
0x180035c39  lea     rcx, [rbp+450h+var_4C8]
0x180035c3d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035c44  nop     dword ptr [rax+rax+00h]
0x180035c49  mov     [rsp+550h+lpszDomain], rax
0x180035c4e  test    rdi, rdi
0x180035c51  jz      short loc_180035C88
0x180035c53  cmp     [rdi], bx
0x180035c56  jnz     short loc_180035C5F
0x180035c58  mov     edx, 10h
0x180035c5d  jmp     short loc_180035C6A
0x180035c5f  cmp     word ptr [rdi], 17h
0x180035c63  jnz     short loc_180035C88
0x180035c65  mov     edx, 1Ch
0x180035c6a  lea     r8, [rsp+550h+var_500]
0x180035c6f  mov     rcx, rdi
0x180035c72  call    cs:__imp_SeciAllocateAndSetIPAddress
0x180035c79  nop     dword ptr [rax+rax+00h]
0x180035c7e  mov     ebx, eax
0x180035c80  test    eax, eax
0x180035c82  js      loc_180035DE3
0x180035c88  mov     ebx, r14d
0x180035c8b  mov     edi, 80070000h
0x180035c90  lea     rcx, [rbp+450h+var_490]
0x180035c94  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180035c9b  nop     dword ptr [rax+rax+00h]
0x180035ca0  mov     [rsp+550h+pQuotaLimits], r14; pQuotaLimits
0x180035ca5  lea     rcx, [rsp+550h+var_4F8]
0x180035caa  mov     [rsp+550h+pdwProfileLength], rcx; pdwProfileLength
0x180035caf  mov     r9d, r13d; dwLogonType
0x180035cb2  lea     rcx, [rsp+550h+Buffer]
0x180035cb7  mov     edx, ebx
0x180035cb9  mov     [rsp+550h+ppProfileBuffer], rcx; ppProfileBuffer
0x180035cbe  mov     r8, r12; lpszPassword
0x180035cc1  lea     rcx, [rsp+550h+hObject]
0x180035cc6  mov     [rsp+550h+ppLogonSid], r14; ppLogonSid
0x180035ccb  mov     [rsp+550h+phToken], rcx; int
0x180035cd0  mov     rcx, rax; lpszUsername
0x180035cd3  mov     rdx, [rsp+rdx*8+550h+lpszDomain]; lpszDomain
0x180035cd8  mov     [rsp+550h+dwLogonProvider], r14d; dwLogonProvider
0x180035cdd  call    cs:__imp_LogonUserExW
0x180035ce4  nop     dword ptr [rax+rax+00h]
0x180035ce9  test    eax, eax
0x180035ceb  jnz     short loc_180035D33
0x180035ced  call    cs:__imp_GetLastError
0x180035cf4  nop     dword ptr [rax+rax+00h]
0x180035cf9  test    eax, eax
0x180035cfb  jle     short loc_180035D02
0x180035cfd  movzx   eax, ax
0x180035d00  or      eax, edi
0x180035d02  cmp     eax, 8007052Eh
0x180035d07  jnz     short loc_180035D0F
0x180035d09  inc     ebx
0x180035d0b  cmp     ebx, esi
0x180035d0d  jb      short loc_180035C90
0x180035d0f  call    cs:__imp_GetLastError
0x180035d16  nop     dword ptr [rax+rax+00h]
0x180035d1b  mov     ebx, eax
0x180035d1d  test    eax, eax
0x180035d1f  jle     short loc_180035D26
0x180035d21  movzx   ebx, ax
0x180035d24  or      ebx, edi
0x180035d26  test    ebx, ebx
0x180035d28  jns     loc_180035DF9
0x180035d2e  jmp     loc_180035DE3
0x180035d33  mov     ecx, 108h; Size
0x180035d38  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035d3d  mov     rdi, rax
0x180035d40  test    rax, rax
0x180035d43  jz      loc_180035DD9
0x180035d49  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180035d50  mov     dword ptr [rdi+0Ch], 1
0x180035d57  lea     rcx, [rdi+78h]; this
0x180035d5b  mov     [rdi], rax
0x180035d5e  mov     [rdi+10h], r14
0x180035d62  mov     [rdi+18h], r14
0x180035d66  mov     [rdi+74h], r14d
0x180035d6a  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x180035d6f  lea     rcx, [rdi+0F8h]
0x180035d76  call    cs:__imp_??0CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::CSmallSpinLock(void)
0x180035d7d  nop     dword ptr [rax+rax+00h]
0x180035d82  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x180035d89  mov     r9, r12; unsigned __int16 *
0x180035d8c  mov     [rdi+0FCh], r14d
0x180035d93  mov     r8, r15; unsigned __int16 *
0x180035d96  mov     dword ptr [rdi+100h], 2
0x180035da0  mov     rcx, rdi; this
0x180035da3  mov     dword ptr [rdi+8], 4E4B4F54h
0x180035daa  mov     rdx, [rsp+550h+hObject]; void *
0x180035daf  mov     [rsp+550h+dwLogonProvider], r13d; unsigned int
0x180035db4  call    ?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z; TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)
0x180035db9  mov     ebx, eax
0x180035dbb  test    eax, eax
0x180035dbd  jns     short loc_180035DD0
0x180035dbf  mov     rax, [rdi]
0x180035dc2  mov     rcx, rdi
0x180035dc5  mov     rax, [rax+10h]
0x180035dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dce  jmp     short loc_180035DE3
0x180035dd0  mov     rax, [rbp+450h+var_4D0]
0x180035dd4  mov     [rax], rdi
0x180035dd7  jmp     short loc_180035DF9
0x180035dd9  mov     ebx, 80070008h
0x180035dde  jmp     short loc_180035DE3
0x180035de0  xor     r14d, r14d
0x180035de3  mov     rcx, [rsp+550h+hObject]; hObject
0x180035de8  test    rcx, rcx
0x180035deb  jz      short loc_180035DF9
0x180035ded  call    cs:__imp_CloseHandle
0x180035df4  nop     dword ptr [rax+rax+00h]
0x180035df9  mov     rcx, [rsp+550h+Buffer]; Buffer
0x180035dfe  test    rcx, rcx
0x180035e01  jz      short loc_180035E0F
0x180035e03  call    cs:__imp_LsaFreeReturnBuffer
0x180035e0a  nop     dword ptr [rax+rax+00h]
0x180035e0f  cmp     [rsp+550h+var_500], r14d
0x180035e14  jz      short loc_180035E22
0x180035e16  call    cs:__imp_SeciFreeCallContext
0x180035e1d  nop     dword ptr [rax+rax+00h]
0x180035e22  lea     rcx, [rbp+450h+var_4C8]
0x180035e26  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180035e2d  nop     dword ptr [rax+rax+00h]
0x180035e32  lea     rcx, [rbp+450h+var_490]
0x180035e36  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180035e3d  nop     dword ptr [rax+rax+00h]
0x180035e42  mov     eax, ebx
0x180035e44  mov     rcx, [rbp+450h+var_50]
0x180035e4b  xor     rcx, rsp; StackCookie
0x180035e4e  call    __security_check_cookie
0x180035e53  add     rsp, 518h
0x180035e5a  pop     r15
0x180035e5c  pop     r14
0x180035e5e  pop     r13
0x180035e60  pop     r12
0x180035e62  pop     rdi
0x180035e63  pop     rsi
0x180035e64  pop     rbx
0x180035e65  pop     rbp
0x180035e66  retn
```
