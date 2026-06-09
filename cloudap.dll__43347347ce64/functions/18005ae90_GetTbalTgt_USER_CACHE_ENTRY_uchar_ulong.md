# GetTbalTgt(_USER_CACHE_ENTRY *,uchar * *,ulong *)

- ea: `0x18005ae90`
- end: `0x18005b10a`
- name: `?GetTbalTgt@@YAJPEAU_USER_CACHE_ENTRY@@PEAPEAEPEAK@Z`
- size: `634`
- prototype: `__int64 __fastcall(struct _USER_CACHE_ENTRY *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b350`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18002d71c`
- `0x18005ae90`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18005af26`
- `ntdll!RtlInitUnicodeString` at `0x18005af26`
- `LSASRV!LsarClose` at `0x18005b0ee`
- `LSASRV!LsarClose` at `0x18005b0ee`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18005b0c2`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x18005b0c2`
- `LSASRV!LsarQuerySecret` at `0x18005af98`
- `LSASRV!LsarQuerySecret` at `0x18005af98`
- `LSASRV!LsarOpenSecret` at `0x18005af41`
- `LSASRV!LsarOpenSecret` at `0x18005af41`

## string_xrefs

- `0x18005aeea`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005af4d`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005afa4`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b00b`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005b054`: `onecore\ds\ext\cloudap\dll\tbal.cpp`
- `0x18005af68`: `LsarOpenSecret TGT`

## pseudocode

```c
__int64 __fastcall GetTbalTgt(struct _USER_CACHE_ENTRY *a1, unsigned __int8 **a2, unsigned int *a3)
{
  const unsigned __int16 *v4; // rdx
  unsigned int LSASecretName; // ebx
  const char *v7; // r9
  const char *v8; // r9
  const char *v9; // r9
  const void *v10; // rsi
  size_t v11; // rdi
  unsigned __int8 *v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  _BYTE *v15; // rax
  __int64 v16; // rdx
  bool v18[8]; // [rsp+20h] [rbp-40h]
  bool v19[8]; // [rsp+20h] [rbp-40h]
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  unsigned int *v22; // [rsp+90h] [rbp+30h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp+48h] BYREF

  v22 = 0;
  v4 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
  v20 = 0;
  SourceString = 0;
  DestinationString = 0;
  LSASecretName = GetLSASecretName((UUID *)((char *)a1 + 248), v4, (unsigned __int16 **)&SourceString, 1, 0);
  if ( LSASecretName )
  {
    v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
    *(_DWORD *)v18 = 577;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v7, *(_QWORD *)v18, "GetLSASecretName for TGT", &Class);
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    LSASecretName = LsarOpenSecret(g_LsaPolicyHandle, &DestinationString, 983043, &v20);
    if ( LSASecretName )
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
      *(_DWORD *)v18 = 586;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v8, *(_QWORD *)v18, "LsarOpenSecret TGT", &Class);
    }
    else
    {
      LSASecretName = LsarQuerySecret(v20, &v22, 0, 0, 0);
      if ( LSASecretName )
      {
        v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v19 = 593;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LSASecretName, v9, *(_QWORD *)v19, "LsarQuerySecret TGT", &Class);
      }
      else if ( v22 && (v10 = (const void *)*((_QWORD *)v22 + 1)) != 0 && (v11 = *v22, (_DWORD)v11) )
      {
        v12 = (unsigned __int8 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v11);
        *a2 = v12;
        if ( v12 )
        {
          memcpy_0(v12, v10, v11);
          *a3 = v11;
        }
        else
        {
          LSASecretName = -1073741801;
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
          *(_DWORD *)v19 = 610;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v13, *(_QWORD *)v19, "AllocateLsaHeap", &Class);
        }
      }
      else
      {
        LSASecretName = -1073740943;
        v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\tbal.cpp");
        *(_DWORD *)v19 = 600;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221226353LL, v14, *(_QWORD *)v19, "No TBAL TGT Secret", &Class);
      }
    }
  }
  if ( v22 )
  {
    v15 = (_BYTE *)*((_QWORD *)v22 + 1);
    if ( v15 )
    {
      v16 = *v22;
      if ( *v22 )
      {
        do
        {
          *v15++ = 0;
          --v16;
        }
        while ( v16 );
      }
    }
    LsaIFree_LSAPR_CR_CIPHER_VALUE();
  }
  if ( SourceString )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(SourceString);
  if ( v20 )
    LsarClose(&v20);
  return LSASecretName;
}

```

