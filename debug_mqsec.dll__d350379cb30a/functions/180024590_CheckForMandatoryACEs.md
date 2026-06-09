# _CheckForMandatoryACEs

- ea: `0x180024590`
- end: `0x1800247dc`
- name: `_CheckForMandatoryACEs`
- size: `588`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180023ef8`

## callees

- `0x180004074`
- `0x1800136f0`
- `0x180017430`
- `0x180021ba8`
- `0x180024590`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180024638`
- `ADVAPI32!EqualSid` at `0x1800246a4`
- `ADVAPI32!EqualSid` at `0x1800246d6`
- `ADVAPI32!EqualSid` at `0x180024638`
- `ADVAPI32!EqualSid` at `0x1800246a4`
- `ADVAPI32!EqualSid` at `0x1800246d6`
- `ADVAPI32!GetAce` at `0x1800245de`
- `ADVAPI32!GetAce` at `0x1800245de`
- `KERNEL32!GetLastError` at `0x18002479c`
- `KERNEL32!GetLastError` at `0x18002479c`

## pseudocode

```c
__int64 __fastcall CheckForMandatoryACEs(PACL pAcl, void *a2, _QWORD *a3, _DWORD *a4, _DWORD *a5, _DWORD *a6)
{
  DWORD AceCount; // edi
  int v7; // ebx
  _DWORD *v8; // r14
  DWORD v9; // esi
  _DWORD *v10; // r15
  struct _ACL *v12; // rax
  _DWORD *v13; // rcx
  struct _GUID *v14; // rdi
  __int64 v15; // rax
  BOOL v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  DWORD LastError; // eax
  DWORD v21; // [rsp+68h] [rbp-19h] BYREF
  int v22; // [rsp+70h] [rbp-11h] BYREF
  LPVOID pAce; // [rsp+78h] [rbp-9h] BYREF
  PSID pSid1; // [rsp+80h] [rbp-1h] BYREF
  struct _GUID *v25; // [rsp+88h] [rbp+7h] BYREF
  PACL v26; // [rsp+D8h] [rbp+57h] BYREF
  PSID pSid2; // [rsp+E0h] [rbp+5Fh]
  _QWORD *v28; // [rsp+E8h] [rbp+67h]

  v28 = a3;
  pSid2 = a2;
  v26 = pAcl;
  AceCount = pAcl->AceCount;
  v7 = 0;
  v8 = a6;
  v9 = 0;
  v10 = a5;
  v21 = AceCount;
  v12 = pAcl;
  while ( 1 )
  {
    pAce = 0;
    if ( !GetAce(v12, v9, &pAce) )
      break;
    pSid1 = 0;
    v25 = 0;
    GetpSidAndObj((struct _ACCESS_ALLOWED_ACE *)pAce, &pSid1, &v22, &v25);
    v13 = pAce;
    if ( *(_BYTE *)pAce == 6 )
    {
      if ( !v7 && !*a4 )
      {
        v14 = v25;
        if ( v25 )
        {
          if ( EqualSid(pSid1, g_pWorldSid) )
          {
            v15 = *(_QWORD *)&v14->Data1 - *v28;
            if ( *(_QWORD *)&v14->Data1 == *v28 )
              v15 = *(_QWORD *)v14->Data4 - v28[1];
            v13 = pAce;
            if ( !v15 )
            {
              AceCount = v21;
              if ( (*((_BYTE *)pAce + 4) & 0x20) != 0 )
                *a4 = 1;
              goto LABEL_16;
            }
          }
          else
          {
            v13 = pAce;
          }
        }
        AceCount = v21;
      }
    }
    else
    {
      v7 = 1;
    }
LABEL_16:
    if ( !*v10 && !*(_BYTE *)v13 && (v13[1] & 0xF00FF) == 0xF00FF )
    {
      v16 = EqualSid(pSid1, g_pSystemSid);
      v13 = pAce;
      if ( v16 )
        *v10 = 1;
    }
    if ( !*v8 && !*(_BYTE *)v13 && (v13[1] & 0x30) == 0x30 && EqualSid(pSid1, pSid2) )
      *v8 = 1;
    v12 = v26;
    if ( ++v9 >= AceCount )
    {
      if ( *v10 && *a4 && *v8 )
      {
        return 1;
      }
      else
      {
        v17 = 0;
        v21 = 0;
        LOWORD(v26) = 30;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v18 = mqwcslen(L"acssctrl/secd4to5");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            4,
            2LL * (v18 + 1),
            L"acssctrl/secd4to5",
            2,
            &v26,
            4,
            &v21,
            0,
            0);
        }
      }
      return v17;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, &WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids, v9, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180024590  mov     rax, rsp
0x180024593  mov     [rax+18h], r8
0x180024597  mov     [rax+10h], rdx
0x18002459b  mov     [rax+8], rcx
0x18002459f  push    rbp
0x1800245a0  push    rbx
0x1800245a1  push    rsi
0x1800245a2  push    rdi
0x1800245a3  push    r12
0x1800245a5  push    r14
0x1800245a7  push    r15
0x1800245a9  lea     rbp, [rax-4Fh]
0x1800245ad  sub     rsp, 90h
0x1800245b4  movzx   edi, word ptr [rcx+4]
0x1800245b8  xor     ebx, ebx
0x1800245ba  mov     r14, [rbp+47h+arg_28]
0x1800245be  xor     esi, esi
0x1800245c0  mov     r15, [rbp+47h+arg_20]
0x1800245c4  mov     r12, r9
0x1800245c7  mov     [rbp+47h+var_60], edi
0x1800245ca  mov     rax, rcx
0x1800245cd  lea     r8, [rbp+47h+pAce]; pAce
0x1800245d1  mov     [rbp+47h+pAce], 0
0x1800245d9  mov     edx, esi; dwAceIndex
0x1800245db  mov     rcx, rax; pAcl
0x1800245de  call    cs:__imp_GetAce
0x1800245e4  test    eax, eax
0x1800245e6  jz      loc_180024780
0x1800245ec  mov     rcx, [rbp+47h+pAce]; struct _ACCESS_ALLOWED_ACE *
0x1800245f0  lea     r9, [rbp+47h+var_40]; struct _GUID **
0x1800245f4  lea     r8, [rbp+47h+var_58]; int *
0x1800245f8  mov     [rbp+47h+pSid1], 0
0x180024600  lea     rdx, [rbp+47h+pSid1]; void **
0x180024604  mov     [rbp+47h+var_40], 0
0x18002460c  call    ?GetpSidAndObj@@YAXPEAU_ACCESS_ALLOWED_ACE@@PEAPEAXPEAHPEAPEAU_GUID@@@Z; GetpSidAndObj(_ACCESS_ALLOWED_ACE *,void * *,int *,_GUID * *)
0x180024611  mov     rcx, [rbp+47h+pAce]
0x180024615  cmp     byte ptr [rcx], 6
0x180024618  jnz     short loc_18002467B
0x18002461a  test    ebx, ebx
0x18002461c  jnz     short loc_180024680
0x18002461e  cmp     [r12], ebx
0x180024622  jnz     short loc_180024680
0x180024624  mov     rdi, [rbp+47h+var_40]
0x180024628  test    rdi, rdi
0x18002462b  jz      short loc_180024676
0x18002462d  mov     rdx, cs:?g_pWorldSid@@3PEAXEA; pSid2
0x180024634  mov     rcx, [rbp+47h+pSid1]; pSid1
0x180024638  call    cs:__imp_EqualSid
0x18002463e  test    eax, eax
0x180024640  jz      short loc_180024672
0x180024642  mov     rcx, [rbp+47h+arg_10]
0x180024646  mov     rax, [rdi]
0x180024649  sub     rax, [rcx]
0x18002464c  jnz     short loc_180024656
0x18002464e  mov     rax, [rdi+8]
0x180024652  sub     rax, [rcx+8]
0x180024656  mov     rcx, [rbp+47h+pAce]
0x18002465a  test    rax, rax
0x18002465d  jnz     short loc_180024676
0x18002465f  test    byte ptr [rcx+4], 20h
0x180024663  mov     edi, [rbp+47h+var_60]
0x180024666  jz      short loc_180024680
0x180024668  mov     dword ptr [r12], 1
0x180024670  jmp     short loc_180024680
0x180024672  mov     rcx, [rbp+47h+pAce]
0x180024676  mov     edi, [rbp+47h+var_60]
0x180024679  jmp     short loc_180024680
0x18002467b  mov     ebx, 1
0x180024680  cmp     dword ptr [r15], 0
0x180024684  jnz     short loc_1800246B9
0x180024686  cmp     byte ptr [rcx], 0
0x180024689  jnz     short loc_1800246B9
0x18002468b  mov     eax, [rcx+4]
0x18002468e  mov     edx, 0F00FFh
0x180024693  and     eax, edx
0x180024695  cmp     eax, edx
0x180024697  jnz     short loc_1800246B9
0x180024699  mov     rdx, cs:?g_pSystemSid@@3PEAXEA; pSid2
0x1800246a0  mov     rcx, [rbp+47h+pSid1]; pSid1
0x1800246a4  call    cs:__imp_EqualSid
0x1800246aa  mov     rcx, [rbp+47h+pAce]
0x1800246ae  test    eax, eax
0x1800246b0  jz      short loc_1800246B9
0x1800246b2  mov     dword ptr [r15], 1
0x1800246b9  cmp     dword ptr [r14], 0
0x1800246bd  jnz     short loc_1800246E7
0x1800246bf  cmp     byte ptr [rcx], 0
0x1800246c2  jnz     short loc_1800246E7
0x1800246c4  mov     eax, [rcx+4]
0x1800246c7  and     eax, 30h
0x1800246ca  cmp     al, 30h ; '0'
0x1800246cc  jnz     short loc_1800246E7
0x1800246ce  mov     rdx, [rbp+47h+pSid2]; pSid2
0x1800246d2  mov     rcx, [rbp+47h+pSid1]; pSid1
0x1800246d6  call    cs:__imp_EqualSid
0x1800246dc  test    eax, eax
0x1800246de  jz      short loc_1800246E7
0x1800246e0  mov     dword ptr [r14], 1
0x1800246e7  mov     rax, [rbp+47h+arg_0]
0x1800246eb  inc     esi
0x1800246ed  cmp     esi, edi
0x1800246ef  jb      loc_1800245CD
0x1800246f5  cmp     dword ptr [r15], 0
0x1800246f9  jz      short loc_18002470F
0x1800246fb  cmp     dword ptr [r12], 0
0x180024700  jz      short loc_18002470F
0x180024702  cmp     dword ptr [r14], 0
0x180024706  jz      short loc_18002470F
0x180024708  mov     ebx, 1
0x18002470d  jmp     short loc_18002477C
0x18002470f  xor     ebx, ebx
0x180024711  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180024718  mov     [rbp+47h+var_60], ebx
0x18002471b  lea     eax, [rbx+1Eh]
0x18002471e  mov     word ptr [rbp+47h+arg_0], ax
0x180024722  jz      short loc_18002477C
0x180024724  lea     rdi, aAcssctrlSecd4t; "acssctrl/secd4to5"
0x18002472b  mov     rcx, rdi; wchar_t *
0x18002472e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180024733  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18002473a  lea     r8d, [rbx+4]
0x18002473e  mov     [rsp+50h], rbx
0x180024743  lea     edx, [rbx+1]
0x180024746  mov     [rsp+0C0h+var_78], rbx
0x18002474b  lea     r9d, [rax+1]
0x18002474f  lea     rax, [rbp+47h+var_60]
0x180024753  add     r9, r9
0x180024756  mov     [rsp+0C0h+var_80], rax
0x18002475b  lea     rax, [rbp+47h+arg_0]
0x18002475f  mov     [rsp+0C0h+var_88], r8
0x180024764  mov     [rsp+0C0h+var_90], rax
0x180024769  mov     [rsp+0C0h+var_98], 2
0x180024772  mov     [rsp+0C0h+var_A0], rdi
0x180024777  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18002477c  mov     eax, ebx
0x18002477e  jmp     short loc_1800247CA
0x180024780  mov     rax, cs:WPP_GLOBAL_Control
0x180024787  lea     rcx, WPP_GLOBAL_Control
0x18002478e  cmp     rax, rcx
0x180024791  jz      short loc_1800247C8
0x180024793  test    byte ptr [rax+10Ch], 1
0x18002479a  jz      short loc_1800247C8
0x18002479c  call    cs:__imp_GetLastError
0x1800247a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247a9  lea     r8, WPP_3f90c469ed593c1daba4a8f3f91f4ca4_Traceguids
0x1800247b0  mov     edx, 0Bh
0x1800247b5  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800247b9  mov     r9d, esi
0x1800247bc  mov     rcx, [rcx+100h]
0x1800247c3  call    WPP_SF_dd
0x1800247c8  xor     eax, eax
0x1800247ca  add     rsp, 90h
0x1800247d1  pop     r15
0x1800247d3  pop     r14
0x1800247d5  pop     r12
0x1800247d7  pop     rdi
0x1800247d8  pop     rsi
0x1800247d9  pop     rbx
0x1800247da  pop     rbp
0x1800247db  retn
```
