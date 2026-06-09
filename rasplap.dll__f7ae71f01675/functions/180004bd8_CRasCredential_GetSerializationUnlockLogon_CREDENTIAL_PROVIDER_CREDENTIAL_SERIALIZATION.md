# CRasCredential::_GetSerializationUnlockLogon(_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)

- ea: `0x180004bd8`
- end: `0x180004d62`
- name: `?_GetSerializationUnlockLogon@CRasCredential@@AEAAJPEAU_CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(CRasCredential *__hidden this, struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180003fa0`

## callees

- `0x180004bd8`
- `0x180004e74`
- `0x180004f5c`
- `0x180005068`
- `0x180005244`
- `0x1800067dc`
- `0x18000b0ce`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004c95`
- `KERNEL32!LocalFree` at `0x180004ca4`
- `KERNEL32!LocalFree` at `0x180004c95`
- `KERNEL32!LocalFree` at `0x180004ca4`
- `ole32!CoTaskMemFree` at `0x180004d57`
- `ole32!CoTaskMemFree` at `0x180004d57`

## pseudocode

```c
__int64 __fastcall CRasCredential::_GetSerializationUnlockLogon(
        CRasCredential *this,
        struct _CREDENTIAL_PROVIDER_CREDENTIAL_SERIALIZATION *a2)
{
  int v3; // eax
  CRasCredential *v5; // rcx
  int v6; // esi
  unsigned __int8 *v7; // rax
  PWSTR Buffer; // rcx
  __int64 Length; // rax
  PWSTR v10; // rdx
  CRasCredential *v12; // rcx
  unsigned __int8 *v13; // rax
  PWSTR v14; // rcx
  __int64 v15; // rax
  PWSTR v16; // rdx
  struct _KERB_CERTIFICATE_LOGON v17; // [rsp+20h] [rbp-50h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+10h] BYREF
  unsigned __int8 *v19; // [rsp+90h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 534);
  if ( *((_DWORD *)this + 138) == 1 )
  {
    if ( v3 )
    {
LABEL_3:
      memset_0(&v17, 0, sizeof(v17));
      v6 = CRasCredential::_KerbInteractiveSCLogonFill(this, &v17);
      if ( v6 >= 0 )
      {
        v18 = 0;
        v19 = 0;
        v6 = CRasCredential::_KerbInteractiveSCLogonPack(v5, &v17, &v19, &v18);
        if ( v6 >= 0 )
        {
          GetNegoAuthPackageId(a2);
          a2->cbSerialization = v18;
          v7 = v19;
          a2->clsidCredentialProvider = CLSID_RASProvider;
          a2->rgbSerialization = v7;
        }
        Buffer = v17.Pin.Buffer;
        if ( v17.Pin.Buffer )
        {
          Length = v17.Pin.Length;
          v10 = v17.Pin.Buffer;
          if ( v17.Pin.Length )
          {
            do
            {
              *(_BYTE *)v10 = 0;
              v10 = (PWSTR)((char *)v10 + 1);
              --Length;
            }
            while ( Length );
          }
          LocalFree(Buffer);
        }
        if ( v17.CspData )
          LocalFree(v17.CspData);
      }
      return (unsigned int)v6;
    }
  }
  else if ( !v3 )
  {
    goto LABEL_3;
  }
  memset(&v17, 0, 56);
  v6 = CRasCredential::_KerbInteractivePwdLogonFill(this, (struct _KERB_INTERACTIVE_LOGON *)&v17);
  if ( v6 >= 0 )
  {
    v18 = 0;
    v19 = 0;
    v6 = CRasCredential::_KerbInteractivePwdLogonPack(v12, (const struct _KERB_INTERACTIVE_LOGON *)&v17, &v19, &v18);
    if ( v6 >= 0 )
    {
      GetNegoAuthPackageId(a2);
      a2->cbSerialization = v18;
      v13 = v19;
      a2->clsidCredentialProvider = CLSID_RASProvider;
      a2->rgbSerialization = v13;
    }
    v14 = v17.Pin.Buffer;
    if ( v17.Pin.Buffer )
    {
      v15 = v17.Pin.Length;
      v16 = v17.Pin.Buffer;
      if ( v17.Pin.Length )
      {
        do
        {
          *(_BYTE *)v16 = 0;
          v16 = (PWSTR)((char *)v16 + 1);
          --v15;
        }
        while ( v15 );
      }
      CoTaskMemFree(v14);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004bd8  mov     [rsp-8+arg_8], rsi
0x180004bdd  mov     [rsp-8+arg_18], rdi
0x180004be2  push    rbp
0x180004be3  mov     rbp, rsp
0x180004be6  sub     rsp, 70h
0x180004bea  cmp     dword ptr [rcx+228h], 1
0x180004bf1  mov     rdi, rdx
0x180004bf4  mov     eax, [rcx+858h]
0x180004bfa  mov     rsi, rcx
0x180004bfd  jz      loc_180004CBE
0x180004c03  test    eax, eax
0x180004c05  jnz     loc_180004CC6
0x180004c0b  xor     edx, edx; Val
0x180004c0d  lea     rcx, [rbp+var_50]; void *
0x180004c11  lea     r8d, [rdx+48h]; Size
0x180004c15  call    memset_0
0x180004c1a  lea     rdx, [rbp+var_50]; struct _KERB_CERTIFICATE_LOGON *
0x180004c1e  mov     rcx, rsi; this
0x180004c21  call    ?_KerbInteractiveSCLogonFill@CRasCredential@@AEAAJPEAU_KERB_CERTIFICATE_LOGON@@@Z; CRasCredential::_KerbInteractiveSCLogonFill(_KERB_CERTIFICATE_LOGON *)
0x180004c26  mov     esi, eax
0x180004c28  test    eax, eax
0x180004c2a  js      short loc_180004CAA
0x180004c2c  lea     r9, [rbp+arg_0]; unsigned int *
0x180004c30  mov     [rbp+arg_0], 0
0x180004c37  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x180004c3b  mov     [rbp+arg_10], 0
0x180004c43  lea     rdx, [rbp+var_50]; struct _KERB_CERTIFICATE_LOGON *
0x180004c47  call    ?_KerbInteractiveSCLogonPack@CRasCredential@@AEAAJAEBU_KERB_CERTIFICATE_LOGON@@PEAPEAEPEAK@Z; CRasCredential::_KerbInteractiveSCLogonPack(_KERB_CERTIFICATE_LOGON const &,uchar * *,ulong *)
0x180004c4c  mov     esi, eax
0x180004c4e  test    eax, eax
0x180004c50  js      short loc_180004C74
0x180004c52  mov     rcx, rdi
0x180004c55  call    GetNegoAuthPackageId
0x180004c5a  movups  xmm0, xmmword ptr cs:CLSID_RASProvider.Data1
0x180004c61  mov     eax, [rbp+arg_0]
0x180004c64  mov     [rdi+14h], eax
0x180004c67  mov     rax, [rbp+arg_10]
0x180004c6b  movdqu  xmmword ptr [rdi+4], xmm0
0x180004c70  mov     [rdi+18h], rax
0x180004c74  mov     rcx, [rbp+var_50.Password.Buffer]; hMem
0x180004c78  test    rcx, rcx
0x180004c7b  jz      short loc_180004C9B
0x180004c7d  movzx   eax, [rbp+var_50.Password.Length]
0x180004c81  mov     rdx, rcx
0x180004c84  test    rax, rax
0x180004c87  jz      short loc_180004C95
0x180004c89  mov     byte ptr [rdx], 0
0x180004c8c  inc     rdx
0x180004c8f  sub     rax, 1
0x180004c93  jnz     short loc_180004C89
0x180004c95  call    cs:__imp_LocalFree
0x180004c9b  mov     rcx, [rbp+var_10]; hMem
0x180004c9f  test    rcx, rcx
0x180004ca2  jz      short loc_180004CAA
0x180004ca4  call    cs:__imp_LocalFree
0x180004caa  lea     r11, [rsp+70h+var_s0]
0x180004caf  mov     eax, esi
0x180004cb1  mov     rsi, [r11+18h]
0x180004cb5  mov     rdi, [r11+28h]
0x180004cb9  mov     rsp, r11
0x180004cbc  pop     rbp
0x180004cbd  retn
0x180004cbe  test    eax, eax
0x180004cc0  jnz     loc_180004C0B
0x180004cc6  xorps   xmm0, xmm0
0x180004cc9  lea     rdx, [rbp+var_50]; struct _KERB_INTERACTIVE_LOGON *
0x180004ccd  xor     eax, eax
0x180004ccf  movups  xmmword ptr [rbp+var_50.MessageType], xmm0
0x180004cd3  mov     [rbp+var_50.Password.Buffer], rax
0x180004cd7  movups  xmmword ptr [rbp+var_50.LogonDomainName.Buffer], xmm0
0x180004cdb  movups  xmmword ptr [rbp-30h], xmm0
0x180004cdf  call    ?_KerbInteractivePwdLogonFill@CRasCredential@@AEAAJPEAU_KERB_INTERACTIVE_LOGON@@@Z; CRasCredential::_KerbInteractivePwdLogonFill(_KERB_INTERACTIVE_LOGON *)
0x180004ce4  mov     esi, eax
0x180004ce6  test    eax, eax
0x180004ce8  js      short loc_180004CAA
0x180004cea  lea     r9, [rbp+arg_0]; unsigned int *
0x180004cee  mov     [rbp+arg_0], 0
0x180004cf5  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x180004cf9  mov     [rbp+arg_10], 0
0x180004d01  lea     rdx, [rbp+var_50]; struct _KERB_INTERACTIVE_LOGON *
0x180004d05  call    ?_KerbInteractivePwdLogonPack@CRasCredential@@AEAAJAEBU_KERB_INTERACTIVE_LOGON@@PEAPEAEPEAK@Z; CRasCredential::_KerbInteractivePwdLogonPack(_KERB_INTERACTIVE_LOGON const &,uchar * *,ulong *)
0x180004d0a  mov     esi, eax
0x180004d0c  test    eax, eax
0x180004d0e  js      short loc_180004D32
0x180004d10  mov     rcx, rdi
0x180004d13  call    GetNegoAuthPackageId
0x180004d18  movups  xmm0, xmmword ptr cs:CLSID_RASProvider.Data1
0x180004d1f  mov     eax, [rbp+arg_0]
0x180004d22  mov     [rdi+14h], eax
0x180004d25  mov     rax, [rbp+arg_10]
0x180004d29  movdqu  xmmword ptr [rdi+4], xmm0
0x180004d2e  mov     [rdi+18h], rax
0x180004d32  mov     rcx, [rbp+var_50.Password.Buffer]; pv
0x180004d36  test    rcx, rcx
0x180004d39  jz      loc_180004CAA
0x180004d3f  movzx   eax, [rbp+var_50.Password.Length]
0x180004d43  mov     rdx, rcx
0x180004d46  test    rax, rax
0x180004d49  jz      short loc_180004D57
0x180004d4b  mov     byte ptr [rdx], 0
0x180004d4e  inc     rdx
0x180004d51  sub     rax, 1
0x180004d55  jnz     short loc_180004D4B
0x180004d57  call    cs:__imp_CoTaskMemFree
0x180004d5d  jmp     loc_180004CAA
```
