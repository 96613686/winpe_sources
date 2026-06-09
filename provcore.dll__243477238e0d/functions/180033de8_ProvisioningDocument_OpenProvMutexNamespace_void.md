# ProvisioningDocument::OpenProvMutexNamespace(void *)

- ea: `0x180033de8`
- end: `0x1800340c1`
- name: `?OpenProvMutexNamespace@ProvisioningDocument@@AEAAJPEAX@Z`
- size: `729`
- prototype: `HRESULT __fastcall(ProvisioningDocument *this, void *pSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800333fc`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x180033de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033f4d`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180033e84`
- `api-ms-win-core-namespace-l1-1-0!AddSIDToBoundaryDescriptor` at `0x180033e84`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180033f08`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180033f08`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180033f3b`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180033f3b`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180033e13`
- `api-ms-win-core-namespace-l1-1-0!CreateBoundaryDescriptorW` at `0x180033e13`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180033ed1`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180033ed1`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180033ee5`

## pseudocode

```c
HRESULT __fastcall ProvisioningDocument::OpenProvMutexNamespace(ProvisioningDocument *this, void *pSid)
{
  DWORD LastError; // eax
  HRESULT result; // eax
  DWORD v6; // eax
  void *v7; // rcx
  int v8; // r14d
  HANDLE v9; // rax
  HANDLE PrivateNamespaceW; // rax
  DWORD v11; // eax
  signed int v12; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v13; // rcx
  unsigned __int16 v14; // dx
  char v15; // al
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+20h] [rbp-48h] BYREF
  void *hBoundaryDescriptor; // [rsp+38h] [rbp-30h] BYREF

  hBoundaryDescriptor = CreateBoundaryDescriptorW(L"ProvisioningBoundary", 0);
  if ( !hBoundaryDescriptor )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Cu, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, LastError);
    }
LABEL_5:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !AddSIDToBoundaryDescriptor(&hBoundaryDescriptor, pSid) )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      v6 = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Du, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, v6);
    }
    DeleteBoundaryDescriptor(hBoundaryDescriptor);
    goto LABEL_5;
  }
  v7 = hBoundaryDescriptor;
  v8 = 10;
  j.fun_ = (void (__fastcall *)(void *))DeleteBoundaryDescriptor;
  j.p1_ = (WWAN_INTERFACE_OBJECT *const)hBoundaryDescriptor;
  j.dismissed_ = 0;
  while ( 1 )
  {
    v9 = OpenPrivateNamespaceW(v7, L"Provisioning");
    this->m_hProvNamespace = v9;
    if ( !v9 )
      break;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v14 = 50;
      goto LABEL_27;
    }
LABEL_28:
    if ( this->m_hProvNamespace || !v8 )
    {
      v15 = 0;
LABEL_41:
      if ( this->m_hProvNamespace || v15 )
      {
        v12 = 0;
      }
      else
      {
        if ( v13 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v13->ReserveSpace[28] & 2) != 0 )
          WPP_SF_(v13->Control.Logger, 0x33u, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
        v12 = -2147467259;
      }
      goto LABEL_48;
    }
    v7 = hBoundaryDescriptor;
  }
  if ( GetLastError() == 52 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Eu, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    v15 = 1;
    goto LABEL_41;
  }
  PrivateNamespaceW = CreatePrivateNamespaceW(0, hBoundaryDescriptor, L"Provisioning");
  this->m_hProvNamespace = PrivateNamespaceW;
  if ( PrivateNamespaceW )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      v14 = 49;
LABEL_27:
      WPP_SF_(v13->Control.Logger, v14, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
      v13 = WPP_GLOBAL_Control;
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  v11 = GetLastError();
  v12 = v11;
  if ( v11 == 183 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x2Fu, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    --v8;
    goto LABEL_28;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x30u, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids, v11);
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_48:
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  return v12;
}

```

## disassembly

