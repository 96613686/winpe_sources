# CheckAndFireGPTriggerEvent(HKEY__ *,int)

- ea: `0x1800213ac`
- end: `0x1800217cd`
- name: `?CheckAndFireGPTriggerEvent@@YAHPEAUHKEY__@@H@Z`
- size: `1057`
- prototype: `__int64 __fastcall(HKEY hKey, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180058f20`
- `0x18005ce5c`

## callees

- `0x180014080`
- `0x1800213ac`
- `0x1800217d4`
- `0x180068650`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002164c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002164c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002165d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002165d`
- `ntdll!EtwEventWrite` at `0x18002153c`
- `ntdll!EtwEventWrite` at `0x180021640`
- `ntdll!EtwEventWrite` at `0x18002153c`
- `ntdll!EtwEventWrite` at `0x180021640`
- `ntdll!EtwEventActivityIdControl` at `0x1800214dc`
- `ntdll!EtwEventActivityIdControl` at `0x1800215e0`
- `ntdll!EtwEventActivityIdControl` at `0x1800214dc`
- `ntdll!EtwEventActivityIdControl` at `0x1800215e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CheckAndFireGPTriggerEvent(HKEY hKey, int a2)
{
  void (*v4)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  unsigned __int64 v8; // rbx
  __int64 *v9; // r14
  __int64 v10; // r8
  unsigned int v11; // eax
  DWORD LastError; // ebx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  unsigned __int64 v15; // rbx
  __int64 *v16; // r14
  __int64 v17; // r8
  unsigned int v18; // eax
  const wchar_t *v19; // r8
  const wchar_t *v20; // r8
  const wchar_t *v21; // r8
  const wchar_t *v22; // r8
  HLOCAL hMem; // [rsp+38h] [rbp-40h] BYREF
  __int64 v25; // [rsp+40h] [rbp-38h]
  __int64 *v26; // [rsp+48h] [rbp-30h]
  int v27; // [rsp+50h] [rbp-28h] BYREF
  int v28; // [rsp+54h] [rbp-24h]
  int v29; // [rsp+58h] [rbp-20h]
  int v30; // [rsp+5Ch] [rbp-1Ch]

  if ( (unsigned int)CSKU::IsDomainIncapableSystem() )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v4 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance )
        {
          if ( g_lpDebugMsgContext )
            RedirectDebugMsg(
              4u,
              L"CheckAndFireGPTriggerEvent: Machine not capable of joining domain. Not firing UBPM trigger events.");
        }
        return 0;
      }
      v5 = L"CheckAndFireGPTriggerEvent: Machine not capable of joining domain. Not firing UBPM trigger events.";
      goto LABEL_62;
    }
    return 0;
  }
  if ( (unsigned int)IsAppliedGPOListEmpty(hKey) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v4 = g_lpDebugMsg;
      if ( !g_lpDebugMsg )
      {
        if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          RedirectDebugMsg(
            4u,
            L"CheckAndFireGPTriggerEvent: Applied GPO list is empty. Not firing UBPM trigger events.");
        return 0;
      }
      v5 = L"CheckAndFireGPTriggerEvent: Applied GPO list is empty. Not firing UBPM trigger events.";
LABEL_62:
      v4(4u, v5);
    }
    return 0;
  }
  hMem = 0;
  v25 = 0;
  if ( a2 )
  {
    v26 = gpTriggerEvent_MachinePolicyPresent;
    v27 = 1704970982;
    v28 = 1302944731;
    v29 = 717946801;
    v30 = -532247273;
    if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
    {
      v6 = 2LL * HIDWORD(v25);
      v7 = hMem;
      *((_QWORD *)hMem + v6) = &v27;
      v7[v6 + 1] = 16;
      ++HIDWORD(v25);
    }
    v8 = CGPServiceEventReporting::s_pTriggerProviderHandle;
    v9 = v26;
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( *(_BYTE *)(v10 + 8) == 1 )
    {
      v11 = EtwEventActivityIdControl(2, v10 + 16);
      if ( v11 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v11);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v11);
          }
        }
      }
    }
    LastError = EtwEventWrite(v8, v9, HIDWORD(v25), hMem);
    if ( LastError )
      LastError = GetLastError();
  }
  else
  {
    v26 = gpTriggerEvent_UserPolicyPresent;
    v27 = 1425753800;
    v28 = 1179447433;
    v29 = -782631503;
    v30 = 1346055350;
    if ( !COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage((COperationalBaseEvent *)&hMem) )
    {
      v13 = 2LL * HIDWORD(v25);
      v14 = hMem;
      *((_QWORD *)hMem + v13) = &v27;
      v14[v13 + 1] = 16;
      ++HIDWORD(v25);
    }
    v15 = CGPServiceEventReporting::s_pTriggerProviderHandle;
    v16 = v26;
    v17 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( *(_BYTE *)(v17 + 8) == 1 )
    {
      v18 = EtwEventActivityIdControl(2, v17 + 16);
      if ( v18 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v18);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"COperationalBaseEvent::ReportOperationalEvent: Failed to set the activity id with error 0x%x",
              v18);
          }
        }
      }
    }
    LastError = EtwEventWrite(v15, v16, HIDWORD(v25), hMem);
    if ( LastError )
      LastError = GetLastError();
  }
  if ( hMem )
    LocalFree(hMem);
  if ( LastError )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        v21 = L"Machine";
        if ( !a2 )
          v21 = L"User";
        g_lpDebugMsg(
          2u,
          L"CheckAndFireGPTriggerEvent: Failed to fire Policy present UBPM trigger event for %s due to error: %d.",
          v21,
          LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v22 = L"Machine";
        if ( !a2 )
          v22 = L"User";
        RedirectDebugMsg(
          2u,
          L"CheckAndFireGPTriggerEvent: Failed to fire Policy present UBPM trigger event for %s due to error: %d.",
          v22,
          LastError);
      }
    }
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      v19 = L"Machine";
      if ( !a2 )
        v19 = L"User";
      g_lpDebugMsg(4u, L"CheckAndFireGPTriggerEvent: Fired Policy present UBPM trigger event for %s.", v19);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      v20 = L"Machine";
      if ( !a2 )
        v20 = L"User";
      RedirectDebugMsg(4u, L"CheckAndFireGPTriggerEvent: Fired Policy present UBPM trigger event for %s.", v20);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800213ac  push    rbp
