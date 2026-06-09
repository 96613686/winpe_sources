# URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(ushort const *,FTP_USER *,ushort const *,AUTHORIZATION_ACCESS_TYPE *)

- ea: `0x180024174`
- end: `0x1800244b4`
- name: `?CheckAuthorizationRule@URL_AUTHZ_RULE_ENTRY@@QEAAJPEBGPEAVFTP_USER@@0PEAW4AUTHORIZATION_ACCESS_TYPE@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(URL_AUTHZ_RULE_ENTRY *this, wchar_t *, struct FTP_USER *, char *, enum AUTHORIZATION_ACCESS_TYPE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024764`

## callees

- `0x180024174`
- `0x1800244bc`
- `0x180024954`
- `0x180024d44`
- `0x180046ff7`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800243f3`
- `msvcrt!_wcsicmp` at `0x1800243f3`
- `KERNEL32!GetLastError` at `0x180024335`
- `KERNEL32!GetLastError` at `0x180024335`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800242b1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800242b1`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024313`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024351`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024379`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024313`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024351`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180024379`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800243ba`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800243ba`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002432b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18002432b`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::CheckAuthorizationRule(
        URL_AUTHZ_RULE_ENTRY *this,
        wchar_t *a2,
        struct FTP_USER *a3,
        char *a4,
        enum AUTHORIZATION_ACCESS_TYPE *a5)
{
  wchar_t *v7; // rax
  unsigned int v9; // r14d
  unsigned int v10; // r10d
  unsigned int v11; // ecx
  __int64 v12; // r11
  __int64 v13; // rax
  char *v14; // rax
  char *v15; // r9
  int v16; // r8d
  int v17; // edx
  int v18; // r15d
  signed int matched; // ebx
  unsigned int v20; // r12d
  __int64 v21; // r14
  __int64 v22; // rbx
  signed int LastError; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  signed __int32 v28[8]; // [rsp+0h] [rbp-70h] BYREF
  int v29; // [rsp+20h] [rbp-50h] BYREF
  int v30; // [rsp+24h] [rbp-4Ch] BYREF
  int v31; // [rsp+28h] [rbp-48h]
  wchar_t *String2; // [rsp+30h] [rbp-40h]
  _QWORD v33[4]; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+58h] [rbp-18h]
  unsigned int Size; // [rsp+60h] [rbp-10h]
  __int16 Size_4; // [rsp+64h] [rbp-Ch]

  v7 = a2;
  String2 = a2;
  v9 = 0;
  v33[0] = 0;
  Src = v33;
  Size = 32;
  Size_4 = 256;
  v29 = 0;
  v10 = *((_DWORD *)this + 20);
  if ( v10 )
  {
    v11 = 0;
    v12 = *((_QWORD *)this + 9);
    while ( 1 )
    {
      v13 = 56LL * v11;
      if ( !*(_DWORD *)(v13 + v12 + 48) )
        break;
      v14 = *(char **)(v13 + v12 + 32);
      v15 = (char *)(a4 - v14);
      do
      {
        v16 = *(unsigned __int16 *)&v15[(_QWORD)v14];
        v17 = *(unsigned __int16 *)v14 - v16;
        if ( v17 )
          break;
        v14 += 2;
      }
      while ( v16 );
      if ( !v17 || !*(_WORD *)a4 )
        break;
      if ( ++v11 >= v10 )
        goto LABEL_10;
    }
    v7 = String2;
  }
  if ( *((_DWORD *)this + 21) || *((_DWORD *)this + 22) && !*v7 )
  {
LABEL_35:
    *(_DWORD *)a5 = *((_DWORD *)this + 5);
    goto LABEL_36;
  }
  v18 = (*(__int64 (__fastcall **)(struct FTP_USER *))(*(_QWORD *)a3 + 72LL))(a3);
  v31 = v18;
  if ( !(*(__int64 (__fastcall **)(struct FTP_USER *))(*(_QWORD *)a3 + 56LL))(a3) && !v18 )
  {
LABEL_10:
    *(_DWORD *)a5 = 2;
LABEL_36:
    matched = 0;
    goto LABEL_37;
  }
  matched = 0;
  v20 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    while ( 1 )
    {
      v21 = 56LL * v20;
      if ( v18 )
      {
        v25 = _wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 3) + v21 + 32), String2);
        v9 = 0;
        if ( !v25 )
          goto LABEL_35;
        goto LABEL_39;
      }
      v30 = 0;
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + v21 + 48) )
        goto LABEL_31;
      CReaderWriterLock3::WriteLock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
      if ( *(_DWORD *)(*((_QWORD *)this + 5) + v21 + 48) )
        goto LABEL_30;
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
      matched = URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(
                  (struct STRU *)(v21 + *((_QWORD *)this + 3)),
                  (struct BUFFER *)v33);
      (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
      if ( matched >= 0 )
        break;
      v9 = 0;
      if ( *((_DWORD *)this + 5) )
        goto LABEL_28;
      matched = 0;
      CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
LABEL_39:
      ++v20;
      v18 = v31;
      if ( v20 >= *((_DWORD *)this + 8) )
        goto LABEL_40;
    }
    v22 = v21 + *((_QWORD *)this + 5);
    if ( BUFFER::Resize((BUFFER *)v22, Size) )
    {
      memcpy_0(*(void **)(v22 + 32), Src, Size);
      _InterlockedOr(v28, 0);
      *(_DWORD *)(v22 + 48) = 1;
    }
    else
    {
      LastError = GetLastError();
      matched = LastError;
      if ( LastError > 0 )
        matched = (unsigned __int16)LastError | 0x80070000;
      if ( matched < 0 )
      {
LABEL_28:
        CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
        goto LABEL_37;
      }
    }
LABEL_30:
    CReaderWriterLock3::WriteUnlock((URL_AUTHZ_RULE_ENTRY *)((char *)this + 48));
LABEL_31:
    matched = URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(
                a3,
                *(void **)(*((_QWORD *)this + 5) + v21 + 32),
                &v30);
    v9 = 0;
    if ( matched >= 0 || *((_DWORD *)this + 5) )
    {
      if ( v30 )
        goto LABEL_35;
    }
    else
    {
      matched = 0;
    }
    goto LABEL_39;
  }
LABEL_40:
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 64LL))(g_pFtpServer);
  if ( !*((_DWORD *)this + 16) )
  {
LABEL_48:
    *(_DWORD *)a5 = 2;
    goto LABEL_49;
  }
  while ( 1 )
  {
    v29 = 0;
    v26 = 56LL * v9;
    v27 = *((_QWORD *)this + 7);
    if ( v18 )
    {
      matched = (*(__int64 (__fastcall **)(struct FTP_USER *, _QWORD, int *))(*(_QWORD *)a3 + 80LL))(
                  a3,
                  *(_QWORD *)(v26 + v27 + 32),
                  &v29);
      if ( matched < 0 )
        goto LABEL_49;
    }
    else
    {
      matched = URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(a3, (struct STRU *)(v26 + v27), &v29);
      if ( matched < 0 )
      {
        if ( *((_DWORD *)this + 5) )
          goto LABEL_49;
        matched = 0;
        goto LABEL_47;
      }
    }
    if ( v29 )
      break;
LABEL_47:
    if ( ++v9 >= *((_DWORD *)this + 16) )
      goto LABEL_48;
  }
  *(_DWORD *)a5 = *((_DWORD *)this + 5);
  matched = 0;
LABEL_49:
  (*(void (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 56LL))(g_pFtpServer);
LABEL_37:
  BUFFER::~BUFFER((BUFFER *)v33);
  return (unsigned int)matched;
}

```

