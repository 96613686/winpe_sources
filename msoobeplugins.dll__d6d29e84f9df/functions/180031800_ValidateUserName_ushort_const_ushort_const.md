# ValidateUserName(ushort const *,ushort const *)

- ea: `0x180031800`
- end: `0x180031a1f`
- name: `?ValidateUserName@@YAJPEBG0@Z`
- size: `543`
- prototype: `__int64 __fastcall(LPCWCH lpString2, LPCWCH lpString1)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002e750`
- `0x18002f510`
- `0x18002f9a0`
- `0x180031150`

## callees

- `0x180003470`
- `0x180008544`
- `0x180031540`
- `0x1800316ac`
- `0x180031800`
- `0x180031a28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180031895`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180031895`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180031871`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180031871`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800318ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800318ff`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003197b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003197b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031957`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180031957`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800318d6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x1800318d6`

## string_xrefs

- `0x1800319e3`: `shell\oobe\machine\plugins\localuser\localuserutil.cpp`

## pseudocode

```c
__int64 __fastcall ValidateUserName(LPCWCH lpString2, WCHAR *lpString1)
{
  __int64 v4; // rdi
  unsigned __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int lpString2a; // [rsp+20h] [rbp-E0h]
  DWORD nSize[2]; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cbSid; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[20]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Sid[80]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  *(_QWORD *)nSize = 0;
  if ( (int)StringCchLengthW(lpString2, 0x15u, (unsigned __int64 *)nSize) < 0 )
    goto LABEL_27;
  v4 = -1;
  do
    ++v4;
  while ( lpString2[v4] );
  if ( wcscspn(lpString2, L"\"/\\[]:|<>+=;,?*%@") != v4 )
  {
LABEL_27:
    v7 = 76;
    goto LABEL_28;
  }
  v5 = *(_QWORD *)nSize;
  if ( !*(_QWORD *)nSize )
  {
LABEL_26:
    v8 = -2147023736;
    v7 = 79;
    goto LABEL_29;
  }
  v6 = 0;
  while ( (unsigned int)_o_iswspace(lpString2[v6]) )
  {
    if ( ++v6 >= v5 )
    {
      if ( v6 == v5 )
        goto LABEL_26;
      break;
    }
  }
  if ( lpString2[v5 - 1] == 46 )
  {
    v7 = 82;
LABEL_28:
    v8 = -2147023581;
    goto LABEL_29;
  }
  if ( !lpString1 )
  {
    nSize[0] = 16;
    if ( !GetComputerNameW(Buffer, nSize) )
      goto LABEL_17;
    lpString1 = Buffer;
  }
  if ( CompareStringW(0x400u, 1u, lpString1, -1, lpString2, -1) == 2 )
  {
    v8 = -2147024844;
    v7 = 97;
    goto LABEL_29;
  }
LABEL_17:
  cchReferencedDomainName = 260;
  cbSid = 68;
  peUse = 0;
  if ( LookupAccountNameW(0, lpString2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse)
    && (!lpString1 || CompareStringOrdinal(lpString1, -1, ReferencedDomainName, -1, 1) == 2) )
  {
    v8 = -2147023580;
    v7 = 110;
  }
  else if ( _IsReservedUserName(lpString2) )
  {
    v8 = -2147023580;
    v7 = 111;
  }
  else
  {
    if ( !(unsigned int)SHIsSAMNameReservedWord(lpString2) )
      return 0;
    v8 = -2147024198;
    v7 = 112;
  }
LABEL_29:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localuserutil.cpp",
    (const char *)v8,
    lpString2a);
  return v8;
}

