# ndisGetNsiClientInfoForThread(_ETHREAD *,_NDIS_NSI_CLIENT_INFO *)

- ea: `0x14004b630`
- end: `0x14004b902`
- name: `?ndisGetNsiClientInfoForThread@@YAXPEAU_ETHREAD@@PEAU_NDIS_NSI_CLIENT_INFO@@@Z`
- size: `722`
- prototype: `void __fastcall(PETHREAD Thread, struct _NDIS_NSI_CLIENT_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140142c48`

## callees

- `0x14004b630`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14004b69d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004b70e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004b69d`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004b70e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004b8f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14004b8f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b7d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b8a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b7d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b8a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b782`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b876`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b782`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b876`
- `ntoskrnl!SeQueryInformationToken` at `0x14004b7f5`
- `ntoskrnl!SeQueryInformationToken` at `0x14004b830`
- `ntoskrnl!SeQueryInformationToken` at `0x14004b7f5`
- `ntoskrnl!SeQueryInformationToken` at `0x14004b830`
- `ntoskrnl!PsGetThreadProperty` at `0x14004b65a`
- `ntoskrnl!PsGetThreadProperty` at `0x14004b65a`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004b8c2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004b8d3`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004b8c2`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x14004b8d3`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004b6c3`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004b734`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004b6c3`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14004b734`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004b6de`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004b74f`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004b6de`
- `ntoskrnl!PsGetThreadSessionId` at `0x14004b74f`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004b806`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004b841`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004b806`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14004b841`

## pseudocode

```c
void __fastcall ndisGetNsiClientInfoForThread(PETHREAD Thread, struct _NDIS_NSI_CLIENT_INFO *a2)
{
  _DWORD *ThreadProperty; // rax
  PACCESS_TOKEN v5; // rax
  void *v6; // rsi
  unsigned int CurrentProcessSessionId; // eax
  unsigned int v8; // ebx
  struct _KTHREAD *CurrentThread; // rsi
  PACCESS_TOKEN v10; // rax
  void *v11; // rbp
  unsigned int ThreadSessionId; // eax
  int v13; // eax
  KIRQL v14; // al
  unsigned int v15; // r8d
  struct _NDIS_IF_COMPARTMENT_BLOCK *v16; // rcx
  struct _NDIS_IF_COMPARTMENT_BLOCK *v17; // r9
  NTSTATUS InformationToken; // ebx
  NTSTATUS v19; // ebx
  int v20; // esi
  KIRQL v21; // al
  PVOID TokenInformation[2]; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+70h] [rbp+18h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+78h] [rbp+20h] BYREF

  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  ThreadProperty = PsGetThreadProperty(Thread, 0x6D43644Eu, 0);
  if ( ThreadProperty )
  {
    *((_DWORD *)a2 + 1) = *ThreadProperty;
    *(_DWORD *)a2 = ThreadProperty[1];
    ObfDereferenceObject(ThreadProperty);
  }
  else
  {
    *(_QWORD *)a2 = 0;
  }
  if ( !*((_DWORD *)a2 + 1) )
  {
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation[0] = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId();
    }
    else
    {
      v5 = PsReferenceImpersonationToken(Thread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v6 = v5;
      if ( v5 )
      {
        InformationToken = SeQueryInformationToken(v5, TokenSessionId, TokenInformation);
        PsDereferenceImpersonationToken(v6);
        if ( InformationToken >= 0 )
        {
          v8 = (unsigned int)TokenInformation[0];
LABEL_8:
          if ( v8 == -1 )
          {
            CurrentThread = KeGetCurrentThread();
            CopyOnOpen = 0;
            EffectiveOnly = 0;
            ImpersonationLevel = SecurityAnonymous;
            TokenInformation[0] = 0;
            if ( KeGetCurrentIrql() >= 2u )
            {
              ThreadSessionId = PsGetCurrentProcessSessionId();
            }
            else
            {
              v10 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
              v11 = v10;
              if ( v10 )
              {
                v19 = SeQueryInformationToken(v10, TokenSessionId, TokenInformation);
                PsDereferenceImpersonationToken(v11);
                if ( v19 >= 0 )
                {
                  v8 = (unsigned int)TokenInformation[0];
                  goto LABEL_13;
                }
              }
              ThreadSessionId = PsGetThreadSessionId(CurrentThread);
            }
            v8 = ThreadSessionId;
          }
LABEL_13:
          if ( v8 < dword_140122898 )
          {
            v20 = 0;
            v21 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
            if ( v8 < dword_140122898 )
              v20 = *((_DWORD *)qword_1401228E8 + 6 * v8);
            KeReleaseSpinLock(&qword_1401228E0, v21);
            if ( !v20 )
              v20 = 1;
            v13 = v20;
          }
          else
          {
            v13 = 1;
          }
          *((_DWORD *)a2 + 1) = v13;
          goto LABEL_16;
        }
      }
      CurrentProcessSessionId = PsGetThreadSessionId(Thread);
    }
    v8 = CurrentProcessSessionId;
    goto LABEL_8;
  }
