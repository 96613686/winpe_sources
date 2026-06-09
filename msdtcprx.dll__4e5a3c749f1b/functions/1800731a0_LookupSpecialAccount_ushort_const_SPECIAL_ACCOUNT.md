# LookupSpecialAccount(ushort const *,_SPECIAL_ACCOUNT_ * *)

- ea: `0x1800731a0`
- end: `0x180073389`
- name: `?LookupSpecialAccount@@YAJPEBGPEAPEAU_SPECIAL_ACCOUNT_@@@Z`
- size: `489`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SPECIAL_ACCOUNT_ **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180072cd4`
- `0x180073390`

## callees

- `0x180006054`
- `0x18001d178`
- `0x18001d184`
- `0x180062658`
- `0x1800731a0`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800732d4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800732f4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007330f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800732d4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800732f4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18007330f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073352`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073279`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180073279`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800732c2`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800732c2`
- `msvcrt!wcschr` at `0x18007323e`
- `msvcrt!wcschr` at `0x18007323e`
- `msvcrt!_wcsicmp` at `0x18007332c`
- `msvcrt!_wcsicmp` at `0x18007332c`

## pseudocode

```c
__int64 __fastcall LookupSpecialAccount(const unsigned __int16 *a1, wchar_t ***a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // r14
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  unsigned int v8; // ebx
  HLOCAL v9; // rax
  void *v10; // rdi
  wchar_t **v11; // rax
  DWORD uBytes; // [rsp+40h] [rbp-238h] BYREF
  enum _SID_NAME_USE uBytes_4; // [rsp+44h] [rbp-234h] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-230h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+50h] [rbp-228h] BYREF

  uBytes = 68;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v5 = (int)v4 + 3;
  v6 = (unsigned __int16 *)operator new[](saturated_mul(v5, 2u));
  v7 = v6;
  if ( !v6 )
    return (unsigned int)-2147024882;
  memset_0(v6, 0, 2 * v5);
  if ( wcschr(a1, 0x5Cu) )
  {
    StringCchCopyW(v7, v5, a1);
  }
  else
  {
    StringCchCopyW(v7, v5, L".\\");
    StringCchCatW(v7, v5, a1);
  }
  v9 = LocalAlloc(0, uBytes);
  cchReferencedDomainName = 256;
  v10 = v9;
  uBytes_4 = 0;
  if ( v9 )
  {
    if ( LookupAccountNameW(0, v7, v9, &uBytes, ReferencedDomainName, &cchReferencedDomainName, &uBytes_4) )
    {
      if ( IsWellKnownSid(v10, WinLocalSystemSid) )
      {
LABEL_13:
        v11 = &g_aSpecialAccounts;
LABEL_14:
        *a2 = v11;
        v8 = 0;
        goto LABEL_22;
      }
      if ( IsWellKnownSid(v10, WinLocalServiceSid) )
      {
        v11 = &off_1800D5260;
        goto LABEL_14;
      }
      if ( IsWellKnownSid(v10, WinNetworkServiceSid) )
      {
        v11 = &off_1800D5270;
        goto LABEL_14;
      }
    }
    else if ( !_wcsicmp(g_aSpecialAccounts, v7) )
    {
      goto LABEL_13;
    }
    v8 = 1;
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_22:
  operator delete(v7);
  if ( v10 )
    LocalFree(v10);
  return v8;
}

```

## disassembly

