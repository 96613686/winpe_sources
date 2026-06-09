# EfspPostCreateImpersonateAndGetData

- ea: `0x140052604`
- end: `0x1400528b6`
- name: `EfspPostCreateImpersonateAndGetData`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14005202c`

## callees

- `0x14000a408`
- `0x14004e1e0`
- `0x140052604`
- `0x1400576c0`
- `0x1400577d4`
- `0x140057890`
- `0x140057adc`
- `0x14005823c`

## import_xrefs

- `ntoskrnl!PsRevertToSelf` at `0x140052896`
- `ntoskrnl!PsRevertToSelf` at `0x140052896`
- `ntoskrnl!PsImpersonateClient` at `0x1400526a3`
- `ntoskrnl!PsImpersonateClient` at `0x140052873`
- `ntoskrnl!PsImpersonateClient` at `0x1400526a3`
- `ntoskrnl!PsImpersonateClient` at `0x140052873`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005267b`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14005267b`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140052882`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140052882`

## pseudocode

```c
__int64 __fastcall EfspPostCreateImpersonateAndGetData(
        int *a1,
        void *a2,
        SECURITY_IMPERSONATION_LEVEL a3,
        __int64 a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _QWORD *a10)
{
  int v10; // ebx
  int v13; // r15d
  unsigned int *v14; // r12
  int *v15; // r14
  PACCESS_TOKEN v16; // r13
  NTSTATUS v17; // edi
  int v18; // ebx
  int v19; // ebx
  NTSTATUS DirEfsClient; // eax
  bool v21; // zf
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 CopyOnOpen; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-20h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+5Ch] [rbp-1Ch] BYREF
  __int64 v28; // [rsp+60h] [rbp-18h] BYREF
  _QWORD v29[2]; // [rsp+68h] [rbp-10h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+C0h] [rbp+48h] BYREF
  void *v31; // [rsp+C8h] [rbp+50h]
  SECURITY_IMPERSONATION_LEVEL v32; // [rsp+D0h] [rbp+58h]
  __int64 v33; // [rsp+D8h] [rbp+60h]

  v33 = a4;
  v32 = a3;
  v31 = a2;
  v10 = *a1;
  v26 = 0;
  v13 = 0;
  HIDWORD(CopyOnOpen) = 0;
  v14 = (unsigned int *)*((_QWORD *)a1 + 1);
  v28 = 0;
  v29[0] = 0;
  LOBYTE(CopyOnOpen) = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  if ( v14 )
    v26 = *v14;
  v15 = (int *)*((_QWORD *)a1 + 2);
  if ( v15 )
    v13 = *v15;
  v16 = PsReferenceImpersonationToken(KeGetCurrentThread(), (PBOOLEAN)&CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v17 = PsImpersonateClient(KeGetCurrentThread(), a2, 1u, 1u, v32);
  if ( v17 < 0 )
  {
    v22 = v29[0];
    goto LABEL_22;
  }
  HIDWORD(CopyOnOpen) = 1;
  v18 = (v10 & 0xFFFFFFF) - 1;
  if ( v18 )
  {
    v19 = v18 - 1;
    if ( v19 )
    {
      if ( v19 != 2 )
        goto LABEL_16;
      DirEfsClient = EfsDecryptFek(v29, v14, v26, (unsigned int)a1[6], v31, v33, a5, a7, a8, &v28, CopyOnOpen);
    }
    else
    {
      v21 = a1[7] == 3;
      v26 = 0;
      if ( v21 )
      {
        DirEfsClient = EfspConstructNewPfileHeader((_DWORD)v15, v13, (_DWORD)v31, 0, 0, (__int64)&v28, (__int64)&v26);
      }
      else
      {
        v17 = EfsWaitForServiceReady();
        if ( v17 < 0 )
          goto LABEL_16;
        DirEfsClient = EfsGenerateDirEfsClient(v13, (_DWORD)v15, a7, (unsigned int)&v26, (__int64)&v28);
      }
    }
  }
  else
  {
    DirEfsClient = EfsGenerateKey((_DWORD)v15, v13, a1[7], (_DWORD)v31, a6, a7, (__int64)v29, (__int64)&v28);
  }
  v17 = DirEfsClient;
LABEL_16:
  v22 = v29[0];
  if ( !v29[0] || *(_DWORD *)(v29[0] + 4LL) != 26115 || qword_140017948 )
  {
    *a10 = v28;
    v23 = 0;
    v28 = 0;
    *a9 = v22;
    v22 = 0;
    v29[0] = 0;
    goto LABEL_23;
  }
  v17 = -1073741790;
LABEL_22:
  v23 = v28;
LABEL_23:
  if ( v23 )
  {
    ((void (*)(void))FreeKRpcMemory)();
    v22 = v29[0];
  }
  if ( v22 )
  {
    if ( a1[6] == 3 || a1[7] == 3 )
      EfspClipSpFree(v22);
    else
      FreeKRpcMemory(v22);
  }
  if ( v16 )
  {
    if ( HIDWORD(CopyOnOpen) )
      PsImpersonateClient(KeGetCurrentThread(), v16, CopyOnOpen, EffectiveOnly, ImpersonationLevel);
    PsDereferenceImpersonationToken(v16);
  }
  else if ( HIDWORD(CopyOnOpen) )
  {
    PsRevertToSelf();
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140052604  mov     [rsp-40h+arg_18], r9
0x140052609  mov     [rsp-40h+arg_10], r8d
0x14005260e  mov     [rsp-40h+arg_8], rdx
0x140052613  push    rbp
0x140052614  push    rbx
0x140052615  push    rsi
0x140052616  push    rdi
0x140052617  push    r12
0x140052619  push    r13
0x14005261b  push    r14
0x14005261d  push    r15
0x14005261f  mov     rbp, rsp
0x140052622  sub     rsp, 78h
0x140052626  mov     ebx, [rcx]
0x140052628  mov     rsi, rcx
0x14005262b  xor     ecx, ecx
0x14005262d  mov     rdi, rdx
0x140052630  mov     [rbp+var_20], ecx
0x140052633  mov     r15d, ecx
0x140052636  mov     [rbp+var_24], ecx
0x140052639  mov     r12, [rsi+8]
0x14005263d  mov     [rbp+var_18], rcx
0x140052641  mov     [rbp+var_10], rcx
0x140052645  mov     [rbp+CopyOnOpen], cl
0x140052648  mov     [rbp+EffectiveOnly], cl
0x14005264b  mov     [rbp+ImpersonationLevel], ecx
0x14005264e  test    r12, r12
0x140052651  jz      short loc_14005265A
0x140052653  mov     eax, [r12]
0x140052657  mov     [rbp+var_20], eax
0x14005265a  mov     r14, [rsi+10h]
0x14005265e  test    r14, r14
0x140052661  jz      short loc_140052666
0x140052663  mov     r15d, [r14]
0x140052666  mov     rcx, gs:188h; Thread
0x14005266f  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x140052673  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x140052677  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14005267b  call    cs:__imp_PsReferenceImpersonationToken
0x140052682  nop     dword ptr [rax+rax+00h]
0x140052687  mov     rcx, gs:188h; Thread
0x140052690  mov     r9b, 1; EffectiveOnly
0x140052693  mov     r13, rax
0x140052696  mov     r8b, r9b; CopyOnOpen
0x140052699  mov     eax, [rbp+arg_10]
0x14005269c  mov     rdx, rdi; Token
0x14005269f  mov     [rsp+78h+var_58], eax; ImpersonationLevel
0x1400526a3  call    cs:__imp_PsImpersonateClient
0x1400526aa  nop     dword ptr [rax+rax+00h]
0x1400526af  mov     edi, eax
0x1400526b1  test    eax, eax
0x1400526b3  js      loc_140052814
0x1400526b9  and     ebx, 0FFFFFFFh
0x1400526bf  mov     [rbp+var_24], 1
0x1400526c6  sub     ebx, 1
0x1400526c9  jz      loc_140052794
0x1400526cf  sub     ebx, 1
0x1400526d2  jz      short loc_14005272F
0x1400526d4  cmp     ebx, 2
0x1400526d7  jnz     loc_1400527CB
0x1400526dd  mov     r9d, [rsi+18h]
0x1400526e1  lea     rax, [rbp+var_18]
0x1400526e5  mov     r8d, [rbp+var_20]
0x1400526e9  lea     rcx, [rbp+var_10]
0x1400526ed  mov     [rsp+78h+var_30], rax
0x1400526f2  mov     rdx, r12
0x1400526f5  mov     rax, [rbp+arg_38]
0x1400526fc  mov     [rsp+78h+var_38], rax
0x140052701  mov     rax, [rbp+arg_30]
0x140052705  mov     [rsp+78h+var_40], rax
0x14005270a  mov     rax, [rbp+arg_20]
0x14005270e  mov     [rsp+78h+var_48], rax
0x140052713  mov     rax, [rbp+arg_18]
0x140052717  mov     [rsp+78h+var_50], rax
0x14005271c  mov     rax, [rbp+arg_8]
0x140052720  mov     qword ptr [rsp+78h+var_58], rax
0x140052725  call    EfsDecryptFek
0x14005272a  jmp     loc_1400527C9
0x14005272f  cmp     dword ptr [rsi+1Ch], 3
0x140052733  mov     [rbp+var_20], 0
0x14005273a  jnz     short loc_14005276B
0x14005273c  mov     r8, [rbp+arg_8]
0x140052740  lea     rax, [rbp+var_20]
0x140052744  mov     [rsp+78h+var_48], rax
0x140052749  xor     r9d, r9d
0x14005274c  lea     rax, [rbp+var_18]
0x140052750  mov     edx, r15d
0x140052753  mov     [rsp+78h+var_50], rax
0x140052758  mov     rcx, r14
0x14005275b  mov     qword ptr [rsp+78h+var_58], 0
0x140052764  call    EfspConstructNewPfileHeader
0x140052769  jmp     short loc_1400527C9
0x14005276b  call    EfsWaitForServiceReady
0x140052770  mov     edi, eax
0x140052772  test    eax, eax
0x140052774  js      short loc_1400527CB
0x140052776  mov     r8, [rbp+arg_30]
0x14005277a  lea     rax, [rbp+var_18]
0x14005277e  lea     r9, [rbp+var_20]
0x140052782  mov     qword ptr [rsp+78h+var_58], rax
0x140052787  mov     rdx, r14
0x14005278a  mov     ecx, r15d
0x14005278d  call    EfsGenerateDirEfsClient
0x140052792  jmp     short loc_1400527C9
0x140052794  mov     r9, [rbp+arg_8]
0x140052798  lea     rax, [rbp+var_18]
0x14005279c  mov     r8d, [rsi+1Ch]
0x1400527a0  mov     edx, r15d
0x1400527a3  mov     [rsp+78h+var_40], rax
0x1400527a8  mov     rcx, r14
0x1400527ab  lea     rax, [rbp+var_10]
0x1400527af  mov     [rsp+78h+var_48], rax
0x1400527b4  mov     rax, [rbp+arg_30]
0x1400527b8  mov     [rsp+78h+var_50], rax
0x1400527bd  mov     al, [rbp+arg_28]
0x1400527c0  mov     byte ptr [rsp+78h+var_58], al
0x1400527c4  call    EfsGenerateKey
0x1400527c9  mov     edi, eax
0x1400527cb  mov     rdx, [rbp+var_10]
0x1400527cf  test    rdx, rdx
0x1400527d2  jz      short loc_1400527EE
0x1400527d4  cmp     dword ptr [rdx+4], 6603h
0x1400527db  jnz     short loc_1400527EE
0x1400527dd  cmp     cs:qword_140017948, 0
0x1400527e5  jnz     short loc_1400527EE
0x1400527e7  mov     edi, 0C0000022h
0x1400527ec  jmp     short loc_140052818
0x1400527ee  mov     rax, [rbp+var_18]
0x1400527f2  mov     rcx, [rbp+arg_48]
0x1400527f9  mov     [rcx], rax
0x1400527fc  xor     ecx, ecx
0x1400527fe  mov     rax, [rbp+arg_40]
0x140052805  mov     [rbp+var_18], rcx
0x140052809  mov     [rax], rdx
0x14005280c  xor     edx, edx
0x14005280e  mov     [rbp+var_10], rdx
0x140052812  jmp     short loc_14005281C
0x140052814  mov     rdx, [rbp+var_10]
0x140052818  mov     rcx, [rbp+var_18]
0x14005281c  test    rcx, rcx
0x14005281f  jz      short loc_14005282A
0x140052821  call    FreeKRpcMemory
0x140052826  mov     rdx, [rbp+var_10]
0x14005282a  test    rdx, rdx
0x14005282d  jz      short loc_14005284D
0x14005282f  cmp     dword ptr [rsi+18h], 3
0x140052833  jz      short loc_140052845
0x140052835  cmp     dword ptr [rsi+1Ch], 3
0x140052839  jz      short loc_140052845
0x14005283b  mov     rcx, rdx
0x14005283e  call    FreeKRpcMemory
0x140052843  jmp     short loc_14005284D
0x140052845  mov     rcx, rdx
0x140052848  call    EfspClipSpFree
0x14005284d  test    r13, r13
0x140052850  jz      short loc_140052890
0x140052852  cmp     [rbp+var_24], 0
0x140052856  jz      short loc_14005287F
0x140052858  mov     rcx, gs:188h; Thread
0x140052861  mov     rdx, r13; Token
0x140052864  mov     eax, [rbp+ImpersonationLevel]
0x140052867  mov     r9b, [rbp+EffectiveOnly]; EffectiveOnly
0x14005286b  mov     r8b, [rbp+CopyOnOpen]; CopyOnOpen
0x14005286f  mov     [rsp+78h+var_58], eax; ImpersonationLevel
0x140052873  call    cs:__imp_PsImpersonateClient
0x14005287a  nop     dword ptr [rax+rax+00h]
0x14005287f  mov     rcx, r13; ImpersonationToken
0x140052882  call    cs:__imp_PsDereferenceImpersonationToken
0x140052889  nop     dword ptr [rax+rax+00h]
0x14005288e  jmp     short loc_1400528A2
0x140052890  cmp     [rbp+var_24], 0
0x140052894  jz      short loc_1400528A2
0x140052896  call    cs:__imp_PsRevertToSelf
0x14005289d  nop     dword ptr [rax+rax+00h]
0x1400528a2  mov     eax, edi
0x1400528a4  add     rsp, 78h
0x1400528a8  pop     r15
0x1400528aa  pop     r14
0x1400528ac  pop     r13
0x1400528ae  pop     r12
0x1400528b0  pop     rdi
0x1400528b1  pop     rsi
0x1400528b2  pop     rbx
0x1400528b3  pop     rbp
0x1400528b4  retn
```
