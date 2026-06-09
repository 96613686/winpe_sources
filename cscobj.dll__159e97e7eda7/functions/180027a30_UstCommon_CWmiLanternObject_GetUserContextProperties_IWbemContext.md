# UstCommon::CWmiLanternObject::GetUserContextProperties(IWbemContext *)

- ea: `0x180027a30`
- end: `0x180027d8f`
- name: `?GetUserContextProperties@CWmiLanternObject@UstCommon@@UEAAJPEAUIWbemContext@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(UstCommon::CWmiLanternObject *__hidden this, struct IWbemContext *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x18000f60c`
- `0x1800144a8`
- `0x180027a30`
- `0x180027dc8`
- `0x180027e48`
- `0x180027eac`
- `0x180027f00`
- `0x180028ccc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027d59`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180027d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027c30`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027bf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180027c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d63`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027ca7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180027ca7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027d6d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027b92`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027c00`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027b92`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027c00`
- `WTSAPI32!WTSQueryUserToken` at `0x180027b33`
- `WTSAPI32!WTSQueryUserToken` at `0x180027b33`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UstCommon::CWmiLanternObject::GetUserContextProperties(DWORD *this, struct IWbemContext *a2)
{
  int v3; // eax
  unsigned int v4; // r15d
  __int64 v5; // r9
  unsigned int v7; // eax
  HANDLE *v8; // rbx
  __int64 v9; // r8
  DWORD LastError; // eax
  HANDLE v11; // r12
  DWORD v12; // eax
  __int64 v13; // r8
  DWORD CurrentProcessId; // eax
  HANDLE v15; // r13
  __int64 v16; // rcx
  DWORD v17; // ebx
  DWORD v18; // eax
  __int64 v19; // r8
  BOOL v20; // ebx
  DWORD v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  HANDLE v25; // [rsp+90h] [rbp+40h] BYREF
  HANDLE v26; // [rsp+A0h] [rbp+50h] BYREF
  HANDLE Token; // [rsp+A8h] [rbp+58h] BYREF

  v3 = (*(__int64 (__fastcall **)(DWORD *, struct IWbemContext *))(*(_QWORD *)this + 16LL))(this, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        22,
        WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
        (unsigned int)v3);
    return v4;
  }
  v5 = this[2];
  if ( (_DWORD)v5 == 2 )
  {
    Token = 0;
    v7 = UstCommon::CComTemporaryRevertToSelf::RevertToSelf(&Token);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, v7);
    v8 = (HANDLE *)(this + 8);
    if ( WTSQueryUserToken(this[6], (PHANDLE)this + 4) )
    {
      v24 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_39:
        if ( Token )
        {
          if ( !SetThreadToken(0, Token) )
            GetLastError();
          CloseHandle(Token);
        }
        return v4;
      }
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
LABEL_36:
        if ( (_UNKNOWN *)v24 != &WPP_GLOBAL_Control && (*(_BYTE *)(v24 + 28) & 2) != 0 )
          WPP_SF_iD(*(_QWORD *)(v24 + 16), 31, v9, *v8, v4);
        goto LABEL_39;
      }
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_dd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          25,
          WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
          this[6],
          LastError);
      }
      v26 = 0;
      v11 = OpenProcess(0x40u, 0, this[10]);
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v26);
      v26 = v11;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v12 = GetLastError();
        WPP_SF_did(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, v13, this[10], v11, v12);
      }
      if ( v11 )
      {
        v25 = 0;
        CurrentProcessId = GetCurrentProcessId();
        v15 = OpenProcess(0x40u, 0, CurrentProcessId);
        CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v25);
        v25 = v15;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          {
            v17 = GetLastError();
            v18 = GetCurrentProcessId();
            WPP_SF_did(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 27, v19, v18, v15, v17);
            v16 = WPP_GLOBAL_Control;
            v8 = (HANDLE *)(this + 8);
          }
          if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 2) != 0 )
            WPP_SF_q(*(_QWORD *)(v16 + 16), 28, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, *((_QWORD *)this + 6));
        }
        v20 = DuplicateHandle(v11, *((HANDLE *)this + 6), v15, v8, 0, 0, 2u);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v21 = GetLastError();
          WPP_SF_idd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v22, v23, *((_QWORD *)this + 6), v20, v21);
        }
        CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v25);
        v8 = (HANDLE *)(this + 8);
      }
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v26);
    }
    v24 = WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, v5);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180027a30  mov     [rsp-38h+arg_8], rbx
