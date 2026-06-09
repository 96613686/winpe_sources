# DPAPICryptUnprotectDataEx(void *,ulong,void *,ulong,void *,void *,ulong,uchar *,ulong,_UNICODE_STRING *,void * *,ulong *)

- ea: `0x18000d540`
- end: `0x18000d9de`
- name: `?DPAPICryptUnprotectDataEx@@YAEPEAXK0K00KPEAEKPEAU_UNICODE_STRING@@PEAPEAXPEAK@Z`
- size: `1182`
- prototype: `bool __fastcall(char *Src, size_t Size, unsigned __int8 *, ULONG, unsigned __int16 **, unsigned int *, signed int, unsigned __int8 *, ULONG, PUNICODE_STRING DestinationString, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d4c0`

## callees

- `0x180007f10`
- `0x1800097f0`
- `0x18000d540`
- `0x180016370`
- `0x18001d810`
- `0x18001e1b4`
- `0x18001eb8c`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x18000d65d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18000d65d`
- `RPCRT4!RpcImpersonateClient` at `0x18000d8d4`
- `RPCRT4!RpcImpersonateClient` at `0x18000d8d4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d675`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000d675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d89c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d602`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d99d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d602`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d99d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d82f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d888`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d82f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000d888`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d92e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d92e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d943`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d711`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d711`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d960`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d975`
- `ntdll!RtlInitUnicodeString` at `0x18000d7dc`
- `ntdll!RtlInitUnicodeString` at `0x18000d7dc`

## string_xrefs

