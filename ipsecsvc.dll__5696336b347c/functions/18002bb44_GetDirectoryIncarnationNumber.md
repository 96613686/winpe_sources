# GetDirectoryIncarnationNumber

- ea: `0x18002bb44`
- end: `0x18002bdec`
- name: `GetDirectoryIncarnationNumber`
- size: `680`
- prototype: `__int64 __fastcall(int, _DWORD *)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002ce78`
- `0x18002cf74`
- `0x18002d2ec`

## callees

- `0x180006f60`
- `0x18000e510`
- `0x18002bb44`
- `0x1800353e4`
- `0x180038f04`
- `0x180038f44`
- `0x180039400`
- `0x180039444`
- `0x18003eaa8`
- `0x18003eac4`
- `0x18003f168`

## import_xrefs

- `WLDAP32!__imp_ldap_msgfree` at `0x18002bdc3`
- `WLDAP32!__imp_ldap_msgfree` at `0x18002bdc3`

## pseudocode

```c
__int64 __fastcall GetDirectoryIncarnationNumber(int a1, _DWORD *a2)
{
  LDAP *v2; // r14
  _QWORD *v3; // rsi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned int Values; // eax
  LPVOID lpMem; // [rsp+30h] [rbp-30h] BYREF
  LDAPMessage *res; // [rsp+38h] [rbp-28h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h] BYREF
  PWSTR v17[2]; // [rsp+50h] [rbp-10h] BYREF
  int v18; // [rsp+98h] [rbp+38h] BYREF
  LDAP *v19; // [rsp+A0h] [rbp+40h]
  _QWORD *v20; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  lpMem = 0;
  v3 = 0;
  v19 = 0;
  v17[1] = 0;
  res = 0;
  v17[0] = (PWSTR)L"whenChanged";
  v15 = 0;
  v20 = 0;
  v18 = 0;
  v16 = 0;
  *a2 = 0;
  v6 = ComputeDefaultDirectory((__int64 *)&lpMem);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v9 = 101;
    goto LABEL_28;
  }
  v10 = OpenDirectoryServerHandle((LPCWSTR)lpMem);
  v7 = v10;
  if ( v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v10);
      v2 = v19;
LABEL_29:
      v8 = WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    v2 = v19;
    goto LABEL_30;
  }
  v2 = v19;
  v6 = LdapSearchHelper((int)v19, a1, 0, (int)L"(objectClass=*)", v17, &res);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v9 = 103;
    goto LABEL_28;
  }
  v6 = LdapFirstEntry(v2, res, &v15);
  v7 = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v9 = 104;
    goto LABEL_28;
  }
  Values = LdapGetValues((_DWORD)v2, v15, (unsigned int)L"whenChanged", (unsigned int)&v20, (__int64)&v18);
  v7 = Values;
  if ( !Values )
  {
    v3 = v20;
    if ( !v20 )
      goto LABEL_34;
    v6 = GeneralizedTimeToTime(*v20, &v16);
    v7 = v6;
    if ( !v6 )
    {
      *a2 = v16;
      goto LABEL_34;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_30;
    v9 = 106;
LABEL_28:
    WPP_SF_d(v8[2], v9, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v6);
    goto LABEL_29;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, Values);
    v3 = v20;
    goto LABEL_29;
  }
  v3 = v20;
LABEL_30:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 )
    WPP_SF_d(v8[2], 107, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v7);
LABEL_34:
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( v2 )
    CloseDirectoryServerHandle(v2);
  if ( res )
    ldap_msgfree(res);
  if ( v3 )
    LdapValueFree(v3);
  return v7;
}

```

## disassembly

