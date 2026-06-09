# CActiveXInstallBroker::InstallCatalogFile(ushort *,ushort *)

- ea: `0x140004c88`
- end: `0x140004e17`
- name: `?InstallCatalogFile@CActiveXInstallBroker@@QEAAJPEAG0@Z`
- size: `399`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007fb0`

## callees

- `0x140004a18`
- `0x140004c88`
- `0x140008f78`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140004deb`
- `KERNEL32!LeaveCriticalSection` at `0x140004deb`
- `KERNEL32!EnterCriticalSection` at `0x140004ce6`
- `KERNEL32!EnterCriticalSection` at `0x140004ce6`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x140004dcf`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x140004dcf`
- `WINTRUST!CryptCATAdminAddCatalog` at `0x140004d8e`
- `WINTRUST!CryptCATAdminAddCatalog` at `0x140004d8e`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140004d6a`
- `WINTRUST!CryptCATAdminAcquireContext` at `0x140004d6a`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x140004dbd`
- `WINTRUST!CryptCATAdminReleaseCatalogContext` at `0x140004dbd`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::InstallCatalogFile(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  bool v3; // zf
  HCATINFO v7; // r15
  int IsAuthorized; // ebx
  __int64 v9; // rdx
  int v10; // ecx
  int v11; // eax
  HCATADMIN v12; // rcx
  HCATADMIN phCatAdmin; // [rsp+20h] [rbp-20h] BYREF
  GUID pgSubsystem; // [rsp+28h] [rbp-18h] BYREF

  v3 = *(_DWORD *)this == 0;
  phCatAdmin = 0;
  pgSubsystem.Data1 = -145692989;
  *(_DWORD *)&pgSubsystem.Data2 = 298924270;
  *(_DWORD *)pgSubsystem.Data4 = -1073683067;
  *(_DWORD *)&pgSubsystem.Data4[4] = -292175281;
  if ( v3 )
  {
    IsAuthorized = -2147024882;
    goto LABEL_24;
  }
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) < 2 )
  {
    IsAuthorized = -2147019873;
    goto LABEL_19;
  }
  if ( a2 && a3 )
  {
    v9 = *((_QWORD *)this + 8) - (_QWORD)a2;
    do
    {
      v10 = *(unsigned __int16 *)((char *)a2 + v9);
      v11 = *a2 - v10;
      if ( v11 )
        break;
      ++a2;
    }
    while ( v10 );
    if ( v11 )
    {
LABEL_10:
      IsAuthorized = -2147024891;
      goto LABEL_19;
    }
    IsAuthorized = CActiveXInstallBroker::FileIsAuthorized(this, a3);
    if ( IsAuthorized >= 0 )
    {
      if ( *((_DWORD *)this + 35) || (unsigned int)ContainingPathIsTamperProof(a3) )
      {
        if ( !CryptCATAdminAcquireContext(&phCatAdmin, &pgSubsystem, 0)
          || (v7 = CryptCATAdminAddCatalog(phCatAdmin, a3, 0, 0)) == 0 )
        {
          IsAuthorized = -2147467259;
        }
        goto LABEL_19;
      }
      goto LABEL_10;
    }
  }
  else
  {
    IsAuthorized = -2147024809;
  }
LABEL_19:
  v12 = phCatAdmin;
  if ( phCatAdmin )
  {
    if ( v7 )
    {
      CryptCATAdminReleaseCatalogContext(phCatAdmin, v7, 0);
      v12 = phCatAdmin;
    }
    CryptCATAdminReleaseContext(v12, 0);
  }
LABEL_24:
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)IsAuthorized;
}

