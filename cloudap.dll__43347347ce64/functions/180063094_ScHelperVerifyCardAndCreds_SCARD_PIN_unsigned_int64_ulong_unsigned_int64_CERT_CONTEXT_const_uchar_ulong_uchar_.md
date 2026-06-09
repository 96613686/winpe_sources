# __ScHelperVerifyCardAndCreds(_SCARD_PIN *,unsigned __int64,ulong,unsigned __int64,_CERT_CONTEXT const *,uchar *,ulong,uchar *,ulong *)

- ea: `0x180063094`
- end: `0x18006332d`
- name: `?__ScHelperVerifyCardAndCreds@@YAJPEAU_SCARD_PIN@@_KK1PEBU_CERT_CONTEXT@@PEAEK3PEAK@Z`
- size: `665`
- prototype: `__int64 __fastcall(struct _SCARD_PIN *, void *, unsigned int, unsigned __int64, const struct _CERT_CONTEXT *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800627c8`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003530c`
- `0x18003faf4`
- `0x180063094`
- `0x18007db08`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006329a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006329a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180063290`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180063290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800632f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800632f5`

## string_xrefs

- `0x1800630f8`: `ImpersonateClient`
- `0x1800632c3`: `SetThreadToken`

## pseudocode

```c
__int64 __fastcall __ScHelperVerifyCardAndCreds(
        struct _SCARD_PIN *a1,
        void *a2,
        unsigned int a3,
        unsigned __int64 a4,
        const struct _CERT_CONTEXT *a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int *a9)
{
  HANDLE v9; // rsi
  int v10; // ebp
  int v11; // r12d
  const WCHAR *v14; // r8
  unsigned int v17; // ebx
  const char *v18; // rax
  const char *v19; // r9
  const char *v20; // rax
  __int64 v21; // r8
  const char *v22; // r9
  signed int LastError; // eax
  unsigned int v24; // edi
  const char *v25; // rax
  unsigned __int8 *v27; // [rsp+20h] [rbp-68h]
  HANDLE hObject; // [rsp+90h] [rbp+8h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  hObject = 0;
  v14 = &Class;
  if ( !a1 )
  {
    v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 0, v20, 696, "No PIN was given for ScHelperVerifyCardAndCreds", v21);
    goto LABEL_9;
  }
  if ( *((_DWORD *)a1 + 3) )
  {
    v17 = ImpersonateClient(&hObject);
    if ( v17 )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v18, 676, "ImpersonateClient", &Class);
      v9 = hObject;
      goto LABEL_19;
    }
    v9 = hObject;
    v10 = 1;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, const WCHAR *))g_pLsaFunctionTable->LsaUnprotectMemory)(
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 2),
    v14);
  v11 = 1;
  v17 = SetScardPin((NCRYPT_HANDLE)a2, a3, *(unsigned __int8 **)a1, *((_DWORD *)a1 + 2));
  if ( !v17 )
  {
LABEL_9:
    if ( a2 )
    {
      v17 = ScHelperDecryptCredentials(a2, a3, a4, a6, a7, a8, a9);
      if ( !v17 )
        goto LABEL_13;
    }
    else
    {
      v17 = -1073741023;
    }
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    LODWORD(v27) = 708;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v22, v27, "ScHelperVerifyCardAndCreds", &Class);
    goto LABEL_13;
  }
  v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v19, 692, "SetScardPin", &Class);
LABEL_13:
  if ( v10 && !SetThreadToken(0, v9) )
  {
    LastError = GetLastError();
    v24 = LastError;
    if ( LastError > 0 )
      v24 = (unsigned __int16)LastError | 0xC0070000;
    v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    LODWORD(v27) = 718;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v24, v25, v27, "SetThreadToken", &Class);
    if ( (v17 & 0x80000000) == 0 )
      v17 = v24;
  }
