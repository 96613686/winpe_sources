# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x140036610`
- end: `0x1400367c7`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `439`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400363c4`
- `0x14012d330`

## callees

- `0x140036610`
- `0x1400367d0`
- `0x140036960`
- `0x140037670`
- `0x140061fb0`
- `0x1400936ec`
- `0x1400954e0`
- `0x14012d3ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003665d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003665d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003663c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14003663c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140036653`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140036653`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140036693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036797`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036713`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140036797`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  void *v6; // rdx
  signed int LastError; // edi
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  void *v13; // rcx
  LPVOID v14; // rbx
  unsigned int AppUserModelId; // eax
  bool *v17; // [rsp+20h] [rbp-20h]
  unsigned __int16 *v18; // [rsp+20h] [rbp-20h]
  unsigned int v19; // [rsp+20h] [rbp-20h]
  PVOID P[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  void *TokenHandle; // [rsp+60h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+28h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v8 = -4;
    TokenHandle = (void *)-4LL;
  }
  else
  {
    if ( !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_8;
    }
    v8 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open(
                (HANDLE)v8,
                P,
                (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
                v5,
                v17);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError != -2147023728 && LastError != -2147024891 )
  {
    if ( LastError >= 0 )
    {
      LODWORD(TokenHandle) = 0;
      if ( (unsigned int)ARI::ProcessToken::SysAppId::GetAppUserModelId(
                           (ARI::ProcessToken::SysAppId *)P[1],
                           0,
                           (unsigned int)&TokenHandle,
                           0,
                           (unsigned __int16 *)v17) == 122 )
      {
        pv = 0;
        CoTaskMemFree(0);
        v12 = _AllocStringWorker<CTCoAllocPolicy>(v11, v10, 0, (_DWORD)TokenHandle, (_DWORD)v17, (__int64)&pv);
        LastError = v12;
        if ( v12 >= 0 )
        {
          v14 = pv;
          AppUserModelId = ARI::ProcessToken::SysAppId::GetAppUserModelId(
                             (ARI::ProcessToken::SysAppId *)P[1],
                             (const struct _TOKEN_SECURITY_ATTRIBUTE_V1 *)(unsigned int)TokenHandle,
                             (unsigned int)&TokenHandle,
                             (unsigned int *)pv,
                             v18);
          if ( !AppUserModelId )
          {
            *a2 = v14;
            CoTaskMemFree(0);
            LastError = 0;
            goto LABEL_23;
          }
          LastError = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0xAC,
                        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
                        (const char *)AppUserModelId,
                        v19);
          v13 = v14;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
            (const char *)(unsigned int)v12,
            (int)v18);
          v13 = pv;
        }
        CoTaskMemFree(v13);
LABEL_23:
        ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)P);
        return (unsigned int)LastError;
      }
      LastError = -2147418113;
      v9 = 168;
    }
    else
    {
      v9 = 165;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)v17);
    goto LABEL_23;
  }
  if ( P[0] )
    ARI::Free(P[0], v6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140036610  mov     [rsp-18h+arg_10], rbx
0x140036615  push    rbp
0x140036616  push    rsi
0x140036617  push    rdi
0x140036618  mov     rbp, rsp
0x14003661b  sub     rsp, 40h
0x14003661f  xorps   xmm0, xmm0
0x140036622  mov     qword ptr [rdx], 0
0x140036629  movdqu  xmmword ptr [rbp+P], xmm0
0x14003662e  mov     rsi, rdx
0x140036631  mov     [rbp+TokenHandle], 0
0x140036639  mov     rbx, rcx
0x14003663c  call    cs:__imp_GetCurrentProcess
0x140036642  cmp     rbx, rax
0x140036645  jz      short loc_14003666F
0x140036647  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14003664b  mov     edx, 8; DesiredAccess
0x140036650  mov     rcx, rbx; ProcessHandle
0x140036653  call    cs:__imp_OpenProcessToken
0x140036659  test    eax, eax
0x14003665b  jnz     short loc_140036669
0x14003665d  call    cs:__imp_GetLastError
0x140036663  mov     edi, eax
0x140036665  test    eax, eax
0x140036667  jnz     short loc_140036699
0x140036669  mov     rcx, [rbp+TokenHandle]
0x14003666d  jmp     short loc_14003667A
0x14003666f  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x140036676  mov     [rbp+TokenHandle], rcx
0x14003667a  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x14003667e  lea     rdx, [rbp+P]; void *
0x140036682  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x140036687  mov     rcx, [rbp+TokenHandle]; hObject
0x14003668b  mov     edi, eax
0x14003668d  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x140036691  jz      short loc_140036699
0x140036693  call    cs:__imp_CloseHandle
0x140036699  test    edi, edi
0x14003669b  jle     short loc_1400366A6
0x14003669d  movzx   edi, di
0x1400366a0  or      edi, 80070000h
0x1400366a6  cmp     edi, 80070490h
0x1400366ac  jz      loc_1400367AA
0x1400366b2  cmp     edi, 80070005h
0x1400366b8  jz      loc_1400367AA
0x1400366be  test    edi, edi
0x1400366c0  jns     short loc_1400366C9
0x1400366c2  mov     edx, 0A5h
0x1400366c7  jmp     short loc_1400366F1
0x1400366c9  mov     rcx, [rbp+P+8]; this
0x1400366cd  lea     r8, [rbp+TokenHandle]; unsigned int
0x1400366d1  xor     r9d, r9d; unsigned int *
0x1400366d4  mov     dword ptr [rbp+TokenHandle], 0
0x1400366db  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x1400366dd  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x1400366e2  cmp     eax, 7Ah ; 'z'
0x1400366e5  jz      short loc_140036709
0x1400366e7  mov     edi, 8000FFFFh
0x1400366ec  mov     edx, 0A8h; void *
0x1400366f1  mov     rcx, [rbp+18h]; this
0x1400366f5  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1400366fc  mov     r9d, edi; char *
0x1400366ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140036704  jmp     loc_14003679F
0x140036709  xor     ecx, ecx; pv
0x14003670b  mov     [rbp+pv], 0
0x140036713  call    cs:__imp_CoTaskMemFree
0x140036719  mov     r9d, dword ptr [rbp+TokenHandle]
0x14003671d  lea     rax, [rbp+pv]
0x140036721  xor     r8d, r8d
0x140036724  mov     [rsp+40h+var_18], rax
0x140036729  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x14003672e  mov     edi, eax
0x140036730  test    eax, eax
0x140036732  jns     short loc_140036758
0x140036734  mov     rcx, [rbp+18h]; this
0x140036738  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14003673f  mov     r9d, eax; char *
0x140036742  mov     edx, 0ABh; void *
0x140036747  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003674c  mov     rcx, [rbp+pv]; pv
0x140036750  call    cs:__imp_CoTaskMemFree
0x140036756  jmp     short loc_14003679F
0x140036758  mov     rbx, [rbp+pv]
0x14003675c  lea     r8, [rbp+TokenHandle]; unsigned int
0x140036760  mov     edx, dword ptr [rbp+TokenHandle]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x140036763  mov     r9, rbx; unsigned int *
0x140036766  mov     rcx, [rbp+P+8]; this
0x14003676a  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x14003676f  test    eax, eax
0x140036771  jz      short loc_140036792
0x140036773  mov     rcx, [rbp+18h]; this
0x140036777  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x14003677e  mov     r9d, eax; char *
0x140036781  mov     edx, 0ACh; void *
0x140036786  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14003678b  mov     edi, eax
0x14003678d  mov     rcx, rbx
0x140036790  jmp     short loc_140036750
0x140036792  xor     ecx, ecx; pv
0x140036794  mov     [rsi], rbx
0x140036797  call    cs:__imp_CoTaskMemFree
0x14003679d  xor     edi, edi
0x14003679f  lea     rcx, [rbp+P]; this
0x1400367a3  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x1400367a8  jmp     short loc_1400367B8
0x1400367aa  mov     rcx, [rbp+P]; P
0x1400367ae  test    rcx, rcx
0x1400367b1  jz      short loc_1400367B8
0x1400367b3  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1400367b8  mov     rbx, [rsp+40h+arg_10]
0x1400367bd  mov     eax, edi
0x1400367bf  add     rsp, 40h
0x1400367c3  pop     rdi
0x1400367c4  pop     rsi
0x1400367c5  pop     rbp
0x1400367c6  retn
```
