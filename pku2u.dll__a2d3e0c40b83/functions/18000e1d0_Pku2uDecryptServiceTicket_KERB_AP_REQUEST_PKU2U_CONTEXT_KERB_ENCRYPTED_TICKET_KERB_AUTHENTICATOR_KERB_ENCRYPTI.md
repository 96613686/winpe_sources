# Pku2uDecryptServiceTicket(KERB_AP_REQUEST *,_PKU2U_CONTEXT *,KERB_ENCRYPTED_TICKET * *,KERB_AUTHENTICATOR * *,KERB_ENCRYPTION_KEY *,KERB_ENCRYPTION_KEY *,long *)

- ea: `0x18000e1d0`
- end: `0x18000e8f3`
- name: `?Pku2uDecryptServiceTicket@@YAJPEAUKERB_AP_REQUEST@@PEAU_PKU2U_CONTEXT@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAPEAUKERB_AUTHENTICATOR@@PEAUKERB_ENCRYPTION_KEY@@4PEAJ@Z`
- size: `1827`
- prototype: `int(struct KERB_AP_REQUEST *, struct _PKU2U_CONTEXT *, struct KERB_ENCRYPTED_TICKET **, struct KERB_AUTHENTICATOR **, struct KERB_ENCRYPTION_KEY *, struct KERB_ENCRYPTION_KEY *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x18000d220`

## callees

- `0x180007dc8`
- `0x18000e1d0`
- `0x18000e900`
- `0x180015190`
- `0x180017a60`
- `0x18001a1d0`
- `0x180021a54`
- `0x180023cb8`
- `0x180023ce0`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000e7fa`
- `ntdll!RtlInitUnicodeString` at `0x18000e80b`
- `ntdll!RtlInitUnicodeString` at `0x18000e7fa`
- `ntdll!RtlInitUnicodeString` at `0x18000e80b`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e2ab`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e6ef`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e2ab`
- `ntdll!RtlLeaveCriticalSection` at `0x18000e6ef`
- `ntdll!RtlEnterCriticalSection` at `0x18000e276`
- `ntdll!RtlEnterCriticalSection` at `0x18000e276`
- `LSASRV!LsaIAuditReplay` at `0x18000e83f`
- `LSASRV!LsaIAuditReplay` at `0x18000e83f`

## pseudocode