## disassembly

```asm
0x180024174  mov     [rsp-38h+arg_18], rbx
0x180024179  push    rbp
0x18002417a  push    rsi
0x18002417b  push    rdi
0x18002417c  push    r12
0x18002417e  push    r13
0x180024180  push    r14
0x180024182  push    r15
0x180024184  mov     rbp, rsp
0x180024187  sub     rsp, 70h
0x18002418b  mov     rax, cs:__security_cookie
0x180024192  xor     rax, rsp
0x180024195  mov     [rbp+var_8], rax
0x180024199  mov     rbx, r9
0x18002419c  mov     r13, r8
0x18002419f  mov     rax, rdx
0x1800241a2  mov     [rbp+String2], rdx
0x1800241a6  mov     rdi, rcx
0x1800241a9  mov     rsi, [rbp+arg_20]
0x1800241ad  xor     r14d, r14d
0x1800241b0  mov     [rbp+var_38], r14
0x1800241b4  lea     rcx, [rbp+var_38]
0x1800241b8  mov     [rbp+Src], rcx
0x1800241bc  mov     dword ptr [rbp+Size], 20h ; ' '
0x1800241c3  mov     word ptr [rbp+Size+4], 100h
0x1800241c9  mov     [rbp+var_50], r14d
0x1800241cd  mov     r10d, [rdi+50h]
0x1800241d1  test    r10d, r10d
0x1800241d4  jz      short loc_18002422B
0x1800241d6  mov     ecx, r14d
0x1800241d9  mov     r11, [rdi+48h]
0x1800241dd  mov     eax, ecx
0x1800241df  imul    rax, 38h ; '8'
0x1800241e3  cmp     [rax+r11+30h], r14d
0x1800241e8  jz      short loc_180024227
0x1800241ea  mov     rax, [rax+r11+20h]
0x1800241ef  mov     r9, rbx
0x1800241f2  sub     r9, rax
0x1800241f5  movzx   edx, word ptr [rax]
0x1800241f8  movzx   r8d, word ptr [rax+r9]
0x1800241fd  sub     edx, r8d
0x180024200  jnz     short loc_18002420B
0x180024202  add     rax, 2
0x180024206  test    r8d, r8d
0x180024209  jnz     short loc_1800241F5
0x18002420b  test    edx, edx
0x18002420d  jz      short loc_180024227
0x18002420f  cmp     [rbx], r14w
0x180024213  jz      short loc_180024227
0x180024215  inc     ecx
0x180024217  cmp     ecx, r10d
0x18002421a  jb      short loc_1800241DD
0x18002421c  mov     dword ptr [rsi], 2
0x180024222  jmp     loc_1800243B3
0x180024227  mov     rax, [rbp+String2]
0x18002422b  cmp     [rdi+54h], r14d
0x18002422f  jnz     loc_1800243AE
0x180024235  cmp     [rdi+58h], r14d
0x180024239  jz      short loc_180024245
0x18002423b  cmp     [rax], r14w
0x18002423f  jz      loc_1800243AE
0x180024245  mov     rax, [r13+0]
0x180024249  mov     rcx, r13
0x18002424c  mov     rax, [rax+48h]
0x180024250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024255  mov     r15d, eax
0x180024258  mov     [rbp+var_48], eax
0x18002425b  mov     rax, [r13+0]
0x18002425f  mov     rcx, r13
0x180024262  mov     rax, [rax+38h]
0x180024266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002426b  test    rax, rax
0x18002426e  jnz     short loc_180024275
0x180024270  test    r15d, r15d
0x180024273  jz      short loc_18002421C
0x180024275  mov     ebx, r14d
0x180024278  mov     r12d, r14d
0x18002427b  cmp     [rdi+20h], r14d
0x18002427f  jbe     loc_180024411
0x180024285  mov     eax, r12d
0x180024288  imul    r14, rax, 38h ; '8'
0x18002428c  test    r15d, r15d
0x18002428f  jnz     loc_1800243E6
0x180024295  mov     [rbp+var_4C], r15d
0x180024299  mov     rax, [rdi+28h]
0x18002429d  mov     ecx, [rax+r14+30h]
0x1800242a2  test    ecx, ecx
0x1800242a4  jnz     loc_18002437F
0x1800242aa  lea     r15, [rdi+30h]
0x1800242ae  mov     rcx, r15
0x1800242b1  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800242b7  mov     rax, [rdi+28h]
0x1800242bb  mov     ecx, [rax+r14+30h]
0x1800242c0  test    ecx, ecx
0x1800242c2  jnz     loc_180024376
0x1800242c8  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800242cf  mov     rax, [rcx]
0x1800242d2  mov     rax, [rax+40h]
0x1800242d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242db  mov     rcx, [rdi+18h]
0x1800242df  add     rcx, r14; struct STRU *
0x1800242e2  lea     rdx, [rbp+var_38]; struct BUFFER *
0x1800242e6  call    ?ResolveUserNameToSidForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVSTRU@@PEAVBUFFER@@@Z; URL_AUTHZ_RULE_ENTRY::ResolveUserNameToSidForWindowsPrincipal(STRU *,BUFFER *)
0x1800242eb  mov     ebx, eax
0x1800242ed  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800242f4  mov     rdx, [rcx]
0x1800242f7  mov     rax, [rdx+38h]
0x1800242fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024300  test    ebx, ebx
0x180024302  jns     short loc_18002431E
0x180024304  xor     r14d, r14d
0x180024307  cmp     [rdi+14h], r14d
0x18002430b  jnz     short loc_18002434E
0x18002430d  mov     ebx, r14d
0x180024310  mov     rcx, r15
0x180024313  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180024319  jmp     loc_180024400
0x18002431e  mov     rbx, [rdi+28h]
0x180024322  add     rbx, r14
0x180024325  mov     edx, dword ptr [rbp+Size]
0x180024328  mov     rcx, rbx
0x18002432b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024331  test    al, al
0x180024333  jnz     short loc_180024359
0x180024335  call    cs:__imp_GetLastError
0x18002433b  mov     ebx, eax
0x18002433d  test    eax, eax
0x18002433f  jle     short loc_18002434A
0x180024341  movzx   ebx, ax
0x180024344  or      ebx, 80070000h
0x18002434a  test    ebx, ebx
0x18002434c  jns     short loc_180024376
0x18002434e  mov     rcx, r15
0x180024351  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180024357  jmp     short loc_1800243B6
0x180024359  mov     r8d, dword ptr [rbp+Size]; Size
0x18002435d  mov     rdx, [rbp+Src]; Src
0x180024361  mov     rcx, [rbx+20h]; void *
0x180024365  call    memcpy_0
0x18002436a  lock or [rsp+70h+var_70], 0
0x18002436f  mov     dword ptr [rbx+30h], 1
0x180024376  mov     rcx, r15
0x180024379  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18002437f  mov     rdx, [rdi+28h]
0x180024383  lea     r8, [rbp+var_4C]; int *
0x180024387  mov     rdx, [rdx+r14+20h]; void *
0x18002438c  mov     rcx, r13; struct FTP_USER *
0x18002438f  call    ?MatchUserNameForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVFTP_USER@@PEAXPEAH@Z; URL_AUTHZ_RULE_ENTRY::MatchUserNameForWindowsPrincipal(FTP_USER *,void *,int *)
0x180024394  mov     ebx, eax
0x180024396  xor     r14d, r14d
0x180024399  test    eax, eax
0x18002439b  jns     short loc_1800243A8
0x18002439d  cmp     [rdi+14h], r14d
0x1800243a1  jnz     short loc_1800243A8
0x1800243a3  mov     ebx, r14d
0x1800243a6  jmp     short loc_180024400
0x1800243a8  cmp     [rbp+var_4C], r14d
0x1800243ac  jz      short loc_180024400
0x1800243ae  mov     eax, [rdi+14h]
0x1800243b1  mov     [rsi], eax
0x1800243b3  mov     ebx, r14d
0x1800243b6  lea     rcx, [rbp+var_38]
0x1800243ba  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800243c0  mov     eax, ebx
0x1800243c2  mov     rcx, [rbp+var_8]
0x1800243c6  xor     rcx, rsp; StackCookie
0x1800243c9  call    __security_check_cookie
0x1800243ce  mov     rbx, [rsp+70h+arg_18]
0x1800243d6  add     rsp, 70h
0x1800243da  pop     r15
0x1800243dc  pop     r14
0x1800243de  pop     r13
0x1800243e0  pop     r12
0x1800243e2  pop     rdi
0x1800243e3  pop     rsi
0x1800243e4  pop     rbp
0x1800243e5  retn
0x1800243e6  mov     rcx, [rdi+18h]
0x1800243ea  mov     rdx, [rbp+String2]; String2
0x1800243ee  mov     rcx, [rcx+r14+20h]; String1
0x1800243f3  call    cs:__imp__wcsicmp
0x1800243f9  xor     r14d, r14d
0x1800243fc  test    eax, eax
0x1800243fe  jz      short loc_1800243AE
0x180024400  inc     r12d
0x180024403  mov     r15d, [rbp+var_48]
0x180024407  cmp     r12d, [rdi+20h]
0x18002440b  jb      loc_180024285
0x180024411  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180024418  mov     rax, [rcx]
0x18002441b  mov     rax, [rax+40h]
0x18002441f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024424  xor     r12d, r12d
0x180024427  cmp     [rdi+40h], r12d
0x18002442b  jbe     short loc_18002448B
0x18002442d  mov     [rbp+var_50], r12d
0x180024431  mov     eax, r14d
0x180024434  imul    rcx, rax, 38h ; '8'
0x180024438  mov     rdx, [rdi+38h]
0x18002443c  lea     r8, [rbp+var_50]; int *
0x180024440  test    r15d, r15d
0x180024443  jnz     short loc_180024461
0x180024445  add     rdx, rcx; struct STRU *
0x180024448  mov     rcx, r13; struct FTP_USER *
0x18002444b  call    ?CheckTokenMembershipForWindowsPrincipal@URL_AUTHZ_RULE_ENTRY@@CAJPEAVFTP_USER@@PEAVSTRU@@PEAH@Z; URL_AUTHZ_RULE_ENTRY::CheckTokenMembershipForWindowsPrincipal(FTP_USER *,STRU *,int *)
0x180024450  mov     ebx, eax
0x180024452  test    eax, eax
0x180024454  jns     short loc_18002447C
0x180024456  cmp     [rdi+14h], r12d
0x18002445a  jnz     short loc_180024491
0x18002445c  mov     ebx, r12d
0x18002445f  jmp     short loc_180024482
0x180024461  mov     rax, [r13+0]
0x180024465  mov     rdx, [rcx+rdx+20h]
0x18002446a  mov     rcx, r13
0x18002446d  mov     rax, [rax+50h]
0x180024471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024476  mov     ebx, eax
0x180024478  test    eax, eax
0x18002447a  js      short loc_180024491
0x18002447c  cmp     [rbp+var_50], r12d
0x180024480  jnz     short loc_1800244A9
0x180024482  inc     r14d
0x180024485  cmp     r14d, [rdi+40h]
0x180024489  jb      short loc_18002442D
0x18002448b  mov     dword ptr [rsi], 2
0x180024491  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180024498  mov     rax, [rcx]
0x18002449b  mov     rax, [rax+38h]
0x18002449f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244a4  jmp     loc_1800243B6
0x1800244a9  mov     eax, [rdi+14h]
0x1800244ac  mov     [rsi], eax
0x1800244ae  mov     ebx, r12d
0x1800244b1  jmp     short loc_180024491
```
