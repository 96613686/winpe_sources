# MsvpGetTbalPrimaryCredentialsFromSecret(_MSV1_0_PRIMARY_CREDENTIAL * *,ulong *)

- ea: `0x180055abc`
- end: `0x180055c67`
- name: `?MsvpGetTbalPrimaryCredentialsFromSecret@@YAJPEAPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAK@Z`
- size: `427`
- prototype: `int(struct _MSV1_0_PRIMARY_CREDENTIAL **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180021ce4`

## callees

- `0x18002ead4`
- `0x18002ee7c`
- `0x180055abc`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180055aff`
- `ntdll!RtlInitUnicodeString` at `0x180055aff`
- `LSASRV!LsarDeleteObject` at `0x180055bf4`
- `LSASRV!LsarDeleteObject` at `0x180055bf4`
- `LSASRV!LsarClose` at `0x180055b97`
- `LSASRV!LsarClose` at `0x180055b97`
- `LSASRV!LsarQuerySecret` at `0x180055bc5`
- `LSASRV!LsarQuerySecret` at `0x180055bc5`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180055b86`
- `LSASRV!LsaIFree_LSAPR_CR_CIPHER_VALUE` at `0x180055b86`
- `LSASRV!LsarOpenSecret` at `0x180055b18`
- `LSASRV!LsarOpenSecret` at `0x180055b18`

## pseudocode

