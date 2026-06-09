# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x140028da8`
- end: `0x140028f8a`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `482`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002825c`
- `0x140138f34`

## callees

- `0x140028da8`
- `0x140028f90`
- `0x140029148`
- `0x140029ec8`
- `0x140065790`
- `0x140098dc4`
- `0x14009ac68`
- `0x140138ff8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028e01`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140028df1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140028df1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140028dd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140028dd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028e3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140028e3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028f53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028ec3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028f06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140028f53`

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
0x140028da8  mov     [rsp-18h+arg_10], rbx
0x140028dad  push    rbp
0x140028dae  push    rsi
0x140028daf  push    rdi
0x140028db0  mov     rbp, rsp
0x140028db3  sub     rsp, 40h
0x140028db7  xorps   xmm0, xmm0
0x140028dba  mov     qword ptr [rdx], 0
0x140028dc1  movdqu  xmmword ptr [rbp+P], xmm0
0x140028dc6  mov     rsi, rdx
0x140028dc9  mov     [rbp+TokenHandle], 0
0x140028dd1  mov     rbx, rcx
0x140028dd4  call    cs:__imp_GetCurrentProcess
0x140028ddb  nop     dword ptr [rax+rax+00h]
0x140028de0  cmp     rbx, rax
0x140028de3  jz      short loc_140028E19
0x140028de5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140028de9  mov     edx, 8; DesiredAccess
0x140028dee  mov     rcx, rbx; ProcessHandle
0x140028df1  call    cs:__imp_OpenProcessToken
0x140028df8  nop     dword ptr [rax+rax+00h]
0x140028dfd  test    eax, eax
0x140028dff  jnz     short loc_140028E13
0x140028e01  call    cs:__imp_GetLastError
0x140028e08  nop     dword ptr [rax+rax+00h]
0x140028e0d  mov     edi, eax
0x140028e0f  test    eax, eax
0x140028e11  jnz     short loc_140028E49
0x140028e13  mov     rcx, [rbp+TokenHandle]
0x140028e17  jmp     short loc_140028E24
0x140028e19  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x140028e20  mov     [rbp+TokenHandle], rcx
0x140028e24  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x140028e28  lea     rdx, [rbp+P]; void *
0x140028e2c  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x140028e31  mov     rcx, [rbp+TokenHandle]; hObject
0x140028e35  mov     edi, eax
0x140028e37  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x140028e3b  jz      short loc_140028E49
0x140028e3d  call    cs:__imp_CloseHandle
0x140028e44  nop     dword ptr [rax+rax+00h]
0x140028e49  test    edi, edi
0x140028e4b  jle     short loc_140028E56
0x140028e4d  movzx   edi, di
0x140028e50  or      edi, 80070000h
0x140028e56  cmp     edi, 80070490h
0x140028e5c  jz      loc_140028F6C
0x140028e62  cmp     edi, 80070005h
0x140028e68  jz      loc_140028F6C
0x140028e6e  test    edi, edi
0x140028e70  jns     short loc_140028E79
0x140028e72  mov     edx, 0A5h
0x140028e77  jmp     short loc_140028EA1
0x140028e79  mov     rcx, [rbp+P+8]; this
0x140028e7d  lea     r8, [rbp+TokenHandle]; unsigned int
0x140028e81  xor     r9d, r9d; unsigned int *
0x140028e84  mov     dword ptr [rbp+TokenHandle], 0
0x140028e8b  xor     edx, edx; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x140028e8d  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x140028e92  cmp     eax, 7Ah ; 'z'
0x140028e95  jz      short loc_140028EB9
0x140028e97  mov     edi, 8000FFFFh
0x140028e9c  mov     edx, 0A8h; void *
0x140028ea1  mov     rcx, [rbp+18h]; this
0x140028ea5  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140028eac  mov     r9d, edi; char *
0x140028eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140028eb4  jmp     loc_140028F61
0x140028eb9  xor     ecx, ecx; pv
0x140028ebb  mov     [rbp+pv], 0
0x140028ec3  call    cs:__imp_CoTaskMemFree
0x140028eca  nop     dword ptr [rax+rax+00h]
0x140028ecf  mov     r9d, dword ptr [rbp+TokenHandle]
0x140028ed3  lea     rax, [rbp+pv]
0x140028ed7  xor     r8d, r8d
0x140028eda  mov     [rsp+40h+var_18], rax
0x140028edf  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x140028ee4  mov     edi, eax
0x140028ee6  test    eax, eax
0x140028ee8  jns     short loc_140028F14
0x140028eea  mov     rcx, [rbp+18h]; this
0x140028eee  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140028ef5  mov     r9d, eax; char *
0x140028ef8  mov     edx, 0ABh; void *
0x140028efd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140028f02  mov     rcx, [rbp+pv]; pv
0x140028f06  call    cs:__imp_CoTaskMemFree
0x140028f0d  nop     dword ptr [rax+rax+00h]
0x140028f12  jmp     short loc_140028F61
0x140028f14  mov     rbx, [rbp+pv]
0x140028f18  lea     r8, [rbp+TokenHandle]; unsigned int
0x140028f1c  mov     edx, dword ptr [rbp+TokenHandle]; struct _TOKEN_SECURITY_ATTRIBUTE_V1 *
0x140028f1f  mov     r9, rbx; unsigned int *
0x140028f22  mov     rcx, [rbp+P+8]; this
0x140028f26  call    ?GetAppUserModelId@SysAppId@ProcessToken@ARI@@YAJPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@IPEAIPEAG@Z; ARI::ProcessToken::SysAppId::GetAppUserModelId(_TOKEN_SECURITY_ATTRIBUTE_V1 const *,uint,uint *,ushort *)
0x140028f2b  test    eax, eax
0x140028f2d  jz      short loc_140028F4E
0x140028f2f  mov     rcx, [rbp+18h]; this
0x140028f33  lea     r8, aOnecoreShellLi_0; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140028f3a  mov     r9d, eax; char *
0x140028f3d  mov     edx, 0ACh; void *
0x140028f42  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140028f47  mov     edi, eax
0x140028f49  mov     rcx, rbx
0x140028f4c  jmp     short loc_140028F06
0x140028f4e  xor     ecx, ecx; pv
0x140028f50  mov     [rsi], rbx
0x140028f53  call    cs:__imp_CoTaskMemFree
0x140028f5a  nop     dword ptr [rax+rax+00h]
0x140028f5f  xor     edi, edi
0x140028f61  lea     rcx, [rbp+P]; this
0x140028f65  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x140028f6a  jmp     short loc_140028F7A
0x140028f6c  mov     rcx, [rbp+P]; P
0x140028f70  test    rcx, rcx
0x140028f73  jz      short loc_140028F7A
0x140028f75  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x140028f7a  mov     rbx, [rsp+40h+arg_10]
0x140028f7f  mov     eax, edi
0x140028f81  add     rsp, 40h
0x140028f85  pop     rdi
0x140028f86  pop     rsi
0x140028f87  pop     rbp
0x140028f88  retn
```
