# NCryptVerifyClaim

- ea: `0x18001c3a0`
- end: `0x18001c68a`
- name: `NCryptVerifyClaim`
- size: `746`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x1800159ec`
- `0x180016878`
- `0x18001c3a0`
- `0x18001f151`
- `0x180020010`

## string_xrefs

- `0x18001c618`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18001c660`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __fastcall NCryptVerifyClaim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD *a6,
        DWORD *a7,
        int a8)
{
  unsigned int v8; // ebx
  unsigned int v11; // ebp
  __int64 v12; // rdx
  _QWORD *v13; // rdi
  __int64 v14; // r9
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(_QWORD, _QWORD, __int64, _QWORD, __int64, BYTE *, _DWORD, DWORD *, int); // r13
  _WORD *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // eax
  NCRYPT_KEY_HANDLE *v24; // rdx
  NCryptKeyName **v25; // r8
  NCryptAlgorithmName **v26; // r9
  __int64 v27; // r8
  int v28; // r9d
  __int64 v30; // [rsp+50h] [rbp-58h]
  __int64 v31; // [rsp+50h] [rbp-58h]

  v8 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, a3, a1);
  v11 = 5;
  if ( v8 != 4 )
    v11 = v8;
  if ( v11 - 5 <= 1 && (Feature_Key_Guard_Attestation__private_featureState & 0x10) == 0 )
  {
    v30 = Feature_Key_Guard_Attestation__private_featureState | 1u;
    wil_details_FeatureReporting_ReportUsageToService(Feature_Key_Guard_Attestation__private_descriptor, v30, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
      v30,
      3,
      Feature_Key_Guard_Attestation__private_descriptor);
  }
  v13 = (_QWORD *)ValidateClientKeyHandle(a1);
  if ( !v13 )
  {
    v14 = 4532;
LABEL_11:
    v15 = -2146893786;
    v16 = 2148073510LL;
LABEL_34:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v14);
    return NormalizeNteStatus(v15, v24, v25, v26, a5, a6, a7);
  }
  v17 = v12;
  if ( a2 )
  {
    v17 = ValidateClientKeyHandle(a2);
    if ( !v17 )
    {
      v14 = 4543;
      goto LABEL_11;
    }
  }
  if ( !a7 )
  {
    v15 = -2146893785;
    v14 = 4551;
    v16 = 2148073511LL;
    goto LABEL_34;
  }
  v18 = v13[1];
  if ( *(_WORD *)(v18 + 16) < 3u
    || (v19 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, BYTE *, _DWORD, DWORD *, int))(v18 + 248)) == 0 )
  {
    v15 = -2146893783;
    v14 = 4565;
    v16 = 2148073513LL;
    goto LABEL_34;
  }
  v20 = *(_WORD **)(v18 + 280);
  v21 = -1;
  do
    ++v21;
  while ( v20[v21] != (_WORD)v12 );
  if ( 2 * v21 != 78 || (v22 = memcmp_0(v20, L"Microsoft Software Key Storage Provider", 0x50u), v12 = 0, v22) )
  {
    if ( v17 )
      v27 = *(_QWORD *)(v17 + 16);
    else
      v27 = v12;
    v23 = v19(*(_QWORD *)(v18 + 272), v13[2], v27, v11, a4, a5, (_DWORD)a6, a7, a8);
  }
  else
  {
    if ( (Feature_Key_Guard_Attestation__private_featureState & 0x10) == 0 )
    {
      v31 = Feature_Key_Guard_Attestation__private_featureState | 1u;
      wil_details_FeatureReporting_ReportUsageToService(Feature_Key_Guard_Attestation__private_descriptor, v31, 3);
      wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(
        v31,
        3,
        Feature_Key_Guard_Attestation__private_descriptor);
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, BYTE *, _DWORD, DWORD *, int))(v13[1] + 248LL))(
            v13[1],
            a1,
            a2,
            v11,
            a4,
            a5,
            (_DWORD)a6,
            a7,
            a8);
  }
  v15 = v23;
  if ( v23 )
  {
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4612);
    EtwLogNCryptOperationFailed(15, *(_QWORD *)(v13[1] + 280LL), v13[3], v28, v15);
  }
  else
  {
    v15 = 0;
  }
  return NormalizeNteStatus(v15, v24, v25, v26, a5, a6, a7);
}

