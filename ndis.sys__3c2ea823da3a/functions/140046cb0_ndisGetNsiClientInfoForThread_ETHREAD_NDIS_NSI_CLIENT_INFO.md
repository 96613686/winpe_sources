# ndisGetNsiClientInfoForThread(_ETHREAD *,_NDIS_NSI_CLIENT_INFO *)

- ea: `0x140046cb0`
- end: `0x140046f82`
- name: `?ndisGetNsiClientInfoForThread@@YAXPEAU_ETHREAD@@PEAU_NDIS_NSI_CLIENT_INFO@@@Z`
- size: `722`
- prototype: `void __fastcall(PETHREAD Thread, struct _NDIS_NSI_CLIENT_INFO *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14013bc44`

## callees

- `0x140046cb0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140046d1d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046d8e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046d1d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140046d8e`
- `ntoskrnl!ObfDereferenceObject` at `0x140046f71`
- `ntoskrnl!ObfDereferenceObject` at `0x140046f71`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046e55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046f25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046e55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140046f25`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046e02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046ef6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046e02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140046ef6`
- `ntoskrnl!SeQueryInformationToken` at `0x140046e75`
- `ntoskrnl!SeQueryInformationToken` at `0x140046eb0`
- `ntoskrnl!SeQueryInformationToken` at `0x140046e75`
- `ntoskrnl!SeQueryInformationToken` at `0x140046eb0`
- `ntoskrnl!PsGetThreadProperty` at `0x140046cda`
- `ntoskrnl!PsGetThreadProperty` at `0x140046cda`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046f42`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046f53`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046f42`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140046f53`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046d43`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046db4`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046d43`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140046db4`
- `ntoskrnl!PsGetThreadSessionId` at `0x140046d5e`
- `ntoskrnl!PsGetThreadSessionId` at `0x140046dcf`
- `ntoskrnl!PsGetThreadSessionId` at `0x140046d5e`
- `ntoskrnl!PsGetThreadSessionId` at `0x140046dcf`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140046e86`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140046ec1`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140046e86`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140046ec1`

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
          if ( v8 < dword_14011C898 )
          {
            v20 = 0;
            v21 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
            if ( v8 < dword_14011C898 )
              v20 = *((_DWORD *)qword_14011C8E8 + 6 * v8);
            KeReleaseSpinLock(&qword_14011C8E0, v21);
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
  v16 = qword_14011C9D8;
  v17 = 0;
  while ( v16 != (struct _NDIS_IF_COMPARTMENT_BLOCK *)&qword_14011C9D8 )
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
0x140046cb0  push    rdi
0x140046cb2  sub     rsp, 50h
0x140046cb6  xorps   xmm0, xmm0
0x140046cb9  mov     [rsp+58h+var_18], rbp
0x140046cbe  movups  xmmword ptr [rdx], xmm0
0x140046cc1  xor     eax, eax
0x140046cc3  mov     [rsp+58h+var_28], r14
0x140046cc8  mov     [rdx+10h], rax
0x140046ccc  mov     rdi, rdx
0x140046ccf  mov     edx, 6D43644Eh; Key
0x140046cd4  xor     r8d, r8d; Flags
0x140046cd7  mov     rbp, rcx
0x140046cda  call    cs:__imp_PsGetThreadProperty
0x140046ce1  nop     dword ptr [rax+rax+00h]
0x140046ce6  xor     r14d, r14d
0x140046ce9  test    rax, rax
0x140046cec  jnz     loc_140046F64
0x140046cf2  mov     [rdi], r14
0x140046cf5  cmp     [rdi+4], r14d
0x140046cf9  jnz     loc_140046DFB
0x140046cff  mov     [rsp+58h+var_10], rbx
0x140046d04  mov     [rsp+58h+var_20], rsi
0x140046d09  mov     [rsp+58h+CopyOnOpen], r14b
0x140046d0e  mov     [rsp+58h+EffectiveOnly], r14b
0x140046d13  mov     [rsp+58h+ImpersonationLevel], r14d
0x140046d18  mov     [rsp+58h+TokenInformation], r14
0x140046d1d  call    cs:__imp_KeGetCurrentIrql
0x140046d24  nop     dword ptr [rax+rax+00h]
0x140046d29  cmp     al, 2
0x140046d2b  jnb     loc_140046F42
0x140046d31  lea     r9, [rsp+58h+ImpersonationLevel]; ImpersonationLevel
0x140046d36  mov     rcx, rbp; Thread
0x140046d39  lea     r8, [rsp+58h+EffectiveOnly]; EffectiveOnly
0x140046d3e  lea     rdx, [rsp+58h+CopyOnOpen]; CopyOnOpen
0x140046d43  call    cs:__imp_PsReferenceImpersonationToken
0x140046d4a  nop     dword ptr [rax+rax+00h]
0x140046d4f  mov     rsi, rax
0x140046d52  test    rax, rax
0x140046d55  jnz     loc_140046E68
0x140046d5b  mov     rcx, rbp
0x140046d5e  call    cs:__imp_PsGetThreadSessionId
0x140046d65  nop     dword ptr [rax+rax+00h]
0x140046d6a  mov     ebx, eax
0x140046d6c  cmp     ebx, 0FFFFFFFFh
0x140046d6f  jnz     short loc_140046DDD
0x140046d71  mov     rsi, gs:188h
0x140046d7a  mov     [rsp+58h+CopyOnOpen], r14b
0x140046d7f  mov     [rsp+58h+EffectiveOnly], r14b
0x140046d84  mov     [rsp+58h+ImpersonationLevel], r14d
0x140046d89  mov     [rsp+58h+TokenInformation], r14
0x140046d8e  call    cs:__imp_KeGetCurrentIrql
0x140046d95  nop     dword ptr [rax+rax+00h]
0x140046d9a  cmp     al, 2
0x140046d9c  jnb     loc_140046F53
0x140046da2  lea     r9, [rsp+58h+ImpersonationLevel]; ImpersonationLevel
0x140046da7  mov     rcx, rsi; Thread
0x140046daa  lea     r8, [rsp+58h+EffectiveOnly]; EffectiveOnly
0x140046daf  lea     rdx, [rsp+58h+CopyOnOpen]; CopyOnOpen
0x140046db4  call    cs:__imp_PsReferenceImpersonationToken
0x140046dbb  nop     dword ptr [rax+rax+00h]
0x140046dc0  mov     rbp, rax
0x140046dc3  test    rax, rax
0x140046dc6  jnz     loc_140046EA3
0x140046dcc  mov     rcx, rsi
0x140046dcf  call    cs:__imp_PsGetThreadSessionId
0x140046dd6  nop     dword ptr [rax+rax+00h]
0x140046ddb  mov     ebx, eax
0x140046ddd  cmp     ebx, cs:dword_14011C898
0x140046de3  jb      loc_140046EEC
0x140046de9  mov     eax, 1
0x140046dee  mov     rsi, [rsp+58h+var_20]
0x140046df3  mov     rbx, [rsp+58h+var_10]
0x140046df8  mov     [rdi+4], eax
0x140046dfb  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140046e02  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140046e09  nop     dword ptr [rax+rax+00h]
0x140046e0e  mov     r8d, [rdi+4]
0x140046e12  lea     r10, qword_14011C9D8
0x140046e19  mov     rcx, cs:qword_14011C9D8
0x140046e20  mov     r9, r14
0x140046e23  mov     r14, [rsp+58h+var_28]
0x140046e28  mov     rbp, [rsp+58h+var_18]
0x140046e2d  cmp     rcx, r10
0x140046e30  jz      short loc_140046E3F
0x140046e32  cmp     [rcx+10h], r8d
0x140046e36  jnz     loc_140046EDE
0x140046e3c  mov     r9, rcx
0x140046e3f  movups  xmm0, xmmword ptr [r9+694h]
0x140046e47  movzx   edx, al; NewIrql
0x140046e4a  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140046e51  movups  xmmword ptr [rdi+8], xmm0
0x140046e55  call    cs:__imp_KeReleaseSpinLock
0x140046e5c  nop     dword ptr [rax+rax+00h]
0x140046e61  add     rsp, 50h
0x140046e65  pop     rdi
0x140046e66  retn
0x140046e68  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x140046e6d  mov     edx, 0Ch; TokenInformationClass
0x140046e72  mov     rcx, rsi; Token
0x140046e75  call    cs:__imp_SeQueryInformationToken
0x140046e7c  nop     dword ptr [rax+rax+00h]
0x140046e81  mov     rcx, rsi; ImpersonationToken
0x140046e84  mov     ebx, eax
0x140046e86  call    cs:__imp_PsDereferenceImpersonationToken
0x140046e8d  nop     dword ptr [rax+rax+00h]
0x140046e92  test    ebx, ebx
0x140046e94  js      loc_140046D5B
0x140046e9a  mov     ebx, dword ptr [rsp+58h+TokenInformation]
0x140046e9e  jmp     loc_140046D6C
0x140046ea3  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x140046ea8  mov     edx, 0Ch; TokenInformationClass
0x140046ead  mov     rcx, rbp; Token
0x140046eb0  call    cs:__imp_SeQueryInformationToken
0x140046eb7  nop     dword ptr [rax+rax+00h]
0x140046ebc  mov     rcx, rbp; ImpersonationToken
0x140046ebf  mov     ebx, eax
0x140046ec1  call    cs:__imp_PsDereferenceImpersonationToken
0x140046ec8  nop     dword ptr [rax+rax+00h]
0x140046ecd  test    ebx, ebx
0x140046ecf  js      loc_140046DCC
0x140046ed5  mov     ebx, dword ptr [rsp+58h+TokenInformation]
0x140046ed9  jmp     loc_140046DDD
0x140046ede  ja      loc_140046E3F
0x140046ee4  mov     rcx, [rcx]
0x140046ee7  jmp     loc_140046E2D
0x140046eec  lea     rcx, qword_14011C8E0; SpinLock
0x140046ef3  mov     esi, r14d
0x140046ef6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140046efd  nop     dword ptr [rax+rax+00h]
0x140046f02  cmp     ebx, cs:dword_14011C898
0x140046f08  jnb     short loc_140046F1B
0x140046f0a  mov     edx, ebx
0x140046f0c  lea     r8, [rdx+rdx*2]
0x140046f10  mov     rdx, cs:qword_14011C8E8
0x140046f17  mov     esi, [rdx+r8*8]
0x140046f1b  movzx   edx, al; NewIrql
0x140046f1e  lea     rcx, qword_14011C8E0; SpinLock
0x140046f25  call    cs:__imp_KeReleaseSpinLock
0x140046f2c  nop     dword ptr [rax+rax+00h]
0x140046f31  mov     eax, 1
0x140046f36  test    esi, esi
0x140046f38  cmovz   esi, eax
0x140046f3b  mov     eax, esi
0x140046f3d  jmp     loc_140046DEE
0x140046f42  call    cs:__imp_PsGetCurrentProcessSessionId
0x140046f49  nop     dword ptr [rax+rax+00h]
0x140046f4e  jmp     loc_140046D6A
0x140046f53  call    cs:__imp_PsGetCurrentProcessSessionId
0x140046f5a  nop     dword ptr [rax+rax+00h]
0x140046f5f  jmp     loc_140046DDB
0x140046f64  mov     ecx, [rax]
0x140046f66  mov     [rdi+4], ecx
0x140046f69  mov     ecx, [rax+4]
0x140046f6c  mov     [rdi], ecx
0x140046f6e  mov     rcx, rax; Object
0x140046f71  call    cs:__imp_ObfDereferenceObject
0x140046f78  nop     dword ptr [rax+rax+00h]
0x140046f7d  jmp     loc_140046CF5
```
