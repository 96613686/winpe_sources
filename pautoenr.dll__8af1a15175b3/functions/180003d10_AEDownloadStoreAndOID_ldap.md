# AEDownloadStoreAndOID(ldap *)

- ea: `0x180003d10`
- end: `0x180003ec4`
- name: `?AEDownloadStoreAndOID@@YAHPEAUldap@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct ldap *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180001d90`

## callees

- `0x180003d10`
- `0x180003ed0`
- `0x180004270`
- `0x180004410`
- `0x1800050b0`
- `0x180006b10`
- `0x180006d58`
- `0x180006ecc`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ea8`
- `RPCRT4!RpcStringFreeW` at `0x180003e9a`
- `RPCRT4!RpcStringFreeW` at `0x180003e9a`

## pseudocode

```c
__int64 __fastcall AEDownloadStoreAndOID(struct ldap *a1)
{
  unsigned int v2; // esi
  __int64 i; // rbp
  unsigned __int16 *v4; // rax
  int v5; // ebx
  RPC_WSTR String[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+40h] [rbp-38h] BYREF

  String[1] = 0;
  String[0] = 0;
  v8 = 0;
  if ( (unsigned int)AEGetConfigDN(a1) )
  {
LABEL_21:
    v2 = 0;
    goto LABEL_22;
  }
  v2 = 1;
  AERetrieveInvocationID(a1, String);
  if ( (unsigned int)AENeedToUpdateDSCache(a1, String[0], 0, 0, (struct _AE_DS_INFO_ *)&v8) )
  {
    for ( i = 0; i != 3; ++i )
    {
      if ( v2 )
      {
        v2 = 1;
        if ( !AEUpdateCertificateStore(
                a1,
                0,
                (unsigned __int16 *)*(&g_rgStoreInfo + 2 * i),
                (unsigned __int16 *)*(&g_rgStoreInfo + 2 * i + 1)) )
          continue;
      }
      v2 = 0;
    }
    if ( v2 && (_DWORD)v8 == 1 )
    {
      v4 = String[0];
      if ( !String[0] )
        goto LABEL_13;
      AEUpdateDSCache(String[0], 0, (const BYTE *)&v8);
    }
  }
  v4 = String[0];
LABEL_13:
  v8 = 0;
  if ( (unsigned int)AENeedToUpdateDSCache(a1, v4, 0, 1, (struct _AE_DS_INFO_ *)&v8)
    || !(unsigned int)I_CryptIsValidDsOIDInfoCache() )
  {
    v5 = AEUpdateDsOIDInfoCache();
    if ( v5 && (_DWORD)v8 == 1 && String[0] )
      AEUpdateDSCache(String[0], 1, (const BYTE *)&v8);
    if ( !v2 )
      goto LABEL_21;
    v2 = 1;
    if ( !v5 )
      goto LABEL_21;
  }
LABEL_22:
  if ( String[0] )
    RpcStringFreeW(String);
  return v2;
}

