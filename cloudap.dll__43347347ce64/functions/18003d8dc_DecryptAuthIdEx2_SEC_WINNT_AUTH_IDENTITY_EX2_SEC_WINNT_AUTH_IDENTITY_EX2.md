# DecryptAuthIdEx2(_SEC_WINNT_AUTH_IDENTITY_EX2 *,_SEC_WINNT_AUTH_IDENTITY_EX2 * *)

- ea: `0x18003d8dc`
- end: `0x18003da1e`
- name: `?DecryptAuthIdEx2@@YAJPEAU_SEC_WINNT_AUTH_IDENTITY_EX2@@PEAPEAU1@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct _SEC_WINNT_AUTH_IDENTITY_EX2 *, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180026ec0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003d8dc`

## import_xrefs

- `SspiCli!SspiCopyAuthIdentity` at `0x18003d905`
- `SspiCli!SspiCopyAuthIdentity` at `0x18003d905`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18003d956`
- `SspiCli!SspiIsAuthIdentityEncrypted` at `0x18003d956`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18003d973`
- `SspiCli!SspiDecryptAuthIdentityEx` at `0x18003d973`
- `SspiCli!SspiFreeAuthIdentity` at `0x18003da06`
- `SspiCli!SspiFreeAuthIdentity` at `0x18003da06`

## string_xrefs

- `0x18003d918`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003d982`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003d9b2`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x18003d93c`: `SspiCopyAuthIdentity`

## pseudocode

```c
__int64 __fastcall DecryptAuthIdEx2(struct _SEC_WINNT_AUTH_IDENTITY_EX2 *a1, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *a2)
{
  unsigned int v4; // ebx
  const char *v5; // rax
  const char *v6; // rdx
  __int64 v7; // r11
  const char *v8; // r10
  const char *v9; // r8
  int v10; // edx
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE EncryptedAuthData; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  EncryptedAuthData = 0;
  v4 = SspiCopyAuthIdentity(a1, &EncryptedAuthData);
  if ( v4 )
  {
    v5 = "";
    do
      v6 = v5--;
    while ( *v5 != 92 && v5 > "onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp" );
    v7 = 0;
    v8 = "0x%08x %s:%u : %s:%ws";
    v9 = "SspiCopyAuthIdentity";
    if ( *v5 == 92 )
      v5 = v6;
    v10 = 404;
  }
  else if ( SspiIsAuthIdentityEncrypted(EncryptedAuthData) )
  {
    v4 = SspiDecryptAuthIdentityEx((a1->Flags & 0x80u) != 0 ? 4 : 1, EncryptedAuthData);
    if ( !v4 )
    {
      v4 = 0;
      *a2 = EncryptedAuthData;
      return v4;
    }
    v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v10 = 413;
    v9 = "SspiDecryptAuthIdentityEx";
  }
  else
  {
    v4 = -1073741811;
    v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v10 = 418;
    v9 = "EX2 buffer should have been encrypted";
  }
  WPPTraceLogA(v7, v8, v4, v5, v10, v9, &Class);
  if ( EncryptedAuthData )
    SspiFreeAuthIdentity(EncryptedAuthData);
  return v4;
}

```

## disassembly

```asm
0x18003d8dc  mov     rax, rsp
0x18003d8df  mov     [rax+8], rbx
0x18003d8e3  mov     [rax+18h], rsi
0x18003d8e7  push    rdi
0x18003d8e8  sub     rsp, 40h
0x18003d8ec  mov     rdi, rdx
0x18003d8ef  mov     qword ptr [rdx], 0
0x18003d8f6  lea     rdx, [rax+10h]; AuthDataCopy
0x18003d8fa  mov     qword ptr [rax+10h], 0
0x18003d902  mov     rsi, rcx
0x18003d905  call    cs:__imp_SspiCopyAuthIdentity
0x18003d90b  mov     ebx, eax
0x18003d90d  test    eax, eax
0x18003d90f  jz      short loc_18003D951
0x18003d911  lea     rax, aOnecoreDsExtCl_6+27h; ""
0x18003d918  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003d91f  mov     rdx, rax
0x18003d922  dec     rax
0x18003d925  cmp     byte ptr [rax], 5Ch ; '\'
0x18003d928  jz      short loc_18003D92F
0x18003d92a  cmp     rax, rcx
0x18003d92d  ja      short loc_18003D91F
0x18003d92f  xor     r11d, r11d
0x18003d932  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003d939  cmp     byte ptr [rax], 5Ch ; '\'
0x18003d93c  lea     r8, aSspicopyauthid; "SspiCopyAuthIdentity"
0x18003d943  cmovz   rax, rdx
0x18003d947  mov     edx, 194h
0x18003d94c  jmp     loc_18003D9D6
0x18003d951  mov     rcx, [rsp+48h+EncryptedAuthData]; EncryptedAuthData
0x18003d956  call    cs:__imp_SspiIsAuthIdentityEncrypted
0x18003d95c  test    al, al
0x18003d95e  jz      short loc_18003D9AF
0x18003d960  mov     eax, [rsi+24h]
0x18003d963  mov     rdx, [rsp+48h+EncryptedAuthData]; EncryptedAuthData
0x18003d968  and     al, 80h
0x18003d96a  neg     al
0x18003d96c  sbb     ecx, ecx
0x18003d96e  and     ecx, 3
0x18003d971  inc     ecx; Options
0x18003d973  call    cs:__imp_SspiDecryptAuthIdentityEx
0x18003d979  mov     ebx, eax
0x18003d97b  test    eax, eax
0x18003d97d  jz      short loc_18003D9A3
0x18003d97f  xor     r11d, r11d
0x18003d982  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003d989  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003d990  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003d995  mov     edx, 19Dh
0x18003d99a  lea     r8, aSspidecryptaut; "SspiDecryptAuthIdentityEx"
0x18003d9a1  jmp     short loc_18003D9D6
0x18003d9a3  mov     rax, [rsp+48h+EncryptedAuthData]
0x18003d9a8  xor     ebx, ebx
0x18003d9aa  mov     [rdi], rax
0x18003d9ad  jmp     short loc_18003DA0C
0x18003d9af  xor     r11d, r11d
0x18003d9b2  lea     rcx, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x18003d9b9  mov     ebx, 0C000000Dh
0x18003d9be  lea     r10, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003d9c5  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003d9ca  mov     edx, 1A2h
0x18003d9cf  lea     r8, aEx2BufferShoul; "EX2 buffer should have been encrypted"
0x18003d9d6  lea     rcx, Class
0x18003d9dd  mov     [rsp+48h+var_18], rcx
0x18003d9e2  mov     r9, rax
0x18003d9e5  mov     [rsp+48h+var_20], r8
0x18003d9ea  mov     rcx, r11
0x18003d9ed  mov     [rsp+48h+var_28], edx
0x18003d9f1  mov     r8d, ebx
0x18003d9f4  mov     rdx, r10
0x18003d9f7  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003d9fc  mov     rcx, [rsp+48h+EncryptedAuthData]; AuthData
0x18003da01  test    rcx, rcx
0x18003da04  jz      short loc_18003DA0C
0x18003da06  call    cs:__imp_SspiFreeAuthIdentity
0x18003da0c  mov     rsi, [rsp+48h+arg_10]
0x18003da11  mov     eax, ebx
0x18003da13  mov     rbx, [rsp+48h+arg_0]
0x18003da18  add     rsp, 40h
0x18003da1c  pop     rdi
0x18003da1d  retn
```