```

## disassembly

```asm
0x180031800  mov     [rsp-8+arg_10], rbx
0x180031805  mov     [rsp-8+arg_18], rsi
0x18003180a  push    rbp
0x18003180b  push    rdi
0x18003180c  push    r12
0x18003180e  push    r14
0x180031810  push    r15
0x180031812  lea     rbp, [rsp-1F0h]
0x18003181a  sub     rsp, 2F0h
0x180031821  mov     rax, cs:__security_cookie
0x180031828  xor     rax, rsp
0x18003182b  mov     [rbp+210h+var_30], rax
0x180031832  xor     r15d, r15d
0x180031835  lea     r8, [rsp+310h+nSize]; unsigned __int64 *
0x18003183a  mov     r14, rdx
0x18003183d  mov     qword ptr [rsp+310h+nSize], r15
0x180031842  mov     rbx, rcx
0x180031845  lea     edx, [r15+15h]; unsigned __int64
0x180031849  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003184e  test    eax, eax
0x180031850  js      loc_1800319D2
0x180031856  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003185a  mov     rdi, r12
0x18003185d  inc     rdi
0x180031860  cmp     [rbx+rdi*2], r15w
0x180031865  jnz     short loc_18003185D
0x180031867  lea     rdx, Control; "\"/\\[]:|<>+=;,?*%@"
0x18003186e  mov     rcx, rbx; String
0x180031871  call    cs:__imp_wcscspn
0x180031877  cmp     rax, rdi
0x18003187a  jnz     loc_1800319D2
0x180031880  mov     rdi, qword ptr [rsp+310h+nSize]
0x180031885  test    rdi, rdi
0x180031888  jz      loc_1800319C6
0x18003188e  mov     rsi, r15
0x180031891  movzx   ecx, word ptr [rbx+rsi*2]
0x180031895  call    cs:__imp__o_iswspace
0x18003189b  test    eax, eax
0x18003189d  jz      short loc_1800318AD
0x18003189f  inc     rsi
0x1800318a2  cmp     rsi, rdi
0x1800318a5  jb      short loc_180031891
0x1800318a7  jz      loc_1800319C6
0x1800318ad  cmp     word ptr [rbx+rdi*2-2], 2Eh ; '.'
0x1800318b3  jnz     short loc_1800318BF
0x1800318b5  mov     edx, 52h ; 'R'
0x1800318ba  jmp     loc_1800319D7
0x1800318bf  test    r14, r14
0x1800318c2  jnz     short loc_1800318E5
0x1800318c4  lea     rdx, [rsp+310h+nSize]; nSize
0x1800318c9  mov     [rsp+310h+nSize], 10h
0x1800318d1  lea     rcx, [rsp+310h+Buffer]; lpBuffer
0x1800318d6  call    cs:__imp_GetComputerNameW
0x1800318dc  test    eax, eax
0x1800318de  jz      short loc_180031917
0x1800318e0  lea     r14, [rsp+310h+Buffer]
0x1800318e5  mov     [rsp+310h+cchCount2], r12d; cchCount2
0x1800318ea  mov     r9d, r12d; cchCount1
0x1800318ed  mov     r8, r14; lpString1
0x1800318f0  mov     [rsp+310h+lpString2], rbx; lpString2
0x1800318f5  mov     edx, 1; dwCmpFlags
0x1800318fa  mov     ecx, 400h; Locale
0x1800318ff  call    cs:__imp_CompareStringW
0x180031905  cmp     eax, 2
0x180031908  jnz     short loc_180031917
0x18003190a  mov     ebx, 80070034h
0x18003190f  lea     edx, [rax+5Fh]
0x180031912  jmp     loc_1800319DC
0x180031917  lea     rax, [rsp+310h+var_2C8]
0x18003191c  mov     [rsp+310h+cchReferencedDomainName], 104h
0x180031924  mov     [rsp+310h+peUse], rax; peUse
0x180031929  lea     r9, [rsp+310h+cbSid]; cbSid
0x18003192e  lea     rax, [rsp+310h+cchReferencedDomainName]
0x180031933  mov     [rsp+310h+cbSid], 44h ; 'D'
0x18003193b  mov     qword ptr [rsp+310h+cchCount2], rax; cchReferencedDomainName
0x180031940  lea     r8, [rbp+210h+Sid]; Sid
0x180031944  lea     rax, [rbp+210h+ReferencedDomainName]
0x180031948  mov     [rsp+310h+var_2C8], r15d
0x18003194d  mov     rdx, rbx; lpAccountName
0x180031950  mov     [rsp+310h+lpString2], rax; ReferencedDomainName
0x180031955  xor     ecx, ecx; lpSystemName
0x180031957  call    cs:__imp_LookupAccountNameW
0x18003195d  test    eax, eax
0x18003195f  jz      short loc_180031992
0x180031961  test    r14, r14
0x180031964  jz      short loc_180031986
0x180031966  mov     r9d, r12d; cchCount2
0x180031969  mov     dword ptr [rsp+310h+lpString2], 1; bIgnoreCase
0x180031971  lea     r8, [rbp+210h+ReferencedDomainName]; lpString2
0x180031975  mov     edx, r12d; cchCount1
0x180031978  mov     rcx, r14; lpString1
0x18003197b  call    cs:__imp_CompareStringOrdinal
0x180031981  cmp     eax, 2
0x180031984  jnz     short loc_180031992
0x180031986  mov     ebx, 80070524h
0x18003198b  mov     edx, 6Eh ; 'n'
0x180031990  jmp     short loc_1800319DC
0x180031992  mov     rcx, rbx; lpString2
0x180031995  call    ?_IsReservedUserName@@YA_NPEBG@Z; _IsReservedUserName(ushort const *)
0x18003199a  test    al, al
0x18003199c  jz      short loc_1800319AA
0x18003199e  mov     ebx, 80070524h
0x1800319a3  mov     edx, 6Fh ; 'o'
0x1800319a8  jmp     short loc_1800319DC
0x1800319aa  mov     rcx, rbx; lpString2
0x1800319ad  call    ?SHIsSAMNameReservedWord@@YAHPEBG@Z; SHIsSAMNameReservedWord(ushort const *)
0x1800319b2  test    eax, eax
0x1800319b4  jz      short loc_1800319C2
0x1800319b6  mov     ebx, 800702BAh
0x1800319bb  mov     edx, 70h ; 'p'
0x1800319c0  jmp     short loc_1800319DC
0x1800319c2  xor     eax, eax
0x1800319c4  jmp     short loc_1800319F4
0x1800319c6  mov     ebx, 80070488h
0x1800319cb  mov     edx, 4Fh ; 'O'
0x1800319d0  jmp     short loc_1800319DC
0x1800319d2  mov     edx, 4Ch ; 'L'; void *
0x1800319d7  mov     ebx, 80070523h
0x1800319dc  mov     rcx, [rbp+218h]; this
0x1800319e3  lea     r8, aShellOobeMachi_29; "shell\\oobe\\machine\\plugins\\localuse"...
0x1800319ea  mov     r9d, ebx; char *
0x1800319ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319f2  mov     eax, ebx
0x1800319f4  mov     rcx, [rbp+210h+var_30]
0x1800319fb  xor     rcx, rsp; StackCookie
0x1800319fe  call    __security_check_cookie
0x180031a03  lea     r11, [rsp+310h+var_20]
0x180031a0b  mov     rbx, [r11+40h]
0x180031a0f  mov     rsi, [r11+48h]
0x180031a13  mov     rsp, r11
0x180031a16  pop     r15
0x180031a18  pop     r14
0x180031a1a  pop     r12
0x180031a1c  pop     rdi
0x180031a1d  pop     rbp
0x180031a1e  retn
```
