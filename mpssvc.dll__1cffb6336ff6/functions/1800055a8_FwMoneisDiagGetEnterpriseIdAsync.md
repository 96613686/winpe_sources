# FwMoneisDiagGetEnterpriseIdAsync

- ea: `0x1800055a8`
- end: `0x1800059eb`
- name: `FwMoneisDiagGetEnterpriseIdAsync`
- size: `1091`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE BindingHandle@<rdx>, LPCWSTR lpUnicodeCharStr@<r8>, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005510`

## callees

- `0x1800052d8`
- `0x1800055a8`
- `0x1800061ac`
- `0x180006ce0`
- `0x180008618`
- `0x180009720`
- `0x18000af3c`
- `0x180017110`
- `0x18002a470`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800b97ec`
- `0x1800ba8cc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005613`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005613`
- `RPCRT4!RpcAsyncAbortCall` at `0x180005793`
- `RPCRT4!RpcAsyncAbortCall` at `0x180005793`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005977`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180005977`
- `fwbase!FwHResultToWindowsError` at `0x180005638`
- `fwbase!FwHResultToWindowsError` at `0x1800057c6`
- `fwbase!FwHResultToWindowsError` at `0x18000591e`
- `fwbase!FwHResultToWindowsError` at `0x180005638`
- `fwbase!FwHResultToWindowsError` at `0x1800057c6`
- `fwbase!FwHResultToWindowsError` at `0x18000591e`
- `fwbase!FwStringCopy` at `0x1800057be`
- `fwbase!FwStringCopy` at `0x180005916`
- `fwbase!FwStringCopy` at `0x1800057be`
- `fwbase!FwStringCopy` at `0x180005916`
- `fwbase!FwAlloc` at `0x18000574a`
- `fwbase!FwAlloc` at `0x18000574a`
- `fwbase!FwCriticalSectionLeave` at `0x180005679`
- `fwbase!FwCriticalSectionLeave` at `0x180005679`

## pseudocode

```c
__int64 __fastcall FwMoneisDiagGetEnterpriseIdAsync(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE BindingHandle,
        LPCWSTR lpUnicodeCharStr,
        int a4,
        _DWORD *a5,
        const char **a6)
{
  DWORD TickCount; // eax
  DWORD v11; // r13d
  unsigned int v12; // eax
  unsigned int v13; // eax
  int v14; // ebx
  __int64 v15; // rcx
  int v17; // eax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  unsigned int EnterpriseId; // eax
  __int64 v25; // rdx
  unsigned int v26; // eax
  unsigned int EnterpriseIdFromCaller; // eax
  int v28; // r8d
  unsigned int v29; // edx
  const char *v30; // rax
  int v31; // [rsp+34h] [rbp-1Ch]
  unsigned int ExceptionCode; // [rsp+38h] [rbp-18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 119, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  ++g_invokedGetEnterpriseId;
  v31 = 0;
  TickCount = GetTickCount();
  *a5 = 0;
  v11 = TickCount;
  *a6 = 0;
  v12 = FwAcquireRPCSharedLock("FwMoneisDiagGetEnterpriseIdAsync");
  v13 = FwHResultToWindowsError(v12);
  ExceptionCode = v13;
  if ( v13 )
  {
    v14 = 0;
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 120, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v13);
      v15 = WPP_GLOBAL_Control;
    }
    goto LABEL_6;
  }
  v17 = EdpFieldsLock();
  if ( v17 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_31;
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      121,
      WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
      (unsigned int)v17);
    goto LABEL_38;
  }
  v31 = 1;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      122,
      WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
      lpUnicodeCharStr);
  if ( !qword_18012C7A8 || !(unsigned int)FwMoneisDiagIsServerInPolicy(lpUnicodeCharStr) )
  {
    v18 = FwAlloc(128);
    v19 = v18;
    if ( v18 )
    {
      memset_0((void *)(v18 + 8), 0, 0x78u);
      *(_QWORD *)v19 = pAsync;
      v21 = FwStringCopy(lpUnicodeCharStr, v19 + 8);
      v22 = FwHResultToWindowsError(v21);
      ExceptionCode = v22;
      if ( !v22 )
      {
        *(_DWORD *)(v19 + 16) = a4;
        *(_QWORD *)(v19 + 24) = a5;
        *(_QWORD *)(v19 + 32) = a6;
        *(_DWORD *)(v19 + 56) = v11;
        v23 = (_QWORD *)qword_18012C728;
        if ( *(__int64 **)qword_18012C728 != &qword_18012C720 )
          __fastfail(3u);
        *(_QWORD *)(v19 + 40) = &qword_18012C720;
        *(_QWORD *)(v19 + 48) = v23;
        *v23 = v19 + 40;
        qword_18012C728 = v19 + 40;
        EnterpriseId = FwMoneisDiagOperationGetEnterpriseId();
        v15 = WPP_GLOBAL_Control;
        v14 = 1;
        ExceptionCode = EnterpriseId;
        if ( EnterpriseId == 997 )
          ExceptionCode = 0;
LABEL_6:
        if ( !ExceptionCode )
          goto LABEL_7;
        goto LABEL_24;
      }
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_31:
        v14 = 1;
        goto LABEL_6;
      }
      v25 = 126;
      v20 = v22;
    }
    else
    {
      v20 = 14;
      ExceptionCode = 14;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        v14 = 1;
LABEL_24:
        ++g_failedGetEnterpriseId;
        if ( pAsync->Event )
        {
          RpcAsyncAbortCall(pAsync, ExceptionCode);
          v15 = WPP_GLOBAL_Control;
        }
LABEL_7:
        if ( !v31 )
          goto LABEL_9;
        goto LABEL_8;
      }
      v25 = 125;
    }
    goto LABEL_37;
  }
  if ( (a4 & 3) != 0 )
  {
    v26 = FwStringCopy(L"*", a6);
    EnterpriseIdFromCaller = FwHResultToWindowsError(v26);
  }
  else
  {
    EnterpriseIdFromCaller = FwMoneisDiagTryGetEnterpriseIdFromCaller(BindingHandle);
  }
  v29 = EnterpriseIdFromCaller;
  ExceptionCode = EnterpriseIdFromCaller;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v30 = L"<null>";
    if ( *a6 )
      v30 = *a6;
    WPP_SF_SDS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v29, v28, (_DWORD)lpUnicodeCharStr, v29, (__int64)v30);
  }
  RpcAsyncCompleteCall(pAsync, &ExceptionCode);
  ExceptionCode = 0;
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v25 = 124;
    v20 = 0;
