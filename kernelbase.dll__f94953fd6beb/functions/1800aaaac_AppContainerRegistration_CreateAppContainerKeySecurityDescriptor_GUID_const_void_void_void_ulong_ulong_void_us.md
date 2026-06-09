# AppContainerRegistration::CreateAppContainerKeySecurityDescriptor(_GUID const *,void *,void *,void *,ulong,ulong *,void * *,ushort *)

- ea: `0x1800aaaac`
- end: `0x1800ab1c8`
- name: `?CreateAppContainerKeySecurityDescriptor@AppContainerRegistration@@CAJPEBU_GUID@@PEAX11KPEAKPEAPEAXPEAG@Z`
- size: `1820`
- prototype: `static int(const struct _GUID *, void *, void *, void *, unsigned int, unsigned int *, void **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180120b8c`
- `0x180120d6c`

## callees

- `0x1800134a0`
- `0x18002f994`
- `0x18004c240`
- `0x18004cb70`
- `0x180053e94`
- `0x180056554`
- `0x180058768`
- `0x180092438`
- `0x1800aaaac`
- `0x1800ab1d0`
- `0x1800ab230`
- `0x1800ab560`
- `0x1800ab9d0`
- `0x1800aba00`
- `0x1800aba30`
- `0x1800aba60`
- `0x1800aba90`
- `0x180120d5c`
- `0x180126e78`
- `0x180133c58`
- `0x180154728`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800aac7e`
- `ntdll!RtlLengthSid` at `0x1800aac8a`
- `ntdll!RtlLengthSid` at `0x1800aac96`
- `ntdll!RtlLengthSid` at `0x1800aaca3`
- `ntdll!RtlLengthSid` at `0x1800ab14c`
- `ntdll!RtlLengthSid` at `0x1800ab162`
- `ntdll!RtlLengthSid` at `0x1800aac7e`
- `ntdll!RtlLengthSid` at `0x1800aac8a`
- `ntdll!RtlLengthSid` at `0x1800aac96`
- `ntdll!RtlLengthSid` at `0x1800aaca3`
- `ntdll!RtlLengthSid` at `0x1800ab14c`
- `ntdll!RtlLengthSid` at `0x1800ab162`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800aaec1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800aafc1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800aaec1`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800aafc1`
- `ntdll!RtlAllocateHeap` at `0x1800aad46`
- `ntdll!RtlAllocateHeap` at `0x1800aad46`

## string_xrefs

- `0x1800aacc7`: `CreateAppContainerKeySD %ul mask 0x%0x %d %d `

## pseudocode

```c
__int64 __fastcall AppContainerRegistration::CreateAppContainerKeySecurityDescriptor(
        const struct _GUID *a1,
        void *a2,
        void *a3,
        void *a4,
        unsigned int AccessMask,
        unsigned int *a6,
        void **a7,
        char *a8)
{
  int v10; // edi
  int v11; // eax
  PSID v12; // r15
  signed int LastError; // r14d
  const char *v14; // r9
  __int64 v15; // rdx
  signed int LastErrorMsg; // eax
  PSID v17; // rcx
  PSID v18; // rcx
  PSID v19; // rcx
  int v21; // eax
  PSID v22; // rbx
  const char *v23; // r9
  int v24; // eax
  PSID v25; // rsi
  const char *v26; // r9
  ULONG v27; // eax
  ULONG v28; // eax
  ULONG v29; // eax
  ULONG v30; // eax
  ULONG v31; // edi
  DWORD v32; // edi
  unsigned int v33; // eax
  ReservedForLocalUse *v34; // rcx
  void *Heap; // rax
  PVOID v36; // rax
  void *v37; // r13
  const char *v38; // r9
  void *v39; // rcx
  int v40; // eax
  ACL *v41; // rdi
  const char *v42; // r9
  PSID v43; // r14
  NTSTATUS v44; // eax
  __int64 v45; // rdx
  int v46; // eax
  PSECURITY_DESCRIPTOR v47; // r14
  NTSTATUS v48; // eax
  signed int v49; // r12d
  bool v50; // sf
  ULONG v51; // eax
  ULONG v52; // eax
  int v53; // [rsp+28h] [rbp-71h]
  const char *v54; // [rsp+28h] [rbp-71h]
  const char *v55; // [rsp+28h] [rbp-71h]
  char *v56; // [rsp+30h] [rbp-69h]
  char *v57; // [rsp+30h] [rbp-69h]
  DWORD cbSid; // [rsp+48h] [rbp-51h] BYREF
  PSID pSid; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v60[128]; // [rsp+58h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]
  const struct _GUID *v62; // [rsp+E8h] [rbp+4Fh] BYREF
  PSID Sid; // [rsp+F0h] [rbp+57h]
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+F8h] [rbp+5Fh] BYREF
  PSID v65; // [rsp+100h] [rbp+67h]

  v65 = a4;
  SelfRelativeSecurityDescriptor = a3;
  Sid = a2;
  v62 = a1;
  lambda_f6d66e2938cd7d2db6473c74ebbf57c0_::_lambda_f6d66e2938cd7d2db6473c74ebbf57c0_(&pSid, &v62);
  wil::ThreadFailureCallback__lambda_cb404202719105b885c5aa52f19c21f0___((struct wil::details::IFailureCallback *)v60);
  pSid = 0;
  cbSid = 68;
  v10 = (a4 != 0) + 5;
  if ( !a3 )
    v10 = (a4 != 0) + 4;
  v11 = Common::GlobalHeap::Alloc(0x44u, &pSid);
  v12 = pSid;
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v11,
      v53);
    goto LABEL_15;
  }
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B0,
                  (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                  v14);
    goto LABEL_15;
  }
  cbSid = 68;
  pSid = 0;
  v21 = Common::GlobalHeap::Alloc(0x44u, &pSid);
  LastError = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v21,
      v53);
    v19 = pSid;
    goto LABEL_14;
  }
  v22 = pSid;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1B9,
                  (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                  v23);
    goto LABEL_13;
  }
  pSid = 0;
  cbSid = 68;
  v24 = Common::GlobalHeap::Alloc(0x44u, &pSid);
  LastError = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v24,
      v53);
    v18 = pSid;
    goto LABEL_12;
  }
  v25 = pSid;
  if ( !CreateWellKnownSid(WinCreatorOwnerSid, 0, pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1C2,
                  (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                  v26);
    goto LABEL_11;
  }
  pSid = 0;
  cbSid = 12 * v10 + 8;
  v27 = RtlLengthSid(v22);
  cbSid += v27;
  v28 = RtlLengthSid(v25);
  cbSid += v28;
  v29 = RtlLengthSid(v12);
  cbSid += v29;
  v30 = RtlLengthSid(Sid);
  v31 = v30 + cbSid;
  cbSid += v30;
  if ( a4 )
  {
    v51 = RtlLengthSid(a4);
    v31 = v51 + cbSid;
    cbSid += v51;
  }
  if ( a3 )
  {
    v52 = RtlLengthSid(a3);
    v31 = v52 + cbSid;
  }
  v32 = (v31 + 3) & 0xFFFFFFFC;
  cbSid = v32;
  v33 = StringCchPrintfA(a8, 0x104u, "CreateAppContainerKeySD %ul mask 0x%0x %d %d ", v32, AccessMask, a3 != 0, a4 != 0);
  LODWORD(v56) = v32;
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x1DA,
    (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
    (const char *)v33,
    (int)"StringCchPrintf %ul 0x%0x",
    v56);
  Heap = ReservedForLocalUse::GetHeap(v34);
  v36 = RtlAllocateHeap(Heap, 0, 0x28u);
  v37 = v36;
  if ( !v36 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)0x8007000ELL,
      (int)v54);
    v39 = 0;
    goto LABEL_29;
  }
  if ( !InitializeSecurityDescriptor(v36, 1u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1DE,
                  (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                  v38);
    v39 = v37;
LABEL_29:
    Common::GlobalHeap::Free(v39);
    v17 = 0;
    goto LABEL_10;
  }
  v40 = Common::GlobalHeap::Alloc(cbSid, &pSid);
  LastError = v40;
  if ( v40 < 0 )
  {
    LODWORD(v57) = cbSid;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v40,
      (int)"Size %u",
      v57);
    Common::GlobalHeap::Free(v37);
    v17 = pSid;
    goto LABEL_10;
  }
  v41 = (ACL *)pSid;
  if ( !InitializeAcl((PACL)pSid, cbSid, 2u) )
  {
    LODWORD(v54) = cbSid;
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x1E2,
                     (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                     "Size %u",
                     v54);
    goto LABEL_8;
  }
  if ( !AddAccessAllowedAceEx(v41, 2u, 3u, 0xF003Fu, v12) )
  {
    v15 = 489;
    goto LABEL_7;
  }
  if ( !AddAccessAllowedAceEx(v41, 2u, 3u, 0x20019u, v25) )
  {
    v15 = 496;
LABEL_7:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)v15,
                     (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                     v42);
