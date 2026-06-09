# ndisNsiGetAllThreadInformation(_NM_REQUEST_GET_ALL_PARAMETERS *)

- ea: `0x14004c180`
- end: `0x14004c420`
- name: `?ndisNsiGetAllThreadInformation@@YAJPEAU_NM_REQUEST_GET_ALL_PARAMETERS@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _NM_REQUEST_GET_ALL_PARAMETERS *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14004c180`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004c201`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c272`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c201`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004c272`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c405`
- `ntoskrnl!ObfDereferenceObject` at `0x14004c405`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004c3a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004c3a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c375`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c375`
- `ntoskrnl!SeQueryInformationToken` at `0x14004c302`
- `ntoskrnl!SeQueryInformationToken` at `0x14004c33d`
- `ntoskrnl!SeQueryInformationToken` at `0x14004c302`
- `ntoskrnl!SeQueryInformationToken` at `0x14004c33d`
- `ntoskrnl!PsGetThreadProperty` at `0x14004c1bf`
- `ntoskrnl!PsGetThreadProperty` at `0x14004c1bf`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004c3d6`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004c3e7`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004c3d6`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004c3e7`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004c227`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004c298`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004c227`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004c298`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004c242`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004c2b3`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004c242`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004c2b3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004c313`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004c34e`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004c313`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004c34e`

## pseudocode

