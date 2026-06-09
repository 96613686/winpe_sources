# IIS_LOGON_PROVIDER::IISLogonUser(ushort const *,ushort const *,ulong,ushort const *,sockaddr *,IHttpTokenEntry * *)

- ea: `0x1800117cc`
- end: `0x180011aec`
- name: `?IISLogonUser@IIS_LOGON_PROVIDER@@QEAAJPEBG0K0PEAUsockaddr@@PEAPEAVIHttpTokenEntry@@@Z`
- size: `800`
- prototype: `int(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, struct sockaddr *, struct IHttpTokenEntry **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c898`

## callees

- `0x180001020`
- `0x18000c324`
- `0x180010b48`
- `0x180010cd4`
- `0x1800117cc`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800118ef`
- `msvcrt!wcschr` at `0x1800118ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011a95`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011ab0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011aba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011ab0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180011aba`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800118cf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800118e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001190b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011921`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011938`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001194e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001195f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800118cf`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800118e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001190b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011921`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011938`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001194e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18001195f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011850`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011879`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011850`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180011879`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180011a2e`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x180011a2e`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x1800119a1`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x1800119a1`
- `SspiCli!LsaFreeReturnBuffer` at `0x180011aa5`
- `SspiCli!LsaFreeReturnBuffer` at `0x180011aa5`

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
  wchar_t *v7; // rsi
  int v11; // ebx
  const wchar_t *v12; // rax
  unsigned int v13; // edi
  const WCHAR *v14; // rax
  unsigned int i; // ebx
  const WCHAR *v16; // rax
  signed int LastError; // eax
  signed int v18; // eax
  _DWORD *v19; // rdi
  DWORD phToken; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwProfileLength; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszDomain; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *Str; // [rsp+68h] [rbp-98h]
  PVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v28[56]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v29[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v30[256]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v31[256]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v7 = ISAPI_REQUEST::sm_pLogonProvider;
  hObject = 0;
  Buffer = 0;
  pdwProfileLength = 0;
  Str = 0;
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v29, v30, 0x100u);
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v28, v31, 0x100u);
  v22 = 0;
  if ( !a7 )
  {
    v11 = -2147024809;
    goto LABEL_33;
  }
  v11 = IIS_LOGON_PROVIDER::DetermineUserAndDomain(
          (IIS_LOGON_PROVIDER *)v7,
          a2,
          a5,
          (struct STRU *)v29,
          (struct STRU *)v28,
          &v22);
  if ( v11 >= 0 )
  {
    if ( !v22 && *STRU::QueryStr((STRU *)v28) && (v12 = STRU::QueryStr((STRU *)v29), wcschr(v12, 0x40u)) )
    {
      v13 = 2;
      if ( !*((_DWORD *)v7 + 641) )
      {
        lpszDomain = 0;
        Str = STRU::QueryStr((STRU *)v28);
        goto LABEL_14;
      }
      v14 = STRU::QueryStr((STRU *)v28);
      Str = 0;
    }
    else
    {
      v13 = 1;
      if ( *STRU::QueryStr((STRU *)v28) )
        v14 = STRU::QueryStr((STRU *)v28);
      else
        v14 = 0;
    }
    lpszDomain = v14;
LABEL_14:
    for ( i = 0; i < v13; ++i )
    {
      v16 = STRU::QueryStr((STRU *)v29);
      if ( LogonUserExW(v16, (&lpszDomain)[i], a3, a4, 0, &hObject, 0, &Buffer, &pdwProfileLength, 0) )
      {
        v19 = operator new(0x108u);
        if ( !v19 )
        {
          v11 = -2147024888;
          goto LABEL_29;
        }
        v19[3] = 1;
        *(_QWORD *)v19 = &TOKEN_ENTRY::`vftable';
        *((_QWORD *)v19 + 2) = 0;
        *((_QWORD *)v19 + 3) = 0;
        v19[29] = 0;
        TOKEN_KEY::TOKEN_KEY((TOKEN_KEY *)(v19 + 30));
        CSmallSpinLock::CSmallSpinLock((CSmallSpinLock *)(v19 + 62));
        v19[65] &= 0xFFFFFFFC;
        v19[63] = 0;
        v19[64] = 2;
        v19[2] = 1313558356;
        v11 = TOKEN_ENTRY::Create((TOKEN_ENTRY *)v19, hObject, a2, a3, a4, phToken);
        if ( v11 < 0 )
        {
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v19 + 16LL))(v19);
          goto LABEL_29;
        }
        *a7 = (struct IHttpTokenEntry *)v19;
        goto LABEL_31;
      }
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147023570 )
        break;
    }
    v18 = GetLastError();
    v11 = v18;
    if ( v18 > 0 )
      v11 = (unsigned __int16)v18 | 0x80070000;
    if ( v11 >= 0 )
      goto LABEL_31;
  }
