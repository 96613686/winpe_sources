# LsaDbpDsIsSecretDsTrustedDomain(_UNICODE_STRING *,_LSAP_DB_OBJECT_INFORMATION *,ulong,ulong,void * *,uchar *)

- ea: `0x180011a44`
- end: `0x180011bff`
- name: `?LsaDbpDsIsSecretDsTrustedDomain@@YAJPEAU_UNICODE_STRING@@PEAU_LSAP_DB_OBJECT_INFORMATION@@KKPEAPEAXPEAE@Z`
- size: `443`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _LSAP_DB_OBJECT_INFORMATION *, unsigned int, unsigned int, void **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002f4f0`

## callees

- `0x18000bf70`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x18000fde0`
- `0x180011a44`

## import_xrefs

- `LSASRV!LsapDbOpenObject` at `0x180011bb8`
- `LSASRV!LsapDbOpenObject` at `0x180011bb8`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180011b27`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x180011b27`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180011bc0`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x180011bc0`
- `ntdll!RtlInitUnicodeString` at `0x180011b21`
- `ntdll!RtlInitUnicodeString` at `0x180011b21`

## pseudocode

```c
__int64 __fastcall LsaDbpDsIsSecretDsTrustedDomain(
        struct _UNICODE_STRING *a1,
        struct _LSAP_DB_OBJECT_INFORMATION *a2,
        int a3,
        unsigned int a4,
        void **a5,
        unsigned __int8 *a6)
{
  int LockTrustedDomainList; // ebx
  PWSTR Buffer; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v19; // [rsp+20h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-51h] BYREF
  __int128 v21; // [rsp+40h] [rbp-39h] BYREF
  __int128 v22; // [rsp+50h] [rbp-29h]
  __int128 v23; // [rsp+60h] [rbp-19h]
  __int128 v24; // [rsp+70h] [rbp-9h]
  __int64 v25; // [rsp+80h] [rbp+7h]

  v19 = 0;
  DestinationString = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids);
  *a6 = 0;
  if ( !HIBYTE(word_18004706B) )
    return 0;
  LockTrustedDomainList = 0;
  if ( byte_18004706E )
  {
    if ( a1->Length > 6u )
    {
      Buffer = a1->Buffer;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids, Buffer + 3);
      RtlInitUnicodeString(&DestinationString, Buffer + 3);
      LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v13);
      if ( LockTrustedDomainList >= 0 )
      {
        v14 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)&DestinationString, &v19);
        if ( v14 >= 0 )
        {
          LockTrustedDomainList = v14;
          if ( (*((_BYTE *)v19 + 56) & 2) != 0 )
            *a6 = 1;
          if ( a5 )
          {
            v16 = *((_OWORD *)a2 + 1);
            v21 = *(_OWORD *)a2;
            v17 = *((_OWORD *)a2 + 2);
            LODWORD(v21) = 2;
            v22 = v16;
            v18 = *((_OWORD *)a2 + 3);
            *((_QWORD *)&v22 + 1) = &DestinationString;
            v23 = v17;
            v25 = *((_QWORD *)a2 + 8);
            v24 = v18;
            LockTrustedDomainList = LsapDbOpenObject(&v21, a4, a3 | 0x400000u, a5, (_DWORD)v19);
          }
        }
        else
        {
          LockTrustedDomainList = 0;
          if ( v14 != -1073741601 )
            LockTrustedDomainList = v14;
        }
        LsapDbExpReleaseLockTrustedDomainList(v15);
      }
    }
    goto LABEL_21;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids, a1);
LABEL_21:
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids,
        (unsigned int)LockTrustedDomainList);
  }
  return (unsigned int)LockTrustedDomainList;
}

```

## disassembly