0x1800213ae  push    rbx
0x1800213af  push    rsi
0x1800213b0  push    rdi
0x1800213b1  push    r14
0x1800213b3  push    r15
0x1800213b5  mov     rbp, rsp
0x1800213b8  sub     rsp, 78h
0x1800213bc  mov     rax, cs:__security_cookie
0x1800213c3  xor     rax, rsp
0x1800213c6  mov     [rbp+var_18], rax
0x1800213ca  mov     esi, edx
0x1800213cc  mov     rbx, rcx
0x1800213cf  call    ?IsDomainIncapableSystem@CSKU@@SAHXZ; CSKU::IsDomainIncapableSystem(void)
0x1800213d4  xor     r15d, r15d
0x1800213d7  test    eax, eax
0x1800213d9  jz      short loc_180021426
0x1800213db  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800213e2  jz      loc_1800217B2
0x1800213e8  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800213ef  test    rax, rax
0x1800213f2  jz      short loc_180021400
0x1800213f4  lea     rdx, aCheckandfiregp; "CheckAndFireGPTriggerEvent: Machine not"...
0x1800213fb  jmp     loc_180021783
0x180021400  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021407  jz      loc_1800217B2
0x18002140d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021414  jz      loc_1800217B2
0x18002141a  lea     rdx, aCheckandfiregp; "CheckAndFireGPTriggerEvent: Machine not"...
0x180021421  jmp     loc_1800217A8
0x180021426  mov     rcx, rbx; hKey
0x180021429  call    ?IsAppliedGPOListEmpty@@YAHPEAUHKEY__@@@Z; IsAppliedGPOListEmpty(HKEY__ *)
0x18002142e  test    eax, eax
0x180021430  jnz     loc_180021767
0x180021436  mov     [rbp+hMem], r15
0x18002143a  mov     [rbp+var_38], r15
0x18002143e  lea     rax, ??_7CGPTriggerBaseEvent@@6B@; const CGPTriggerBaseEvent::`vftable'
0x180021445  mov     [rbp+var_48], rax
0x180021449  test    esi, esi
0x18002144b  jz      loc_180021555
0x180021451  lea     rax, gpTriggerEvent_MachinePolicyPresent
0x180021458  mov     [rbp+var_30], rax
0x18002145c  mov     [rbp+var_28], 659FCAE6h
0x180021463  mov     [rbp+var_24], 4DA95BDBh
0x18002146a  mov     [rbp+var_20], 2ACAFFB1h
0x180021471  mov     [rbp+var_1C], 0E0468D17h
0x180021478  lea     rcx, [rbp+hMem]; this
0x18002147c  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180021481  test    eax, eax
0x180021483  jnz     short loc_1800214A3
0x180021485  mov     ecx, dword ptr [rbp+var_38+4]
0x180021488  add     rcx, rcx
0x18002148b  mov     rax, [rbp+hMem]
0x18002148f  lea     rdx, [rbp+var_28]
0x180021493  mov     [rax+rcx*8], rdx
0x180021497  mov     qword ptr [rax+rcx*8+8], 10h
0x1800214a0  inc     dword ptr [rbp+var_38+4]
0x1800214a3  mov     rbx, cs:?s_pTriggerProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pTriggerProviderHandle
0x1800214aa  mov     r14, [rbp+var_30]
0x1800214ae  mov     ecx, cs:_tls_index
0x1800214b4  mov     rax, gs:58h
0x1800214bd  mov     r8, [rax+rcx*8]
0x1800214c1  mov     eax, 8
0x1800214c6  mov     edi, 2
0x1800214cb  cmp     byte ptr [rax+r8], 1
0x1800214d0  jnz     short loc_18002152E
0x1800214d2  mov     edx, 10h
0x1800214d7  add     rdx, r8
0x1800214da  mov     ecx, edi
0x1800214dc  call    cs:__imp_EtwEventActivityIdControl
0x1800214e2  mov     r8d, eax
0x1800214e5  test    eax, eax
0x1800214e7  jz      short loc_18002152E
0x1800214e9  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800214f0  jz      short loc_18002152E
0x1800214f2  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800214f9  test    rax, rax
0x1800214fc  jz      short loc_18002150E
0x1800214fe  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180021505  mov     ecx, edi
0x180021507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002150c  jmp     short loc_18002152E
0x18002150e  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021515  jz      short loc_18002152E
0x180021517  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002151e  jz      short loc_18002152E
0x180021520  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180021527  mov     ecx, edi; unsigned int
0x180021529  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18002152e  mov     r9, [rbp+hMem]
0x180021532  mov     r8d, dword ptr [rbp+var_38+4]
0x180021536  mov     rdx, r14
0x180021539  mov     rcx, rbx
0x18002153c  call    cs:__imp_EtwEventWrite
0x180021542  mov     ebx, eax
0x180021544  test    eax, eax
0x180021546  jz      short loc_180021550
0x180021548  call    cs:__imp_GetLastError
0x18002154e  mov     ebx, eax
0x180021550  jmp     loc_180021654
0x180021555  lea     rax, gpTriggerEvent_UserPolicyPresent
0x18002155c  mov     [rbp+var_30], rax
0x180021560  mov     [rbp+var_28], 54FB46C8h
0x180021567  mov     [rbp+var_24], 464CF089h
0x18002156e  mov     [rbp+var_20], 0D159FDB1h
0x180021575  mov     [rbp+var_1C], 503B2CB6h
0x18002157c  lea     rcx, [rbp+hMem]; this
0x180021580  call    ?VerifyAndAllocateEventDataDescriptorStorage@COperationalBaseEvent@@AEAAKXZ; COperationalBaseEvent::VerifyAndAllocateEventDataDescriptorStorage(void)
0x180021585  test    eax, eax
0x180021587  jnz     short loc_1800215A7
0x180021589  mov     ecx, dword ptr [rbp+var_38+4]
0x18002158c  add     rcx, rcx
0x18002158f  mov     rax, [rbp+hMem]
0x180021593  lea     rdx, [rbp+var_28]
0x180021597  mov     [rax+rcx*8], rdx
0x18002159b  mov     qword ptr [rax+rcx*8+8], 10h
0x1800215a4  inc     dword ptr [rbp+var_38+4]
0x1800215a7  mov     rbx, cs:?s_pTriggerProviderHandle@CGPServiceEventReporting@@0_KA; unsigned __int64 CGPServiceEventReporting::s_pTriggerProviderHandle
0x1800215ae  mov     r14, [rbp+var_30]
0x1800215b2  mov     ecx, cs:_tls_index
0x1800215b8  mov     rax, gs:58h
0x1800215c1  mov     r8, [rax+rcx*8]
0x1800215c5  mov     eax, 8
0x1800215ca  mov     edi, 2
0x1800215cf  cmp     byte ptr [rax+r8], 1
0x1800215d4  jnz     short loc_180021632
0x1800215d6  mov     edx, 10h
0x1800215db  add     rdx, r8
0x1800215de  mov     ecx, edi
0x1800215e0  call    cs:__imp_EtwEventActivityIdControl
0x1800215e6  mov     r8d, eax
0x1800215e9  test    eax, eax
0x1800215eb  jz      short loc_180021632
0x1800215ed  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800215f4  jz      short loc_180021632
0x1800215f6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800215fd  test    rax, rax
0x180021600  jz      short loc_180021612
0x180021602  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x180021609  mov     ecx, edi
0x18002160b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021610  jmp     short loc_180021632
0x180021612  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021619  jz      short loc_180021632
0x18002161b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021622  jz      short loc_180021632
0x180021624  lea     rdx, aCoperationalba; "COperationalBaseEvent::ReportOperationa"...
0x18002162b  mov     ecx, edi; unsigned int
0x18002162d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021632  mov     r9, [rbp+hMem]
0x180021636  mov     r8d, dword ptr [rbp+var_38+4]
0x18002163a  mov     rdx, r14
0x18002163d  mov     rcx, rbx
0x180021640  call    cs:__imp_EtwEventWrite
0x180021646  mov     ebx, eax
0x180021648  test    eax, eax
0x18002164a  jz      short loc_180021654
0x18002164c  call    cs:__imp_GetLastError
0x180021652  mov     ebx, eax
0x180021654  mov     rcx, [rbp+hMem]; hMem
0x180021658  test    rcx, rcx
0x18002165b  jz      short loc_180021663
0x18002165d  call    cs:__imp_LocalFree
0x180021663  test    ebx, ebx
0x180021665  jnz     loc_1800216ED
0x18002166b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x180021672  jz      loc_180021760
0x180021678  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18002167f  test    rax, rax
0x180021682  jz      short loc_1800216AC
0x180021684  lea     rcx, aUser; "User"
0x18002168b  lea     r8, aMachine; "Machine"
0x180021692  test    esi, esi
0x180021694  cmovz   r8, rcx
0x180021698  lea     rdx, aCheckandfiregp_2; "CheckAndFireGPTriggerEvent: Fired Polic"...
0x18002169f  lea     ecx, [rbx+4]
0x1800216a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216a7  jmp     loc_180021760
0x1800216ac  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800216b3  jz      loc_180021760
0x1800216b9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800216c0  jz      loc_180021760
0x1800216c6  lea     rcx, aUser; "User"
0x1800216cd  lea     r8, aMachine; "Machine"
0x1800216d4  test    esi, esi
0x1800216d6  cmovz   r8, rcx
0x1800216da  lea     rdx, aCheckandfiregp_2; "CheckAndFireGPTriggerEvent: Fired Polic"...
0x1800216e1  mov     ecx, 4; unsigned int
0x1800216e6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800216eb  jmp     short loc_180021760
0x1800216ed  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800216f4  jz      short loc_180021760
0x1800216f6  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800216fd  test    rax, rax
0x180021700  jz      short loc_180021729
0x180021702  lea     rcx, aUser; "User"
0x180021709  lea     r8, aMachine; "Machine"
0x180021710  test    esi, esi
0x180021712  cmovz   r8, rcx
0x180021716  mov     r9d, ebx
0x180021719  lea     rdx, aCheckandfiregp_1; "CheckAndFireGPTriggerEvent: Failed to f"...
0x180021720  mov     ecx, edi
0x180021722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021727  jmp     short loc_180021760
0x180021729  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021730  jz      short loc_180021760
0x180021732  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180021739  jz      short loc_180021760
0x18002173b  lea     rcx, aUser; "User"
0x180021742  lea     r8, aMachine; "Machine"
0x180021749  test    esi, esi
0x18002174b  cmovz   r8, rcx
0x18002174f  mov     r9d, ebx
0x180021752  lea     rdx, aCheckandfiregp_1; "CheckAndFireGPTriggerEvent: Failed to f"...
0x180021759  mov     ecx, edi; unsigned int
0x18002175b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180021760  mov     eax, 1
0x180021765  jmp     short loc_1800217B4
0x180021767  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x18002176e  jz      short loc_1800217B2
0x180021770  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180021777  test    rax, rax
0x18002177a  jz      short loc_18002178F
0x18002177c  lea     rdx, aCheckandfiregp_0; "CheckAndFireGPTriggerEvent: Applied GPO"...
0x180021783  mov     ecx, 4
0x180021788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002178d  jmp     short loc_1800217B2
0x18002178f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x180021796  jz      short loc_1800217B2
0x180021798  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18002179f  jz      short loc_1800217B2
0x1800217a1  lea     rdx, aCheckandfiregp_0; "CheckAndFireGPTriggerEvent: Applied GPO"...
0x1800217a8  mov     ecx, 4; unsigned int
0x1800217ad  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800217b2  xor     eax, eax
0x1800217b4  mov     rcx, [rbp+var_18]
0x1800217b8  xor     rcx, rsp; StackCookie
0x1800217bb  call    __security_check_cookie
0x1800217c0  add     rsp, 78h
0x1800217c4  pop     r15
0x1800217c6  pop     r14
0x1800217c8  pop     rdi
0x1800217c9  pop     rsi
0x1800217ca  pop     rbx
0x1800217cb  pop     rbp
0x1800217cc  retn
```
