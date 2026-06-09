# DRMCreateClientSession

- ea: `0x18001b2a0`
- end: `0x18001b4aa`
- name: `DRMCreateClientSession`
- size: `522`
- prototype: `HRESULT __stdcall(DRMCALLBACK pfnCallback, UINT uCallbackVersion, PWSTR wszGroupIDProviderType, PWSTR wszGroupID, DRMHSESSION *phClient)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180017acc`
- `0x180018650`
- `0x18001c610`
- `0x18005b49c`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004328`
- `0x1800046c8`
- `0x18001b2a0`
- `0x18001f678`
- `0x18001f8e0`
- `0x1800200e4`
- `0x180020348`
- `0x180022898`
- `0x18005bd8a`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b39b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b39b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b3cc`
- `USER32!GetSystemMetrics` at `0x18001b359`
- `USER32!GetSystemMetrics` at `0x18001b359`

## string_xrefs

- `0x18001b2b7`: `[msdrm]:+DRMCreateClientSession - uCallbackVersion = %d,wszGroupIDProviderType = %S,wszGroupID = %S\n`
- `0x18001b48b`: `[msdrm]:-DRMCreateClientSession HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateClientSession(
        DRMCALLBACK pfnCallback,
        UINT uCallbackVersion,
        PWSTR wszGroupIDProviderType,
        PWSTR wszGroupID,
        DRMHSESSION *phClient)
{
  __int64 v9; // r8
  __int64 v10; // r9
  DRMHSESSION *v11; // r15
  __int64 v12; // r8
  __int64 v13; // r9
  HRESULT ClientEvents; // edi
  CDRMClient *v15; // rax
  CDRMClient *v16; // rax
  CDRMClient *v17; // rsi
  struct _RTL_CRITICAL_SECTION *v18; // r14
  CDRMCBase *v19; // rcx
  CDRMCBase *v20; // rcx
  void *v21; // rcx
  unsigned int v22; // edx
  void *Block; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v25; // [rsp+80h] [rbp+8h] BYREF

  _RTLTRACE(
    "[msdrm]:+DRMCreateClientSession - uCallbackVersion = %d,wszGroupIDProviderType = %S,wszGroupID = %S\n",
    uCallbackVersion,
    wszGroupIDProviderType,
    wszGroupID);
  v25 = 0;
  if ( pfnCallback
    && (v11 = phClient) != 0
    && (unsigned __int8)DRMIsValidStringT<unsigned short>(wszGroupIDProviderType, 0, v9, v10)
    && uCallbackVersion <= 1
    && (!wcscmp_0(wszGroupIDProviderType, L"WindowsAuthProvider")
     || !wcscmp_0(wszGroupIDProviderType, L"PassportAuthProvider"))
    && (!wszGroupID || *wszGroupID && (unsigned __int8)DRMIsValidStringT<unsigned short>(wszGroupID, 0, v12, v13)) )
  {
    if ( GetSystemMetrics(67) )
    {
      ClientEvents = -2147168392;
    }
    else
    {
      v15 = (CDRMClient *)operator new(0x1D8u);
      if ( v15 && (v16 = CDRMClient::CDRMClient(v15), (v17 = v16) != 0) )
      {
        v18 = (struct _RTL_CRITICAL_SECTION *)((char *)v16 + 88);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v16 + 88));
        *((_QWORD *)v17 + 16) = pfnCallback;
        LeaveCriticalSection(v18);
        EnterCriticalSection(v18);
        *((_DWORD *)v17 + 34) = uCallbackVersion;
        LeaveCriticalSection(v18);
        EnterCriticalSection(v18);
        Block = 0;
        ClientEvents = CDRMCBase::DuplicateStringEx(v19, wszGroupIDProviderType, (unsigned __int16 **)&Block);
        if ( ClientEvents < 0 )
        {
          v21 = Block;
        }
        else
        {
          CDRMCBase::DeleteString(v20, (unsigned __int16 **)v17 + 19);
          v21 = 0;
          *((_QWORD *)v17 + 19) = Block;
        }
        operator delete(v21);
        LeaveCriticalSection(v18);
        if ( ClientEvents < 0
          || wszGroupID && (ClientEvents = CDRMClient::SetUserID(v17, wszGroupID), ClientEvents < 0)
          || (ClientEvents = DRMCInt::CreateHandle(2u, v17, &v25), ClientEvents < 0)
          || (ClientEvents = CDRMClient::CreateClientEvents(v17, v22), ClientEvents < 0) )
        {
          (**(void (__fastcall ***)(CDRMClient *, __int64))v17)(v17, 1);
        }
        else
        {
          *v11 = v25;
        }
      }
      else
      {
        ClientEvents = -2147024882;
      }
    }
  }
  else
  {
    ClientEvents = -2147024809;
  }
  _RTLTRACE("[msdrm]:-DRMCreateClientSession HR=%x\n", ClientEvents);
  return ClientEvents;
}

```