- `0x18000d615`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000d72a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000d7b8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x18000d80c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
bool __fastcall DPAPICryptUnprotectDataEx(
        char *Src,
        size_t Size,
        unsigned __int8 *a3,
        ULONG a4,
        unsigned __int16 **a5,
        unsigned int *a6,
        signed int a7,
        unsigned __int8 *a8,
        ULONG a9,
        PUNICODE_STRING DestinationString,
        unsigned __int8 **a11,
        unsigned int *a12)
{
  SIZE_T v13; // r13
  DWORD v15; // eax
  DWORD LastError; // eax
  __int64 v17; // r9
  DWORD v18; // ebx
  int v19; // eax
  SIZE_T v20; // rdi
  unsigned __int8 *v21; // rax
  unsigned __int8 *v22; // rsi
  unsigned __int16 **p_SourceString; // r10
  DWORD v24; // eax
  unsigned __int8 *v25; // rax
  char v26; // al
  char v27; // al
  RPC_STATUS v28; // eax
  PCWSTR SourceString; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 *v31; // [rsp+70h] [rbp-90h]
  unsigned __int8 *v32; // [rsp+78h] [rbp-88h]
  unsigned int *v33; // [rsp+80h] [rbp-80h]
  int v34; // [rsp+90h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE BindingHandle; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+A0h] [rbp-60h]
  int v37; // [rsp+A4h] [rbp-5Ch]
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  HANDLE Token; // [rsp+B0h] [rbp-50h]
  HLOCAL v40; // [rsp+B8h] [rbp-48h]
  HLOCAL hMem; // [rsp+D8h] [rbp-28h]

  v32 = a3;
  v13 = (unsigned int)Size;
  v31 = a8;
  v33 = a12;
  memset_0(&v34, 0, 0x270u);
  SourceString = 0;
  if ( !g_fDPAPIInitialized )
  {
    SetLastError(0x54Fu);
    return 0;
  }
  v15 = CPSCreateServerContext((struct CRYPT_SERVER_CONTEXT *)&v34, 0, (const unsigned __int16 **)a5, a6);
  if ( v15 )
  {
    SetLastError(v15);
    return 0;
  }
  if ( !a11 || !Src || (unsigned int)v13 < 0x34 )
    goto LABEL_37;
  if ( !v37 || v34 != 624 )
    goto LABEL_18;
  if ( v36 || hObject )
  {
    if ( RevertToSelf() )
      goto LABEL_18;
    LastError = GetLastError();
    v17 = 858;
    goto LABEL_17;
  }
  if ( BindingHandle )
  {
    LastError = RpcRevertToSelfEx(BindingHandle);
    if ( LastError )
    {
      v17 = 872;
LABEL_17:
      DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", v17);
    }
  }
LABEL_18:
  *a11 = 0;
  *a12 = 0;
  if ( *(_DWORD *)Src == 1 )
  {
    if ( a7 < 0 )
      goto LABEL_26;
    v19 = *((_DWORD *)Src + 10);
    if ( (v19 & 3) == 0 && (v19 & 8) == 0 )
    {
      if ( *(_QWORD *)(Src + 4) != *(_QWORD *)&g_guidDefaultProvider.Data1
        || *(_QWORD *)(Src + 12) != *(_QWORD *)g_guidDefaultProvider.Data4 )
      {
        v18 = 13;
        goto LABEL_38;
      }
LABEL_26:
      v20 = v13;
      v21 = (unsigned __int8 *)LocalAlloc(0, v13);
      v22 = v21;
      if ( v21 )
      {
        memcpy_0(v21, Src, v13);
        p_SourceString = (unsigned __int16 **)&SourceString;
        if ( !DestinationString )
          p_SourceString = 0;
        v24 = SPCryptUnprotect(
                &v34,
                a11,
                (UUID *)v33,
                v22 + 20,
                (int)v13 - 20,
                p_SourceString,
                v32,
                a4,
                0,
                a7 | 0x40000000u,
                v31,
                a9);
        v18 = v24;
        if ( v24 )
        {
          DebugTraceError(v24, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp", 2480);
        }
        else if ( DestinationString )
        {
          RtlInitUnicodeString(DestinationString, SourceString);
        }
        v25 = v22;
        do
        {
          *v25++ = 0;
          --v20;
        }
        while ( v20 );
        LocalFree(v22);
      }
      else
      {
        v18 = 14;
      }
      goto LABEL_38;
    }
LABEL_37:
    v18 = 87;
    goto LABEL_38;
  }
  v18 = 13;
LABEL_38:
  if ( v37 )
  {
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
      {
        v26 = GetLastError();
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            v26,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            224);
      }
    }
    else if ( hObject )
    {
      if ( !SetThreadToken(0, hObject) )
      {
        v27 = GetLastError();
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            v27,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            240);
      }
    }
    else if ( BindingHandle )
    {
      v28 = RpcImpersonateClient(BindingHandle);
      if ( v28 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            (unsigned int)&WPP_GLOBAL_Control,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            v28,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
            0);
      }
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v40 )
  {
    LocalFree(v40);
    v40 = 0;
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( Token )
    CloseHandle(Token);
  if ( v34 == 624 )
    memset_0(&v34, 0, 0x270u);
  SetLastError(v18);
  return !v18 || v18 == 593938;
}