```c
__int64 __fastcall ndisNsiGetAllThreadInformation(struct _NM_REQUEST_GET_ALL_PARAMETERS *a1)
{
  int v1; // edx
  int *v2; // rbx
  struct _KTHREAD *CurrentThread; // rsi
  int *ThreadProperty; // rax
  __int64 v5; // rcx
  PACCESS_TOKEN v6; // rax
  void *v7; // rbp
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v9; // edi
  struct _KTHREAD *v10; // rsi
  __int64 v11; // rcx
  PACCESS_TOKEN v12; // rax
  void *v13; // rbp
  unsigned int ThreadSessionId; // eax
  int v15; // eax
  NTSTATUS v17; // edi
  NTSTATUS v18; // edi
  int v19; // esi
  KIRQL v20; // al
  unsigned __int8 EffectiveOnly; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+58h] [rbp+10h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp+18h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v1 = *((_DWORD *)a1 + 8);
  if ( !v1 )
  {
    v2 = (int *)*((_QWORD *)a1 + 5);
    if ( !v2 )
      return 0;
    CurrentThread = KeGetCurrentThread();
    ThreadProperty = (int *)PsGetThreadProperty(CurrentThread, 0x6D43644Eu, 0);
    if ( ThreadProperty )
    {
      *v2 = *ThreadProperty;
      v2[1] = ThreadProperty[1];
      ObfDereferenceObject(ThreadProperty);
    }
    else
    {
      *(_QWORD *)v2 = 0;
    }
    if ( *v2 )
      return 0;
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId(v5);
    }
    else
    {
      v6 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v7 = v6;
      if ( v6 )
      {
        v17 = SeQueryInformationToken(v6, TokenSessionId, &TokenInformation);
        PsDereferenceImpersonationToken(v7);
        if ( v17 >= 0 )
        {
          v9 = (unsigned int)TokenInformation;
LABEL_10:
          if ( v9 == -1 )
          {
            v10 = KeGetCurrentThread();
            CopyOnOpen = 0;
            EffectiveOnly = 0;
            ImpersonationLevel = SecurityAnonymous;
            TokenInformation = 0;
            if ( KeGetCurrentIrql() >= 2u )
            {
              ThreadSessionId = PsGetCurrentProcessSessionId(v11);
            }
            else
            {
              v12 = PsReferenceImpersonationToken(v10, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
              v13 = v12;
              if ( v12 )
              {
                v18 = SeQueryInformationToken(v12, TokenSessionId, &TokenInformation);
                PsDereferenceImpersonationToken(v13);
                if ( v18 >= 0 )
                {
                  v9 = (unsigned int)TokenInformation;
                  goto LABEL_15;
                }
              }
              ThreadSessionId = PsGetThreadSessionId(v10);
            }
            v9 = ThreadSessionId;
          }
LABEL_15:
          if ( v9 < dword_14011C898 )
          {
            v19 = 0;
            v20 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
            if ( v9 < dword_14011C898 )
              v19 = *((_DWORD *)qword_14011C8E8 + 6 * v9);
            KeReleaseSpinLock(&qword_14011C8E0, v20);
            if ( !v19 )
              v19 = 1;
            v15 = v19;
          }
          else
          {
            v15 = 1;
          }
          *v2 = v15;
          return 0;
        }
      }
      CurrentProcessSessionId = PsGetThreadSessionId(CurrentThread);
    }
    v9 = CurrentProcessSessionId;
    goto LABEL_10;
  }
  if ( (unsigned int)(v1 - 1) > 1 )
    return 3221225485LL;
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x14004c180  sub     rsp, 48h
0x14004c184  mov     edx, [rcx+20h]
0x14004c187  test    edx, edx
0x14004c189  jnz     loc_14004C3C1
0x14004c18f  mov     [rsp+48h+var_8], rbx
0x14004c194  mov     rbx, [rcx+28h]
0x14004c198  test    rbx, rbx
0x14004c19b  jz      loc_14004C2E8
0x14004c1a1  mov     [rsp+48h+var_18], rsi
0x14004c1a6  xor     r8d, r8d; Flags
0x14004c1a9  mov     rsi, gs:188h
0x14004c1b2  mov     edx, 6D43644Eh; Key
0x14004c1b7  mov     rcx, rsi; Thread
0x14004c1ba  mov     [rsp+48h+var_28], r14
0x14004c1bf  call    cs:__imp_PsGetThreadProperty
0x14004c1c6  nop     dword ptr [rax+rax+00h]
0x14004c1cb  xor     r14d, r14d
0x14004c1ce  test    rax, rax
0x14004c1d1  jnz     loc_14004C3F8
0x14004c1d7  mov     [rbx], r14
0x14004c1da  cmp     [rbx], r14d
0x14004c1dd  jnz     loc_14004C2DE
0x14004c1e3  mov     [rsp+48h+var_20], rdi
0x14004c1e8  mov     [rsp+48h+var_10], rbp
0x14004c1ed  mov     [rsp+48h+CopyOnOpen], r14b
0x14004c1f2  mov     [rsp+48h+EffectiveOnly], r14b
0x14004c1f7  mov     [rsp+48h+ImpersonationLevel], r14d
0x14004c1fc  mov     [rsp+48h+TokenInformation], r14
0x14004c201  call    cs:__imp_KeGetCurrentIrql
0x14004c208  nop     dword ptr [rax+rax+00h]
0x14004c20d  cmp     al, 2
0x14004c20f  jnb     loc_14004C3D6
0x14004c215  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004c21a  mov     rcx, rsi; Thread
0x14004c21d  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004c222  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004c227  call    cs:__imp_PsReferenceImpersonationToken
0x14004c22e  nop     dword ptr [rax+rax+00h]
0x14004c233  mov     rbp, rax
0x14004c236  test    rax, rax
0x14004c239  jnz     loc_14004C2F5
0x14004c23f  mov     rcx, rsi
0x14004c242  call    cs:__imp_PsGetThreadSessionId
0x14004c249  nop     dword ptr [rax+rax+00h]
0x14004c24e  mov     edi, eax
0x14004c250  cmp     edi, 0FFFFFFFFh
0x14004c253  jnz     short loc_14004C2C1
0x14004c255  mov     rsi, gs:188h
0x14004c25e  mov     [rsp+48h+CopyOnOpen], r14b
0x14004c263  mov     [rsp+48h+EffectiveOnly], r14b
0x14004c268  mov     [rsp+48h+ImpersonationLevel], r14d
0x14004c26d  mov     [rsp+48h+TokenInformation], r14
0x14004c272  call    cs:__imp_KeGetCurrentIrql
0x14004c279  nop     dword ptr [rax+rax+00h]
0x14004c27e  cmp     al, 2
0x14004c280  jnb     loc_14004C3E7
0x14004c286  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x14004c28b  mov     rcx, rsi; Thread
0x14004c28e  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x14004c293  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x14004c298  call    cs:__imp_PsReferenceImpersonationToken
0x14004c29f  nop     dword ptr [rax+rax+00h]
0x14004c2a4  mov     rbp, rax
0x14004c2a7  test    rax, rax
0x14004c2aa  jnz     loc_14004C330
0x14004c2b0  mov     rcx, rsi
0x14004c2b3  call    cs:__imp_PsGetThreadSessionId
0x14004c2ba  nop     dword ptr [rax+rax+00h]
0x14004c2bf  mov     edi, eax
0x14004c2c1  cmp     edi, cs:dword_14011C898
0x14004c2c7  mov     rbp, [rsp+48h+var_10]
0x14004c2cc  jb      loc_14004C36B
0x14004c2d2  mov     eax, 1
0x14004c2d7  mov     rdi, [rsp+48h+var_20]
0x14004c2dc  mov     [rbx], eax
0x14004c2de  mov     rsi, [rsp+48h+var_18]
0x14004c2e3  mov     r14, [rsp+48h+var_28]
0x14004c2e8  mov     rbx, [rsp+48h+var_8]
0x14004c2ed  xor     eax, eax
0x14004c2ef  add     rsp, 48h
0x14004c2f3  retn
0x14004c2f5  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004c2fa  mov     edx, 0Ch; TokenInformationClass
0x14004c2ff  mov     rcx, rbp; Token
0x14004c302  call    cs:__imp_SeQueryInformationToken
0x14004c309  nop     dword ptr [rax+rax+00h]
0x14004c30e  mov     rcx, rbp; ImpersonationToken
0x14004c311  mov     edi, eax
0x14004c313  call    cs:__imp_PsDereferenceImpersonationToken
0x14004c31a  nop     dword ptr [rax+rax+00h]
0x14004c31f  test    edi, edi
0x14004c321  js      loc_14004C23F
0x14004c327  mov     edi, dword ptr [rsp+48h+TokenInformation]
0x14004c32b  jmp     loc_14004C250
0x14004c330  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004c335  mov     edx, 0Ch; TokenInformationClass
0x14004c33a  mov     rcx, rbp; Token
0x14004c33d  call    cs:__imp_SeQueryInformationToken
0x14004c344  nop     dword ptr [rax+rax+00h]
0x14004c349  mov     rcx, rbp; ImpersonationToken
0x14004c34c  mov     edi, eax
0x14004c34e  call    cs:__imp_PsDereferenceImpersonationToken
0x14004c355  nop     dword ptr [rax+rax+00h]
0x14004c35a  test    edi, edi
0x14004c35c  js      loc_14004C2B0
0x14004c362  mov     edi, dword ptr [rsp+48h+TokenInformation]
0x14004c366  jmp     loc_14004C2C1
0x14004c36b  lea     rcx, qword_14011C8E0; SpinLock
0x14004c372  mov     esi, r14d
0x14004c375  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004c37c  nop     dword ptr [rax+rax+00h]
0x14004c381  cmp     edi, cs:dword_14011C898
0x14004c387  jnb     short loc_14004C39A
0x14004c389  mov     edx, edi
0x14004c38b  lea     r8, [rdx+rdx*2]
0x14004c38f  mov     rdx, cs:qword_14011C8E8
0x14004c396  mov     esi, [rdx+r8*8]
0x14004c39a  movzx   edx, al; NewIrql
0x14004c39d  lea     rcx, qword_14011C8E0; SpinLock
0x14004c3a4  call    cs:__imp_KeReleaseSpinLock
0x14004c3ab  nop     dword ptr [rax+rax+00h]
0x14004c3b0  mov     eax, 1
0x14004c3b5  test    esi, esi
0x14004c3b7  cmovz   esi, eax
0x14004c3ba  mov     eax, esi
0x14004c3bc  jmp     loc_14004C2D7
0x14004c3c1  sub     edx, 1
0x14004c3c4  jz      short loc_14004C3CB
0x14004c3c6  cmp     edx, 1
0x14004c3c9  jnz     short loc_14004C416
0x14004c3cb  mov     eax, 0C0000002h
0x14004c3d0  add     rsp, 48h
0x14004c3d4  retn
0x14004c3d6  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004c3dd  nop     dword ptr [rax+rax+00h]
0x14004c3e2  jmp     loc_14004C24E
0x14004c3e7  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004c3ee  nop     dword ptr [rax+rax+00h]
0x14004c3f3  jmp     loc_14004C2BF
0x14004c3f8  mov     ecx, [rax]
0x14004c3fa  mov     [rbx], ecx
0x14004c3fc  mov     ecx, [rax+4]
0x14004c3ff  mov     [rbx+4], ecx
0x14004c402  mov     rcx, rax; Object
0x14004c405  call    cs:__imp_ObfDereferenceObject
0x14004c40c  nop     dword ptr [rax+rax+00h]
0x14004c411  jmp     loc_14004C1DA
0x14004c416  mov     eax, 0C000000Dh
0x14004c41b  jmp     loc_14004C2EF
```
