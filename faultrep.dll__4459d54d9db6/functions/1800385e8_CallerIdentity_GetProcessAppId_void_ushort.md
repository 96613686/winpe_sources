# CallerIdentity::GetProcessAppId(void *,ushort * *)

- ea: `0x1800385e8`
- end: `0x1800387e4`
- name: `?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `508`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, _QWORD *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027474`

## callees

- `0x18000e30c`
- `0x1800380f8`
- `0x180038204`
- `0x1800385e8`
- `0x180038a08`
- `0x180038bac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180038617`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003862e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038638`
- `ntdll!RtlFreeHeap` at `0x180038778`
- `ntdll!RtlFreeHeap` at `0x1800387a5`
- `ntdll!RtlFreeHeap` at `0x1800387cc`
- `ntdll!RtlFreeHeap` at `0x180038778`
- `ntdll!RtlFreeHeap` at `0x1800387a5`
- `ntdll!RtlFreeHeap` at `0x1800387cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003866e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003866e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003875a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038787`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800386f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003875a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038787`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetProcessAppId(HANDLE ProcessHandle, _QWORD *a2, unsigned __int16 **a3)
{
  const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **v5; // r9
  signed int LastError; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  PVOID v9; // r8
  const unsigned __int16 *v10; // rcx
  int v11; // eax
  void *v12; // rbx
  unsigned int AppUserModelId; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // edi
  PVOID P[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  void *TokenHandle; // [rsp+40h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp+18h] BYREF

  *a2 = 0;
  *(_OWORD *)P = 0;
  TokenHandle = 0;
  if ( ProcessHandle == GetCurrentProcess() )
  {
    v7 = -4;
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
    v7 = (__int64)TokenHandle;
  }
  LastError = ARI::ProcessToken::SysAppId::Open(
                (HANDLE)v7,
                P,
                (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **)&P[1],
                v5,
                (bool *)P[0]);
  if ( TokenHandle != (void *)-4LL )
    CloseHandle(TokenHandle);
LABEL_8:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023728 || LastError == -2147024891 )
  {
    v9 = P[0];
    if ( !P[0] )
      return (unsigned int)LastError;
LABEL_28:
    if ( v9 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    return (unsigned int)LastError;
  }
  if ( LastError < 0 )
  {
    v8 = 165;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)LastError,
      (int)P[0]);
LABEL_15:
    v9 = P[0];
    goto LABEL_28;
  }
  LODWORD(TokenHandle) = 0;
  if ( (unsigned int)ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                       (ARI::ProcessToken::AutoSysAppId *)P,
                       0,
                       (unsigned int *)&TokenHandle,
                       0) != 122 )
  {
    LastError = -2147418113;
    v8 = 168;
    goto LABEL_14;
  }
  pv = 0;
  CoTaskMemFree(0);
  v11 = CoAllocStringLen(v10, (unsigned int)TokenHandle, (unsigned __int16 **)&pv);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
      (const char *)(unsigned int)v11,
      (int)P[0]);
    CoTaskMemFree(pv);
    goto LABEL_15;
  }
  v12 = pv;
  AppUserModelId = ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(
                     (ARI::ProcessToken::AutoSysAppId *)P,
                     (unsigned int)TokenHandle,
                     (unsigned int *)&TokenHandle,
                     (unsigned __int16 *)pv);
  if ( AppUserModelId )
  {
    v16 = wil::details::in1diag3::Return_Win32(retaddr, v14, v15, (const char *)AppUserModelId, (unsigned int)P[0]);
    CoTaskMemFree(v12);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return v16;
  }
  else
  {
    *a2 = v12;
    CoTaskMemFree(0);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x1800385e8  mov     [rsp-8+arg_10], rbx
0x1800385ed  mov     [rsp-8+arg_18], rdi
0x1800385f2  push    rbp
0x1800385f3  mov     rbp, rsp
0x1800385f6  sub     rsp, 30h
0x1800385fa  xorps   xmm0, xmm0
0x1800385fd  mov     qword ptr [rdx], 0
0x180038604  movdqu  xmmword ptr [rbp+P], xmm0
0x180038609  mov     rdi, rdx
0x18003860c  mov     [rbp+TokenHandle], 0
0x180038614  mov     rbx, rcx
0x180038617  call    cs:__imp_GetCurrentProcess
0x18003861d  cmp     rbx, rax
0x180038620  jz      short loc_18003864A
0x180038622  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180038626  mov     edx, 8; DesiredAccess
0x18003862b  mov     rcx, rbx; ProcessHandle
0x18003862e  call    cs:__imp_OpenProcessToken
0x180038634  test    eax, eax
0x180038636  jnz     short loc_180038644
0x180038638  call    cs:__imp_GetLastError
0x18003863e  mov     ebx, eax
0x180038640  test    eax, eax
0x180038642  jnz     short loc_180038674
0x180038644  mov     rcx, [rbp+TokenHandle]
0x180038648  jmp     short loc_180038655
0x18003864a  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180038651  mov     [rbp+TokenHandle], rcx
0x180038655  lea     r8, [rbp+P+8]; struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **
0x180038659  lea     rdx, [rbp+P]; void *
0x18003865d  call    ?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z; ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)
0x180038662  mov     rcx, [rbp+TokenHandle]; hObject
0x180038666  mov     ebx, eax
0x180038668  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x18003866c  jz      short loc_180038674
0x18003866e  call    cs:__imp_CloseHandle
0x180038674  test    ebx, ebx
0x180038676  jle     short loc_180038681
0x180038678  movzx   ebx, bx
0x18003867b  or      ebx, 80070000h
0x180038681  cmp     ebx, 80070490h
0x180038687  jz      loc_1800387AF
0x18003868d  cmp     ebx, 80070005h
0x180038693  jz      loc_1800387AF
0x180038699  test    ebx, ebx
0x18003869b  jns     short loc_1800386BE
0x18003869d  mov     edx, 0A5h; void *
0x1800386a2  mov     rcx, [rbp+8]; this
0x1800386a6  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800386ad  mov     r9d, ebx; char *
0x1800386b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800386b5  mov     r8, [rbp+P]
0x1800386b9  jmp     loc_1800387B8
0x1800386be  xor     r9d, r9d; unsigned __int16 *
0x1800386c1  mov     dword ptr [rbp+TokenHandle], 0
0x1800386c8  lea     r8, [rbp+TokenHandle]; unsigned int *
0x1800386cc  xor     edx, edx; unsigned int
0x1800386ce  lea     rcx, [rbp+P]; this
0x1800386d2  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x1800386d7  cmp     eax, 7Ah ; 'z'
0x1800386da  jz      short loc_1800386E8
0x1800386dc  mov     ebx, 8000FFFFh
0x1800386e1  mov     edx, 0A8h
0x1800386e6  jmp     short loc_1800386A2
0x1800386e8  xor     ecx, ecx; pv
0x1800386ea  mov     [rbp+pv], 0
0x1800386f2  call    cs:__imp_CoTaskMemFree
0x1800386f8  mov     edx, dword ptr [rbp+TokenHandle]; unsigned __int64
0x1800386fb  lea     r8, [rbp+pv]; unsigned __int16 **
0x1800386ff  call    ?CoAllocStringLen@@YAJPEBG_KPEAPEAG@Z; CoAllocStringLen(ushort const *,unsigned __int64,ushort * *)
0x180038704  mov     ebx, eax
0x180038706  test    eax, eax
0x180038708  jns     short loc_18003872E
0x18003870a  mov     rcx, [rbp+8]; this
0x18003870e  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180038715  mov     r9d, eax; char *
0x180038718  mov     edx, 0ABh; void *
0x18003871d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038722  mov     rcx, [rbp+pv]; pv
0x180038726  call    cs:__imp_CoTaskMemFree
0x18003872c  jmp     short loc_1800386B5
0x18003872e  mov     rbx, [rbp+pv]
0x180038732  lea     r8, [rbp+TokenHandle]; unsigned int *
0x180038736  mov     edx, dword ptr [rbp+TokenHandle]; unsigned int
0x180038739  lea     rcx, [rbp+P]; this
0x18003873d  mov     r9, rbx; unsigned __int16 *
0x180038740  call    ?GetAppUserModelId@AutoSysAppId@ProcessToken@ARI@@QEBAJIPEAIPEAG@Z; ARI::ProcessToken::AutoSysAppId::GetAppUserModelId(uint,uint *,ushort *)
0x180038745  test    eax, eax
0x180038747  jz      short loc_180038782
0x180038749  mov     rcx, [rbp+8]; this
0x18003874d  mov     r9d, eax; char *
0x180038750  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038755  mov     rcx, rbx; pv
0x180038758  mov     edi, eax
0x18003875a  call    cs:__imp_CoTaskMemFree
0x180038760  mov     r8, [rbp+P]; P
0x180038764  test    r8, r8
0x180038767  jz      short loc_18003877E
0x180038769  mov     rcx, gs:60h
0x180038772  xor     edx, edx; Flags
0x180038774  mov     rcx, [rcx+30h]; HeapHandle
0x180038778  call    cs:__imp_RtlFreeHeap
0x18003877e  mov     eax, edi
0x180038780  jmp     short loc_1800387D4
0x180038782  xor     ecx, ecx; pv
0x180038784  mov     [rdi], rbx
0x180038787  call    cs:__imp_CoTaskMemFree
0x18003878d  mov     r8, [rbp+P]; P
0x180038791  test    r8, r8
0x180038794  jz      short loc_1800387AB
0x180038796  mov     rcx, gs:60h
0x18003879f  xor     edx, edx; Flags
0x1800387a1  mov     rcx, [rcx+30h]; HeapHandle
0x1800387a5  call    cs:__imp_RtlFreeHeap
0x1800387ab  xor     eax, eax
0x1800387ad  jmp     short loc_1800387D4
0x1800387af  mov     r8, [rbp+P]; P
0x1800387b3  test    r8, r8
0x1800387b6  jz      short loc_1800387D2
0x1800387b8  test    r8, r8
0x1800387bb  jz      short loc_1800387D2
0x1800387bd  mov     rcx, gs:60h
0x1800387c6  xor     edx, edx; Flags
0x1800387c8  mov     rcx, [rcx+30h]; HeapHandle
0x1800387cc  call    cs:__imp_RtlFreeHeap
0x1800387d2  mov     eax, ebx
0x1800387d4  mov     rbx, [rsp+30h+arg_10]
0x1800387d9  mov     rdi, [rsp+30h+arg_18]
0x1800387de  add     rsp, 30h
0x1800387e2  pop     rbp
0x1800387e3  retn
```
