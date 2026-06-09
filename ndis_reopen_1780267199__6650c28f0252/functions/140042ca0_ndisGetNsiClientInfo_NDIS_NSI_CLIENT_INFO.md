# ndisGetNsiClientInfo(_NDIS_NSI_CLIENT_INFO *)

- ea: `0x140042ca0`
- end: `0x140042f7b`
- name: `?ndisGetNsiClientInfo@@YAXPEAU_NDIS_NSI_CLIENT_INFO@@@Z`
- size: `731`
- prototype: `void __fastcall(struct _NDIS_NSI_CLIENT_INFO *)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140042710`
- `0x140042a10`
- `0x14008ece0`
- `0x14008f110`
- `0x1400d1880`
- `0x1400d23f0`
- `0x1400d3f60`
- `0x1400d41b0`
- `0x140179860`
- `0x14017f9d0`

## callees

- `0x140042ca0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140042d16`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042d87`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042d16`
- `ntoskrnl!KeGetCurrentIrql` at `0x140042d87`
- `ntoskrnl!ObfDereferenceObject` at `0x140042f6a`
- `ntoskrnl!ObfDereferenceObject` at `0x140042f6a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042e4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042f1e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042e4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140042f1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042dfb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042eef`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042dfb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140042eef`
- `ntoskrnl!SeQueryInformationToken` at `0x140042e6e`
- `ntoskrnl!SeQueryInformationToken` at `0x140042ea9`
- `ntoskrnl!SeQueryInformationToken` at `0x140042e6e`
- `ntoskrnl!SeQueryInformationToken` at `0x140042ea9`
- `ntoskrnl!PsGetThreadProperty` at `0x140042cd3`
- `ntoskrnl!PsGetThreadProperty` at `0x140042cd3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140042f3b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140042f4c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140042f3b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140042f4c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140042d3c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140042dad`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140042d3c`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140042dad`
- `ntoskrnl!PsGetThreadSessionId` at `0x140042d57`
- `ntoskrnl!PsGetThreadSessionId` at `0x140042dc8`
- `ntoskrnl!PsGetThreadSessionId` at `0x140042d57`
- `ntoskrnl!PsGetThreadSessionId` at `0x140042dc8`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140042e7f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140042eba`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140042e7f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140042eba`

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
          if ( v8 < dword_140122898 )
          {
            v21 = 0;
            v22 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
            if ( v8 < dword_140122898 )
              v21 = *((_DWORD *)qword_1401228E8 + 6 * v8);
            KeReleaseSpinLock(&qword_1401228E0, v22);
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
  v17 = qword_1401229D8;
  v18 = 0;
  while ( v17 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8 )
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
0x140042ca0  push    rdi
0x140042ca2  sub     rsp, 40h
0x140042ca6  mov     [rsp+48h+var_18], rbp
0x140042cab  xorps   xmm0, xmm0
0x140042cae  mov     rbp, gs:188h
0x140042cb7  xor     eax, eax
0x140042cb9  movups  xmmword ptr [rcx], xmm0
0x140042cbc  mov     [rcx+10h], rax
0x140042cc0  mov     rdi, rcx
0x140042cc3  mov     rcx, rbp; Thread
0x140042cc6  mov     [rsp+48h+var_28], r14
0x140042ccb  xor     r8d, r8d; Flags
0x140042cce  mov     edx, 6D43644Eh; Key
0x140042cd3  call    cs:__imp_PsGetThreadProperty
0x140042cda  nop     dword ptr [rax+rax+00h]
0x140042cdf  xor     r14d, r14d
0x140042ce2  test    rax, rax
0x140042ce5  jnz     loc_140042F5D
0x140042ceb  mov     [rdi], r14
0x140042cee  cmp     [rdi+4], r14d
0x140042cf2  jnz     loc_140042DF4
0x140042cf8  mov     [rsp+48h+var_10], rbx
0x140042cfd  mov     [rsp+48h+var_20], rsi
0x140042d02  mov     [rsp+48h+CopyOnOpen], r14b
0x140042d07  mov     [rsp+48h+EffectiveOnly], r14b
0x140042d0c  mov     [rsp+48h+ImpersonationLevel], r14d
0x140042d11  mov     [rsp+48h+TokenInformation], r14
0x140042d16  call    cs:__imp_KeGetCurrentIrql
0x140042d1d  nop     dword ptr [rax+rax+00h]
0x140042d22  cmp     al, 2
0x140042d24  jnb     loc_140042F3B
0x140042d2a  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140042d2f  mov     rcx, rbp; Thread
0x140042d32  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140042d37  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140042d3c  call    cs:__imp_PsReferenceImpersonationToken
0x140042d43  nop     dword ptr [rax+rax+00h]
0x140042d48  mov     rsi, rax
0x140042d4b  test    rax, rax
0x140042d4e  jnz     loc_140042E61
0x140042d54  mov     rcx, rbp
0x140042d57  call    cs:__imp_PsGetThreadSessionId
0x140042d5e  nop     dword ptr [rax+rax+00h]
0x140042d63  mov     ebx, eax
0x140042d65  cmp     ebx, 0FFFFFFFFh
0x140042d68  jnz     short loc_140042DD6
0x140042d6a  mov     rsi, gs:188h
0x140042d73  mov     [rsp+48h+CopyOnOpen], r14b
0x140042d78  mov     [rsp+48h+EffectiveOnly], r14b
0x140042d7d  mov     [rsp+48h+ImpersonationLevel], r14d
0x140042d82  mov     [rsp+48h+TokenInformation], r14
0x140042d87  call    cs:__imp_KeGetCurrentIrql
0x140042d8e  nop     dword ptr [rax+rax+00h]
0x140042d93  cmp     al, 2
0x140042d95  jnb     loc_140042F4C
0x140042d9b  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140042da0  mov     rcx, rsi; Thread
0x140042da3  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140042da8  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140042dad  call    cs:__imp_PsReferenceImpersonationToken
0x140042db4  nop     dword ptr [rax+rax+00h]
0x140042db9  mov     rbp, rax
0x140042dbc  test    rax, rax
0x140042dbf  jnz     loc_140042E9C
0x140042dc5  mov     rcx, rsi
0x140042dc8  call    cs:__imp_PsGetThreadSessionId
0x140042dcf  nop     dword ptr [rax+rax+00h]
0x140042dd4  mov     ebx, eax
0x140042dd6  cmp     ebx, cs:dword_140122898
0x140042ddc  jb      loc_140042EE5
0x140042de2  mov     eax, 1
0x140042de7  mov     rsi, [rsp+48h+var_20]
0x140042dec  mov     rbx, [rsp+48h+var_10]
0x140042df1  mov     [rdi+4], eax
0x140042df4  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140042dfb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140042e02  nop     dword ptr [rax+rax+00h]
0x140042e07  mov     r8d, [rdi+4]
0x140042e0b  lea     r10, qword_1401229D8
0x140042e12  mov     rcx, cs:qword_1401229D8
0x140042e19  mov     r9, r14
0x140042e1c  mov     r14, [rsp+48h+var_28]
0x140042e21  mov     rbp, [rsp+48h+var_18]
0x140042e26  cmp     rcx, r10
0x140042e29  jz      short loc_140042E38
0x140042e2b  cmp     [rcx+10h], r8d
0x140042e2f  jnz     loc_140042ED7
0x140042e35  mov     r9, rcx
0x140042e38  movups  xmm0, xmmword ptr [r9+694h]
0x140042e40  movzx   edx, al; NewIrql
0x140042e43  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140042e4a  movups  xmmword ptr [rdi+8], xmm0
0x140042e4e  call    cs:__imp_KeReleaseSpinLock
0x140042e55  nop     dword ptr [rax+rax+00h]
0x140042e5a  add     rsp, 40h
0x140042e5e  pop     rdi
0x140042e5f  retn
0x140042e61  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140042e66  mov     edx, 0Ch; TokenInformationClass
0x140042e6b  mov     rcx, rsi; Token
0x140042e6e  call    cs:__imp_SeQueryInformationToken
0x140042e75  nop     dword ptr [rax+rax+00h]
0x140042e7a  mov     rcx, rsi; ImpersonationToken
0x140042e7d  mov     ebx, eax
0x140042e7f  call    cs:__imp_PsDereferenceImpersonationToken
0x140042e86  nop     dword ptr [rax+rax+00h]
0x140042e8b  test    ebx, ebx
0x140042e8d  js      loc_140042D54
0x140042e93  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140042e97  jmp     loc_140042D65
0x140042e9c  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140042ea1  mov     edx, 0Ch; TokenInformationClass
0x140042ea6  mov     rcx, rbp; Token
0x140042ea9  call    cs:__imp_SeQueryInformationToken
0x140042eb0  nop     dword ptr [rax+rax+00h]
0x140042eb5  mov     rcx, rbp; ImpersonationToken
0x140042eb8  mov     ebx, eax
0x140042eba  call    cs:__imp_PsDereferenceImpersonationToken
0x140042ec1  nop     dword ptr [rax+rax+00h]
0x140042ec6  test    ebx, ebx
0x140042ec8  js      loc_140042DC5
0x140042ece  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140042ed2  jmp     loc_140042DD6
0x140042ed7  ja      loc_140042E38
0x140042edd  mov     rcx, [rcx]
0x140042ee0  jmp     loc_140042E26
0x140042ee5  lea     rcx, qword_1401228E0; SpinLock
0x140042eec  mov     esi, r14d
0x140042eef  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140042ef6  nop     dword ptr [rax+rax+00h]
0x140042efb  cmp     ebx, cs:dword_140122898
0x140042f01  jnb     short loc_140042F14
0x140042f03  mov     edx, ebx
0x140042f05  lea     r8, [rdx+rdx*2]
0x140042f09  mov     rdx, cs:qword_1401228E8
0x140042f10  mov     esi, [rdx+r8*8]
0x140042f14  movzx   edx, al; NewIrql
0x140042f17  lea     rcx, qword_1401228E0; SpinLock
0x140042f1e  call    cs:__imp_KeReleaseSpinLock
0x140042f25  nop     dword ptr [rax+rax+00h]
0x140042f2a  mov     eax, 1
0x140042f2f  test    esi, esi
0x140042f31  cmovz   esi, eax
0x140042f34  mov     eax, esi
0x140042f36  jmp     loc_140042DE7
0x140042f3b  call    cs:__imp_PsGetCurrentProcessSessionId
0x140042f42  nop     dword ptr [rax+rax+00h]
0x140042f47  jmp     loc_140042D63
0x140042f4c  call    cs:__imp_PsGetCurrentProcessSessionId
0x140042f53  nop     dword ptr [rax+rax+00h]
0x140042f58  jmp     loc_140042DD4
0x140042f5d  mov     ecx, [rax]
0x140042f5f  mov     [rdi+4], ecx
0x140042f62  mov     ecx, [rax+4]
0x140042f65  mov     [rdi], ecx
0x140042f67  mov     rcx, rax; Object
0x140042f6a  call    cs:__imp_ObfDereferenceObject
0x140042f71  nop     dword ptr [rax+rax+00h]
0x140042f76  jmp     loc_140042CEE
```