```asm
0x180033de8  mov     [rsp+arg_10], rbx
0x180033ded  push    rbp
0x180033dee  push    rdi
0x180033def  push    r14
0x180033df1  sub     rsp, 50h
0x180033df5  mov     rax, cs:__security_cookie
0x180033dfc  xor     rax, rsp
0x180033dff  mov     [rsp+68h+var_28], rax
0x180033e04  mov     rbx, pSid
0x180033e07  mov     rbp, this
0x180033e0a  xor     edx, edx; Flags
0x180033e0c  lea     this, aProvisioningbo; "ProvisioningBoundary"
0x180033e13  call    cs:__imp_CreateBoundaryDescriptorW
0x180033e19  mov     [rsp+68h+hBoundaryDescriptor], rax
0x180033e1e  test    rax, rax
0x180033e21  jnz     short loc_180033E7C
0x180033e23  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033e2a  lea     rdi, WPP_GLOBAL_Control
0x180033e31  cmp     rax, rdi
0x180033e34  jz      short loc_180033E61
0x180033e36  test    byte ptr [rax+1Ch], 2
0x180033e3a  jz      short loc_180033E61
0x180033e3c  call    cs:__imp_GetLastError
0x180033e42  mov     this, cs:WPP_GLOBAL_Control
0x180033e49  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033e50  mov     edx, 2Ch ; ','; id
0x180033e55  mov     r9d, eax; _a1
0x180033e58  mov     this, [this+10h]; Logger
0x180033e5c  call    WPP_SF_d
0x180033e61  call    cs:__imp_GetLastError
0x180033e67  test    eax, eax
0x180033e69  jle     loc_1800340A3
0x180033e6f  movzx   eax, ax
0x180033e72  or      eax, 80070000h
0x180033e77  jmp     loc_1800340A3
0x180033e7c  mov     pSid, rbx; RequiredSid
0x180033e7f  lea     this, [rsp+68h+hBoundaryDescriptor]; BoundaryDescriptor
0x180033e84  call    cs:__imp_AddSIDToBoundaryDescriptor
0x180033e8a  test    eax, eax
0x180033e8c  jnz     short loc_180033ED9
0x180033e8e  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033e95  lea     rdi, WPP_GLOBAL_Control
0x180033e9c  cmp     rax, rdi
0x180033e9f  jz      short loc_180033ECC
0x180033ea1  test    byte ptr [rax+1Ch], 2
0x180033ea5  jz      short loc_180033ECC
0x180033ea7  call    cs:__imp_GetLastError
0x180033ead  mov     this, cs:WPP_GLOBAL_Control
0x180033eb4  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033ebb  mov     edx, 2Dh ; '-'; id
0x180033ec0  mov     r9d, eax; _a1
0x180033ec3  mov     this, [this+10h]; Logger
0x180033ec7  call    WPP_SF_d
0x180033ecc  mov     this, [rsp+68h+hBoundaryDescriptor]; BoundaryDescriptor
0x180033ed1  call    cs:__imp_DeleteBoundaryDescriptor
0x180033ed7  jmp     short loc_180033E61
0x180033ed9  mov     this, [rsp+68h+hBoundaryDescriptor]; lpBoundaryDescriptor
0x180033ede  lea     rdi, WPP_GLOBAL_Control
0x180033ee5  mov     rax, cs:__imp_DeleteBoundaryDescriptor
0x180033eec  mov     r14d, 0Ah
0x180033ef2  mov     [rsp+68h+j.fun_], rax
0x180033ef7  mov     [rsp+68h+j.p1_], this
0x180033efc  mov     [rsp+68h+j.dismissed_], 0
0x180033f01  lea     pSid, AliasPrefix; "Provisioning"
0x180033f08  call    cs:__imp_OpenPrivateNamespaceW
0x180033f0e  mov     [rbp+80h], rax
0x180033f15  test    rax, rax
0x180033f18  jnz     loc_180033FAC
0x180033f1e  call    cs:__imp_GetLastError
0x180033f24  cmp     eax, 34h ; '4'
0x180033f27  jz      loc_18003402C
0x180033f2d  mov     pSid, [rsp+68h+hBoundaryDescriptor]; lpBoundaryDescriptor
0x180033f32  lea     r8, AliasPrefix; "Provisioning"
0x180033f39  xor     ecx, ecx; lpPrivateNamespaceAttributes
0x180033f3b  call    cs:__imp_CreatePrivateNamespaceW
0x180033f41  mov     [rbp+80h], rax
0x180033f48  test    rax, rax
0x180033f4b  jnz     short loc_180033F93
0x180033f4d  call    cs:__imp_GetLastError
0x180033f53  mov     ebx, eax
0x180033f55  cmp     eax, 0B7h
0x180033f5a  jnz     loc_180033FF3
0x180033f60  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033f67  cmp     this, rdi
0x180033f6a  jz      short loc_180033F8E
0x180033f6c  test    byte ptr [this+1Ch], 10h
0x180033f70  jz      short loc_180033F8E
0x180033f72  mov     this, [this+10h]; Logger
0x180033f76  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033f7d  mov     edx, 2Fh ; '/'; id
0x180033f82  call    WPP_SF_
0x180033f87  mov     this, cs:WPP_GLOBAL_Control
0x180033f8e  dec     r14d
0x180033f91  jmp     short loc_180033FDA
0x180033f93  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033f9a  cmp     this, rdi
0x180033f9d  jz      short loc_180033FDA
0x180033f9f  test    byte ptr [this+1Ch], 10h
0x180033fa3  jz      short loc_180033FDA
0x180033fa5  mov     edx, 31h ; '1'
0x180033faa  jmp     short loc_180033FC3
0x180033fac  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033fb3  cmp     this, rdi
0x180033fb6  jz      short loc_180033FDA
0x180033fb8  test    byte ptr [this+1Ch], 10h
0x180033fbc  jz      short loc_180033FDA
0x180033fbe  mov     edx, 32h ; '2'; id
0x180033fc3  mov     this, [this+10h]; Logger
0x180033fc7  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180033fce  call    WPP_SF_
0x180033fd3  mov     this, cs:WPP_GLOBAL_Control
0x180033fda  cmp     qword ptr [rbp+80h], 0
0x180033fe2  jnz     short loc_18003405E
0x180033fe4  test    r14d, r14d
0x180033fe7  jz      short loc_18003405E
0x180033fe9  mov     this, [rsp+68h+hBoundaryDescriptor]
0x180033fee  jmp     loc_180033F01
0x180033ff3  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180033ffa  cmp     this, rdi
0x180033ffd  jz      short loc_18003401D
0x180033fff  test    byte ptr [this+1Ch], 2
0x180034003  jz      short loc_18003401D
0x180034005  mov     this, [this+10h]; Logger
0x180034009  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180034010  mov     edx, 30h ; '0'; id
0x180034015  mov     r9d, ebx; _a1
0x180034018  call    WPP_SF_d
0x18003401d  test    ebx, ebx
0x18003401f  jle     short loc_180034097
0x180034021  movzx   ebx, bx
0x180034024  or      ebx, 80070000h
0x18003402a  jmp     short loc_180034097
0x18003402c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180034033  cmp     this, rdi
0x180034036  jz      short loc_18003405A
0x180034038  test    byte ptr [this+1Ch], 10h
0x18003403c  jz      short loc_18003405A
0x18003403e  mov     this, [this+10h]; Logger
0x180034042  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180034049  mov     edx, 2Eh ; '.'; id
0x18003404e  call    WPP_SF_
0x180034053  mov     this, cs:WPP_GLOBAL_Control
0x18003405a  mov     al, 1
0x18003405c  jmp     short loc_180034060
0x18003405e  xor     al, al
0x180034060  cmp     qword ptr [rbp+80h], 0
0x180034068  jnz     short loc_180034095
0x18003406a  test    al, al
0x18003406c  jnz     short loc_180034095
0x18003406e  cmp     this, rdi; __annotation("TMF:",
0x180034071  jz      short loc_18003408E
0x180034073  test    byte ptr [this+1Ch], 2
0x180034077  jz      short loc_18003408E
0x180034079  mov     this, [this+10h]; Logger
0x18003407d  lea     r8, WPP_c2cb335829b637d2e69068cbb01b90a7_Traceguids; TraceGuid
0x180034084  mov     edx, 33h ; '3'; id
0x180034089  call    WPP_SF_
0x18003408e  mov     ebx, 80004005h
0x180034093  jmp     short loc_180034097
0x180034095  xor     ebx, ebx
0x180034097  lea     this, [rsp+68h+j]; j
0x18003409c  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x1800340a1  mov     eax, ebx
0x1800340a3  mov     this, [rsp+68h+var_28]
0x1800340a8  xor     this, rsp; StackCookie
0x1800340ab  call    __security_check_cookie
0x1800340b0  mov     rbx, [rsp+68h+arg_10]
0x1800340b8  add     rsp, 50h
0x1800340bc  pop     r14
0x1800340be  pop     rdi
0x1800340bf  pop     rbp
0x1800340c0  retn
```
