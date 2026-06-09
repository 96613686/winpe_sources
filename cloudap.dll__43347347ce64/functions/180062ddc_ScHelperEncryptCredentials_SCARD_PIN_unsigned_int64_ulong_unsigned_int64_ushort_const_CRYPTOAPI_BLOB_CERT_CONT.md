# __ScHelperEncryptCredentials(_SCARD_PIN *,unsigned __int64,ulong,unsigned __int64,ushort const *,_CRYPTOAPI_BLOB *,_CERT_CONTEXT const *,_ScHelper_RandomCredBits *,uchar *,ulong,uchar *,ulong *)

- ea: `0x180062ddc`
- end: `0x18006308d`
- name: `?__ScHelperEncryptCredentials@@YAJPEAU_SCARD_PIN@@_KK1PEBGPEAU_CRYPTOAPI_BLOB@@PEBU_CERT_CONTEXT@@PEAU_ScHelper_RandomCredBits@@PEAEK6PEAK@Z`
- size: `689`
- prototype: `__int64 __fastcall(struct _SCARD_PIN *, void *, unsigned int, __int64, const unsigned __int16 *, struct _CRYPTOAPI_BLOB *, const struct _CERT_CONTEXT *, struct _ScHelper_RandomCredBits *, unsigned __int8 *, size_t, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18003d41c`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003530c`
- `0x18003faf4`
- `0x180062ddc`
- `0x18007de50`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ffb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062ffb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062ff1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180062ff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063056`

## string_xrefs

- `0x180062e3f`: `ImpersonateClient`
- `0x180063024`: `SetThreadToken`

## pseudocode

```c
__int64 __fastcall __ScHelperEncryptCredentials(
        struct _SCARD_PIN *a1,
        void *a2,
        unsigned int a3,
        __int64 a4,
        const unsigned __int16 *a5,
        struct _CRYPTOAPI_BLOB *a6,
        const struct _CERT_CONTEXT *a7,
        struct _ScHelper_RandomCredBits *a8,
        unsigned __int8 *a9,
        size_t a10,
        unsigned __int8 *a11,
        unsigned int *a12)
{
  HANDLE v12; // rsi
  int v13; // edi
  int v14; // ebp
  const WCHAR *v16; // r8
  unsigned int v19; // ebx
  const char *v20; // rax
  const char *v21; // r9
  const char *v22; // rax
  __int64 v23; // r8
  const char *v24; // r9
  signed int LastError; // eax
  unsigned int v26; // edi
  const char *v27; // rax
  __int64 v29; // [rsp+20h] [rbp-88h]
  size_t v30; // [rsp+40h] [rbp-68h]
  HANDLE hObject; // [rsp+B0h] [rbp+8h] BYREF

  v12 = 0;
  v13 = 0;
  v14 = 0;
  hObject = 0;
  v16 = &Class;
  if ( !a1 )
  {
    v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 0, v22, 608, "No PIN was provided for ScHelperEncryptCredentials", v23);
LABEL_9:
    LODWORD(v30) = a10;
    v19 = ScHelperEncryptCredentials(
            a2,
            (__int64)a6,
            (__int64)a7,
            (__int64)a8,
            (__int64)a9,
            v30,
            (__int64)a11,
            (__int64)a12);
    if ( v19 )
    {
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
      LODWORD(v29) = 623;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v24, v29, "ScHelperEncryptCredentials", &Class);
    }
    goto LABEL_11;
  }
  if ( *((_DWORD *)a1 + 3) )
  {
    v19 = ImpersonateClient(&hObject);
    if ( v19 )
    {
      v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v20, 588, "ImpersonateClient", &Class);
      v12 = hObject;
      goto LABEL_17;
    }
    v12 = hObject;
    v13 = 1;
  }
  ((void (__fastcall *)(_QWORD, _QWORD, const WCHAR *))g_pLsaFunctionTable->LsaUnprotectMemory)(
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 2),
    v16);
  v14 = 1;
  v19 = SetScardPin((NCRYPT_HANDLE)a2, a3, *(unsigned __int8 **)a1, *((_DWORD *)a1 + 2));
  if ( !v19 )
    goto LABEL_9;
  v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v19, v21, 604, "SetScardPin", &Class);
LABEL_11:
  if ( v13 && !SetThreadToken(0, v12) )
  {
    LastError = GetLastError();
    v26 = LastError;
    if ( LastError > 0 )
      v26 = (unsigned __int16)LastError | 0xC0070000;
    v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\libs\\scardutility\\lib\\scardcryptoutility.cpp");
    LODWORD(v29) = 633;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v26, v27, v29, "SetThreadToken", &Class);
    if ( (v19 & 0x80000000) == 0 )
      v19 = v26;
  }
LABEL_17:
  if ( v12 )
    CloseHandle(v12);
  if ( v14 )
    ((void (__fastcall *)(_QWORD, _QWORD))g_pLsaFunctionTable->LsaProtectMemory)(
      *(_QWORD *)a1,
      *((unsigned int *)a1 + 2));
  return v19;
}

```