LABEL_29:
  if ( hObject )
    CloseHandle(hObject);
LABEL_31:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
LABEL_33:
  STRU::~STRU((STRU *)v28);
  STRU::~STRU((STRU *)v29);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800117cc  mov     [rsp-8+arg_0], rbx
0x1800117d1  push    rbp
0x1800117d2  push    rsi
0x1800117d3  push    rdi
0x1800117d4  push    r12
0x1800117d6  push    r13
0x1800117d8  push    r14
0x1800117da  push    r15
0x1800117dc  lea     rbp, [rsp-400h]
0x1800117e4  sub     rsp, 500h
0x1800117eb  mov     rax, cs:__security_cookie
0x1800117f2  xor     rax, rsp
0x1800117f5  mov     [rbp+430h+var_40], rax
0x1800117fc  mov     rbx, [rbp+430h+arg_20]
0x180011803  lea     rcx, [rbp+430h+var_440]; void *
0x180011807  mov     r15, [rbp+430h+arg_30]
0x18001180e  xor     eax, eax
0x180011810  mov     rsi, cs:?sm_pLogonProvider@ISAPI_REQUEST@@0PEAVIIS_LOGON_PROVIDER@@EA; IIS_LOGON_PROVIDER * ISAPI_REQUEST::sm_pLogonProvider
0x180011817  mov     r12, r8
0x18001181a  mov     r14, rdx
0x18001181d  mov     [rsp+530h+hObject], rax
0x180011822  xor     edx, edx; Val
0x180011824  mov     [rsp+530h+Buffer], rax
0x180011829  mov     r8d, 200h; Size
0x18001182f  mov     [rsp+530h+var_4DC], eax
0x180011833  mov     [rsp+530h+var_4C8], rax
0x180011838  mov     r13d, r9d
0x18001183b  call    memset_0
0x180011840  mov     edi, 100h
0x180011845  lea     rdx, [rbp+430h+var_440]
0x180011849  mov     r8d, edi
0x18001184c  lea     rcx, [rbp+430h+var_480]
0x180011850  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180011856  xor     edx, edx; Val
0x180011858  lea     rcx, [rbp+430h+var_240]; void *
0x18001185f  mov     r8d, 200h; Size
0x180011865  call    memset_0
0x18001186a  mov     r8d, edi
0x18001186d  lea     rdx, [rbp+430h+var_240]
0x180011874  lea     rcx, [rsp+530h+var_4B8]
0x180011879  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18001187f  xor     edi, edi
0x180011881  mov     [rsp+530h+var_4E0], edi
0x180011885  test    r15, r15
0x180011888  jnz     short loc_180011894
0x18001188a  mov     ebx, 80070057h
0x18001188f  jmp     loc_180011AAB
0x180011894  lea     rax, [rsp+530h+var_4E0]
0x180011899  mov     r8, rbx; unsigned __int16 *
0x18001189c  mov     [rsp+530h+phToken], rax; int *
0x1800118a1  lea     r9, [rbp+430h+var_480]; struct STRU *
0x1800118a5  lea     rax, [rsp+530h+var_4B8]
0x1800118aa  mov     rdx, r14; unsigned __int16 *
0x1800118ad  mov     rcx, rsi; this
0x1800118b0  mov     qword ptr [rsp+530h+dwLogonProvider], rax; struct STRU *
0x1800118b5  call    ?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z; IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)
0x1800118ba  mov     ebx, eax
0x1800118bc  test    eax, eax
0x1800118be  js      loc_180011A8B
0x1800118c4  cmp     [rsp+530h+var_4E0], edi
0x1800118c8  jnz     short loc_18001192E
0x1800118ca  lea     rcx, [rsp+530h+var_4B8]
0x1800118cf  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800118d5  cmp     [rax], di
0x1800118d8  jz      short loc_18001192E
0x1800118da  lea     rcx, [rbp+430h+var_480]
0x1800118de  mov     ebx, 40h ; '@'
0x1800118e3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800118e9  mov     rcx, rax; Str
0x1800118ec  movzx   edx, bx; Ch
0x1800118ef  call    cs:__imp_wcschr
0x1800118f5  test    rax, rax
0x1800118f8  jz      short loc_18001192E
0x1800118fa  cmp     dword ptr [rsi+0A04h], 0
0x180011901  lea     edi, [rbx-3Eh]
0x180011904  lea     rcx, [rsp+530h+var_4B8]
0x180011909  jz      short loc_18001191A
0x18001190b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011911  xor     esi, esi
0x180011913  mov     [rsp+530h+var_4C8], rsi
0x180011918  jmp     short loc_180011954
0x18001191a  xor     esi, esi
0x18001191c  mov     [rsp+530h+lpszDomain], rsi
0x180011921  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011927  mov     [rsp+530h+var_4C8], rax
0x18001192c  jmp     short loc_180011959
0x18001192e  lea     rcx, [rsp+530h+var_4B8]
0x180011933  mov     edi, 1
0x180011938  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001193e  xor     esi, esi
0x180011940  cmp     [rax], si
0x180011943  jnz     short loc_180011949
0x180011945  mov     eax, esi
0x180011947  jmp     short loc_180011954
0x180011949  lea     rcx, [rsp+530h+var_4B8]
0x18001194e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011954  mov     [rsp+530h+lpszDomain], rax
0x180011959  mov     ebx, esi
0x18001195b  lea     rcx, [rbp+430h+var_480]
0x18001195f  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180011965  mov     [rsp+530h+pQuotaLimits], rsi; pQuotaLimits
0x18001196a  lea     rcx, [rsp+530h+var_4DC]
0x18001196f  mov     [rsp+530h+pdwProfileLength], rcx; pdwProfileLength
0x180011974  mov     r9d, r13d; dwLogonType
0x180011977  lea     rcx, [rsp+530h+Buffer]
0x18001197c  mov     edx, ebx
0x18001197e  mov     [rsp+530h+ppProfileBuffer], rcx; ppProfileBuffer
0x180011983  mov     r8, r12; lpszPassword
0x180011986  lea     rcx, [rsp+530h+hObject]
0x18001198b  mov     [rsp+530h+ppLogonSid], rsi; ppLogonSid
0x180011990  mov     [rsp+530h+phToken], rcx; int
0x180011995  mov     rcx, rax; lpszUsername
0x180011998  mov     rdx, [rsp+rdx*8+530h+lpszDomain]; lpszDomain
0x18001199d  mov     [rsp+530h+dwLogonProvider], esi; dwLogonProvider
0x1800119a1  call    cs:__imp_LogonUserExW
0x1800119a7  test    eax, eax
0x1800119a9  jnz     short loc_1800119EC
0x1800119ab  call    cs:__imp_GetLastError
0x1800119b1  test    eax, eax
0x1800119b3  jle     short loc_1800119BD
0x1800119b5  movzx   eax, ax
0x1800119b8  or      eax, 80070000h
0x1800119bd  cmp     eax, 8007052Eh
0x1800119c2  jnz     short loc_1800119CA
0x1800119c4  inc     ebx
0x1800119c6  cmp     ebx, edi
0x1800119c8  jb      short loc_18001195B
0x1800119ca  call    cs:__imp_GetLastError
0x1800119d0  mov     ebx, eax
0x1800119d2  test    eax, eax
0x1800119d4  jle     short loc_1800119DF
0x1800119d6  movzx   ebx, ax
0x1800119d9  or      ebx, 80070000h
0x1800119df  test    ebx, ebx
0x1800119e1  jns     loc_180011A9B
0x1800119e7  jmp     loc_180011A8B
0x1800119ec  mov     ecx, 108h; Size
0x1800119f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800119f6  mov     rdi, rax
0x1800119f9  test    rax, rax
0x1800119fc  jz      loc_180011A86
0x180011a02  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x180011a09  mov     dword ptr [rdi+0Ch], 1
0x180011a10  lea     rcx, [rdi+78h]; this
0x180011a14  mov     [rdi], rax
0x180011a17  mov     [rdi+10h], rsi
0x180011a1b  mov     [rdi+18h], rsi
0x180011a1f  mov     [rdi+74h], esi
0x180011a22  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x180011a27  lea     rcx, [rdi+0F8h]
0x180011a2e  call    cs:__imp_??0CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::CSmallSpinLock(void)
0x180011a34  and     dword ptr [rdi+104h], 0FFFFFFFCh
0x180011a3b  mov     r9, r12; unsigned __int16 *
0x180011a3e  mov     [rdi+0FCh], esi
0x180011a44  mov     r8, r14; unsigned __int16 *
0x180011a47  mov     dword ptr [rdi+100h], 2
0x180011a51  mov     rcx, rdi; this
0x180011a54  mov     dword ptr [rdi+8], 4E4B4F54h
0x180011a5b  mov     rdx, [rsp+530h+hObject]; void *
0x180011a60  mov     [rsp+530h+dwLogonProvider], r13d; unsigned int
0x180011a65  call    ?Create@TOKEN_ENTRY@@QEAAJPEAXPEBG1KH@Z; TOKEN_ENTRY::Create(void *,ushort const *,ushort const *,ulong,int)
0x180011a6a  mov     ebx, eax
0x180011a6c  test    eax, eax
0x180011a6e  jns     short loc_180011A81
0x180011a70  mov     rax, [rdi]
0x180011a73  mov     rcx, rdi
0x180011a76  mov     rax, [rax+10h]
0x180011a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a7f  jmp     short loc_180011A8B
0x180011a81  mov     [r15], rdi
0x180011a84  jmp     short loc_180011A9B
0x180011a86  mov     ebx, 80070008h
0x180011a8b  mov     rcx, [rsp+530h+hObject]; hObject
0x180011a90  test    rcx, rcx
0x180011a93  jz      short loc_180011A9B
0x180011a95  call    cs:__imp_CloseHandle
0x180011a9b  mov     rcx, [rsp+530h+Buffer]; Buffer
0x180011aa0  test    rcx, rcx
0x180011aa3  jz      short loc_180011AAB
0x180011aa5  call    cs:__imp_LsaFreeReturnBuffer
0x180011aab  lea     rcx, [rsp+530h+var_4B8]
0x180011ab0  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011ab6  lea     rcx, [rbp+430h+var_480]
0x180011aba  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011ac0  mov     eax, ebx
0x180011ac2  mov     rcx, [rbp+430h+var_40]
0x180011ac9  xor     rcx, rsp; StackCookie
0x180011acc  call    __security_check_cookie
0x180011ad1  mov     rbx, [rsp+530h+arg_0]
0x180011ad9  add     rsp, 500h
0x180011ae0  pop     r15
0x180011ae2  pop     r14
0x180011ae4  pop     r13
0x180011ae6  pop     r12
0x180011ae8  pop     rdi
0x180011ae9  pop     rsi
0x180011aea  pop     rbp
0x180011aeb  retn
```
