# NdisGetSessionCompartmentId

- ea: `0x140043f70`
- end: `0x1400440a2`
- name: `NdisGetSessionCompartmentId`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140043ac0`
- `0x140043eb0`
- `0x140043f10`
- `0x1400c9a30`

## callees

- `0x140043f70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140043fa2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140043fa2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044074`
- `ntoskrnl!KeReleaseSpinLock` at `0x140044074`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044045`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044045`
- `ntoskrnl!SeQueryInformationToken` at `0x140044015`
- `ntoskrnl!SeQueryInformationToken` at `0x140044015`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140044091`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140044091`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043fc8`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140043fc8`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043fdf`
- `ntoskrnl!PsGetThreadSessionId` at `0x140043fdf`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140044026`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140044026`

## pseudocode

```c
__int64 __fastcall NdisGetSessionCompartmentId(unsigned int a1)
{
  unsigned int v1; // ebx
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v3; // rcx
  PACCESS_TOKEN v4; // rax
  void *v5; // rsi
  unsigned int CurrentProcessSessionId; // eax
  NTSTATUS v8; // ebx
  unsigned int v9; // edi
  KIRQL v10; // al
  unsigned __int8 EffectiveOnly; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+58h] [rbp+10h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp+18h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v1 = a1;
  if ( a1 == -1 )
  {
    CurrentThread = KeGetCurrentThread();
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId(v3);
    }
    else
    {
      v4 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v5 = v4;
      if ( v4 )
      {
        v8 = SeQueryInformationToken(v4, TokenSessionId, &TokenInformation);
        PsDereferenceImpersonationToken(v5);
        if ( v8 >= 0 )
        {
          v1 = (unsigned int)TokenInformation;
          goto LABEL_6;
        }
      }
      CurrentProcessSessionId = PsGetThreadSessionId(CurrentThread);
    }
    v1 = CurrentProcessSessionId;
  }
LABEL_6:
  if ( v1 >= dword_14011C898 )
    return 1;
  v9 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc(&qword_14011C8E0);
  if ( v1 < dword_14011C898 )
    v9 = *((_DWORD *)qword_14011C8E8 + 6 * v1);
  KeReleaseSpinLock(&qword_14011C8E0, v10);
  if ( !v9 )
    return 1;
  return v9;
}

```

## disassembly

```asm
0x140043f70  push    rbx
0x140043f72  push    rbp
0x140043f73  push    rdi
0x140043f74  sub     rsp, 30h
0x140043f78  xor     ebp, ebp
0x140043f7a  mov     [rsp+48h+var_20], rsi
0x140043f7f  mov     ebx, ecx
0x140043f81  cmp     ecx, 0FFFFFFFFh
0x140043f84  jnz     short loc_140043FED
0x140043f86  mov     rdi, gs:188h
0x140043f8f  mov     [rsp+48h+CopyOnOpen], bpl
0x140043f94  mov     [rsp+48h+EffectiveOnly], bpl
0x140043f99  mov     [rsp+48h+ImpersonationLevel], ebp
0x140043f9d  mov     [rsp+48h+TokenInformation], rbp
0x140043fa2  call    cs:__imp_KeGetCurrentIrql
0x140043fa9  nop     dword ptr [rax+rax+00h]
0x140043fae  cmp     al, 2
0x140043fb0  jnb     loc_140044091
0x140043fb6  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140043fbb  mov     rcx, rdi; Thread
0x140043fbe  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140043fc3  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140043fc8  call    cs:__imp_PsReferenceImpersonationToken
0x140043fcf  nop     dword ptr [rax+rax+00h]
0x140043fd4  mov     rsi, rax
0x140043fd7  test    rax, rax
0x140043fda  jnz     short loc_140044008
0x140043fdc  mov     rcx, rdi
0x140043fdf  call    cs:__imp_PsGetThreadSessionId
0x140043fe6  nop     dword ptr [rax+rax+00h]
0x140043feb  mov     ebx, eax
0x140043fed  cmp     ebx, cs:dword_14011C898
0x140043ff3  mov     rsi, [rsp+48h+var_20]
0x140043ff8  jb      short loc_14004403C
0x140043ffa  mov     eax, 1
0x140043fff  add     rsp, 30h
0x140044003  pop     rdi
0x140044004  pop     rbp
0x140044005  pop     rbx
0x140044006  retn
0x140044008  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x14004400d  mov     edx, 0Ch; TokenInformationClass
0x140044012  mov     rcx, rsi; Token
0x140044015  call    cs:__imp_SeQueryInformationToken
0x14004401c  nop     dword ptr [rax+rax+00h]
0x140044021  mov     rcx, rsi; ImpersonationToken
0x140044024  mov     ebx, eax
0x140044026  call    cs:__imp_PsDereferenceImpersonationToken
0x14004402d  nop     dword ptr [rax+rax+00h]
0x140044032  test    ebx, ebx
0x140044034  js      short loc_140043FDC
0x140044036  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x14004403a  jmp     short loc_140043FED
0x14004403c  lea     rcx, qword_14011C8E0; SpinLock
0x140044043  mov     edi, ebp
0x140044045  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004404c  nop     dword ptr [rax+rax+00h]
0x140044051  cmp     ebx, cs:dword_14011C898
0x140044057  jnb     short loc_14004406A
0x140044059  mov     edx, ebx
0x14004405b  lea     r8, [rdx+rdx*2]
0x14004405f  mov     rdx, cs:qword_14011C8E8
0x140044066  mov     edi, [rdx+r8*8]
0x14004406a  movzx   edx, al; NewIrql
0x14004406d  lea     rcx, qword_14011C8E0; SpinLock
0x140044074  call    cs:__imp_KeReleaseSpinLock
0x14004407b  nop     dword ptr [rax+rax+00h]
0x140044080  mov     eax, 1
0x140044085  test    edi, edi
0x140044087  cmovz   edi, eax
0x14004408a  mov     eax, edi
0x14004408c  jmp     loc_140043FFF
0x140044091  call    cs:__imp_PsGetCurrentProcessSessionId
0x140044098  nop     dword ptr [rax+rax+00h]
0x14004409d  jmp     loc_140043FEB
```