```

## disassembly

```asm
0x180003d10  mov     r11, rsp
0x180003d13  push    rsi
0x180003d14  push    rdi
0x180003d15  sub     rsp, 68h
0x180003d19  mov     rax, cs:__security_cookie
0x180003d20  xor     rax, rsp
0x180003d23  mov     [rsp+78h+var_28], rax
0x180003d28  mov     [r11+10h], rbx
0x180003d2c  lea     rdx, [r11-40h]
0x180003d30  mov     [r11+20h], r14
0x180003d34  xorps   xmm0, xmm0
0x180003d37  xor     r14d, r14d
0x180003d3a  mov     rbx, rcx
0x180003d3d  mov     [r11-40h], r14
0x180003d41  mov     [r11-48h], r14
0x180003d45  movups  [rsp+78h+var_38], xmm0
0x180003d4a  call    AEGetConfigDN
0x180003d4f  mov     rdi, [rsp+78h+hMem]
0x180003d54  test    eax, eax
0x180003d56  jnz     loc_180003E7A
0x180003d5c  lea     rdx, [rsp+78h+String]; StringUuid
0x180003d61  mov     rcx, rbx; ExternalHandle
0x180003d64  mov     esi, 1
0x180003d69  call    ?AERetrieveInvocationID@@YAHPEAUldap@@PEAPEAG@Z; AERetrieveInvocationID(ldap *,ushort * *)
0x180003d6e  mov     rdx, [rsp+78h+String]; unsigned __int16 *
0x180003d73  lea     rax, [rsp+78h+var_38]
0x180003d78  xor     r9d, r9d; int
0x180003d7b  mov     [rsp+78h+var_58], rax; struct _AE_DS_INFO_ *
0x180003d80  mov     r8, rdi; unsigned __int16 *
0x180003d83  mov     rcx, rbx; ld
0x180003d86  call    ?AENeedToUpdateDSCache@@YAHPEAUldap@@PEAG1HPEAU_AE_DS_INFO_@@@Z; AENeedToUpdateDSCache(ldap *,ushort *,ushort *,int,_AE_DS_INFO_ *)
0x180003d8b  test    eax, eax
0x180003d8d  jz      short loc_180003E0A
0x180003d8f  mov     [rsp+78h+arg_10], rbp
0x180003d97  mov     ebp, r14d
0x180003d9a  mov     [rsp+78h+var_18], r15
0x180003d9f  lea     r15, ?g_rgStoreInfo@@3PAU_AE_STORE_INFO_@@A; _AE_STORE_INFO_ near * g_rgStoreInfo
0x180003da6  test    esi, esi
0x180003da8  jz      short loc_180003DCD
0x180003daa  mov     r8, rbp
0x180003dad  mov     rdx, rdi; unsigned __int16 *
0x180003db0  add     r8, r8
0x180003db3  mov     rcx, rbx; struct ldap *
0x180003db6  mov     r9, [r15+r8*8+8]; unsigned __int16 *
0x180003dbb  mov     r8, [r15+r8*8]; unsigned __int16 *
0x180003dbf  call    ?AEUpdateCertificateStore@@YAJPEAUldap@@PEAG11@Z; AEUpdateCertificateStore(ldap *,ushort *,ushort *,ushort *)
0x180003dc4  mov     esi, 1
0x180003dc9  test    eax, eax
0x180003dcb  jz      short loc_180003DD0
0x180003dcd  mov     esi, r14d
0x180003dd0  inc     rbp
0x180003dd3  cmp     rbp, 3
0x180003dd7  jnz     short loc_180003DA6
0x180003dd9  mov     r15, [rsp+78h+var_18]
0x180003dde  mov     rbp, [rsp+78h+arg_10]
0x180003de6  test    esi, esi
0x180003de8  jz      short loc_180003E0A
0x180003dea  cmp     dword ptr [rsp+78h+var_38], 1
0x180003def  jnz     short loc_180003E0A
0x180003df1  mov     rax, [rsp+78h+String]
0x180003df6  test    rax, rax
0x180003df9  jz      short loc_180003E0F
0x180003dfb  lea     r8, [rsp+78h+var_38]; struct _AE_DS_INFO_ *
0x180003e00  xor     edx, edx; int
0x180003e02  mov     rcx, rax; lpSubKey
0x180003e05  call    ?AEUpdateDSCache@@YAHPEAGHPEAU_AE_DS_INFO_@@@Z; AEUpdateDSCache(ushort *,int,_AE_DS_INFO_ *)
0x180003e0a  mov     rax, [rsp+78h+String]
0x180003e0f  lea     rcx, [rsp+78h+var_38]
0x180003e14  xorps   xmm0, xmm0
0x180003e17  mov     [rsp+78h+var_58], rcx; struct _AE_DS_INFO_ *
0x180003e1c  mov     r9d, 1; int
0x180003e22  mov     rcx, rbx; ld
0x180003e25  mov     r8, rdi; unsigned __int16 *
0x180003e28  mov     rdx, rax; unsigned __int16 *
0x180003e2b  movups  [rsp+78h+var_38], xmm0
0x180003e30  call    ?AENeedToUpdateDSCache@@YAHPEAUldap@@PEAG1HPEAU_AE_DS_INFO_@@@Z; AENeedToUpdateDSCache(ldap *,ushort *,ushort *,int,_AE_DS_INFO_ *)
0x180003e35  test    eax, eax
0x180003e37  jnz     short loc_180003E42
0x180003e39  call    I_CryptIsValidDsOIDInfoCache
0x180003e3e  test    eax, eax
0x180003e40  jnz     short loc_180003E7D
0x180003e42  call    AEUpdateDsOIDInfoCache
0x180003e47  mov     ebx, eax
0x180003e49  test    eax, eax
0x180003e4b  jz      short loc_180003E6D
0x180003e4d  cmp     dword ptr [rsp+78h+var_38], 1
0x180003e52  jnz     short loc_180003E6D
0x180003e54  mov     rcx, [rsp+78h+String]; lpSubKey
0x180003e59  test    rcx, rcx
0x180003e5c  jz      short loc_180003E6D
0x180003e5e  lea     r8, [rsp+78h+var_38]; struct _AE_DS_INFO_ *
0x180003e63  mov     edx, 1; int
0x180003e68  call    ?AEUpdateDSCache@@YAHPEAGHPEAU_AE_DS_INFO_@@@Z; AEUpdateDSCache(ushort *,int,_AE_DS_INFO_ *)
0x180003e6d  test    esi, esi
0x180003e6f  jz      short loc_180003E7A
0x180003e71  mov     esi, 1
0x180003e76  test    ebx, ebx
0x180003e78  jnz     short loc_180003E7D
0x180003e7a  mov     esi, r14d
0x180003e7d  cmp     [rsp+78h+String], 0
0x180003e83  mov     r14, [rsp+78h+arg_18]
0x180003e8b  mov     rbx, [rsp+78h+arg_8]
0x180003e93  jz      short loc_180003EA0
0x180003e95  lea     rcx, [rsp+78h+String]; String
0x180003e9a  call    cs:__imp_RpcStringFreeW
0x180003ea0  test    rdi, rdi
0x180003ea3  jz      short loc_180003EAE
0x180003ea5  mov     rcx, rdi; hMem
0x180003ea8  call    cs:__imp_LocalFree
0x180003eae  mov     eax, esi
0x180003eb0  mov     rcx, [rsp+78h+var_28]
0x180003eb5  xor     rcx, rsp; StackCookie
0x180003eb8  call    __security_check_cookie
0x180003ebd  add     rsp, 68h
0x180003ec1  pop     rdi
0x180003ec2  pop     rsi
0x180003ec3  retn
```
