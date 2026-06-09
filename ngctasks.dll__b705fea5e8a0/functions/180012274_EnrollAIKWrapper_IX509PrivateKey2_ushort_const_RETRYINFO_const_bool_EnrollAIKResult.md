# EnrollAIKWrapper(IX509PrivateKey2 *,ushort const *,_RETRYINFO const *,bool *,EnrollAIKResult * *)

- ea: `0x180012274`
- end: `0x180012430`
- name: `?EnrollAIKWrapper@@YAJPEAUIX509PrivateKey2@@PEBGPEBU_RETRYINFO@@PEA_NPEAPEAUEnrollAIKResult@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(struct IX509PrivateKey2 *, const unsigned __int16 *, const struct _RETRYINFO *, bool *, struct EnrollAIKResult **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800126e4`

## callees

- `0x18000ebc0`
- `0x180012274`
- `0x180012ff0`
- `0x180013310`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012418`
- `certenroll!__imp_EnrollForAIKCertificate` at `0x1800122d4`
- `certenroll!__imp_EnrollForAIKCertificate` at `0x1800123b9`
- `certenroll!__imp_EnrollForAIKCertificate` at `0x1800122d4`
- `certenroll!__imp_EnrollForAIKCertificate` at `0x1800123b9`
- `certenroll!__imp_FreeEnrollAIKResult` at `0x180012391`
- `certenroll!__imp_FreeEnrollAIKResult` at `0x180012391`

## string_xrefs

- `0x1800122f4`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180012352`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800123d5`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x1800123fc`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall EnrollAIKWrapper(
        struct IX509PrivateKey2 *a1,
        const unsigned __int16 *a2,
        const struct _RETRYINFO *a3,
        bool *a4,
        struct EnrollAIKResult **a5)
{
  unsigned int v9; // ebx
  int LoggedOnUserImpersonationToken; // eax
  int v11; // r15d
  int v13; // [rsp+30h] [rbp-48h]
  HANDLE hObject; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  hObject = 0;
  *a4 = 0;
  v9 = EnrollForAIKCertificate(0, L"-Scenario:pregen", 0, 0, a1, a5, -2147467259);
  if ( v9 == -2145844841 )
  {
    LoggedOnUserImpersonationToken = GetLoggedOnUserImpersonationToken(&hObject);
    v11 = LoggedOnUserImpersonationToken;
    if ( LoggedOnUserImpersonationToken < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x46B,
        (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
        (const char *)(unsigned int)LoggedOnUserImpersonationToken);
    if ( !v11 )
    {
      LogAIKEnrollmentResult(0x80190197, 1, 0, a2, *a5, a3);
      *a4 = 1;
      FreeEnrollAIKResult(*a5);
      *a5 = 0;
      v13 = EnrollForAIKCertificate(0, L"-Scenario:pregen", 0, hObject, a1, a5, -2145844841);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x485,
          (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v13);
      v9 = v13;
    }
  }
  if ( hObject )
    CloseHandle(hObject);
  return v9;
}

```

## disassembly

```asm
0x180012274  mov     rax, rsp
0x180012277  mov     [rax+20h], r9
0x18001227b  mov     [rax+18h], r8
0x18001227f  mov     [rax+10h], rdx
0x180012283  mov     [rax+8], rcx
0x180012287  push    rbx
0x180012288  push    rsi
0x180012289  push    rdi
0x18001228a  push    r12
0x18001228c  push    r13
0x18001228e  push    r14
0x180012290  push    r15
0x180012292  sub     rsp, 40h
0x180012296  mov     rdi, r9
0x180012299  mov     r12, r8
0x18001229c  mov     r13, rdx
0x18001229f  mov     r14, rcx
0x1800122a2  mov     qword ptr [rax-40h], 0
0x1800122aa  mov     byte ptr [r9], 0
0x1800122ae  mov     dword ptr [rax-48h], 80004005h
0x1800122b5  mov     rsi, [rsp+78h+arg_20]
0x1800122bd  mov     [rax-50h], rsi
0x1800122c1  mov     [rax-58h], rcx
0x1800122c5  xor     r9d, r9d
0x1800122c8  xor     r8d, r8d
0x1800122cb  lea     rdx, aScenarioPregen; "-Scenario:pregen"
0x1800122d2  xor     ecx, ecx
0x1800122d4  call    cs:__imp_EnrollForAIKCertificate
0x1800122da  mov     dword ptr [rsp+78h+var_48], eax
0x1800122de  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800122e2  jmp     short loc_18001232D
0x1800122e4  mov     rcx, [rsp+78h]; this
0x1800122e9  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800122ed  test    ebx, ebx
0x1800122ef  jns     short loc_180012305
0x1800122f1  mov     r9d, ebx; char *
0x1800122f4  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800122fb  mov     edx, 461h; void *
0x180012300  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012305  mov     rsi, [rsp+78h+arg_20]
0x18001230d  mov     rdi, [rsp+78h+arg_18]
0x180012315  mov     r12, [rsp+78h+arg_10]
0x18001231d  mov     r13, [rsp+78h+arg_8]
0x180012325  mov     r14, [rsp+78h+arg_0]
0x18001232d  cmp     ebx, 80190197h
0x180012333  jnz     loc_18001240E
0x180012339  lea     rcx, [rsp+78h+hObject]; void **
0x18001233e  call    ?GetLoggedOnUserImpersonationToken@@YAJPEAPEAX@Z; GetLoggedOnUserImpersonationToken(void * *)
0x180012343  mov     r15d, eax
0x180012346  mov     rcx, [rsp+78h]; this
0x18001234b  test    eax, eax
0x18001234d  jns     short loc_180012363
0x18001234f  mov     r9d, eax; char *
0x180012352  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012359  mov     edx, 46Bh; void *
0x18001235e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012363  test    r15d, r15d
0x180012366  jnz     loc_18001240E
0x18001236c  mov     [rsp+78h+var_50], r12; struct _RETRYINFO *
0x180012371  mov     rax, [rsi]
0x180012374  mov     [rsp+78h+var_58], rax; struct EnrollAIKResult *
0x180012379  mov     r9, r13; unsigned __int16 *
0x18001237c  xor     r8d, r8d; bool
0x18001237f  mov     dl, 1; bool
0x180012381  mov     ecx, 80190197h; unsigned int
0x180012386  call    ?LogAIKEnrollmentResult@@YAXJ_N0PEBGPEBUEnrollAIKResult@@PEBU_RETRYINFO@@@Z; LogAIKEnrollmentResult(long,bool,bool,ushort const *,EnrollAIKResult const *,_RETRYINFO const *)
0x18001238b  mov     byte ptr [rdi], 1
0x18001238e  mov     rcx, [rsi]
0x180012391  call    cs:__imp_FreeEnrollAIKResult
0x180012397  mov     qword ptr [rsi], 0
0x18001239e  mov     [rsp+78h+var_50], rsi
0x1800123a3  mov     [rsp+78h+var_58], r14; int
0x1800123a8  mov     r9, [rsp+78h+hObject]
0x1800123ad  xor     r8d, r8d
0x1800123b0  lea     rdx, aScenarioPregen; "-Scenario:pregen"
0x1800123b7  xor     ecx, ecx
0x1800123b9  call    cs:__imp_EnrollForAIKCertificate
0x1800123bf  mov     dword ptr [rsp+78h+var_48], eax
0x1800123c3  mov     rcx, [rsp+78h]; this
0x1800123c8  mov     eax, dword ptr [rsp+78h+var_48]
0x1800123cc  test    eax, eax
0x1800123ce  jns     short loc_1800123E6
0x1800123d0  mov     r9d, dword ptr [rsp+78h+var_48]; char *
0x1800123d5  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800123dc  mov     edx, 485h; void *
0x1800123e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800123e6  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800123ea  jmp     short loc_18001240E
0x1800123ec  mov     ebx, dword ptr [rsp+78h+var_48]
0x1800123f0  test    ebx, ebx
0x1800123f2  jns     short loc_18001240E
0x1800123f4  mov     rcx, [rsp+78h]; this
0x1800123f9  mov     r9d, ebx; char *
0x1800123fc  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180012403  mov     edx, 489h; void *
0x180012408  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001240d  nop
0x18001240e  mov     rcx, [rsp+78h+hObject]; hObject
0x180012413  test    rcx, rcx
0x180012416  jz      short loc_18001241E
0x180012418  call    cs:__imp_CloseHandle
0x18001241e  mov     eax, ebx
0x180012420  add     rsp, 40h
0x180012424  pop     r15
0x180012426  pop     r14
0x180012428  pop     r13
0x18001242a  pop     r12
0x18001242c  pop     rdi
0x18001242d  pop     rsi
0x18001242e  pop     rbx
0x18001242f  retn
0x1800202d2  push    rbp
0x1800202d4  sub     rsp, 30h
0x1800202d8  mov     rbp, rdx
0x1800202db  mov     rax, [rcx]
0x1800202de  mov     ecx, [rax]
0x1800202e0  mov     [rbp+30h], ecx
0x1800202e3  mov     eax, 1
0x1800202e8  add     rsp, 30h
0x1800202ec  pop     rbp
0x1800202ed  retn
0x1800202ef  push    rbp
0x1800202f1  sub     rsp, 30h
0x1800202f5  mov     rbp, rdx
0x1800202f8  mov     rax, [rcx]
0x1800202fb  mov     ecx, [rax]
0x1800202fd  mov     [rbp+30h], ecx
0x180020300  mov     eax, 1
0x180020305  add     rsp, 30h
0x180020309  pop     rbp
0x18002030a  retn
```
