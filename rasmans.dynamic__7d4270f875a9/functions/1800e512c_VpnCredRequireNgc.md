# VpnCredRequireNgc

- ea: `0x1800e512c`
- end: `0x1800e53d9`
- name: `VpnCredRequireNgc`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b06c`

## callees

- `0x180005bfc`
- `0x18000c37c`
- `0x180033654`
- `0x1800e4d0c`
- `0x1800e512c`
- `0x1800e5858`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e51ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e51ad`
- `RPCRT4!RpcImpersonateClient` at `0x1800e51ea`
- `RPCRT4!RpcImpersonateClient` at `0x1800e51ea`
- `RPCRT4!RpcRevertToSelf` at `0x1800e52f7`
- `RPCRT4!RpcRevertToSelf` at `0x1800e533b`
- `RPCRT4!RpcRevertToSelf` at `0x1800e52f7`
- `RPCRT4!RpcRevertToSelf` at `0x1800e533b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e519d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800e519d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5256`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e52e9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e5256`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e52e9`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e5356`
- `CRYPT32!CertFreeCertificateContext` at `0x1800e5356`

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
0x1800e512c  mov     [rsp+arg_0], rbx
0x1800e5131  mov     [rsp+arg_8], rbp
0x1800e5136  push    rsi
0x1800e5137  push    rdi
0x1800e5138  push    r12
0x1800e513a  push    r13
0x1800e513c  push    r14
0x1800e513e  sub     rsp, 30h
0x1800e5142  mov     r14, r9
0x1800e5145  mov     rdi, r8
0x1800e5148  mov     rbp, rdx
0x1800e514b  mov     esi, ecx
0x1800e514d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5154  lea     r12, WPP_GLOBAL_Control
0x1800e515b  lea     r13, WPP_78ade74619a93ad44c469a263d1f5015_Traceguids
0x1800e5162  cmp     rcx, r12
0x1800e5165  jz      short loc_1800E518C
0x1800e5167  test    byte ptr [rcx+1Ch], 80h
0x1800e516b  jz      short loc_1800E518C
0x1800e516d  cmp     byte ptr [rcx+19h], 6
0x1800e5171  jb      short loc_1800E518C
0x1800e5173  mov     rcx, [rcx+10h]
0x1800e5177  mov     edx, 0Ah
0x1800e517c  mov     [rsp+58h+var_38], r8
0x1800e5181  mov     r9d, esi
0x1800e5184  mov     r8, r13
0x1800e5187  call    WPP_SF_dq
0x1800e518c  mov     [rsp+58h+pCertContext], 0
0x1800e5195  test    rdi, rdi
0x1800e5198  jz      short loc_1800E51E8
0x1800e519a  mov     rcx, rdi; hToken
0x1800e519d  call    cs:__imp_ImpersonateLoggedOnUser
0x1800e51a4  nop     dword ptr [rax+rax+00h]
0x1800e51a9  test    eax, eax
0x1800e51ab  jnz     short loc_1800E5213
0x1800e51ad  call    cs:__imp_GetLastError
0x1800e51b4  nop     dword ptr [rax+rax+00h]
0x1800e51b9  mov     ebx, eax
0x1800e51bb  test    eax, eax
0x1800e51bd  jz      short loc_1800E5213
0x1800e51bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e51c6  cmp     rcx, r12
0x1800e51c9  jz      loc_1800E53BF
0x1800e51cf  mov     edx, 0Bh
0x1800e51d4  mov     rcx, [rcx+10h]
0x1800e51d8  mov     r9d, eax
0x1800e51db  mov     r8, r13
0x1800e51de  call    WPP_SF_d
0x1800e51e3  jmp     loc_1800E5362
0x1800e51e8  xor     ecx, ecx; BindingHandle
0x1800e51ea  call    cs:__imp_RpcImpersonateClient
0x1800e51f1  nop     dword ptr [rax+rax+00h]
0x1800e51f6  mov     ebx, eax
0x1800e51f8  test    eax, eax
0x1800e51fa  jz      short loc_1800E5213
0x1800e51fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5203  cmp     rcx, r12
0x1800e5206  jz      loc_1800E53BF
0x1800e520c  mov     edx, 0Ch
0x1800e5211  jmp     short loc_1800E51D4
0x1800e5213  lea     r8, [rsp+58h+pCertContext]
0x1800e5218  mov     rdx, rbp
0x1800e521b  mov     ecx, esi
0x1800e521d  call    VpnGetCertContext
0x1800e5222  mov     rsi, [rsp+58h+pCertContext]
0x1800e5227  mov     ebx, eax
0x1800e5229  test    eax, eax
0x1800e522b  jz      short loc_1800E5267
0x1800e522d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5234  cmp     rcx, r12
0x1800e5237  jz      short loc_1800E524D
0x1800e5239  mov     edx, 0Dh
0x1800e523e  mov     rcx, [rcx+10h]
0x1800e5242  mov     r9d, eax
0x1800e5245  mov     r8, r13
0x1800e5248  call    WPP_SF_d
0x1800e524d  test    rdi, rdi
0x1800e5250  jz      loc_1800E533B
0x1800e5256  call    cs:__imp_RevertToSelf
0x1800e525d  nop     dword ptr [rax+rax+00h]
0x1800e5262  jmp     loc_1800E5347
0x1800e5267  mov     r8, [rsp+58h+arg_20]
0x1800e526f  mov     rcx, rsi
0x1800e5272  call    SCardCertToNgc
0x1800e5277  mov     dword ptr [r14], 1
0x1800e527e  mov     ebx, eax
0x1800e5280  cmp     eax, 80090029h
0x1800e5285  jz      short loc_1800E52A5
0x1800e5287  cmp     eax, 80090010h
0x1800e528c  jz      short loc_1800E52A5
0x1800e528e  test    eax, eax
0x1800e5290  jz      short loc_1800E52DA
0x1800e5292  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5299  cmp     rcx, r12
0x1800e529c  jz      short loc_1800E524D
0x1800e529e  mov     edx, 0Fh
0x1800e52a3  jmp     short loc_1800E523E
0x1800e52a5  mov     dword ptr [r14], 0
0x1800e52ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e52b3  cmp     rcx, r12
0x1800e52b6  jz      short loc_1800E52D8
0x1800e52b8  test    byte ptr [rcx+1Ch], 80h
0x1800e52bc  jz      short loc_1800E52D8
0x1800e52be  cmp     byte ptr [rcx+19h], 5
0x1800e52c2  jb      short loc_1800E52D8
0x1800e52c4  mov     rcx, [rcx+10h]
0x1800e52c8  mov     edx, 0Eh
0x1800e52cd  mov     r9d, eax
0x1800e52d0  mov     r8, r13
0x1800e52d3  call    WPP_SF_d
0x1800e52d8  xor     ebx, ebx
0x1800e52da  cmp     dword ptr [r14], 1
0x1800e52de  jnz     loc_1800E524D
0x1800e52e4  test    rdi, rdi
0x1800e52e7  jz      short loc_1800E52F7
0x1800e52e9  call    cs:__imp_RevertToSelf
0x1800e52f0  nop     dword ptr [rax+rax+00h]
0x1800e52f5  jmp     short loc_1800E5303
0x1800e52f7  call    cs:__imp_RpcRevertToSelf
0x1800e52fe  nop     dword ptr [rax+rax+00h]
0x1800e5303  mov     r8, [rsp+58h+arg_28]
0x1800e530b  mov     rcx, rsi
0x1800e530e  call    SCardCertToNgc
0x1800e5313  mov     ebx, eax
0x1800e5315  test    eax, eax
0x1800e5317  jz      short loc_1800E5347
0x1800e5319  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5320  cmp     rcx, r12
0x1800e5323  jz      short loc_1800E534E
0x1800e5325  mov     rcx, [rcx+10h]
0x1800e5329  mov     edx, 10h
0x1800e532e  mov     r9d, eax
0x1800e5331  mov     r8, r13
0x1800e5334  call    WPP_SF_d
0x1800e5339  jmp     short loc_1800E5347
0x1800e533b  call    cs:__imp_RpcRevertToSelf
0x1800e5342  nop     dword ptr [rax+rax+00h]
0x1800e5347  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e534e  test    rsi, rsi
0x1800e5351  jz      short loc_1800E5369
0x1800e5353  mov     rcx, rsi; pCertContext
0x1800e5356  call    cs:__imp_CertFreeCertificateContext
0x1800e535d  nop     dword ptr [rax+rax+00h]
0x1800e5362  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e5369  cmp     rcx, r12
0x1800e536c  jz      short loc_1800E53BF
0x1800e536e  test    byte ptr [rcx+1Ch], 80h
0x1800e5372  jz      short loc_1800E539A
0x1800e5374  cmp     byte ptr [rcx+19h], 5
0x1800e5378  jb      short loc_1800E539A
0x1800e537a  cmp     dword ptr [r14], 0
0x1800e537e  mov     edx, 11h
0x1800e5383  mov     rcx, [rcx+10h]
0x1800e5387  mov     r8, r13
0x1800e538a  setnz   r9b
0x1800e538e  call    WPP_SF_c
0x1800e5393  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e539a  cmp     rcx, r12
0x1800e539d  jz      short loc_1800E53BF
0x1800e539f  test    byte ptr [rcx+1Ch], 80h
0x1800e53a3  jz      short loc_1800E53BF
0x1800e53a5  cmp     byte ptr [rcx+19h], 6
0x1800e53a9  jb      short loc_1800E53BF
0x1800e53ab  mov     rcx, [rcx+10h]
0x1800e53af  mov     edx, 12h
0x1800e53b4  mov     r9d, ebx
0x1800e53b7  mov     r8, r13
0x1800e53ba  call    WPP_SF_d
0x1800e53bf  mov     rbp, [rsp+58h+arg_8]
0x1800e53c4  mov     eax, ebx
0x1800e53c6  mov     rbx, [rsp+58h+arg_0]
0x1800e53cb  add     rsp, 30h
0x1800e53cf  pop     r14
0x1800e53d1  pop     r13
0x1800e53d3  pop     r12
0x1800e53d5  pop     rdi
0x1800e53d6  pop     rsi
0x1800e53d7  retn
```
