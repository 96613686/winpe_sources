# LsaIfSynchronizeMasterKeys(void *,_CREDENTIAL_KEY *,ulong *,ulong *)

- ea: `0x18002ca70`
- end: `0x18002cd14`
- name: `?LsaIfSynchronizeMasterKeys@@YAJPEAXPEAU_CREDENTIAL_KEY@@PEAK2@Z`
- size: `676`
- prototype: `__int64 __fastcall(HANDLE hToken, struct _CREDENTIAL_KEY *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007f10`
- `0x1800097f0`
- `0x18000c4a0`
- `0x18000db40`
- `0x18001ab70`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002ca70`
- `0x18002e130`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cbb9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002cbb9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc1b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002cc1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cbc9`
- `CRYPTSP!SystemFunction007` at `0x18002cb97`
- `CRYPTSP!SystemFunction007` at `0x18002cb97`

## string_xrefs

- `0x18002cbdb`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002cc31`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002cca0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002cce1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall LsaIfSynchronizeMasterKeys(
        HANDLE hToken,
        struct _CREDENTIAL_KEY *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v8; // r9
  ULONG v9; // edx
  __int64 v10; // rcx
  __int64 v11; // xmm0_8
  unsigned int LastError; // ebx
  __int64 v13; // rcx
  int v14; // eax
  int v15; // edi
  void *v16; // rcx
  unsigned int v17; // eax
  int v18; // edi
  __int128 v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+54h] [rbp-ACh]
  UCHAR v23[16]; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v24; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v25; // [rsp+84h] [rbp-7Ch]
  _DWORD v26[13]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v27; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned int v28[142]; // [rsp+C8h] [rbp-38h] BYREF

  memset_0(v26, 0, 0x270u);
  v21 = 0;
  v20 = 0;
  v25 = 0;
  v22 = 0;
  *(_OWORD *)v23 = 0;
  v24 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
  if ( !a2 )
  {
    v8 = 1666;
LABEL_27:
    LastError = -1073741811;
    v13 = 3221225485LL;
    goto LABEL_28;
  }
  v9 = *((_DWORD *)a2 + 3);
  if ( v9 > 0xFFFF
    || (v10 = *((unsigned int *)a2 + 2), (unsigned int)v10 > *(_DWORD *)a2)
    || (unsigned int)v10 + v9 > *(_DWORD *)a2 )
  {
    v8 = 1676;
    goto LABEL_27;
  }
  v11 = *(_QWORD *)((char *)a2 + 20);
  v21 = *((_DWORD *)a2 + 4);
  DWORD2(v22) = *((_DWORD *)a2 + 7);
  *(_QWORD *)&v22 = v11;
  *((_QWORD *)&v20 + 1) = (char *)a2 + v10;
  LOWORD(v20) = v9;
  if ( !(unsigned int)FMyPrimitiveSHA((PUCHAR)a2 + v10, v9, v23) )
  {
    LastError = -1073283059;
    v8 = 1703;
    v13 = 3221684237LL;
LABEL_28:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v8);
    return LastError;
  }
  v14 = SystemFunction007(&v20, (char *)&v24 + 4);
  LastError = v14;
  if ( v14 < 0 )
  {
    v8 = 1714;
    v13 = (unsigned int)v14;
    goto LABEL_28;
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v15 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)v26, 0, 0, 0);
    RevertToSelf();
    if ( v15 )
    {
      DebugTraceError(
        (unsigned int)v15,
        "dwError",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        1741);
      if ( v15 <= 0 )
        return (unsigned int)v15;
      LastError = (unsigned __int16)v15;
      goto LABEL_16;
    }
    GetDefaultAlgInfo(v16, &v27, 0, v28, 0);
    v17 = SynchronizeMasterKeys(v26, 0, (struct DP_KEK *)&v21, 0, 2u, a3, a4);
    v18 = v17;
    if ( v17 )
    {
      DebugTraceError(v17, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1769);
      if ( v18 > 0 )
        LastError = (unsigned __int16)v18 | 0xC0070000;
      else
        LastError = v18;
    }
    CPSDeleteServerContext((struct CRYPT_SERVER_CONTEXT *)v26);
  }
  else
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 1730);
    if ( (int)LastError > 0 )
    {
      LastError = (unsigned __int16)LastError;
LABEL_16:
      LastError |= 0xC0070000;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18002ca70  push    rbp
0x18002ca72  push    rbx
0x18002ca73  push    rsi
0x18002ca74  push    rdi
0x18002ca75  push    r14
0x18002ca77  lea     rbp, [rsp-210h]
0x18002ca7f  sub     rsp, 310h
0x18002ca86  mov     rax, cs:__security_cookie
0x18002ca8d  xor     rax, rsp
0x18002ca90  mov     [rbp+230h+var_30], rax
0x18002ca97  mov     rsi, r8
0x18002ca9a  mov     rbx, rdx
0x18002ca9d  mov     rdi, rcx
0x18002caa0  xor     edx, edx; Val
0x18002caa2  mov     r8d, 270h; Size
0x18002caa8  lea     rcx, [rbp+230h+var_2A0]; void *
0x18002caac  mov     r14, r9
0x18002caaf  call    memset_0
0x18002cab4  xorps   xmm0, xmm0
0x18002cab7  mov     [rsp+330h+var_2E0], 0
0x18002cabf  xor     eax, eax
0x18002cac1  movups  [rsp+330h+var_2F0], xmm0
0x18002cac6  mov     [rbp+230h+var_2AC], rax
0x18002caca  movups  [rsp+330h+var_2DC], xmm0
0x18002cacf  movups  xmmword ptr [rsp+330h+var_2CC], xmm0
0x18002cad4  movups  [rsp+330h+var_2BC], xmm0
0x18002cad9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cae0  lea     rax, WPP_GLOBAL_Control
0x18002cae7  cmp     rcx, rax
0x18002caea  jz      short loc_18002CB07
0x18002caec  test    byte ptr [rcx+1Ch], 4
0x18002caf0  jz      short loc_18002CB07
0x18002caf2  mov     rcx, [rcx+10h]
0x18002caf6  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002cafd  mov     edx, 1Eh
0x18002cb02  call    WPP_SF_
0x18002cb07  test    rbx, rbx
0x18002cb0a  jnz     short loc_18002CB17
0x18002cb0c  mov     r9d, 682h
0x18002cb12  jmp     loc_18002CCD7
0x18002cb17  mov     edx, [rbx+0Ch]; cbInput
0x18002cb1a  cmp     edx, 0FFFFh
0x18002cb20  ja      loc_18002CCD1
0x18002cb26  mov     ecx, [rbx+8]
0x18002cb29  cmp     ecx, [rbx]
0x18002cb2b  ja      loc_18002CCD1
0x18002cb31  lea     eax, [rcx+rdx]
0x18002cb34  cmp     eax, [rbx]
0x18002cb36  ja      loc_18002CCD1
0x18002cb3c  mov     eax, [rbx+10h]
0x18002cb3f  add     rcx, rbx; pbInput
0x18002cb42  movsd   xmm0, qword ptr [rbx+14h]
0x18002cb47  mov     [rsp+330h+var_2E0], eax
0x18002cb4b  mov     eax, [rbx+1Ch]
0x18002cb4e  mov     dword ptr [rsp+330h+var_2DC+8], eax
0x18002cb52  movzx   eax, dx
0x18002cb55  lea     rax, [rsp+330h+var_2CC]
0x18002cb5a  movsd   qword ptr [rsp+330h+var_2DC], xmm0
0x18002cb60  mov     [rsp+330h+var_310], rax; PUCHAR
0x18002cb65  mov     qword ptr [rsp+330h+var_2F0+8], rcx
0x18002cb6a  mov     word ptr [rsp+330h+var_2F0], dx
0x18002cb6f  call    FMyPrimitiveSHA
0x18002cb74  test    eax, eax
0x18002cb76  jnz     short loc_18002CB8D
0x18002cb78  mov     ebx, 0C007000Dh
0x18002cb7d  mov     r9d, 6A7h
0x18002cb83  mov     ecx, 0C007000Dh
0x18002cb88  jmp     loc_18002CCE1
0x18002cb8d  lea     rdx, [rsp+330h+var_2BC+4]
0x18002cb92  lea     rcx, [rsp+330h+var_2F0]
0x18002cb97  call    cs:__imp_SystemFunction007
0x18002cb9e  nop     dword ptr [rax+rax+00h]
0x18002cba3  mov     ebx, eax
0x18002cba5  test    eax, eax
0x18002cba7  jns     short loc_18002CBB6
0x18002cba9  mov     r9d, 6B2h
0x18002cbaf  mov     ecx, eax
0x18002cbb1  jmp     loc_18002CCE1
0x18002cbb6  mov     rcx, rdi; hToken
0x18002cbb9  call    cs:__imp_ImpersonateLoggedOnUser
0x18002cbc0  nop     dword ptr [rax+rax+00h]
0x18002cbc5  test    eax, eax
0x18002cbc7  jnz     short loc_18002CC08
0x18002cbc9  call    cs:__imp_GetLastError
0x18002cbd0  nop     dword ptr [rax+rax+00h]
0x18002cbd5  mov     r9d, 6C2h
0x18002cbdb  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cbe2  mov     ecx, eax
0x18002cbe4  lea     rdx, aDwerror; "dwError"
0x18002cbeb  mov     ebx, eax
0x18002cbed  call    DebugTraceError
0x18002cbf2  test    ebx, ebx
0x18002cbf4  jle     loc_18002CCF4
0x18002cbfa  movzx   ebx, bx
0x18002cbfd  or      ebx, 0C0070000h
0x18002cc03  jmp     loc_18002CCF4
0x18002cc08  xor     r9d, r9d; unsigned int *
0x18002cc0b  lea     rcx, [rbp+230h+var_2A0]; struct CRYPT_SERVER_CONTEXT *
0x18002cc0f  xor     r8d, r8d; unsigned __int16 **
0x18002cc12  xor     edx, edx; void *
0x18002cc14  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18002cc19  mov     edi, eax
0x18002cc1b  call    cs:__imp_RevertToSelf
0x18002cc22  nop     dword ptr [rax+rax+00h]
0x18002cc27  test    edi, edi
0x18002cc29  jz      short loc_18002CC56
0x18002cc2b  mov     r9d, 6CDh
0x18002cc31  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cc38  lea     rdx, aDwerror; "dwError"
0x18002cc3f  mov     ecx, edi
0x18002cc41  call    DebugTraceError
0x18002cc46  test    edi, edi
0x18002cc48  jg      short loc_18002CC51
0x18002cc4a  mov     ebx, edi
0x18002cc4c  jmp     loc_18002CCF4
0x18002cc51  movzx   ebx, di
0x18002cc54  jmp     short loc_18002CBFD
0x18002cc56  lea     r9, [rbp+230h+var_268]; unsigned int *
0x18002cc5a  mov     [rsp+330h+var_310], 0; unsigned int *
0x18002cc63  xor     r8d, r8d; unsigned int *
0x18002cc66  lea     rdx, [rbp+230h+var_26C]; unsigned int *
0x18002cc6a  call    ?GetDefaultAlgInfo@@YAXPEAXPEAK111@Z; GetDefaultAlgInfo(void *,ulong *,ulong *,ulong *,ulong *)
0x18002cc6f  mov     [rsp+330h+var_300], r14; unsigned int *
0x18002cc74  lea     r8, [rsp+330h+var_2E0]; struct DP_KEK *
0x18002cc79  mov     [rsp+330h+var_308], rsi; unsigned int *
0x18002cc7e  lea     rcx, [rbp+230h+var_2A0]; void *
0x18002cc82  xor     r9d, r9d; struct DP_KEK *
0x18002cc85  mov     dword ptr [rsp+330h+var_310], 2; unsigned int
0x18002cc8d  xor     edx, edx; unsigned int
0x18002cc8f  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002cc94  mov     edi, eax
0x18002cc96  test    eax, eax
0x18002cc98  jz      short loc_18002CCC6
0x18002cc9a  mov     r9d, 6E9h
0x18002cca0  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cca7  lea     rdx, aDwerror; "dwError"
0x18002ccae  mov     ecx, eax
0x18002ccb0  call    DebugTraceError
0x18002ccb5  test    edi, edi
0x18002ccb7  jg      short loc_18002CCBD
0x18002ccb9  mov     ebx, edi
0x18002ccbb  jmp     short loc_18002CCC6
0x18002ccbd  movzx   ebx, di
0x18002ccc0  or      ebx, 0C0070000h
0x18002ccc6  lea     rcx, [rbp+230h+var_2A0]; struct CRYPT_SERVER_CONTEXT *
0x18002ccca  call    ?CPSDeleteServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@@Z; CPSDeleteServerContext(CRYPT_SERVER_CONTEXT *)
0x18002cccf  jmp     short loc_18002CCF4
0x18002ccd1  mov     r9d, 68Ch
0x18002ccd7  mov     ebx, 0C000000Dh
0x18002ccdc  mov     ecx, 0C000000Dh
0x18002cce1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002cce8  lea     rdx, aStatus; "Status"
0x18002ccef  call    DebugTraceError
0x18002ccf4  mov     eax, ebx
0x18002ccf6  mov     rcx, [rbp+230h+var_30]
0x18002ccfd  xor     rcx, rsp; StackCookie
0x18002cd00  call    __security_check_cookie
0x18002cd05  add     rsp, 310h
0x18002cd0c  pop     r14
0x18002cd0e  pop     rdi
0x18002cd0f  pop     rsi
0x18002cd10  pop     rbx
0x18002cd11  pop     rbp
0x18002cd12  retn
```
