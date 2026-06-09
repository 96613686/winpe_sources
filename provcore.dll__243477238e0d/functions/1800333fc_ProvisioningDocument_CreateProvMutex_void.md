# ProvisioningDocument::CreateProvMutex(void)

- ea: `0x1800333fc`
- end: `0x18003374b`
- name: `?CreateProvMutex@ProvisioningDocument@@AEAAJXZ`
- size: `847`
- prototype: `HRESULT __fastcall(ProvisioningDocument *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180033304`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x1800333fc`
- `0x180033de8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800334fc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800334b8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800334b8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800336b4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800336b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003347a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003353f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003347a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003353f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033564`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800335dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336e7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033594`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180033594`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180033432`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180033432`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800334ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800334ad`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003360f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18003360f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033656`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180033656`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003351c`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18003351c`

## pseudocode

```c
HRESULT __fastcall ProvisioningDocument::CreateProvMutex(ProvisioningDocument *this)
{
  DWORD LastError; // eax
  HRESULT result; // eax
  DWORD v4; // edi
  WWAN_INTERFACE_OBJECT *v5; // rbx
  DWORD v6; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  DWORD v9; // eax
  unsigned __int16 v10; // dx
  signed int v11; // eax
  HANDLE v12; // rax
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+20h] [rbp-89h] BYREF
  _SECURITY_ATTRIBUTES secAttr; // [rsp+38h] [rbp-71h] BYREF
  unsigned int sidSize; // [rsp+50h] [rbp-59h] BYREF
  _SECURITY_DESCRIPTOR secDesc; // [rsp+58h] [rbp-51h] BYREF
  unsigned __int8 sidBuffer[68]; // [rsp+80h] [rbp-29h] BYREF

  sidSize = 68;
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, sidBuffer, &sidSize) )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, LastError);
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = ProvisioningDocument::OpenProvMutexNamespace(this, sidBuffer);
  if ( result < 0 )
    return result;
  v4 = GetLengthSid(sidBuffer) + 20;
  v5 = (WWAN_INTERFACE_OBJECT *)malloc(v4);
  if ( v5 )
  {
    j.fun_ = (void (__fastcall *)(void *))free;
    j.dismissed_ = 0;
    j.p1_ = v5;
    if ( !InitializeAcl((PACL)v5, v4, 2u) )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        v6 = GetLastError();
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x26u, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, v6);
      }
      v7 = GetLastError();
      v8 = v7;
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_43:
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
      return v8;
    }
    if ( AddAccessAllowedAce((PACL)v5, 2u, 0x1F0001u, sidBuffer) )
    {
      memset(&secDesc, 0, sizeof(secDesc));
      if ( InitializeSecurityDescriptor(&secDesc, 1u) )
      {
        memset(&secAttr, 0, sizeof(secAttr));
        if ( SetSecurityDescriptorDacl(&secDesc, 1, (PACL)v5, 0) )
        {
          secAttr.nLength = 24;
          secAttr.lpSecurityDescriptor = &secDesc;
          secAttr.bInheritHandle = 0;
          v12 = CreateMutexW(&secAttr, 0, L"Provisioning\\ProvMutex");
          this->m_hProvMutex = v12;
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Bu, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
            }
            v8 = 0;
            goto LABEL_43;
          }
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
          {
            goto LABEL_24;
          }
          v9 = GetLastError();
          v10 = 42;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
          {
            goto LABEL_24;
          }
          v9 = GetLastError();
          v10 = 41;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
        {
          goto LABEL_24;
        }
        v9 = GetLastError();
        v10 = 40;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_24;
      }
      v9 = GetLastError();
      v10 = 39;
    }
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, v10, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, v9);
LABEL_24:
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v8 = v11;
    goto LABEL_43;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x25u, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
  }
  return -2147024882;
}

```

## disassembly