```

## disassembly

```asm
0x18000d540  push    rbp
0x18000d542  push    rbx
0x18000d543  push    rsi
0x18000d544  push    rdi
0x18000d545  push    r12
0x18000d547  push    r13
0x18000d549  push    r14
0x18000d54b  push    r15
0x18000d54d  lea     rbp, [rsp-218h]
0x18000d555  sub     rsp, 318h
0x18000d55c  mov     rax, cs:__security_cookie
0x18000d563  xor     rax, rsp
0x18000d566  mov     [rbp+250h+var_50], rax
0x18000d56d  mov     rax, [rbp+250h+arg_38]
0x18000d574  mov     rbx, rcx
0x18000d577  mov     r14, [rbp+250h+arg_58]
0x18000d57e  lea     rcx, [rbp+250h+var_2C0]; void *
0x18000d582  mov     rdi, [rbp+250h+arg_20]
0x18000d589  mov     rsi, [rbp+250h+arg_28]
0x18000d590  mov     r15, [rbp+250h+DestinationString]
0x18000d597  mov     r12, [rbp+250h+arg_50]
0x18000d59e  mov     [rsp+350h+var_2D8], r8
0x18000d5a3  mov     r8d, 270h; Size
0x18000d5a9  mov     r13d, edx
0x18000d5ac  xor     edx, edx; Val
0x18000d5ae  mov     [rsp+350h+var_2E0], rax
0x18000d5b3  mov     [rbp+250h+var_2D0], r14
0x18000d5b7  mov     [rsp+350h+var_2F0], r9d
0x18000d5bc  call    memset_0
0x18000d5c1  cmp     cs:?g_fDPAPIInitialized@@3HA, 0; int g_fDPAPIInitialized
0x18000d5c8  mov     [rsp+350h+SourceString], 0
0x18000d5d1  jnz     short loc_18000D5EB
0x18000d5d3  mov     ecx, 54Fh; dwErrCode
0x18000d5d8  call    cs:__imp_SetLastError
0x18000d5df  nop     dword ptr [rax+rax+00h]
0x18000d5e4  xor     al, al
0x18000d5e6  jmp     loc_18000D9BA
0x18000d5eb  mov     r9, rsi; unsigned int *
0x18000d5ee  lea     rcx, [rbp+250h+var_2C0]; struct CRYPT_SERVER_CONTEXT *
0x18000d5f2  mov     r8, rdi; unsigned __int16 **
0x18000d5f5  xor     edx, edx; void *
0x18000d5f7  call    ?CPSCreateServerContext@@YAKPEAUCRYPT_SERVER_CONTEXT@@PEAXPEAPEBGPEAK@Z; CPSCreateServerContext(CRYPT_SERVER_CONTEXT *,void *,ushort const * *,ulong *)
0x18000d5fc  test    eax, eax
0x18000d5fe  jz      short loc_18000D615
0x18000d600  mov     ecx, eax; dwErrCode
0x18000d602  call    cs:__imp_SetLastError
0x18000d609  nop     dword ptr [rax+rax+00h]
0x18000d60e  xor     al, al
0x18000d610  jmp     loc_18000D9BA
0x18000d615  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000d61c  test    r12, r12
0x18000d61f  jz      loc_18000D815
0x18000d625  test    rbx, rbx
0x18000d628  jz      loc_18000D815
0x18000d62e  cmp     r13d, 34h ; '4'
0x18000d632  jb      loc_18000D815
0x18000d638  cmp     [rbp+250h+var_2AC], 0
0x18000d63c  jz      short loc_18000D6A8
0x18000d63e  cmp     [rbp+250h+var_2C0], 270h
0x18000d645  jnz     short loc_18000D6A8
0x18000d647  cmp     [rbp+250h+var_2B0], 0
0x18000d64b  jnz     short loc_18000D675
0x18000d64d  cmp     [rbp+250h+hObject], 0
0x18000d652  jnz     short loc_18000D675
0x18000d654  mov     rcx, [rbp+250h+BindingHandle]; BindingHandle
0x18000d658  test    rcx, rcx
0x18000d65b  jz      short loc_18000D6A8
0x18000d65d  call    cs:__imp_RpcRevertToSelfEx
0x18000d664  nop     dword ptr [rax+rax+00h]
0x18000d669  test    eax, eax
0x18000d66b  jz      short loc_18000D6A8
0x18000d66d  mov     r9d, 368h
0x18000d673  jmp     short loc_18000D697
0x18000d675  call    cs:__imp_RevertToSelf
0x18000d67c  nop     dword ptr [rax+rax+00h]
0x18000d681  test    eax, eax
0x18000d683  jnz     short loc_18000D6A8
0x18000d685  call    cs:__imp_GetLastError
0x18000d68c  nop     dword ptr [rax+rax+00h]
0x18000d691  mov     r9d, 35Ah
0x18000d697  mov     r8, rdi
0x18000d69a  lea     rdx, aDwlasterror; "dwLastError"
0x18000d6a1  mov     ecx, eax
0x18000d6a3  call    DebugTraceError
0x18000d6a8  mov     qword ptr [r12], 0
0x18000d6b0  mov     dword ptr [r14], 0
0x18000d6b7  cmp     dword ptr [rbx], 1
0x18000d6ba  jz      short loc_18000D6C6
0x18000d6bc  mov     ebx, 0Dh
0x18000d6c1  jmp     loc_18000D81A
0x18000d6c6  mov     r14d, [rbp+250h+arg_30]
0x18000d6cd  test    r14d, r14d
0x18000d6d0  js      short loc_18000D709
0x18000d6d2  mov     eax, [rbx+28h]
0x18000d6d5  test    al, 3
0x18000d6d7  jnz     loc_18000D815
0x18000d6dd  test    al, 8
0x18000d6df  jnz     loc_18000D815
0x18000d6e5  mov     rax, [rbx+4]
0x18000d6e9  cmp     rax, qword ptr cs:?g_guidDefaultProvider@@3U_GUID@@A.Data1; _GUID g_guidDefaultProvider ...
0x18000d6f0  jnz     short loc_18000D6FF
0x18000d6f2  mov     rax, [rbx+0Ch]
0x18000d6f6  cmp     rax, qword ptr cs:?g_guidDefaultProvider@@3U_GUID@@A.Data4; _GUID g_guidDefaultProvider ...
0x18000d6fd  jz      short loc_18000D709
0x18000d6ff  mov     ebx, 0Dh
0x18000d704  jmp     loc_18000D81A
0x18000d709  mov     rdx, r13; uBytes
0x18000d70c  xor     ecx, ecx; uFlags
0x18000d70e  mov     rdi, r13
0x18000d711  call    cs:__imp_LocalAlloc
0x18000d718  nop     dword ptr [rax+rax+00h]
0x18000d71d  mov     rsi, rax
0x18000d720  test    rax, rax
0x18000d723  jnz     short loc_18000D736
0x18000d725  mov     ebx, 0Eh
0x18000d72a  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000d731  jmp     loc_18000D81A
0x18000d736  mov     r8, r13; Size
0x18000d739  mov     rdx, rbx; Src
0x18000d73c  mov     rcx, rsi; void *
0x18000d73f  call    memcpy_0
0x18000d744  mov     r8, [rbp+250h+var_2D0]; unsigned int *
0x18000d748  lea     ecx, [r13-14h]
0x18000d74c  xor     eax, eax
0x18000d74e  lea     r10, [rsp+350h+SourceString]
0x18000d753  bts     r14d, 1Eh
0x18000d758  lea     r9, [rsi+14h]; unsigned __int8 *
0x18000d75c  test    r15, r15
0x18000d75f  mov     rdx, r12; unsigned __int8 **
0x18000d762  cmovz   r10, rax
0x18000d766  mov     eax, [rbp+250h+arg_40]
0x18000d76c  mov     [rsp+350h+var_2F8], eax; ULONG
0x18000d770  mov     rax, [rsp+350h+var_2E0]
0x18000d775  mov     [rsp+350h+var_300], rax; unsigned __int8 *
0x18000d77a  mov     eax, [rsp+350h+var_2F0]
0x18000d77e  mov     [rsp+350h+var_308], r14d; unsigned int
0x18000d783  mov     [rsp+350h+var_310], 0; struct _SSCRYPTPROTECTDATA_PROMPTSTRUCT *
0x18000d78c  mov     [rsp+350h+cbInput], eax; cbInput
0x18000d790  mov     rax, [rsp+350h+var_2D8]
0x18000d795  mov     [rsp+350h+var_320], rax; unsigned __int8 *
0x18000d79a  mov     [rsp+350h+var_328], r10; unsigned __int16 **
0x18000d79f  mov     [rsp+350h+var_330], ecx; unsigned int
0x18000d7a3  lea     rcx, [rbp+250h+var_2C0]; void *
0x18000d7a7  call    ?SPCryptUnprotect@@YAKPEAXPEAPEAEPEAKPEAEKPEAPEAG3KPEAU_SSCRYPTPROTECTDATA_PROMPTSTRUCT@@K3K@Z; SPCryptUnprotect(void *,uchar * *,ulong *,uchar *,ulong,ushort * *,uchar *,ulong,_SSCRYPTPROTECTDATA_PROMPTSTRUCT *,ulong,uchar *,ulong)
0x18000d7ac  mov     ebx, eax
0x18000d7ae  test    eax, eax
0x18000d7b0  jz      short loc_18000D7CF
0x18000d7b2  mov     r9d, 9B0h
0x18000d7b8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000d7bf  lea     rdx, aDwretval; "dwRetVal"
0x18000d7c6  mov     ecx, eax
0x18000d7c8  call    DebugTraceError
0x18000d7cd  jmp     short loc_18000D7E8
0x18000d7cf  test    r15, r15
0x18000d7d2  jz      short loc_18000D7E8
0x18000d7d4  mov     rdx, [rsp+350h+SourceString]; SourceString
0x18000d7d9  mov     rcx, r15; DestinationString
0x18000d7dc  call    cs:__imp_RtlInitUnicodeString
0x18000d7e3  nop     dword ptr [rax+rax+00h]
0x18000d7e8  mov     rax, rsi
0x18000d7eb  test    r13d, r13d
0x18000d7ee  jz      short loc_18000D7FD
0x18000d7f0  mov     byte ptr [rax], 0
0x18000d7f3  lea     rax, [rax+1]
0x18000d7f7  sub     rdi, 1
0x18000d7fb  jnz     short loc_18000D7F0
0x18000d7fd  mov     rcx, rsi; hMem
0x18000d800  call    cs:__imp_LocalFree
0x18000d807  nop     dword ptr [rax+rax+00h]
0x18000d80c  lea     rdi, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000d813  jmp     short loc_18000D81A
0x18000d815  mov     ebx, 57h ; 'W'
0x18000d81a  cmp     [rbp+250h+var_2AC], 0
0x18000d81e  jz      loc_18000D925
0x18000d824  mov     rdx, [rbp+250h+Token]; Token
0x18000d828  test    rdx, rdx
0x18000d82b  jz      short loc_18000D87D
0x18000d82d  xor     ecx, ecx; Thread
0x18000d82f  call    cs:__imp_SetThreadToken
0x18000d836  nop     dword ptr [rax+rax+00h]
0x18000d83b  test    eax, eax
0x18000d83d  jnz     loc_18000D925
0x18000d843  call    cs:__imp_GetLastError
0x18000d84a  nop     dword ptr [rax+rax+00h]
0x18000d84f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d856  lea     rdx, WPP_GLOBAL_Control
0x18000d85d  cmp     rcx, rdx
0x18000d860  jz      loc_18000D925
0x18000d866  test    byte ptr [rcx+1Ch], 1
0x18000d86a  jz      loc_18000D925
0x18000d870  mov     dword ptr [rsp+350h+var_320], 2E0h
0x18000d878  jmp     loc_18000D905
0x18000d87d  mov     rdx, [rbp+250h+hObject]; Token
0x18000d881  test    rdx, rdx
0x18000d884  jz      short loc_18000D8CB
0x18000d886  xor     ecx, ecx; Thread
0x18000d888  call    cs:__imp_SetThreadToken
0x18000d88f  nop     dword ptr [rax+rax+00h]
0x18000d894  test    eax, eax
0x18000d896  jnz     loc_18000D925
0x18000d89c  call    cs:__imp_GetLastError
0x18000d8a3  nop     dword ptr [rax+rax+00h]
0x18000d8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8af  lea     rdx, WPP_GLOBAL_Control
0x18000d8b6  cmp     rcx, rdx
0x18000d8b9  jz      short loc_18000D925
0x18000d8bb  test    byte ptr [rcx+1Ch], 1
0x18000d8bf  jz      short loc_18000D925
0x18000d8c1  mov     dword ptr [rsp+350h+var_320], 2F0h
0x18000d8c9  jmp     short loc_18000D905
0x18000d8cb  mov     rcx, [rbp+250h+BindingHandle]; BindingHandle
0x18000d8cf  test    rcx, rcx
0x18000d8d2  jz      short loc_18000D925
0x18000d8d4  call    cs:__imp_RpcImpersonateClient
0x18000d8db  nop     dword ptr [rax+rax+00h]
0x18000d8e0  test    eax, eax
0x18000d8e2  jz      short loc_18000D925
0x18000d8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8eb  lea     rdx, WPP_GLOBAL_Control
0x18000d8f2  cmp     rcx, rdx
0x18000d8f5  jz      short loc_18000D925
0x18000d8f7  test    byte ptr [rcx+1Ch], 1
0x18000d8fb  jz      short loc_18000D925
0x18000d8fd  mov     dword ptr [rsp+350h+var_320], 300h
0x18000d905  mov     rcx, [rcx+10h]
0x18000d909  lea     r9, aDwlasterror; "dwLastError"
0x18000d910  mov     [rsp+350h+var_328], rdi
0x18000d915  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000d91c  mov     [rsp+350h+var_330], eax
0x18000d920  call    WPP_SF_sDsd
0x18000d925  mov     rcx, [rbp+250h+hMem]; hMem
0x18000d929  test    rcx, rcx
0x18000d92c  jz      short loc_18000D93A
0x18000d92e  call    cs:__imp_LocalFree
0x18000d935  nop     dword ptr [rax+rax+00h]
0x18000d93a  mov     rcx, [rbp+250h+var_298]; hMem
0x18000d93e  test    rcx, rcx
0x18000d941  jz      short loc_18000D957
0x18000d943  call    cs:__imp_LocalFree
0x18000d94a  nop     dword ptr [rax+rax+00h]
0x18000d94f  mov     [rbp+250h+var_298], 0
0x18000d957  mov     rcx, [rbp+250h+hObject]; hObject
0x18000d95b  test    rcx, rcx
0x18000d95e  jz      short loc_18000D96C
0x18000d960  call    cs:__imp_CloseHandle
0x18000d967  nop     dword ptr [rax+rax+00h]
0x18000d96c  mov     rcx, [rbp+250h+Token]; hObject
0x18000d970  test    rcx, rcx
0x18000d973  jz      short loc_18000D981
0x18000d975  call    cs:__imp_CloseHandle
0x18000d97c  nop     dword ptr [rax+rax+00h]
0x18000d981  cmp     [rbp+250h+var_2C0], 270h
0x18000d988  jnz     short loc_18000D99B
0x18000d98a  xor     edx, edx; Val
0x18000d98c  lea     rcx, [rbp+250h+var_2C0]; void *
0x18000d990  mov     r8d, 270h; Size
0x18000d996  call    memset_0
0x18000d99b  mov     ecx, ebx; dwErrCode
0x18000d99d  call    cs:__imp_SetLastError
0x18000d9a4  nop     dword ptr [rax+rax+00h]
0x18000d9a9  test    ebx, ebx
0x18000d9ab  jz      short loc_18000D9B8
0x18000d9ad  cmp     ebx, 91012h
0x18000d9b3  setz    al
0x18000d9b6  jmp     short loc_18000D9BA
0x18000d9b8  mov     al, 1
0x18000d9ba  mov     rcx, [rbp+250h+var_50]
0x18000d9c1  xor     rcx, rsp; StackCookie
0x18000d9c4  call    __security_check_cookie
0x18000d9c9  add     rsp, 318h
0x18000d9d0  pop     r15
0x18000d9d2  pop     r14
0x18000d9d4  pop     r13
0x18000d9d6  pop     r12
0x18000d9d8  pop     rdi
0x18000d9d9  pop     rsi
0x18000d9da  pop     rbx
0x18000d9db  pop     rbp
0x18000d9dc  retn
```