```asm
0x1800731a0  mov     [rsp+arg_10], rbx
0x1800731a5  mov     [rsp+arg_18], rbp
0x1800731aa  push    rsi
0x1800731ab  push    rdi
0x1800731ac  push    r14
0x1800731ae  sub     rsp, 260h
0x1800731b5  mov     rax, cs:__security_cookie
0x1800731bc  xor     rax, rsp
0x1800731bf  mov     [rsp+278h+var_28], rax
0x1800731c7  xor     ebp, ebp
0x1800731c9  mov     dword ptr [rsp+278h+uBytes], 44h ; 'D'
0x1800731d1  mov     rbx, rdx
0x1800731d4  mov     rdi, rcx
0x1800731d7  test    rcx, rcx
0x1800731da  jz      loc_18007335A
0x1800731e0  test    rdx, rdx
0x1800731e3  jz      loc_18007335A
0x1800731e9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800731ed  mov     [rdx], rbp
0x1800731f0  mov     rax, rcx
0x1800731f3  inc     rax
0x1800731f6  cmp     [rdi+rax*2], bp
0x1800731fa  jnz     short loc_1800731F3
0x1800731fc  add     eax, 3
0x1800731ff  movsxd  r14, eax
0x180073202  mov     eax, 2
0x180073207  mul     r14
0x18007320a  cmovb   rax, rcx
0x18007320e  mov     rcx, rax; unsigned __int64
0x180073211  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180073216  mov     rsi, rax
0x180073219  test    rax, rax
0x18007321c  jnz     short loc_180073228
0x18007321e  mov     ebx, 8007000Eh
0x180073223  jmp     loc_18007335F
0x180073228  lea     r8, [r14+r14]; Size
0x18007322c  xor     edx, edx; Val
0x18007322e  mov     rcx, rsi; void *
0x180073231  call    memset_0
0x180073236  mov     edx, 5Ch ; '\'; Ch
0x18007323b  mov     rcx, rdi; Str
0x18007323e  call    cs:__imp_wcschr
0x180073244  mov     rdx, r14; unsigned __int64
0x180073247  mov     rcx, rsi; unsigned __int16 *
0x18007324a  test    rax, rax
0x18007324d  jnz     short loc_18007326B
0x18007324f  lea     r8, asc_1800BC720; ".\\"
0x180073256  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007325b  mov     r8, rdi; unsigned __int16 *
0x18007325e  mov     rdx, r14; unsigned __int64
0x180073261  mov     rcx, rsi; unsigned __int16 *
0x180073264  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180073269  jmp     short loc_180073273
0x18007326b  mov     r8, rdi; unsigned __int16 *
0x18007326e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180073273  mov     edx, dword ptr [rsp+278h+uBytes]; uBytes
0x180073277  xor     ecx, ecx; uFlags
0x180073279  call    cs:__imp_LocalAlloc
0x18007327f  mov     [rsp+278h+var_230], 100h
0x180073287  mov     rdi, rax
0x18007328a  mov     dword ptr [rsp+278h+uBytes+4], ebp
0x18007328e  test    rax, rax
0x180073291  jz      loc_18007333D
0x180073297  lea     rax, [rsp+278h+uBytes+4]
0x18007329c  mov     r8, rdi; Sid
0x18007329f  mov     [rsp+278h+peUse], rax; peUse
0x1800732a4  lea     r9, [rsp+278h+uBytes]; cbSid
0x1800732a9  lea     rax, [rsp+278h+var_230]
0x1800732ae  mov     rdx, rsi; lpAccountName
0x1800732b1  mov     [rsp+278h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800732b6  xor     ecx, ecx; lpSystemName
0x1800732b8  lea     rax, [rsp+278h+var_228]
0x1800732bd  mov     [rsp+278h+ReferencedDomainName], rax; ReferencedDomainName
0x1800732c2  call    cs:__imp_LookupAccountNameW
0x1800732c8  test    eax, eax
0x1800732ca  jz      short loc_180073322
0x1800732cc  mov     edx, 16h; WellKnownSidType
0x1800732d1  mov     rcx, rdi; pSid
0x1800732d4  call    cs:__imp_IsWellKnownSid
0x1800732da  test    eax, eax
0x1800732dc  jz      short loc_1800732EC
0x1800732de  lea     rax, ?g_aSpecialAccounts@@3PAU_SPECIAL_ACCOUNT_@@A; _SPECIAL_ACCOUNT_ near * g_aSpecialAccounts
0x1800732e5  mov     [rbx], rax
0x1800732e8  mov     ebx, ebp
0x1800732ea  jmp     short loc_180073342
0x1800732ec  mov     edx, 17h; WellKnownSidType
0x1800732f1  mov     rcx, rdi; pSid
0x1800732f4  call    cs:__imp_IsWellKnownSid
0x1800732fa  test    eax, eax
0x1800732fc  jz      short loc_180073307
0x1800732fe  lea     rax, off_1800D5260; "NT AUTHORITY\\LocalService"
0x180073305  jmp     short loc_1800732E5
0x180073307  mov     edx, 18h; WellKnownSidType
0x18007330c  mov     rcx, rdi; pSid
0x18007330f  call    cs:__imp_IsWellKnownSid
0x180073315  test    eax, eax
0x180073317  jz      short loc_180073336
0x180073319  lea     rax, off_1800D5270; "NT AUTHORITY\\NetworkService"
0x180073320  jmp     short loc_1800732E5
0x180073322  mov     rcx, cs:?g_aSpecialAccounts@@3PAU_SPECIAL_ACCOUNT_@@A; String1
0x180073329  mov     rdx, rsi; String2
0x18007332c  call    cs:__imp__wcsicmp
0x180073332  test    eax, eax
0x180073334  jz      short loc_1800732DE
0x180073336  mov     ebx, 1
0x18007333b  jmp     short loc_180073342
0x18007333d  mov     ebx, 8007000Eh
0x180073342  mov     rcx, rsi; Block
0x180073345  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007334a  test    rdi, rdi
0x18007334d  jz      short loc_18007335F
0x18007334f  mov     rcx, rdi; hMem
0x180073352  call    cs:__imp_LocalFree
0x180073358  jmp     short loc_18007335F
0x18007335a  mov     ebx, 80070057h
0x18007335f  mov     eax, ebx
0x180073361  mov     rcx, [rsp+278h+var_28]
0x180073369  xor     rcx, rsp; StackCookie
0x18007336c  call    __security_check_cookie
0x180073371  lea     r11, [rsp+278h+var_18]
0x180073379  mov     rbx, [r11+30h]
0x18007337d  mov     rbp, [r11+38h]
0x180073381  mov     rsp, r11
0x180073384  pop     r14
0x180073386  pop     rdi
0x180073387  pop     rsi
0x180073388  retn
```
