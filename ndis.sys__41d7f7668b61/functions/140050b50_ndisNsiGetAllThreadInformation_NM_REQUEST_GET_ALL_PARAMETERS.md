# ndisNsiGetAllThreadInformation(_NM_REQUEST_GET_ALL_PARAMETERS *)

- ea: `0x140050b50`
- end: `0x140050df0`
- name: `?ndisNsiGetAllThreadInformation@@YAJPEAU_NM_REQUEST_GET_ALL_PARAMETERS@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _NM_REQUEST_GET_ALL_PARAMETERS *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140050b50`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140050bd1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140050c42`
- `ntoskrnl!KeGetCurrentIrql` at `0x140050bd1`
- `ntoskrnl!KeGetCurrentIrql` at `0x140050c42`
- `ntoskrnl!ObfDereferenceObject` at `0x140050dd5`
- `ntoskrnl!ObfDereferenceObject` at `0x140050dd5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140050d74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140050d74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140050d45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140050d45`
- `ntoskrnl!SeQueryInformationToken` at `0x140050cd2`
- `ntoskrnl!SeQueryInformationToken` at `0x140050d0d`
- `ntoskrnl!SeQueryInformationToken` at `0x140050cd2`
- `ntoskrnl!SeQueryInformationToken` at `0x140050d0d`
- `ntoskrnl!PsGetThreadProperty` at `0x140050b8f`
- `ntoskrnl!PsGetThreadProperty` at `0x140050b8f`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050da6`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050db7`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050da6`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140050db7`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140050bf7`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140050c68`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140050bf7`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140050c68`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050c12`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050c83`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050c12`
- `ntoskrnl!PsGetThreadSessionId` at `0x140050c83`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050ce3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050d1e`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050ce3`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140050d1e`

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
          if ( v9 < dword_140122898 )
          {
            v19 = 0;
            v20 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
            if ( v9 < dword_140122898 )
              v19 = *((_DWORD *)qword_1401228E8 + 6 * v9);
            KeReleaseSpinLock(&qword_1401228E0, v20);
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
0x140050b50  sub     rsp, 48h
0x140050b54  mov     edx, [rcx+20h]
0x140050b57  test    edx, edx
0x140050b59  jnz     loc_140050D91
0x140050b5f  mov     [rsp+48h+var_8], rbx
0x140050b64  mov     rbx, [rcx+28h]
0x140050b68  test    rbx, rbx
0x140050b6b  jz      loc_140050CB8
0x140050b71  mov     [rsp+48h+var_18], rsi
0x140050b76  xor     r8d, r8d; Flags
0x140050b79  mov     rsi, gs:188h
0x140050b82  mov     edx, 6D43644Eh; Key
0x140050b87  mov     rcx, rsi; Thread
0x140050b8a  mov     [rsp+48h+var_28], r14
0x140050b8f  call    cs:__imp_PsGetThreadProperty
0x140050b96  nop     dword ptr [rax+rax+00h]
0x140050b9b  xor     r14d, r14d
0x140050b9e  test    rax, rax
0x140050ba1  jnz     loc_140050DC8
0x140050ba7  mov     [rbx], r14
0x140050baa  cmp     [rbx], r14d
0x140050bad  jnz     loc_140050CAE
0x140050bb3  mov     [rsp+48h+var_20], rdi
0x140050bb8  mov     [rsp+48h+var_10], rbp
0x140050bbd  mov     [rsp+48h+CopyOnOpen], r14b
0x140050bc2  mov     [rsp+48h+EffectiveOnly], r14b
0x140050bc7  mov     [rsp+48h+ImpersonationLevel], r14d
0x140050bcc  mov     [rsp+48h+TokenInformation], r14
0x140050bd1  call    cs:__imp_KeGetCurrentIrql
0x140050bd8  nop     dword ptr [rax+rax+00h]
0x140050bdd  cmp     al, 2
0x140050bdf  jnb     loc_140050DA6
0x140050be5  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140050bea  mov     rcx, rsi; Thread
0x140050bed  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140050bf2  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140050bf7  call    cs:__imp_PsReferenceImpersonationToken
0x140050bfe  nop     dword ptr [rax+rax+00h]
0x140050c03  mov     rbp, rax
0x140050c06  test    rax, rax
0x140050c09  jnz     loc_140050CC5
0x140050c0f  mov     rcx, rsi
0x140050c12  call    cs:__imp_PsGetThreadSessionId
0x140050c19  nop     dword ptr [rax+rax+00h]
0x140050c1e  mov     edi, eax
0x140050c20  cmp     edi, 0FFFFFFFFh
0x140050c23  jnz     short loc_140050C91
0x140050c25  mov     rsi, gs:188h
0x140050c2e  mov     [rsp+48h+CopyOnOpen], r14b
0x140050c33  mov     [rsp+48h+EffectiveOnly], r14b
0x140050c38  mov     [rsp+48h+ImpersonationLevel], r14d
0x140050c3d  mov     [rsp+48h+TokenInformation], r14
0x140050c42  call    cs:__imp_KeGetCurrentIrql
0x140050c49  nop     dword ptr [rax+rax+00h]
0x140050c4e  cmp     al, 2
0x140050c50  jnb     loc_140050DB7
0x140050c56  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140050c5b  mov     rcx, rsi; Thread
0x140050c5e  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140050c63  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140050c68  call    cs:__imp_PsReferenceImpersonationToken
0x140050c6f  nop     dword ptr [rax+rax+00h]
0x140050c74  mov     rbp, rax
0x140050c77  test    rax, rax
0x140050c7a  jnz     loc_140050D00
0x140050c80  mov     rcx, rsi
0x140050c83  call    cs:__imp_PsGetThreadSessionId
0x140050c8a  nop     dword ptr [rax+rax+00h]
0x140050c8f  mov     edi, eax
0x140050c91  cmp     edi, cs:dword_140122898
0x140050c97  mov     rbp, [rsp+48h+var_10]
0x140050c9c  jb      loc_140050D3B
0x140050ca2  mov     eax, 1
0x140050ca7  mov     rdi, [rsp+48h+var_20]
0x140050cac  mov     [rbx], eax
0x140050cae  mov     rsi, [rsp+48h+var_18]
0x140050cb3  mov     r14, [rsp+48h+var_28]
0x140050cb8  mov     rbx, [rsp+48h+var_8]
0x140050cbd  xor     eax, eax
0x140050cbf  add     rsp, 48h
0x140050cc3  retn
0x140050cc5  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140050cca  mov     edx, 0Ch; TokenInformationClass
0x140050ccf  mov     rcx, rbp; Token
0x140050cd2  call    cs:__imp_SeQueryInformationToken
0x140050cd9  nop     dword ptr [rax+rax+00h]
0x140050cde  mov     rcx, rbp; ImpersonationToken
0x140050ce1  mov     edi, eax
0x140050ce3  call    cs:__imp_PsDereferenceImpersonationToken
0x140050cea  nop     dword ptr [rax+rax+00h]
0x140050cef  test    edi, edi
0x140050cf1  js      loc_140050C0F
0x140050cf7  mov     edi, dword ptr [rsp+48h+TokenInformation]
0x140050cfb  jmp     loc_140050C20
0x140050d00  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140050d05  mov     edx, 0Ch; TokenInformationClass
0x140050d0a  mov     rcx, rbp; Token
0x140050d0d  call    cs:__imp_SeQueryInformationToken
0x140050d14  nop     dword ptr [rax+rax+00h]
0x140050d19  mov     rcx, rbp; ImpersonationToken
0x140050d1c  mov     edi, eax
0x140050d1e  call    cs:__imp_PsDereferenceImpersonationToken
0x140050d25  nop     dword ptr [rax+rax+00h]
0x140050d2a  test    edi, edi
0x140050d2c  js      loc_140050C80
0x140050d32  mov     edi, dword ptr [rsp+48h+TokenInformation]
0x140050d36  jmp     loc_140050C91
0x140050d3b  lea     rcx, qword_1401228E0; SpinLock
0x140050d42  mov     esi, r14d
0x140050d45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140050d4c  nop     dword ptr [rax+rax+00h]
0x140050d51  cmp     edi, cs:dword_140122898
0x140050d57  jnb     short loc_140050D6A
0x140050d59  mov     edx, edi
0x140050d5b  lea     r8, [rdx+rdx*2]
0x140050d5f  mov     rdx, cs:qword_1401228E8
0x140050d66  mov     esi, [rdx+r8*8]
0x140050d6a  movzx   edx, al; NewIrql
0x140050d6d  lea     rcx, qword_1401228E0; SpinLock
0x140050d74  call    cs:__imp_KeReleaseSpinLock
0x140050d7b  nop     dword ptr [rax+rax+00h]
0x140050d80  mov     eax, 1
0x140050d85  test    esi, esi
0x140050d87  cmovz   esi, eax
0x140050d8a  mov     eax, esi
0x140050d8c  jmp     loc_140050CA7
0x140050d91  sub     edx, 1
0x140050d94  jz      short loc_140050D9B
0x140050d96  cmp     edx, 1
0x140050d99  jnz     short loc_140050DE6
0x140050d9b  mov     eax, 0C0000002h
0x140050da0  add     rsp, 48h
0x140050da4  retn
0x140050da6  call    cs:__imp_PsGetCurrentProcessSessionId
0x140050dad  nop     dword ptr [rax+rax+00h]
0x140050db2  jmp     loc_140050C1E
0x140050db7  call    cs:__imp_PsGetCurrentProcessSessionId
0x140050dbe  nop     dword ptr [rax+rax+00h]
0x140050dc3  jmp     loc_140050C8F
0x140050dc8  mov     ecx, [rax]
0x140050dca  mov     [rbx], ecx
0x140050dcc  mov     ecx, [rax+4]
0x140050dcf  mov     [rbx+4], ecx
0x140050dd2  mov     rcx, rax; Object
0x140050dd5  call    cs:__imp_ObfDereferenceObject
0x140050ddc  nop     dword ptr [rax+rax+00h]
0x140050de1  jmp     loc_140050BAA
0x140050de6  mov     eax, 0C000000Dh
0x140050deb  jmp     loc_140050CBF
```