0x180027a35  push    rbp
0x180027a36  push    rsi
0x180027a37  push    rdi
0x180027a38  push    r12
0x180027a3a  push    r13
0x180027a3c  push    r14
0x180027a3e  push    r15
0x180027a40  mov     rbp, rsp
0x180027a43  sub     rsp, 50h
0x180027a47  mov     r14, rcx
0x180027a4a  mov     rax, [rcx]
0x180027a4d  mov     rax, [rax+10h]
0x180027a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a56  mov     r15d, eax
0x180027a59  test    eax, eax
0x180027a5b  jns     short loc_180027A9E
0x180027a5d  lea     rsi, WPP_GLOBAL_Control
0x180027a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a6b  cmp     rcx, rsi
0x180027a6e  jz      loc_180027D74
0x180027a74  mov     edi, 2
0x180027a79  test    [rcx+1Ch], dil
0x180027a7d  jz      loc_180027D74
0x180027a83  lea     edx, [rdi+14h]
0x180027a86  mov     r9d, eax
0x180027a89  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027a90  mov     rcx, [rcx+10h]
0x180027a94  call    WPP_SF_d
0x180027a99  jmp     loc_180027D74
0x180027a9e  mov     r9d, [r14+8]
0x180027aa2  mov     edi, 2
0x180027aa7  cmp     r9d, edi
0x180027aaa  jz      short loc_180027AE2
0x180027aac  lea     rsi, WPP_GLOBAL_Control
0x180027ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027aba  cmp     rcx, rsi
0x180027abd  jz      short loc_180027AD8
0x180027abf  test    [rcx+1Ch], dil
0x180027ac3  jz      short loc_180027AD8
0x180027ac5  lea     edx, [rdi+15h]
0x180027ac8  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027acf  mov     rcx, [rcx+10h]
0x180027ad3  call    WPP_SF_d
0x180027ad8  mov     eax, 80070057h
0x180027add  jmp     loc_180027D77
0x180027ae2  mov     [rbp+Token], 0
0x180027aea  lea     rcx, [rbp+Token]; TokenHandle
0x180027aee  call    ?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ; UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)
0x180027af3  lea     rsi, WPP_GLOBAL_Control
0x180027afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b01  cmp     rcx, rsi
0x180027b04  jz      short loc_180027B24
0x180027b06  test    [rcx+1Ch], dil
0x180027b0a  jz      short loc_180027B24
0x180027b0c  mov     edx, 18h
0x180027b11  mov     r9d, eax
0x180027b14  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027b1b  mov     rcx, [rcx+10h]
0x180027b1f  call    WPP_SF_d
0x180027b24  lea     rbx, [r14+20h]
0x180027b28  mov     [rbp+var_10], rbx
0x180027b2c  mov     rdx, rbx; phToken
0x180027b2f  mov     ecx, [r14+18h]; SessionId
0x180027b33  call    cs:__imp_WTSQueryUserToken
0x180027b39  test    eax, eax
0x180027b3b  jnz     loc_180027CFE
0x180027b41  mov     rax, cs:WPP_GLOBAL_Control
0x180027b48  cmp     rax, rsi
0x180027b4b  jz      short loc_180027B7D
0x180027b4d  test    [rax+1Ch], dil
0x180027b51  jz      short loc_180027B7D
0x180027b53  call    cs:__imp_GetLastError
0x180027b59  mov     edx, 19h
0x180027b5e  mov     [rsp+50h+dwDesiredAccess], eax
0x180027b62  mov     r9d, [r14+18h]
0x180027b66  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b74  mov     rcx, [rcx+10h]
0x180027b78  call    WPP_SF_dd
0x180027b7d  mov     [rbp+arg_10], 0
0x180027b85  mov     r8d, [r14+28h]; dwProcessId
0x180027b89  xor     edx, edx; bInheritHandle
0x180027b8b  lea     r13d, [rdx+40h]
0x180027b8f  mov     ecx, r13d; dwDesiredAccess
0x180027b92  call    cs:__imp_OpenProcess
0x180027b98  mov     r12, rax
0x180027b9b  lea     rcx, [rbp+arg_10]
0x180027b9f  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180027ba4  mov     [rbp+arg_10], r12
0x180027ba8  mov     rax, cs:WPP_GLOBAL_Control
0x180027baf  cmp     rax, rsi
0x180027bb2  jz      short loc_180027BE1
0x180027bb4  test    [rax+1Ch], dil
0x180027bb8  jz      short loc_180027BE1
0x180027bba  call    cs:__imp_GetLastError
0x180027bc0  lea     edx, [r13-26h]
0x180027bc4  mov     [rsp+50h+bInheritHandle], eax
0x180027bc8  mov     qword ptr [rsp+50h+dwDesiredAccess], r12
0x180027bcd  mov     r9d, [r14+28h]
0x180027bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bd8  mov     rcx, [rcx+10h]
0x180027bdc  call    WPP_SF_did
0x180027be1  test    r12, r12
0x180027be4  jz      loc_180027CF2
0x180027bea  mov     [rbp+arg_0], 0
0x180027bf2  call    cs:__imp_GetCurrentProcessId
0x180027bf8  mov     r8d, eax; dwProcessId
0x180027bfb  xor     edx, edx; bInheritHandle
0x180027bfd  mov     ecx, r13d; dwDesiredAccess
0x180027c00  call    cs:__imp_OpenProcess
0x180027c06  mov     r13, rax
0x180027c09  lea     rcx, [rbp+arg_0]
0x180027c0d  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180027c12  mov     [rbp+arg_0], r13
0x180027c16  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c1d  cmp     rcx, rsi
0x180027c20  jz      short loc_180027C86
0x180027c22  test    [rcx+1Ch], dil
0x180027c26  jz      short loc_180027C62
0x180027c28  call    cs:__imp_GetLastError
0x180027c2e  mov     ebx, eax
0x180027c30  call    cs:__imp_GetCurrentProcessId
0x180027c36  mov     edx, 1Bh
0x180027c3b  mov     [rsp+50h+bInheritHandle], ebx
0x180027c3f  mov     qword ptr [rsp+50h+dwDesiredAccess], r13
0x180027c44  mov     r9d, eax
0x180027c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c4e  mov     rcx, [rcx+10h]
0x180027c52  call    WPP_SF_did
0x180027c57  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c5e  lea     rbx, [r14+20h]
0x180027c62  cmp     rcx, rsi
0x180027c65  jz      short loc_180027C86
0x180027c67  test    [rcx+1Ch], dil
0x180027c6b  jz      short loc_180027C86
0x180027c6d  mov     edx, 1Ch
0x180027c72  mov     r9, [r14+30h]
0x180027c76  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027c7d  mov     rcx, [rcx+10h]
0x180027c81  call    WPP_SF_q
0x180027c86  mov     [rsp+50h+dwOptions], edi; dwOptions
0x180027c8a  mov     [rsp+50h+bInheritHandle], 0; bInheritHandle
0x180027c92  mov     [rsp+50h+dwDesiredAccess], 0; dwDesiredAccess
0x180027c9a  mov     r9, rbx; lpTargetHandle
0x180027c9d  mov     r8, r13; hTargetProcessHandle
0x180027ca0  mov     rdx, [r14+30h]; hSourceHandle
0x180027ca4  mov     rcx, r12; hSourceProcessHandle
0x180027ca7  call    cs:__imp_DuplicateHandle
0x180027cad  mov     ebx, eax
0x180027caf  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cb6  cmp     rcx, rsi
0x180027cb9  jz      short loc_180027CE4
0x180027cbb  test    [rcx+1Ch], dil
0x180027cbf  jz      short loc_180027CE4
0x180027cc1  call    cs:__imp_GetLastError
0x180027cc7  mov     [rsp+50h+bInheritHandle], eax
0x180027ccb  mov     [rsp+50h+dwDesiredAccess], ebx
0x180027ccf  mov     r9, [r14+30h]
0x180027cd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cda  mov     rcx, [rcx+10h]
0x180027cde  call    WPP_SF_idd
0x180027ce3  nop
0x180027ce4  lea     rcx, [rbp+arg_0]
0x180027ce8  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180027ced  nop
0x180027cee  mov     rbx, [rbp+var_10]
0x180027cf2  lea     rcx, [rbp+arg_10]
0x180027cf6  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x180027cfb  nop
0x180027cfc  jmp     short loc_180027D25
0x180027cfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d05  cmp     rcx, rsi
0x180027d08  jz      short loc_180027D4E
0x180027d0a  test    [rcx+1Ch], dil
0x180027d0e  jz      short loc_180027D2C
0x180027d10  mov     edx, 1Eh
0x180027d15  lea     r8, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x180027d1c  mov     rcx, [rcx+10h]
0x180027d20  call    WPP_SF_
0x180027d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d2c  cmp     rcx, rsi
0x180027d2f  jz      short loc_180027D4E
0x180027d31  test    [rcx+1Ch], dil
0x180027d35  jz      short loc_180027D4E
0x180027d37  mov     edx, 1Fh
0x180027d3c  mov     [rsp+50h+dwDesiredAccess], r15d
0x180027d41  mov     r9, [rbx]
0x180027d44  mov     rcx, [rcx+10h]
0x180027d48  call    WPP_SF_iD
0x180027d4d  nop
0x180027d4e  mov     rdx, [rbp+Token]; Token
0x180027d52  test    rdx, rdx
0x180027d55  jz      short loc_180027D74
0x180027d57  xor     ecx, ecx; Thread
0x180027d59  call    cs:__imp_SetThreadToken
0x180027d5f  test    eax, eax
0x180027d61  jnz     short loc_180027D69
0x180027d63  call    cs:__imp_GetLastError
0x180027d69  mov     rcx, [rbp+Token]; hObject
0x180027d6d  call    cs:__imp_CloseHandle
0x180027d73  nop
0x180027d74  mov     eax, r15d
0x180027d77  mov     rbx, [rsp+50h+arg_8]
0x180027d7f  add     rsp, 50h
0x180027d83  pop     r15
0x180027d85  pop     r14
0x180027d87  pop     r13
0x180027d89  pop     r12
0x180027d8b  pop     rdi
0x180027d8c  pop     rsi
0x180027d8d  pop     rbp
0x180027d8e  retn
```