```asm
0x18002bb44  mov     [rsp-28h+arg_0], rbx
0x18002bb49  push    rbp
0x18002bb4a  push    rsi
0x18002bb4b  push    rdi
0x18002bb4c  push    r14
0x18002bb4e  push    r15
0x18002bb50  mov     rbp, rsp
0x18002bb53  sub     rsp, 60h
0x18002bb57  xor     r14d, r14d
0x18002bb5a  mov     [rbp+lpMem], 0
0x18002bb62  xor     esi, esi
0x18002bb64  mov     [rbp+arg_10], r14
0x18002bb68  mov     r15, rcx
0x18002bb6b  mov     [rbp+var_8], r14
0x18002bb6f  lea     rax, aWhenchanged_0; "whenChanged"
0x18002bb76  mov     [rbp+res], r14
0x18002bb7a  lea     rcx, [rbp+lpMem]
0x18002bb7e  mov     [rbp+var_10], rax
0x18002bb82  mov     [rbp+var_20], r14
0x18002bb86  mov     rdi, rdx
0x18002bb89  mov     [rbp+arg_18], rsi
0x18002bb8d  mov     [rbp+arg_8], esi
0x18002bb90  mov     [rbp+var_18], rsi
0x18002bb94  mov     [rdx], esi
0x18002bb96  call    ComputeDefaultDirectory
0x18002bb9b  mov     ebx, eax
0x18002bb9d  test    eax, eax
0x18002bb9f  jz      short loc_18002BBCA
0x18002bba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bba8  lea     rdi, WPP_GLOBAL_Control
0x18002bbaf  cmp     rcx, rdi
0x18002bbb2  jz      loc_18002BD9D
0x18002bbb8  test    byte ptr [rcx+1Ch], 10h
0x18002bbbc  jz      loc_18002BD73
0x18002bbc2  lea     edx, [rsi+65h]
0x18002bbc5  jmp     loc_18002BD59
0x18002bbca  mov     rcx, [rbp+lpMem]; DomainName
0x18002bbce  lea     r8, [rbp+arg_10]
0x18002bbd2  call    OpenDirectoryServerHandle
0x18002bbd7  mov     ebx, eax
0x18002bbd9  test    eax, eax
0x18002bbdb  jz      short loc_18002BC20
0x18002bbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbe4  lea     rdi, WPP_GLOBAL_Control
0x18002bbeb  cmp     rcx, rdi
0x18002bbee  jz      short loc_18002BC17
0x18002bbf0  test    byte ptr [rcx+1Ch], 10h
0x18002bbf4  jz      short loc_18002BC17
0x18002bbf6  mov     rcx, [rcx+10h]
0x18002bbfa  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bc01  mov     edx, 66h ; 'f'
0x18002bc06  mov     r9d, eax
0x18002bc09  call    WPP_SF_d
0x18002bc0e  mov     r14, [rbp+arg_10]
0x18002bc12  jmp     loc_18002BD6C
0x18002bc17  mov     r14, [rbp+arg_10]
0x18002bc1b  jmp     loc_18002BD73
0x18002bc20  mov     r14, [rbp+arg_10]
0x18002bc24  lea     rax, [rbp+res]
0x18002bc28  mov     [rsp+60h+var_38], rax; LDAPMessage **
0x18002bc2d  lea     r9, aObjectclass; "(objectClass=*)"
0x18002bc34  lea     rax, [rbp+var_10]
0x18002bc38  xor     r8d, r8d; int
0x18002bc3b  mov     rdx, r15; int
0x18002bc3e  mov     [rsp+60h+var_40], rax; PZPWSTR
0x18002bc43  mov     rcx, r14; int
0x18002bc46  call    LdapSearchHelper
0x18002bc4b  mov     ebx, eax
0x18002bc4d  test    eax, eax
0x18002bc4f  jz      short loc_18002BC7C
0x18002bc51  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc58  lea     rdi, WPP_GLOBAL_Control
0x18002bc5f  cmp     rcx, rdi
0x18002bc62  jz      loc_18002BD9D
0x18002bc68  test    byte ptr [rcx+1Ch], 10h
0x18002bc6c  jz      loc_18002BD73
0x18002bc72  mov     edx, 67h ; 'g'
0x18002bc77  jmp     loc_18002BD59
0x18002bc7c  mov     rdx, [rbp+res]
0x18002bc80  lea     r8, [rbp+var_20]
0x18002bc84  mov     rcx, r14
0x18002bc87  call    LdapFirstEntry
0x18002bc8c  mov     ebx, eax
0x18002bc8e  test    eax, eax
0x18002bc90  jz      short loc_18002BCBD
0x18002bc92  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bc99  lea     rdi, WPP_GLOBAL_Control
0x18002bca0  cmp     rcx, rdi
0x18002bca3  jz      loc_18002BD9D
0x18002bca9  test    byte ptr [rcx+1Ch], 10h
0x18002bcad  jz      loc_18002BD73
0x18002bcb3  mov     edx, 68h ; 'h'
0x18002bcb8  jmp     loc_18002BD59
0x18002bcbd  mov     rdx, [rbp+var_20]
0x18002bcc1  lea     rax, [rbp+arg_8]
0x18002bcc5  lea     r9, [rbp+arg_18]
0x18002bcc9  mov     [rsp+60h+var_40], rax
0x18002bcce  lea     r8, aWhenchanged_0; "whenChanged"
0x18002bcd5  mov     rcx, r14
0x18002bcd8  call    LdapGetValues
0x18002bcdd  mov     ebx, eax
0x18002bcdf  test    eax, eax
0x18002bce1  jz      short loc_18002BD20
0x18002bce3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcea  lea     rdi, WPP_GLOBAL_Control
0x18002bcf1  cmp     rcx, rdi
0x18002bcf4  jz      short loc_18002BD1A
0x18002bcf6  test    byte ptr [rcx+1Ch], 10h
0x18002bcfa  jz      short loc_18002BD1A
0x18002bcfc  mov     rcx, [rcx+10h]
0x18002bd00  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bd07  mov     edx, 69h ; 'i'
0x18002bd0c  mov     r9d, eax
0x18002bd0f  call    WPP_SF_d
0x18002bd14  mov     rsi, [rbp+arg_18]
0x18002bd18  jmp     short loc_18002BD6C
0x18002bd1a  mov     rsi, [rbp+arg_18]
0x18002bd1e  jmp     short loc_18002BD73
0x18002bd20  mov     rsi, [rbp+arg_18]
0x18002bd24  test    rsi, rsi
0x18002bd27  jz      short loc_18002BD9D
0x18002bd29  mov     rcx, [rsi]
0x18002bd2c  lea     rdx, [rbp+var_18]
0x18002bd30  call    GeneralizedTimeToTime
0x18002bd35  mov     ebx, eax
0x18002bd37  test    eax, eax
0x18002bd39  jz      short loc_18002BD98
0x18002bd3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd42  lea     rdi, WPP_GLOBAL_Control
0x18002bd49  cmp     rcx, rdi
0x18002bd4c  jz      short loc_18002BD9D
0x18002bd4e  test    byte ptr [rcx+1Ch], 10h
0x18002bd52  jz      short loc_18002BD73
0x18002bd54  mov     edx, 6Ah ; 'j'
0x18002bd59  mov     rcx, [rcx+10h]
0x18002bd5d  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bd64  mov     r9d, eax
0x18002bd67  call    WPP_SF_d
0x18002bd6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd73  cmp     rcx, rdi
0x18002bd76  jz      short loc_18002BD9D
0x18002bd78  test    byte ptr [rcx+1Ch], 10h
0x18002bd7c  jz      short loc_18002BD9D
0x18002bd7e  mov     rcx, [rcx+10h]
0x18002bd82  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002bd89  mov     edx, 6Bh ; 'k'
0x18002bd8e  mov     r9d, ebx
0x18002bd91  call    WPP_SF_d
0x18002bd96  jmp     short loc_18002BD9D
0x18002bd98  mov     eax, dword ptr [rbp+var_18]
0x18002bd9b  mov     [rdi], eax
0x18002bd9d  cmp     [rbp+lpMem], 0
0x18002bda2  jz      short loc_18002BDAD
0x18002bda4  mov     rcx, [rbp+lpMem]; lpMem
0x18002bda8  call    IpsecFreeMem
0x18002bdad  test    r14, r14
0x18002bdb0  jz      short loc_18002BDBA
0x18002bdb2  mov     rcx, r14
0x18002bdb5  call    CloseDirectoryServerHandle
0x18002bdba  mov     rcx, [rbp+res]; res
0x18002bdbe  test    rcx, rcx
0x18002bdc1  jz      short loc_18002BDC9
0x18002bdc3  call    cs:__imp_ldap_msgfree
0x18002bdc9  test    rsi, rsi
0x18002bdcc  jz      short loc_18002BDD6
0x18002bdce  mov     rcx, rsi
0x18002bdd1  call    LdapValueFree
0x18002bdd6  mov     eax, ebx
0x18002bdd8  mov     rbx, [rsp+60h+arg_0]
0x18002bde0  add     rsp, 60h
0x18002bde4  pop     r15
0x18002bde6  pop     r14
0x18002bde8  pop     rdi
0x18002bde9  pop     rsi
0x18002bdea  pop     rbp
0x18002bdeb  retn
```