LABEL_19:
  if ( v9 )
    CloseHandle(v9);
  if ( v11 )
    ((void (__fastcall *)(_QWORD, _QWORD))g_pLsaFunctionTable->LsaProtectMemory)(
      *(_QWORD *)a1,
      *((unsigned int *)a1 + 2));
  return v17;
}

```

## disassembly

```asm
0x180063094  mov     rax, rsp
0x180063097  push    rbx
0x180063098  push    rbp
0x180063099  push    rsi
0x18006309a  push    rdi
0x18006309b  push    r12
0x18006309d  push    r13
0x18006309f  push    r14
0x1800630a1  push    r15
0x1800630a3  sub     rsp, 48h
0x1800630a7  xor     esi, esi
0x1800630a9  xor     ebp, ebp
0x1800630ab  xor     r12d, r12d
0x1800630ae  mov     [rax+8], rsi
0x1800630b2  mov     r15d, r8d
0x1800630b5  mov     r13, r9
0x1800630b8  lea     r8, Class
0x1800630bf  mov     rdi, rdx
0x1800630c2  mov     r14, rcx
0x1800630c5  test    rcx, rcx
0x1800630c8  jz      loc_1800631B9
0x1800630ce  cmp     [rcx+0Ch], esi
0x1800630d1  jz      short loc_18006313C
0x1800630d3  lea     rcx, [rax+8]; void **
0x1800630d7  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x1800630dc  mov     ebx, eax
0x1800630de  test    eax, eax
0x1800630e0  jz      short loc_18006312F
0x1800630e2  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x1800630e9  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800630ee  mov     r9, rax
0x1800630f1  lea     r15, Class
0x1800630f8  lea     rax, aImpersonatecli; "ImpersonateClient"
0x1800630ff  mov     [rsp+88h+var_58], r15
0x180063104  mov     qword ptr [rsp+88h+var_60], rax
0x180063109  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180063110  mov     r8d, ebx
0x180063113  mov     dword ptr [rsp+88h+var_68], 2A4h
0x18006311b  xor     ecx, ecx
0x18006311d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180063122  mov     rsi, [rsp+88h+hObject]
0x18006312a  jmp     loc_1800632ED
0x18006312f  mov     rsi, [rsp+88h+hObject]
0x180063137  mov     ebp, 1
0x18006313c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180063143  mov     edx, [r14+8]
0x180063147  mov     rcx, [r14]
0x18006314a  mov     rax, [rax+168h]
0x180063151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063156  mov     r9d, [r14+8]; unsigned int
0x18006315a  mov     edx, r15d; unsigned int
0x18006315d  mov     r8, [r14]; unsigned __int8 *
0x180063160  mov     rcx, rdi; hObject
0x180063163  mov     r12d, 1
0x180063169  call    ?SetScardPin@@YAJ_KKPEAEK@Z; SetScardPin(unsigned __int64,ulong,uchar *,ulong)
0x18006316e  mov     ebx, eax
0x180063170  test    eax, eax
0x180063172  jz      short loc_1800631F2
0x180063174  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x18006317b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180063180  mov     r9, rax
0x180063183  lea     r15, Class
0x18006318a  mov     [rsp+88h+var_58], r15
0x18006318f  lea     rax, aSetscardpin; "SetScardPin"
0x180063196  mov     qword ptr [rsp+88h+var_60], rax
0x18006319b  mov     dword ptr [rsp+88h+var_68], 2B4h
0x1800631a3  mov     r8d, ebx
0x1800631a6  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800631ad  xor     ecx, ecx
0x1800631af  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800631b4  jmp     loc_180063287
0x1800631b9  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x1800631c0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800631c5  mov     [rsp+88h+var_58], r8
0x1800631ca  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800631d1  mov     r9, rax
0x1800631d4  xor     r8d, r8d
0x1800631d7  lea     rax, aNoPinWasGivenF; "No PIN was given for ScHelperVerifyCard"...
0x1800631de  xor     ecx, ecx
0x1800631e0  mov     qword ptr [rsp+88h+var_60], rax
0x1800631e5  mov     dword ptr [rsp+88h+var_68], 2B8h
0x1800631ed  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800631f2  test    rdi, rdi
0x1800631f5  jnz     short loc_1800631FE
0x1800631f7  mov     ebx, 0C0000321h
0x1800631fc  jmp     short loc_18006324C
0x1800631fe  mov     rax, [rsp+88h+arg_40]
0x180063206  mov     r8, r13; unsigned __int64
0x180063209  mov     r9, [rsp+88h+arg_20]
0x180063211  mov     edx, r15d; dwKeySpec
0x180063214  mov     [rsp+88h+var_50], rax; unsigned int *
0x180063219  mov     rcx, rdi; void *
0x18006321c  mov     rax, [rsp+88h+arg_38]
0x180063224  mov     [rsp+88h+var_58], rax; unsigned __int8 *
0x180063229  mov     eax, [rsp+88h+arg_30]
0x180063230  mov     [rsp+88h+var_60], eax; unsigned int
0x180063234  mov     rax, [rsp+88h+arg_28]
0x18006323c  mov     [rsp+88h+var_68], rax; unsigned __int8 *
0x180063241  call    ScHelperDecryptCredentials
0x180063246  mov     ebx, eax
0x180063248  test    eax, eax
0x18006324a  jz      short loc_180063280
0x18006324c  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180063253  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180063258  mov     r9, rax
0x18006325b  lea     r15, Class
0x180063262  mov     [rsp+88h+var_58], r15
0x180063267  lea     rax, aSchelperverify; "ScHelperVerifyCardAndCreds"
0x18006326e  mov     qword ptr [rsp+88h+var_60], rax
0x180063273  mov     dword ptr [rsp+88h+var_68], 2C4h
0x18006327b  jmp     loc_1800631A3
0x180063280  lea     r15, Class
0x180063287  test    ebp, ebp
0x180063289  jz      short loc_1800632ED
0x18006328b  mov     rdx, rsi; Token
0x18006328e  xor     ecx, ecx; Thread
0x180063290  call    cs:__imp_SetThreadToken
0x180063296  test    eax, eax
0x180063298  jnz     short loc_1800632ED
0x18006329a  call    cs:__imp_GetLastError
0x1800632a0  mov     edi, eax
0x1800632a2  test    eax, eax
0x1800632a4  jle     short loc_1800632AF
0x1800632a6  movzx   edi, ax
0x1800632a9  or      edi, 0C0070000h
0x1800632af  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x1800632b6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800632bb  mov     r9, rax
0x1800632be  mov     [rsp+88h+var_58], r15
0x1800632c3  lea     rax, aSetthreadtoken; "SetThreadToken"
0x1800632ca  mov     r8d, edi
0x1800632cd  mov     qword ptr [rsp+88h+var_60], rax
0x1800632d2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800632d9  xor     ecx, ecx
0x1800632db  mov     dword ptr [rsp+88h+var_68], 2CEh
0x1800632e3  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800632e8  test    ebx, ebx
0x1800632ea  cmovns  ebx, edi
0x1800632ed  test    rsi, rsi
0x1800632f0  jz      short loc_1800632FB
0x1800632f2  mov     rcx, rsi; hObject
0x1800632f5  call    cs:__imp_CloseHandle
0x1800632fb  test    r12d, r12d
0x1800632fe  jz      short loc_18006331A
0x180063300  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180063307  mov     edx, [r14+8]
0x18006330b  mov     rcx, [r14]
0x18006330e  mov     rax, [rax+160h]
0x180063315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006331a  mov     eax, ebx
0x18006331c  add     rsp, 48h
0x180063320  pop     r15
0x180063322  pop     r14
0x180063324  pop     r13
0x180063326  pop     r12
0x180063328  pop     rdi
0x180063329  pop     rsi
0x18006332a  pop     rbp
0x18006332b  pop     rbx
0x18006332c  retn
```