```

## disassembly

```asm
0x140004c88  mov     [rsp-28h+arg_8], rbx
0x140004c8d  push    rbp
0x140004c8e  push    rsi
0x140004c8f  push    rdi
0x140004c90  push    r14
0x140004c92  push    r15
0x140004c94  mov     rbp, rsp
0x140004c97  sub     rsp, 40h
0x140004c9b  mov     rax, cs:__security_cookie
0x140004ca2  xor     rax, rsp
0x140004ca5  mov     [rbp+var_8], rax
0x140004ca9  cmp     dword ptr [rcx], 0
0x140004cac  mov     r14, r8
0x140004caf  mov     rbx, rdx
0x140004cb2  mov     [rbp+phCatAdmin], 0
0x140004cba  mov     rsi, rcx
0x140004cbd  mov     [rbp+pgSubsystem.Data1], 0F750E6C3h
0x140004cc4  mov     dword ptr [rbp+pgSubsystem.Data2], 11D138EEh
0x140004ccb  mov     dword ptr [rbp+pgSubsystem.Data4], 0C000E585h
0x140004cd2  mov     dword ptr [rbp+pgSubsystem.Data4+4], 0EE95C24Fh
0x140004cd9  jz      loc_140004DDD
0x140004cdf  add     rcx, 8; lpCriticalSection
0x140004ce3  xor     r15d, r15d
0x140004ce6  call    cs:__imp_EnterCriticalSection
0x140004ced  nop     dword ptr [rax+rax+00h]
0x140004cf2  cmp     dword ptr [rsi+30h], 2
0x140004cf6  jge     short loc_140004D02
0x140004cf8  mov     ebx, 8007139Fh
0x140004cfd  jmp     loc_140004DA9
0x140004d02  test    rbx, rbx
0x140004d05  jz      loc_140004DA4
0x140004d0b  test    r14, r14
0x140004d0e  jz      loc_140004DA4
0x140004d14  mov     rdx, [rsi+40h]
0x140004d18  sub     rdx, rbx
0x140004d1b  movzx   eax, word ptr [rbx]
0x140004d1e  movzx   ecx, word ptr [rbx+rdx]
0x140004d22  sub     eax, ecx
0x140004d24  jnz     short loc_140004D2E
0x140004d26  add     rbx, 2
0x140004d2a  test    ecx, ecx
0x140004d2c  jnz     short loc_140004D1B
0x140004d2e  test    eax, eax
0x140004d30  jz      short loc_140004D39
0x140004d32  mov     ebx, 80070005h
0x140004d37  jmp     short loc_140004DA9
0x140004d39  mov     rdx, r14; unsigned __int16 *
0x140004d3c  mov     rcx, rsi; this
0x140004d3f  call    ?FileIsAuthorized@CActiveXInstallBroker@@AEAAJPEBGH@Z; CActiveXInstallBroker::FileIsAuthorized(ushort const *,int)
0x140004d44  mov     ebx, eax
0x140004d46  test    eax, eax
0x140004d48  js      short loc_140004DA9
0x140004d4a  cmp     [rsi+8Ch], r15d
0x140004d51  jnz     short loc_140004D5F
0x140004d53  mov     rcx, r14; unsigned __int16 *
0x140004d56  call    ?ContainingPathIsTamperProof@@YAHPEBG@Z; ContainingPathIsTamperProof(ushort const *)
0x140004d5b  test    eax, eax
0x140004d5d  jz      short loc_140004D32
0x140004d5f  xor     r8d, r8d; dwFlags
0x140004d62  lea     rdx, [rbp+pgSubsystem]; pgSubsystem
0x140004d66  lea     rcx, [rbp+phCatAdmin]; phCatAdmin
0x140004d6a  call    cs:__imp_CryptCATAdminAcquireContext
0x140004d71  nop     dword ptr [rax+rax+00h]
0x140004d76  test    eax, eax
0x140004d78  jnz     short loc_140004D81
0x140004d7a  mov     ebx, 80004005h
0x140004d7f  jmp     short loc_140004DA9
0x140004d81  mov     rcx, [rbp+phCatAdmin]; hCatAdmin
0x140004d85  xor     r9d, r9d; dwFlags
0x140004d88  xor     r8d, r8d; pwszSelectBaseName
0x140004d8b  mov     rdx, r14; pwszCatalogFile
0x140004d8e  call    cs:__imp_CryptCATAdminAddCatalog
0x140004d95  nop     dword ptr [rax+rax+00h]
0x140004d9a  mov     r15, rax
0x140004d9d  test    rax, rax
0x140004da0  jnz     short loc_140004DA9
0x140004da2  jmp     short loc_140004D7A
0x140004da4  mov     ebx, 80070057h
0x140004da9  mov     rcx, [rbp+phCatAdmin]; hCatAdmin
0x140004dad  test    rcx, rcx
0x140004db0  jz      short loc_140004DE2
0x140004db2  test    r15, r15
0x140004db5  jz      short loc_140004DCD
0x140004db7  xor     r8d, r8d; dwFlags
0x140004dba  mov     rdx, r15; hCatInfo
0x140004dbd  call    cs:__imp_CryptCATAdminReleaseCatalogContext
0x140004dc4  nop     dword ptr [rax+rax+00h]
0x140004dc9  mov     rcx, [rbp+phCatAdmin]; hCatAdmin
0x140004dcd  xor     edx, edx; dwFlags
0x140004dcf  call    cs:__imp_CryptCATAdminReleaseContext
0x140004dd6  nop     dword ptr [rax+rax+00h]
0x140004ddb  jmp     short loc_140004DE2
0x140004ddd  mov     ebx, 8007000Eh
0x140004de2  cmp     dword ptr [rsi], 0
0x140004de5  jz      short loc_140004DF7
0x140004de7  lea     rcx, [rsi+8]; lpCriticalSection
0x140004deb  call    cs:__imp_LeaveCriticalSection
0x140004df2  nop     dword ptr [rax+rax+00h]
0x140004df7  mov     eax, ebx
0x140004df9  mov     rcx, [rbp+var_8]
0x140004dfd  xor     rcx, rsp; StackCookie
0x140004e00  call    __security_check_cookie
0x140004e05  mov     rbx, [rsp+40h+arg_8]
0x140004e0a  add     rsp, 40h
0x140004e0e  pop     r15
0x140004e10  pop     r14
0x140004e12  pop     rdi
0x140004e13  pop     rsi
0x140004e14  pop     rbp
0x140004e15  retn
```