```

## disassembly

```asm
0x18001c3a0  mov     [rsp+arg_18], r9
0x18001c3a5  push    rbx
0x18001c3a6  push    rbp
0x18001c3a7  push    rsi
0x18001c3a8  push    rdi
0x18001c3a9  push    r12
0x18001c3ab  push    r13
0x18001c3ad  push    r14
0x18001c3af  push    r15
0x18001c3b1  sub     rsp, 68h
0x18001c3b5  mov     ebx, r8d
0x18001c3b8  mov     r15, rdx
0x18001c3bb  mov     r14, rcx
0x18001c3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3c5  lea     rax, WPP_GLOBAL_Control
0x18001c3cc  cmp     rcx, rax
0x18001c3cf  jz      short loc_18001C3F3
0x18001c3d1  test    byte ptr [rcx+1Ch], 4
0x18001c3d5  jz      short loc_18001C3F3
0x18001c3d7  mov     eax, [rsp+0A8h+arg_38]
0x18001c3de  mov     edx, 25h ; '%'
0x18001c3e3  mov     rcx, [rcx+10h]
0x18001c3e7  mov     r9, r14
0x18001c3ea  mov     dword ptr [rsp+0A8h+var_88], eax
0x18001c3ee  call    WPP_SF_PD
0x18001c3f3  cmp     ebx, 4
0x18001c3f6  mov     ebp, 5
0x18001c3fb  cmovnz  ebp, ebx
0x18001c3fe  xor     edx, edx
0x18001c400  lea     eax, [rbp-5]
0x18001c403  lea     r13d, [rdx+3]
0x18001c407  cmp     eax, 1
0x18001c40a  ja      short loc_18001C45B
0x18001c40c  mov     ecx, cs:Feature_Key_Guard_Attestation__private_featureState
0x18001c412  mov     [rsp+0A8h+var_58], rdx
0x18001c417  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18001c41b  test    cl, 10h
0x18001c41e  jnz     short loc_18001C45B
0x18001c420  mov     rax, [rsp+0A8h+var_58]
0x18001c425  or      ecx, 1
0x18001c428  mov     [rsp+0A8h+var_58], rax
0x18001c42d  mov     r8d, r13d
0x18001c430  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18001c434  lea     rcx, Feature_Key_Guard_Attestation__private_descriptor
0x18001c43b  mov     rdx, [rsp+0A8h+var_58]
0x18001c440  call    wil_details_FeatureReporting_ReportUsageToService
0x18001c445  mov     rcx, [rsp+0A8h+var_58]
0x18001c44a  lea     r8, Feature_Key_Guard_Attestation__private_descriptor
0x18001c451  mov     edx, r13d
0x18001c454  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18001c459  xor     edx, edx
0x18001c45b  mov     rcx, r14
0x18001c45e  call    ValidateClientKeyHandle
0x18001c463  mov     rdi, rax
0x18001c466  test    rax, rax
0x18001c469  jnz     short loc_18001C480
0x18001c46b  mov     r9d, 11B4h
0x18001c471  mov     ebx, 80090026h
0x18001c476  mov     ecx, 80090026h
0x18001c47b  jmp     loc_18001C660
0x18001c480  mov     rbx, rdx
0x18001c483  test    r15, r15
0x18001c486  jz      short loc_18001C4A0
0x18001c488  mov     rcx, r15
0x18001c48b  call    ValidateClientKeyHandle
0x18001c490  mov     rbx, rax
0x18001c493  test    rax, rax
0x18001c496  jnz     short loc_18001C4A0
0x18001c498  mov     r9d, 11BFh
0x18001c49e  jmp     short loc_18001C471
0x18001c4a0  mov     r12, [rsp+0A8h+arg_30]
0x18001c4a8  test    r12, r12
0x18001c4ab  jnz     short loc_18001C4C2
0x18001c4ad  mov     ebx, 80090027h
0x18001c4b2  mov     r9d, 11C7h
0x18001c4b8  mov     ecx, 80090027h
0x18001c4bd  jmp     loc_18001C660
0x18001c4c2  mov     rsi, [rdi+8]
0x18001c4c6  cmp     [rsi+10h], r13w
0x18001c4cb  jb      loc_18001C650
0x18001c4d1  mov     r13, [rsi+0F8h]
0x18001c4d8  test    r13, r13
0x18001c4db  jz      loc_18001C650
0x18001c4e1  mov     rcx, [rsi+118h]; Buf1
0x18001c4e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c4ec  inc     rax
0x18001c4ef  cmp     [rcx+rax*2], dx
0x18001c4f3  jnz     short loc_18001C4EC
0x18001c4f5  add     rax, rax
0x18001c4f8  cmp     rax, 4Eh ; 'N'
0x18001c4fc  jnz     loc_18001C5B3
0x18001c502  lea     r8d, [rax+2]; Size
0x18001c506  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18001c50d  call    memcmp_0
0x18001c512  xor     edx, edx
0x18001c514  test    eax, eax
0x18001c516  jnz     loc_18001C5B3
0x18001c51c  mov     ecx, cs:Feature_Key_Guard_Attestation__private_featureState
0x18001c522  mov     [rsp+0A8h+var_58], rdx
0x18001c527  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18001c52b  test    cl, 10h
0x18001c52e  jnz     short loc_18001C56B
0x18001c530  mov     rax, [rsp+0A8h+var_58]
0x18001c535  lea     ebx, [rdx+3]
0x18001c538  or      ecx, 1
0x18001c53b  mov     [rsp+0A8h+var_58], rax
0x18001c540  mov     dword ptr [rsp+0A8h+var_58], ecx
0x18001c544  mov     r8d, ebx
0x18001c547  mov     rdx, [rsp+0A8h+var_58]
0x18001c54c  lea     rcx, Feature_Key_Guard_Attestation__private_descriptor
0x18001c553  call    wil_details_FeatureReporting_ReportUsageToService
0x18001c558  mov     rcx, [rsp+0A8h+var_58]
0x18001c55d  lea     r8, Feature_Key_Guard_Attestation__private_descriptor
0x18001c564  mov     edx, ebx
0x18001c566  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x18001c56b  mov     edx, [rsp+0A8h+arg_38]
0x18001c572  mov     r8, r15
0x18001c575  mov     rcx, [rdi+8]
0x18001c579  mov     [rsp+0A8h+var_68], edx
0x18001c57d  mov     edx, dword ptr [rsp+0A8h+arg_28]
0x18001c584  mov     [rsp+0A8h+var_70], r12
0x18001c589  mov     rax, [rcx+0F8h]
0x18001c590  mov     [rsp+0A8h+var_78], edx
0x18001c594  mov     rdx, [rsp+0A8h+arg_20]
0x18001c59c  mov     [rsp+0A8h+var_80], rdx
0x18001c5a1  mov     rdx, [rsp+0A8h+arg_18]
0x18001c5a9  mov     [rsp+0A8h+var_88], rdx
0x18001c5ae  mov     rdx, r14
0x18001c5b1  jmp     short loc_18001C604
0x18001c5b3  test    rbx, rbx
0x18001c5b6  jz      short loc_18001C5BE
0x18001c5b8  mov     r8, [rbx+10h]
0x18001c5bc  jmp     short loc_18001C5C1
0x18001c5be  mov     r8, rdx
0x18001c5c1  mov     eax, [rsp+0A8h+arg_38]
0x18001c5c8  mov     edx, dword ptr [rsp+0A8h+arg_28]
0x18001c5cf  mov     rcx, [rsi+110h]
0x18001c5d6  mov     [rsp+0A8h+var_68], eax
0x18001c5da  mov     rax, r13
0x18001c5dd  mov     [rsp+0A8h+var_70], r12
0x18001c5e2  mov     [rsp+0A8h+var_78], edx
0x18001c5e6  mov     rdx, [rsp+0A8h+arg_20]
0x18001c5ee  mov     [rsp+0A8h+var_80], rdx
0x18001c5f3  mov     rdx, [rsp+0A8h+arg_18]
0x18001c5fb  mov     [rsp+0A8h+var_88], rdx
0x18001c600  mov     rdx, [rdi+10h]
0x18001c604  mov     r9d, ebp
0x18001c607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c60c  mov     ebx, eax
0x18001c60e  test    eax, eax
0x18001c610  jz      short loc_18001C64C
0x18001c612  mov     r9d, 1204h
0x18001c618  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c61f  lea     rdx, aStatus; "Status"
0x18001c626  mov     ecx, eax
0x18001c628  call    DebugTraceError
0x18001c62d  mov     rdx, [rdi+8]
0x18001c631  mov     ecx, 0Fh
0x18001c636  mov     r8, [rdi+18h]
0x18001c63a  mov     dword ptr [rsp+0A8h+var_88], ebx
0x18001c63e  mov     rdx, [rdx+118h]
0x18001c645  call    EtwLogNCryptOperationFailed
0x18001c64a  jmp     short loc_18001C673
0x18001c64c  xor     ebx, ebx
0x18001c64e  jmp     short loc_18001C673
0x18001c650  mov     ebx, 80090029h
0x18001c655  mov     r9d, 11D5h
0x18001c65b  mov     ecx, 80090029h
0x18001c660  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c667  lea     rdx, aStatus; "Status"
0x18001c66e  call    DebugTraceError
0x18001c673  mov     ecx, ebx
0x18001c675  add     rsp, 68h
0x18001c679  pop     r15
0x18001c67b  pop     r14
0x18001c67d  pop     r13
0x18001c67f  pop     r12
0x18001c681  pop     rdi
0x18001c682  pop     rsi
0x18001c683  pop     rbp
0x18001c684  pop     rbx
0x18001c685  jmp     NormalizeNteStatus
```
