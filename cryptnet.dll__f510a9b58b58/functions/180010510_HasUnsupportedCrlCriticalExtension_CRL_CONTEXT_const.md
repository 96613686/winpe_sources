# HasUnsupportedCrlCriticalExtension(_CRL_CONTEXT const *)

- ea: `0x180010510`
- end: `0x1800105d7`
- name: `?HasUnsupportedCrlCriticalExtension@@YAHPEBU_CRL_CONTEXT@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(const struct _CRL_CONTEXT *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f140`
- `0x1800105e0`

## callees

- `0x180010510`

## import_xrefs

- `CRYPT32!I_CertDiagControl` at `0x1800105b8`
- `CRYPT32!I_CertDiagControl` at `0x1800105b8`

## string_xrefs

- `0x180010591`: `IsCrlCriticalExtensionSupported`

## pseudocode

```c
__int64 __fastcall HasUnsupportedCrlCriticalExtension(const struct _CRL_CONTEXT *a1)
{
  PCRL_INFO pCrlInfo; // rax
  DWORD cExtension; // ebx
  PCERT_EXTENSION i; // r11
  const char * near **j; // r9
  unsigned __int8 *pszObjId; // rax
  int v7; // ecx
  int v8; // edx
  _QWORD v10[3]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  pCrlInfo = a1->pCrlInfo;
  cExtension = pCrlInfo->cExtension;
  for ( i = pCrlInfo->rgExtension; ; ++i )
  {
    if ( !cExtension )
      return 0;
    if ( i->fCritical )
      break;
LABEL_11:
    --cExtension;
  }
  for ( j = &rgpszSupportedCrlExtensionOID; *j; ++j )
  {
    pszObjId = (unsigned __int8 *)i->pszObjId;
    do
    {
      v7 = pszObjId[(char *)*j - i->pszObjId];
      v8 = *pszObjId - v7;
      if ( v8 )
        break;
      ++pszObjId;
    }
    while ( v7 );
    if ( !v8 )
      goto LABEL_11;
  }
  v10[0] = a1;
  v10[2] = 0;
  v12 = 0;
  v10[1] = L"IsCrlCriticalExtensionSupported";
  v11 = 0;
  I_CertDiagControl(5, v10, 0);
  return 1;
}

```

## disassembly

```asm
0x180010510  mov     [rsp+arg_0], rbx
0x180010515  mov     [rsp+arg_8], rsi
0x18001051a  push    rdi
0x18001051b  sub     rsp, 50h
0x18001051f  mov     rax, [rcx+18h]
0x180010523  lea     rsi, ?rgpszSupportedCrlExtensionOID@@3PAPEBDA; char const * near * rgpszSupportedCrlExtensionOID
0x18001052a  mov     rdi, rcx
0x18001052d  mov     ebx, [rax+50h]
0x180010530  mov     r11, [rax+58h]
0x180010534  test    ebx, ebx
0x180010536  jz      loc_1800105C5
0x18001053c  cmp     dword ptr [r11+8], 0
0x180010541  jz      short loc_18001057D
0x180010543  mov     r10, [r11]
0x180010546  mov     r9, rsi
0x180010549  nop     dword ptr [rax+00000000h]
0x180010550  mov     r8, [r9]
0x180010553  test    r8, r8
0x180010556  jz      short loc_180010585
0x180010558  mov     rax, r10
0x18001055b  sub     r8, r10
0x18001055e  xchg    ax, ax
0x180010560  movzx   edx, byte ptr [rax]
0x180010563  movzx   ecx, byte ptr [rax+r8]
0x180010568  sub     edx, ecx
0x18001056a  jnz     short loc_180010573
0x18001056c  inc     rax
0x18001056f  test    ecx, ecx
0x180010571  jnz     short loc_180010560
0x180010573  test    edx, edx
0x180010575  jz      short loc_18001057D
0x180010577  add     r9, 8
0x18001057b  jmp     short loc_180010550
0x18001057d  dec     ebx
0x18001057f  add     r11, 20h ; ' '
0x180010583  jmp     short loc_180010534
0x180010585  xor     ecx, ecx
0x180010587  mov     [rsp+58h+var_38], rdi
0x18001058c  mov     [rsp+58h+var_28], rcx
0x180010591  lea     rax, aIscrlcriticale; "IsCrlCriticalExtensionSupported"
0x180010598  mov     [rsp+58h+var_10], rcx
0x18001059d  lea     rdx, [rsp+58h+var_38]
0x1800105a2  xorps   xmm0, xmm0
0x1800105a5  mov     [rsp+58h+var_30], rax
0x1800105aa  mov     ecx, 5
0x1800105af  xor     r8d, r8d
0x1800105b2  movdqu  [rsp+58h+var_20], xmm0
0x1800105b8  call    cs:__imp_I_CertDiagControl
0x1800105be  mov     eax, 1
0x1800105c3  jmp     short loc_1800105C7
0x1800105c5  xor     eax, eax
0x1800105c7  mov     rbx, [rsp+58h+arg_0]
0x1800105cc  mov     rsi, [rsp+58h+arg_8]
0x1800105d1  add     rsp, 50h
0x1800105d5  pop     rdi
0x1800105d6  retn
```