```c
__int64 __fastcall MsvpGetTbalPrimaryCredentialsFromSecret(struct _MSV1_0_PRIMARY_CREDENTIAL **a1, unsigned int *a2)
{
  struct _MSV1_0_PRIMARY_CREDENTIAL *v4; // rdi
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rcx
  _BYTE *v8; // rax
  _BYTE *v9; // rcx
  __int64 v10; // rdx
  struct _MSV1_0_PRIMARY_CREDENTIAL *v12; // rcx
  struct NtlmCredIsoApi *v13; // rax
  struct _MSV1_0_PRIMARY_CREDENTIAL *v14; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  unsigned int *v16; // [rsp+80h] [rbp+30h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v4 = 0;
  DestinationString = 0;
  v14 = 0;
  RtlInitUnicodeString(&DestinationString, L"M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4A87-BA71-41B0ECF3A9EA}");
  v5 = LsarOpenSecret(NtLmGlobalPolicyHandle, &DestinationString, 3, &v17);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -1073741772 )
      goto LABEL_4;
    goto LABEL_3;
  }
  v6 = LsarQuerySecret(v17, &v16, 0, 0, 0);
  if ( v6 < 0 )
    goto LABEL_8;
  if ( !v16 || !*((_QWORD *)v16 + 1) || !*v16 )
  {
LABEL_3:
    v6 = -1073740943;
    goto LABEL_4;
  }
  LsarDeleteObject(&v17);
  v6 = MspDeserializeTbalCredential(*((unsigned __int8 **)v16 + 1), *v16, &v14, a2);
  if ( v6 >= 0 )
  {
    v12 = v14;
    v13 = LocalhostNtLmCredIsoObj::IsoObj;
    *a1 = v14;
    *((_QWORD *)v12 + 4) = v13;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids, (unsigned int)v6);
  v4 = v14;
LABEL_4:
  if ( v4 )
  {
    v7 = 352;
    v8 = (char *)v4 + 32;
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
    ((void (__fastcall *)(struct _MSV1_0_PRIMARY_CREDENTIAL *))qword_180088240)(v4);
  }
LABEL_8:
  if ( v16 )
  {
    v9 = (_BYTE *)*((_QWORD *)v16 + 1);
    if ( v9 )
    {
      v10 = *v16;
      if ( *v16 )
      {
        do
        {
          *v9++ = 0;
          --v10;
        }
        while ( v10 );
      }
    }
    LsaIFree_LSAPR_CR_CIPHER_VALUE(v16);
  }
  if ( v17 )
    LsarClose(&v17);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180055abc  mov     [rsp-18h+arg_0], rbx
0x180055ac1  mov     [rsp-18h+arg_8], rsi
0x180055ac6  push    rbp
0x180055ac7  push    rdi
0x180055ac8  push    r14
0x180055aca  mov     rbp, rsp
0x180055acd  sub     rsp, 50h
0x180055ad1  mov     r14, rdx
0x180055ad4  mov     [rbp+arg_18], 0
0x180055adc  mov     rsi, rcx
0x180055adf  mov     [rbp+arg_10], 0
0x180055ae7  xorps   xmm0, xmm0
0x180055aea  lea     rdx, aMMsv10TbalPrim; "M$_MSV1_0_TBAL_PRIMARY_{22BE8E5B-58B3-4"...
0x180055af1  xor     edi, edi
0x180055af3  lea     rcx, [rbp+DestinationString]; DestinationString
0x180055af7  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180055afb  mov     [rbp+var_20], rdi
0x180055aff  call    cs:__imp_RtlInitUnicodeString
0x180055b05  mov     rcx, cs:NtLmGlobalPolicyHandle
0x180055b0c  lea     r9, [rbp+arg_18]
0x180055b10  lea     r8d, [rdi+3]
0x180055b14  lea     rdx, [rbp+DestinationString]
0x180055b18  call    cs:__imp_LsarOpenSecret
0x180055b1e  mov     ebx, eax
0x180055b20  test    eax, eax
0x180055b22  jns     loc_180055BB2
0x180055b28  cmp     eax, 0C0000034h
0x180055b2d  jnz     short loc_180055B34
0x180055b2f  mov     ebx, 0C0000371h
0x180055b34  test    rdi, rdi
0x180055b37  jz      short loc_180055B5D
0x180055b39  mov     ecx, 160h
0x180055b3e  lea     rax, [rdi+20h]
0x180055b42  mov     byte ptr [rax], 0
0x180055b45  inc     rax
0x180055b48  sub     rcx, 1
0x180055b4c  jnz     short loc_180055B42
0x180055b4e  mov     rax, cs:qword_180088240
0x180055b55  mov     rcx, rdi
0x180055b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b5d  mov     rax, [rbp+arg_10]
0x180055b61  test    rax, rax
0x180055b64  jz      short loc_180055B8C
0x180055b66  mov     rcx, [rax+8]
0x180055b6a  test    rcx, rcx
0x180055b6d  jz      short loc_180055B82
0x180055b6f  mov     edx, [rax]
0x180055b71  test    rdx, rdx
0x180055b74  jz      short loc_180055B82
0x180055b76  mov     byte ptr [rcx], 0
0x180055b79  inc     rcx
0x180055b7c  sub     rdx, 1
0x180055b80  jnz     short loc_180055B76
0x180055b82  mov     rcx, [rbp+arg_10]
0x180055b86  call    cs:__imp_LsaIFree_LSAPR_CR_CIPHER_VALUE
0x180055b8c  cmp     [rbp+arg_18], 0
0x180055b91  jz      short loc_180055B9D
0x180055b93  lea     rcx, [rbp+arg_18]
0x180055b97  call    cs:__imp_LsarClose
0x180055b9d  mov     rsi, [rsp+50h+arg_8]
0x180055ba2  mov     eax, ebx
0x180055ba4  mov     rbx, [rsp+50h+arg_0]
0x180055ba9  add     rsp, 50h
0x180055bad  pop     r14
0x180055baf  pop     rdi
0x180055bb0  pop     rbp
0x180055bb1  retn
0x180055bb2  mov     rcx, [rbp+arg_18]
0x180055bb6  lea     rdx, [rbp+arg_10]
0x180055bba  xor     r9d, r9d
0x180055bbd  mov     [rsp+50h+var_30], rdi
0x180055bc2  xor     r8d, r8d
0x180055bc5  call    cs:__imp_LsarQuerySecret
0x180055bcb  mov     ebx, eax
0x180055bcd  test    eax, eax
0x180055bcf  js      short loc_180055B5D
0x180055bd1  mov     rax, [rbp+arg_10]
0x180055bd5  test    rax, rax
0x180055bd8  jz      loc_180055B2F
0x180055bde  cmp     [rax+8], rdi
0x180055be2  jz      loc_180055B2F
0x180055be8  cmp     [rax], edi
0x180055bea  jz      loc_180055B2F
0x180055bf0  lea     rcx, [rbp+arg_18]
0x180055bf4  call    cs:__imp_LsarDeleteObject
0x180055bfa  mov     rcx, [rbp+arg_10]
0x180055bfe  lea     r8, [rbp+var_20]; struct _MSV1_0_PRIMARY_CREDENTIAL **
0x180055c02  mov     r9, r14; unsigned int *
0x180055c05  mov     edx, [rcx]; unsigned int
0x180055c07  mov     rcx, [rcx+8]; unsigned __int8 *
0x180055c0b  call    ?MspDeserializeTbalCredential@@YAJPEAEKPEAPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAK@Z; MspDeserializeTbalCredential(uchar *,ulong,_MSV1_0_PRIMARY_CREDENTIAL * *,ulong *)
0x180055c10  mov     ebx, eax
0x180055c12  test    eax, eax
0x180055c14  jns     short loc_180055C50
0x180055c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c1d  lea     rax, WPP_GLOBAL_Control
0x180055c24  cmp     rcx, rax
0x180055c27  jz      short loc_180055C47
0x180055c29  test    byte ptr [rcx+1Ch], 1
0x180055c2d  jz      short loc_180055C47
0x180055c2f  mov     rcx, [rcx+10h]
0x180055c33  lea     r8, WPP_a66d676dc5db3a60f54e622a6aecb7e0_Traceguids
0x180055c3a  mov     edx, 0Ah
0x180055c3f  mov     r9d, ebx
0x180055c42  call    WPP_SF_d
0x180055c47  mov     rdi, [rbp+var_20]
0x180055c4b  jmp     loc_180055B34
0x180055c50  mov     rcx, [rbp+var_20]
0x180055c54  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180055c5b  mov     [rsi], rcx
0x180055c5e  mov     [rcx+20h], rax
0x180055c62  jmp     loc_180055B5D
```
