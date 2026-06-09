# CClassicSharingDialog::_ValidateNewShareName(ushort const *)

- ea: `0x18006337c`
- end: `0x1800635b1`
- name: `?_ValidateNewShareName@CClassicSharingDialog@@AEAAJPEBG@Z`
- size: `565`
- prototype: `int(CClassicSharingDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180061c14`

## callees

- `0x1800115cc`
- `0x180011cb0`
- `0x18001d2d0`
- `0x1800254e0`
- `0x1800259bc`
- `0x18005e4b4`
- `0x18005e51c`
- `0x180061250`
- `0x18006337c`
- `0x180072674`
- `0x180073280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800633eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800633ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006342e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006347a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800633eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800633ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006342e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006347a`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180063467`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180063467`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180063418`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180063418`
- `SHLWAPI!PathIsRootW` at `0x180063459`
- `SHLWAPI!PathIsRootW` at `0x180063459`

## pseudocode

```c
__int64 __fastcall CClassicSharingDialog::_ValidateNewShareName(
        CClassicSharingDialog *this,
        const unsigned __int16 *a2)
{
  int inited; // edi
  __int64 v5; // rax
  int v6; // edx
  HWND v7; // rcx
  const WCHAR *v8; // rcx
  CShareCache *v9; // rcx
  CShareInfo *v10; // rax
  CShareInfo *v11; // rbx
  unsigned int v12; // edx
  __int64 v13; // rcx
  CShareInfo **v14; // rax
  WCHAR v16; // [rsp+28h] [rbp-450h] BYREF
  int v17; // [rsp+2Ah] [rbp-44Eh]
  unsigned __int16 v18[264]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-238h] BYREF

  inited = -2147024809;
  if ( !a2 )
    goto LABEL_26;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  if ( !v5 )
  {
LABEL_26:
    v7 = *(HWND *)this;
    v6 = -2147483380;
    goto LABEL_27;
  }
  if ( !(unsigned int)IsValidShareName(a2) )
  {
    v6 = -2147483379;
    goto LABEL_11;
  }
  if ( !(unsigned int)_o__wcsicmp(&g_szIpcShare, a2)
    || !(unsigned int)_o__wcsicmp(&g_szAdminShare, a2)
    && (!GetWindowsDirectoryW(Buffer, 0x104u) || (unsigned int)_o__wcsicmp(*((_QWORD *)this + 1), Buffer)) )
  {
    v6 = -2147483375;
LABEL_11:
    v7 = *(HWND *)this;
LABEL_27:
    MyErrorDialog(v7, v6);
    return (unsigned int)inited;
  }
  v8 = (const WCHAR *)*((_QWORD *)this + 1);
  v16 = *v8;
  v17 = 36;
  if ( PathIsRootW(v8) && GetDriveTypeW(*((LPCWSTR *)this + 1)) == 3 && !(unsigned int)_o__wcsicmp(a2, &v16) )
  {
    MyErrorDialog(*(HWND *)this, -2147483377, a2);
    return (unsigned int)inited;
  }
  if ( !CShareCache::IsExistingShare(v9, a2, v18, 260) )
    return 0;
  if ( ConfirmReplaceShare(*(HWND *)this, a2, v18, *((const unsigned __int16 **)this + 1)) == 6 )
  {
    inited = -2147024882;
    v10 = (CShareInfo *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *((_QWORD *)v10 + 2) = 1;
      *((_QWORD *)v10 + 3) = 0;
      *((_DWORD *)v10 + 8) = -1;
      *(_QWORD *)v10 = v10;
      *((_QWORD *)v10 + 1) = v10;
      inited = CShareInfo::InitInstance(v10);
      if ( inited < 0
        || (inited = CShareInfo::SetNetname(v11, a2), inited < 0)
        || (inited = CShareInfo::SetPath(v11, v18), inited < 0) )
      {
        CShareInfo::`scalar deleting destructor'(v11, v12);
        return (unsigned int)inited;
      }
      *((_DWORD *)v11 + 5) = 2;
      v13 = *((_QWORD *)this + 5);
      v14 = *(CShareInfo ***)(v13 + 8);
      *(_QWORD *)v11 = v13;
      *((_QWORD *)v11 + 1) = v14;
      *(_QWORD *)(v13 + 8) = v11;
      *v14 = v11;
      return 0;
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18006337c  mov     [rsp+arg_10], rbx
0x180063381  mov     [rsp+arg_18], rbp
0x180063386  push    rsi
0x180063387  push    rdi
0x180063388  push    r14
0x18006338a  sub     rsp, 460h
0x180063391  mov     rax, cs:__security_cookie
0x180063398  xor     rax, rsp
0x18006339b  mov     [rsp+478h+var_28], rax
0x1800633a3  xor     r14d, r14d
0x1800633a6  mov     rbp, rdx
0x1800633a9  mov     rsi, rcx
0x1800633ac  mov     edi, 80070057h
0x1800633b1  test    rdx, rdx
0x1800633b4  jz      loc_18006357A
0x1800633ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800633be  inc     rax
0x1800633c1  cmp     [rdx+rax*2], r14w
0x1800633c6  jnz     short loc_1800633BE
0x1800633c8  test    rax, rax
0x1800633cb  jz      loc_18006357A
0x1800633d1  mov     rcx, rbp; unsigned __int16 *
0x1800633d4  call    ?IsValidShareName@@YAHPEBG@Z; IsValidShareName(ushort const *)
0x1800633d9  test    eax, eax
0x1800633db  jz      loc_180063570
0x1800633e1  mov     rdx, rbp
0x1800633e4  lea     rcx, ?g_szIpcShare@@3PAGA; "IPC$"
0x1800633eb  call    cs:__imp__o__wcsicmp
0x1800633f1  test    eax, eax
0x1800633f3  jz      short loc_180063438
0x1800633f5  mov     rdx, rbp
0x1800633f8  lea     rcx, ?g_szAdminShare@@3PAGA; "ADMIN$"
0x1800633ff  call    cs:__imp__o__wcsicmp
0x180063405  mov     ebx, 104h
0x18006340a  test    eax, eax
0x18006340c  jnz     short loc_180063445
0x18006340e  mov     edx, ebx; uSize
0x180063410  lea     rcx, [rsp+478h+Buffer]; lpBuffer
0x180063418  call    cs:__imp_GetWindowsDirectoryW
0x18006341e  test    eax, eax
0x180063420  jz      short loc_180063438
0x180063422  mov     rcx, [rsi+8]
0x180063426  lea     rdx, [rsp+478h+Buffer]
0x18006342e  call    cs:__imp__o__wcsicmp
0x180063434  test    eax, eax
0x180063436  jz      short loc_180063445
0x180063438  mov     edx, 80000111h
0x18006343d  mov     rcx, [rsi]
0x180063440  jmp     loc_180063582
0x180063445  mov     rcx, [rsi+8]; pszPath
0x180063449  movzx   eax, word ptr [rcx]
0x18006344c  mov     [rsp+478h+var_450], ax
0x180063451  mov     [rsp+478h+var_44E], 24h ; '$'
0x180063459  call    cs:__imp_PathIsRootW
0x18006345f  test    eax, eax
0x180063461  jz      short loc_180063499
0x180063463  mov     rcx, [rsi+8]; lpRootPathName
0x180063467  call    cs:__imp_GetDriveTypeW
0x18006346d  cmp     eax, 3
0x180063470  jnz     short loc_180063499
0x180063472  lea     rdx, [rsp+478h+var_450]
0x180063477  mov     rcx, rbp
0x18006347a  call    cs:__imp__o__wcsicmp
0x180063480  test    eax, eax
0x180063482  jnz     short loc_180063499
0x180063484  mov     rcx, [rsi]; HWND
0x180063487  mov     r8, rbp
0x18006348a  mov     edx, 8000010Fh; int
0x18006348f  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180063494  jmp     loc_180063587
0x180063499  mov     r9d, ebx; int
0x18006349c  lea     r8, [rsp+478h+var_448]; unsigned __int16 *
0x1800634a1  mov     rdx, rbp; unsigned __int16 *
0x1800634a4  call    ?IsExistingShare@CShareCache@@QEAAHPEBGPEAGH@Z; CShareCache::IsExistingShare(ushort const *,ushort *,int)
0x1800634a9  test    eax, eax
0x1800634ab  jz      loc_180063561
0x1800634b1  mov     r9, [rsi+8]; unsigned __int16 *
0x1800634b5  lea     r8, [rsp+478h+var_448]; unsigned __int16 *
0x1800634ba  mov     rcx, [rsi]; HWND
0x1800634bd  mov     rdx, rbp; unsigned __int16 *
0x1800634c0  call    ?ConfirmReplaceShare@@YAKPEAUHWND__@@PEBG11@Z; ConfirmReplaceShare(HWND__ *,ushort const *,ushort const *,ushort const *)
0x1800634c5  cmp     eax, 6
0x1800634c8  jnz     loc_180063587
0x1800634ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800634d5  mov     edi, 8007000Eh
0x1800634da  lea     ecx, [rax+22h]; unsigned __int64
0x1800634dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800634e2  mov     [rsp+478h+var_458], rax
0x1800634e7  mov     rbx, rax
0x1800634ea  test    rax, rax
0x1800634ed  jz      loc_180063587
0x1800634f3  mov     qword ptr [rax+10h], 1
0x1800634fb  mov     [rax+18h], r14
0x1800634ff  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x180063506  mov     [rax], rax
0x180063509  mov     [rax+8], rax
0x18006350d  test    rax, rax
0x180063510  jz      short loc_180063587
0x180063512  mov     rcx, rax; this
0x180063515  call    ?InitInstance@CShareInfo@@QEAAJXZ; CShareInfo::InitInstance(void)
0x18006351a  mov     edi, eax
0x18006351c  test    eax, eax
0x18006351e  js      short loc_180063566
0x180063520  mov     rdx, rbp; unsigned __int16 *
0x180063523  mov     rcx, rbx; this
0x180063526  call    ?SetNetname@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetNetname(ushort const *)
0x18006352b  mov     edi, eax
0x18006352d  test    eax, eax
0x18006352f  js      short loc_180063566
0x180063531  lea     rdx, [rsp+478h+var_448]; unsigned __int16 *
0x180063536  mov     rcx, rbx; this
0x180063539  call    ?SetPath@CShareInfo@@QEAAJPEBG@Z; CShareInfo::SetPath(ushort const *)
0x18006353e  mov     edi, eax
0x180063540  test    eax, eax
0x180063542  js      short loc_180063566
0x180063544  mov     dword ptr [rbx+14h], 2
0x18006354b  mov     rcx, [rsi+28h]
0x18006354f  mov     rax, [rcx+8]
0x180063553  mov     [rbx], rcx
0x180063556  mov     [rbx+8], rax
0x18006355a  mov     [rcx+8], rbx
0x18006355e  mov     [rax], rbx
0x180063561  mov     edi, r14d
0x180063564  jmp     short loc_180063587
0x180063566  mov     rcx, rbx; this
0x180063569  call    ??_GCShareInfo@@QEAAPEAXI@Z; CShareInfo::`scalar deleting destructor'(uint)
0x18006356e  jmp     short loc_180063587
0x180063570  mov     edx, 8000010Dh
0x180063575  jmp     loc_18006343D
0x18006357a  mov     rcx, [rcx]; HWND
0x18006357d  mov     edx, 8000010Ch; int
0x180063582  call    ?MyErrorDialog@@YAXPEAUHWND__@@JZZ; MyErrorDialog(HWND__ *,long,...)
0x180063587  mov     eax, edi
0x180063589  mov     rcx, [rsp+478h+var_28]
0x180063591  xor     rcx, rsp; StackCookie
0x180063594  call    __security_check_cookie
0x180063599  lea     r11, [rsp+478h+var_18]
0x1800635a1  mov     rbx, [r11+30h]
0x1800635a5  mov     rbp, [r11+38h]
0x1800635a9  mov     rsp, r11
0x1800635ac  pop     r14
0x1800635ae  pop     rdi
0x1800635af  pop     rsi
0x1800635b0  retn
```
