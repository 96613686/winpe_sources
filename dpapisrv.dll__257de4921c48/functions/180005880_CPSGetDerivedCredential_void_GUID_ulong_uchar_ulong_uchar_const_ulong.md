# CPSGetDerivedCredential(void *,_GUID *,ulong,uchar *,ulong,uchar * const,ulong *)

- ea: `0x180005880`
- end: `0x180005a25`
- name: `?CPSGetDerivedCredential@@YAKPEAXPEAU_GUID@@KPEAEKQEAEPEAK@Z`
- size: `421`
- prototype: `__int64 __fastcall(_DWORD *, struct _GUID *, char, unsigned __int8 *, ULONG, unsigned __int8 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001866c`

## callees

- `0x180004d80`
- `0x180004e60`
- `0x180005880`
- `0x1800063c0`
- `0x180006510`
- `0x180007f10`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800058d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800058d3`

## string_xrefs

- `0x180005996`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800059d5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`
- `0x1800059f5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\crypt32.cpp`

## pseudocode

```c
__int64 __fastcall CPSGetDerivedCredential(
        _DWORD *a1,
        struct _GUID *a2,
        char a3,
        unsigned __int8 *a4,
        ULONG a5,
        unsigned __int8 *const a6,
        unsigned int *a7)
{
  ULONG cbInput; // esi
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  struct _LUID v15; // [rsp+80h] [rbp+8h] BYREF

  v15 = 0;
  if ( a1 && *a1 != 624 )
    return 87;
  cbInput = a5;
  if ( !a5 || !a4 )
    return 87;
  LastError = CPSImpersonateClient(a1);
  if ( LastError )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
        139);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( (unsigned int)GetThreadAuthenticationId(CurrentThread, &v15) )
    {
      LastError = QueryDerivedCredential(a2, &v15, a3, a4, cbInput, a6, a7);
      if ( LastError
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          WPP_GLOBAL_Control,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
          166);
      }
    }
    else
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "dwLastError",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\crypt32.cpp",
        1170);
    }
    CPSRevertToSelf(a1);
  }
  return LastError;
}

```

## disassembly

```asm
0x180005880  mov     rax, rsp
0x180005883  push    rbx
0x180005884  push    rbp
0x180005885  push    rsi
0x180005886  push    rdi
0x180005887  push    r14
0x180005889  push    r15
0x18000588b  sub     rsp, 48h
0x18000588f  mov     qword ptr [rax+8], 0
0x180005897  mov     rbp, r9
0x18000589a  mov     r14d, r8d
0x18000589d  mov     r15, rdx
0x1800058a0  mov     rdi, rcx
0x1800058a3  test    rcx, rcx
0x1800058a6  jnz     loc_180005966
0x1800058ac  mov     esi, [rsp+78h+arg_20]
0x1800058b3  test    esi, esi
0x1800058b5  jz      loc_180005972
0x1800058bb  test    rbp, rbp
0x1800058be  jz      loc_180005972
0x1800058c4  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x1800058c9  mov     ebx, eax
0x1800058cb  test    eax, eax
0x1800058cd  jnz     loc_180005979
0x1800058d3  call    cs:__imp_GetCurrentThread
0x1800058da  nop     dword ptr [rax+rax+00h]
0x1800058df  mov     rcx, rax
0x1800058e2  lea     rdx, [rsp+78h+arg_0]
0x1800058ea  call    GetThreadAuthenticationId
0x1800058ef  test    eax, eax
0x1800058f1  jz      loc_1800059C3
0x1800058f7  mov     rax, [rsp+78h+arg_30]
0x1800058ff  lea     rdx, [rsp+78h+arg_0]; struct _LUID *
0x180005907  mov     [rsp+78h+var_48], rax; __int64
0x18000590c  mov     r9, rbp
0x18000590f  mov     rax, [rsp+78h+arg_28]
0x180005917  mov     r8d, r14d
0x18000591a  mov     [rsp+78h+var_50], rax; __int64
0x18000591f  mov     rcx, r15; struct _GUID *
0x180005922  mov     [rsp+78h+cbInput], esi; cbInput
0x180005926  call    QueryDerivedCredential
0x18000592b  mov     ebx, eax
0x18000592d  test    eax, eax
0x18000592f  jz      short loc_18000594E
0x180005931  mov     rdx, cs:WPP_GLOBAL_Control
0x180005938  lea     rcx, WPP_GLOBAL_Control
0x18000593f  cmp     rdx, rcx
0x180005942  jz      short loc_18000594E
0x180005944  test    byte ptr [rdx+1Ch], 1
0x180005948  jnz     loc_1800059F1
0x18000594e  mov     rcx, rdi; void *
0x180005951  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180005956  mov     eax, ebx
0x180005958  add     rsp, 48h
0x18000595c  pop     r15
0x18000595e  pop     r14
0x180005960  pop     rdi
0x180005961  pop     rsi
0x180005962  pop     rbp
0x180005963  pop     rbx
0x180005964  retn
0x180005966  cmp     dword ptr [rcx], 270h
0x18000596c  jz      loc_1800058AC
0x180005972  mov     eax, 57h ; 'W'
0x180005977  jmp     short loc_180005958
0x180005979  mov     rdx, cs:WPP_GLOBAL_Control
0x180005980  lea     rcx, WPP_GLOBAL_Control
0x180005987  cmp     rdx, rcx
0x18000598a  jz      short loc_180005956
0x18000598c  test    byte ptr [rdx+1Ch], 1
0x180005990  jz      short loc_180005956
0x180005992  mov     rcx, [rdx+10h]
0x180005996  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000599d  mov     dword ptr [rsp+78h+var_48], 48Bh
0x1800059a5  lea     r9, aDwlasterror; "dwLastError"
0x1800059ac  mov     [rsp+78h+var_50], rax
0x1800059b1  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800059b8  mov     [rsp+78h+cbInput], ebx
0x1800059bc  call    WPP_SF_sDsd
0x1800059c1  jmp     short loc_180005956
0x1800059c3  call    cs:__imp_GetLastError
0x1800059ca  nop     dword ptr [rax+rax+00h]
0x1800059cf  mov     r9d, 492h
0x1800059d5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800059dc  mov     ecx, eax
0x1800059de  lea     rdx, aDwlasterror; "dwLastError"
0x1800059e5  mov     ebx, eax
0x1800059e7  call    DebugTraceError
0x1800059ec  jmp     loc_18000594E
0x1800059f1  mov     rcx, [rdx+10h]
0x1800059f5  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800059fc  mov     dword ptr [rsp+78h+var_48], 4A6h
0x180005a04  lea     r9, aDwlasterror; "dwLastError"
0x180005a0b  mov     [rsp+78h+var_50], rax
0x180005a10  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180005a17  mov     [rsp+78h+cbInput], ebx
0x180005a1b  call    WPP_SF_sDsd
0x180005a20  jmp     loc_18000594E
```