LABEL_8:
    LastError = LastErrorMsg;
LABEL_9:
    Common::GlobalHeap::Free(v37);
    v17 = v41;
LABEL_10:
    Common::GlobalHeap::Free(v17);
LABEL_11:
    v18 = v25;
LABEL_12:
    Common::GlobalHeap::Free(v18);
LABEL_13:
    v19 = v22;
LABEL_14:
    Common::GlobalHeap::Free(v19);
    goto LABEL_15;
  }
  if ( !AddAccessAllowedAceEx(v41, 2u, 3u, 0xF003Fu, v22) )
  {
    v15 = 503;
    goto LABEL_7;
  }
  v43 = Sid;
  if ( !AddAccessAllowedAceEx(v41, 2u, 3u, 0xF003Fu, Sid) )
  {
    v15 = 510;
    goto LABEL_7;
  }
  if ( SelfRelativeSecurityDescriptor && !AddAccessAllowedAceEx(v41, 2u, 3u, 0xF003Fu, SelfRelativeSecurityDescriptor) )
  {
    v15 = 519;
    goto LABEL_7;
  }
  if ( v65 && !AddAccessAllowedAceEx(v41, 2u, 3u, AccessMask, v65) )
  {
    v15 = 529;
    goto LABEL_7;
  }
  if ( !SetSecurityDescriptorDacl(v37, 1, v41, 0) )
  {
    v15 = 533;
    goto LABEL_7;
  }
  if ( !SetSecurityDescriptorOwner(v37, v43, 0) )
  {
    v15 = 534;
    goto LABEL_7;
  }
  if ( !SetSecurityDescriptorGroup(v37, v43, 0) )
  {
    v15 = 535;
    goto LABEL_7;
  }
  cbSid = 0;
  v44 = RtlAbsoluteToSelfRelativeSD(v37, 0, &cbSid);
  if ( v44 >= 0 )
  {
    LastError = -2147024895;
    v45 = 542;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)LastError,
      (int)v55);
    goto LABEL_9;
  }
  BaseSetLastNTError((unsigned int)v44);
  LastError = NtCurrentTeb()->LastErrorValue;
  if ( LastError != 122 )
  {
    v50 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v50 = LastError < 0;
    }
    if ( !v50 )
      goto LABEL_9;
    v45 = 544;
    goto LABEL_43;
  }
  SelfRelativeSecurityDescriptor = 0;
  v46 = Common::GlobalHeap::Alloc(cbSid, &SelfRelativeSecurityDescriptor);
  LastError = v46;
  if ( v46 < 0 )
  {
    LODWORD(v57) = cbSid;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v46,
      (int)"Size %u",
      v57);
    Common::GlobalHeap::Free(SelfRelativeSecurityDescriptor);
    goto LABEL_9;
  }
  v47 = SelfRelativeSecurityDescriptor;
  v48 = RtlAbsoluteToSelfRelativeSD(v37, SelfRelativeSecurityDescriptor, &cbSid);
  if ( v48 < 0 )
  {
    BaseSetLastNTError((unsigned int)v48);
    LODWORD(v55) = cbSid;
    v49 = wil::details::in1diag3::Return_GetLastErrorMsg(
            retaddr,
            (void *)0x224,
            (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
            "Size %u",
            v55);
    Common::GlobalHeap::Free(v47);
    Common::GlobalHeap::Free(v37);
    Common::GlobalHeap::Free(v41);
    Common::GlobalHeap::Free(v25);
    Common::GlobalHeap::Free(v22);
    LastError = v49;
  }
  else
  {
    *a6 = -2147483641;
    *a7 = v47;
    Common::GlobalHeap::Free(0);
    Common::GlobalHeap::Free(v37);
    Common::GlobalHeap::Free(v41);
    Common::GlobalHeap::Free(v25);
    Common::GlobalHeap::Free(v22);
    LastError = 0;
  }
LABEL_15:
  Common::GlobalHeap::Free(v12);
  wil::details::ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___::_ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___(v60);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800aaaac  mov     rax, rsp
0x1800aaaaf  mov     [rax+20h], r9
0x1800aaab3  mov     [rax+18h], r8
0x1800aaab7  mov     [rax+10h], rdx
0x1800aaabb  mov     [rax+8], rcx
0x1800aaabf  push    rbp
0x1800aaac0  push    rbx
0x1800aaac1  push    rsi
0x1800aaac2  push    rdi
0x1800aaac3  push    r12
0x1800aaac5  push    r13
0x1800aaac7  push    r14
0x1800aaac9  push    r15
0x1800aaacb  lea     rbp, [rax-47h]
0x1800aaacf  sub     rsp, 98h
0x1800aaad6  lea     rdx, [rbp+3Fh+arg_0]
0x1800aaada  mov     r13, r9
0x1800aaadd  lea     rcx, [rbp+3Fh+pSid]
0x1800aaae1  mov     r12, r8
0x1800aaae4  call    _lambda_f6d66e2938cd7d2db6473c74ebbf57c0____lambda_f6d66e2938cd7d2db6473c74ebbf57c0_
0x1800aaae9  mov     rdx, rax
0x1800aaaec  lea     rcx, [rbp+3Fh+var_80]; struct wil::details::IFailureCallback *
0x1800aaaf0  call    wil__ThreadFailureCallback__lambda_cb404202719105b885c5aa52f19c21f0___
0x1800aaaf5  mov     rax, r13
0x1800aaaf8  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800aaafc  neg     rax
0x1800aaaff  sbb     ecx, ecx
0x1800aab01  xor     esi, esi
0x1800aab03  neg     ecx
0x1800aab05  mov     [rbp+3Fh+pSid], rsi
0x1800aab09  add     ecx, 4
0x1800aab0c  test    r12, r12
0x1800aab0f  lea     ebx, [rsi+44h]
0x1800aab12  mov     [rbp+3Fh+cbSid], ebx
0x1800aab15  lea     edi, [rcx+1]
0x1800aab18  cmovz   edi, ecx
0x1800aab1b  mov     ecx, ebx; Size
0x1800aab1d  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800aab22  mov     r15, [rbp+3Fh+pSid]
0x1800aab26  mov     r14d, eax
0x1800aab29  test    eax, eax
0x1800aab2b  js      loc_1800AB064
0x1800aab31  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800aab35  mov     r8, r15; pSid
0x1800aab38  xor     edx, edx; DomainSid
0x1800aab3a  lea     ecx, [rsi+16h]; WellKnownSidType
0x1800aab3d  call    CreateWellKnownSid
0x1800aab42  test    eax, eax
0x1800aab44  jnz     short loc_1800AABBC
0x1800aab46  mov     rcx, [rbp+47h]; this
0x1800aab4a  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800aab51  mov     edx, 1B0h; void *
0x1800aab56  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aab5b  mov     r14d, eax
0x1800aab5e  jmp     short loc_1800AAB94
0x1800aab60  mov     edx, 1F0h; void *
0x1800aab65  mov     rcx, [rbp+47h]; this
0x1800aab69  mov     r8, r12; unsigned int
0x1800aab6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aab71  mov     r14d, eax
0x1800aab74  mov     rcx, r13; void *
0x1800aab77  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aab7c  mov     rcx, rdi; void *
0x1800aab7f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aab84  mov     rcx, rsi; void *
0x1800aab87  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aab8c  mov     rcx, rbx; void *
0x1800aab8f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aab94  mov     rcx, r15; void *
0x1800aab97  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aab9c  lea     rcx, [rbp+3Fh+var_80]
0x1800aaba0  call    wil__details__ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0______ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___
0x1800aaba5  mov     eax, r14d
0x1800aaba8  add     rsp, 98h
0x1800aabaf  pop     r15
0x1800aabb1  pop     r14
0x1800aabb3  pop     r13
0x1800aabb5  pop     r12
0x1800aabb7  pop     rdi
0x1800aabb8  pop     rsi
0x1800aabb9  pop     rbx
0x1800aabba  pop     rbp
0x1800aabbb  retn
0x1800aabbc  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800aabc0  mov     [rbp+3Fh+cbSid], ebx
0x1800aabc3  mov     rcx, rbx; Size
0x1800aabc6  mov     [rbp+3Fh+pSid], rsi
0x1800aabca  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800aabcf  mov     r14d, eax
0x1800aabd2  test    eax, eax
0x1800aabd4  js      loc_1800AB107
0x1800aabda  mov     rbx, [rbp+3Fh+pSid]
0x1800aabde  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800aabe2  xor     edx, edx; DomainSid
0x1800aabe4  mov     r8, rbx; pSid
0x1800aabe7  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800aabea  call    CreateWellKnownSid
0x1800aabef  test    eax, eax
0x1800aabf1  jnz     short loc_1800AAC10
0x1800aabf3  mov     rcx, [rbp+47h]; this
0x1800aabf7  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800aabfe  mov     edx, 1B9h; void *
0x1800aac03  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aac08  mov     r14d, eax
0x1800aac0b  jmp     loc_1800AAB8C
0x1800aac10  mov     ecx, 44h ; 'D'; Size
0x1800aac15  mov     [rbp+3Fh+pSid], rsi
0x1800aac19  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800aac1d  mov     [rbp+3Fh+cbSid], ecx
0x1800aac20  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800aac25  mov     r14d, eax
0x1800aac28  test    eax, eax
0x1800aac2a  js      loc_1800AB128
0x1800aac30  mov     rsi, [rbp+3Fh+pSid]
0x1800aac34  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800aac38  xor     edx, edx; DomainSid
0x1800aac3a  mov     r8, rsi; pSid
0x1800aac3d  lea     ecx, [rdx+3]; WellKnownSidType
0x1800aac40  call    CreateWellKnownSid
0x1800aac45  test    eax, eax
0x1800aac47  jnz     short loc_1800AAC66
0x1800aac49  mov     rcx, [rbp+47h]; this
0x1800aac4d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800aac54  mov     edx, 1C2h; void *
0x1800aac59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aac5e  mov     r14d, eax
0x1800aac61  jmp     loc_1800AAB84
0x1800aac66  lea     eax, [rdi+rdi*2]
0x1800aac69  mov     [rbp+3Fh+pSid], 0
0x1800aac71  lea     eax, ds:8[rax*4]
0x1800aac78  mov     rcx, rbx; Sid
0x1800aac7b  mov     [rbp+3Fh+cbSid], eax
0x1800aac7e  call    cs:__imp_RtlLengthSid
0x1800aac84  add     [rbp+3Fh+cbSid], eax
0x1800aac87  mov     rcx, rsi; Sid
0x1800aac8a  call    cs:__imp_RtlLengthSid
0x1800aac90  add     [rbp+3Fh+cbSid], eax
0x1800aac93  mov     rcx, r15; Sid
0x1800aac96  call    cs:__imp_RtlLengthSid
0x1800aac9c  mov     rcx, [rbp+3Fh+Sid]; Sid
0x1800aaca0  add     [rbp+3Fh+cbSid], eax
0x1800aaca3  call    cs:__imp_RtlLengthSid
0x1800aaca9  mov     edi, [rbp+3Fh+cbSid]
0x1800aacac  add     edi, eax
0x1800aacae  mov     [rbp+3Fh+cbSid], edi
0x1800aacb1  test    r13, r13
0x1800aacb4  jnz     loc_1800AB149
0x1800aacba  test    r12, r12
0x1800aacbd  jnz     loc_1800AB15F
0x1800aacc3  mov     r14d, [rbp+3Fh+AccessMask]
0x1800aacc7  lea     r8, aCreateappconta_7; "CreateAppContainerKeySD %ul mask 0x%0x "...
0x1800aacce  xor     ecx, ecx
0x1800aacd0  add     edi, 3
0x1800aacd3  and     edi, 0FFFFFFFCh
0x1800aacd6  mov     edx, 104h; unsigned __int64
0x1800aacdb  test    r13, r13
0x1800aacde  mov     [rbp+3Fh+cbSid], edi
0x1800aace1  mov     r9d, edi
0x1800aace4  setnz   cl
0x1800aace7  xor     eax, eax
0x1800aace9  mov     [rsp+30h], ecx
0x1800aaced  test    r12, r12
0x1800aacf0  mov     rcx, [rbp+3Fh+arg_38]; char *
0x1800aacf7  setnz   al
0x1800aacfa  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800aacfe  mov     dword ptr [rsp+0D0h+var_B0], r14d
0x1800aad03  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800aad08  mov     rcx, [rbp+47h]; this
0x1800aad0c  lea     rdx, aStringcchprint; "StringCchPrintf %ul 0x%0x"
0x1800aad13  mov     [rsp+30h], r14d
0x1800aad18  lea     r12, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800aad1f  mov     dword ptr [rsp+0D0h+var_A8], edi; char *
0x1800aad23  mov     r9d, eax; char *
0x1800aad26  mov     [rsp+0D0h+var_B0], rdx; int
0x1800aad2b  mov     r8, r12; unsigned int
0x1800aad2e  mov     edx, 1DAh; void *
0x1800aad33  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800aad38  call    ?GetHeap@ReservedForLocalUse@@YAPEAXXZ; ReservedForLocalUse::GetHeap(void)
0x1800aad3d  xor     edx, edx; Flags
0x1800aad3f  mov     rcx, rax; HeapHandle
0x1800aad42  lea     r8d, [rdx+28h]; Size
0x1800aad46  call    cs:__imp_RtlAllocateHeap
0x1800aad4c  mov     r13, rax
0x1800aad4f  test    rax, rax
0x1800aad52  jz      loc_1800AB172
0x1800aad58  mov     edx, 1; dwRevision
0x1800aad5d  mov     rcx, rax; pSecurityDescriptor
0x1800aad60  call    InitializeSecurityDescriptor
0x1800aad65  test    eax, eax
0x1800aad67  jnz     short loc_1800AAD8C
0x1800aad69  mov     rcx, [rbp+47h]; this
0x1800aad6d  mov     r8, r12; unsigned int
0x1800aad70  mov     edx, 1DEh; void *
0x1800aad75  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aad7a  mov     r14d, eax
0x1800aad7d  mov     rcx, r13; void *
0x1800aad80  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800aad85  xor     ecx, ecx
0x1800aad87  jmp     loc_1800AAB7F
0x1800aad8c  mov     ecx, [rbp+3Fh+cbSid]; Size
0x1800aad8f  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800aad93  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800aad98  mov     edx, [rbp+3Fh+cbSid]; nAclLength
0x1800aad9b  mov     r14d, eax
0x1800aad9e  test    eax, eax
0x1800aada0  js      loc_1800AB081
0x1800aada6  mov     rdi, [rbp+3Fh+pSid]
0x1800aadaa  mov     r14d, 2
0x1800aadb0  mov     r8d, r14d; dwAclRevision
0x1800aadb3  mov     rcx, rdi; pAcl
0x1800aadb6  call    InitializeAcl
0x1800aadbb  test    eax, eax
0x1800aadbd  jz      loc_1800AAEEE
0x1800aadc3  mov     r9d, 0F003Fh; AccessMask
0x1800aadc9  mov     [rsp+0D0h+var_B0], r15; pSid
0x1800aadce  lea     r8d, [r14+1]; AceFlags
0x1800aadd2  mov     edx, r14d; dwAceRevision
0x1800aadd5  mov     rcx, rdi; pAcl
0x1800aadd8  call    AddAccessAllowedAceEx
0x1800aaddd  test    eax, eax
0x1800aaddf  jz      loc_1800AAF12
0x1800aade5  mov     r9d, 20019h; AccessMask
0x1800aadeb  mov     [rsp+0D0h+var_B0], rsi; pSid
0x1800aadf0  lea     r8d, [r14+1]; AceFlags
0x1800aadf4  mov     edx, r14d; dwAceRevision
0x1800aadf7  mov     rcx, rdi; pAcl
0x1800aadfa  call    AddAccessAllowedAceEx
0x1800aadff  test    eax, eax
0x1800aae01  jz      loc_1800AAB60
0x1800aae07  mov     r9d, 0F003Fh; AccessMask
0x1800aae0d  mov     [rsp+0D0h+var_B0], rbx; pSid
0x1800aae12  lea     r8d, [r14+1]; AceFlags
0x1800aae16  mov     edx, r14d; dwAceRevision
0x1800aae19  mov     rcx, rdi; pAcl
0x1800aae1c  call    AddAccessAllowedAceEx
0x1800aae21  test    eax, eax
0x1800aae23  jz      loc_1800AAF1C
0x1800aae29  mov     r14, [rbp+3Fh+Sid]
0x1800aae2d  mov     edx, 2; dwAceRevision
0x1800aae32  mov     r9d, 0F003Fh; AccessMask
0x1800aae38  mov     [rsp+0D0h+var_B0], r14; int
0x1800aae3d  mov     rcx, rdi; pAcl
0x1800aae40  lea     r8d, [rdx+1]; AceFlags
0x1800aae44  call    AddAccessAllowedAceEx
0x1800aae49  test    eax, eax
0x1800aae4b  jz      loc_1800AAF26
0x1800aae51  mov     rax, [rbp+3Fh+SelfRelativeSecurityDescriptor]
0x1800aae55  test    rax, rax
0x1800aae58  jnz     loc_1800AB0B6
0x1800aae5e  mov     rax, [rbp+3Fh+arg_18]
0x1800aae62  test    rax, rax
0x1800aae65  jnz     loc_1800AAF4E
0x1800aae6b  xor     r9d, r9d; bDaclDefaulted
0x1800aae6e  mov     r8, rdi; pDacl
0x1800aae71  mov     rcx, r13; pSecurityDescriptor
0x1800aae74  lea     edx, [r9+1]; bDaclPresent
0x1800aae78  call    SetSecurityDescriptorDacl
0x1800aae7d  test    eax, eax
0x1800aae7f  jz      loc_1800AAF30
0x1800aae85  xor     r8d, r8d; bOwnerDefaulted
0x1800aae88  mov     rdx, r14; pOwner
0x1800aae8b  mov     rcx, r13; pSecurityDescriptor
0x1800aae8e  call    SetSecurityDescriptorOwner
0x1800aae93  test    eax, eax
0x1800aae95  jz      loc_1800AAF3A
0x1800aae9b  xor     r8d, r8d; bGroupDefaulted
0x1800aae9e  mov     rdx, r14; pGroup
0x1800aaea1  mov     rcx, r13; pSecurityDescriptor
0x1800aaea4  call    SetSecurityDescriptorGroup
0x1800aaea9  test    eax, eax
0x1800aaeab  jz      loc_1800AAF44
0x1800aaeb1  lea     r8, [rbp+3Fh+cbSid]; BufferLength
0x1800aaeb5  mov     [rbp+3Fh+cbSid], 0
0x1800aaebc  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1800aaebe  mov     rcx, r13; AbsoluteSecurityDescriptor
0x1800aaec1  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1800aaec7  test    eax, eax
0x1800aaec9  js      loc_1800AAF7A
0x1800aaecf  mov     r14d, 80070001h
0x1800aaed5  mov     edx, 21Eh; void *
0x1800aaeda  mov     rcx, [rbp+47h]; this
0x1800aaede  mov     r9d, r14d; char *
0x1800aaee1  mov     r8, r12; unsigned int
0x1800aaee4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aaee9  jmp     loc_1800AAB74
0x1800aaeee  mov     eax, [rbp+3Fh+cbSid]
0x1800aaef1  lea     r9, aSizeU; "Size %u"
0x1800aaef8  mov     rcx, [rbp+47h]; this
0x1800aaefc  mov     r8, r12; unsigned int
0x1800aaeff  mov     edx, 1E2h; void *
0x1800aaf04  mov     dword ptr [rsp+0D0h+var_B0], eax; char *
0x1800aaf08  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800aaf0d  jmp     loc_1800AAB71
0x1800aaf12  mov     edx, 1E9h
0x1800aaf17  jmp     loc_1800AAB65
0x1800aaf1c  mov     edx, 1F7h
0x1800aaf21  jmp     loc_1800AAB65
0x1800aaf26  mov     edx, 1FEh
0x1800aaf2b  jmp     loc_1800AAB65
0x1800aaf30  mov     edx, 215h
  ... truncated ...
```