```asm
0x1800333fc  push    rbp
0x1800333fe  push    rbx
0x1800333ff  push    rsi
0x180033400  push    rdi
0x180033401  lea     rbp, [rsp-3Fh]
0x180033406  sub     rsp, 0E8h
0x18003340d  mov     rax, cs:__security_cookie
0x180033414  xor     rax, rsp
0x180033417  mov     [rbp+57h+var_30], rax
0x18003341b  xor     edx, edx; DomainSid
0x18003341d  mov     [rbp+57h+sidSize], 44h ; 'D'
0x180033424  mov     rsi, this
0x180033427  lea     r9, [rbp+57h+sidSize]; cbSid
0x18003342b  lea     r8, [rbp+57h+sidBuffer]; pSid
0x18003342f  lea     ecx, [rdx+17h]; WellKnownSidType
0x180033432  call    cs:__imp_CreateWellKnownSid
0x180033438  test    eax, eax
0x18003343a  jnz     short loc_180033495
0x18003343c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033443  lea     rax, WPP_GLOBAL_Control
0x18003344a  cmp     this, rax
0x18003344d  jz      short loc_18003347A
0x18003344f  test    byte ptr [this+1Ch], 2
0x180033453  jz      short loc_18003347A
0x180033455  call    cs:__imp_GetLastError
0x18003345b  mov     this, cs:WPP_GLOBAL_Control
0x180033462  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033469  mov     edx, 24h ; '$'; id
0x18003346e  mov     r9d, eax; _a1
0x180033471  mov     this, [this+10h]; Logger
0x180033475  call    WPP_SF_d
0x18003347a  call    cs:__imp_GetLastError
0x180033480  test    eax, eax
0x180033482  jle     loc_180033733
0x180033488  movzx   eax, ax
0x18003348b  or      eax, 80070000h
0x180033490  jmp     loc_180033733
0x180033495  lea     rdx, [rbp+57h+sidBuffer]; pSid
0x180033499  mov     this, rsi; this
0x18003349c  call    ?OpenProvMutexNamespace@ProvisioningDocument@@AEAAJPEAX@Z; ProvisioningDocument::OpenProvMutexNamespace(void *)
0x1800334a1  test    eax, eax
0x1800334a3  js      loc_180033733
0x1800334a9  lea     this, [rbp+57h+sidBuffer]; pSid
0x1800334ad  call    cs:__imp_GetLengthSid
0x1800334b3  lea     edi, [rax+14h]
0x1800334b6  mov     ecx, edi; Size
0x1800334b8  call    cs:__imp_malloc
0x1800334be  mov     rbx, rax
0x1800334c1  test    rax, rax
0x1800334c4  jnz     short loc_1800334FC
0x1800334c6  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800334cd  lea     rax, WPP_GLOBAL_Control
0x1800334d4  cmp     this, rax
0x1800334d7  jz      short loc_1800334F2
0x1800334d9  test    byte ptr [this+1Ch], 2
0x1800334dd  jz      short loc_1800334F2
0x1800334df  mov     this, [this+10h]; Logger
0x1800334e3  lea     edx, [rbx+25h]; id
0x1800334e6  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x1800334ed  call    WPP_SF_
0x1800334f2  mov     eax, 8007000Eh
0x1800334f7  jmp     loc_180033733
0x1800334fc  mov     rax, cs:__imp_free
0x180033503  mov     r8d, 2; dwAclRevision
0x180033509  mov     edx, edi; nAclLength
0x18003350b  mov     [rsp+100h+j.fun_], rax
0x180033510  mov     this, rbx; pAcl
0x180033513  mov     [rsp+100h+j.dismissed_], 0
0x180033518  mov     [rbp+57h+j.p1_], rbx
0x18003351c  call    cs:__imp_InitializeAcl
0x180033522  test    eax, eax
0x180033524  jnz     short loc_180033582
0x180033526  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003352d  lea     rax, WPP_GLOBAL_Control
0x180033534  cmp     this, rax
0x180033537  jz      short loc_180033564
0x180033539  test    byte ptr [this+1Ch], 2
0x18003353d  jz      short loc_180033564
0x18003353f  call    cs:__imp_GetLastError
0x180033545  mov     this, cs:WPP_GLOBAL_Control
0x18003354c  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033553  mov     edx, 26h ; '&'; id
0x180033558  mov     r9d, eax; _a1
0x18003355b  mov     this, [this+10h]; Logger
0x18003355f  call    WPP_SF_d
0x180033564  call    cs:__imp_GetLastError
0x18003356a  mov     ebx, eax
0x18003356c  test    eax, eax
0x18003356e  jle     loc_180033727
0x180033574  movzx   ebx, ax
0x180033577  or      ebx, 80070000h
0x18003357d  jmp     loc_180033727
0x180033582  lea     r9, [rbp+57h+sidBuffer]; pSid
0x180033586  mov     edx, 2; dwAceRevision
0x18003358b  mov     r8d, 1F0001h; AccessMask
0x180033591  mov     this, rbx; pAcl
0x180033594  call    cs:__imp_AddAccessAllowedAce
0x18003359a  test    eax, eax
0x18003359c  jnz     short loc_1800335F5
0x18003359e  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800335a5  lea     rax, WPP_GLOBAL_Control
0x1800335ac  cmp     this, rax
0x1800335af  jz      short loc_1800335DC
0x1800335b1  test    byte ptr [this+1Ch], 2
0x1800335b5  jz      short loc_1800335DC
0x1800335b7  call    cs:__imp_GetLastError
0x1800335bd  mov     edx, 27h ; '''; id
0x1800335c2  mov     this, cs:WPP_GLOBAL_Control
0x1800335c9  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x1800335d0  mov     r9d, eax; _a1
0x1800335d3  mov     this, [this+10h]; Logger
0x1800335d7  call    WPP_SF_d
0x1800335dc  call    cs:__imp_GetLastError
0x1800335e2  test    eax, eax
0x1800335e4  jle     short loc_1800335EE
0x1800335e6  movzx   eax, ax
0x1800335e9  or      eax, 80070000h
0x1800335ee  mov     ebx, eax
0x1800335f0  jmp     loc_180033727
0x1800335f5  xor     eax, eax
0x1800335f7  lea     this, [rbp+57h+secDesc]; pSecurityDescriptor
0x1800335fb  xorps   xmm0, xmm0
0x1800335fe  mov     [rbp+57h+secDesc.Dacl], rax
0x180033602  movups  xmmword ptr [rbp+57h+secDesc.Revision], xmm0
0x180033606  lea     edi, [rax+1]
0x180033609  mov     edx, edi; dwRevision
0x18003360b  movups  xmmword ptr [rbp+57h+secDesc.Group], xmm0
0x18003360f  call    cs:__imp_InitializeSecurityDescriptor
0x180033615  test    eax, eax
0x180033617  jnz     short loc_18003363D
0x180033619  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033620  lea     rax, WPP_GLOBAL_Control
0x180033627  cmp     this, rax
0x18003362a  jz      short loc_1800335DC
0x18003362c  test    byte ptr [this+1Ch], 2
0x180033630  jz      short loc_1800335DC
0x180033632  call    cs:__imp_GetLastError
0x180033638  lea     edx, [rdi+27h]
0x18003363b  jmp     short loc_1800335C2
0x18003363d  xorps   xmm0, xmm0
0x180033640  lea     this, [rbp+57h+secDesc]; pSecurityDescriptor
0x180033644  xor     eax, eax
0x180033646  xor     r9d, r9d; bDaclDefaulted
0x180033649  mov     r8, rbx; pDacl
0x18003364c  mov     qword ptr [rbp+57h+secAttr.bInheritHandle], rax
0x180033650  mov     edx, edi; bDaclPresent
0x180033652  movups  xmmword ptr [rbp+57h+secAttr.nLength], xmm0
0x180033656  call    cs:__imp_SetSecurityDescriptorDacl
0x18003365c  test    eax, eax
0x18003365e  jnz     short loc_180033691
0x180033660  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033667  lea     rax, WPP_GLOBAL_Control
0x18003366e  cmp     this, rax
0x180033671  jz      loc_1800335DC
0x180033677  test    byte ptr [this+1Ch], 2
0x18003367b  jz      loc_1800335DC
0x180033681  call    cs:__imp_GetLastError
0x180033687  mov     edx, 29h ; ')'
0x18003368c  jmp     loc_1800335C2
0x180033691  lea     rax, [rbp+57h+secDesc]
0x180033695  mov     [rbp+57h+secAttr.nLength], 18h
0x18003369c  lea     r8, Name; "Provisioning\\ProvMutex"
0x1800336a3  mov     [rbp+57h+secAttr.lpSecurityDescriptor], rax
0x1800336a7  xor     edx, edx; bInitialOwner
0x1800336a9  mov     [rbp+57h+secAttr.bInheritHandle], 0
0x1800336b0  lea     this, [rbp+57h+secAttr]; lpMutexAttributes
0x1800336b4  call    cs:__imp_CreateMutexW
0x1800336ba  mov     [rsi+88h], rax
0x1800336c1  test    rax, rax
0x1800336c4  jnz     short loc_1800336F7
0x1800336c6  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800336cd  lea     rax, WPP_GLOBAL_Control
0x1800336d4  cmp     this, rax
0x1800336d7  jz      loc_1800335DC
0x1800336dd  test    byte ptr [this+1Ch], 2
0x1800336e1  jz      loc_1800335DC
0x1800336e7  call    cs:__imp_GetLastError
0x1800336ed  mov     edx, 2Ah ; '*'
0x1800336f2  jmp     loc_1800335C2
0x1800336f7  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800336fe  lea     rax, WPP_GLOBAL_Control
0x180033705  cmp     this, rax
0x180033708  jz      short loc_180033725
0x18003370a  test    byte ptr [this+1Ch], 10h
0x18003370e  jz      short loc_180033725
0x180033710  mov     this, [this+10h]; Logger
0x180033714  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x18003371b  mov     edx, 2Bh ; '+'; id
0x180033720  call    WPP_SF_
0x180033725  xor     ebx, ebx
0x180033727  lea     this, [rsp+100h+j]; j
0x18003372c  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180033731  mov     eax, ebx
0x180033733  mov     this, [rbp+57h+var_30]
0x180033737  xor     this, rsp; StackCookie
0x18003373a  call    __security_check_cookie
0x18003373f  add     rsp, 0E8h
0x180033746  pop     rdi
0x180033747  pop     rsi
0x180033748  pop     rbx
0x180033749  pop     rbp
0x18003374a  retn
```
