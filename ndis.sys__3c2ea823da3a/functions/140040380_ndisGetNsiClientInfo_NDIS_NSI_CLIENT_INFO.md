# ndisGetNsiClientInfo(_NDIS_NSI_CLIENT_INFO *)

- ea: `0x140040380`
- end: `0x14004065b`
- name: `?ndisGetNsiClientInfo@@YAXPEAU_NDIS_NSI_CLIENT_INFO@@@Z`
- size: `731`
- prototype: `void __fastcall(struct _NDIS_NSI_CLIENT_INFO *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14003fdf0`
- `0x1400400f0`
- `0x1400899f0`
- `0x140089e20`
- `0x1400cc6d0`
- `0x1400cd240`
- `0x1400cedb0`
- `0x1400cf000`
- `0x140173860`
- `0x140179a00`

## callees

- `0x140040380`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400403f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140040467`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400403f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140040467`
- `ntoskrnl!ObfDereferenceObject` at `0x14004064a`
- `ntoskrnl!ObfDereferenceObject` at `0x14004064a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004052e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004052e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400405fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400404db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400405cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400404db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400405cf`
- `ntoskrnl!SeQueryInformationToken` at `0x14004054e`
- `ntoskrnl!SeQueryInformationToken` at `0x140040589`
- `ntoskrnl!SeQueryInformationToken` at `0x14004054e`
- `ntoskrnl!SeQueryInformationToken` at `0x140040589`
- `ntoskrnl!PsGetThreadProperty` at `0x1400403b3`
- `ntoskrnl!PsGetThreadProperty` at `0x1400403b3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004061b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004062c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004061b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004062c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004041c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004048d`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004041c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004048d`
- `ntoskrnl!PsGetThreadSessionId` at `0x140040437`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400404a8`
- `ntoskrnl!PsGetThreadSessionId` at `0x140040437`
- `ntoskrnl!PsGetThreadSessionId` at `0x1400404a8`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004055f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004059a`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004055f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004059a`

## pseudocode

```c
void __fastcall ndisGetNsiClientInfo(struct _NDIS_NSI_CLIENT_INFO *a1)
{
  struct _KTHREAD *CurrentThread; // rbp
  _DWORD *ThreadProperty; // rax
  __int64 v4; // rcx
  PACCESS_TOKEN v5; // rax
  void *v6; // rsi
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v8; // ebx
  struct _KTHREAD *v9; // rsi
  __int64 v10; // rcx
  PACCESS_TOKEN v11; // rax
  void *v12; // rbp
  unsigned int ThreadSessionId; // eax
  int v14; // eax
  KIRQL v15; // al
  unsigned int v16; // r8d
  struct _NDIS_IF_COMPARTMENT_BLOCK *v17; // rcx
  struct _NDIS_IF_COMPARTMENT_BLOCK *v18; // r9
  NTSTATUS v19; // ebx
  NTSTATUS v20; // ebx
  int v21; // esi
  KIRQL v22; // al
  unsigned __int8 EffectiveOnly; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+58h] [rbp+10h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp+18h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  CurrentThread = KeGetCurrentThread();
  *(_OWORD *)a1 = 0;
  *((_QWORD *)a1 + 2) = 0;
  ThreadProperty = PsGetThreadProperty(CurrentThread, 0x6D43644Eu, 0);
  if ( ThreadProperty )
  {
    *((_DWORD *)a1 + 1) = *ThreadProperty;
    *(_DWORD *)a1 = ThreadProperty[1];
    ObfDereferenceObject(ThreadProperty);
  }
  else
  {
    *(_QWORD *)a1 = 0;
  }
  if ( !*((_DWORD *)a1 + 1) )
  {
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId(v4);
    }
    else
    {
      v5 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v6 = v5;
      if ( v5 )
      {
        v19 = SeQueryInformationToken(v5, TokenSessionId, &TokenInformation);
        PsDereferenceImpersonationToken(v6);
        if ( v19 >= 0 )
        {
          v8 = (unsigned int)TokenInformation;
LABEL_8:
          if ( v8 == -1 )
          {
            v9 = KeGetCurrentThread();
            CopyOnOpen = 0;
            EffectiveOnly = 0;
            ImpersonationLevel = SecurityAnonymous;
            TokenInformation = 0;
            if ( KeGetCurrentIrql() >= 2u )
            {
              ThreadSessionId = PsGetCurrentProcessSessionId(v10);
            }
            else
            {
              v11 = PsReferenceImpersonationToken(v9, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
              v12 = v11;
              if ( v11 )
              {
                v20 = SeQueryInformationToken(v11, TokenSessionId, &TokenInformation);
                PsDereferenceImpersonationToken(v12);
                if ( v20 >= 0 )
                {
                  v8 = (unsigned int)TokenInformation;
                  goto LABEL_13;
                }
              }
              ThreadSessionId = PsGetThreadSessionId(v9);
            }
            v8 = ThreadSessionId;
          }
LABEL_13:
          if ( v8 < dword_14011C898 )
          {
            v21 = 0;
            v22 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
            if ( v8 < dword_14011C898 )
              v21 = *((_DWORD *)qword_14011C8E8 + 6 * v8);
            KeReleaseSpinLock(&qword_14011C8E0, v22);
            if ( !v21 )
              v21 = 1;
            v14 = v21;
          }
          else
          {
            v14 = 1;
          }
          *((_DWORD *)a1 + 1) = v14;
          goto LABEL_16;
        }
      }
      CurrentProcessSessionId = PsGetThreadSessionId(CurrentThread);
    }
    v8 = CurrentProcessSessionId;
    goto LABEL_8;
  }
LABEL_16:
  v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  v16 = *((_DWORD *)a1 + 1);
  v17 = qword_14011C9D8;
  v18 = 0;
  while ( v17 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8 )
  {
    if ( *((_DWORD *)v17 + 4) == v16 )
    {
      v18 = v17;
      break;
    }
    if ( *((_DWORD *)v17 + 4) > v16 )
      break;
    v17 = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)v17;
  }
  *(_OWORD *)((char *)a1 + 8) = *(_OWORD *)((char *)v18 + 1684);
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v15);
}

```