```asm
0x180011a44  push    rbp
0x180011a46  push    rbx
0x180011a47  push    rsi
0x180011a48  push    rdi
0x180011a49  push    r12
0x180011a4b  push    r14
0x180011a4d  push    r15
0x180011a4f  lea     rbp, [rsp-17h]
0x180011a54  sub     rsp, 90h
0x180011a5b  xorps   xmm0, xmm0
0x180011a5e  mov     [rbp+47h+var_A0], 0
0x180011a66  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x180011a6a  mov     r12d, r9d
0x180011a6d  mov     r15d, r8d
0x180011a70  mov     r14, rdx
0x180011a73  mov     rdi, rcx
0x180011a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180011a7d  test    byte ptr [rcx+1Ch], 1
0x180011a81  jz      short loc_180011A98
0x180011a83  mov     rcx, [rcx+10h]
0x180011a87  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180011a8e  mov     edx, 16h
0x180011a93  call    WPP_SF_
0x180011a98  mov     rsi, [rbp+47h+arg_28]
0x180011a9c  mov     byte ptr [rsi], 0
0x180011a9f  cmp     byte ptr cs:word_18004706B+1, 0
0x180011aa6  jnz     short loc_180011AAF
0x180011aa8  xor     eax, eax
0x180011aaa  jmp     loc_180011BED
0x180011aaf  xor     ebx, ebx
0x180011ab1  cmp     cs:byte_18004706E, bl
0x180011ab7  jnz     short loc_180011AE5
0x180011ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ac0  test    byte ptr [rcx+1Ch], 1
0x180011ac4  jz      loc_180011BEB
0x180011aca  mov     rcx, [rcx+10h]
0x180011ace  lea     edx, [rbx+17h]
0x180011ad1  mov     r9, rdi
0x180011ad4  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180011adb  call    WPP_SF_Z
0x180011ae0  jmp     loc_180011BC6
0x180011ae5  cmp     word ptr [rdi], 6
0x180011ae9  jbe     loc_180011BC6
0x180011aef  mov     rbx, [rdi+8]
0x180011af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011afa  test    byte ptr [rcx+1Ch], 1
0x180011afe  jz      short loc_180011B19
0x180011b00  mov     rcx, [rcx+10h]
0x180011b04  lea     r9, [rbx+6]
0x180011b08  mov     edx, 18h
0x180011b0d  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180011b14  call    WPP_SF_S
0x180011b19  lea     rdx, [rbx+6]; SourceString
0x180011b1d  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x180011b21  call    cs:__imp_RtlInitUnicodeString
0x180011b27  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x180011b2d  mov     ebx, eax
0x180011b2f  test    eax, eax
0x180011b31  js      loc_180011BC6
0x180011b37  lea     rdx, [rbp+47h+var_A0]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x180011b3b  lea     rcx, [rbp+47h+DestinationString]; struct _LSAPR_UNICODE_STRING *
0x180011b3f  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x180011b44  test    eax, eax
0x180011b46  jns     short loc_180011B54
0x180011b48  xor     ebx, ebx
0x180011b4a  cmp     eax, 0C00000DFh
0x180011b4f  cmovnz  ebx, eax
0x180011b52  jmp     short loc_180011BC0
0x180011b54  mov     ebx, eax
0x180011b56  mov     rax, [rbp+47h+var_A0]
0x180011b5a  test    byte ptr [rax+38h], 2
0x180011b5e  jz      short loc_180011B63
0x180011b60  mov     byte ptr [rsi], 1
0x180011b63  mov     r9, [rbp+47h+arg_20]
0x180011b67  test    r9, r9
0x180011b6a  jz      short loc_180011BC0
0x180011b6c  movups  xmm0, xmmword ptr [r14]
0x180011b70  bts     r15d, 16h
0x180011b75  lea     rax, [rbp+47h+DestinationString]
0x180011b79  movups  xmm1, xmmword ptr [r14+10h]
0x180011b7e  lea     rcx, [rbp+47h+var_80]
0x180011b82  mov     r8d, r15d
0x180011b85  movaps  [rbp+47h+var_80], xmm0
0x180011b89  mov     edx, r12d
0x180011b8c  movups  xmm0, xmmword ptr [r14+20h]
0x180011b91  mov     dword ptr [rbp+47h+var_80], 2
0x180011b98  movaps  [rbp+47h+var_70], xmm1
0x180011b9c  movups  xmm1, xmmword ptr [r14+30h]
0x180011ba1  mov     qword ptr [rbp+47h+var_70+8], rax
0x180011ba5  movaps  [rbp+47h+var_60], xmm0
0x180011ba9  movsd   xmm0, qword ptr [r14+40h]
0x180011baf  movsd   [rbp+47h+var_40], xmm0
0x180011bb4  movaps  [rbp+47h+var_50], xmm1
0x180011bb8  call    cs:__imp_LsapDbOpenObject
0x180011bbe  mov     ebx, eax
0x180011bc0  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x180011bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bcd  test    byte ptr [rcx+1Ch], 1
0x180011bd1  jz      short loc_180011BEB
0x180011bd3  mov     rcx, [rcx+10h]
0x180011bd7  lea     r8, WPP_0cb0a8c443e335b2be1df43914923a62_Traceguids
0x180011bde  mov     edx, 19h
0x180011be3  mov     r9d, ebx
0x180011be6  call    WPP_SF_d
0x180011beb  mov     eax, ebx
0x180011bed  add     rsp, 90h
0x180011bf4  pop     r15
0x180011bf6  pop     r14
0x180011bf8  pop     r12
0x180011bfa  pop     rdi
0x180011bfb  pop     rsi
0x180011bfc  pop     rbx
0x180011bfd  pop     rbp
0x180011bfe  retn
```