```c
__int64 __fastcall Pku2uDecryptServiceTicket(
        struct KERB_AP_REQUEST *a1,
        struct _PKU2U_CONTEXT *a2,
        struct KERB_ENCRYPTED_TICKET **a3,
        struct KERB_AUTHENTICATOR **a4,
        struct KERB_ENCRYPTION_KEY *a5,
        struct KERB_ENCRYPTION_KEY *a6,
        int *Size)
{
  unsigned int v7; // eax
  _BYTE *v10; // r8
  unsigned int v12; // r9d
  __int64 v13; // rbx
  int *v14; // rdi
  struct KERB_ENCRYPTION_KEY *v15; // r12
  __int64 v16; // rbx
  unsigned int i; // edx
  __int64 v18; // r15
  void **v19; // rbx
  struct CAuthenticatorList *v20; // r9
  int v21; // eax
  int v22; // r15d
  void (*v23)(void); // rax
  void (*v24)(void); // rax
  void (*v25)(void); // rax
  __int64 v27; // r10
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  struct KERB_ENCRYPTION_KEY *v31; // rax
  void *v32; // rsi
  void *v33; // rax
  struct PKERB_HOST_ADDRESSES **v34; // rdx
  struct _UNICODE_STRING *v35; // rax
  __int128 *v36; // rdi
  _QWORD *v37; // rsi
  _QWORD *v38; // rbx
  union _LARGE_INTEGER *v39; // [rsp+20h] [rbp-C1h]
  unsigned __int8 v40; // [rsp+28h] [rbp-B9h]
  unsigned __int8 v41; // [rsp+30h] [rbp-B1h]
  _QWORD v42[2]; // [rsp+70h] [rbp-71h] BYREF
  struct _UNICODE_STRING v43; // [rsp+80h] [rbp-61h] BYREF
  struct _UNICODE_STRING v44; // [rsp+90h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v46; // [rsp+B0h] [rbp-31h] BYREF
  __int64 v47; // [rsp+C0h] [rbp-21h]
  _OWORD v48[5]; // [rsp+C8h] [rbp-19h] BYREF
  struct _UNICODE_STRING *v49; // [rsp+130h] [rbp+4Fh] BYREF
  int v50; // [rsp+138h] [rbp+57h] BYREF
  struct KERB_AUTHENTICATOR **v51; // [rsp+148h] [rbp+67h]

  v51 = a4;
  v7 = *((_DWORD *)a1 + 2);
  v50 = 0;
  v10 = (char *)&v50 + 3;
  v12 = 0;
  v43 = 0;
  if ( v7 > 0x20 )
  {
    v7 = 32;
  }
  else if ( v7 <= 7 )
  {
    goto LABEL_3;
  }
  v27 = *((_QWORD *)a1 + 2);
  do
  {
    v28 = v12;
    v7 -= 8;
    ++v12;
    *v10-- = *(_BYTE *)(v28 + v27);
  }
  while ( v7 > 7 );
LABEL_3:
  if ( v7 )
    *v10 = *(_BYTE *)(v12 + *((_QWORD *)a1 + 2)) & (-1 << (8 - v7));
  v13 = *((_QWORD *)a2 + 2);
  v14 = Size;
  v15 = a5;
  memset(v48, 0, 32);
  LOBYTE(v49) = 0;
  *Size = 0;
  if ( *(_DWORD *)(v13 + 32) )
  {
    v13 = *((_QWORD *)a2 + 4);
    if ( !v13 )
    {
      v22 = -2146893042;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_47;
      v30 = 19;
      goto LABEL_44;
    }
  }
  if ( (v50 & 0x40000000) != 0 )
  {
    v22 = -2146893048;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_47;
    v30 = 20;
LABEL_44:
    WPP_SF_(v29[2], v30, &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids);
LABEL_87:
    v19 = (void **)v51;
    goto LABEL_18;
  }
  v16 = v13 + 40;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v16);
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(v16 + 136) )
    {
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v16);
      v22 = -2146893042;
      *v14 = 41;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
          *((unsigned int *)a1 + 15));
        goto LABEL_87;
      }
LABEL_47:
      v19 = (void **)v51;
LABEL_48:
      if ( *a3 )
      {
        KerbFreeData(0x21u, *a3);
        *a3 = 0;
      }
      if ( *v19 )
      {
        KerbFreeData(0x22u, *v19);
        *v19 = 0;
      }
      KerbFreeKey(v15);
      goto LABEL_20;
    }
    v18 = *(_QWORD *)(v16 + 144) + 24LL * i;
    if ( *((_DWORD *)a1 + 15) == *(_DWORD *)v18 )
      break;
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)v16);
  v19 = (void **)v51;
  v21 = KerbCheckTicket(
          (struct KERB_AP_REQUEST *)((char *)a1 + 24),
          (struct KERB_AP_REQUEST *)((char *)a1 + 96),
          (struct KERB_ENCRYPTION_KEY *)v18,
          v20,
          v39,
          v40,
          v41,
          (struct _KERB_REPLAY_AUDIT_INFO *)v48,
          a3,
          v51,
          v15,
          (struct _PKU2U_CONTEXT *)((char *)a2 + 224),
          (unsigned __int8 *)&v49);
  *v14 = v21;
  if ( !v21 )
  {
    v31 = a6;
    *(_OWORD *)a6 = *(_OWORD *)v18;
    *((_QWORD *)v31 + 2) = *(_QWORD *)(v18 + 16);
    LODWORD(Size) = *(_DWORD *)(v18 + 8);
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
    {
      v32 = (void *)(*(__int64 (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))();
    }
    else
    {
      v33 = (void *)(**((__int64 (***)(void))Pku2uGlobalBaseSSP + 31))();
      v32 = v33;
      if ( v33 )
      {
        memset_0(v33, 0, (unsigned int)Size);
        *((_QWORD *)a6 + 2) = v32;
LABEL_83:
        memcpy_0(v32, *(const void **)(v18 + 16), *(unsigned int *)(v18 + 8));
        v22 = 0;
        *v14 = 0;
        goto LABEL_20;
      }
    }
    *((_QWORD *)a6 + 2) = v32;
    if ( !v32 )
    {
      *v14 = 60;
      v22 = KerbMapKerbError(60);
      goto LABEL_18;
    }
    goto LABEL_83;
  }
  if ( v21 > 6 )
  {
    switch ( v21 )
    {
      case 7:
        v22 = -1073741429;
        break;
      case 12:
        v22 = -1073741714;
        break;
      case 14:
        v22 = -1073741059;
        break;
      case 16:
        v22 = -1073741637;
        break;
      case 18:
        v22 = -1073741710;
        break;
      case 23:
        v22 = -1073741711;
        break;
      case 24:
      case 25:
      case 41:
        v22 = -1073741718;
        break;
      case 27:
      case 69:
        v22 = -1073740792;
        break;
      case 28:
        v22 = -1073741424;
        break;
      case 29:
      case 68:
        v22 = -1073741730;
        break;
      case 32:
      case 33:
      case 37:
        v22 = -1073741517;
        break;
      case 35:
        v22 = -2146893022;
        break;
      case 39:
      case 40:
      case 71:
        v22 = -1073741811;
        break;
      case 45:
        v22 = -1073741022;
        break;
      case 52:
        v22 = -1073741306;
        break;
      case 60:
        v22 = -1073741670;
        break;
      case 70:
        v22 = -2146869247;
        break;
      case 72:
        v22 = -2146885616;
        break;
      case 73:
        v22 = -2146885614;
        break;
      case 74:
        v22 = -2146885613;
        break;
      case 75:
      case 76:
        v22 = -1073741063;
        break;
      case 77:
        v22 = -2146762480;
        break;
      default:
        goto LABEL_78;
    }
  }
  else if ( v21 == 6 )
  {
    v22 = -1073741724;
  }
  else if ( v21 == -2147483644 )
  {
    v22 = -1073741562;
  }
  else
  {
LABEL_78:
    v22 = -1073741715;
  }
LABEL_18:
  if ( *v14 == 34 )
  {
    v34 = (struct PKERB_HOST_ADDRESSES **)*a3;
    v42[0] = 0;
    v49 = 0;
    v42[1] = 0;
    v47 = 0;
    Size = 0;
    DestinationString = 0;
    v44 = 0;
    v46 = 0;
    if ( v34 && (*(_BYTE *)v34 & 0x20) != 0 )
    {
      KerbGetClientNetbiosAddress(&v43, v34[19]);
      v35 = &v43;
      if ( !v43.Length )
        v35 = 0;
      v49 = v35;
    }
    v36 = &v46;
    v37 = v48;
    if ( !((unsigned __int8 (__fastcall *)(__int128 *))Pku2uGlobalLsaFunctions->GetCallInfo)(&v46) )
      v36 = 0;
    v38 = &v48[1];
    if ( !LOWORD(v48[0]) )
      v37 = v42;
    if ( !LOWORD(v48[1]) )
      v38 = v42;
    Size = *(int **)(*(_QWORD *)(*((_QWORD *)a2 + 2) + 24LL) + 24LL);
    RtlInitUnicodeString(&DestinationString, L"KRB_AP_REQ");
    RtlInitUnicodeString(&v44, L"pku2u");
    LsaIAuditReplay(v37, v38, &DestinationString, &v44, v49, &Size, v36, 0);
    v19 = (void **)v51;
  }
  if ( v22 < 0 )
    goto LABEL_48;
LABEL_20:
  if ( *((_QWORD *)&v48[0] + 1) )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v23 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v23 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v23();
    v48[0] = 0;
  }
  if ( *((_QWORD *)&v48[1] + 1) )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v24 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v24 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v24();
    v48[1] = 0;
  }
  if ( v43.Buffer )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v25 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v25 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v25();
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x18000e1d0  mov     [rsp-8+arg_10], rbx
0x18000e1d5  mov     [rsp-8+arg_18], r9
0x18000e1da  push    rbp
0x18000e1db  push    rsi
0x18000e1dc  push    rdi
0x18000e1dd  push    r12
0x18000e1df  push    r13
0x18000e1e1  push    r14
0x18000e1e3  push    r15
0x18000e1e5  lea     rbp, [rsp-0Fh]
0x18000e1ea  sub     rsp, 0F0h
0x18000e1f1  mov     eax, [rcx+8]
0x18000e1f4  xor     r15d, r15d
0x18000e1f7  mov     [rbp+3Fh+arg_8], r15d
0x18000e1fb  xorps   xmm0, xmm0
0x18000e1fe  mov     r13, r8
0x18000e201  mov     r14, rdx
0x18000e204  lea     r8, [rbp+3Fh+arg_8+3]
0x18000e208  mov     rsi, rcx
0x18000e20b  mov     r9d, r15d
0x18000e20e  movups  xmmword ptr [rbp+3Fh+var_A0.Length], xmm0
0x18000e212  cmp     eax, 20h ; ' '
0x18000e215  ja      loc_18000E432
0x18000e21b  cmp     eax, 7
0x18000e21e  ja      loc_18000E437
0x18000e224  test    eax, eax
0x18000e226  jnz     loc_18000E459
0x18000e22c  mov     rbx, [r14+10h]
0x18000e230  xorps   xmm0, xmm0
0x18000e233  mov     rdi, [rbp+3Fh+Size]
0x18000e237  xor     eax, eax
0x18000e239  mov     r12, [rbp+3Fh+arg_20]
0x18000e23d  movups  [rbp+3Fh+var_58+2], xmm0
0x18000e241  mov     word ptr [rbp+3Fh+var_58], r15w
0x18000e246  movups  xmmword ptr [rbp+3Fh+var_48], xmm0
0x18000e24a  mov     byte ptr [rbp+3Fh+arg_0], al
0x18000e24d  mov     [rdi], r15d
0x18000e250  cmp     [rbx+20h], eax
0x18000e253  jz      short loc_18000E262
0x18000e255  mov     rbx, [r14+20h]
0x18000e259  test    rbx, rbx
0x18000e25c  jz      loc_18000E479
0x18000e262  test    [rbp+3Fh+arg_8], 40000000h
0x18000e269  jnz     loc_18000E4B9
0x18000e26f  add     rbx, 28h ; '('
0x18000e273  mov     rcx, rbx; CriticalSection
0x18000e276  call    cs:__imp_RtlEnterCriticalSection
0x18000e27c  mov     edx, r15d
0x18000e27f  cmp     edx, [rbx+88h]
0x18000e285  jnb     loc_18000E6EC
0x18000e28b  mov     eax, edx
0x18000e28d  lea     rcx, [rax+rax*2]
0x18000e291  mov     rax, [rbx+90h]
0x18000e298  lea     r15, [rax+rcx*8]
0x18000e29c  mov     eax, [rax+rcx*8]
0x18000e29f  cmp     [rsi+3Ch], eax
0x18000e2a2  jnz     loc_18000E51D
0x18000e2a8  mov     rcx, rbx; CriticalSection
0x18000e2ab  call    cs:__imp_RtlLeaveCriticalSection
0x18000e2b1  mov     rbx, [rbp+3Fh+arg_18]
0x18000e2b5  lea     r8, [rbp+3Fh+arg_0]
0x18000e2b9  mov     [rsp+120h+var_C0], r8; unsigned __int8 *
0x18000e2be  lea     rax, [r14+0E0h]
0x18000e2c5  mov     [rsp+120h+var_C8], rax; struct KERB_ENCRYPTION_KEY *
0x18000e2ca  lea     rdx, [rsi+60h]; struct KERB_ENCRYPTED_DATA *
0x18000e2ce  mov     [rsp+120h+var_D0], r12; struct KERB_ENCRYPTION_KEY *
0x18000e2d3  lea     rax, [rbp+3Fh+var_58]
0x18000e2d7  mov     [rsp+120h+var_D8], rbx; struct KERB_AUTHENTICATOR **
0x18000e2dc  lea     rcx, [rsi+18h]; struct KERB_TICKET *
0x18000e2e0  mov     [rsp+120h+var_E0], r13; struct KERB_ENCRYPTED_TICKET **
0x18000e2e5  mov     r8, r15; struct KERB_ENCRYPTION_KEY *
0x18000e2e8  mov     [rsp+120h+var_E8], rax; struct _KERB_REPLAY_AUDIT_INFO *
0x18000e2ed  call    ?KerbCheckTicket@@YAJPEAUKERB_TICKET@@PEAUKERB_ENCRYPTED_DATA@@PEAUKERB_ENCRYPTION_KEY@@PEAVCAuthenticatorList@@PEAT_LARGE_INTEGER@@EEPEAU_KERB_REPLAY_AUDIT_INFO@@PEAPEAUKERB_ENCRYPTED_TICKET@@PEAPEAUKERB_AUTHENTICATOR@@22PEAE@Z; KerbCheckTicket(KERB_TICKET *,KERB_ENCRYPTED_DATA *,KERB_ENCRYPTION_KEY *,CAuthenticatorList *,_LARGE_INTEGER *,uchar,uchar,_KERB_REPLAY_AUDIT_INFO *,KERB_ENCRYPTED_TICKET * *,KERB_AUTHENTICATOR * *,KERB_ENCRYPTION_KEY *,KERB_ENCRYPTION_KEY *,uchar *)
0x18000e2f2  mov     [rdi], eax
0x18000e2f4  test    eax, eax
0x18000e2f6  jz      loc_18000E655
0x18000e2fc  cmp     eax, 6
0x18000e2ff  jg      loc_18000E52F
0x18000e305  jz      loc_18000E524
0x18000e30b  cmp     eax, 80000004h
0x18000e310  jnz     def_18000E556; jumptable 000000018000E556 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67
0x18000e316  mov     r15d, 0C0000106h
0x18000e31c  jmp     short loc_18000E342
0x18000e31e  mov     rax, [rbp+3Fh+arg_28]
0x18000e322  mov     [rax+10h], rsi
0x18000e326  test    rsi, rsi
0x18000e329  jnz     loc_18000E6CE
0x18000e32f  mov     ecx, 3Ch ; '<'; int
0x18000e334  mov     dword ptr [rdi], 3Ch ; '<'
0x18000e33a  call    ?KerbMapKerbError@@YAJJ@Z; KerbMapKerbError(long)
0x18000e33f  mov     r15d, eax
0x18000e342  cmp     dword ptr [rdi], 22h ; '"'
0x18000e345  jz      loc_18000E744
0x18000e34b  test    r15d, r15d
0x18000e34e  js      loc_18000E4DC
0x18000e354  mov     rcx, qword ptr [rbp+3Fh+var_58+8]
0x18000e358  test    rcx, rcx
0x18000e35b  jz      short loc_18000E38B
0x18000e35d  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000e364  cmp     dword ptr [rax+0D0h], 1
0x18000e36b  jnz     loc_18000E408
0x18000e371  mov     rax, [rax+0F0h]
0x18000e378  mov     rax, [rax+188h]
0x18000e37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e384  xorps   xmm0, xmm0
0x18000e387  movups  [rbp+3Fh+var_58], xmm0
0x18000e38b  mov     rcx, [rbp+3Fh+var_40]
0x18000e38f  test    rcx, rcx
0x18000e392  jz      short loc_18000E3BE
0x18000e394  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000e39b  cmp     dword ptr [rax+0D0h], 1
0x18000e3a2  jnz     short loc_18000E418
0x18000e3a4  mov     rax, [rax+0F0h]
0x18000e3ab  mov     rax, [rax+188h]
0x18000e3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b7  xorps   xmm0, xmm0
0x18000e3ba  movups  xmmword ptr [rbp-9], xmm0
0x18000e3be  mov     rcx, [rbp+3Fh+var_A0.Buffer]
0x18000e3c2  test    rcx, rcx
0x18000e3c5  jz      short loc_18000E3EA
0x18000e3c7  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000e3ce  cmp     dword ptr [rax+0D0h], 1
0x18000e3d5  jnz     short loc_18000E425
0x18000e3d7  mov     rax, [rax+0F0h]
0x18000e3de  mov     rax, [rax+188h]
0x18000e3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3ea  mov     rbx, [rsp+120h+arg_10]
0x18000e3f2  mov     eax, r15d
0x18000e3f5  add     rsp, 0F0h
0x18000e3fc  pop     r15
0x18000e3fe  pop     r14
0x18000e400  pop     r13
0x18000e402  pop     r12
0x18000e404  pop     rdi
0x18000e405  pop     rsi
0x18000e406  pop     rbp
0x18000e407  retn
0x18000e408  mov     rax, [rax+0F8h]
0x18000e40f  mov     rax, [rax+8]
0x18000e413  jmp     loc_18000E37F
0x18000e418  mov     rax, [rax+0F8h]
0x18000e41f  mov     rax, [rax+8]
0x18000e423  jmp     short loc_18000E3B2
0x18000e425  mov     rax, [rax+0F8h]
0x18000e42c  mov     rax, [rax+8]
0x18000e430  jmp     short loc_18000E3E5
0x18000e432  mov     eax, 20h ; ' '
0x18000e437  mov     r10, [rcx+10h]
0x18000e43b  mov     ecx, r9d
0x18000e43e  add     eax, 0FFFFFFF8h
0x18000e441  inc     r9d
0x18000e444  movzx   edx, byte ptr [rcx+r10]
0x18000e449  mov     [r8], dl
0x18000e44c  dec     r8
0x18000e44f  cmp     eax, 7
0x18000e452  ja      short loc_18000E43B
0x18000e454  jmp     loc_18000E224
0x18000e459  mov     ecx, 8
0x18000e45e  mov     edx, 0FFh
0x18000e463  sub     ecx, eax
0x18000e465  mov     rax, [rsi+10h]
0x18000e469  shl     dl, cl
0x18000e46b  mov     ecx, r9d
0x18000e46e  and     dl, [rcx+rax]
0x18000e471  mov     [r8], dl
0x18000e474  jmp     loc_18000E22C
0x18000e479  mov     r15d, 8009030Eh
0x18000e47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e486  lea     rax, WPP_GLOBAL_Control
0x18000e48d  cmp     rcx, rax
0x18000e490  jz      short loc_18000E4D8
0x18000e492  test    byte ptr [rcx+1Ch], 1
0x18000e496  jz      short loc_18000E4D8
0x18000e498  mov     edx, 13h
0x18000e49d  jmp     short loc_18000E4A4
0x18000e49f  mov     edx, 14h
0x18000e4a4  mov     rcx, [rcx+10h]
0x18000e4a8  lea     r8, WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids
0x18000e4af  call    WPP_SF_
0x18000e4b4  jmp     loc_18000E73B
0x18000e4b9  mov     r15d, 80090308h
0x18000e4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4c6  lea     rax, WPP_GLOBAL_Control
0x18000e4cd  cmp     rcx, rax
0x18000e4d0  jz      short loc_18000E4D8
0x18000e4d2  test    byte ptr [rcx+1Ch], 2
0x18000e4d6  jnz     short loc_18000E49F
0x18000e4d8  mov     rbx, [rbp+3Fh+arg_18]
0x18000e4dc  mov     rdx, [r13+0]; void *
0x18000e4e0  test    rdx, rdx
0x18000e4e3  jz      short loc_18000E4F7
0x18000e4e5  mov     ecx, 21h ; '!'; unsigned int
0x18000e4ea  call    ?KerbFreeData@@YAXKPEAX@Z; KerbFreeData(ulong,void *)
0x18000e4ef  mov     qword ptr [r13+0], 0
0x18000e4f7  mov     rdx, [rbx]; void *
0x18000e4fa  test    rdx, rdx
0x18000e4fd  jz      short loc_18000E510
0x18000e4ff  mov     ecx, 22h ; '"'; unsigned int
0x18000e504  call    ?KerbFreeData@@YAXKPEAX@Z; KerbFreeData(ulong,void *)
0x18000e509  mov     qword ptr [rbx], 0
0x18000e510  mov     rcx, r12; struct KERB_ENCRYPTION_KEY *
0x18000e513  call    ?KerbFreeKey@@YAXPEAUKERB_ENCRYPTION_KEY@@@Z; KerbFreeKey(KERB_ENCRYPTION_KEY *)
0x18000e518  jmp     loc_18000E354
0x18000e51d  inc     edx
0x18000e51f  jmp     loc_18000E27F
0x18000e524  mov     r15d, 0C0000064h
0x18000e52a  jmp     loc_18000E342
0x18000e52f  add     eax, 0FFFFFFF9h; switch 71 cases
0x18000e532  cmp     eax, 46h
0x18000e535  ja      def_18000E556; jumptable 000000018000E556 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67
0x18000e53b  lea     rdx, __ImageBase
0x18000e542  cdqe
0x18000e544  movzx   eax, ds:(byte_18000E8AC - 180000000h)[rdx+rax]
0x18000e54c  mov     ecx, ds:(jpt_18000E556 - 180000000h)[rdx+rax*4]
0x18000e553  add     rcx, rdx
0x18000e556  jmp     rcx; switch jump
0x18000e558  mov     r15d, 0C0000072h; jumptable 000000018000E556 case 18
0x18000e55e  jmp     loc_18000E342
0x18000e563  mov     r15d, 0C0000071h; jumptable 000000018000E556 case 23
0x18000e569  jmp     loc_18000E342
0x18000e56e  mov     r15d, 0C000009Ah; jumptable 000000018000E556 case 60
0x18000e574  jmp     loc_18000E342
0x18000e579  mov     r15d, 0C0000133h; jumptable 000000018000E556 cases 32,33,37
0x18000e57f  jmp     loc_18000E342
0x18000e584  mov     r15d, 0C000006Eh; jumptable 000000018000E556 case 12
0x18000e58a  jmp     loc_18000E342
0x18000e58f  mov     r15d, 0C000018Bh; jumptable 000000018000E556 case 7
0x18000e595  jmp     loc_18000E342
0x18000e59a  mov     r15d, 0C000006Ah; jumptable 000000018000E556 cases 24,25,41
0x18000e5a0  jmp     loc_18000E342
0x18000e5a5  mov     r15d, 0C0000206h; jumptable 000000018000E556 case 52
0x18000e5ab  jmp     loc_18000E342
0x18000e5b0  mov     r15d, 0C00000BBh; jumptable 000000018000E556 case 16
0x18000e5b6  jmp     loc_18000E342
0x18000e5bb  mov     r15d, 80090322h; jumptable 000000018000E556 case 35
0x18000e5c1  jmp     loc_18000E342
0x18000e5c6  mov     r15d, 0C000005Eh; jumptable 000000018000E556 cases 29,68
0x18000e5cc  jmp     loc_18000E342
0x18000e5d1  mov     r15d, 80096001h; jumptable 000000018000E556 case 70
0x18000e5d7  jmp     loc_18000E342
0x18000e5dc  mov     r15d, 0C000000Dh; jumptable 000000018000E556 cases 39,40,71
0x18000e5e2  jmp     loc_18000E342
0x18000e5e7  mov     r15d, 80092010h; jumptable 000000018000E556 case 72
0x18000e5ed  jmp     loc_18000E342
0x18000e5f2  mov     r15d, 80092012h; jumptable 000000018000E556 case 73
0x18000e5f8  jmp     loc_18000E342
0x18000e5fd  mov     r15d, 800B0110h; jumptable 000000018000E556 case 77
0x18000e603  jmp     loc_18000E342
0x18000e608  mov     r15d, 80092013h; jumptable 000000018000E556 case 74
0x18000e60e  jmp     loc_18000E342
0x18000e613  mov     r15d, 0C00002F9h; jumptable 000000018000E556 cases 75,76
0x18000e619  jmp     loc_18000E342
0x18000e61e  mov     r15d, 0C0000190h; jumptable 000000018000E556 case 28
0x18000e624  jmp     loc_18000E342
0x18000e629  mov     r15d, 0C00002FDh; jumptable 000000018000E556 case 14
0x18000e62f  jmp     loc_18000E342
0x18000e634  mov     r15d, 0C0000408h; jumptable 000000018000E556 cases 27,69
0x18000e63a  jmp     loc_18000E342
0x18000e63f  mov     r15d, 0C0000322h; jumptable 000000018000E556 case 45
0x18000e645  jmp     loc_18000E342
0x18000e64a  mov     r15d, 0C000006Dh; jumptable 000000018000E556 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67
0x18000e650  jmp     loc_18000E342
0x18000e655  mov     rax, [rbp+3Fh+arg_28]
0x18000e659  movups  xmm0, xmmword ptr [r15]
0x18000e65d  movups  xmmword ptr [rax], xmm0
0x18000e660  movsd   xmm1, qword ptr [r15+10h]
0x18000e666  movsd   qword ptr [rax+10h], xmm1
0x18000e66b  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000e672  mov     ecx, [r15+8]
0x18000e676  mov     dword ptr [rbp+3Fh+Size], ecx
0x18000e679  cmp     dword ptr [rax+0D0h], 1
0x18000e680  jnz     short loc_18000E69D
0x18000e682  mov     rax, [rax+0F0h]
0x18000e689  mov     rax, [rax+180h]
0x18000e690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e695  mov     rsi, rax
0x18000e698  jmp     loc_18000E31E
0x18000e69d  mov     rax, [rax+0F8h]
0x18000e6a4  mov     rax, [rax]
0x18000e6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ac  mov     rsi, rax
0x18000e6af  test    rax, rax
0x18000e6b2  jz      loc_18000E31E
0x18000e6b8  mov     r8d, dword ptr [rbp+3Fh+Size]; Size
0x18000e6bc  xor     edx, edx; Val
0x18000e6be  mov     rcx, rax; void *
0x18000e6c1  call    memset_0
0x18000e6c6  mov     rax, [rbp+3Fh+arg_28]
0x18000e6ca  mov     [rax+10h], rsi
0x18000e6ce  mov     r8d, [r15+8]; Size
0x18000e6d2  mov     rcx, rsi; void *
0x18000e6d5  mov     rdx, [r15+10h]; Src
0x18000e6d9  call    memcpy_0
0x18000e6de  xor     r15d, r15d
0x18000e6e1  mov     dword ptr [rdi], 0
0x18000e6e7  jmp     loc_18000E354
0x18000e6ec  mov     rcx, rbx; CriticalSection
0x18000e6ef  call    cs:__imp_RtlLeaveCriticalSection
0x18000e6f5  mov     r15d, 8009030Eh
0x18000e6fb  mov     dword ptr [rdi], 29h ; ')'
  ... truncated ...
```
