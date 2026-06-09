# AppContainerRegistration::CreateAppContainerKeySecurityDescriptor(_GUID const *,void *,void *,void *,ulong,ulong *,void * *,ushort *)

- ea: `0x1800b7f9c`
- end: `0x1800b8702`
- name: `?CreateAppContainerKeySecurityDescriptor@AppContainerRegistration@@CAJPEBU_GUID@@PEAX11KPEAKPEAPEAXPEAG@Z`
- size: `1894`
- prototype: `static int(const struct _GUID *, void *, void *, void *, unsigned int, unsigned int *, void **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18012a034`
- `0x18012a1f8`

## callees

- `0x1800129d0`
- `0x18004b9d0`
- `0x180056dc0`
- `0x180057738`
- `0x18005997c`
- `0x18005b2c4`
- `0x1800a1904`
- `0x1800ac008`
- `0x1800b7f9c`
- `0x1800b8710`
- `0x1800b8ad0`
- `0x1800b8e60`
- `0x1800b8e90`
- `0x1800b8ec0`
- `0x1800b8ef0`
- `0x1800b8f20`
- `0x18012a1e8`
- `0x18013045c`
- `0x18013d748`
- `0x18015f2d0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800b816f`
- `ntdll!RtlLengthSid` at `0x1800b8181`
- `ntdll!RtlLengthSid` at `0x1800b8193`
- `ntdll!RtlLengthSid` at `0x1800b81a6`
- `ntdll!RtlLengthSid` at `0x1800b867e`
- `ntdll!RtlLengthSid` at `0x1800b869a`
- `ntdll!RtlLengthSid` at `0x1800b816f`
- `ntdll!RtlLengthSid` at `0x1800b8181`
- `ntdll!RtlLengthSid` at `0x1800b8193`
- `ntdll!RtlLengthSid` at `0x1800b81a6`
- `ntdll!RtlLengthSid` at `0x1800b867e`
- `ntdll!RtlLengthSid` at `0x1800b869a`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800b83d8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800b84e8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800b83d8`
- `ntdll!RtlAbsoluteToSelfRelativeSD` at `0x1800b84e8`

## string_xrefs

- `0x1800b81d0`: `CreateAppContainerKeySD %ul mask 0x%0x %d %d `

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
  ACL *v17; // rcx
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
  int v34; // eax
  PSID v35; // r13
  const char *v36; // r9
  PSID v37; // rcx
  int v38; // eax
  ACL *v39; // rdi
  const char *v40; // r9
  PSID v41; // r14
  NTSTATUS v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  PSECURITY_DESCRIPTOR v45; // r14
  NTSTATUS v46; // eax
  signed int v47; // r12d
  bool v48; // sf
  ULONG v49; // eax
  ULONG v50; // eax
  int v51; // [rsp+28h] [rbp-81h]
  const char *v52; // [rsp+28h] [rbp-81h]
  const char *v53; // [rsp+28h] [rbp-81h]
  char *v54; // [rsp+30h] [rbp-79h]
  char *v55; // [rsp+30h] [rbp-79h]
  DWORD cbSid; // [rsp+48h] [rbp-61h] BYREF
  PSID Sid; // [rsp+50h] [rbp-59h] BYREF
  PSID pSid[2]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v59[128]; // [rsp+68h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+47h]
  const struct _GUID *v61; // [rsp+F8h] [rbp+4Fh] BYREF
  PSID pOwner; // [rsp+100h] [rbp+57h]
  PSECURITY_DESCRIPTOR SelfRelativeSecurityDescriptor; // [rsp+108h] [rbp+5Fh] BYREF
  PSID v64; // [rsp+110h] [rbp+67h]

  v64 = a4;
  SelfRelativeSecurityDescriptor = a3;
  pOwner = a2;
  v61 = a1;
  lambda_f6d66e2938cd7d2db6473c74ebbf57c0_::_lambda_f6d66e2938cd7d2db6473c74ebbf57c0_(pSid, &v61);
  wil::ThreadFailureCallback__lambda_cb404202719105b885c5aa52f19c21f0___((struct wil::details::IFailureCallback *)v59);
  pSid[0] = 0;
  cbSid = 68;
  v10 = (a4 != 0) + 5;
  if ( !a3 )
    v10 = (a4 != 0) + 4;
  v11 = Common::GlobalHeap::Alloc(0x44u, pSid);
  v12 = pSid[0];
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)(unsigned int)v11,
      v51);
    goto LABEL_15;
  }
  if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid[0], &cbSid) )
  {
    cbSid = 68;
    Sid = 0;
    v21 = Common::GlobalHeap::Alloc(0x44u, &Sid);
    LastError = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
        (const char *)(unsigned int)v21,
        v51);
      v19 = Sid;
      goto LABEL_14;
    }
    v22 = Sid;
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, Sid, &cbSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1B9,
                    (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                    v23);
      goto LABEL_13;
    }
    Sid = 0;
    cbSid = 68;
    v24 = Common::GlobalHeap::Alloc(0x44u, &Sid);
    LastError = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
        (const char *)(unsigned int)v24,
        v51);
      v18 = Sid;
      goto LABEL_12;
    }
    v25 = Sid;
    if ( !CreateWellKnownSid(WinCreatorOwnerSid, 0, Sid, &cbSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1C2,
                    (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                    v26);
      goto LABEL_11;
    }
    pSid[0] = 0;
    cbSid = 12 * v10 + 8;
    v27 = RtlLengthSid(v22);
    cbSid += v27;
    v28 = RtlLengthSid(v25);
    cbSid += v28;
    v29 = RtlLengthSid(v12);
    cbSid += v29;
    v30 = RtlLengthSid(pOwner);
    v31 = v30 + cbSid;
    cbSid += v30;
    if ( a4 )
    {
      v49 = RtlLengthSid(a4);
      v31 = v49 + cbSid;
      cbSid += v49;
    }
    if ( a3 )
    {
      v50 = RtlLengthSid(a3);
      v31 = v50 + cbSid;
    }
    v32 = (v31 + 3) & 0xFFFFFFFC;
    cbSid = v32;
    v33 = StringCchPrintfA(
            a8,
            0x104u,
            "CreateAppContainerKeySD %ul mask 0x%0x %d %d ",
            v32,
            AccessMask,
            a3 != 0,
            a4 != 0);
    LODWORD(v54) = v32;
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
      (const char *)v33,
      (int)"StringCchPrintf %ul 0x%0x",
      v54);
    Sid = 0;
    v34 = Common::GlobalHeap::Alloc(0x28u, &Sid);
    LastError = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DD,
        (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
        (const char *)(unsigned int)v34,
        (int)v52);
      v37 = Sid;
      goto LABEL_29;
    }
    v35 = Sid;
    if ( !InitializeSecurityDescriptor(Sid, 1u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1DE,
                    (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                    v36);
      v37 = v35;
LABEL_29:
      Common::GlobalHeap::Free(v37);
      v17 = 0;
      goto LABEL_10;
    }
    v38 = Common::GlobalHeap::Alloc(cbSid, pSid);
    LastError = v38;
    if ( v38 < 0 )
    {
      LODWORD(v55) = cbSid;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1E1,
        (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
        (const char *)(unsigned int)v38,
        (int)"Size %u",
        v55);
      Common::GlobalHeap::Free(v35);
      v17 = (ACL *)pSid[0];
      goto LABEL_10;
    }
    v39 = (ACL *)pSid[0];
    if ( !InitializeAcl((PACL)pSid[0], cbSid, 2u) )
    {
      LODWORD(v52) = cbSid;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x1E2,
                       (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                       "Size %u",
                       v52);
      goto LABEL_8;
    }
    if ( AddAccessAllowedAceEx(v39, 2u, 3u, 0xF003Fu, v12) )
    {
      if ( AddAccessAllowedAceEx(v39, 2u, 3u, 0x20019u, v25) )
      {
        if ( AddAccessAllowedAceEx(v39, 2u, 3u, 0xF003Fu, v22) )
        {
          v41 = pOwner;
          if ( AddAccessAllowedAceEx(v39, 2u, 3u, 0xF003Fu, pOwner) )
          {
            if ( SelfRelativeSecurityDescriptor
              && !AddAccessAllowedAceEx(v39, 2u, 3u, 0xF003Fu, SelfRelativeSecurityDescriptor) )
            {
              v15 = 519;
              goto LABEL_7;
            }
            if ( v64 && !AddAccessAllowedAceEx(v39, 2u, 3u, AccessMask, v64) )
            {
              v15 = 529;
              goto LABEL_7;
            }
            if ( SetSecurityDescriptorDacl(v35, 1, v39, 0) )
            {
              if ( SetSecurityDescriptorOwner(v35, v41, 0) )
              {
                if ( SetSecurityDescriptorGroup(v35, v41, 0) )
                {
                  cbSid = 0;
                  if ( v35 )
                  {
                    v42 = RtlAbsoluteToSelfRelativeSD(v35, 0, &cbSid);
                    if ( v42 >= 0 )
                    {
                      LastError = -2147024895;
                      v43 = 542;
                      goto LABEL_44;
                    }
                  }
                  else
                  {
                    v42 = -1073741811;
                  }
                  BaseSetLastNTError((unsigned int)v42);
                  LastError = NtCurrentTeb()->LastErrorValue;
                  if ( LastError == 122 )
                  {
                    SelfRelativeSecurityDescriptor = 0;
                    v44 = Common::GlobalHeap::Alloc(cbSid, &SelfRelativeSecurityDescriptor);
                    LastError = v44;
                    if ( v44 >= 0 )
                    {
                      v45 = SelfRelativeSecurityDescriptor;
                      if ( v35 )
                      {
                        v46 = RtlAbsoluteToSelfRelativeSD(v35, SelfRelativeSecurityDescriptor, &cbSid);
                        if ( v46 >= 0 )
                        {
                          *a6 = -2147483641;
                          *a7 = v45;
                          Common::GlobalHeap::Free(0);
                          Common::GlobalHeap::Free(v35);
                          Common::GlobalHeap::Free(v39);
                          Common::GlobalHeap::Free(v25);
                          Common::GlobalHeap::Free(v22);
                          LastError = 0;
                          goto LABEL_15;
                        }
                      }
                      else
                      {
                        v46 = -1073741811;
                      }
                      BaseSetLastNTError((unsigned int)v46);
                      LODWORD(v53) = cbSid;
                      v47 = wil::details::in1diag3::Return_GetLastErrorMsg(
                              retaddr,
                              (void *)0x224,
                              (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                              "Size %u",
                              v53);
                      Common::GlobalHeap::Free(v45);
                      Common::GlobalHeap::Free(v35);
                      Common::GlobalHeap::Free(v39);
                      Common::GlobalHeap::Free(v25);
                      Common::GlobalHeap::Free(v22);
                      LastError = v47;
                      goto LABEL_15;
                    }
                    LODWORD(v55) = cbSid;
                    wil::details::in1diag3::Return_HrMsg(
                      retaddr,
                      (void *)0x223,
                      (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                      (const char *)(unsigned int)v44,
                      (int)"Size %u",
                      v55);
                    Common::GlobalHeap::Free(SelfRelativeSecurityDescriptor);
                    goto LABEL_9;
                  }
                  v48 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v48 = LastError < 0;
                  }
                  if ( !v48 )
                  {
LABEL_9:
                    Common::GlobalHeap::Free(v35);
                    v17 = v39;
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
                  v43 = 544;
LABEL_44:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v43,
                    (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                    (const char *)(unsigned int)LastError,
                    (int)v53);
                  goto LABEL_9;
                }
                v15 = 535;
              }
              else
              {
                v15 = 534;
              }
            }
            else
            {
              v15 = 533;
            }
          }
          else
          {
            v15 = 510;
          }
        }
        else
        {
          v15 = 503;
        }
      }
      else
      {
        v15 = 496;
      }
    }
    else
    {
      v15 = 489;
    }
LABEL_7:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)v15,
                     (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                     v40);
LABEL_8:
    LastError = LastErrorMsg;
    goto LABEL_9;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"onecore\\base\\appmodel\\appcontainerregistration\\appcontainerregistration.cpp",
                v14);
LABEL_15:
  Common::GlobalHeap::Free(v12);
  wil::details::ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___::_ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___(v59);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800b7f9c  mov     rax, rsp
0x1800b7f9f  mov     [rax+20h], r9
0x1800b7fa3  mov     [rax+18h], r8
0x1800b7fa7  mov     [rax+10h], rdx
0x1800b7fab  mov     [rax+8], rcx
0x1800b7faf  push    rbp
0x1800b7fb0  push    rbx
0x1800b7fb1  push    rsi
0x1800b7fb2  push    rdi
0x1800b7fb3  push    r12
0x1800b7fb5  push    r13
0x1800b7fb7  push    r14
0x1800b7fb9  push    r15
0x1800b7fbb  lea     rbp, [rax-47h]
0x1800b7fbf  sub     rsp, 0A8h
0x1800b7fc6  lea     rdx, [rbp+3Fh+arg_0]
0x1800b7fca  mov     r13, r9
0x1800b7fcd  lea     rcx, [rbp+3Fh+pSid]
0x1800b7fd1  mov     r12, r8
0x1800b7fd4  call    _lambda_f6d66e2938cd7d2db6473c74ebbf57c0____lambda_f6d66e2938cd7d2db6473c74ebbf57c0_
0x1800b7fd9  mov     rdx, rax
0x1800b7fdc  lea     rcx, [rbp+3Fh+var_80]; struct wil::details::IFailureCallback *
0x1800b7fe0  call    wil__ThreadFailureCallback__lambda_cb404202719105b885c5aa52f19c21f0___
0x1800b7fe5  mov     rax, r13
0x1800b7fe8  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800b7fec  neg     rax
0x1800b7fef  sbb     ecx, ecx
0x1800b7ff1  xor     esi, esi
0x1800b7ff3  neg     ecx
0x1800b7ff5  mov     [rbp+3Fh+pSid], rsi
0x1800b7ff9  add     ecx, 4
0x1800b7ffc  test    r12, r12
0x1800b7fff  lea     ebx, [rsi+44h]
0x1800b8002  mov     [rbp+3Fh+cbSid], ebx
0x1800b8005  lea     edi, [rcx+1]
0x1800b8008  cmovz   edi, ecx
0x1800b800b  mov     ecx, ebx; Size
0x1800b800d  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800b8012  mov     r15, [rbp+3Fh+pSid]
0x1800b8016  mov     r14d, eax
0x1800b8019  test    eax, eax
0x1800b801b  js      loc_1800B8596
0x1800b8021  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800b8025  mov     r8, r15; pSid
0x1800b8028  xor     edx, edx; DomainSid
0x1800b802a  lea     ecx, [rsi+16h]; WellKnownSidType
0x1800b802d  call    CreateWellKnownSid
0x1800b8032  test    eax, eax
0x1800b8034  jnz     short loc_1800B80AD
0x1800b8036  mov     rcx, [rbp+47h]; this
0x1800b803a  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800b8041  mov     edx, 1B0h; void *
0x1800b8046  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b804b  mov     r14d, eax
0x1800b804e  jmp     short loc_1800B8084
0x1800b8050  mov     edx, 1F0h; void *
0x1800b8055  mov     rcx, [rbp+47h]; this
0x1800b8059  mov     r8, r12; unsigned int
0x1800b805c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b8061  mov     r14d, eax
0x1800b8064  mov     rcx, r13; void *
0x1800b8067  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b806c  mov     rcx, rdi; void *
0x1800b806f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b8074  mov     rcx, rsi; void *
0x1800b8077  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b807c  mov     rcx, rbx; void *
0x1800b807f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b8084  mov     rcx, r15; void *
0x1800b8087  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b808c  lea     rcx, [rbp+3Fh+var_80]
0x1800b8090  call    wil__details__ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0______ThreadFailureCallbackFn__lambda_f6d66e2938cd7d2db6473c74ebbf57c0___
0x1800b8095  mov     eax, r14d
0x1800b8098  add     rsp, 0A8h
0x1800b809f  pop     r15
0x1800b80a1  pop     r14
0x1800b80a3  pop     r13
0x1800b80a5  pop     r12
0x1800b80a7  pop     rdi
0x1800b80a8  pop     rsi
0x1800b80a9  pop     rbx
0x1800b80aa  pop     rbp
0x1800b80ab  retn
0x1800b80ad  lea     rdx, [rbp+3Fh+Sid]; void **
0x1800b80b1  mov     [rbp+3Fh+cbSid], ebx
0x1800b80b4  mov     rcx, rbx; Size
0x1800b80b7  mov     [rbp+3Fh+Sid], rsi
0x1800b80bb  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800b80c0  mov     r14d, eax
0x1800b80c3  test    eax, eax
0x1800b80c5  js      loc_1800B8639
0x1800b80cb  mov     rbx, [rbp+3Fh+Sid]
0x1800b80cf  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800b80d3  xor     edx, edx; DomainSid
0x1800b80d5  mov     r8, rbx; pSid
0x1800b80d8  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800b80db  call    CreateWellKnownSid
0x1800b80e0  test    eax, eax
0x1800b80e2  jnz     short loc_1800B8101
0x1800b80e4  mov     rcx, [rbp+47h]; this
0x1800b80e8  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800b80ef  mov     edx, 1B9h; void *
0x1800b80f4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b80f9  mov     r14d, eax
0x1800b80fc  jmp     loc_1800B807C
0x1800b8101  mov     ecx, 44h ; 'D'; Size
0x1800b8106  mov     [rbp+3Fh+Sid], rsi
0x1800b810a  lea     rdx, [rbp+3Fh+Sid]; void **
0x1800b810e  mov     [rbp+3Fh+cbSid], ecx
0x1800b8111  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800b8116  mov     r14d, eax
0x1800b8119  test    eax, eax
0x1800b811b  js      loc_1800B865A
0x1800b8121  mov     rsi, [rbp+3Fh+Sid]
0x1800b8125  lea     r9, [rbp+3Fh+cbSid]; cbSid
0x1800b8129  xor     edx, edx; DomainSid
0x1800b812b  mov     r8, rsi; pSid
0x1800b812e  lea     ecx, [rdx+3]; WellKnownSidType
0x1800b8131  call    CreateWellKnownSid
0x1800b8136  test    eax, eax
0x1800b8138  jnz     short loc_1800B8157
0x1800b813a  mov     rcx, [rbp+47h]; this
0x1800b813e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800b8145  mov     edx, 1C2h; void *
0x1800b814a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b814f  mov     r14d, eax
0x1800b8152  jmp     loc_1800B8074
0x1800b8157  lea     eax, [rdi+rdi*2]
0x1800b815a  mov     [rbp+3Fh+pSid], 0
0x1800b8162  lea     eax, ds:8[rax*4]
0x1800b8169  mov     rcx, rbx; Sid
0x1800b816c  mov     [rbp+3Fh+cbSid], eax
0x1800b816f  call    cs:__imp_RtlLengthSid
0x1800b8176  nop     dword ptr [rax+rax+00h]
0x1800b817b  add     [rbp+3Fh+cbSid], eax
0x1800b817e  mov     rcx, rsi; Sid
0x1800b8181  call    cs:__imp_RtlLengthSid
0x1800b8188  nop     dword ptr [rax+rax+00h]
0x1800b818d  add     [rbp+3Fh+cbSid], eax
0x1800b8190  mov     rcx, r15; Sid
0x1800b8193  call    cs:__imp_RtlLengthSid
0x1800b819a  nop     dword ptr [rax+rax+00h]
0x1800b819f  mov     rcx, [rbp+3Fh+pOwner]; Sid
0x1800b81a3  add     [rbp+3Fh+cbSid], eax
0x1800b81a6  call    cs:__imp_RtlLengthSid
0x1800b81ad  nop     dword ptr [rax+rax+00h]
0x1800b81b2  mov     edi, [rbp+3Fh+cbSid]
0x1800b81b5  add     edi, eax
0x1800b81b7  mov     [rbp+3Fh+cbSid], edi
0x1800b81ba  test    r13, r13
0x1800b81bd  jnz     loc_1800B867B
0x1800b81c3  test    r12, r12
0x1800b81c6  jnz     loc_1800B8697
0x1800b81cc  mov     r14d, [rbp+3Fh+AccessMask]
0x1800b81d0  lea     r8, aCreateappconta_7; "CreateAppContainerKeySD %ul mask 0x%0x "...
0x1800b81d7  xor     ecx, ecx
0x1800b81d9  add     edi, 3
0x1800b81dc  and     edi, 0FFFFFFFCh
0x1800b81df  mov     edx, 104h; unsigned __int64
0x1800b81e4  test    r13, r13
0x1800b81e7  mov     [rbp+3Fh+cbSid], edi
0x1800b81ea  mov     r9d, edi
0x1800b81ed  setnz   cl
0x1800b81f0  xor     eax, eax
0x1800b81f2  mov     [rsp+30h], ecx
0x1800b81f6  test    r12, r12
0x1800b81f9  mov     rcx, [rbp+3Fh+arg_38]; char *
0x1800b8200  setnz   al
0x1800b8203  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800b8207  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x1800b820c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800b8211  mov     rcx, [rbp+47h]; this
0x1800b8215  lea     rdx, aStringcchprint; "StringCchPrintf %ul 0x%0x"
0x1800b821c  mov     [rsp+30h], r14d
0x1800b8221  lea     r12, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\appcontainerre"...
0x1800b8228  mov     dword ptr [rsp+0E0h+var_B8], edi; char *
0x1800b822c  mov     r9d, eax; char *
0x1800b822f  mov     [rsp+0E0h+var_C0], rdx; int
0x1800b8234  mov     r8, r12; unsigned int
0x1800b8237  mov     edx, 1DAh; void *
0x1800b823c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800b8241  lea     rdx, [rbp+3Fh+Sid]; void **
0x1800b8245  mov     [rbp+3Fh+Sid], 0
0x1800b824d  mov     ecx, 28h ; '('; Size
0x1800b8252  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800b8257  mov     r14d, eax
0x1800b825a  test    eax, eax
0x1800b825c  js      loc_1800B86B0
0x1800b8262  mov     r13, [rbp+3Fh+Sid]
0x1800b8266  mov     edx, 1; dwRevision
0x1800b826b  mov     rcx, r13; pSecurityDescriptor
0x1800b826e  call    InitializeSecurityDescriptor
0x1800b8273  test    eax, eax
0x1800b8275  jnz     short loc_1800B829A
0x1800b8277  mov     rcx, [rbp+47h]; this
0x1800b827b  mov     r8, r12; unsigned int
0x1800b827e  mov     edx, 1DEh; void *
0x1800b8283  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b8288  mov     r14d, eax
0x1800b828b  mov     rcx, r13; void *
0x1800b828e  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800b8293  xor     ecx, ecx
0x1800b8295  jmp     loc_1800B806F
0x1800b829a  mov     ecx, [rbp+3Fh+cbSid]; Size
0x1800b829d  lea     rdx, [rbp+3Fh+pSid]; void **
0x1800b82a1  call    ?Alloc@GlobalHeap@Common@@SAJ_KPEAPEAX@Z; Common::GlobalHeap::Alloc(unsigned __int64,void * *)
0x1800b82a6  mov     edx, [rbp+3Fh+cbSid]; nAclLength
0x1800b82a9  mov     r14d, eax
0x1800b82ac  test    eax, eax
0x1800b82ae  js      loc_1800B85B3
0x1800b82b4  mov     rdi, [rbp+3Fh+pSid]
0x1800b82b8  mov     r14d, 2
0x1800b82be  mov     r8d, r14d; dwAclRevision
0x1800b82c1  mov     rcx, rdi; pAcl
0x1800b82c4  call    InitializeAcl
0x1800b82c9  test    eax, eax
0x1800b82cb  jz      loc_1800B840B
0x1800b82d1  mov     r9d, 0F003Fh; AccessMask
0x1800b82d7  mov     [rsp+0E0h+var_C0], r15; pSid
0x1800b82dc  lea     r8d, [r14+1]; AceFlags
0x1800b82e0  mov     edx, r14d; dwAceRevision
0x1800b82e3  mov     rcx, rdi; pAcl
0x1800b82e6  call    AddAccessAllowedAceEx
0x1800b82eb  test    eax, eax
0x1800b82ed  jz      loc_1800B842F
0x1800b82f3  mov     r9d, 20019h; AccessMask
0x1800b82f9  mov     [rsp+0E0h+var_C0], rsi; pSid
0x1800b82fe  lea     r8d, [r14+1]; AceFlags
0x1800b8302  mov     edx, r14d; dwAceRevision
0x1800b8305  mov     rcx, rdi; pAcl
0x1800b8308  call    AddAccessAllowedAceEx
0x1800b830d  test    eax, eax
0x1800b830f  jz      loc_1800B8050
0x1800b8315  mov     r9d, 0F003Fh; AccessMask
0x1800b831b  mov     [rsp+0E0h+var_C0], rbx; pSid
0x1800b8320  lea     r8d, [r14+1]; AceFlags
0x1800b8324  mov     edx, r14d; dwAceRevision
0x1800b8327  mov     rcx, rdi; pAcl
0x1800b832a  call    AddAccessAllowedAceEx
0x1800b832f  test    eax, eax
0x1800b8331  jz      loc_1800B8439
0x1800b8337  mov     r14, [rbp+3Fh+pOwner]
0x1800b833b  mov     edx, 2; dwAceRevision
0x1800b8340  mov     r9d, 0F003Fh; AccessMask
0x1800b8346  mov     [rsp+0E0h+var_C0], r14; int
0x1800b834b  mov     rcx, rdi; pAcl
0x1800b834e  lea     r8d, [rdx+1]; AceFlags
0x1800b8352  call    AddAccessAllowedAceEx
0x1800b8357  test    eax, eax
0x1800b8359  jz      loc_1800B8443
0x1800b835f  mov     rax, [rbp+3Fh+SelfRelativeSecurityDescriptor]
0x1800b8363  test    rax, rax
0x1800b8366  jnz     loc_1800B85E8
0x1800b836c  mov     rax, [rbp+3Fh+arg_18]
0x1800b8370  test    rax, rax
0x1800b8373  jnz     loc_1800B846B
0x1800b8379  xor     r9d, r9d; bDaclDefaulted
0x1800b837c  mov     r8, rdi; pDacl
0x1800b837f  mov     rcx, r13; pSecurityDescriptor
0x1800b8382  lea     edx, [r9+1]; bDaclPresent
0x1800b8386  call    SetSecurityDescriptorDacl
0x1800b838b  test    eax, eax
0x1800b838d  jz      loc_1800B844D
0x1800b8393  xor     r8d, r8d; bOwnerDefaulted
0x1800b8396  mov     rdx, r14; pOwner
0x1800b8399  mov     rcx, r13; pSecurityDescriptor
0x1800b839c  call    SetSecurityDescriptorOwner
0x1800b83a1  test    eax, eax
0x1800b83a3  jz      loc_1800B8457
0x1800b83a9  xor     r8d, r8d; bGroupDefaulted
0x1800b83ac  mov     rdx, r14; pGroup
0x1800b83af  mov     rcx, r13; pSecurityDescriptor
0x1800b83b2  call    SetSecurityDescriptorGroup
0x1800b83b7  test    eax, eax
0x1800b83b9  jz      loc_1800B8461
0x1800b83bf  mov     [rbp+3Fh+cbSid], 0
0x1800b83c6  test    r13, r13
0x1800b83c9  jz      loc_1800B8497
0x1800b83cf  lea     r8, [rbp+3Fh+cbSid]; BufferLength
0x1800b83d3  xor     edx, edx; SelfRelativeSecurityDescriptor
0x1800b83d5  mov     rcx, r13; AbsoluteSecurityDescriptor
0x1800b83d8  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1800b83df  nop     dword ptr [rax+rax+00h]
0x1800b83e4  test    eax, eax
0x1800b83e6  js      loc_1800B849C
0x1800b83ec  mov     r14d, 80070001h
0x1800b83f2  mov     edx, 21Eh; void *
0x1800b83f7  mov     rcx, [rbp+47h]; this
0x1800b83fb  mov     r9d, r14d; char *
0x1800b83fe  mov     r8, r12; unsigned int
0x1800b8401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8406  jmp     loc_1800B8064
0x1800b840b  mov     eax, [rbp+3Fh+cbSid]
0x1800b840e  lea     r9, aSizeU; "Size %u"
0x1800b8415  mov     rcx, [rbp+47h]; this
0x1800b8419  mov     r8, r12; unsigned int
0x1800b841c  mov     edx, 1E2h; void *
0x1800b8421  mov     dword ptr [rsp+0E0h+var_C0], eax; char *
0x1800b8425  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800b842a  jmp     loc_1800B8061
  ... truncated ...
```
