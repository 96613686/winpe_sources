# VpnCredRequireNgc

- ea: `0x1800e3684`
- end: `0x1800e3900`
- name: `VpnCredRequireNgc`
- size: `636`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800584e0`

## callees

- `0x180005e34`
- `0x18000bf70`
- `0x18003204c`
- `0x1800e32b4`
- `0x1800e3684`
- `0x1800e3d58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e36ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e36ff`
- `RPCRT4!RpcImpersonateClient` at `0x1800e3736`
- `RPCRT4!RpcImpersonateClient` at `0x1800e3736`
- `RPCRT4!RpcRevertToSelf` at `0x1800e3831`
- `RPCRT4!RpcRevertToSelf` at `0x1800e386f`
- `RPCRT4!RpcRevertToSelf` at `0x1800e3831`
- `RPCRT4!RpcRevertToSelf` at `0x1800e386f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e36f5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e36f5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e379c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e3829`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e379c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e3829`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e3884`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e3884`

## pseudocode

```c
__int64 __fastcall VpnCredRequireNgc(unsigned int a1, __int64 a2, void *a3, _DWORD *a4, __int64 a5, __int64 a6)
{
  DWORD LastError; // eax
  DWORD v11; // ebx
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  DWORD CertContext; // eax
  __int64 v16; // rdx
  const CERT_CONTEXT *v17; // rsi
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  DWORD v21; // eax
  struct _LIST_ENTRY *v22; // rcx
  PCCERT_CONTEXT pCertContext; // [rsp+70h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_dq(WPP_GLOBAL_Control[1].Flink, 10, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, a1, a3);
  }
  pCertContext = 0;
  if ( a3 )
  {
    if ( !ImpersonateLoggedOnUser(a3) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v11;
        v13 = 11;
        goto LABEL_10;
      }
    }
  }
  else
  {
    LastError = RpcImpersonateClient(0);
    v11 = LastError;
    if ( LastError )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v11;
      v13 = 12;
LABEL_10:
      WPP_SF_d(v12[1].Flink, v13, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, LastError);
      goto LABEL_41;
    }
  }
  CertContext = VpnGetCertContext(a1, a2, &pCertContext);
  v17 = pCertContext;
  v11 = CertContext;
  if ( CertContext )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_18;
    v19 = 13;
    goto LABEL_17;
  }
  CertContext = SCardCertToNgc(pCertContext, v16, a5);
  *a4 = 1;
  v11 = CertContext;
  if ( CertContext == -2146893783 || CertContext == -2146893808 )
  {
    *a4 = 0;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 14, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, CertContext);
    }
    v11 = 0;
  }
  else if ( CertContext )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      v19 = 15;
LABEL_17:
      WPP_SF_d(v18[1].Flink, v19, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, CertContext);
    }
LABEL_18:
    if ( a3 )
      RevertToSelf();
    else
      RpcRevertToSelf();
    goto LABEL_38;
  }
  if ( *a4 != 1 )
    goto LABEL_18;
  if ( a3 )
    RevertToSelf();
  else
    RpcRevertToSelf();
  v21 = SCardCertToNgc(v17, v20, a6);
  v11 = v21;
  if ( !v21 )
    goto LABEL_38;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 16, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v21);
LABEL_38:
    v22 = WPP_GLOBAL_Control;
  }
  if ( !v17 )
    goto LABEL_42;
  CertFreeCertificateContext(v17);
LABEL_41:
  v22 = WPP_GLOBAL_Control;
LABEL_42:
  if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( SBYTE4(v22[1].Blink) < 0 && BYTE1(v22[1].Blink) >= 5u )
    {
      LOBYTE(v14) = *a4 != 0;
      WPP_SF_c(v22[1].Flink, 17, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v14);
      v22 = WPP_GLOBAL_Control;
    }
    if ( v22 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v22[1].Blink) < 0 && BYTE1(v22[1].Blink) >= 6u )
      WPP_SF_d(v22[1].Flink, 18, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1800e3684  mov     [rsp+arg_0], rbx
0x1800e3689  mov     [rsp+arg_8], rbp
0x1800e368e  push    rsi
0x1800e368f  push    rdi
0x1800e3690  push    r12
0x1800e3692  push    r13
0x1800e3694  push    r14
0x1800e3696  sub     rsp, 30h
0x1800e369a  mov     r14, r9
0x1800e369d  mov     rdi, r8
0x1800e36a0  mov     rbp, rdx
0x1800e36a3  mov     esi, ecx
0x1800e36a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e36ac  lea     r12, WPP_GLOBAL_Control
0x1800e36b3  lea     r13, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e36ba  cmp     rcx, r12
0x1800e36bd  jz      short loc_1800E36E4
0x1800e36bf  test    byte ptr [rcx+1Ch], 80h
0x1800e36c3  jz      short loc_1800E36E4
0x1800e36c5  cmp     byte ptr [rcx+19h], 6
0x1800e36c9  jb      short loc_1800E36E4
0x1800e36cb  mov     rcx, [rcx+10h]
0x1800e36cf  mov     edx, 0Ah
0x1800e36d4  mov     [rsp+58h+var_38], r8
0x1800e36d9  mov     r9d, esi
0x1800e36dc  mov     r8, r13
0x1800e36df  call    WPP_SF_dq
0x1800e36e4  mov     [rsp+58h+pCertContext], 0
0x1800e36ed  test    rdi, rdi
0x1800e36f0  jz      short loc_1800E3734
0x1800e36f2  mov     rcx, rdi; hToken
0x1800e36f5  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e36fb  test    eax, eax
0x1800e36fd  jnz     short loc_1800E3759
0x1800e36ff  call    cs:__imp_GetLastError
0x1800e3705  mov     ebx, eax
0x1800e3707  test    eax, eax
0x1800e3709  jz      short loc_1800E3759
0x1800e370b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3712  cmp     rcx, r12
0x1800e3715  jz      loc_1800E38E7
0x1800e371b  mov     edx, 0Bh
0x1800e3720  mov     rcx, [rcx+10h]
0x1800e3724  mov     r9d, eax
0x1800e3727  mov     r8, r13
0x1800e372a  call    WPP_SF_d
0x1800e372f  jmp     loc_1800E388A
0x1800e3734  xor     ecx, ecx; BindingHandle
0x1800e3736  call    cs:__imp_RpcImpersonateClient
0x1800e373c  mov     ebx, eax
0x1800e373e  test    eax, eax
0x1800e3740  jz      short loc_1800E3759
0x1800e3742  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3749  cmp     rcx, r12
0x1800e374c  jz      loc_1800E38E7
0x1800e3752  mov     edx, 0Ch
0x1800e3757  jmp     short loc_1800E3720
0x1800e3759  lea     r8, [rsp+58h+pCertContext]
0x1800e375e  mov     rdx, rbp
0x1800e3761  mov     ecx, esi
0x1800e3763  call    VpnGetCertContext
0x1800e3768  mov     rsi, [rsp+58h+pCertContext]
0x1800e376d  mov     ebx, eax
0x1800e376f  test    eax, eax
0x1800e3771  jz      short loc_1800E37A7
0x1800e3773  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e377a  cmp     rcx, r12
0x1800e377d  jz      short loc_1800E3793
0x1800e377f  mov     edx, 0Dh
0x1800e3784  mov     rcx, [rcx+10h]
0x1800e3788  mov     r9d, eax
0x1800e378b  mov     r8, r13
0x1800e378e  call    WPP_SF_d
0x1800e3793  test    rdi, rdi
0x1800e3796  jz      loc_1800E386F
0x1800e379c  call    cs:__imp_RevertToSelf
0x1800e37a2  jmp     loc_1800E3875
0x1800e37a7  mov     r8, [rsp+58h+arg_20]
0x1800e37af  mov     rcx, rsi
0x1800e37b2  call    SCardCertToNgc
0x1800e37b7  mov     dword ptr [r14], 1
0x1800e37be  mov     ebx, eax
0x1800e37c0  cmp     eax, 80090029h
0x1800e37c5  jz      short loc_1800E37E5
0x1800e37c7  cmp     eax, 80090010h
0x1800e37cc  jz      short loc_1800E37E5
0x1800e37ce  test    eax, eax
0x1800e37d0  jz      short loc_1800E381A
0x1800e37d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e37d9  cmp     rcx, r12
0x1800e37dc  jz      short loc_1800E3793
0x1800e37de  mov     edx, 0Fh
0x1800e37e3  jmp     short loc_1800E3784
0x1800e37e5  mov     dword ptr [r14], 0
0x1800e37ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e37f3  cmp     rcx, r12
0x1800e37f6  jz      short loc_1800E3818
0x1800e37f8  test    byte ptr [rcx+1Ch], 80h
0x1800e37fc  jz      short loc_1800E3818
0x1800e37fe  cmp     byte ptr [rcx+19h], 5
0x1800e3802  jb      short loc_1800E3818
0x1800e3804  mov     rcx, [rcx+10h]
0x1800e3808  mov     edx, 0Eh
0x1800e380d  mov     r9d, eax
0x1800e3810  mov     r8, r13
0x1800e3813  call    WPP_SF_d
0x1800e3818  xor     ebx, ebx
0x1800e381a  cmp     dword ptr [r14], 1
0x1800e381e  jnz     loc_1800E3793
0x1800e3824  test    rdi, rdi
0x1800e3827  jz      short loc_1800E3831
0x1800e3829  call    cs:__imp_RevertToSelf
0x1800e382f  jmp     short loc_1800E3837
0x1800e3831  call    cs:__imp_RpcRevertToSelf
0x1800e3837  mov     r8, [rsp+58h+arg_28]
0x1800e383f  mov     rcx, rsi
0x1800e3842  call    SCardCertToNgc
0x1800e3847  mov     ebx, eax
0x1800e3849  test    eax, eax
0x1800e384b  jz      short loc_1800E3875
0x1800e384d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3854  cmp     rcx, r12
0x1800e3857  jz      short loc_1800E387C
0x1800e3859  mov     rcx, [rcx+10h]
0x1800e385d  mov     edx, 10h
0x1800e3862  mov     r9d, eax
0x1800e3865  mov     r8, r13
0x1800e3868  call    WPP_SF_d
0x1800e386d  jmp     short loc_1800E3875
0x1800e386f  call    cs:__imp_RpcRevertToSelf
0x1800e3875  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e387c  test    rsi, rsi
0x1800e387f  jz      short loc_1800E3891
0x1800e3881  mov     rcx, rsi; pCertContext
0x1800e3884  call    cs:__imp_CertFreeCertificateContext
0x1800e388a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3891  cmp     rcx, r12
0x1800e3894  jz      short loc_1800E38E7
0x1800e3896  test    byte ptr [rcx+1Ch], 80h
0x1800e389a  jz      short loc_1800E38C2
0x1800e389c  cmp     byte ptr [rcx+19h], 5
0x1800e38a0  jb      short loc_1800E38C2
0x1800e38a2  cmp     dword ptr [r14], 0
0x1800e38a6  mov     edx, 11h
0x1800e38ab  mov     rcx, [rcx+10h]
0x1800e38af  mov     r8, r13
0x1800e38b2  setnz   r9b
0x1800e38b6  call    WPP_SF_c
0x1800e38bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e38c2  cmp     rcx, r12
0x1800e38c5  jz      short loc_1800E38E7
0x1800e38c7  test    byte ptr [rcx+1Ch], 80h
0x1800e38cb  jz      short loc_1800E38E7
0x1800e38cd  cmp     byte ptr [rcx+19h], 6
0x1800e38d1  jb      short loc_1800E38E7
0x1800e38d3  mov     rcx, [rcx+10h]
0x1800e38d7  mov     edx, 12h
0x1800e38dc  mov     r9d, ebx
0x1800e38df  mov     r8, r13
0x1800e38e2  call    WPP_SF_d
0x1800e38e7  mov     rbp, [rsp+58h+arg_8]
0x1800e38ec  mov     eax, ebx
0x1800e38ee  mov     rbx, [rsp+58h+arg_0]
0x1800e38f3  add     rsp, 30h
0x1800e38f7  pop     r14
0x1800e38f9  pop     r13
0x1800e38fb  pop     r12
0x1800e38fd  pop     rdi
0x1800e38fe  pop     rsi
0x1800e38ff  retn
```