## disassembly

```asm
0x18005ae90  mov     [rsp-28h+arg_8], rbx
0x18005ae95  push    rbp
0x18005ae96  push    rsi
0x18005ae97  push    rdi
0x18005ae98  push    r12
0x18005ae9a  push    r15
0x18005ae9c  mov     rbp, rsp
0x18005ae9f  sub     rsp, 60h
0x18005aea3  mov     r12, rdx
0x18005aea6  mov     [rbp+arg_0], 0
0x18005aeae  mov     rdx, [rcx+60h]; unsigned __int16 *
0x18005aeb2  mov     r15, r8
0x18005aeb5  xorps   xmm0, xmm0
0x18005aeb8  mov     [rbp+var_20], 0
0x18005aec0  add     rcx, 0F8h; Uuid
0x18005aec7  mov     [rbp+SourceString], 0
0x18005aecf  mov     r9b, 1; bool
0x18005aed2  mov     [rsp+60h+var_40], 0; bool
0x18005aed7  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18005aedb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005aedf  call    ?GetLSASecretName@@YAJPEBU_GUID@@PEBGPEAPEAG_N3@Z; GetLSASecretName(_GUID const *,ushort const *,ushort * *,bool,bool)
0x18005aee4  mov     ebx, eax
0x18005aee6  test    eax, eax
0x18005aee8  jz      short loc_18005AF1E
0x18005aeea  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005aef1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005aef6  mov     r9, rax
0x18005aef9  lea     rax, Class
0x18005af00  mov     [rsp+60h+var_30], rax
0x18005af05  lea     rax, aGetlsasecretna_0; "GetLSASecretName for TGT"
0x18005af0c  mov     [rsp+60h+var_38], rax
0x18005af11  mov     dword ptr [rsp+60h+var_40], 241h
0x18005af19  jmp     loc_18005B088
0x18005af1e  mov     rdx, [rbp+SourceString]; SourceString
0x18005af22  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005af26  call    cs:__imp_RtlInitUnicodeString
0x18005af2c  mov     rcx, cs:?g_LsaPolicyHandle@@3PEAXEA; void * g_LsaPolicyHandle
0x18005af33  lea     r9, [rbp+var_20]
0x18005af37  mov     r8d, 0F0003h
0x18005af3d  lea     rdx, [rbp+DestinationString]
0x18005af41  call    cs:__imp_LsarOpenSecret
0x18005af47  mov     ebx, eax
0x18005af49  test    eax, eax
0x18005af4b  jz      short loc_18005AF81
0x18005af4d  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005af54  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005af59  mov     r9, rax
0x18005af5c  lea     rax, Class
0x18005af63  mov     [rsp+60h+var_30], rax
0x18005af68  lea     rax, aLsaropensecret; "LsarOpenSecret TGT"
0x18005af6f  mov     [rsp+60h+var_38], rax
0x18005af74  mov     dword ptr [rsp+60h+var_40], 24Ah
0x18005af7c  jmp     loc_18005B088
0x18005af81  mov     rcx, [rbp+var_20]
0x18005af85  lea     rdx, [rbp+arg_0]
0x18005af89  xor     r9d, r9d
0x18005af8c  mov     qword ptr [rsp+60h+var_40], 0
0x18005af95  xor     r8d, r8d
0x18005af98  call    cs:__imp_LsarQuerySecret
0x18005af9e  mov     ebx, eax
0x18005afa0  test    eax, eax
0x18005afa2  jz      short loc_18005AFD8
0x18005afa4  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005afab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005afb0  mov     r9, rax
0x18005afb3  lea     rax, Class
0x18005afba  mov     [rsp+60h+var_30], rax
0x18005afbf  lea     rax, aLsarquerysecre_0; "LsarQuerySecret TGT"
0x18005afc6  mov     [rsp+60h+var_38], rax
0x18005afcb  mov     dword ptr [rsp+60h+var_40], 251h
0x18005afd3  jmp     loc_18005B088
0x18005afd8  mov     rax, [rbp+arg_0]
0x18005afdc  test    rax, rax
0x18005afdf  jz      short loc_18005B054
0x18005afe1  mov     rsi, [rax+8]
0x18005afe5  test    rsi, rsi
0x18005afe8  jz      short loc_18005B054
0x18005afea  mov     edi, [rax]
0x18005afec  test    edi, edi
0x18005afee  jz      short loc_18005B054
0x18005aff0  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005aff7  mov     ecx, edi
0x18005aff9  mov     rax, [rax+28h]
0x18005affd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b002  mov     [r12], rax
0x18005b006  test    rax, rax
0x18005b009  jnz     short loc_18005B041
0x18005b00b  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b012  mov     ebx, 0C0000017h
0x18005b017  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b01c  mov     r9, rax
0x18005b01f  lea     rax, Class
0x18005b026  mov     [rsp+60h+var_30], rax
0x18005b02b  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18005b032  mov     [rsp+60h+var_38], rax
0x18005b037  mov     dword ptr [rsp+60h+var_40], 262h
0x18005b03f  jmp     short loc_18005B088
0x18005b041  mov     r8, rdi; Size
0x18005b044  mov     rdx, rsi; Src
0x18005b047  mov     rcx, rax; void *
0x18005b04a  call    memcpy_0
0x18005b04f  mov     [r15], edi
0x18005b052  jmp     short loc_18005B099
0x18005b054  lea     rcx, aOnecoreDsExtCl_8; "onecore\\ds\\ext\\cloudap\\dll\\tbal.cp"...
0x18005b05b  mov     ebx, 0C0000371h
0x18005b060  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18005b065  mov     r9, rax
0x18005b068  lea     rax, Class
0x18005b06f  mov     [rsp+60h+var_30], rax
0x18005b074  lea     rax, aNoTbalTgtSecre; "No TBAL TGT Secret"
0x18005b07b  mov     [rsp+60h+var_38], rax
0x18005b080  mov     dword ptr [rsp+60h+var_40], 258h
0x18005b088  mov     r8d, ebx
0x18005b08b  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18005b092  xor     ecx, ecx
0x18005b094  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18005b099  mov     rcx, [rbp+arg_0]
0x18005b09d  test    rcx, rcx
0x18005b0a0  jz      short loc_18005B0C8
0x18005b0a2  mov     rax, [rcx+8]
0x18005b0a6  test    rax, rax
0x18005b0a9  jz      short loc_18005B0C2
0x18005b0ab  mov     edx, [rcx]
0x18005b0ad  test    rdx, rdx
0x18005b0b0  jz      short loc_18005B0C2
0x18005b0b2  mov     byte ptr [rax], 0
0x18005b0b5  inc     rax
0x18005b0b8  sub     rdx, 1
0x18005b0bc  jnz     short loc_18005B0B2
0x18005b0be  mov     rcx, [rbp+arg_0]
0x18005b0c2  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x18005b0c8  cmp     [rbp+SourceString], 0
0x18005b0cd  jz      short loc_18005B0E3
0x18005b0cf  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18005b0d6  mov     rcx, [rbp+SourceString]
0x18005b0da  mov     rax, [rax+30h]
0x18005b0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0e3  cmp     [rbp+var_20], 0
0x18005b0e8  jz      short loc_18005B0F4
0x18005b0ea  lea     rcx, [rbp+var_20]
0x18005b0ee  call    cs:__imp_LsarClose
0x18005b0f4  mov     eax, ebx
0x18005b0f6  mov     rbx, [rsp+60h+arg_8]
0x18005b0fe  add     rsp, 60h
0x18005b102  pop     r15
0x18005b104  pop     r12
0x18005b106  pop     rdi
0x18005b107  pop     rsi
0x18005b108  pop     rbp
0x18005b109  retn
```