## disassembly

```asm
0x180062ddc  mov     rax, rsp
0x180062ddf  push    rbx
0x180062de0  push    rbp
0x180062de1  push    rsi
0x180062de2  push    rdi
0x180062de3  push    r12
0x180062de5  push    r13
0x180062de7  push    r14
0x180062de9  push    r15
0x180062deb  sub     rsp, 68h
0x180062def  xor     esi, esi
0x180062df1  xor     edi, edi
0x180062df3  xor     ebp, ebp
0x180062df5  mov     [rax+8], rsi
0x180062df9  mov     r15d, r8d
0x180062dfc  mov     r13, r9
0x180062dff  lea     r8, Class
0x180062e06  mov     r12, rdx
0x180062e09  mov     r14, rcx
0x180062e0c  test    rcx, rcx
0x180062e0f  jz      loc_180062EFF
0x180062e15  cmp     [rcx+0Ch], esi
0x180062e18  jz      short loc_180062E83
0x180062e1a  lea     rcx, [rax+8]; void **
0x180062e1e  call    ?ImpersonateClient@@YAJPEAPEAX@Z; ImpersonateClient(void * *)
0x180062e23  mov     ebx, eax
0x180062e25  test    eax, eax
0x180062e27  jz      short loc_180062E76
0x180062e29  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180062e30  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180062e35  mov     r9, rax
0x180062e38  lea     r15, Class
0x180062e3f  lea     rax, aImpersonatecli; "ImpersonateClient"
0x180062e46  mov     [rsp+0A8h+var_78], r15
0x180062e4b  mov     [rsp+0A8h+var_80], rax
0x180062e50  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180062e57  mov     r8d, ebx
0x180062e5a  mov     dword ptr [rsp+0A8h+var_88], 24Ch
0x180062e62  xor     ecx, ecx
0x180062e64  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180062e69  mov     rsi, [rsp+0A8h+hObject]
0x180062e71  jmp     loc_18006304E
0x180062e76  mov     rsi, [rsp+0A8h+hObject]
0x180062e7e  mov     edi, 1
0x180062e83  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180062e8a  mov     edx, [r14+8]
0x180062e8e  mov     rcx, [r14]
0x180062e91  mov     rax, [rax+168h]
0x180062e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062e9d  mov     r9d, [r14+8]; unsigned int
0x180062ea1  mov     edx, r15d; unsigned int
0x180062ea4  mov     r8, [r14]; unsigned __int8 *
0x180062ea7  mov     rcx, r12; hObject
0x180062eaa  mov     ebp, 1
0x180062eaf  call    ?SetScardPin@@YAJ_KKPEAEK@Z; SetScardPin(unsigned __int64,ulong,uchar *,ulong)
0x180062eb4  mov     ebx, eax
0x180062eb6  test    eax, eax
0x180062eb8  jz      short loc_180062F38
0x180062eba  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180062ec1  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180062ec6  mov     r9, rax
0x180062ec9  lea     r15, Class
0x180062ed0  mov     [rsp+0A8h+var_78], r15
0x180062ed5  lea     rax, aSetscardpin; "SetScardPin"
0x180062edc  mov     [rsp+0A8h+var_80], rax
0x180062ee1  mov     dword ptr [rsp+0A8h+var_88], 25Ch
0x180062ee9  mov     r8d, ebx
0x180062eec  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180062ef3  xor     ecx, ecx
0x180062ef5  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180062efa  jmp     loc_180062FE8
0x180062eff  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180062f06  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180062f0b  mov     [rsp+0A8h+var_78], r8
0x180062f10  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180062f17  mov     r9, rax
0x180062f1a  xor     r8d, r8d
0x180062f1d  lea     rax, aNoPinWasProvid; "No PIN was provided for ScHelperEncrypt"...
0x180062f24  xor     ecx, ecx
0x180062f26  mov     [rsp+0A8h+var_80], rax
0x180062f2b  mov     dword ptr [rsp+0A8h+var_88], 260h
0x180062f33  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180062f38  mov     rax, [rsp+0A8h+arg_58]
0x180062f40  mov     r8, r13
0x180062f43  mov     r9, [rsp+0A8h+arg_20]
0x180062f4b  mov     edx, r15d
0x180062f4e  mov     [rsp+0A8h+var_58], rax; __int64
0x180062f53  mov     rcx, r12; void *
0x180062f56  mov     rax, [rsp+0A8h+arg_50]
0x180062f5e  mov     [rsp+0A8h+var_60], rax; __int64
0x180062f63  mov     eax, dword ptr [rsp+0A8h+arg_48]
0x180062f6a  mov     dword ptr [rsp+0A8h+var_68], eax; size_t
0x180062f6e  mov     rax, [rsp+0A8h+arg_40]
0x180062f76  mov     [rsp+0A8h+var_70], rax; __int64
0x180062f7b  mov     rax, [rsp+0A8h+arg_38]
0x180062f83  mov     [rsp+0A8h+var_78], rax; __int64
0x180062f88  mov     rax, [rsp+0A8h+arg_30]
0x180062f90  mov     [rsp+0A8h+var_80], rax; __int64
0x180062f95  mov     rax, [rsp+0A8h+arg_28]
0x180062f9d  mov     [rsp+0A8h+var_88], rax; __int64
0x180062fa2  call    ScHelperEncryptCredentials
0x180062fa7  mov     ebx, eax
0x180062fa9  test    eax, eax
0x180062fab  jz      short loc_180062FE1
0x180062fad  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180062fb4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180062fb9  mov     r9, rax
0x180062fbc  lea     r15, Class
0x180062fc3  mov     [rsp+0A8h+var_78], r15
0x180062fc8  lea     rax, aSchelperencryp_0; "ScHelperEncryptCredentials"
0x180062fcf  mov     [rsp+0A8h+var_80], rax
0x180062fd4  mov     dword ptr [rsp+0A8h+var_88], 26Fh
0x180062fdc  jmp     loc_180062EE9
0x180062fe1  lea     r15, Class
0x180062fe8  test    edi, edi
0x180062fea  jz      short loc_18006304E
0x180062fec  mov     rdx, rsi; Token
0x180062fef  xor     ecx, ecx; Thread
0x180062ff1  call    cs:__imp_SetThreadToken
0x180062ff7  test    eax, eax
0x180062ff9  jnz     short loc_18006304E
0x180062ffb  call    cs:__imp_GetLastError
0x180063001  mov     edi, eax
0x180063003  test    eax, eax
0x180063005  jle     short loc_180063010
0x180063007  movzx   edi, ax
0x18006300a  or      edi, 0C0070000h
0x180063010  lea     rcx, aOnecoreDsExtCl_0; "onecore\\ds\\ext\\cloudap\\libs\\scardu"...
0x180063017  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18006301c  mov     r9, rax
0x18006301f  mov     [rsp+0A8h+var_78], r15
0x180063024  lea     rax, aSetthreadtoken; "SetThreadToken"
0x18006302b  mov     r8d, edi
0x18006302e  mov     [rsp+0A8h+var_80], rax
0x180063033  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18006303a  xor     ecx, ecx
0x18006303c  mov     dword ptr [rsp+0A8h+var_88], 279h
0x180063044  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180063049  test    ebx, ebx
0x18006304b  cmovns  ebx, edi
0x18006304e  test    rsi, rsi
0x180063051  jz      short loc_18006305C
0x180063053  mov     rcx, rsi; hObject
0x180063056  call    cs:__imp_CloseHandle
0x18006305c  test    ebp, ebp
0x18006305e  jz      short loc_18006307A
0x180063060  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180063067  mov     edx, [r14+8]
0x18006306b  mov     rcx, [r14]
0x18006306e  mov     rax, [rax+160h]
0x180063075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006307a  mov     eax, ebx
0x18006307c  add     rsp, 68h
0x180063080  pop     r15
0x180063082  pop     r14
0x180063084  pop     r13
0x180063086  pop     r12
0x180063088  pop     rdi
0x180063089  pop     rsi
0x18006308a  pop     rbp
0x18006308b  pop     rbx
0x18006308c  retn
```