LABEL_16:
  v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  v15 = *((_DWORD *)a2 + 1);
  v16 = qword_1401229D8;
  v17 = 0;
  while ( v16 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_1401229D8 )
  {
    if ( *((_DWORD *)v16 + 4) == v15 )
    {
      v17 = v16;
      break;
    }
    if ( *((_DWORD *)v16 + 4) > v15 )
      break;
    v16 = *(struct _NDIS_IF_COMPARTMENT_BLOCK **)v16;
  }
  *(_OWORD *)((char *)a2 + 8) = *(_OWORD *)((char *)v17 + 1684);
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, v14);
}

```

## disassembly

```asm
0x14004b630  push    rdi
0x14004b632  sub     rsp, 50h
0x14004b636  xorps   xmm0, xmm0
0x14004b639  mov     [rsp+58h+var_18], rbp
0x14004b63e  movups  xmmword ptr [rdx], xmm0
0x14004b641  xor     eax, eax
0x14004b643  mov     [rsp+58h+var_28], r14
0x14004b648  mov     [rdx+10h], rax
0x14004b64c  mov     rdi, rdx
0x14004b64f  mov     edx, 6D43644Eh; Key
0x14004b654  xor     r8d, r8d; Flags
0x14004b657  mov     rbp, rcx
0x14004b65a  call    cs:__imp_PsGetThreadProperty
0x14004b661  nop     dword ptr [rax+rax+00h]
0x14004b666  xor     r14d, r14d
0x14004b669  test    rax, rax
0x14004b66c  jnz     loc_14004B8E4
0x14004b672  mov     [rdi], r14
0x14004b675  cmp     [rdi+4], r14d
0x14004b679  jnz     loc_14004B77B
0x14004b67f  mov     [rsp+58h+var_10], rbx
0x14004b684  mov     [rsp+58h+var_20], rsi
0x14004b689  mov     [rsp+58h+CopyOnOpen], r14b
0x14004b68e  mov     [rsp+58h+EffectiveOnly], r14b
0x14004b693  mov     [rsp+58h+ImpersonationLevel], r14d
0x14004b698  mov     [rsp+58h+TokenInformation], r14
0x14004b69d  call    cs:__imp_KeGetCurrentIrql
0x14004b6a4  nop     dword ptr [rax+rax+00h]
0x14004b6a9  cmp     al, 2
0x14004b6ab  jnb     loc_14004B8C2
0x14004b6b1  lea     r9, [rsp+58h+ImpersonationLevel]; ImpersonationLevel
0x14004b6b6  mov     rcx, rbp; Thread
0x14004b6b9  lea     r8, [rsp+58h+EffectiveOnly]; EffectiveOnly
0x14004b6be  lea     rdx, [rsp+58h+CopyOnOpen]; CopyOnOpen
0x14004b6c3  call    cs:__imp_PsReferenceImpersonationToken
0x14004b6ca  nop     dword ptr [rax+rax+00h]
0x14004b6cf  mov     rsi, rax
0x14004b6d2  test    rax, rax
0x14004b6d5  jnz     loc_14004B7E8
0x14004b6db  mov     rcx, rbp
0x14004b6de  call    cs:__imp_PsGetThreadSessionId
0x14004b6e5  nop     dword ptr [rax+rax+00h]
0x14004b6ea  mov     ebx, eax
0x14004b6ec  cmp     ebx, 0FFFFFFFFh
0x14004b6ef  jnz     short loc_14004B75D
0x14004b6f1  mov     rsi, gs:188h
0x14004b6fa  mov     [rsp+58h+CopyOnOpen], r14b
0x14004b6ff  mov     [rsp+58h+EffectiveOnly], r14b
0x14004b704  mov     [rsp+58h+ImpersonationLevel], r14d
0x14004b709  mov     [rsp+58h+TokenInformation], r14
0x14004b70e  call    cs:__imp_KeGetCurrentIrql
0x14004b715  nop     dword ptr [rax+rax+00h]
0x14004b71a  cmp     al, 2
0x14004b71c  jnb     loc_14004B8D3
0x14004b722  lea     r9, [rsp+58h+ImpersonationLevel]; ImpersonationLevel
0x14004b727  mov     rcx, rsi; Thread
0x14004b72a  lea     r8, [rsp+58h+EffectiveOnly]; EffectiveOnly
0x14004b72f  lea     rdx, [rsp+58h+CopyOnOpen]; CopyOnOpen
0x14004b734  call    cs:__imp_PsReferenceImpersonationToken
0x14004b73b  nop     dword ptr [rax+rax+00h]
0x14004b740  mov     rbp, rax
0x14004b743  test    rax, rax
0x14004b746  jnz     loc_14004B823
0x14004b74c  mov     rcx, rsi
0x14004b74f  call    cs:__imp_PsGetThreadSessionId
0x14004b756  nop     dword ptr [rax+rax+00h]
0x14004b75b  mov     ebx, eax
0x14004b75d  cmp     ebx, cs:dword_140122898
0x14004b763  jb      loc_14004B86C
0x14004b769  mov     eax, 1
0x14004b76e  mov     rsi, [rsp+58h+var_20]
0x14004b773  mov     rbx, [rsp+58h+var_10]
0x14004b778  mov     [rdi+4], eax
0x14004b77b  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004b782  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b789  nop     dword ptr [rax+rax+00h]
0x14004b78e  mov     r8d, [rdi+4]
0x14004b792  lea     r10, qword_1401229D8
0x14004b799  mov     rcx, cs:qword_1401229D8
0x14004b7a0  mov     r9, r14
0x14004b7a3  mov     r14, [rsp+58h+var_28]
0x14004b7a8  mov     rbp, [rsp+58h+var_18]
0x14004b7ad  cmp     rcx, r10
0x14004b7b0  jz      short loc_14004B7BF
0x14004b7b2  cmp     [rcx+10h], r8d
0x14004b7b6  jnz     loc_14004B85E
0x14004b7bc  mov     r9, rcx
0x14004b7bf  movups  xmm0, xmmword ptr [r9+694h]
0x14004b7c7  movzx   edx, al; NewIrql
0x14004b7ca  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x14004b7d1  movups  xmmword ptr [rdi+8], xmm0
0x14004b7d5  call    cs:__imp_KeReleaseSpinLock
0x14004b7dc  nop     dword ptr [rax+rax+00h]
0x14004b7e1  add     rsp, 50h
0x14004b7e5  pop     rdi
0x14004b7e6  retn
0x14004b7e8  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x14004b7ed  mov     edx, 0Ch; TokenInformationClass
0x14004b7f2  mov     rcx, rsi; Token
0x14004b7f5  call    cs:__imp_SeQueryInformationToken
0x14004b7fc  nop     dword ptr [rax+rax+00h]
0x14004b801  mov     rcx, rsi; ImpersonationToken
0x14004b804  mov     ebx, eax
0x14004b806  call    cs:__imp_PsDereferenceImpersonationToken
0x14004b80d  nop     dword ptr [rax+rax+00h]
0x14004b812  test    ebx, ebx
0x14004b814  js      loc_14004B6DB
0x14004b81a  mov     ebx, dword ptr [rsp+58h+TokenInformation]
0x14004b81e  jmp     loc_14004B6EC
0x14004b823  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x14004b828  mov     edx, 0Ch; TokenInformationClass
0x14004b82d  mov     rcx, rbp; Token
0x14004b830  call    cs:__imp_SeQueryInformationToken
0x14004b837  nop     dword ptr [rax+rax+00h]
0x14004b83c  mov     rcx, rbp; ImpersonationToken
0x14004b83f  mov     ebx, eax
0x14004b841  call    cs:__imp_PsDereferenceImpersonationToken
0x14004b848  nop     dword ptr [rax+rax+00h]
0x14004b84d  test    ebx, ebx
0x14004b84f  js      loc_14004B74C
0x14004b855  mov     ebx, dword ptr [rsp+58h+TokenInformation]
0x14004b859  jmp     loc_14004B75D
0x14004b85e  ja      loc_14004B7BF
0x14004b864  mov     rcx, [rcx]
0x14004b867  jmp     loc_14004B7AD
0x14004b86c  lea     rcx, qword_1401228E0; SpinLock
0x14004b873  mov     esi, r14d
0x14004b876  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b87d  nop     dword ptr [rax+rax+00h]
0x14004b882  cmp     ebx, cs:dword_140122898
0x14004b888  jnb     short loc_14004B89B
0x14004b88a  mov     edx, ebx
0x14004b88c  lea     r8, [rdx+rdx*2]
0x14004b890  mov     rdx, cs:qword_1401228E8
0x14004b897  mov     esi, [rdx+r8*8]
0x14004b89b  movzx   edx, al; NewIrql
0x14004b89e  lea     rcx, qword_1401228E0; SpinLock
0x14004b8a5  call    cs:__imp_KeReleaseSpinLock
0x14004b8ac  nop     dword ptr [rax+rax+00h]
0x14004b8b1  mov     eax, 1
0x14004b8b6  test    esi, esi
0x14004b8b8  cmovz   esi, eax
0x14004b8bb  mov     eax, esi
0x14004b8bd  jmp     loc_14004B76E
0x14004b8c2  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004b8c9  nop     dword ptr [rax+rax+00h]
0x14004b8ce  jmp     loc_14004B6EA
0x14004b8d3  call    cs:__imp_PsGetCurrentProcessSessionId
0x14004b8da  nop     dword ptr [rax+rax+00h]
0x14004b8df  jmp     loc_14004B75B
0x14004b8e4  mov     ecx, [rax]
0x14004b8e6  mov     [rdi+4], ecx
0x14004b8e9  mov     ecx, [rax+4]
0x14004b8ec  mov     [rdi], ecx
0x14004b8ee  mov     rcx, rax; Object
0x14004b8f1  call    cs:__imp_ObfDereferenceObject
0x14004b8f8  nop     dword ptr [rax+rax+00h]
0x14004b8fd  jmp     loc_14004B675
```