## disassembly

```asm
0x140040380  push    rdi
0x140040382  sub     rsp, 40h
0x140040386  mov     [rsp+48h+var_18], rbp
0x14004038b  xorps   xmm0, xmm0
0x14004038e  mov     rbp, gs:188h
0x140040397  xor     eax, eax
0x140040399  movups  xmmword ptr [rcx], xmm0
0x14004039c  mov     [rcx+10h], rax
0x1400403a0  mov     rdi, rcx
0x1400403a3  mov     rcx, rbp; Thread
0x1400403a6  mov     [rsp+48h+var_28], r14
0x1400403ab  xor     r8d, r8d; Flags
0x1400403ae  mov     edx, 6D43644Eh; Key
0x1400403b3  call    cs:__imp_PsGetThreadProperty
0x1400403ba  nop     dword ptr [rax+rax+00h]
0x1400403bf  xor     r14d, r14d
0x1400403c2  test    rax, rax
0x1400403c5  jnz     loc_14004063D
0x1400403cb  mov     [rdi], r14
0x1400403ce  cmp     [rdi+4], r14d
0x1400403d2  jnz     loc_1400404D4
0x1400403d8  mov     [rsp+48h+var_10], rbx
0x1400403dd  mov     [rsp+48h+var_20], rsi
0x1400403e2  mov     [rsp+48h+CopyOnOpen], r14b
0x1400403e7  mov     [rsp+48h+EffectiveOnly], r14b
0x1400403ec  mov     [rsp+48h+ImpersonationLevel], r14d
0x1400403f1  mov     [rsp+48h+TokenInformation], r14
0x1400403f6  call    cs:__imp_KeGetCurrentIrql
0x1400403fd  nop     dword ptr [rax+rax+00h]
0x140040402  cmp     al, 2
0x140040404  jnb     loc_14004061B
0x14004040a  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004040f  mov     rcx, rbp; Thread
0x140040412  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140040417  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004041c  call    cs:__imp_PsReferenceImpersonationToken
0x140040423  nop     dword ptr [rax+rax+00h]
0x140040428  mov     rsi, rax
0x14004042b  test    rax, rax
0x14004042e  jnz     loc_140040541
0x140040434  mov     rcx, rbp
0x140040437  call    cs:__imp_PsGetThreadSessionId
0x14004043e  nop     dword ptr [rax+rax+00h]
0x140040443  mov     ebx, eax
0x140040445  cmp     ebx, 0FFFFFFFFh
0x140040448  jnz     short loc_1400404B6
0x14004044a  mov     rsi, gs:188h
0x140040453  mov     [rsp+48h+CopyOnOpen], r14b
0x140040458  mov     [rsp+48h+EffectiveOnly], r14b
0x14004045d  mov     [rsp+48h+ImpersonationLevel], r14d
0x140040462  mov     [rsp+48h+TokenInformation], r14
0x140040467  call    cs:__imp_KeGetCurrentIrql
0x14004046e  nop     dword ptr [rax+rax+00h]
0x140040473  cmp     al, 2
0x140040475  jnb     loc_14004062C
0x14004047b  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140040480  mov     rcx, rsi; Thread
0x140040483  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140040488  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004048d  call    cs:__imp_PsReferenceImpersonationToken
0x140040494  nop     dword ptr [rax+rax+00h]
0x140040499  mov     rbp, rax
0x14004049c  test    rax, rax
0x14004049f  jnz     loc_14004057C
0x1400404a5  mov     rcx, rsi
0x1400404a8  call    cs:__imp_PsGetThreadSessionId
0x1400404af  nop     dword ptr [rax+rax+00h]
0x1400404b4  mov     ebx, eax
0x1400404b6  cmp     ebx, cs:dword_14011C898
0x1400404bc  jb      loc_1400405C5
0x1400404c2  mov     eax, 1
0x1400404c7  mov     rsi, [rsp+48h+var_20]
0x1400404cc  mov     rbx, [rsp+48h+var_10]
0x1400404d1  mov     [rdi+4], eax
0x1400404d4  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x1400404db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400404e2  nop     dword ptr [rax+rax+00h]
0x1400404e7  mov     r8d, [rdi+4]
0x1400404eb  lea     r10, qword_14011C9D8
0x1400404f2  mov     rcx, cs:qword_14011C9D8
0x1400404f9  mov     r9, r14
0x1400404fc  mov     r14, [rsp+48h+var_28]
0x140040501  mov     rbp, [rsp+48h+var_18]
0x140040506  cmp     rcx, r10
0x140040509  jz      short loc_140040518
0x14004050b  cmp     [rcx+10h], r8d
0x14004050f  jnz     loc_1400405B7
0x140040515  mov     r9, rcx
0x140040518  movups  xmm0, xmmword ptr [r9+694h]
0x140040520  movzx   edx, al; NewIrql
0x140040523  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004052a  movups  xmmword ptr [rdi+8], xmm0
0x14004052e  call    cs:__imp_KeReleaseSpinLock
0x140040535  nop     dword ptr [rax+rax+00h]
0x14004053a  add     rsp, 40h
0x14004053e  pop     rdi
0x14004053f  retn
0x140040541  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140040546  mov     edx, 0Ch; TokenInformationClass
0x14004054b  mov     rcx, rsi; Token
0x14004054e  call    cs:__imp_SeQueryInformationToken
0x140040555  nop     dword ptr [rax+rax+00h]
0x14004055a  mov     rcx, rsi; ImpersonationToken
0x14004055d  mov     ebx, eax
0x14004055f  call    cs:__imp_PsDereferenceImpersonationToken
0x140040566  nop     dword ptr [rax+rax+00h]
0x14004056b  test    ebx, ebx
0x14004056d  js      loc_140040434
0x140040573  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140040577  jmp     loc_140040445
0x14004057c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140040581  mov     edx, 0Ch; TokenInformationClass
0x140040586  mov     rcx, rbp; Token
0x140040589  call    cs:__imp_SeQueryInformationToken
0x140040590  nop     dword ptr [rax+rax+00h]
0x140040595  mov     rcx, rbp; ImpersonationToken
0x140040598  mov     ebx, eax
0x14004059a  call    cs:__imp_PsDereferenceImpersonationToken
0x1400405a1  nop     dword ptr [rax+rax+00h]
0x1400405a6  test    ebx, ebx
0x1400405a8  js      loc_1400404A5
0x1400405ae  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x1400405b2  jmp     loc_1400404B6
0x1400405b7  ja      loc_140040518
0x1400405bd  mov     rcx, [rcx]
0x1400405c0  jmp     loc_140040506
0x1400405c5  lea     rcx, qword_14011C8E0; SpinLock
0x1400405cc  mov     esi, r14d
0x1400405cf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400405d6  nop     dword ptr [rax+rax+00h]
0x1400405db  cmp     ebx, cs:dword_14011C898
0x1400405e1  jnb     short loc_1400405F4
0x1400405e3  mov     edx, ebx
0x1400405e5  lea     r8, [rdx+rdx*2]
0x1400405e9  mov     rdx, cs:qword_14011C8E8
0x1400405f0  mov     esi, [rdx+r8*8]
0x1400405f4  movzx   edx, al; NewIrql
0x1400405f7  lea     rcx, qword_14011C8E0; SpinLock
0x1400405fe  call    cs:__imp_KeReleaseSpinLock
0x140040605  nop     dword ptr [rax+rax+00h]
0x14004060a  mov     eax, 1
0x14004060f  test    esi, esi
0x140040611  cmovz   esi, eax
0x140040614  mov     eax, esi
0x140040616  jmp     loc_1400404C7
0x14004061b  call    cs:__imp_PsGetCurrentProcessSessionId
0x140040622  nop     dword ptr [rax+rax+00h]
0x140040627  jmp     loc_140040443
0x14004062c  call    cs:__imp_PsGetCurrentProcessSessionId
0x140040633  nop     dword ptr [rax+rax+00h]
0x140040638  jmp     loc_1400404B4
0x14004063d  mov     ecx, [rax]
0x14004063f  mov     [rdi+4], ecx
0x140040642  mov     ecx, [rax+4]
0x140040645  mov     [rdi], ecx
0x140040647  mov     rcx, rax; Object
0x14004064a  call    cs:__imp_ObfDereferenceObject
0x140040651  nop     dword ptr [rax+rax+00h]
0x140040656  jmp     loc_1400403CE
```