## disassembly

```asm
0x18001b2a0  push    rbx
0x18001b2a2  push    rbp
0x18001b2a3  push    rsi
0x18001b2a4  push    rdi
0x18001b2a5  push    r12
0x18001b2a7  push    r13
0x18001b2a9  push    r14
0x18001b2ab  push    r15
0x18001b2ad  sub     rsp, 38h
0x18001b2b1  mov     r12, rcx
0x18001b2b4  mov     rbp, r9
0x18001b2b7  lea     rcx, aMsdrmDrmcreate_9; "[msdrm]:+DRMCreateClientSession - uCall"...
0x18001b2be  mov     rbx, r8
0x18001b2c1  mov     edi, edx
0x18001b2c3  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001b2c8  xor     r13d, r13d
0x18001b2cb  mov     [rsp+78h+arg_0], r13d
0x18001b2d3  test    r12, r12
0x18001b2d6  jz      loc_18001B484
0x18001b2dc  mov     r15, [rsp+78h+phClient]
0x18001b2e4  test    r15, r15
0x18001b2e7  jz      loc_18001B484
0x18001b2ed  xor     edx, edx
0x18001b2ef  mov     rcx, rbx
0x18001b2f2  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001b2f7  test    al, al
0x18001b2f9  jz      loc_18001B484
0x18001b2ff  cmp     edi, 1
0x18001b302  ja      loc_18001B484
0x18001b308  lea     rdx, aWindowsauthpro; "WindowsAuthProvider"
0x18001b30f  mov     rcx, rbx; String1
0x18001b312  call    wcscmp_0
0x18001b317  test    eax, eax
0x18001b319  jz      short loc_18001B332
0x18001b31b  lea     rdx, aPassportauthpr; "PassportAuthProvider"
0x18001b322  mov     rcx, rbx; String1
0x18001b325  call    wcscmp_0
0x18001b32a  test    eax, eax
0x18001b32c  jnz     loc_18001B484
0x18001b332  test    rbp, rbp
0x18001b335  jz      short loc_18001B354
0x18001b337  cmp     [rbp+0], r13w
0x18001b33c  jz      loc_18001B484
0x18001b342  xor     edx, edx
0x18001b344  mov     rcx, rbp
0x18001b347  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001b34c  test    al, al
0x18001b34e  jz      loc_18001B484
0x18001b354  mov     ecx, 43h ; 'C'; nIndex
0x18001b359  call    cs:__imp_GetSystemMetrics
0x18001b35f  test    eax, eax
0x18001b361  jz      short loc_18001B36D
0x18001b363  mov     edi, 8004CF78h
0x18001b368  jmp     loc_18001B489
0x18001b36d  mov     ecx, 1D8h; Size
0x18001b372  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b377  test    rax, rax
0x18001b37a  jz      loc_18001B47D
0x18001b380  mov     rcx, rax; this
0x18001b383  call    ??0CDRMClient@@QEAA@XZ; CDRMClient::CDRMClient(void)
0x18001b388  mov     rsi, rax
0x18001b38b  test    rax, rax
0x18001b38e  jz      loc_18001B47D
0x18001b394  lea     r14, [rax+58h]
0x18001b398  mov     rcx, r14; lpCriticalSection
0x18001b39b  call    cs:__imp_EnterCriticalSection
0x18001b3a1  mov     rcx, r14; lpCriticalSection
0x18001b3a4  mov     [rsi+80h], r12
0x18001b3ab  call    cs:__imp_LeaveCriticalSection
0x18001b3b1  mov     rcx, r14; lpCriticalSection
0x18001b3b4  call    cs:__imp_EnterCriticalSection
0x18001b3ba  mov     rcx, r14; lpCriticalSection
0x18001b3bd  mov     [rsi+88h], edi
0x18001b3c3  call    cs:__imp_LeaveCriticalSection
0x18001b3c9  mov     rcx, r14; lpCriticalSection
0x18001b3cc  call    cs:__imp_EnterCriticalSection
0x18001b3d2  lea     r8, [rsp+78h+Block]; unsigned __int16 **
0x18001b3d7  mov     [rsp+78h+Block], r13
0x18001b3dc  mov     rdx, rbx; unsigned __int16 *
0x18001b3df  call    ?DuplicateStringEx@CDRMCBase@@QEAAJPEAGPEAPEAG@Z; CDRMCBase::DuplicateStringEx(ushort *,ushort * *)
0x18001b3e4  mov     edi, eax
0x18001b3e6  test    eax, eax
0x18001b3e8  js      short loc_18001B406
0x18001b3ea  lea     rbx, [rsi+98h]
0x18001b3f1  mov     rdx, rbx; unsigned __int16 **
0x18001b3f4  call    ?DeleteString@CDRMCBase@@QEAAJPEAPEAG@Z; CDRMCBase::DeleteString(ushort * *)
0x18001b3f9  mov     rax, [rsp+78h+Block]
0x18001b3fe  mov     rcx, r13
0x18001b401  mov     [rbx], rax
0x18001b404  jmp     short loc_18001B40B
0x18001b406  mov     rcx, [rsp+78h+Block]; Block
0x18001b40b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b410  mov     rcx, r14; lpCriticalSection
0x18001b413  call    cs:__imp_LeaveCriticalSection
0x18001b419  test    edi, edi
0x18001b41b  js      short loc_18001B468
0x18001b41d  test    rbp, rbp
0x18001b420  jz      short loc_18001B433
0x18001b422  mov     rdx, rbp; unsigned __int16 *
0x18001b425  mov     rcx, rsi; this
0x18001b428  call    ?SetUserID@CDRMClient@@QEAAJPEAG@Z; CDRMClient::SetUserID(ushort *)
0x18001b42d  mov     edi, eax
0x18001b42f  test    eax, eax
0x18001b431  js      short loc_18001B468
0x18001b433  lea     r8, [rsp+78h+arg_0]; unsigned int *
0x18001b43b  mov     rdx, rsi; void *
0x18001b43e  mov     ecx, 2; unsigned int
0x18001b443  call    ?CreateHandle@DRMCInt@@SAJIPEAXPEAK@Z; DRMCInt::CreateHandle(uint,void *,ulong *)
0x18001b448  mov     edi, eax
0x18001b44a  test    eax, eax
0x18001b44c  js      short loc_18001B468
0x18001b44e  mov     rcx, rsi; this
0x18001b451  call    ?CreateClientEvents@CDRMClient@@QEAAJK@Z; CDRMClient::CreateClientEvents(ulong)
0x18001b456  mov     edi, eax
0x18001b458  test    eax, eax
0x18001b45a  js      short loc_18001B468
0x18001b45c  mov     eax, [rsp+78h+arg_0]
0x18001b463  mov     [r15], eax
0x18001b466  jmp     short loc_18001B489
0x18001b468  mov     rax, [rsi]
0x18001b46b  mov     edx, 1
0x18001b470  mov     rcx, rsi
0x18001b473  mov     rax, [rax]
0x18001b476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b47b  jmp     short loc_18001B489
0x18001b47d  mov     edi, 8007000Eh
0x18001b482  jmp     short loc_18001B489
0x18001b484  mov     edi, 80070057h
0x18001b489  mov     edx, edi
0x18001b48b  lea     rcx, aMsdrmDrmcreate_1; "[msdrm]:-DRMCreateClientSession HR=%x\n"
0x18001b492  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001b497  mov     eax, edi
0x18001b499  add     rsp, 38h
0x18001b49d  pop     r15
0x18001b49f  pop     r14
0x18001b4a1  pop     r13
0x18001b4a3  pop     r12
0x18001b4a5  pop     rdi
0x18001b4a6  pop     rsi
0x18001b4a7  pop     rbp
0x18001b4a8  pop     rbx
0x18001b4a9  retn
```