LABEL_37:
    WPP_SF_d(*(_QWORD *)(v15 + 16), v25, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v20);
LABEL_38:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v14 = 1;
LABEL_8:
  FwCriticalSectionLeave(qword_18012C740);
  v15 = WPP_GLOBAL_Control;
LABEL_9:
  if ( v14 )
  {
    FwReleaseRPCSharedLock("FwMoneisDiagGetEnterpriseIdAsync");
    v15 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_BYTE *)(v15 + 28) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(v15 + 16), 127, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, ExceptionCode);
  return ExceptionCode;
}

```

## disassembly

```asm
0x1800055a8  mov     [rsp-38h+arg_18], rbx
0x1800055ad  push    rbp
0x1800055ae  push    rsi
0x1800055af  push    rdi
0x1800055b0  push    r12
0x1800055b2  push    r13
0x1800055b4  push    r14
0x1800055b6  push    r15
0x1800055b8  mov     rbp, rsp
0x1800055bb  sub     rsp, 50h
0x1800055bf  mov     rax, cs:__security_cookie
0x1800055c6  xor     rax, rsp
0x1800055c9  mov     [rbp+var_10], rax
0x1800055cd  mov     r15, [rbp+arg_20]
0x1800055d1  mov     esi, r9d
0x1800055d4  mov     rdi, [rbp+arg_28]
0x1800055d8  mov     r14, r8
0x1800055db  mov     rbx, rdx
0x1800055de  mov     r12, rcx
0x1800055e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055e8  lea     rax, WPP_GLOBAL_Control
0x1800055ef  cmp     rcx, rax
0x1800055f2  jz      short loc_1800055FE
0x1800055f4  test    byte ptr [rcx+1Ch], 8
0x1800055f8  jnz     loc_18000585D
0x1800055fe  inc     cs:g_invokedGetEnterpriseId
0x180005605  mov     [rbp+ExceptionCode], 0
0x18000560c  mov     [rbp+var_1C], 0
0x180005613  call    cs:__imp_GetTickCount
0x180005619  mov     dword ptr [r15], 0
0x180005620  lea     rcx, aFwmoneisdiagge_1; "FwMoneisDiagGetEnterpriseIdAsync"
0x180005627  mov     r13d, eax
0x18000562a  mov     qword ptr [rdi], 0
0x180005631  call    FwAcquireRPCSharedLock
0x180005636  mov     ecx, eax
0x180005638  call    cs:__imp_FwHResultToWindowsError
0x18000563e  mov     [rbp+ExceptionCode], eax
0x180005641  test    eax, eax
0x180005643  jz      loc_1800056EA
0x180005649  xor     ebx, ebx
0x18000564b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005652  lea     rsi, WPP_GLOBAL_Control
0x180005659  cmp     rcx, rsi
0x18000565c  jnz     loc_180005877
0x180005662  cmp     [rbp+ExceptionCode], 0
0x180005666  jnz     loc_18000577A
0x18000566c  cmp     [rbp+var_1C], 0
0x180005670  jz      short loc_180005686
0x180005672  lea     rcx, qword_18012C740
0x180005679  call    cs:__imp_FwCriticalSectionLeave
0x18000567f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005686  test    ebx, ebx
0x180005688  jz      short loc_18000569D
0x18000568a  lea     rcx, aFwmoneisdiagge_1; "FwMoneisDiagGetEnterpriseIdAsync"
0x180005691  call    FwReleaseRPCSharedLock
0x180005696  mov     rcx, cs:WPP_GLOBAL_Control
0x18000569d  cmp     rcx, rsi
0x1800056a0  jnz     short loc_1800056C9
0x1800056a2  mov     eax, [rbp+ExceptionCode]
0x1800056a5  mov     rcx, [rbp+var_10]
0x1800056a9  xor     rcx, rsp; StackCookie
0x1800056ac  call    __security_check_cookie
0x1800056b1  mov     rbx, [rsp+50h+arg_18]
0x1800056b9  add     rsp, 50h
0x1800056bd  pop     r15
0x1800056bf  pop     r14
0x1800056c1  pop     r13
0x1800056c3  pop     r12
0x1800056c5  pop     rdi
0x1800056c6  pop     rsi
0x1800056c7  pop     rbp
0x1800056c8  retn
0x1800056c9  test    byte ptr [rcx+1Ch], 8
0x1800056cd  jz      short loc_1800056A2
0x1800056cf  mov     r9d, [rbp+ExceptionCode]
0x1800056d3  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800056da  mov     rcx, [rcx+10h]
0x1800056de  mov     edx, 7Fh
0x1800056e3  call    WPP_SF_d
0x1800056e8  jmp     short loc_1800056A2
0x1800056ea  mov     [rbp+var_20], 1
0x1800056f1  call    EdpFieldsLock
0x1800056f6  test    eax, eax
0x1800056f8  js      loc_180005842
0x1800056fe  mov     [rbp+var_1C], 1
0x180005705  mov     rcx, cs:WPP_GLOBAL_Control
0x18000570c  lea     rax, WPP_GLOBAL_Control
0x180005713  cmp     rcx, rax
0x180005716  jz      short loc_180005722
0x180005718  test    byte ptr [rcx+1Ch], 4
0x18000571c  jnz     loc_1800058E9
0x180005722  cmp     cs:qword_18012C7A8, 0
0x18000572a  jz      short loc_180005745
0x18000572c  lea     r8, dword_18012C7B0
0x180005733  mov     edx, esi
0x180005735  mov     rcx, r14; lpUnicodeCharStr
0x180005738  call    FwMoneisDiagIsServerInPolicy
0x18000573d  test    eax, eax
0x18000573f  jnz     loc_180005906
0x180005745  mov     ecx, 80h
0x18000574a  call    cs:__imp_FwAlloc
0x180005750  mov     rbx, rax
0x180005753  test    rax, rax
0x180005756  jnz     short loc_1800057A5
0x180005758  lea     r9d, [rax+0Eh]
0x18000575c  mov     [rbp+ExceptionCode], r9d
0x180005760  mov     rcx, cs:WPP_GLOBAL_Control
0x180005767  lea     rsi, WPP_GLOBAL_Control
0x18000576e  cmp     rcx, rsi
0x180005771  jnz     loc_1800059A2
0x180005777  mov     ebx, [rbp+var_20]
0x18000577a  inc     cs:g_failedGetEnterpriseId
0x180005781  cmp     dword ptr [r12+28h], 0
0x180005787  jz      loc_18000566C
0x18000578d  mov     edx, [rbp+ExceptionCode]; ExceptionCode
0x180005790  mov     rcx, r12; pAsync
0x180005793  call    cs:__imp_RpcAsyncAbortCall
0x180005799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057a0  jmp     loc_18000566C
0x1800057a5  xor     edx, edx; Val
0x1800057a7  lea     rcx, [rax+8]; void *
0x1800057ab  lea     r8d, [rdx+78h]; Size
0x1800057af  call    memset_0
0x1800057b4  lea     rdx, [rbx+8]
0x1800057b8  mov     [rbx], r12
0x1800057bb  mov     rcx, r14
0x1800057be  call    cs:__imp_FwStringCopy
0x1800057c4  mov     ecx, eax
0x1800057c6  call    cs:__imp_FwHResultToWindowsError
0x1800057cc  mov     [rbp+ExceptionCode], eax
0x1800057cf  test    eax, eax
0x1800057d1  jnz     loc_1800059B6
0x1800057d7  mov     [rbx+10h], esi
0x1800057da  lea     rdx, qword_18012C720
0x1800057e1  mov     [rbx+18h], r15
0x1800057e5  mov     [rbx+20h], rdi
0x1800057e9  mov     [rbx+38h], r13d
0x1800057ed  mov     rcx, cs:qword_18012C728
0x1800057f4  cmp     [rcx], rdx
0x1800057f7  jnz     loc_1800059E4
0x1800057fd  lea     rax, [rbx+28h]
0x180005801  mov     [rax], rdx
0x180005804  mov     [rax+8], rcx
0x180005808  mov     [rcx], rax
0x18000580b  mov     cs:qword_18012C728, rax
0x180005812  call    FwMoneisDiagOperationGetEnterpriseId
0x180005817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000581e  lea     rsi, WPP_GLOBAL_Control
0x180005825  mov     ebx, [rbp+var_20]
0x180005828  mov     [rbp+ExceptionCode], eax
0x18000582b  cmp     eax, 3E5h
0x180005830  jnz     loc_180005662
0x180005836  mov     [rbp+ExceptionCode], 0
0x18000583d  jmp     loc_180005662
0x180005842  mov     rcx, cs:WPP_GLOBAL_Control
0x180005849  lea     rsi, WPP_GLOBAL_Control
0x180005850  cmp     rcx, rsi
0x180005853  jnz     short loc_1800058A5
0x180005855  mov     ebx, [rbp+var_20]
0x180005858  jmp     loc_180005662
0x18000585d  mov     rcx, [rcx+10h]
0x180005861  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180005868  mov     edx, 77h ; 'w'
0x18000586d  call    WPP_SF_
0x180005872  jmp     loc_1800055FE
0x180005877  test    byte ptr [rcx+1Ch], 1
0x18000587b  jz      loc_180005662
0x180005881  mov     rcx, [rcx+10h]
0x180005885  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x18000588c  mov     edx, 78h ; 'x'
0x180005891  mov     r9d, eax
0x180005894  call    WPP_SF_d
0x180005899  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058a0  jmp     loc_180005662
0x1800058a5  test    byte ptr [rcx+1Ch], 1
0x1800058a9  jz      short loc_180005855
0x1800058ab  mov     rcx, [rcx+10h]
0x1800058af  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800058b6  mov     edx, 79h ; 'y'
0x1800058bb  mov     r9d, eax
0x1800058be  call    WPP_SF_d
0x1800058c3  jmp     short loc_1800058DD
0x1800058c5  mov     edx, 7Ch ; '|'
0x1800058ca  xor     r9d, r9d
0x1800058cd  mov     rcx, [rcx+10h]
0x1800058d1  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800058d8  call    WPP_SF_d
0x1800058dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058e4  jmp     loc_180005855
0x1800058e9  mov     rcx, [rcx+10h]
0x1800058ed  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800058f4  mov     edx, 7Ah ; 'z'
0x1800058f9  mov     r9, r14
0x1800058fc  call    WPP_SF_S
0x180005901  jmp     loc_180005722
0x180005906  mov     rdx, rdi
0x180005909  test    sil, 3
0x18000590d  jz      short loc_180005926
0x18000590f  lea     rcx, String1; "*"
0x180005916  call    cs:__imp_FwStringCopy
0x18000591c  mov     ecx, eax
0x18000591e  call    cs:__imp_FwHResultToWindowsError
0x180005924  jmp     short loc_18000592E
0x180005926  mov     rcx, rbx; BindingHandle
0x180005929  call    FwMoneisDiagTryGetEnterpriseIdFromCaller
0x18000592e  mov     edx, eax
0x180005930  mov     rcx, cs:WPP_GLOBAL_Control
0x180005937  lea     rsi, WPP_GLOBAL_Control
0x18000593e  mov     [rbp+ExceptionCode], eax
0x180005941  cmp     rcx, rsi
0x180005944  jz      short loc_180005970
0x180005946  test    byte ptr [rcx+1Ch], 4
0x18000594a  jz      short loc_180005970
0x18000594c  cmp     qword ptr [rdi], 0
0x180005950  lea     rax, aNull; "<null>"
0x180005957  mov     rcx, [rcx+10h]
0x18000595b  mov     r9, r14
0x18000595e  cmovnz  rax, [rdi]
0x180005962  mov     [rsp+50h+var_28], rax
0x180005967  mov     [rsp+50h+var_30], edx
0x18000596b  call    WPP_SF_SDS
0x180005970  lea     rdx, [rbp+ExceptionCode]; Reply
0x180005974  mov     rcx, r12; pAsync
0x180005977  call    cs:__imp_RpcAsyncCompleteCall
0x18000597d  mov     [rbp+ExceptionCode], 0
0x180005984  mov     rcx, cs:WPP_GLOBAL_Control
0x18000598b  cmp     rcx, rsi
0x18000598e  jz      short loc_18000599A
0x180005990  test    byte ptr [rcx+1Ch], 1
0x180005994  jnz     loc_1800058C5
0x18000599a  mov     ebx, [rbp+var_20]
0x18000599d  jmp     loc_180005672
0x1800059a2  test    byte ptr [rcx+1Ch], 1
0x1800059a6  jz      loc_180005777
0x1800059ac  mov     edx, 7Dh ; '}'
0x1800059b1  jmp     loc_1800058CD
0x1800059b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059bd  lea     rsi, WPP_GLOBAL_Control
0x1800059c4  cmp     rcx, rsi
0x1800059c7  jz      loc_180005855
0x1800059cd  test    byte ptr [rcx+1Ch], 1
0x1800059d1  jz      loc_180005855
0x1800059d7  mov     edx, 7Eh ; '~'
0x1800059dc  mov     r9d, eax
0x1800059df  jmp     loc_1800058CD
0x1800059e4  mov     ecx, 3
0x1800059e9  int     29h; Win8: RtlFailFast(ecx)
```
